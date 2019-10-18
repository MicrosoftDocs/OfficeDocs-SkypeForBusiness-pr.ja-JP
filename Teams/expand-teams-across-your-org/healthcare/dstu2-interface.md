---
title: 患者のアプリと EHR の統合 DSTU2 インターフェイス
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Microsoft Teams の患者向けアプリ EHR の統合
ms.openlocfilehash: 179cd031b6e32ee3ed32a6d3be1fa4afaae68cc2
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570371"
---
# <a name="dstu2-interface-specification"></a>DSTU2 インターフェイスの仕様

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Microsoft Teams の患者と連携するように FHIR サーバーを設定または再構成するには、アプリがアクセスする必要があるデータを把握する必要があります。 FHIR サーバーでは、次のリソースについて、バンドルを使った POST 要求をサポートしている必要があります。

- [診療](#patient)
- [観察](#observation)
- [状態](#condition)
- [状況](#encounter)
- [Allergy intolerance](#allergyintolerance)
- [サポート](#coverage)
- [投薬注文](#medication-order)
- [場所](#location)

> [!NOTE]
> 患者リソースは唯一の必須リソースであり、アプリがまったく読み込まれません。 ただし、Microsoft Teams の患者アプリを使用して、最も優れたエンドユーザーエクスペリエンスを実現するために、以下に記載されている仕様ごとに、上記のすべてのリソースのサポートを実装することをお勧めします。

Microsoft Teams の患者アプリから複数のリソースに対するクエリは、FHIR サーバーの URL への要求のバンドル (バッチ) を投稿します。 サーバーは各要求を処理し、各要求によって一致したリソースのバンドルを返します。 詳細と例については[https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction)、「」を参照してください。

以下のすべての FHIR リソースは、直接リソース参照によってアクセスできる必要があります。

## <a name="conformance-minimum-required-field-set"></a>準拠している必要な最小フィールドセット

 FHIR サーバーでは、その機能の事実上の概要を把握するために、準拠のステートメントを実装する必要があります。 DSTU2 FHIR サーバーでは、次のパラメーターが想定されています。

1. 後
   1. Mode
   2. 通信
   3. リソース: 種類
   4. セキュリティ: [OAuth uri 用の拡張子](http://hl7.org/fhir/extension-oauth-uris.html)
2. FhirVersion (Microsoft のコードでは、複数のバージョンをサポートするために、どのバージョンをピボットする必要があるかを理解する必要があります)。

この[https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html)フィールドセットのその他の詳細については、を参照してください。

## <a name="patient"></a>診療

以下は、 [Argonaut の患者プロファイル](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)フィールドのサブセットである、最小の必須フィールドです。

1. 家族
2. 名前。指定された
3. 女性
4. 地
5. MRN (識別子)

優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリも次のフィールドを読み取ります。

1. 名前を指定します。
2. 名前プレフィックス
3. CareProvider (患者リソースのこの参照には、次の例に示す表示フィールドを含める必要があります)。

* * *

    要求: <fhir-server>/Patient/<患者 id> を取得する
    
    応答: {"resourceType": "患者"、"id": "<>"、"
      .
      .
      "name": [{"use": "オフィシャル", "prefix": ["Mr"], "family": ["Chau"], "指定した部分": ["Hugh"]}], "識別子": [{"use": [{"]" と入力 ": {" コード ":"http://hl7.org/fhir/v2/0203"、" "": "", "" ":" "", "" ":" "," "値": "" "," "" "" ":" "", "" "1957-06-05 1234567"," careProvider ": [{" display ":" Jane Doe "}],}

* * *

リソース検索では、/Patient/_search と次のパラメーターで POST メソッドを使います。

1. id
2. ファミリ: contains = (ファミリ名に値が含まれているすべての患者を検索します。)
3. 指定さ\<れた = substring>
4. name =\<substring>
5. 生年月日 = (完全一致)
6. \_count (返される結果の最大数) <br> 応答には、検索結果として返されるレコードの合計数が含まれ\_ている必要があります。カウントは、返されるレコードの数を制限するために PatientsApp によって使用されます。
7. 識別子 =\<mrn>

目標は、次のようにして患者の検索とフィルター処理を行うことができるようにすることです。

- ID: これは、FHIR のすべてのリソースが持つリソース ID です。
- MRN: 診療員が知っている患者の実際の識別子です。 この MRN は、FHIR の識別子リソース内の識別子の種類に基づいていることを理解しています。
- 名前
- 地

この通話の次の例を参照してください。

* * *

    要求 <: fhir-server>/Patient/_search 要求本文: 指定 = hugh&ファミリ = chau
    
    応答: {"resourceType": "バンドル"、"id": "<バンドル id>",。
      .
      .
      "entry": [{"リソース": {"resourceType": "患者"、"id": "<>"、"name": [{"text": "Hugh Chau", "family": ["Chau"], "指定された": ["Hugh"]}, "性別": "男性", "生年月日": "1957-06-05": "検索": {""

* * *

この[https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html)フィールドセットのその他の詳細については、を参照してください。

## <a name="observation"></a>観察

以下は、必須の最小フィールドであり、Argonaut の重要な署名プロファイルのサブセットです。

 1. 発効 (日付と時刻)
 2. コードの記述
 3. Valu不定の値

優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリも次のフィールドを読み取ります。

 1. コード。ディスプレイ
 2. Valuの単位

コンポーネントの所見を使う場合は、各コンポーネントの観測に同じロジックが適用されます。

リソース検索では、GET メソッドと次のパラメーターを使います。

1. 患者 =\<患者 id\>
2. sort: desc =\<フィールドの例 期日\>

目標は、患者の最新のバイタル・サインを取得できるようにすることです (観測された VitalSigns)。

* * *

    要求: <fhir-server>/監視? 患者 =<患者の>&_sort:d esc = date&category = バイタルサイン
    
    応答: {"resourceType": "バンドル"、"id": "<バンドル id>", "「"」と入力して、"、" 集計 "と入力します: [{" リソース ": {" リソース ": {" resourceType ":" <"、" id ":" リソース id> "," カテゴリ ": {" コード ":" "{code": "\" code ":": [{" システム ":"http://loinc.org"," コード ":" 39156-5 "," 表示 ":" bmi "}]," effectiveDateTime ":" 2009-12-01 "," valuvalu":" ":" 値 ": 34.4," unit ":"? "http://unitsofmeasure.org" "," "システム": "", "code": "?"
        .
        .
      ] }

* * *

この[https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html)フィールドセットのその他の詳細については、を参照してください。

## <a name="condition"></a>状態

以下は、 [Argonaut 条件プロファイル](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)の一部である最小必須フィールドです。

1. コード。 [0]。表示

優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリでは、次のフィールドも読み取ることができます。

1. 記録された日付
2. 程度

リソース検索では、GET メソッドと次のパラメーターを使います。

1. 患者 =\<患者 id の>
2. _ count =\<最大結果>

この通話の次の例を参照してください。

* * *

    要求: fhir-server>/条件? 患者 =<患者 id>&_count = 10 を取得 <
    
    応答: {"resourceType": "バンドル", "id": "<バンドル id>"、"種類": "searchset"、"集計": ""、"" のように入力します: [{"リソース": {"resourceType": "id": "<リソース id>"、"コード": {"code": [{              "システム": "http://snomed.info/sct", "コード": "386033004", "表示": "", "Neuropathy": "syst", "dateRecorded": "2018-09-17", "深刻度": {"": [{]em ":http://snomed.info/sct" "," コード ":" 24484000 "," 表示 ":" 重大 "}"}},}]}

* * *

この[https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html)フィールドセットのその他の詳細については、を参照してください。

## <a name="encounter"></a>状況

"US Core" というプロファイルのサブセットである、最低限必要なフィールドは次のとおりです。

1. 状態
2. [0] と入力します。コーディング [0]。表示

さらに、US Core の次のフィールドは、プロファイルの "サポートが必要" フィールドを示しています。

1. 期間. 開始日
2. 場所 [0]場所。表示

リソース検索では、GET メソッドと次のパラメーターを使います。

1. 患者 =\<患者 id の>
2. (並べ替え: desc =\<フィールドの例) 日付>
3. _ count =\<最大結果>

目標は、患者の最後の既知の場所を取得できるようにすることです。 各検出は、位置情報リソースを参照します。 参照には、場所の表示フィールドも含まれます。 この通話の次の例を参照してください。
* * *

    要求: fhir-server>/<を取得します。患者 =<患者-id>&_sort:d esc = date&_count = 1
    
    応答: {"resourceType": "バンドル", "種類": "searchset", "集計": "{" リソース ": {" resourceType ":" <リソース id> "、" id ":" "を使用": "" という値: [{"use": "" # ":" "値"<id>: ": "到着"、"種類": [{"display": "予定"}]、[}]、"患者": {"参照": "患者" と "<" のような "!": ">": "!": "!": {"start": "09/17/2018 1:00:00 PM"}, "場所": [{             "場所": {"display": "クリニック-ENT"},} "}}]}

* * *

この[https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm)フィールドセットのその他の詳細については、を参照してください。

## <a name="allergyintolerance"></a>AllergyIntolerance

以下は、Argonaut AllergyIntolerance profile のサブセットである最小必須フィールドです。

1. コード。テキスト
2. コード。 [0]。表示
3. 状態

優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリも次のフィールドを読み取ります。

1. RecordedDate
2. 注テキスト
3. 反力 [..]物質。テキスト
4. 反力 [..]影響 [..]テキスト
5. テキストの Div

リソース検索では、GET メソッドと次のパラメーターを使います。

1. 患者 = \<患者 id の>

この通話の次の例を参照してください。

* * *

    要求: <fhir-server>/AllergyIntolerance? 患者 =<患者 id を取得>
    
    応答: {"resourceType": "バンドル", "id": "<バンドル id>"、"種類"、"searchset"、"total": 1, "recordedDate": "2018"、"id": "<リソース id>"、"": ""、""、"-09": "-090Z "," 物質 ": {" text ":" Cashew ナット "}," 状態 ":" 確認 "," 反応 ": [{" 物質 ": {" 物質 ":" "Injectable": "cashew ナット allergenic extract Product"}, "manifestation ": [{" text ":" Anaphylactic 反 "}]}"}} "}

* * *

この[https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html)フィールドセットのその他の詳細については、を参照してください。

## <a name="medication-order"></a>投薬注文

以下は、Argonaut MedicationOrder profile のサブセットである最小必須フィールドです。

1. 記録された日付
2. Prescriber
3. 投薬 (参照の場合)
4. 投薬 (概念の場合)

優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリでは、次のフィールドも読み取ることができます。

1. DateEnded
2. DosageInstruction。
3. テキストの Div

リソース検索では、GET メソッドと次のパラメーターを使います。

1. 患者 =\<患者 id の>
2. _ count =\<最大結果>

この通話の次の例を参照してください。

* * *

    要求: <fhir-server>/MedicationOrder? 患者 =<患者 id>&_count = 10
    
    応答: {"resourceType": "バンドル", "id": "<バンドル id>"、"種類"、"searchset"、"total": 1, "medi": "{" リソース ": {" resourceType ":" "、" id ":" <リソース id> "、" dateWritten ":" 2018-09-17 "," MedicationOrder "cationCodeableConcept ": {" text ":" Lisinopril 20 MG 口頭タブレット "}," prescriber ": {" display ":" Jane Doe "}," dosageInstruction ": [{" テキスト ":" "{" テキスト "

* * *  

この[https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html)フィールドセットのその他の詳細については、を参照してください。

## <a name="coverage"></a>サポート

以下は、US Core または Argonaut のプロファイルでカバーされていない最低限の必須フィールドです。

1. 給料または

リソース検索では、GET メソッドと次のパラメーターを使います。

1. 患者 =\<患者 id の>

この通話の次の例を参照してください。

* * *

    要求: <fhir-server>/利用可能かどうかを確認してください。患者 =<患者 id>
    
    応答: {"resourceType": "次へ" と入力します: "searchset", "集計": "検索": {"resourceType": [{"リソース": {"resourceType": "<"、"id": "リソース id>"、"プラン": "第1の保険はありません"、"サブスクリプション": "患者/<患者の> "}}}]}

* * *

この[https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html)フィールドセットのその他の詳細については、を参照してください。

## <a name="location"></a>場所

このリソース[は、リソースの参照](#encounter)としてのみ使用されます。

この[https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html)フィールドセットのその他の詳細については、を参照してください。
