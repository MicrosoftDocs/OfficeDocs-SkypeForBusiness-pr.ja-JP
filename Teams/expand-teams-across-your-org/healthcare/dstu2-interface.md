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
# <a name="dstu2-interface-specification"></a><span data-ttu-id="26796-103">DSTU2 インターフェイスの仕様</span><span class="sxs-lookup"><span data-stu-id="26796-103">DSTU2 interface specification</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="26796-104">Microsoft Teams の患者と連携するように FHIR サーバーを設定または再構成するには、アプリがアクセスする必要があるデータを把握する必要があります。</span><span class="sxs-lookup"><span data-stu-id="26796-104">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="26796-105">FHIR サーバーでは、次のリソースについて、バンドルを使った POST 要求をサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="26796-105">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="26796-106">診療</span><span class="sxs-lookup"><span data-stu-id="26796-106">Patient</span></span>](#patient)
- [<span data-ttu-id="26796-107">観察</span><span class="sxs-lookup"><span data-stu-id="26796-107">Observation</span></span>](#observation)
- [<span data-ttu-id="26796-108">状態</span><span class="sxs-lookup"><span data-stu-id="26796-108">Condition</span></span>](#condition)
- [<span data-ttu-id="26796-109">状況</span><span class="sxs-lookup"><span data-stu-id="26796-109">Encounter</span></span>](#encounter)
- [<span data-ttu-id="26796-110">Allergy intolerance</span><span class="sxs-lookup"><span data-stu-id="26796-110">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="26796-111">サポート</span><span class="sxs-lookup"><span data-stu-id="26796-111">Coverage</span></span>](#coverage)
- [<span data-ttu-id="26796-112">投薬注文</span><span class="sxs-lookup"><span data-stu-id="26796-112">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="26796-113">場所</span><span class="sxs-lookup"><span data-stu-id="26796-113">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="26796-114">患者リソースは唯一の必須リソースであり、アプリがまったく読み込まれません。</span><span class="sxs-lookup"><span data-stu-id="26796-114">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="26796-115">ただし、Microsoft Teams の患者アプリを使用して、最も優れたエンドユーザーエクスペリエンスを実現するために、以下に記載されている仕様ごとに、上記のすべてのリソースのサポートを実装することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="26796-115">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="26796-116">Microsoft Teams の患者アプリから複数のリソースに対するクエリは、FHIR サーバーの URL への要求のバンドル (バッチ) を投稿します。</span><span class="sxs-lookup"><span data-stu-id="26796-116">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="26796-117">サーバーは各要求を処理し、各要求によって一致したリソースのバンドルを返します。</span><span class="sxs-lookup"><span data-stu-id="26796-117">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="26796-118">詳細と例については[https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction)、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26796-118">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="26796-119">以下のすべての FHIR リソースは、直接リソース参照によってアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="26796-119">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="26796-120">準拠している必要な最小フィールドセット</span><span class="sxs-lookup"><span data-stu-id="26796-120">Conformance minimum required field set</span></span>

 <span data-ttu-id="26796-121">FHIR サーバーでは、その機能の事実上の概要を把握するために、準拠のステートメントを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="26796-121">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="26796-122">DSTU2 FHIR サーバーでは、次のパラメーターが想定されています。</span><span class="sxs-lookup"><span data-stu-id="26796-122">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

1. <span data-ttu-id="26796-123">後</span><span class="sxs-lookup"><span data-stu-id="26796-123">REST</span></span>
   1. <span data-ttu-id="26796-124">Mode</span><span class="sxs-lookup"><span data-stu-id="26796-124">Mode</span></span>
   2. <span data-ttu-id="26796-125">通信</span><span class="sxs-lookup"><span data-stu-id="26796-125">Interaction</span></span>
   3. <span data-ttu-id="26796-126">リソース: 種類</span><span class="sxs-lookup"><span data-stu-id="26796-126">Resource: Type</span></span>
   4. <span data-ttu-id="26796-127">セキュリティ: [OAuth uri 用の拡張子](http://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="26796-127">Security: [Extension for OAuth URIs](http://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="26796-128">FhirVersion (Microsoft のコードでは、複数のバージョンをサポートするために、どのバージョンをピボットする必要があるかを理解する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="26796-128">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="26796-129">この[https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html)フィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26796-129">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="26796-130">診療</span><span class="sxs-lookup"><span data-stu-id="26796-130">Patient</span></span>

<span data-ttu-id="26796-131">以下は、 [Argonaut の患者プロファイル](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)フィールドのサブセットである、最小の必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="26796-131">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

1. <span data-ttu-id="26796-132">家族</span><span class="sxs-lookup"><span data-stu-id="26796-132">Name.Family</span></span>
2. <span data-ttu-id="26796-133">名前。指定された</span><span class="sxs-lookup"><span data-stu-id="26796-133">Name.Given</span></span>
3. <span data-ttu-id="26796-134">女性</span><span class="sxs-lookup"><span data-stu-id="26796-134">Gender</span></span>
4. <span data-ttu-id="26796-135">地</span><span class="sxs-lookup"><span data-stu-id="26796-135">BirthDate</span></span>
5. <span data-ttu-id="26796-136">MRN (識別子)</span><span class="sxs-lookup"><span data-stu-id="26796-136">MRN (Identifier)</span></span>

<span data-ttu-id="26796-137">優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリも次のフィールドを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="26796-137">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="26796-138">名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="26796-138">Name.Use</span></span>
2. <span data-ttu-id="26796-139">名前プレフィックス</span><span class="sxs-lookup"><span data-stu-id="26796-139">Name.Prefix</span></span>
3. <span data-ttu-id="26796-140">CareProvider (患者リソースのこの参照には、次の例に示す表示フィールドを含める必要があります)。</span><span class="sxs-lookup"><span data-stu-id="26796-140">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

* * *

    <span data-ttu-id="26796-141">要求: <fhir-server>/Patient/<患者 id> を取得する</span><span class="sxs-lookup"><span data-stu-id="26796-141">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="26796-142">応答: {"resourceType": "患者"、"id": "<>"、"</span><span class="sxs-lookup"><span data-stu-id="26796-142">Response: { "resourceType": "Patient", "id": "<patient-id>", .</span></span>
      <span data-ttu-id="26796-143">.</span><span class="sxs-lookup"><span data-stu-id="26796-143"></span></span>
      <span data-ttu-id="26796-144">.</span><span class="sxs-lookup"><span data-stu-id="26796-144"></span></span>
      <span data-ttu-id="26796-145">"name": [{"use": "オフィシャル", "prefix": ["Mr"], "family": ["Chau"], "指定した部分": ["Hugh"]}], "識別子": [{"use": [{"]" と入力 ": {" コード ":"http://hl7.org/fhir/v2/0203"、" "": "", "" ":" "", "" ":" "," "値": "" "," "" "" ":" "", "" "1957-06-05 1234567"," careProvider ": [{" display ":" Jane Doe "}],}</span><span class="sxs-lookup"><span data-stu-id="26796-145">"name": [ { "use": "official", "prefix": [ "Mr" ], "family": [ "Chau" ], "given": [ "Hugh" ] } ], "identifier": [ { "use": "official", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR" } ] }, "value": "1234567" } ], "gender": "male", "birthDate": "1957-06-05", "careProvider": [{ "display": "Jane Doe" }], }</span></span>

* * *

<span data-ttu-id="26796-146">リソース検索では、/Patient/_search と次のパラメーターで POST メソッドを使います。</span><span class="sxs-lookup"><span data-stu-id="26796-146">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="26796-147">id</span><span class="sxs-lookup"><span data-stu-id="26796-147">id</span></span>
2. <span data-ttu-id="26796-148">ファミリ: contains = (ファミリ名に値が含まれているすべての患者を検索します。)</span><span class="sxs-lookup"><span data-stu-id="26796-148">family:contains=(searches for all patients whose family name contains the value.)</span></span>
3. <span data-ttu-id="26796-149">指定さ\<れた = substring></span><span class="sxs-lookup"><span data-stu-id="26796-149">given=\<substring></span></span>
4. <span data-ttu-id="26796-150">name =\<substring></span><span class="sxs-lookup"><span data-stu-id="26796-150">name=\<substring></span></span>
5. <span data-ttu-id="26796-151">生年月日 = (完全一致)</span><span class="sxs-lookup"><span data-stu-id="26796-151">birthdate=(exact match)</span></span>
6. <span data-ttu-id="26796-152">\_count (返される結果の最大数)</span><span class="sxs-lookup"><span data-stu-id="26796-152">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="26796-153">応答には、検索結果として返されるレコードの合計数が含まれ\_ている必要があります。カウントは、返されるレコードの数を制限するために PatientsApp によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="26796-153">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="26796-154">識別子 =\<mrn></span><span class="sxs-lookup"><span data-stu-id="26796-154">identifier=\<mrn></span></span>

<span data-ttu-id="26796-155">目標は、次のようにして患者の検索とフィルター処理を行うことができるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="26796-155">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="26796-156">ID: これは、FHIR のすべてのリソースが持つリソース ID です。</span><span class="sxs-lookup"><span data-stu-id="26796-156">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="26796-157">MRN: 診療員が知っている患者の実際の識別子です。</span><span class="sxs-lookup"><span data-stu-id="26796-157">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="26796-158">この MRN は、FHIR の識別子リソース内の識別子の種類に基づいていることを理解しています。</span><span class="sxs-lookup"><span data-stu-id="26796-158">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="26796-159">名前</span><span class="sxs-lookup"><span data-stu-id="26796-159">Name</span></span>
- <span data-ttu-id="26796-160">地</span><span class="sxs-lookup"><span data-stu-id="26796-160">Birthdate</span></span>

<span data-ttu-id="26796-161">この通話の次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26796-161">See the following example  of this call.</span></span>

* * *

    <span data-ttu-id="26796-162">要求 <: fhir-server>/Patient/_search 要求本文: 指定 = hugh&ファミリ = chau</span><span class="sxs-lookup"><span data-stu-id="26796-162">Request: POST <fhir-server>/Patient/_search Request Body: given=hugh&family=chau</span></span>
    
    <span data-ttu-id="26796-163">応答: {"resourceType": "バンドル"、"id": "<バンドル id>",。</span><span class="sxs-lookup"><span data-stu-id="26796-163">Response: { "resourceType": "Bundle", "id": "<bundle-id>", .</span></span>
      <span data-ttu-id="26796-164">.</span><span class="sxs-lookup"><span data-stu-id="26796-164"></span></span>
      <span data-ttu-id="26796-165">.</span><span class="sxs-lookup"><span data-stu-id="26796-165"></span></span>
      <span data-ttu-id="26796-166">"entry": [{"リソース": {"resourceType": "患者"、"id": "<>"、"name": [{"text": "Hugh Chau", "family": ["Chau"], "指定された": ["Hugh"]}, "性別": "男性", "生年月日": "1957-06-05": "検索": {""</span><span class="sxs-lookup"><span data-stu-id="26796-166">"entry": [ { "resource": { "resourceType": "Patient", "id": "<patient-id>", "name": [ { "text": "Hugh Chau", "family": [ "Chau" ], "given": [ "Hugh" ] } ], "gender": "male", "birthDate": "1957-06-05" }, "search": { "mode": "match" } } ] }</span></span>

* * *

<span data-ttu-id="26796-167">この[https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html)フィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26796-167">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="26796-168">観察</span><span class="sxs-lookup"><span data-stu-id="26796-168">Observation</span></span>

<span data-ttu-id="26796-169">以下は、必須の最小フィールドであり、Argonaut の重要な署名プロファイルのサブセットです。</span><span class="sxs-lookup"><span data-stu-id="26796-169">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 1. <span data-ttu-id="26796-170">発効 (日付と時刻)</span><span class="sxs-lookup"><span data-stu-id="26796-170">Effective (date time or period)</span></span>
 2. <span data-ttu-id="26796-171">コードの記述</span><span class="sxs-lookup"><span data-stu-id="26796-171">Code.Coding.Code</span></span>
 3. <span data-ttu-id="26796-172">Valu不定の値</span><span class="sxs-lookup"><span data-stu-id="26796-172">ValueQuantity.Value</span></span>

<span data-ttu-id="26796-173">優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリも次のフィールドを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="26796-173">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 1. <span data-ttu-id="26796-174">コード。ディスプレイ</span><span class="sxs-lookup"><span data-stu-id="26796-174">Code.Coding.Display</span></span>
 2. <span data-ttu-id="26796-175">Valuの単位</span><span class="sxs-lookup"><span data-stu-id="26796-175">ValueQuantity.Unit</span></span>

<span data-ttu-id="26796-176">コンポーネントの所見を使う場合は、各コンポーネントの観測に同じロジックが適用されます。</span><span class="sxs-lookup"><span data-stu-id="26796-176">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="26796-177">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="26796-177">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="26796-178">患者 =\<患者 id\></span><span class="sxs-lookup"><span data-stu-id="26796-178">patient=\<patient id\></span></span>
2. <span data-ttu-id="26796-179">sort: desc =\<フィールドの例</span><span class="sxs-lookup"><span data-stu-id="26796-179">sort:desc=\<field ex.</span></span> <span data-ttu-id="26796-180">期日\></span><span class="sxs-lookup"><span data-stu-id="26796-180">date\></span></span>

<span data-ttu-id="26796-181">目標は、患者の最新のバイタル・サインを取得できるようにすることです (観測された VitalSigns)。</span><span class="sxs-lookup"><span data-stu-id="26796-181">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

* * *

    <span data-ttu-id="26796-182">要求: <fhir-server>/監視? 患者 =<患者の>&_sort:d esc = date&category = バイタルサイン</span><span class="sxs-lookup"><span data-stu-id="26796-182">Request: GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs</span></span>
    
    <span data-ttu-id="26796-183">応答: {"resourceType": "バンドル"、"id": "<バンドル id>", "「"」と入力して、"、" 集計 "と入力します: [{" リソース ": {" リソース ": {" resourceType ":" <"、" id ":" リソース id> "," カテゴリ ": {" コード ":" "{code": "\" code ":": [{" システム ":"http://loinc.org"," コード ":" 39156-5 "," 表示 ":" bmi "}]," effectiveDateTime ":" 2009-12-01 "," valuvalu":" ":" 値 ": 34.4," unit ":"? "http://unitsofmeasure.org" "," "システム": "", "code": "?"</span><span class="sxs-lookup"><span data-stu-id="26796-183">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": { "coding": [ { code": "vital-signs" } ], }, "code": { "coding": [ { "system": "http://loinc.org", "code": "39156-5", "display": "bmi" } ], }, "effectiveDateTime": "2009-12-01", "valueQuantity": { "value": 34.4, "unit": "kg/m2", "system": "http://unitsofmeasure.org", "code": "kg/m2" } }, }, .</span></span>
        <span data-ttu-id="26796-184">.</span><span class="sxs-lookup"><span data-stu-id="26796-184"></span></span>
        <span data-ttu-id="26796-185">.</span><span class="sxs-lookup"><span data-stu-id="26796-185"></span></span>
      <span data-ttu-id="26796-186">] }</span><span class="sxs-lookup"><span data-stu-id="26796-186"></span></span>

* * *

<span data-ttu-id="26796-187">この[https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html)フィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26796-187">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="26796-188">状態</span><span class="sxs-lookup"><span data-stu-id="26796-188">Condition</span></span>

<span data-ttu-id="26796-189">以下は、 [Argonaut 条件プロファイル](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)の一部である最小必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="26796-189">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="26796-190">コード。 [0]。表示</span><span class="sxs-lookup"><span data-stu-id="26796-190">Code.Coding[0].Display</span></span>

<span data-ttu-id="26796-191">優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリでは、次のフィールドも読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="26796-191">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="26796-192">記録された日付</span><span class="sxs-lookup"><span data-stu-id="26796-192">Date Recorded</span></span>
2. <span data-ttu-id="26796-193">程度</span><span class="sxs-lookup"><span data-stu-id="26796-193">Severity</span></span>

<span data-ttu-id="26796-194">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="26796-194">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="26796-195">患者 =\<患者 id の></span><span class="sxs-lookup"><span data-stu-id="26796-195">patient=\<patient id></span></span>
2. <span data-ttu-id="26796-196">_ count =\<最大結果></span><span class="sxs-lookup"><span data-stu-id="26796-196">_count=\<max results></span></span>

<span data-ttu-id="26796-197">この通話の次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26796-197">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="26796-198">要求: fhir-server>/条件? 患者 =<患者 id>&_count = 10 を取得 <</span><span class="sxs-lookup"><span data-stu-id="26796-198">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="26796-199">応答: {"resourceType": "バンドル", "id": "<バンドル id>"、"種類": "searchset"、"集計": ""、"" のように入力します: [{"リソース": {"resourceType": "id": "<リソース id>"、"コード": {"code": [{              "システム": "http://snomed.info/sct", "コード": "386033004", "表示": "", "Neuropathy": "syst", "dateRecorded": "2018-09-17", "深刻度": {"": [{]em ":http://snomed.info/sct" "," コード ":" 24484000 "," 表示 ":" 重大 "}"}},}]}</span><span class="sxs-lookup"><span data-stu-id="26796-199">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Condition",         "id": "<resource-id>",         "code": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "386033004",               "display": "Neuropathy (nerve damage)"             }           ]         },         "dateRecorded": "2018-09-17",         "severity": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "24484000",               "display": "Severe"             }           ]         }       },     }   ] }</span></span>

* * *

<span data-ttu-id="26796-200">この[https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html)フィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26796-200">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="26796-201">状況</span><span class="sxs-lookup"><span data-stu-id="26796-201">Encounter</span></span>

<span data-ttu-id="26796-202">"US Core" というプロファイルのサブセットである、最低限必要なフィールドは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="26796-202">These are the minimum required fields, which are a subset of the US Core Encounter profile “must have” fields:</span></span>

1. <span data-ttu-id="26796-203">状態</span><span class="sxs-lookup"><span data-stu-id="26796-203">Status</span></span>
2. <span data-ttu-id="26796-204">[0] と入力します。コーディング [0]。表示</span><span class="sxs-lookup"><span data-stu-id="26796-204">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="26796-205">さらに、US Core の次のフィールドは、プロファイルの "サポートが必要" フィールドを示しています。</span><span class="sxs-lookup"><span data-stu-id="26796-205">In addition, the following fields from US Core Encounter profile’s “must support” fields</span></span>

1. <span data-ttu-id="26796-206">期間. 開始日</span><span class="sxs-lookup"><span data-stu-id="26796-206">Period.Start</span></span>
2. <span data-ttu-id="26796-207">場所 [0]場所。表示</span><span class="sxs-lookup"><span data-stu-id="26796-207">Location[0].Location.Display</span></span>

<span data-ttu-id="26796-208">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="26796-208">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="26796-209">患者 =\<患者 id の></span><span class="sxs-lookup"><span data-stu-id="26796-209">patient=\<patient id></span></span>
2. <span data-ttu-id="26796-210">(並べ替え: desc =\<フィールドの例)</span><span class="sxs-lookup"><span data-stu-id="26796-210">_sort:desc=\<field ex.</span></span> <span data-ttu-id="26796-211">日付></span><span class="sxs-lookup"><span data-stu-id="26796-211">date></span></span>
3. <span data-ttu-id="26796-212">_ count =\<最大結果></span><span class="sxs-lookup"><span data-stu-id="26796-212">_count=\<max results></span></span>

<span data-ttu-id="26796-213">目標は、患者の最後の既知の場所を取得できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="26796-213">The goal is to be able to retrieve the patient’s last known location.</span></span> <span data-ttu-id="26796-214">各検出は、位置情報リソースを参照します。</span><span class="sxs-lookup"><span data-stu-id="26796-214">Each encounter references a location resource.</span></span> <span data-ttu-id="26796-215">参照には、場所の表示フィールドも含まれます。</span><span class="sxs-lookup"><span data-stu-id="26796-215">The reference shall also include the location’s display field.</span></span> <span data-ttu-id="26796-216">この通話の次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26796-216">See the following example of this call.</span></span>
* * *

    <span data-ttu-id="26796-217">要求: fhir-server>/<を取得します。患者 =<患者-id>&_sort:d esc = date&_count = 1</span><span class="sxs-lookup"><span data-stu-id="26796-217">Request: GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1</span></span>
    
    <span data-ttu-id="26796-218">応答: {"resourceType": "バンドル", "種類": "searchset", "集計": "{" リソース ": {" resourceType ":" <リソース id> "、" id ":" "を使用": "" という値: [{"use": "" # ":" "値"<id>: ": "到着"、"種類": [{"display": "予定"}]、[}]、"患者": {"参照": "患者" と "<" のような "!": ">": "!": "!": {"start": "09/17/2018 1:00:00 PM"}, "場所": [{             "場所": {"display": "クリニック-ENT"},} "}}]}</span><span class="sxs-lookup"><span data-stu-id="26796-218">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Encounter",         "id": "<resource-id>",         "identifier": [{ "use": "official", "value": "<id>" }],         "status": "arrived",         "type": [           {             "coding": [{ "display": "Appointment" }],           }         ],         "patient": { "reference": "Patient/<patient-id>" },         "period": { "start": "09/17/2018 1:00:00 PM" },         "location": [           {             "location": { "display": "Clinic - ENT" },           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="26796-219">この[https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm)フィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26796-219">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="26796-220">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="26796-220">AllergyIntolerance</span></span>

<span data-ttu-id="26796-221">以下は、Argonaut AllergyIntolerance profile のサブセットである最小必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="26796-221">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

1. <span data-ttu-id="26796-222">コード。テキスト</span><span class="sxs-lookup"><span data-stu-id="26796-222">Code.Text</span></span>
2. <span data-ttu-id="26796-223">コード。 [0]。表示</span><span class="sxs-lookup"><span data-stu-id="26796-223">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="26796-224">状態</span><span class="sxs-lookup"><span data-stu-id="26796-224">Status</span></span>

<span data-ttu-id="26796-225">優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリも次のフィールドを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="26796-225">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="26796-226">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="26796-226">RecordedDate</span></span>
2. <span data-ttu-id="26796-227">注テキスト</span><span class="sxs-lookup"><span data-stu-id="26796-227">Note.Text</span></span>
3. <span data-ttu-id="26796-228">反力 [..]物質。テキスト</span><span class="sxs-lookup"><span data-stu-id="26796-228">Reaction[..].Substance.Text</span></span>
4. <span data-ttu-id="26796-229">反力 [..]影響 [..]テキスト</span><span class="sxs-lookup"><span data-stu-id="26796-229">Reaction[..].Manifestation[..].Text</span></span>
5. <span data-ttu-id="26796-230">テキストの Div</span><span class="sxs-lookup"><span data-stu-id="26796-230">Text.Div</span></span>

<span data-ttu-id="26796-231">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="26796-231">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="26796-232">患者 = \<患者 id の></span><span class="sxs-lookup"><span data-stu-id="26796-232">Patient =  \<patient id></span></span>

<span data-ttu-id="26796-233">この通話の次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26796-233">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="26796-234">要求: <fhir-server>/AllergyIntolerance? 患者 =<患者 id を取得></span><span class="sxs-lookup"><span data-stu-id="26796-234">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="26796-235">応答: {"resourceType": "バンドル", "id": "<バンドル id>"、"種類"、"searchset"、"total": 1, "recordedDate": "2018"、"id": "<リソース id>"、"": ""、""、"-09": "-090Z "," 物質 ": {" text ":" Cashew ナット "}," 状態 ":" 確認 "," 反応 ": [{" 物質 ": {" 物質 ":" "Injectable": "cashew ナット allergenic extract Product"}, "manifestation ": [{" text ":" Anaphylactic 反 "}]}"}} "}</span><span class="sxs-lookup"><span data-stu-id="26796-235">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "recordedDate": "2018-09-17T07:00:00.000Z",         "substance": {           "text": "Cashew nuts"         },         "status": "confirmed",         "reaction": [           {             "substance": {               "text": "cashew nut allergenic extract Injectable Product"             },             "manifestation": [               {                 "text": "Anaphylactic reaction"               }             ]           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="26796-236">この[https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html)フィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26796-236">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="26796-237">投薬注文</span><span class="sxs-lookup"><span data-stu-id="26796-237">Medication Order</span></span>

<span data-ttu-id="26796-238">以下は、Argonaut MedicationOrder profile のサブセットである最小必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="26796-238">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

1. <span data-ttu-id="26796-239">記録された日付</span><span class="sxs-lookup"><span data-stu-id="26796-239">DateWritten</span></span>
2. <span data-ttu-id="26796-240">Prescriber</span><span class="sxs-lookup"><span data-stu-id="26796-240">Prescriber.Display</span></span>
3. <span data-ttu-id="26796-241">投薬 (参照の場合)</span><span class="sxs-lookup"><span data-stu-id="26796-241">Medication.Display (if reference)</span></span>
4. <span data-ttu-id="26796-242">投薬 (概念の場合)</span><span class="sxs-lookup"><span data-stu-id="26796-242">Medication.Text (if concept)</span></span>

<span data-ttu-id="26796-243">優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリでは、次のフィールドも読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="26796-243">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="26796-244">DateEnded</span><span class="sxs-lookup"><span data-stu-id="26796-244">DateEnded</span></span>
2. <span data-ttu-id="26796-245">DosageInstruction。</span><span class="sxs-lookup"><span data-stu-id="26796-245">DosageInstruction.Text</span></span>
3. <span data-ttu-id="26796-246">テキストの Div</span><span class="sxs-lookup"><span data-stu-id="26796-246">Text.Div</span></span>

<span data-ttu-id="26796-247">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="26796-247">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="26796-248">患者 =\<患者 id の></span><span class="sxs-lookup"><span data-stu-id="26796-248">patient=\<patient id></span></span>
2. <span data-ttu-id="26796-249">_ count =\<最大結果></span><span class="sxs-lookup"><span data-stu-id="26796-249">_count=\<max results></span></span>

<span data-ttu-id="26796-250">この通話の次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26796-250">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="26796-251">要求: <fhir-server>/MedicationOrder? 患者 =<患者 id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="26796-251">Request: GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="26796-252">応答: {"resourceType": "バンドル", "id": "<バンドル id>"、"種類"、"searchset"、"total": 1, "medi": "{" リソース ": {" resourceType ":" "、" id ":" <リソース id> "、" dateWritten ":" 2018-09-17 "," MedicationOrder "cationCodeableConcept ": {" text ":" Lisinopril 20 MG 口頭タブレット "}," prescriber ": {" display ":" Jane Doe "}," dosageInstruction ": [{" テキスト ":" "{" テキスト "</span><span class="sxs-lookup"><span data-stu-id="26796-252">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "MedicationOrder",         "id": "<resource-id>",         "dateWritten": "2018-09-17",         "medicationCodeableConcept": {           "text": "Lisinopril 20 MG Oral Tablet"         },         "prescriber": {           "display": "Jane Doe"         },         "dosageInstruction": [           {             "text": "1 daily"           }         ]       }     }   ] }</span></span>

* * *  

<span data-ttu-id="26796-253">この[https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html)フィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26796-253">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="26796-254">サポート</span><span class="sxs-lookup"><span data-stu-id="26796-254">Coverage</span></span>

<span data-ttu-id="26796-255">以下は、US Core または Argonaut のプロファイルでカバーされていない最低限の必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="26796-255">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="26796-256">給料または</span><span class="sxs-lookup"><span data-stu-id="26796-256">Payor</span></span>

<span data-ttu-id="26796-257">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="26796-257">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="26796-258">患者 =\<患者 id の></span><span class="sxs-lookup"><span data-stu-id="26796-258">patient=\<patient id></span></span>

<span data-ttu-id="26796-259">この通話の次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26796-259">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="26796-260">要求: <fhir-server>/利用可能かどうかを確認してください。患者 =<患者 id></span><span class="sxs-lookup"><span data-stu-id="26796-260">Request: GET <fhir-server>/Coverage?patient=<patient-id></span></span>
    
    <span data-ttu-id="26796-261">応答: {"resourceType": "次へ" と入力します: "searchset", "集計": "検索": {"resourceType": [{"リソース": {"resourceType": "<"、"id": "リソース id>"、"プラン": "第1の保険はありません"、"サブスクリプション": "患者/<患者の> "}}}]}</span><span class="sxs-lookup"><span data-stu-id="26796-261">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Coverage",         "id": "<resource-id>",         "plan": "No Primary Insurance",         "subscriber": { "reference": "Patient/<patient-id>" }       }     }   ] }</span></span>

* * *

<span data-ttu-id="26796-262">この[https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html)フィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26796-262">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="26796-263">場所</span><span class="sxs-lookup"><span data-stu-id="26796-263">Location</span></span>

<span data-ttu-id="26796-264">このリソース[は、リソースの参照](#encounter)としてのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="26796-264">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="26796-265">この[https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html)フィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26796-265">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
