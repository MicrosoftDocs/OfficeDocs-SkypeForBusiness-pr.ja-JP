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
# <a name="dstu2-interface-specification"></a><span data-ttu-id="aa86d-103">DSTU2 インターフェイスの仕様</span><span class="sxs-lookup"><span data-stu-id="aa86d-103">DSTU2 interface specification</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="aa86d-104">設定するか、マイクロソフト チームの患者のアプリケーションで動作する、FHIR サーバーを再構成する、アプリケーションがアクセスする必要がどのようなデータを理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa86d-104">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="aa86d-105">FHIR サーバーは、以下のリソースのバンドルを使用して POST 要求をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa86d-105">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="aa86d-106">患者</span><span class="sxs-lookup"><span data-stu-id="aa86d-106">Patient</span></span>](#patient)
- [<span data-ttu-id="aa86d-107">観測</span><span class="sxs-lookup"><span data-stu-id="aa86d-107">Observation</span></span>](#observation)
- [<span data-ttu-id="aa86d-108">状態</span><span class="sxs-lookup"><span data-stu-id="aa86d-108">Condition</span></span>](#condition)
- [<span data-ttu-id="aa86d-109">発生します。</span><span class="sxs-lookup"><span data-stu-id="aa86d-109">Encounter</span></span>](#encounter)
- [<span data-ttu-id="aa86d-110">Allergy 思いがけず</span><span class="sxs-lookup"><span data-stu-id="aa86d-110">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="aa86d-111">カバレッジ</span><span class="sxs-lookup"><span data-stu-id="aa86d-111">Coverage</span></span>](#coverage)
- [<span data-ttu-id="aa86d-112">薬注文</span><span class="sxs-lookup"><span data-stu-id="aa86d-112">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="aa86d-113">場所</span><span class="sxs-lookup"><span data-stu-id="aa86d-113">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="aa86d-114">患者のリソースは、唯一の必須のリソース (せず、アプリケーションがまったく読み込まれないです。</span><span class="sxs-lookup"><span data-stu-id="aa86d-114">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="aa86d-115">ただし、パートナーがマイクロソフト チームの患者のアプリケーションに最適なエンド ユーザー エクスペリエンスの下で提供されている仕様ごとの上記のすべてのリソースのサポートを実装することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="aa86d-115">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="aa86d-116">複数のリソースの Microsoft チームの患者のアプリケーションからのクエリは、FHIR サーバーの URL に要求のバンドル (バッチ) を転記します。</span><span class="sxs-lookup"><span data-stu-id="aa86d-116">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="aa86d-117">サーバーでは、各要求を処理し、各要求に一致するリソースのバンドルを返します。</span><span class="sxs-lookup"><span data-stu-id="aa86d-117">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="aa86d-118">詳細と例についてを参照してください[https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction)。</span><span class="sxs-lookup"><span data-stu-id="aa86d-118">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="aa86d-119">次の FHIR のすべてのリソースを直接リソース参照によってアクセスできることがあります。</span><span class="sxs-lookup"><span data-stu-id="aa86d-119">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="aa86d-120">準拠の最低限必要なフィールドを設定</span><span class="sxs-lookup"><span data-stu-id="aa86d-120">Conformance minimum required field set</span></span>

 <span data-ttu-id="aa86d-121">FHIR サーバーに事実の概要、機能の適合に関する声明を実装しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="aa86d-121">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="aa86d-122">予測しています、DSTU2 の FHIR サーバーのパラメーターの下。</span><span class="sxs-lookup"><span data-stu-id="aa86d-122">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

1. <span data-ttu-id="aa86d-123">残りの部分</span><span class="sxs-lookup"><span data-stu-id="aa86d-123">REST</span></span>
   1. <span data-ttu-id="aa86d-124">Mode</span><span class="sxs-lookup"><span data-stu-id="aa86d-124">Mode</span></span>
   2. <span data-ttu-id="aa86d-125">相互作用</span><span class="sxs-lookup"><span data-stu-id="aa86d-125">Interaction</span></span>
   3. <span data-ttu-id="aa86d-126">リソース: の種類</span><span class="sxs-lookup"><span data-stu-id="aa86d-126">Resource: Type</span></span>
   4. <span data-ttu-id="aa86d-127">[OAuth の Uri の拡張機能](http://hl7.org/fhir/extension-oauth-uris.html)のセキュリティ:</span><span class="sxs-lookup"><span data-stu-id="aa86d-127">Security: [Extension for OAuth URIs](http://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="aa86d-128">FhirVersion の (コードが必要ですどちらのバージョンを複数のバージョンをサポートしていますをピボットする必要があることを理解しておきたいです。</span><span class="sxs-lookup"><span data-stu-id="aa86d-128">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="aa86d-129">参照してください[https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html)他の詳細については、このフィールドを設定します。</span><span class="sxs-lookup"><span data-stu-id="aa86d-129">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="aa86d-130">患者</span><span class="sxs-lookup"><span data-stu-id="aa86d-130">Patient</span></span>

<span data-ttu-id="aa86d-131">[Argonaut 患者プロファイル](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)のフィールドのサブセットである最低限の必須フィールドがあります。</span><span class="sxs-lookup"><span data-stu-id="aa86d-131">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

1. <span data-ttu-id="aa86d-132">Name.Family</span><span class="sxs-lookup"><span data-stu-id="aa86d-132">Name.Family</span></span>
2. <span data-ttu-id="aa86d-133">Name.Given</span><span class="sxs-lookup"><span data-stu-id="aa86d-133">Name.Given</span></span>
3. <span data-ttu-id="aa86d-134">性別</span><span class="sxs-lookup"><span data-stu-id="aa86d-134">Gender</span></span>
4. <span data-ttu-id="aa86d-135">[誕生日]</span><span class="sxs-lookup"><span data-stu-id="aa86d-135">BirthDate</span></span>
5. <span data-ttu-id="aa86d-136">MRN (識別子)</span><span class="sxs-lookup"><span data-stu-id="aa86d-136">MRN (Identifier)</span></span>

<span data-ttu-id="aa86d-137">Argonaut のフィールドだけでなく、優れたユーザー エクスペリエンスの患者のアプリケーションも次のフィールドを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="aa86d-137">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="aa86d-138">Name.Use</span><span class="sxs-lookup"><span data-stu-id="aa86d-138">Name.Use</span></span>
2. <span data-ttu-id="aa86d-139">Name.Prefix</span><span class="sxs-lookup"><span data-stu-id="aa86d-139">Name.Prefix</span></span>
3. <span data-ttu-id="aa86d-140">(患者のリソースには、この参照は、次の例に示すように表示フィールドを含める必要があります) CareProvider</span><span class="sxs-lookup"><span data-stu-id="aa86d-140">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

* * *

    <span data-ttu-id="aa86d-141">_LT_fhir-server>/患者/<patient ・ id> を取得する要求。</span><span class="sxs-lookup"><span data-stu-id="aa86d-141">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="aa86d-142">応答: {「リソースの種類」:「患者」、"id":"<patient-id>"です。</span><span class="sxs-lookup"><span data-stu-id="aa86d-142">Response: { "resourceType": "Patient", "id": "<patient-id>", .</span></span>
      <span data-ttu-id="aa86d-143">.</span><span class="sxs-lookup"><span data-stu-id="aa86d-143"></span></span>
      <span data-ttu-id="aa86d-144">.</span><span class="sxs-lookup"><span data-stu-id="aa86d-144"></span></span>
      <span data-ttu-id="aa86d-145">[名]: [{を使用する]:「正式な」、「プレフィックス」: [「様」]「家族」: ["Chau"]"指定": ["も"]}]、識別子]: [{を使用する]:「正式な」、「タイプ」: {"コーディング": [{システム:"http://hl7.org/fhir/v2/0203"、"コード":"様"}]}、"値":"1234567"}]、"性別":「男性」、"生年月日":」1957-06-05"、"careProvider": [{0} を表示する]: [}]}</span><span class="sxs-lookup"><span data-stu-id="aa86d-145">"name": [ { "use": "official", "prefix": [ "Mr" ], "family": [ "Chau" ], "given": [ "Hugh" ] } ], "identifier": [ { "use": "official", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR" } ] }, "value": "1234567" } ], "gender": "male", "birthDate": "1957-06-05", "careProvider": [{ "display": "Jane Doe" }], }</span></span>

* * *

<span data-ttu-id="aa86d-146">リソース検索は、/Patient/_search し、次のパラメーターで POST メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="aa86d-146">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="aa86d-147">id</span><span class="sxs-lookup"><span data-stu-id="aa86d-147">id</span></span>
2. <span data-ttu-id="aa86d-148">ファミリ: を含む = (家族の名前を持つ値を含むすべての患者のための検索)。</span><span class="sxs-lookup"><span data-stu-id="aa86d-148">family:contains=(searches for all patients whose family name contains the value.)</span></span>
3. <span data-ttu-id="aa86d-149">指定された =\<substring></span><span class="sxs-lookup"><span data-stu-id="aa86d-149">given=\<substring></span></span>
4. <span data-ttu-id="aa86d-150">名前 =\<substring></span><span class="sxs-lookup"><span data-stu-id="aa86d-150">name=\<substring></span></span>
5. <span data-ttu-id="aa86d-151">生年月日 =(exact match)</span><span class="sxs-lookup"><span data-stu-id="aa86d-151">birthdate=(exact match)</span></span>
6. <span data-ttu-id="aa86d-152">\_カウント (返される結果の最大数)</span><span class="sxs-lookup"><span data-stu-id="aa86d-152">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="aa86d-153">応答は、検索結果として返されるレコードの合計数を含める必要があり、\_カウントが適用されます、PatientsApp によって返されるレコードの数を制限します。</span><span class="sxs-lookup"><span data-stu-id="aa86d-153">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="aa86d-154">識別子 =\<mrn></span><span class="sxs-lookup"><span data-stu-id="aa86d-154">identifier=\<mrn></span></span>

<span data-ttu-id="aa86d-155">目標は、するを検索およびフィルターを次のように患者のことです。</span><span class="sxs-lookup"><span data-stu-id="aa86d-155">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="aa86d-156">ID: これは、FHIR のすべてのリソースがリソースの ID です。</span><span class="sxs-lookup"><span data-stu-id="aa86d-156">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="aa86d-157">MRN: これは、医療スタッフが知っている患者の実際の識別子です。</span><span class="sxs-lookup"><span data-stu-id="aa86d-157">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="aa86d-158">この MRN が FHIR で識別子のリソースの内部識別子の種類に基づいて理解します。</span><span class="sxs-lookup"><span data-stu-id="aa86d-158">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="aa86d-159">名前</span><span class="sxs-lookup"><span data-stu-id="aa86d-159">Name</span></span>
- <span data-ttu-id="aa86d-160">[誕生日]</span><span class="sxs-lookup"><span data-stu-id="aa86d-160">Birthdate</span></span>

<span data-ttu-id="aa86d-161">この呼び出しの次の使用例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa86d-161">See the following example  of this call.</span></span>

* * *

    <span data-ttu-id="aa86d-162">要求: ポスト <fhir ・ server>/患者/_search 要求本文: 指定された hugh&family を = = chau</span><span class="sxs-lookup"><span data-stu-id="aa86d-162">Request: POST <fhir-server>/Patient/_search Request Body: given=hugh&family=chau</span></span>
    
    <span data-ttu-id="aa86d-163">応答: {「リソースの種類」:「バンドル」、"id":"<bundle-id>"。</span><span class="sxs-lookup"><span data-stu-id="aa86d-163">Response: { "resourceType": "Bundle", "id": "<bundle-id>", .</span></span>
      <span data-ttu-id="aa86d-164">.</span><span class="sxs-lookup"><span data-stu-id="aa86d-164"></span></span>
      <span data-ttu-id="aa86d-165">.</span><span class="sxs-lookup"><span data-stu-id="aa86d-165"></span></span>
      <span data-ttu-id="aa86d-166">[入力]: [{「リソース」: {「リソースの種類」:「患者」、"id":"<patient id>"、「名前」: [{「テキスト」:"も Chau、"「家族」: ["Chau"]「指定」: [「も」]}]、「性別」:「男性」、「生年月日」:」1957-06-05」}、[検索]: {「モード」:「一致」}}]}</span><span class="sxs-lookup"><span data-stu-id="aa86d-166">"entry": [ { "resource": { "resourceType": "Patient", "id": "<patient-id>", "name": [ { "text": "Hugh Chau", "family": [ "Chau" ], "given": [ "Hugh" ] } ], "gender": "male", "birthDate": "1957-06-05" }, "search": { "mode": "match" } } ] }</span></span>

* * *

<span data-ttu-id="aa86d-167">参照してください[https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html)他の詳細については、このフィールドを設定します。</span><span class="sxs-lookup"><span data-stu-id="aa86d-167">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="aa86d-168">観測</span><span class="sxs-lookup"><span data-stu-id="aa86d-168">Observation</span></span>

<span data-ttu-id="aa86d-169">Argonaut バイタル ・ サインのプロファイルの一部は、最低限必要なフィールドがあります。</span><span class="sxs-lookup"><span data-stu-id="aa86d-169">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 1. <span data-ttu-id="aa86d-170">有効 (日付時刻または期間)</span><span class="sxs-lookup"><span data-stu-id="aa86d-170">Effective (date time or period)</span></span>
 2. <span data-ttu-id="aa86d-171">Code.Coding.Code</span><span class="sxs-lookup"><span data-stu-id="aa86d-171">Code.Coding.Code</span></span>
 3. <span data-ttu-id="aa86d-172">ValueQuantity.Value</span><span class="sxs-lookup"><span data-stu-id="aa86d-172">ValueQuantity.Value</span></span>

<span data-ttu-id="aa86d-173">Argonaut のフィールドだけでなく、優れたユーザー エクスペリエンスの患者のアプリケーションも次のフィールドを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="aa86d-173">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 1. <span data-ttu-id="aa86d-174">Code.Coding.Display</span><span class="sxs-lookup"><span data-stu-id="aa86d-174">Code.Coding.Display</span></span>
 2. <span data-ttu-id="aa86d-175">ValueQuantity.Unit</span><span class="sxs-lookup"><span data-stu-id="aa86d-175">ValueQuantity.Unit</span></span>

<span data-ttu-id="aa86d-176">コンポーネントの観測値を使用すると、各コンポーネントの観測と同じロジックが適用されます。</span><span class="sxs-lookup"><span data-stu-id="aa86d-176">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="aa86d-177">リソース検索では、GET メソッドと、次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="aa86d-177">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="aa86d-178">患者 =\<患者の id\></span><span class="sxs-lookup"><span data-stu-id="aa86d-178">patient=\<patient id\></span></span>
2. <span data-ttu-id="aa86d-179">並べ替え: 説明 =\<ex フィールドです。</span><span class="sxs-lookup"><span data-stu-id="aa86d-179">sort:desc=\<field ex.</span></span> <span data-ttu-id="aa86d-180">日付\></span><span class="sxs-lookup"><span data-stu-id="aa86d-180">date\></span></span>

<span data-ttu-id="aa86d-181">目標は、[VitalSigns.DSTU.saz] (観察しますか?)、患者の最新のバイタル ・ サインを取得できるようにすること。</span><span class="sxs-lookup"><span data-stu-id="aa86d-181">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

* * *

    <span data-ttu-id="aa86d-182">要求: 観察/<fhir ・ server> を取得? 患者 = <patient-id>&_sort:desc = date&category = 重要な記号</span><span class="sxs-lookup"><span data-stu-id="aa86d-182">Request: GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs</span></span>
    
    <span data-ttu-id="aa86d-183">応答: {「リソースの種類」:「バンドル」、"id":"<bundle id>"、「種類」:"searchset"、「合計」: 20、[入力]: [{「リソース」: {「リソースの種類」:「観察」、"id":"<resource id>"、「カテゴリ」: {「コーディング」: [{コード":「重要な記号」}]、}、「コード」: {」コーディング": [{システム:"http://loinc.org"、「コード」:「39156-5」、「表示」:「bmi」}]}、"effectiveDateTime":」2009-12-01"、"valueQuantity": {"値": 34.4、「出荷単位」:"kg/m 2」、「システム」:」http://unitsofmeasure.org」、「コード」:"kg/m 2」}}、}、。</span><span class="sxs-lookup"><span data-stu-id="aa86d-183">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": { "coding": [ { code": "vital-signs" } ], }, "code": { "coding": [ { "system": "http://loinc.org", "code": "39156-5", "display": "bmi" } ], }, "effectiveDateTime": "2009-12-01", "valueQuantity": { "value": 34.4, "unit": "kg/m2", "system": "http://unitsofmeasure.org", "code": "kg/m2" } }, }, .</span></span>
        <span data-ttu-id="aa86d-184">.</span><span class="sxs-lookup"><span data-stu-id="aa86d-184"></span></span>
        <span data-ttu-id="aa86d-185">.</span><span class="sxs-lookup"><span data-stu-id="aa86d-185"></span></span>
      <span data-ttu-id="aa86d-186">] }</span><span class="sxs-lookup"><span data-stu-id="aa86d-186"></span></span>

* * *

<span data-ttu-id="aa86d-187">参照してください[https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html)他の詳細については、このフィールドを設定します。</span><span class="sxs-lookup"><span data-stu-id="aa86d-187">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="aa86d-188">状態</span><span class="sxs-lookup"><span data-stu-id="aa86d-188">Condition</span></span>

<span data-ttu-id="aa86d-189">[Argonaut 条件プロファイル](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)の一部である最低限の必須フィールドがあります。</span><span class="sxs-lookup"><span data-stu-id="aa86d-189">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="aa86d-190">Code.Coding[0]。表示</span><span class="sxs-lookup"><span data-stu-id="aa86d-190">Code.Coding[0].Display</span></span>

<span data-ttu-id="aa86d-191">Argonaut のフィールドだけでなく、優れたユーザー エクスペリエンスの患者のアプリケーションも読み取れる次のフィールド。</span><span class="sxs-lookup"><span data-stu-id="aa86d-191">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="aa86d-192">記録されている日付</span><span class="sxs-lookup"><span data-stu-id="aa86d-192">Date Recorded</span></span>
2. <span data-ttu-id="aa86d-193">重大度レベル</span><span class="sxs-lookup"><span data-stu-id="aa86d-193">Severity</span></span>

<span data-ttu-id="aa86d-194">リソース検索では、GET メソッドと、次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="aa86d-194">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="aa86d-195">患者 =\<患者の id></span><span class="sxs-lookup"><span data-stu-id="aa86d-195">patient=\<patient id></span></span>
2. <span data-ttu-id="aa86d-196">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="aa86d-196">_count=\<max results></span></span>

<span data-ttu-id="aa86d-197">この呼び出しの次の使用例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa86d-197">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="aa86d-198">要求の場合: <fhir-server> または条件を取得しますか? 患者 = <patient id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="aa86d-198">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="aa86d-199">応答: {「リソースの種類」:「バンドル」、"id":"<bundle id>"、「種類」:"searchset"、「合計」: 1 の場合、[入力]: [{「リソース」: {「リソースの種類」:「条件」、"id":"<resource id>"、「コード」: {「コーディング」: [{              システム:"http://snomed.info/sct"、「コード」:「386033004」、「表示」:「Neuropathy (nerve 破損)」}]}、"dateRecorded":] 2018-09-17"、「重要度」: {"コーディング": [{0}] system":"http://snomed.info/sct"、「コード」:「24484000」、「表示」:「重大」}]}}、}]}</span><span class="sxs-lookup"><span data-stu-id="aa86d-199">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Condition",         "id": "<resource-id>",         "code": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "386033004",               "display": "Neuropathy (nerve damage)"             }           ]         },         "dateRecorded": "2018-09-17",         "severity": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "24484000",               "display": "Severe"             }           ]         }       },     }   ] }</span></span>

* * *

<span data-ttu-id="aa86d-200">参照してください[https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html)他の詳細については、このフィールドを設定します。</span><span class="sxs-lookup"><span data-stu-id="aa86d-200">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="aa86d-201">発生します。</span><span class="sxs-lookup"><span data-stu-id="aa86d-201">Encounter</span></span>

<span data-ttu-id="aa86d-202">これらは、米国の主要な発生プロファイル」必要があります"フィールドのサブセットである最低限の必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="aa86d-202">These are the minimum required fields, which are a subset of the US Core Encounter profile “must have” fields:</span></span>

1. <span data-ttu-id="aa86d-203">状態</span><span class="sxs-lookup"><span data-stu-id="aa86d-203">Status</span></span>
2. <span data-ttu-id="aa86d-204">[0] を入力します。[0] をコーディングします。表示</span><span class="sxs-lookup"><span data-stu-id="aa86d-204">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="aa86d-205">さらに、フィールドから米国の主要な発生プロファイルの次のフィールドする必要があります「サポート」</span><span class="sxs-lookup"><span data-stu-id="aa86d-205">In addition, the following fields from US Core Encounter profile’s “must support” fields</span></span>

1. <span data-ttu-id="aa86d-206">Period.Start</span><span class="sxs-lookup"><span data-stu-id="aa86d-206">Period.Start</span></span>
2. <span data-ttu-id="aa86d-207">[0] の場所です。Location.Display</span><span class="sxs-lookup"><span data-stu-id="aa86d-207">Location[0].Location.Display</span></span>

<span data-ttu-id="aa86d-208">リソース検索では、GET メソッドと、次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="aa86d-208">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="aa86d-209">患者 =\<患者の id></span><span class="sxs-lookup"><span data-stu-id="aa86d-209">patient=\<patient id></span></span>
2. <span data-ttu-id="aa86d-210">_sort:desc =\<ex フィールドです。</span><span class="sxs-lookup"><span data-stu-id="aa86d-210">_sort:desc=\<field ex.</span></span> <span data-ttu-id="aa86d-211">date></span><span class="sxs-lookup"><span data-stu-id="aa86d-211">date></span></span>
3. <span data-ttu-id="aa86d-212">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="aa86d-212">_count=\<max results></span></span>

<span data-ttu-id="aa86d-213">目標は、患者の最後の既知の場所を取得できるようにすること。</span><span class="sxs-lookup"><span data-stu-id="aa86d-213">The goal is to be able to retrieve the patient’s last known location.</span></span> <span data-ttu-id="aa86d-214">各遭遇は、場所のリソースを参照します。</span><span class="sxs-lookup"><span data-stu-id="aa86d-214">Each encounter references a location resource.</span></span> <span data-ttu-id="aa86d-215">参照では、保管場所の表示のフィールドを含むものとも。</span><span class="sxs-lookup"><span data-stu-id="aa86d-215">The reference shall also include the location’s display field.</span></span> <span data-ttu-id="aa86d-216">この呼び出しの次の使用例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa86d-216">See the following example of this call.</span></span>
* * *

    <span data-ttu-id="aa86d-217">要求: <fhir-server>/出会いを取得しますか? 患者 = <patient-id>&_sort:desc = date&_count = 1</span><span class="sxs-lookup"><span data-stu-id="aa86d-217">Request: GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1</span></span>
    
    <span data-ttu-id="aa86d-218">応答: {「リソースの種類」:「バンドル」、「タイプ」:"searchset"、「合計」: 1 の場合、[入力]: [{「リソース」: {"リソースの種類」:"発生"、"id":"<resource id>"、[識別子]: [{を使用する]:「正式な」、「値」:"<id>」}]、[状態:」が到着した」、「型」: [{「コーディング」: [{を表示する]: 予定}]、}]"患者"、: {参照:"患者と <patient-id>"}"期間"、: {スタート ボタン:"09/17/2018 午後 1:00:00"}、場所: [{             [場所]: {を表示する]:「クリニック-ENT}、}]}}]}</span><span class="sxs-lookup"><span data-stu-id="aa86d-218">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Encounter",         "id": "<resource-id>",         "identifier": [{ "use": "official", "value": "<id>" }],         "status": "arrived",         "type": [           {             "coding": [{ "display": "Appointment" }],           }         ],         "patient": { "reference": "Patient/<patient-id>" },         "period": { "start": "09/17/2018 1:00:00 PM" },         "location": [           {             "location": { "display": "Clinic - ENT" },           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="aa86d-219">参照してください[https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm)他の詳細については、このフィールドを設定します。</span><span class="sxs-lookup"><span data-stu-id="aa86d-219">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="aa86d-220">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="aa86d-220">AllergyIntolerance</span></span>

<span data-ttu-id="aa86d-221">Argonaut AllergyIntolerance プロファイルの一部は、最低限必要なフィールドがあります。</span><span class="sxs-lookup"><span data-stu-id="aa86d-221">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

1. <span data-ttu-id="aa86d-222">Code.Text</span><span class="sxs-lookup"><span data-stu-id="aa86d-222">Code.Text</span></span>
2. <span data-ttu-id="aa86d-223">Code.Coding[0]。表示</span><span class="sxs-lookup"><span data-stu-id="aa86d-223">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="aa86d-224">状態</span><span class="sxs-lookup"><span data-stu-id="aa86d-224">Status</span></span>

<span data-ttu-id="aa86d-225">Argonaut のフィールドだけでなく、優れたユーザー エクスペリエンスの患者のアプリケーションも次のフィールドを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="aa86d-225">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="aa86d-226">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="aa86d-226">RecordedDate</span></span>
2. <span data-ttu-id="aa86d-227">Note.Text</span><span class="sxs-lookup"><span data-stu-id="aa86d-227">Note.Text</span></span>
3. <span data-ttu-id="aa86d-228">反 [.]。Substance.Text</span><span class="sxs-lookup"><span data-stu-id="aa86d-228">Reaction[..].Substance.Text</span></span>
4. <span data-ttu-id="aa86d-229">反 [.]。付きマニフェスト [.]。テキスト</span><span class="sxs-lookup"><span data-stu-id="aa86d-229">Reaction[..].Manifestation[..].Text</span></span>
5. <span data-ttu-id="aa86d-230">Text.Div</span><span class="sxs-lookup"><span data-stu-id="aa86d-230">Text.Div</span></span>

<span data-ttu-id="aa86d-231">リソース検索では、GET メソッドと、次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="aa86d-231">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="aa86d-232">患者 =\<患者の id></span><span class="sxs-lookup"><span data-stu-id="aa86d-232">Patient =  \<patient id></span></span>

<span data-ttu-id="aa86d-233">この呼び出しの次の使用例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa86d-233">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="aa86d-234">要求の場合: <fhir-server>/AllergyIntolerance を取得しますか? 患者 = <patient id></span><span class="sxs-lookup"><span data-stu-id="aa86d-234">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="aa86d-235">応答: {「リソースの種類」:「バンドル」、"id":"<bundle id>"、「種類」:"searchset"、「合計」: 1 の場合、[入力]: [{「リソース」: {「リソースの種類」:"AllergyIntolerance"、"id":"<resource id>"、"recordedDate":"2018-09-17T07:00:00.000Z」、「物質」: {"テキスト":「までナット」}、状態:"確認"、"反": [{"物質": {「テキスト」:「までナット allergenic は、Injectable の製品を抽出」}、"manifestati: [{「文字列」:「Anaphylactic 反」}]}]}}]}</span><span class="sxs-lookup"><span data-stu-id="aa86d-235">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "recordedDate": "2018-09-17T07:00:00.000Z",         "substance": {           "text": "Cashew nuts"         },         "status": "confirmed",         "reaction": [           {             "substance": {               "text": "cashew nut allergenic extract Injectable Product"             },             "manifestation": [               {                 "text": "Anaphylactic reaction"               }             ]           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="aa86d-236">参照してください[https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html)他の詳細については、このフィールドを設定します。</span><span class="sxs-lookup"><span data-stu-id="aa86d-236">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="aa86d-237">薬注文</span><span class="sxs-lookup"><span data-stu-id="aa86d-237">Medication Order</span></span>

<span data-ttu-id="aa86d-238">Argonaut MedicationOrder プロファイルの一部は、最低限必要なフィールドがあります。</span><span class="sxs-lookup"><span data-stu-id="aa86d-238">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

1. <span data-ttu-id="aa86d-239">DateWritten</span><span class="sxs-lookup"><span data-stu-id="aa86d-239">DateWritten</span></span>
2. <span data-ttu-id="aa86d-240">Prescriber.Display</span><span class="sxs-lookup"><span data-stu-id="aa86d-240">Prescriber.Display</span></span>
3. <span data-ttu-id="aa86d-241">Medication.Display (場合の参照)</span><span class="sxs-lookup"><span data-stu-id="aa86d-241">Medication.Display (if reference)</span></span>
4. <span data-ttu-id="aa86d-242">Medication.Text (場合の概念)</span><span class="sxs-lookup"><span data-stu-id="aa86d-242">Medication.Text (if concept)</span></span>

<span data-ttu-id="aa86d-243">Argonaut のフィールドだけでなく、優れたユーザー エクスペリエンスの患者のアプリケーションも読み取れる次のフィールド。</span><span class="sxs-lookup"><span data-stu-id="aa86d-243">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="aa86d-244">DateEnded</span><span class="sxs-lookup"><span data-stu-id="aa86d-244">DateEnded</span></span>
2. <span data-ttu-id="aa86d-245">DosageInstruction.Text</span><span class="sxs-lookup"><span data-stu-id="aa86d-245">DosageInstruction.Text</span></span>
3. <span data-ttu-id="aa86d-246">Text.Div</span><span class="sxs-lookup"><span data-stu-id="aa86d-246">Text.Div</span></span>

<span data-ttu-id="aa86d-247">リソース検索では、GET メソッドと、次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="aa86d-247">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="aa86d-248">患者 =\<患者の id></span><span class="sxs-lookup"><span data-stu-id="aa86d-248">patient=\<patient id></span></span>
2. <span data-ttu-id="aa86d-249">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="aa86d-249">_count=\<max results></span></span>

<span data-ttu-id="aa86d-250">この呼び出しの次の使用例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa86d-250">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="aa86d-251">要求の場合: <fhir-server>/MedicationOrder を取得しますか? 患者 = <patient id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="aa86d-251">Request: GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="aa86d-252">応答: {「リソースの種類」:「バンドル」、"id":"<bundle id>"、「種類」:"searchset"、「合計」: 1 の場合、[入力]: [{「リソース」: {「リソースの種類」:"MedicationOrder"、"id":"<resource id>"、"dateWritten":「2018-09-17」、"・ メディア ・cationCodeableConcept": {「テキスト」:「Lisinopril 20 MG 口頭タブレット」}「prescriber」、: {を表示する]: [}、"dosageInstruction": [{「テキスト」:"1 日"}]}}]}</span><span class="sxs-lookup"><span data-stu-id="aa86d-252">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "MedicationOrder",         "id": "<resource-id>",         "dateWritten": "2018-09-17",         "medicationCodeableConcept": {           "text": "Lisinopril 20 MG Oral Tablet"         },         "prescriber": {           "display": "Jane Doe"         },         "dosageInstruction": [           {             "text": "1 daily"           }         ]       }     }   ] }</span></span>

* * *  

<span data-ttu-id="aa86d-253">参照してください[https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html)他の詳細については、このフィールドを設定します。</span><span class="sxs-lookup"><span data-stu-id="aa86d-253">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="aa86d-254">カバレッジ</span><span class="sxs-lookup"><span data-stu-id="aa86d-254">Coverage</span></span>

<span data-ttu-id="aa86d-255">Argonaut または米国のコアのいずれかのプロファイルの対象になっていない、最低限必要なフィールドがあります。</span><span class="sxs-lookup"><span data-stu-id="aa86d-255">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="aa86d-256">Payor</span><span class="sxs-lookup"><span data-stu-id="aa86d-256">Payor</span></span>

<span data-ttu-id="aa86d-257">リソース検索では、GET メソッドと、次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="aa86d-257">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="aa86d-258">患者 =\<患者の id></span><span class="sxs-lookup"><span data-stu-id="aa86d-258">patient=\<patient id></span></span>

<span data-ttu-id="aa86d-259">この呼び出しの次の使用例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa86d-259">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="aa86d-260">要求の場合: <fhir-server>/対応範囲を取得しますか? 患者 = <patient id></span><span class="sxs-lookup"><span data-stu-id="aa86d-260">Request: GET <fhir-server>/Coverage?patient=<patient-id></span></span>
    
    <span data-ttu-id="aa86d-261">応答: {「リソースの種類」:「バンドル」、「タイプ」:"searchset"、「合計」: 1 の場合、[入力]: [{「リソース」: {"リソースの種類":"補充"、"id":"<resource id>"、「計画」:「いいえ主保険」、「サブスクライバー」: {参照:"患者/<patient id>"}}}]}</span><span class="sxs-lookup"><span data-stu-id="aa86d-261">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Coverage",         "id": "<resource-id>",         "plan": "No Primary Insurance",         "subscriber": { "reference": "Patient/<patient-id>" }       }     }   ] }</span></span>

* * *

<span data-ttu-id="aa86d-262">参照してください[https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html)他の詳細については、このフィールドを設定します。</span><span class="sxs-lookup"><span data-stu-id="aa86d-262">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="aa86d-263">場所</span><span class="sxs-lookup"><span data-stu-id="aa86d-263">Location</span></span>

<span data-ttu-id="aa86d-264">このリソースは、[発生する](#encounter)リソースの参照としてのみ使用されています。</span><span class="sxs-lookup"><span data-stu-id="aa86d-264">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="aa86d-265">参照してください[https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html)他の詳細については、このフィールドを設定します。</span><span class="sxs-lookup"><span data-stu-id="aa86d-265">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
