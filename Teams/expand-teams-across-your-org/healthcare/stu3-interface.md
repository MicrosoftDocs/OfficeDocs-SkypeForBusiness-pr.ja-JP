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
# <a name="stu3-interface-specification"></a><span data-ttu-id="2c54d-103">STU3 インターフェイスの仕様</span><span class="sxs-lookup"><span data-stu-id="2c54d-103">STU3 interface specification</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="2c54d-104">設定するか、マイクロソフト チームの患者のアプリケーションで動作する、FHIR サーバーを再構成する、アプリケーションがアクセスする必要がどのようなデータを理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c54d-104">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="2c54d-105">FHIR サーバーは、以下のリソースのバンドルを使用して POST 要求をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c54d-105">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="2c54d-106">患者</span><span class="sxs-lookup"><span data-stu-id="2c54d-106">Patient</span></span>](#patient)
- [<span data-ttu-id="2c54d-107">観測</span><span class="sxs-lookup"><span data-stu-id="2c54d-107">Observation</span></span>](#observation)
- [<span data-ttu-id="2c54d-108">状態</span><span class="sxs-lookup"><span data-stu-id="2c54d-108">Condition</span></span>](#condition)
- [<span data-ttu-id="2c54d-109">発生します。</span><span class="sxs-lookup"><span data-stu-id="2c54d-109">Encounter</span></span>](#encounter)
- [<span data-ttu-id="2c54d-110">Allergy 思いがけず</span><span class="sxs-lookup"><span data-stu-id="2c54d-110">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="2c54d-111">カバレッジ</span><span class="sxs-lookup"><span data-stu-id="2c54d-111">Coverage</span></span>](#coverage)
- <span data-ttu-id="2c54d-112">[薬の明細書](#medication-request)(、MedicationOrder、PatientsApp の DSTU2 のバージョンに置き換えられます)</span><span class="sxs-lookup"><span data-stu-id="2c54d-112">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="2c54d-113">(については、必要なこのリソースからに指定するに遭遇した) 場所</span><span class="sxs-lookup"><span data-stu-id="2c54d-113">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="2c54d-114">患者のリソースは、(することがなく、アプリケーションがまったく読み込まれない) 唯一の必須リソースです。ただし、パートナーがマイクロソフト チームの患者のアプリケーションに最適なエンド ユーザー エクスペリエンスの下で提供されている仕様ごとの上記のすべてのリソースのサポートを実装することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2c54d-114">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="2c54d-115">複数のリソースの Microsoft チームの患者のアプリケーションからのクエリは FHIR サーバーの URL に要求のバンドル (バッチ) を転記します。</span><span class="sxs-lookup"><span data-stu-id="2c54d-115">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="2c54d-116">サーバーは、各要求を処理し、各要求に一致するリソースのバンドルを返すものとします。</span><span class="sxs-lookup"><span data-stu-id="2c54d-116">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="2c54d-117">詳細と例についてを参照してください[https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction)。</span><span class="sxs-lookup"><span data-stu-id="2c54d-117">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="2c54d-118">ステートメントの機能</span><span class="sxs-lookup"><span data-stu-id="2c54d-118">Capability Statement</span></span>

<span data-ttu-id="2c54d-119">最低限必要なフィールドがあります。</span><span class="sxs-lookup"><span data-stu-id="2c54d-119">These are the minimum required fields:</span></span>

1. <span data-ttu-id="2c54d-120">残りの部分</span><span class="sxs-lookup"><span data-stu-id="2c54d-120">REST</span></span>
   1. <span data-ttu-id="2c54d-121">Mode</span><span class="sxs-lookup"><span data-stu-id="2c54d-121">Mode</span></span>
   2. <span data-ttu-id="2c54d-122">相互作用</span><span class="sxs-lookup"><span data-stu-id="2c54d-122">Interaction</span></span>
   3. <span data-ttu-id="2c54d-123">リソース: の種類</span><span class="sxs-lookup"><span data-stu-id="2c54d-123">Resource: Type</span></span>
   4. <span data-ttu-id="2c54d-124">[OAuth の Uri の拡張機能](http://hl7.org/fhir/extension-oauth-uris.html)のセキュリティ:</span><span class="sxs-lookup"><span data-stu-id="2c54d-124">Security: [Extension for OAuth URIs](http://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="2c54d-125">FhirVersion の (コードが必要ですこれをピボットする必要がありますどちらのバージョンを理解します。</span><span class="sxs-lookup"><span data-stu-id="2c54d-125">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="2c54d-126">参照してください[https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html)他の詳細については、このフィールドを設定します。</span><span class="sxs-lookup"><span data-stu-id="2c54d-126">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="2c54d-127">患者</span><span class="sxs-lookup"><span data-stu-id="2c54d-127">Patient</span></span>

<span data-ttu-id="2c54d-128">Argonaut 患者のプロファイルのフィールドのサブセットは、最低限必要なフィールドを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="2c54d-128">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

1. <span data-ttu-id="2c54d-129">Name.Given</span><span class="sxs-lookup"><span data-stu-id="2c54d-129">Name.Given</span></span>
2. <span data-ttu-id="2c54d-130">Name.Family</span><span class="sxs-lookup"><span data-stu-id="2c54d-130">Name.Family</span></span>
3. <span data-ttu-id="2c54d-131">性別</span><span class="sxs-lookup"><span data-stu-id="2c54d-131">Gender</span></span>
4. <span data-ttu-id="2c54d-132">[誕生日]</span><span class="sxs-lookup"><span data-stu-id="2c54d-132">BirthDate</span></span>
5. <span data-ttu-id="2c54d-133">MRN (識別子)</span><span class="sxs-lookup"><span data-stu-id="2c54d-133">MRN (Identifier)</span></span>

<span data-ttu-id="2c54d-134">[Argonaut フィールド](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)だけでなく、優れたユーザー エクスペリエンスの患者のアプリケーションも読み取れる次のフィールド。</span><span class="sxs-lookup"><span data-stu-id="2c54d-134">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="2c54d-135">Name.Use</span><span class="sxs-lookup"><span data-stu-id="2c54d-135">Name.Use</span></span>
2. <span data-ttu-id="2c54d-136">Name.Prefix</span><span class="sxs-lookup"><span data-stu-id="2c54d-136">Name.Prefix</span></span>
3. <span data-ttu-id="2c54d-137">[GeneralPractitioner] - 患者のリソース (表示フィールド) で、GeneralPractitioner の参照を含める必要があります</span><span class="sxs-lookup"><span data-stu-id="2c54d-137">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="2c54d-138">リソース検索は、/Patient/_search し、次のパラメーターで POST メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="2c54d-138">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="2c54d-139">id</span><span class="sxs-lookup"><span data-stu-id="2c54d-139">id</span></span>
2. <span data-ttu-id="2c54d-140">家族 (家族の名前を持つ値を含むすべての患者のための検索条件) を =</span><span class="sxs-lookup"><span data-stu-id="2c54d-140">family=(searches for all patients whose family name contains the value)</span></span>
3. <span data-ttu-id="2c54d-141">指定された =\<substring></span><span class="sxs-lookup"><span data-stu-id="2c54d-141">given=\<substring></span></span>
4. <span data-ttu-id="2c54d-142">生年月日 =(exact match)</span><span class="sxs-lookup"><span data-stu-id="2c54d-142">birthdate=(exact match)</span></span>
5. <span data-ttu-id="2c54d-143">性別 = (管理の性別の 1 つの値)</span><span class="sxs-lookup"><span data-stu-id="2c54d-143">gender=(values being one of the administrative-gender)</span></span>
6. <span data-ttu-id="2c54d-144">\_カウント (返される結果の最大数)</span><span class="sxs-lookup"><span data-stu-id="2c54d-144">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="2c54d-145">応答は、検索結果として返されるレコードの合計数を含める必要があり、\_カウントが適用されます、PatientsApp によって返されるレコードの数を制限します。</span><span class="sxs-lookup"><span data-stu-id="2c54d-145">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="2c54d-146">識別子 =\<mrn></span><span class="sxs-lookup"><span data-stu-id="2c54d-146">identifier=\<mrn></span></span>

<span data-ttu-id="2c54d-147">目標は、するを検索およびフィルターを次のように患者のことです。</span><span class="sxs-lookup"><span data-stu-id="2c54d-147">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="2c54d-148">ID: これは、FHIR のすべてのリソースがリソースの ID です。</span><span class="sxs-lookup"><span data-stu-id="2c54d-148">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="2c54d-149">MRN: これは、医療スタッフが知っている患者の実際の識別子です。</span><span class="sxs-lookup"><span data-stu-id="2c54d-149">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="2c54d-150">この MRN が FHIR で識別子のリソースの内部識別子の型に基づくことを理解します。</span><span class="sxs-lookup"><span data-stu-id="2c54d-150">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="2c54d-151">名前</span><span class="sxs-lookup"><span data-stu-id="2c54d-151">Name</span></span>
- <span data-ttu-id="2c54d-152">[誕生日]</span><span class="sxs-lookup"><span data-stu-id="2c54d-152">Birthdate</span></span>

<span data-ttu-id="2c54d-153">次の呼び出しの例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c54d-153">See the following example of the call:</span></span>

* * *

    <span data-ttu-id="2c54d-154">要求: ポスト <fhir ・ server>/患者/_search 要求本文: 指定された ruth&family を = = 黒</span><span class="sxs-lookup"><span data-stu-id="2c54d-154">Request: POST <fhir-server>/Patient/_search Request Body: given=ruth&family=black</span></span>
    
    <span data-ttu-id="2c54d-155">応答: {"リソースの種類":「バンドル」、"id":"<bundle id>"、「メタ」: {"lastUpdated":"2019-01-14T23:44:45.052 + 00時 00分」}、[種類]:"searchset"、「合計」: 1 の場合、「リンク」: [{「関係」:「自己」、"url": <fhir-server>/患者として」}]、入力: [{"fullUrl": <fhir-server>/患者/<patient ・ id>"、「リソース」: {「リソースの種類」:「患者」、"id":"<patient id>"、「メタ」: {」バージョン Id」:「1」、"lastUpdated":"2017-10-18T18:32:37.000 + 00時 00分」}、「テキスト」: {[状態]:「生成」、"div": "</span><span class="sxs-lookup"><span data-stu-id="2c54d-155">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "meta": { "lastUpdated": "2019-01-14T23:44:45.052+00:00" }, "type": "searchset", "total": 1, "link": [ { "relation": "self", "url": <fhir-server>/Patient/_search" } ], "entry": [ { "fullUrl": <fhir-server>/Patient/<patient-id>", "resource": { "resourceType": "Patient", "id": "<patient-id>", "meta": { "versionId": "1", "lastUpdated": "2017-10-18T18:32:37.000+00:00" }, "text": { "status": "generated", "div": "</span></span><div><span data-ttu-id="2c54d-156">\n</span><span class="sxs-lookup"><span data-stu-id="2c54d-156">\n</span></span>        <p><span data-ttu-id="2c54d-157">ラス黒</span><span class="sxs-lookup"><span data-stu-id="2c54d-157">Ruth Black</span></span></p><span data-ttu-id="2c54d-158">\n</span><span class="sxs-lookup"><span data-stu-id="2c54d-158">\n</span></span>      </div><span data-ttu-id="2c54d-159">」}、[識別子]: [{を使用する]:「通常」、「種類」: {「コーディング」: [{システム:」http://hl7.org/fhir/v2/0203」、「コード」:「様」、「表示」:「医療記録番号」、"userSelected": false}]、「テキスト」:「医療記録番号」}、システム:」http://hospital.smarthealthit.org"、「値」:「1234567」}]「アクティブ」、: true の場合、」名]: [{を使用する]:「公式な」、「家族」:「黒」、「指定された」: [「ルース」C"</span><span class="sxs-lookup"><span data-stu-id="2c54d-159">" }, "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR", "display": "Medical record number", "userSelected": false } ], "text": "Medical record number" }, "system": "http://hospital.smarthealthit.org", "value": "1234567" } ], "active": true, "name": [ { "use": "official", "family": "Black", "given": [ "Ruth", "C."</span></span>
    <span data-ttu-id="2c54d-160">}]、「通信」: [{システム:「電話」、「値」:「800-599-2739」、「使用」:「ホーム」}、{システム:「電話」、「値」:「800-808-7785」、「使用」:「モバイル」}、{システム:「電子メール」、「値」:"ruth.black@example.com"}]、「性別」:「女性」、"生年月日":"1951-08-23」、」アドレス]: [{を使用する]:「ホーム」、「直線」: ["26 南 RdApt 22"]、「市区町村」:"Sapulpa"、「状態」:"OK"、"郵便番号":"74066"、"都道府県":"アメリカ"}]}、[検索]: {"モード":"一致"}}]}</span><span class="sxs-lookup"><span data-stu-id="2c54d-160">] } ], "telecom": [ { "system": "phone", "value": "800-599-2739", "use": "home" }, { "system": "phone", "value": "800-808-7785", "use": "mobile" }, { "system": "email", "value": "ruth.black@example.com" } ], "gender": "female", "birthDate": "1951-08-23", "address": [ { "use": "home", "line": [ "26 South RdApt 22" ], "city": "Sapulpa", "state": "OK", "postalCode": "74066", "country": "USA" } ] }, "search": { "mode": "match" } } ] }</span></span>

* * *

    <span data-ttu-id="2c54d-161">_LT_fhir-server>/患者/<patient ・ id> を取得する要求。</span><span class="sxs-lookup"><span data-stu-id="2c54d-161">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="2c54d-162">応答: {「リソースの種類」:「患者」、"id":"<patient id>"、[識別子]: [{を使用する]:「通常」、「種類」: {「コーディング」: [{システム:」http://hl7.org/fhir/v2/0203"、「コード」:「様」、}]、「テキスト」:「医療記録番号」}、「値」:「1234567」}]「名前」、: [{を使用する]:「正式な」、」ファミリ」:「アダム」、「指定」: ["ダニエル","X"です。</span><span class="sxs-lookup"><span data-stu-id="2c54d-162">Response: { "resourceType": "Patient", "id": "<patient-id>", "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR", } ], "text": "Medical record number" }, "value": "1234567" } ], "name": [ { "use": "official", "family": "Adams", "given": [ "Daniel", "X."</span></span> <span data-ttu-id="2c54d-163">{]}]、「性別」:「男性」、「生年月日」:「1925-12-23」、}</span><span class="sxs-lookup"><span data-stu-id="2c54d-163">] } ], "gender": "male", "birthDate": "1925-12-23", }</span></span>

* * *

<span data-ttu-id="2c54d-164">参照してください[http://hl7.org/fhir/stu3/patient.html](http://hl7.org/fhir/stu3/patient.html)他の詳細については、このフィールドを設定します。</span><span class="sxs-lookup"><span data-stu-id="2c54d-164">See [http://hl7.org/fhir/stu3/patient.html](http://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="2c54d-165">観測</span><span class="sxs-lookup"><span data-stu-id="2c54d-165">Observation</span></span>

<span data-ttu-id="2c54d-166">これらは、 [Argonaut-バイタル ・ サインのプロファイル](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)の一部である最低限の必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="2c54d-166">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

1. <span data-ttu-id="2c54d-167">有効 (日付時刻または期間)</span><span class="sxs-lookup"><span data-stu-id="2c54d-167">Effective (date time or period)</span></span>
2. <span data-ttu-id="2c54d-168">Code.Coding.Code</span><span class="sxs-lookup"><span data-stu-id="2c54d-168">Code.Coding.Code</span></span>
3. <span data-ttu-id="2c54d-169">ValueQuantity.Value</span><span class="sxs-lookup"><span data-stu-id="2c54d-169">ValueQuantity.Value</span></span>

<span data-ttu-id="2c54d-170">Argonaut のフィールドだけでなく、優れたユーザー エクスペリエンスの患者のアプリケーションも読み取れる次のフィールド。</span><span class="sxs-lookup"><span data-stu-id="2c54d-170">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="2c54d-171">Code.Coding.Display</span><span class="sxs-lookup"><span data-stu-id="2c54d-171">Code.Coding.Display</span></span>
2. <span data-ttu-id="2c54d-172">ValueQuantity.Unit</span><span class="sxs-lookup"><span data-stu-id="2c54d-172">ValueQuantity.Unit</span></span>

<span data-ttu-id="2c54d-173">リソース検索では、GET メソッドと、次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="2c54d-173">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="2c54d-174">患者 =\<患者の id></span><span class="sxs-lookup"><span data-stu-id="2c54d-174">patient=\<patient id></span></span>
2. <span data-ttu-id="2c54d-175">_sort = 日付</span><span class="sxs-lookup"><span data-stu-id="2c54d-175">_sort=-date</span></span>
3. <span data-ttu-id="2c54d-176">カテゴリ (のクエリは"カテゴリ = 重要な記号") バイタル ・ サインの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="2c54d-176">category (we will query for “category=vital-signs”) to retrieve the list of vital signs.</span></span>

<span data-ttu-id="2c54d-177">呼び出しの次の使用例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c54d-177">Refer to this example of the call:</span></span>

* * *

    <span data-ttu-id="2c54d-178">要求: 観察/<fhir ・ server> を取得? 患者 = <patient id>&category = 重要な記号</span><span class="sxs-lookup"><span data-stu-id="2c54d-178">Request: GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs</span></span>
    
    <span data-ttu-id="2c54d-179">応答: {「リソースの種類」:「バンドル」、「id」:"<bundle id>"、"種類":"searchset"、"合計": 20、入力: [{"リソース": {「リソースの種類」:「観察」、"id":"<resource id>"、"カテゴリ": [{"コーディング": [{システム:"http://hl7.org/fhir/observation-category"、「コード」:」重要な記号"}]、}]、「コード」: {「コーディング」: [{システム:」http://loinc.org」、「コード」:「8867-4」、「表示」:"heart_rate"}]}、"effectiveDateTime":」2009-04-08T00:00:00-06時 00分"、"valueQuantity": {「値」: 72.0、「出荷単位」:"{拍}/分」、システム」:」http://unitsofmeasure.org」、}}}。</span><span class="sxs-lookup"><span data-stu-id="2c54d-179">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": [ { "coding": [ { "system": "http://hl7.org/fhir/observation-category", "code": "vital-signs" } ], } ], "code": { "coding": [ { "system": "http://loinc.org", "code": "8867-4", "display": "heart_rate" } ] }, "effectiveDateTime": "2009-04-08T00:00:00-06:00", "valueQuantity": { "value": 72.0, "unit": "{beats}/min", "system": "http://unitsofmeasure.org", } } }, .</span></span>
        <span data-ttu-id="2c54d-180">.</span><span class="sxs-lookup"><span data-stu-id="2c54d-180"></span></span>
        <span data-ttu-id="2c54d-181">.</span><span class="sxs-lookup"><span data-stu-id="2c54d-181"></span></span>
      <span data-ttu-id="2c54d-182">] }</span><span class="sxs-lookup"><span data-stu-id="2c54d-182"></span></span>

* * *

<span data-ttu-id="2c54d-183">参照してください[https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html)他の詳細については、このフィールドを設定します。</span><span class="sxs-lookup"><span data-stu-id="2c54d-183">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="2c54d-184">状態</span><span class="sxs-lookup"><span data-stu-id="2c54d-184">Condition</span></span>

<span data-ttu-id="2c54d-185">[Argonaut 条件プロファイル](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)の一部である最低限の必須フィールドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="2c54d-185">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

1. <span data-ttu-id="2c54d-186">Code.Coding[0]。表示</span><span class="sxs-lookup"><span data-stu-id="2c54d-186">Code.Coding[0].Display</span></span>

<span data-ttu-id="2c54d-187">Argonaut のフィールドだけでなく、優れたユーザー エクスペリエンスの患者のアプリケーションも読み取れる次のフィールド。</span><span class="sxs-lookup"><span data-stu-id="2c54d-187">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="2c54d-188">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="2c54d-188">AssertedDate</span></span>
2. <span data-ttu-id="2c54d-189">重大度レベル</span><span class="sxs-lookup"><span data-stu-id="2c54d-189">Severity</span></span>

<span data-ttu-id="2c54d-190">リソース検索では、GET メソッドと、次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="2c54d-190">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="2c54d-191">患者 =\<患者の id></span><span class="sxs-lookup"><span data-stu-id="2c54d-191">patient=\<patient id></span></span>
2. <span data-ttu-id="2c54d-192">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="2c54d-192">_count=\<max results></span></span>

<span data-ttu-id="2c54d-193">この呼び出しの次の使用例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c54d-193">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="2c54d-194">要求の場合: <fhir-server> または条件を取得しますか? 患者 = <patient id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="2c54d-194">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="2c54d-195">応答します {"リソースの種類」:「バンドル」、「id」:"<bundle id>"、"種類":"searchset"、"合計": 2、[入力]: [{"リソース": {"リソースの種類」:"条件"、"id":"<resource id>"、"コード": {"コーディング": [{システム:"http://snomed.info/sct"、"コード":"185903001"、」。表示する]:"インフルエンザ注射のニーズ、「}]}、「重要度」: {"コーディング": [{システム:"http://snomed.info/sct"、「コード」:「24484000」を表示する]:「重大」}]}、"assertedDate":"2018-04-04」}}。</span><span class="sxs-lookup"><span data-stu-id="2c54d-195">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 2, "entry": [ { "resource": { "resourceType": "Condition", "id": "<resource-id>", "code": { "coding": [ { "system": "http://snomed.info/sct", "code": "185903001", "display": "Needs influenza immunization", } ] }, "severity": { "coding": [ { "system": "http://snomed.info/sct", "code": "24484000", "display": "Severe" } ] }, "assertedDate": "2018-04-04" } }, .</span></span>
        <span data-ttu-id="2c54d-196">.</span><span class="sxs-lookup"><span data-stu-id="2c54d-196"></span></span>
        <span data-ttu-id="2c54d-197">.</span><span class="sxs-lookup"><span data-stu-id="2c54d-197"></span></span>
      <span data-ttu-id="2c54d-198">] }</span><span class="sxs-lookup"><span data-stu-id="2c54d-198"></span></span>

* * *
<span data-ttu-id="2c54d-199">参照してください[http://hl7.org/fhir/stu3/condition.html](http://hl7.org/fhir/stu3/condition.html)他の詳細については、このフィールドを設定します。</span><span class="sxs-lookup"><span data-stu-id="2c54d-199">See [http://hl7.org/fhir/stu3/condition.html](http://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="2c54d-200">発生します。</span><span class="sxs-lookup"><span data-stu-id="2c54d-200">Encounter</span></span>

<span data-ttu-id="2c54d-201">これらは、最低限の必須フィールドで、[プロファイルの u. s. コアが発生する](http://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html)「必要があります」フィールドのサブセットである)。</span><span class="sxs-lookup"><span data-stu-id="2c54d-201">These are the minimum required fields, which are a subset of the [US Core Encounter profile](http://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) “must have” fields).</span></span>

1. <span data-ttu-id="2c54d-202">状態</span><span class="sxs-lookup"><span data-stu-id="2c54d-202">Status</span></span>
2. <span data-ttu-id="2c54d-203">[0] を入力します。[0] をコーディングします。表示</span><span class="sxs-lookup"><span data-stu-id="2c54d-203">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="2c54d-204">さらに、プロファイルの u. s. コアの発生から次のフィールドする必要があります「サポート」のフィールド。</span><span class="sxs-lookup"><span data-stu-id="2c54d-204">In addition, the following fields from US Core Encounter profile’s “must support” fields:</span></span>

1. <span data-ttu-id="2c54d-205">Period.Start</span><span class="sxs-lookup"><span data-stu-id="2c54d-205">Period.Start</span></span>
2. <span data-ttu-id="2c54d-206">[0] の場所です。Location.Display</span><span class="sxs-lookup"><span data-stu-id="2c54d-206">Location[0].Location.Display</span></span>

<span data-ttu-id="2c54d-207">リソース検索では、GET メソッドと、次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="2c54d-207">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="2c54d-208">患者 =\<患者の id></span><span class="sxs-lookup"><span data-stu-id="2c54d-208">patient=\<patient id></span></span>
2. <span data-ttu-id="2c54d-209">_sort:desc =\<ex フィールドです。</span><span class="sxs-lookup"><span data-stu-id="2c54d-209">_sort:desc=\<field ex.</span></span> <span data-ttu-id="2c54d-210">date></span><span class="sxs-lookup"><span data-stu-id="2c54d-210">date></span></span>
3. <span data-ttu-id="2c54d-211">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="2c54d-211">_count=\<max results></span></span>

<span data-ttu-id="2c54d-212">目標は、患者の最後の既知の場所を取得できるようにすること。</span><span class="sxs-lookup"><span data-stu-id="2c54d-212">The goal is to be able to retrieve the patient’s last known location.</span></span> <span data-ttu-id="2c54d-213">各遭遇は、場所のリソースを参照します。</span><span class="sxs-lookup"><span data-stu-id="2c54d-213">Each encounter references a location resource.</span></span> <span data-ttu-id="2c54d-214">参照では、保管場所の表示のフィールドを含むものとも。</span><span class="sxs-lookup"><span data-stu-id="2c54d-214">The reference shall also include the location’s display field.</span></span>

<span data-ttu-id="2c54d-215">参照してください[http://hl7.org/fhir/stu3/encounter.html](http://hl7.org/fhir/stu3/encounter.html)他の詳細については、このフィールドを設定します。</span><span class="sxs-lookup"><span data-stu-id="2c54d-215">See [http://hl7.org/fhir/stu3/encounter.html](http://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="2c54d-216">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="2c54d-216">AllergyIntolerance</span></span>

<span data-ttu-id="2c54d-217">[Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html)プロファイルの一部は、最低限必要なフィールドがあります。</span><span class="sxs-lookup"><span data-stu-id="2c54d-217">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

1. <span data-ttu-id="2c54d-218">Code.Text</span><span class="sxs-lookup"><span data-stu-id="2c54d-218">Code.Text</span></span>
2. <span data-ttu-id="2c54d-219">Code.Coding[0]。表示</span><span class="sxs-lookup"><span data-stu-id="2c54d-219">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="2c54d-220">ClinicalStatus/VerificationStatus (読み取る両方)</span><span class="sxs-lookup"><span data-stu-id="2c54d-220">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="2c54d-221">Argonaut のフィールドに加え、優れたユーザー エクスペリエンスの患者アプリケーション参照することも次のフィールド。</span><span class="sxs-lookup"><span data-stu-id="2c54d-221">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

1. <span data-ttu-id="2c54d-222">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="2c54d-222">AssertedDate</span></span>
2. <span data-ttu-id="2c54d-223">Note.Text</span><span class="sxs-lookup"><span data-stu-id="2c54d-223">Note.Text</span></span>
3. <span data-ttu-id="2c54d-224">反力</span><span class="sxs-lookup"><span data-stu-id="2c54d-224">Reaction</span></span>
    1. <span data-ttu-id="2c54d-225">物質 (1 つのコーディング要素)</span><span class="sxs-lookup"><span data-stu-id="2c54d-225">Substance (one coding element)</span></span>
    2. <span data-ttu-id="2c54d-226">付きマニフェスト (1 つのコーディング要素)</span><span class="sxs-lookup"><span data-stu-id="2c54d-226">Manifestation (one coding element)</span></span>

<span data-ttu-id="2c54d-227">リソース検索では、GET メソッドと、次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="2c54d-227">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="2c54d-228">患者 =\<患者の id></span><span class="sxs-lookup"><span data-stu-id="2c54d-228">Patient =  \<patient id></span></span>

<span data-ttu-id="2c54d-229">次の呼び出しの例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c54d-229">See the following example of the call:</span></span> 

* * *

    <span data-ttu-id="2c54d-230">要求の場合: <fhir-server>/AllergyIntolerance を取得しますか? 患者 = <patient id></span><span class="sxs-lookup"><span data-stu-id="2c54d-230">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="2c54d-231">応答: {"リソースの種類":「バンドル」、"id":"<bundle id>"、「種類」:"searchset"、「合計」: 1 の場合、[入力]: [{「リソース」: {「リソースの種類」:"AllergyIntolerance"、"id":"<resource id>"、"clinicalStatus":「アクティブ」、"verificationStatus」:「確認」、「コード」: {「コーディング」: [{システム:"http://rxnav.nlm.nih.gov/REST/Ndfrt"、「コード」:"N0000175503"を表示する]:「sulfonamide antibacterial」、}]、「テキスト」:"sulfonamide antibacterial"}、"assertedDate":"2018-01-01T00:00:00-07時 00分」、「反力」: [{」付きマニフェスト」: [{「コーディング」: [{システム:"http://snomed.info/sct"、"コード"。 「271807003」、「表示」:"スキン rash"}]、「文字列」:"スキン rash"}]、}]}}]}</span><span class="sxs-lookup"><span data-stu-id="2c54d-231">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "clinicalStatus": "active",         "verificationStatus": "confirmed",         "code": {           "coding": [             {               "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",               "code": "N0000175503",               "display": "sulfonamide antibacterial",             }           ],           "text": "sulfonamide antibacterial"         },         "assertedDate": "2018-01-01T00:00:00-07:00",         "reaction": [           {             "manifestation": [               {                 "coding": [                   {                     "system": "http://snomed.info/sct",                     "code": "271807003",                     "display": "skin rash",                   }                 ],                 "text": "skin rash"               }             ],           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="2c54d-232">参照してください[http://hl7.org/fhir/stu3/allergyintolerance.html](http://hl7.org/fhir/stu3/allergyintolerance.html)他の詳細については、このフィールドを設定します。</span><span class="sxs-lookup"><span data-stu-id="2c54d-232">See [http://hl7.org/fhir/stu3/allergyintolerance.html](http://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="2c54d-233">薬の要求</span><span class="sxs-lookup"><span data-stu-id="2c54d-233">Medication Request</span></span>

<span data-ttu-id="2c54d-234">[プロファイルの u. s. の中核となる薬の要求](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)の一部は、最低限の必須フィールドがあります。</span><span class="sxs-lookup"><span data-stu-id="2c54d-234">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

1. <span data-ttu-id="2c54d-235">Medication.Display (場合の参照)</span><span class="sxs-lookup"><span data-stu-id="2c54d-235">Medication.Display (if Reference)</span></span>
2. <span data-ttu-id="2c54d-236">Medication.Text (場合 CodableConcept)</span><span class="sxs-lookup"><span data-stu-id="2c54d-236">Medication.Text (if CodableConcept)</span></span>
3. <span data-ttu-id="2c54d-237">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="2c54d-237">AuthoredOn</span></span>
4. <span data-ttu-id="2c54d-238">Requester.Agent.Display</span><span class="sxs-lookup"><span data-stu-id="2c54d-238">Requester.Agent.Display</span></span>

<span data-ttu-id="2c54d-239">米国の主要なフィールドだけでなく、優れたユーザー エクスペリエンスの患者のアプリケーションを参照することも次のフィールド。</span><span class="sxs-lookup"><span data-stu-id="2c54d-239">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="2c54d-240">DosageInstruction れました。テキスト</span><span class="sxs-lookup"><span data-stu-id="2c54d-240">DosageInstruction[..].Text</span></span>
2. <span data-ttu-id="2c54d-241">テキスト</span><span class="sxs-lookup"><span data-stu-id="2c54d-241">Text</span></span>

<span data-ttu-id="2c54d-242">リソース検索では、GET メソッドと、次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="2c54d-242">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="2c54d-243">患者 =\<患者の id></span><span class="sxs-lookup"><span data-stu-id="2c54d-243">patient=\<patient id></span></span>
2. <span data-ttu-id="2c54d-244">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="2c54d-244">_count=\<max results></span></span>

<span data-ttu-id="2c54d-245">参照してください[https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html)他の詳細については、このフィールドを設定します。</span><span class="sxs-lookup"><span data-stu-id="2c54d-245">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="2c54d-246">カバレッジ</span><span class="sxs-lookup"><span data-stu-id="2c54d-246">Coverage</span></span>

<span data-ttu-id="2c54d-247">Argonaut または米国のコアのいずれかのプロファイルの対象になっていない、最低限必要なフィールドがあります。</span><span class="sxs-lookup"><span data-stu-id="2c54d-247">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="2c54d-248">少なくとも 1 つの要素のグループ化</span><span class="sxs-lookup"><span data-stu-id="2c54d-248">Grouping, at least one element with</span></span>
    1. <span data-ttu-id="2c54d-249">グループの表示インタ</span><span class="sxs-lookup"><span data-stu-id="2c54d-249">GroupDisplay</span></span>
    2. <span data-ttu-id="2c54d-250">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="2c54d-250">PlanDisplay</span></span>
2. <span data-ttu-id="2c54d-251">期間</span><span class="sxs-lookup"><span data-stu-id="2c54d-251">Period</span></span>
3. <span data-ttu-id="2c54d-252">サブスクライバー Id</span><span class="sxs-lookup"><span data-stu-id="2c54d-252">SubscriberId</span></span>

<span data-ttu-id="2c54d-253">リソース検索では、GET メソッドと、次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="2c54d-253">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="2c54d-254">患者 =\<患者の id></span><span class="sxs-lookup"><span data-stu-id="2c54d-254">Patient = \<patient id></span></span>

<span data-ttu-id="2c54d-255">参照してください[http://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html)他の詳細については、このフィールドを設定します。</span><span class="sxs-lookup"><span data-stu-id="2c54d-255">See [http://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
