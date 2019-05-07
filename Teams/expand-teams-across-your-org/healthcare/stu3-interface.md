---
title: 患者アプリケーション、EHR の STU3 の統合インタ フェース
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: チーム患者の Microsoft アプリケーションの EHR の統合
ms.openlocfilehash: 34fd6bb1ecaf788a55aca877c671c9a51cb07944
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2019
ms.locfileid: "33643117"
---
# <a name="stu3-interface-specification"></a>STU3 インターフェイスの仕様

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

設定するか、マイクロソフト チームの患者のアプリケーションで動作する、FHIR サーバーを再構成する、アプリケーションがアクセスする必要がどのようなデータを理解する必要があります。 FHIR サーバーは、以下のリソースのバンドルを使用して POST 要求をサポートする必要があります。

- [患者](#patient)
- [観測](#observation)
- [状態](#condition)
- [発生します。](#encounter)
- [Allergy 思いがけず](#allergyintolerance)
- [カバレッジ](#coverage)
- [薬の明細書](#medication-request)(、MedicationOrder、PatientsApp の DSTU2 のバージョンに置き換えられます)
- (については、必要なこのリソースからに指定するに遭遇した) 場所

> [!NOTE]
> 患者のリソースは、(することがなく、アプリケーションがまったく読み込まれない) 唯一の必須リソースです。ただし、パートナーがマイクロソフト チームの患者のアプリケーションに最適なエンド ユーザー エクスペリエンスの下で提供されている仕様ごとの上記のすべてのリソースのサポートを実装することをお勧めします。

複数のリソースの Microsoft チームの患者のアプリケーションからのクエリは FHIR サーバーの URL に要求のバンドル (バッチ) を転記します。 サーバーは、各要求を処理し、各要求に一致するリソースのバンドルを返すものとします。 詳細と例についてを参照してください[https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction)。

## <a name="capability-statement"></a>ステートメントの機能

最低限必要なフィールドがあります。

1. 残りの部分
   1. Mode
   2. 相互作用
   3. リソース: の種類
   4. [OAuth の Uri の拡張機能](http://hl7.org/fhir/extension-oauth-uris.html)のセキュリティ:
2. FhirVersion の (コードが必要ですこれをピボットする必要がありますどちらのバージョンを理解します。

参照してください[https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html)他の詳細については、このフィールドを設定します。

## <a name="patient"></a>患者

Argonaut 患者のプロファイルのフィールドのサブセットは、最低限必要なフィールドを以下に示します。

1. Name.Given
2. Name.Family
3. 性別
4. [誕生日]
5. MRN (識別子)

[Argonaut フィールド](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)だけでなく、優れたユーザー エクスペリエンスの患者のアプリケーションも読み取れる次のフィールド。

1. Name.Use
2. Name.Prefix
3. [GeneralPractitioner] - 患者のリソース (表示フィールド) で、GeneralPractitioner の参照を含める必要があります

リソース検索は、/Patient/_search し、次のパラメーターで POST メソッドを使用します。

1. id
2. 家族 (家族の名前を持つ値を含むすべての患者のための検索条件) を =
3. 指定された =\<substring>
4. 生年月日 =(exact match)
5. 性別 = (管理の性別の 1 つの値)
6. \_カウント (返される結果の最大数) <br> 応答は、検索結果として返されるレコードの合計数を含める必要があり、\_カウントが適用されます、PatientsApp によって返されるレコードの数を制限します。
7. 識別子 =\<mrn>

目標は、するを検索およびフィルターを次のように患者のことです。

- ID: これは、FHIR のすべてのリソースがリソースの ID です。
- MRN: これは、医療スタッフが知っている患者の実際の識別子です。 この MRN が FHIR で識別子のリソースの内部識別子の型に基づくことを理解します。
- 名前
- [誕生日]

次の呼び出しの例を参照してください。

* * *

    要求: ポスト <fhir ・ server>/患者/_search 要求本文: 指定された ruth&family を = = 黒
    
    応答: {"リソースの種類":「バンドル」、"id":"<bundle id>"、「メタ」: {"lastUpdated":"2019-01-14T23:44:45.052 + 00時 00分」}、[種類]:"searchset"、「合計」: 1 の場合、「リンク」: [{「関係」:「自己」、"url": <fhir-server>/患者として」}]、入力: [{"fullUrl": <fhir-server>/患者/<patient ・ id>"、「リソース」: {「リソースの種類」:「患者」、"id":"<patient id>"、「メタ」: {」バージョン Id」:「1」、"lastUpdated":"2017-10-18T18:32:37.000 + 00時 00分」}、「テキスト」: {[状態]:「生成」、"div": "<div>\n        <p>ラス黒</p>\n      </div>」}、[識別子]: [{を使用する]:「通常」、「種類」: {「コーディング」: [{システム:」http://hl7.org/fhir/v2/0203」、「コード」:「様」、「表示」:「医療記録番号」、"userSelected": false}]、「テキスト」:「医療記録番号」}、システム:」http://hospital.smarthealthit.org"、「値」:「1234567」}]「アクティブ」、: true の場合、」名]: [{を使用する]:「公式な」、「家族」:「黒」、「指定された」: [「ルース」C"
    }]、「通信」: [{システム:「電話」、「値」:「800-599-2739」、「使用」:「ホーム」}、{システム:「電話」、「値」:「800-808-7785」、「使用」:「モバイル」}、{システム:「電子メール」、「値」:"ruth.black@example.com"}]、「性別」:「女性」、"生年月日":"1951-08-23」、」アドレス]: [{を使用する]:「ホーム」、「直線」: ["26 南 RdApt 22"]、「市区町村」:"Sapulpa"、「状態」:"OK"、"郵便番号":"74066"、"都道府県":"アメリカ"}]}、[検索]: {"モード":"一致"}}]}

* * *

    _LT_fhir-server>/患者/<patient ・ id> を取得する要求。
    
    応答: {「リソースの種類」:「患者」、"id":"<patient id>"、[識別子]: [{を使用する]:「通常」、「種類」: {「コーディング」: [{システム:」http://hl7.org/fhir/v2/0203"、「コード」:「様」、}]、「テキスト」:「医療記録番号」}、「値」:「1234567」}]「名前」、: [{を使用する]:「正式な」、」ファミリ」:「アダム」、「指定」: ["ダニエル","X"です。 {]}]、「性別」:「男性」、「生年月日」:「1925-12-23」、}

* * *

参照してください[http://hl7.org/fhir/stu3/patient.html](http://hl7.org/fhir/stu3/patient.html)他の詳細については、このフィールドを設定します。

## <a name="observation"></a>観測

これらは、 [Argonaut-バイタル ・ サインのプロファイル](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)の一部である最低限の必須フィールドです。

1. 有効 (日付時刻または期間)
2. Code.Coding.Code
3. ValueQuantity.Value

Argonaut のフィールドだけでなく、優れたユーザー エクスペリエンスの患者のアプリケーションも読み取れる次のフィールド。

1. Code.Coding.Display
2. ValueQuantity.Unit

リソース検索では、GET メソッドと、次のパラメーターを使用します。

1. 患者 =\<患者の id>
2. _sort = 日付
3. カテゴリ (のクエリは"カテゴリ = 重要な記号") バイタル ・ サインの一覧を取得します。

呼び出しの次の使用例を参照してください。

* * *

    要求: 観察/<fhir ・ server> を取得? 患者 = <patient id>&category = 重要な記号
    
    応答: {「リソースの種類」:「バンドル」、「id」:"<bundle id>"、"種類":"searchset"、"合計": 20、入力: [{"リソース": {「リソースの種類」:「観察」、"id":"<resource id>"、"カテゴリ": [{"コーディング": [{システム:"http://hl7.org/fhir/observation-category"、「コード」:」重要な記号"}]、}]、「コード」: {「コーディング」: [{システム:」http://loinc.org」、「コード」:「8867-4」、「表示」:"heart_rate"}]}、"effectiveDateTime":」2009-04-08T00:00:00-06時 00分"、"valueQuantity": {「値」: 72.0、「出荷単位」:"{拍}/分」、システム」:」http://unitsofmeasure.org」、}}}。
        .
        .
      ] }

* * *

参照してください[https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html)他の詳細については、このフィールドを設定します。

## <a name="condition"></a>状態

[Argonaut 条件プロファイル](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)の一部である最低限の必須フィールドを次に示します。

1. Code.Coding[0]。表示

Argonaut のフィールドだけでなく、優れたユーザー エクスペリエンスの患者のアプリケーションも読み取れる次のフィールド。

1. AssertedDate
2. 重大度レベル

リソース検索では、GET メソッドと、次のパラメーターを使用します。

1. 患者 =\<患者の id>
2. _count =\<max results>

この呼び出しの次の使用例を参照してください。

* * *

    要求の場合: <fhir-server> または条件を取得しますか? 患者 = <patient id>&_count = 10
    
    応答します {"リソースの種類」:「バンドル」、「id」:"<bundle id>"、"種類":"searchset"、"合計": 2、[入力]: [{"リソース": {"リソースの種類」:"条件"、"id":"<resource id>"、"コード": {"コーディング": [{システム:"http://snomed.info/sct"、"コード":"185903001"、」。表示する]:"インフルエンザ注射のニーズ、「}]}、「重要度」: {"コーディング": [{システム:"http://snomed.info/sct"、「コード」:「24484000」を表示する]:「重大」}]}、"assertedDate":"2018-04-04」}}。
        .
        .
      ] }

* * *
参照してください[http://hl7.org/fhir/stu3/condition.html](http://hl7.org/fhir/stu3/condition.html)他の詳細については、このフィールドを設定します。

## <a name="encounter"></a>発生します。

これらは、最低限の必須フィールドで、[プロファイルの u. s. コアが発生する](http://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html)「必要があります」フィールドのサブセットである)。

1. 状態
2. [0] を入力します。[0] をコーディングします。表示

さらに、プロファイルの u. s. コアの発生から次のフィールドする必要があります「サポート」のフィールド。

1. Period.Start
2. [0] の場所です。Location.Display

リソース検索では、GET メソッドと、次のパラメーターを使用します。

1. 患者 =\<患者の id>
2. _sort:desc =\<ex フィールドです。 date>
3. _count =\<max results>

目標は、患者の最後の既知の場所を取得できるようにすること。 各遭遇は、場所のリソースを参照します。 参照では、保管場所の表示のフィールドを含むものとも。

参照してください[http://hl7.org/fhir/stu3/encounter.html](http://hl7.org/fhir/stu3/encounter.html)他の詳細については、このフィールドを設定します。

## <a name="allergyintolerance"></a>AllergyIntolerance

[Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html)プロファイルの一部は、最低限必要なフィールドがあります。

1. Code.Text
2. Code.Coding[0]。表示
3. ClinicalStatus/VerificationStatus (読み取る両方)

Argonaut のフィールドに加え、優れたユーザー エクスペリエンスの患者アプリケーション参照することも次のフィールド。

1. AssertedDate
2. Note.Text
3. 反力
    1. 物質 (1 つのコーディング要素)
    2. 付きマニフェスト (1 つのコーディング要素)

リソース検索では、GET メソッドと、次のパラメーターを使用します。

1. 患者 =\<患者の id>

次の呼び出しの例を参照してください。 

* * *

    要求の場合: <fhir-server>/AllergyIntolerance を取得しますか? 患者 = <patient id>
    
    応答: {"リソースの種類":「バンドル」、"id":"<bundle id>"、「種類」:"searchset"、「合計」: 1 の場合、[入力]: [{「リソース」: {「リソースの種類」:"AllergyIntolerance"、"id":"<resource id>"、"clinicalStatus":「アクティブ」、"verificationStatus」:「確認」、「コード」: {「コーディング」: [{システム:"http://rxnav.nlm.nih.gov/REST/Ndfrt"、「コード」:"N0000175503"を表示する]:「sulfonamide antibacterial」、}]、「テキスト」:"sulfonamide antibacterial"}、"assertedDate":"2018-01-01T00:00:00-07時 00分」、「反力」: [{」付きマニフェスト」: [{「コーディング」: [{システム:"http://snomed.info/sct"、"コード"。 「271807003」、「表示」:"スキン rash"}]、「文字列」:"スキン rash"}]、}]}}]}

* * *

参照してください[http://hl7.org/fhir/stu3/allergyintolerance.html](http://hl7.org/fhir/stu3/allergyintolerance.html)他の詳細については、このフィールドを設定します。

## <a name="medication-request"></a>薬の要求

[プロファイルの u. s. の中核となる薬の要求](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)の一部は、最低限の必須フィールドがあります。

1. Medication.Display (場合の参照)
2. Medication.Text (場合 CodableConcept)
3. AuthoredOn
4. Requester.Agent.Display

米国の主要なフィールドだけでなく、優れたユーザー エクスペリエンスの患者のアプリケーションを参照することも次のフィールド。

1. DosageInstruction れました。テキスト
2. テキスト

リソース検索では、GET メソッドと、次のパラメーターを使用します。

1. 患者 =\<患者の id>
2. _count =\<max results>

参照してください[https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html)他の詳細については、このフィールドを設定します。

## <a name="coverage"></a>カバレッジ

Argonaut または米国のコアのいずれかのプロファイルの対象になっていない、最低限必要なフィールドがあります。

1. 少なくとも 1 つの要素のグループ化
    1. グループの表示インタ
    2. PlanDisplay
2. 期間
3. サブスクライバー Id

リソース検索では、GET メソッドと、次のパラメーターを使用します。

1. 患者 =\<患者の id>

参照してください[http://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html)他の詳細については、このフィールドを設定します。
