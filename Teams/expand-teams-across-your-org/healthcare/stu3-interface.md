---
title: 患者のアプリと EHR の統合 STU3 インターフェイス
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
description: 電子医療記録を Microsoft Teams の患者アプリと STU3 インターフェイス仕様に統合する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1c5e19ff28c67641ac5b643e1944bf2435fbf164
ms.sourcegitcommit: 3b54a56ec1fe4366580621e19cdbb6a833a01161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2020
ms.locfileid: "48361347"
---
# <a name="stu3-interface-specification"></a>STU3 インターフェイスの仕様

> [!IMPORTANT]
> **2020年10月15日に有効な患者アプリは廃止され、ユーザーは Teams app store からインストールできなくなります。今すぐ Teams の [リストアプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) を使い始めることをお勧めします。**
>
>患者のアプリデータは、チームをバックアップする Office 365 グループのグループメールボックスに格納されます。 患者のアプリが廃止されると、そのアプリに関連付けられたデータはすべてこのグループに保持されますが、ユーザーインターフェイスを使ってアクセスすることはできなくなります。 現在のユーザーは、 [リストアプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)を使ってリストを再作成できます。
>
>[リストアプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)は、すべての Teams ユーザー用にプレインストールされており、すべてのチームとチャネルでタブとして使用できます。 リストを使用すると、ケアチームは、組み込みの [患者] テンプレートを使用して、最初から、または Excel にデータをインポートして、患者リストを作成できます。 組織でのリストアプリの管理方法の詳細については、「 [リストアプリを管理](../../manage-lists-app.md)する」を参照してください。

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Microsoft Teams の患者と連携するように FHIR サーバーを設定または再構成するには、アプリがアクセスする必要があるデータを把握する必要があります。 FHIR サーバーでは、次のリソースについて、バンドルを使った POST 要求をサポートしている必要があります。

- [診療](#patient)
- [観察](#observation)
- [状態](#condition)
- [状況](#encounter)
- [Allergy Intolerance](#allergyintolerance)
- [サポート](#coverage)
- [投薬ステートメント](#medication-request) (PATIENTSAPP の DSTU2 バージョンの MedicationOrder を置き換えます)
- 場所 (このリソースから必要な情報は、発生する可能性があります)

> [!NOTE]
> 患者のリソースは唯一の必須リソースです (アプリがまったく読み込まれなくなります)。ただし、Microsoft Teams の患者アプリを使用して、最も優れたエンドユーザーエクスペリエンスを実現するために、以下に記載されている仕様ごとに、上記のすべてのリソースのサポートを実装することをお勧めします。

複数のリソースの Microsoft Teams の患者アプリからのクエリは、FHIR サーバーの URL に対する要求のバンドル (バッチ) を投稿するものとします。 サーバーは各要求を処理し、各要求によって一致したリソースのバンドルを返します。 詳細と例については、「」を参照してください [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) 。

## <a name="capability-statement"></a>機能ステートメント

最低限必要なフィールドを次に示します。

1. 後
   1. モード
   2. 通信
   3. リソース: 種類
   4. セキュリティ: [OAuth uri 用の拡張子](https://hl7.org/fhir/extension-oauth-uris.html)
2. FhirVersion (コードは、どのバージョンをピボットするかを理解するために必要です。)

[https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html)このフィールドセットのその他の詳細については、を参照してください。

## <a name="patient"></a>診療

以下は、Argonaut の患者プロファイルフィールドのサブセットである、必要な最小フィールドを示しています。

1. 名前。指定された
2. 家族
3. 女性
4. 地
5. MRN (識別子)

優れたユーザーエクスペリエンスを実現するために、 [Argonaut フィールド](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)に加えて、患者アプリでは、次のフィールドも読み取ることができます。

1. 名前を指定します。
2. 名前プレフィックス
3. [一般の専門スタッフ]-すべての専門スタッフ参照が患者リソースに含まれている必要があります (表示フィールドのみ)。

リソース検索では、/Patient/_search と次のパラメーターで POST メソッドを使います。

1. id
2. family = (ファミリ名に値が含まれているすべての患者を検索)
3. 指定 =\<substring>
4. 生年月日 = (完全一致)
5. 性別 = (いずれかの管理者の性別の値)
6. \_count (返される結果の最大数) <br> 応答には、 \_ 返されるレコードの数を制限するために、検索とカウントの結果として返されるレコードの合計数が含まれている必要があります。
7. 識別子 =\<mrn>

目標は、次のようにして患者の検索とフィルター処理を行うことができるようにすることです。

- ID: これは、FHIR のすべてのリソースが持つリソース ID です。
- MRN: 診療員が知っている患者の実際の識別子です。 この MRN は、FHIR の識別子リソース内の識別子の種類に基づいています。
- 名前
- 地

次の通話の例を参照してください。

* * *

    要求: <fhir-server>/Patient/_search 要求本文: 指定 = ruth&ファミリ = 黒
    
    応答: {"resourceType": "バンドル"、"id": "<バンドル id>"、"メタ": {"lastUpdated": "2019-01-14T23: 45.052 + 00:00"}, "種類": "searchset", "total": [{"relation": [{"relation": "/Patient/_search"} "," entry ":):" @ "" {":" self ":><[{" fullUrl ": <fhir-server>/Patient/<患者 id>", "リソース": {"resourceType": "<"、"id": ">" という、"" という "、" meta ": {" versionId ":" 1 "、" 最終更新 ":" 2017-10-18T18:32: 37.000 + 00:00 "}," テキスト ": {" 状態 ":" 生成された "," div ":"<div>i        <p>Ruth ブラック</p>i      </div>"}," 識別子 ": [{" use ":" 通常 "と入力します。 {" コード ": [{" システム ":" "," code ":" "," code ":" "," https://hl7.org/fhir/v2/0203 display "userSelected": false} "," text ":" 医療記録番号 "}," system ":" "" "値": "1234567"}], "Ruth": "{" use ":" "{" use ":" "{" use ":" "{" use ":" ' http://hospital.smarthealthit.org
    ]}]、"電気通信": [{"システム": "電話"、"値": "800-599-2739"、"use": "home"}、"ruth.black@example.com": "800-808-7785"、"値": ""、"使用": ""、"次の値:" "、" 次の値 ":" "、" "、" 女性 "," 生年月日 ":" 1951-08-23 "、" 住所 ": [{" use ":" home "," line ": [" ""、"市": ""、"市区町村" "," 都道府県 ":" OK "," 郵便番号 ":" 74066 "," 国名 ":" USA "}]}," 検索 ": {" mode ":" match "}}}}}

* * *

    要求: <fhir-server>/Patient/<患者 id> を取得する
    
    応答: {"resourceType": "患者"、"id": "<患者の>", "識別子": [{"use": "{" use ":" 通常 "、" type ": {" コード ": [{" system ":" https://hl7.org/fhir/v2/0203 "、" code ":" MR "、}"、"text": "医学レコード番号"}, "値": "1234567"}], "Adams" "{" use ":" "{" use ":" "{" use "" "": "' ]}], "性別": "男性", "生年月日": "1925-12-23",}

* * *

[https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html)このフィールドセットのその他の詳細については、を参照してください。

## <a name="observation"></a>観察

これらのフィールドは、 [Argonaut](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)に必要な最低限の条件を示しています。

1. 発効 (日付と時刻)
2. コードの記述
3. Valu不定の値

優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリでは、次のフィールドも読み取ることができます。

1. コード。ディスプレイ
2. Valuの単位

リソース検索では、GET メソッドと次のパラメーターを使います。

1. 患者 =\<patient id>
2. _sort =-date
3. category ("カテゴリ = バイタル-記号") を照会して、重要な記号の一覧を取得します。

次の通話の例を参照してください。

* * *

    要求: fhir-server>/監視? 患者 =<患者-id>&カテゴリ = バイバイ <
    
    応答: {"resourceType": "バンドル"、"id": "<バンドル id>"、"type" と入力します。検索セット "," 集計 ":" {"リソース": {"resourceType": "観測"、"id": "<リソース id>", "分類": [{"システム": [{"]" という値: [{"システム": "{" "コード": "" {" https://hl7.org/fhir/observation-category )" コード ": {" コード ": [{" system ":" "," code ":" http://loinc.org 8867-4 "、" 表示 ":" heart_rate "}]}、" effectiveDateTime ":" 2009-04-08T00:00:00-06:00 "," Valuvaluアンチ ty ": {" value ": 72.0," unit ":" {拍}/最小 "," システム ":" http://unitsofmeasure.org ",}}},
        .
        .
      ] }

* * *

[https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html)このフィールドセットのその他の詳細については、を参照してください。

## <a name="condition"></a>状態

[Argonaut 条件プロファイル](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)のサブセットである最小必須フィールドを次に示します。

1. コード。 [0]。表示

優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリでは、次のフィールドも読み取ることができます。

1. AssertedDate
2. 程度

リソース検索では、GET メソッドと次のパラメーターを使います。

1. 患者 =\<patient id>
2. _count =\<max results>

この通話の次の例を参照してください。

* * *

    要求: fhir-server>/条件? 患者 =<患者 id>&_count = 10 を取得 <
    
    応答: {"resourceType": "バンドル", "id": "<バンドル id>"、"種類"、"searchset"、"集計": [{"リソース": {"resourceType": [{"リソース": {"resourceType": "id": "id": "<リソース id>"、"コード": "" http://snomed.info/sct , "コード": "185903001", "表示": "influenza immunization"、"}"、"severity": {"assertedDate": "" http://snomed.info/sct 、"code": ""、"code": "24484000"、"表示": "", "表示": "" "" 2018-04-04
        .
        .
      ] }

* * *
[https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html)このフィールドセットのその他の詳細については、を参照してください。

## <a name="encounter"></a>状況

" [US Core](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) " というプロファイルのサブセットである最小必須フィールドは、"フィールドが含まれている必要があります" である必要があります。

1. 状態
2. [0] と入力します。コーディング [0]。表示

さらに、US Core の次のフィールドは、プロファイルの "サポートが必要" フィールドを示しています。

1. 期間. 開始日
2. 場所 [0]場所。表示

リソース検索では、GET メソッドと次のパラメーターを使います。

1. 患者 =\<patient id>
2. _sort: desc =\<field ex. date>
3. _count =\<max results>

目標は、患者の最後の既知の場所を取得できるようにすることです。 各検出は、位置情報リソースを参照します。 参照には、場所の表示フィールドも含まれます。

[https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html)このフィールドセットのその他の詳細については、を参照してください。

## <a name="allergyintolerance"></a>AllergyIntolerance

以下は、 [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile のサブセットである最小必須フィールドです。

1. コード。テキスト
2. コード。 [0]。表示
3. ClinicalStatus/VerificationStatus (両方とも読む)

優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリは次のフィールドも読み取ることができます。

1. AssertedDate
2. 注テキスト
3. 反
    1. 物質 (1 つのコーディング要素)
    2. 影響 (1 つのコード要素)

リソース検索では、GET メソッドと次のパラメーターを使います。

1. 患者 =  \<patient id>

次の通話の例を参照してください。 

* * *

    要求: <fhir-server>/AllergyIntolerance? 患者 =<患者 id を取得>
    
    応答: {"resourceType": "バンドル"、"id": "<バンドル id>"、"種類": "searchset"、"合計": 1, "エントリ": [{"リソース": "AllergyIntolerance"、"id": "<リソース id>"、"verificationStatus": "clinicalStatus": ""、"": "確認"、"コード": ""、"": " http://rxnav.nlm.nih.gov/REST/Ndfrt ", "code": "" N0000175503 "," display ":" sulfonamide antibacterial "," sulfonamide antibacterial "}," assertedDate ":" 2018-01-01T00:00:00-07:00:00:00:00 "," 反応 ": [{" 影響 ": [{" コード ": [{" system ":" http://snomed.info/sct "," code ":" 271807003 "," 表示 ":" "," 表示 ":" "," 表示 ":" "{rash",}], "テキスト": "スキン rash"} "

* * *

[https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html)このフィールドセットのその他の詳細については、を参照してください。

## <a name="medication-request"></a>投薬要求

以下は、 [US Core 投薬要求プロファイル](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)のサブセットである最小必須フィールドです。

1. 投薬 (参照の場合)
2. 投薬 (CodableConcept の場合)
3. AuthoredOn
4. 要求者。ディスプレイ

優れたユーザーエクスペリエンスを実現するには、米国内のコアフィールドに加えて、患者のアプリでも次のフィールドを読み取ることができます。

1. DosageInstruction [..]テキスト
2. テキスト

リソース検索では、GET メソッドと次のパラメーターを使います。

1. 患者 =\<patient id>
2. _count =\<max results>

[https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html)このフィールドセットのその他の詳細については、を参照してください。

## <a name="coverage"></a>サポート

以下は、US Core または Argonaut のプロファイルでカバーされていない最低限の必須フィールドです。

1. グループ化、少なくとも1つの要素を
    1. GroupDisplay
    2. Plan ディスプレイ
2. ピリオド
3. SubscriberId

リソース検索では、GET メソッドと次のパラメーターを使います。

1. 患者 = \<patient id>

[https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html)このフィールドセットのその他の詳細については、を参照してください。
