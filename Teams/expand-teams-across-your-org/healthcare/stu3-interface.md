---
title: Patients App and EHR integration STU3 interface
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
description: Microsoft Teams Patients アプリと STU3 インターフェイスの仕様に電子健康記録を統合する方法について説明します。
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4e20619badb2509d0a90f396563a98796e718e2f
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803495"
---
# <a name="stu3-interface-specification"></a>STU3 インターフェイスの仕様

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
- [お薬に](#medication-request) 関する声明 (DSTU2 バージョンの PatientsApp のOrder を置き換える)
- 場所 (このリソースに必要な情報は Encounter に含まれます)

> [!NOTE]
> Patient リソースは唯一の必須リソースです (アプリが読み込めずに)。ただし、パートナーは、以下に示す仕様に従って上記のすべてのリソースのサポートを実装し、Microsoft Teams Patients アプリを使用した最適なエクスペリエンスを実現Microsoft Teams勧めします。

Microsoft Teams Patients アプリからの複数のリソースに対するクエリは、FHIR サーバーの URL に要求のバンドル (BATCH) を投稿する必要があります。 サーバーは各要求を処理し、各要求に一致するリソースのバンドルを返します。 詳細と例については、 を参照してください [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) 。

## <a name="capability-statement"></a>Capability ステートメント

必須の最小フィールドを次に示します。

 - REST

    - モード
    - 対話
    - リソース: 型
    - セキュリティ: [OAuth URI の拡張機能](https://hl7.org/fhir/extension-oauth-uris.html)
    
 - FhirVersion (このコードでは、ピボットするバージョンを理解するためにこれを必要とします)。

この [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) フィールド セットのその他の詳細については、 を参照してください。

## <a name="patient"></a>患者

Argonaut 患者プロファイル フィールドのサブセットである最小必須フィールドを次に示します。

 - Name.Given
 - Name.Family
 - 性別
 - BirthDate
 - MRN (識別子)

[Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)フィールドに加えて、患者アプリは次のフィールドを読み取って、ユーザー エクスペリエンスを向上できます。

 - Name.Use
 - Name.Prefix
 - [GeneralPractitioner] - GeneralPractitioner の参照は、患者リソースに含める必要があります (表示フィールドのみ)

リソース検索では、/Patient/_search の POST メソッドと次のパラメーターを使用します。

 - id
 - family=(ファミリ名に値が含まれるすべての患者を検索します)
 - given=\<substring>
 - birthdate=(完全一致)
 - gender=(管理性別の 1 つである値)
 - \_count (返される結果の最大数) <br> 応答には、検索の結果として返されるレコードの総数が含まれている必要があります。返されるレコードの数を制限するために、PatientsApp によってカウントが \_ 使用されます。
 - identifier=\<mrn>

目標は、次の方法で患者を検索してフィルター処理できる状態に設定します。

- ID: これは、FHIR のすべてのリソースが持つリソース ID です。
- MRN: これは、医療スタッフが知る患者の実際の識別子です。 この MRN は、FHIR の識別子リソース内の識別子の種類に基づくと理解しています。
- 名前
- 生年月日

呼び出しの次の例を参照してください。

```
Request:
POST <fhir-server>/Patient/_search
Request Body:
given=ruth&family=black

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "meta": {
    "lastUpdated": "2019-01-14T23:44:45.052+00:00"
  },
  "type": "searchset",
  "total": 1,
  "link": [
    {
      "relation": "self",
      "url": <fhir-server>/Patient/_search"
    }
  ],
  "entry": [
    {
      "fullUrl": <fhir-server>/Patient/<patient-id>",
      "resource": {
        "resourceType": "Patient",
        "id": "<patient-id>",
        "meta": {
          "versionId": "1",
          "lastUpdated": "2017-10-18T18:32:37.000+00:00"
        },
        "text": {
          "status": "generated",
          "div": "<div>\n        <p>Ruth Black</p>\n      </div>"
        },
        "identifier": [
          {
            "use": "usual",
            "type": {
              "coding": [
                {
                  "system": "https://hl7.org/fhir/v2/0203",
                  "code": "MR",
                  "display": "Medical record number",
                  "userSelected": false
                }
              ],
              "text": "Medical record number"
            },
            "system": "http://hospital.smarthealthit.org",
            "value": "1234567"
          }
        ],
        "active": true,
        "name": [
          {
            "use": "official",
            "family": "Black",
            "given": [
              "Ruth",
              "C."
            ]
          }
        ],
        "telecom": [
          {
            "system": "phone",
            "value": "800-599-2739",
            "use": "home"
          },
          {
            "system": "phone",
            "value": "800-808-7785",
            "use": "mobile"
          },
          {
            "system": "email",
            "value": "ruth.black@example.com"
          }
        ],
        "gender": "female",
        "birthDate": "1951-08-23",
        "address": [
          {
            "use": "home",
            "line": [
              "26 South RdApt 22"
            ],
            "city": "Sapulpa",
            "state": "OK",
            "postalCode": "74066",
            "country": "USA"
          }
        ]
      },
      "search": {
        "mode": "match"
      }
    }
  ]
}
```

```
Request:
GET <fhir-server>/Patient/<patient-id>

Response:
{
  "resourceType": "Patient",
  "id": "<patient-id>",
  "identifier": [
    {
      "use": "usual",
      "type": {
        "coding": [
          {
            "system": "https://hl7.org/fhir/v2/0203",
            "code": "MR",
          }
        ],
        "text": "Medical record number"
      },
      "value": "1234567"
    }
  ],
  "name": [
    {
      "use": "official",
      "family": "Adams",
      "given": [ "Daniel", "X." ]
    }
  ],
  "gender": "male",
  "birthDate": "1925-12-23",
}
```

この [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) フィールド セットのその他の詳細については、 を参照してください。

## <a name="observation"></a>観察

これらは必須の最小フィールドです。これは、Argonaut プロファイルの [サブセットVital-Signsです](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)。

 - 有効 (日付の時刻または期間)
 - Code.Coding.Code
 - ValueQuantity.Value

Argonaut フィールドに加えて、ユーザー エクスペリエンスを向上するために、Patients アプリは次のフィールドも読み取り可能です。

 - Code.Coding.Display
 - ValueQuantity.Unit

リソース検索では、GET メソッドと次のパラメーターを使用します。

 - patient=\<patient id>
 - _sort=-date
 - category ("category=vital-signs" をクエリして、バイタル サインの一覧を取得します。

呼び出しの次の例を参照してください。

```
Request:
GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs

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
        "category": [
          {
            "coding": [
              {
                "system": "https://hl7.org/fhir/observation-category",
                "code": "vital-signs"
              }
            ],
          }
        ],
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "8867-4",
              "display": "heart_rate"
            }
          ]
        },
        "effectiveDateTime": "2009-04-08T00:00:00-06:00",
        "valueQuantity": {
          "value": 72.0,
          "unit": "{beats}/min",
          "system": "http://unitsofmeasure.org",
        }
      }
    },
    .
    .
    .
  ]
}
```

この [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) フィールド セットのその他の詳細については、 を参照してください。

## <a name="condition"></a>状態

Argonaut 条件プロファイルのサブセットである最小必須 [フィールドを次に示します](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)。

 - Code.Coding[0].表示

Argonaut フィールドに加えて、ユーザー エクスペリエンスを向上するために、Patients アプリは次のフィールドも読み取り可能です。

 - AssertedDate
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
  "total": 2,
  "entry": [
    {
      "resource": {
        "resourceType": "Condition",
        "id": "<resource-id>",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "185903001",
              "display": "Needs influenza immunization",
            }
          ]
        },
        "severity": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "24484000",
              "display": "Severe"
            }
          ]
        },
        "assertedDate": "2018-04-04"
      }
    },
    .
    .
    .
  ]
}
```

この [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) フィールド セットのその他の詳細については、 を参照してください。

## <a name="encounter"></a>Encounter

これらは、US [Core Encounter](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) プロファイルの "必要な" フィールドのサブセットである最小必須フィールドです。

 - 状態
 - 「[0]」と入力します。Coding[0].表示

さらに、US Core Encounter プロファイルの "サポートが必要" フィールドの次のフィールドも表示されます。

 - Period.Start
 - Location[0].Location.Display

リソース検索では、GET メソッドと次のパラメーターを使用します。

 - patient=\<patient id>
 - _sort:desc=\<field ex. date>
 - _count=\<max results>

目標は、患者の最後の既知の場所を取得できる点です。 各エンカウンターは、場所リソースを参照します。 参照には、場所の表示フィールドも含める必要があります。

この [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) フィールド セットのその他の詳細については、 を参照してください。

## <a name="allergyintolerance"></a>分性Intolerance

次に示すのは必須の最小フィールドです。 [これは、Argonautいしなやかプロファイルのサブセット](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) です。

 - Code.Text
 - Code.Coding[0].表示
 - ClinicalStatus/VerificationStatus (両方を読み取る)

Argonaut フィールドに加えて、ユーザー エクスペリエンスを向上するために、Patients アプリは次のフィールドも読み取り可能です。

 - AssertedDate
 - Note.Text
 - リアクション
    - Substance (1 つのコーディング要素)
    - 症状 (1 つのコーディング要素)

リソース検索では、GET メソッドと次のパラメーターを使用します。

 - Patient =  \<patient id>

呼び出しの次の例を参照してください。 

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
        "clinicalStatus": "active",
        "verificationStatus": "confirmed",
        "code": {
          "coding": [
            {
              "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",
              "code": "N0000175503",
              "display": "sulfonamide antibacterial",
            }
          ],
          "text": "sulfonamide antibacterial"
        },
        "assertedDate": "2018-01-01T00:00:00-07:00",
        "reaction": [
          {
            "manifestation": [
              {
                "coding": [
                  {
                    "system": "http://snomed.info/sct",
                    "code": "271807003",
                    "display": "skin rash",
                  }
                ],
                "text": "skin rash"
              }
            ],
          }
        ]
      }
    }
  ]
}
```

この [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) フィールド セットのその他の詳細については、 を参照してください。

## <a name="medication-request"></a>薬の要求

これらは必須の最小フィールドです。これは [、US Coreの核薬要求プロファイルのサブセットです](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)。

 - しだい.Display (参考の場合)
 - (CodableConcept の場合)
 - AuthoredOn
 - Requester.Agent.Display

US Core フィールドに加えて、ユーザー エクスペリエンスを向上するために、Patients アプリは次のフィールドも読み取り可能です。

 - ストラクター [...]。テキスト
 - テキスト

リソース検索では、GET メソッドと次のパラメーターを使用します。

 - patient=\<patient id>
 - _count=\<max results>

この [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) フィールド セットのその他の詳細については、 を参照してください。

## <a name="coverage"></a>対象範囲

これらは必須の最小フィールドで、US Core プロファイルまたは Argonaut プロファイルの対象外です。

 - グループ化、少なくとも 1 つの要素
    - GroupDisplay
    - PlanDisplay
 - 期間
 - SubscriberId

リソース検索では、GET メソッドと次のパラメーターを使用します。

 - Patient = \<patient id>

この [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) フィールド セットのその他の詳細については、 を参照してください。
