---
title: " 患者アプリケーション、EHR の DSTU2 の統合インタ フェース"
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
ms.openlocfilehash: 85fd90fb338f8b19762dc9433fa1dc281f3cedff
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2019
ms.locfileid: "33643115"
---
# <a name="dstu2-interface-specification"></a>DSTU2 インターフェイスの仕様

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

設定するか、マイクロソフト チームの患者のアプリケーションで動作する、FHIR サーバーを再構成する、アプリケーションがアクセスする必要がどのようなデータを理解する必要があります。 FHIR サーバーは、以下のリソースのバンドルを使用して POST 要求をサポートする必要があります。

- [患者](#patient)
- [観測](#observation)
- [状態](#condition)
- [発生します。](#encounter)
- [Allergy 思いがけず](#allergyintolerance)
- [カバレッジ](#coverage)
- [薬注文](#medication-order)
- [場所](#location)

> [!NOTE]
> 患者のリソースは、唯一の必須のリソース (せず、アプリケーションがまったく読み込まれないです。 ただし、パートナーがマイクロソフト チームの患者のアプリケーションに最適なエンド ユーザー エクスペリエンスの下で提供されている仕様ごとの上記のすべてのリソースのサポートを実装することをお勧めします。

複数のリソースの Microsoft チームの患者のアプリケーションからのクエリは、FHIR サーバーの URL に要求のバンドル (バッチ) を転記します。 サーバーでは、各要求を処理し、各要求に一致するリソースのバンドルを返します。 詳細と例についてを参照してください[https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction)。

次の FHIR のすべてのリソースを直接リソース参照によってアクセスできることがあります。

## <a name="conformance-minimum-required-field-set"></a>準拠の最低限必要なフィールドを設定

 FHIR サーバーに事実の概要、機能の適合に関する声明を実装しなければなりません。 予測しています、DSTU2 の FHIR サーバーのパラメーターの下。

1. 残りの部分
   1. Mode
   2. 相互作用
   3. リソース: の種類
   4. [OAuth の Uri の拡張機能](http://hl7.org/fhir/extension-oauth-uris.html)のセキュリティ:
2. FhirVersion の (コードが必要ですどちらのバージョンを複数のバージョンをサポートしていますをピボットする必要があることを理解しておきたいです。

参照してください[https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html)他の詳細については、このフィールドを設定します。

## <a name="patient"></a>患者

[Argonaut 患者プロファイル](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)のフィールドのサブセットである最低限の必須フィールドがあります。

1. Name.Family
2. Name.Given
3. 性別
4. [誕生日]
5. MRN (識別子)

Argonaut のフィールドだけでなく、優れたユーザー エクスペリエンスの患者のアプリケーションも次のフィールドを読み取ります。

1. Name.Use
2. Name.Prefix
3. (患者のリソースには、この参照は、次の例に示すように表示フィールドを含める必要があります) CareProvider

* * *

    _LT_fhir-server>/患者/<patient ・ id> を取得する要求。
    
    応答: {「リソースの種類」:「患者」、"id":"<patient-id>"です。
      .
      .
      [名]: [{を使用する]:「正式な」、「プレフィックス」: [「様」]「家族」: ["Chau"]"指定": ["も"]}]、識別子]: [{を使用する]:「正式な」、「タイプ」: {"コーディング": [{システム:"http://hl7.org/fhir/v2/0203"、"コード":"様"}]}、"値":"1234567"}]、"性別":「男性」、"生年月日":」1957-06-05"、"careProvider": [{0} を表示する]: [}]}

* * *

リソース検索は、/Patient/_search し、次のパラメーターで POST メソッドを使用します。

1. id
2. ファミリ: を含む = (家族の名前を持つ値を含むすべての患者のための検索)。
3. 指定された =\<substring>
4. 名前 =\<substring>
5. 生年月日 =(exact match)
6. \_カウント (返される結果の最大数) <br> 応答は、検索結果として返されるレコードの合計数を含める必要があり、\_カウントが適用されます、PatientsApp によって返されるレコードの数を制限します。
7. 識別子 =\<mrn>

目標は、するを検索およびフィルターを次のように患者のことです。

- ID: これは、FHIR のすべてのリソースがリソースの ID です。
- MRN: これは、医療スタッフが知っている患者の実際の識別子です。 この MRN が FHIR で識別子のリソースの内部識別子の種類に基づいて理解します。
- 名前
- [誕生日]

この呼び出しの次の使用例を参照してください。

* * *

    要求: ポスト <fhir ・ server>/患者/_search 要求本文: 指定された hugh&family を = = chau
    
    応答: {「リソースの種類」:「バンドル」、"id":"<bundle-id>"。
      .
      .
      [入力]: [{「リソース」: {「リソースの種類」:「患者」、"id":"<patient id>"、「名前」: [{「テキスト」:"も Chau、"「家族」: ["Chau"]「指定」: [「も」]}]、「性別」:「男性」、「生年月日」:」1957-06-05」}、[検索]: {「モード」:「一致」}}]}

* * *

参照してください[https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html)他の詳細については、このフィールドを設定します。

## <a name="observation"></a>観測

Argonaut バイタル ・ サインのプロファイルの一部は、最低限必要なフィールドがあります。

 1. 有効 (日付時刻または期間)
 2. Code.Coding.Code
 3. ValueQuantity.Value

Argonaut のフィールドだけでなく、優れたユーザー エクスペリエンスの患者のアプリケーションも次のフィールドを読み取ります。

 1. Code.Coding.Display
 2. ValueQuantity.Unit

コンポーネントの観測値を使用すると、各コンポーネントの観測と同じロジックが適用されます。

リソース検索では、GET メソッドと、次のパラメーターを使用します。

1. 患者 =\<患者の id\>
2. 並べ替え: 説明 =\<ex フィールドです。 日付\>

目標は、[VitalSigns.DSTU.saz] (観察しますか?)、患者の最新のバイタル ・ サインを取得できるようにすること。

* * *

    要求: 観察/<fhir ・ server> を取得? 患者 = <patient-id>&_sort:desc = date&category = 重要な記号
    
    応答: {「リソースの種類」:「バンドル」、"id":"<bundle id>"、「種類」:"searchset"、「合計」: 20、[入力]: [{「リソース」: {「リソースの種類」:「観察」、"id":"<resource id>"、「カテゴリ」: {「コーディング」: [{コード":「重要な記号」}]、}、「コード」: {」コーディング": [{システム:"http://loinc.org"、「コード」:「39156-5」、「表示」:「bmi」}]}、"effectiveDateTime":」2009-12-01"、"valueQuantity": {"値": 34.4、「出荷単位」:"kg/m 2」、「システム」:」http://unitsofmeasure.org」、「コード」:"kg/m 2」}}、}、。
        .
        .
      ] }

* * *

参照してください[https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html)他の詳細については、このフィールドを設定します。

## <a name="condition"></a>状態

[Argonaut 条件プロファイル](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)の一部である最低限の必須フィールドがあります。

1. Code.Coding[0]。表示

Argonaut のフィールドだけでなく、優れたユーザー エクスペリエンスの患者のアプリケーションも読み取れる次のフィールド。

1. 記録されている日付
2. 重大度レベル

リソース検索では、GET メソッドと、次のパラメーターを使用します。

1. 患者 =\<患者の id>
2. _count =\<max results>

この呼び出しの次の使用例を参照してください。

* * *

    要求の場合: <fhir-server> または条件を取得しますか? 患者 = <patient id>&_count = 10
    
    応答: {「リソースの種類」:「バンドル」、"id":"<bundle id>"、「種類」:"searchset"、「合計」: 1 の場合、[入力]: [{「リソース」: {「リソースの種類」:「条件」、"id":"<resource id>"、「コード」: {「コーディング」: [{              システム:"http://snomed.info/sct"、「コード」:「386033004」、「表示」:「Neuropathy (nerve 破損)」}]}、"dateRecorded":] 2018-09-17"、「重要度」: {"コーディング": [{0}] system":"http://snomed.info/sct"、「コード」:「24484000」、「表示」:「重大」}]}}、}]}

* * *

参照してください[https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html)他の詳細については、このフィールドを設定します。

## <a name="encounter"></a>発生します。

これらは、米国の主要な発生プロファイル」必要があります"フィールドのサブセットである最低限の必須フィールドです。

1. 状態
2. [0] を入力します。[0] をコーディングします。表示

さらに、フィールドから米国の主要な発生プロファイルの次のフィールドする必要があります「サポート」

1. Period.Start
2. [0] の場所です。Location.Display

リソース検索では、GET メソッドと、次のパラメーターを使用します。

1. 患者 =\<患者の id>
2. _sort:desc =\<ex フィールドです。 date>
3. _count =\<max results>

目標は、患者の最後の既知の場所を取得できるようにすること。 各遭遇は、場所のリソースを参照します。 参照では、保管場所の表示のフィールドを含むものとも。 この呼び出しの次の使用例を参照してください。
* * *

    要求: <fhir-server>/出会いを取得しますか? 患者 = <patient-id>&_sort:desc = date&_count = 1
    
    応答: {「リソースの種類」:「バンドル」、「タイプ」:"searchset"、「合計」: 1 の場合、[入力]: [{「リソース」: {"リソースの種類」:"発生"、"id":"<resource id>"、[識別子]: [{を使用する]:「正式な」、「値」:"<id>」}]、[状態:」が到着した」、「型」: [{「コーディング」: [{を表示する]: 予定}]、}]"患者"、: {参照:"患者と <patient-id>"}"期間"、: {スタート ボタン:"09/17/2018 午後 1:00:00"}、場所: [{             [場所]: {を表示する]:「クリニック-ENT}、}]}}]}

* * *

参照してください[https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm)他の詳細については、このフィールドを設定します。

## <a name="allergyintolerance"></a>AllergyIntolerance

Argonaut AllergyIntolerance プロファイルの一部は、最低限必要なフィールドがあります。

1. Code.Text
2. Code.Coding[0]。表示
3. 状態

Argonaut のフィールドだけでなく、優れたユーザー エクスペリエンスの患者のアプリケーションも次のフィールドを読み取ります。

1. RecordedDate
2. Note.Text
3. 反 [.]。Substance.Text
4. 反 [.]。付きマニフェスト [.]。テキスト
5. Text.Div

リソース検索では、GET メソッドと、次のパラメーターを使用します。

1. 患者 =\<患者の id>

この呼び出しの次の使用例を参照してください。

* * *

    要求の場合: <fhir-server>/AllergyIntolerance を取得しますか? 患者 = <patient id>
    
    応答: {「リソースの種類」:「バンドル」、"id":"<bundle id>"、「種類」:"searchset"、「合計」: 1 の場合、[入力]: [{「リソース」: {「リソースの種類」:"AllergyIntolerance"、"id":"<resource id>"、"recordedDate":"2018-09-17T07:00:00.000Z」、「物質」: {"テキスト":「までナット」}、状態:"確認"、"反": [{"物質": {「テキスト」:「までナット allergenic は、Injectable の製品を抽出」}、"manifestati: [{「文字列」:「Anaphylactic 反」}]}]}}]}

* * *

参照してください[https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html)他の詳細については、このフィールドを設定します。

## <a name="medication-order"></a>薬注文

Argonaut MedicationOrder プロファイルの一部は、最低限必要なフィールドがあります。

1. DateWritten
2. Prescriber.Display
3. Medication.Display (場合の参照)
4. Medication.Text (場合の概念)

Argonaut のフィールドだけでなく、優れたユーザー エクスペリエンスの患者のアプリケーションも読み取れる次のフィールド。

1. DateEnded
2. DosageInstruction.Text
3. Text.Div

リソース検索では、GET メソッドと、次のパラメーターを使用します。

1. 患者 =\<患者の id>
2. _count =\<max results>

この呼び出しの次の使用例を参照してください。

* * *

    要求の場合: <fhir-server>/MedicationOrder を取得しますか? 患者 = <patient id>&_count = 10
    
    応答: {「リソースの種類」:「バンドル」、"id":"<bundle id>"、「種類」:"searchset"、「合計」: 1 の場合、[入力]: [{「リソース」: {「リソースの種類」:"MedicationOrder"、"id":"<resource id>"、"dateWritten":「2018-09-17」、"・ メディア ・cationCodeableConcept": {「テキスト」:「Lisinopril 20 MG 口頭タブレット」}「prescriber」、: {を表示する]: [}、"dosageInstruction": [{「テキスト」:"1 日"}]}}]}

* * *  

参照してください[https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html)他の詳細については、このフィールドを設定します。

## <a name="coverage"></a>カバレッジ

Argonaut または米国のコアのいずれかのプロファイルの対象になっていない、最低限必要なフィールドがあります。

1. Payor

リソース検索では、GET メソッドと、次のパラメーターを使用します。

1. 患者 =\<患者の id>

この呼び出しの次の使用例を参照してください。

* * *

    要求の場合: <fhir-server>/対応範囲を取得しますか? 患者 = <patient id>
    
    応答: {「リソースの種類」:「バンドル」、「タイプ」:"searchset"、「合計」: 1 の場合、[入力]: [{「リソース」: {"リソースの種類":"補充"、"id":"<resource id>"、「計画」:「いいえ主保険」、「サブスクライバー」: {参照:"患者/<patient id>"}}}]}

* * *

参照してください[https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html)他の詳細については、このフィールドを設定します。

## <a name="location"></a>場所

このリソースは、[発生する](#encounter)リソースの参照としてのみ使用されています。

参照してください[https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html)他の詳細については、このフィールドを設定します。
