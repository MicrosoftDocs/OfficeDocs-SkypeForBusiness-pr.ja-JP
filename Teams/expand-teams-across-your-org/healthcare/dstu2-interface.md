---
title: Patients App and EHR integration DSTU2 interface
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Teams で DSTU2 インターフェイスの仕様について説明します。Microsoft Teams Patients アプリで動作する FHIR サーバーの設定や再構成などです。
ms.custom: seo-marvel-mar2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 12833ea55977cf7e8d18ee5c10b1f17d898b27b3
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803485"
---
# <a name="dstu2-interface-specification"></a>DSTU2 インターフェイスの仕様

> [!NOTE]
> 2020 年 10 月 30 日より、患者アプリは廃止され、Teams の[リスト アプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)に置き換えられました。 患者アプリのデータは、チームを支援する Office 365 グループのグループ メールボックスに保存されます。 患者アプリに関連付けられているすべてのデータはこのグループに保持されますが、ユーザー インターフェイスからアクセスすることはできなくなります。 ユーザーは、[リスト アプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)を使用してリストを再作成できます。
>
>リストを使用すると、医療機関のケア チームは、ラウンドや学際的なチーム会議から一般的な患者の監視に至るまでのシナリオで患者リストを作成できます。 開始するには、リストの患者テンプレートを確認してください。 組織でリスト アプリを管理する方法の詳細については、「[リスト アプリの管理](../../manage-lists-app.md)」を参照してください。

Microsoft Teams Patients アプリで動作する FHIR サーバーを設定または再構成するには、アプリがアクセスする必要があるデータを理解する必要があります。 FHIR サーバーは、次のリソースのバンドルを使用した POST 要求をサポートする必要があります。

- [患者](#patient)
- [観察](#observation)
- [状態](#condition)
- [Encounter](#encounter)
- [取り込み中の容容性](#allergyintolerance)
- [対象範囲](#coverage)
- [薬の順序](#medication-order)
- [場所](#location)

> [!NOTE]
> Patient リソースは唯一の必須リソースです (アプリが読み込めずに)。 ただし、パートナーは、以下に示す仕様に従って上記のすべてのリソースのサポートを実装し、Microsoft Teams Patients アプリを使用した最適なエクスペリエンスを実現Microsoft Teams勧めします。

FHIR サーバー Microsoft Teams要求のバンドル (BATCH) 後に複数のリソースについて、Microsoft Teams Patients アプリからクエリを実行します。 サーバーは各要求を処理し、各要求に一致するリソースのバンドルを返します。 詳細と例については、 を参照してください [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) 。

次のすべての FHIR リソースには、直接リソース参照でアクセスできる必要があります。

## <a name="conformance-minimum-required-field-set"></a>準拠の最小必須フィールド セット

 FHIR Server は、機能の概要を実際に説明するために、準拠ステートメントを実装する必要があります。 DSTU2 FHIR サーバーでは、次のパラメーターが必要です。

 - REST

    - モード
    - 対話
    - リソース: 型
    - セキュリティ: [OAuth URI の拡張機能](https://hl7.org/fhir/extension-oauth-uris.html)
   
 - FhirVersion (複数のバージョンをサポートする場合、どのバージョンにピボットする必要があるのか理解するには、このコードが必要です)。

この [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) フィールド セットのその他の詳細については、 を参照してください。

## <a name="patient"></a>患者

これらは [、Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) 患者プロファイル フィールドのサブセットである最小必須フィールドです。

 - Name.Family
 - Name.Given
 - 性別
 - BirthDate
 - MRN (識別子)

Argonaut フィールドに加えて、ユーザー エクスペリエンスを向上するために、Patients アプリでは次のフィールドも読み上げられます。

 - Name.Use
 - Name.Prefix
 - CareProvider (Patient リソースのこの参照には、次の例に示す表示フィールドを含める必要があります)。

    ```
    Request:
    GET <fhir-server>/Patient/<patient-id>
    
    Response:
    {
      "resourceType": "Patient",
      "id": "<patient-id>",
      .
      .
      .
      "name": [
        {
          "use": "official",
          "prefix": [ "Mr" ],
          "family": [ "Chau" ],
          "given": [ "Hugh" ]
        }
      ],
      "identifier": [
        {
          "use": "official",
          "type": {
            "coding": [
              {
                "system": "https://hl7.org/fhir/v2/0203",
                "code": "MR"
              }
            ]
          },
          "value": "1234567"
        }
      ],
      "gender": "male",
      "birthDate": "1957-06-05",
      "careProvider": [{ "display": "Jane Doe" }],
    }
    ```

リソース検索では、/Patient/_search の POST メソッドと次のパラメーターを使用します。

 - id
 - family:contains=(家族名に値が含まれているすべての患者を検索します)。
 - given=\<substring>
 - name=\<substring>
 - birthdate=(完全一致)
 - \_count (返される結果の最大数) <br> 応答には、検索の結果として返されたレコードの総数を含める必要があります。Count は、PatientsApp によって返されるレコードの数を制限するために \_ 使用されます。
 - identifier=\<mrn>

目標は、次の方法で患者を検索してフィルター処理できる状態に設定します。

- ID: これは、FHIR のすべてのリソースが持つリソース ID です。
- MRN: これは、医療スタッフが知る患者の実際の識別子です。 この MRN は、FHIR の識別子リソース内の識別子の種類に基づくと理解しています
- 名前
- 生年月日

この呼び出しの次の例を参照してください。

```
Request:
POST <fhir-server>/Patient/_search
Request Body:
given=hugh&family=chau

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  .
  .
  .
  "entry": [
    {
      "resource": {
        "resourceType": "Patient",
        "id": "<patient-id>",
        "name": [
          {
            "text": "Hugh Chau",
            "family": [ "Chau" ],
            "given": [ "Hugh" ]
          }
        ],
        "gender": "male",
        "birthDate": "1957-06-05"
      },
      "search": {
        "mode": "match"
      }
    }
  ]
}
```

この [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) フィールド セットのその他の詳細については、 を参照してください。

## <a name="observation"></a>観察

これらは、Argonaut バイタサイン プロファイルのサブセットである最小必須フィールドです。

 - 有効 (日付の時刻または期間)
 - Code.Coding.Code
 - ValueQuantity.Value

Argonaut フィールドに加えて、ユーザー エクスペリエンスを向上するために、Patients アプリでは次のフィールドも読み上げられます。

 - Code.Coding.Display
 - ValueQuantity.Unit

コンポーネントの観察を使用する場合は、各コンポーネントの観察に同じロジックが適用されます。

リソース検索では、GET メソッドと次のパラメーターを使用します。

 - patient=\<patient id\>
 - sort:desc=\<field ex. date\>

目標は、患者の最新の重要な兆候 [VitalSigns.DSTU.saz] (観察?) を取得できる点です。

```
Request:
GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 20,
  "entry": [
    {
      "resource": {
        "resourceType": "Observation",
        "id": "<resource-id>",
        "category": {
          "coding": [ { code": "vital-signs" } ],
        },
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "39156-5",
              "display": "bmi"
            }
          ],
        },
        "effectiveDateTime": "2009-12-01",
        "valueQuantity": {
          "value": 34.4,
          "unit": "kg/m2",
          "system": "http://unitsofmeasure.org",
          "code": "kg/m2"
        }
      },
    },
    .
    .
    .
  ]
}
```

この [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) フィールド セットのその他の詳細については、 を参照してください。

## <a name="condition"></a>状態

これらは、Argonaut 条件プロファイルのサブセットである最小 [必須フィールドです](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)。

1. Code.Coding[0].表示

Argonaut フィールドに加えて、ユーザー エクスペリエンスを向上するために、Patients アプリは次のフィールドも読み取り可能です。

 - 記録日
 - 重大度

リソース検索では、GET メソッドと次のパラメーターを使用します。

 - patient=\<patient id>
 - _count=\<max results>

この呼び出しの次の例を参照してください。

```
Request:
GET <fhir-server>/Condition?patient=<patient-id>&_count=10

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "Condition",
        "id": "<resource-id>",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "386033004",
              "display": "Neuropathy (nerve damage)"
            }
          ]
        },
        "dateRecorded": "2018-09-17",
        "severity": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "24484000",
              "display": "Severe"
            }
          ]
        }
      },
    }
  ]
}
```

この [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) フィールド セットのその他の詳細については、 を参照してください。

## <a name="encounter"></a>Encounter

これらは、US Core Encounter プロファイルの "must have" フィールドのサブセットである最小必須フィールドです。

 - 状態
 - 「[0]」と入力します。Coding[0].表示

さらに、US Core Encounter プロファイルの "サポートが必要" フィールドの次のフィールド

 - Period.Start
 - Location[0].Location.Display

リソース検索では、GET メソッドと次のパラメーターを使用します。

 - patient=\<patient id>
 - _sort:desc=\<field ex. date>
 - _count=\<max results>

目標は、患者の最後の既知の場所を取得できる点です。 各エンカウンターは、場所リソースを参照します。 参照には、場所の表示フィールドも含める必要があります。 この呼び出しの次の例を参照してください。

```
Request:
GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1

Response:
{
  "resourceType": "Bundle",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "Encounter",
        "id": "<resource-id>",
        "identifier": [{ "use": "official", "value": "<id>" }],
        "status": "arrived",
        "type": [
          {
            "coding": [{ "display": "Appointment" }],
          }
        ],
        "patient": { "reference": "Patient/<patient-id>" },
        "period": { "start": "09/17/2018 1:00:00 PM" },
        "location": [
          {
            "location": { "display": "Clinic - ENT" },
          }
        ]
      }
    }
  ]
}
```

この [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) フィールド セットのその他の詳細については、 を参照してください。

## <a name="allergyintolerance"></a>分性Intolerance

次に示すのは必須の最小フィールドです。これは、Argonautいしなやかプロファイルのサブセットです。

 - Code.Text
 - Code.Coding[0].表示
 - 状態

Argonaut フィールドに加えて、ユーザー エクスペリエンスを向上するために、Patients アプリでは次のフィールドも読み上げられます。

 - RecordedDate
 - Note.Text
 - Reaction[..].Substance.Text
 - Reaction[..].[..].テキスト
 - Text.Div

リソース検索では、GET メソッドと次のパラメーターを使用します。

 - Patient =  \<patient id>

この呼び出しの次の例を参照してください。

```
Request:
GET <fhir-server>/AllergyIntolerance?patient=<patient-id>

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "AllergyIntolerance",
        "id": "<resource-id>",
        "recordedDate": "2018-09-17T07:00:00.000Z",
        "substance": {
          "text": "Cashew nuts"
        },
        "status": "confirmed",
        "reaction": [
          {
            "substance": {
              "text": "cashew nut allergenic extract Injectable Product"
            },
            "manifestation": [
              {
                "text": "Anaphylactic reaction"
              }
            ]
          }
        ]
      }
    }
  ]
}
```

この [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) フィールド セットのその他の詳細については、 を参照してください。

## <a name="medication-order"></a>薬の順序

これらは、ArgonautOrder プロファイルのサブセットである最小必須フィールドです。

 - DateWritten
 - Prescriber.Display
 - しだい.Display (参考資料の場合)
 - しだい.Text (概念の場合)

Argonaut フィールドに加えて、ユーザー エクスペリエンスを向上するために、Patients アプリは次のフィールドも読み取り可能です。

 - DateEnded
 - ストラクター.Text
 - Text.Div

リソース検索では、GET メソッドと次のパラメーターを使用します。

 - patient=\<patient id>
 - _count=\<max results>

この呼び出しの次の例を参照してください。

```
Request:
GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "MedicationOrder",
        "id": "<resource-id>",
        "dateWritten": "2018-09-17",
        "medicationCodeableConcept": {
          "text": "Lisinopril 20 MG Oral Tablet"
        },
        "prescriber": {
          "display": "Jane Doe"
        },
        "dosageInstruction": [
          {
            "text": "1 daily"
          }
        ]
      }
    }
  ]
}
```

この [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) フィールド セットのその他の詳細については、 を参照してください。

## <a name="coverage"></a>対象範囲

これらは必須の最小フィールドで、US Core プロファイルまたは Argonaut プロファイルの対象外です。

 - Payor

リソース検索では、GET メソッドと次のパラメーターを使用します。

 - patient=\<patient id>

この呼び出しの次の例を参照してください。

```
Request:
GET <fhir-server>/Coverage?patient=<patient-id>

Response:
{
  "resourceType": "Bundle",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "Coverage",
        "id": "<resource-id>",
        "plan": "No Primary Insurance",
        "subscriber": { "reference": "Patient/<patient-id>" }
      }
    }
  ]
}
```
    
この [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) フィールド セットのその他の詳細については、 を参照してください。

## <a name="location"></a>場所

このリソースは、Encounter リソースの参照として [のみ使用](#encounter) されます。

この [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) フィールド セットのその他の詳細については、 を参照してください。
