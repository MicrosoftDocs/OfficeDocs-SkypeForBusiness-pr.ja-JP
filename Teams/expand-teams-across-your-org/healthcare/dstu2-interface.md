---
title: 患者のアプリと EHR の統合 DSTU2 インターフェイス
author: jambirk
ms.author: jambirk
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
description: Microsoft Teams の患者向けアプリ EHR の統合
ms.openlocfilehash: d7acea1002d80a397469d242cfbbb1adfba07a24
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827805"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="5acb6-103">DSTU2 インターフェイスの仕様</span><span class="sxs-lookup"><span data-stu-id="5acb6-103">DSTU2 interface specification</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="5acb6-104">Microsoft Teams の患者と連携するように FHIR サーバーを設定または再構成するには、アプリがアクセスする必要があるデータを把握する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5acb6-104">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="5acb6-105">FHIR サーバーでは、次のリソースについて、バンドルを使った POST 要求をサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5acb6-105">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="5acb6-106">診療</span><span class="sxs-lookup"><span data-stu-id="5acb6-106">Patient</span></span>](#patient)
- [<span data-ttu-id="5acb6-107">観察</span><span class="sxs-lookup"><span data-stu-id="5acb6-107">Observation</span></span>](#observation)
- [<span data-ttu-id="5acb6-108">状態</span><span class="sxs-lookup"><span data-stu-id="5acb6-108">Condition</span></span>](#condition)
- [<span data-ttu-id="5acb6-109">状況</span><span class="sxs-lookup"><span data-stu-id="5acb6-109">Encounter</span></span>](#encounter)
- [<span data-ttu-id="5acb6-110">Allergy intolerance</span><span class="sxs-lookup"><span data-stu-id="5acb6-110">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="5acb6-111">サポート</span><span class="sxs-lookup"><span data-stu-id="5acb6-111">Coverage</span></span>](#coverage)
- [<span data-ttu-id="5acb6-112">投薬注文</span><span class="sxs-lookup"><span data-stu-id="5acb6-112">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="5acb6-113">場所</span><span class="sxs-lookup"><span data-stu-id="5acb6-113">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="5acb6-114">患者リソースは唯一の必須リソースであり、アプリがまったく読み込まれません。</span><span class="sxs-lookup"><span data-stu-id="5acb6-114">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="5acb6-115">ただし、Microsoft Teams の患者アプリを使用して、最も優れたエンドユーザーエクスペリエンスを実現するために、以下に記載されている仕様ごとに、上記のすべてのリソースのサポートを実装することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5acb6-115">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="5acb6-116">Microsoft Teams の患者アプリから複数のリソースに対するクエリは、FHIR サーバーの URL への要求のバンドル (バッチ) を投稿します。</span><span class="sxs-lookup"><span data-stu-id="5acb6-116">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="5acb6-117">サーバーは各要求を処理し、各要求によって一致したリソースのバンドルを返します。</span><span class="sxs-lookup"><span data-stu-id="5acb6-117">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="5acb6-118">詳細と例については[https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction)、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5acb6-118">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="5acb6-119">以下のすべての FHIR リソースは、直接リソース参照によってアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5acb6-119">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="5acb6-120">準拠している必要な最小フィールドセット</span><span class="sxs-lookup"><span data-stu-id="5acb6-120">Conformance minimum required field set</span></span>

 <span data-ttu-id="5acb6-121">FHIR サーバーでは、その機能の事実上の概要を把握するために、準拠のステートメントを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5acb6-121">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="5acb6-122">DSTU2 FHIR サーバーでは、次のパラメーターが想定されています。</span><span class="sxs-lookup"><span data-stu-id="5acb6-122">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

1. <span data-ttu-id="5acb6-123">後</span><span class="sxs-lookup"><span data-stu-id="5acb6-123">REST</span></span>
   1. <span data-ttu-id="5acb6-124">モード</span><span class="sxs-lookup"><span data-stu-id="5acb6-124">Mode</span></span>
   2. <span data-ttu-id="5acb6-125">通信</span><span class="sxs-lookup"><span data-stu-id="5acb6-125">Interaction</span></span>
   3. <span data-ttu-id="5acb6-126">リソース: 種類</span><span class="sxs-lookup"><span data-stu-id="5acb6-126">Resource: Type</span></span>
   4. <span data-ttu-id="5acb6-127">セキュリティ: [OAuth uri 用の拡張子](http://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="5acb6-127">Security: [Extension for OAuth URIs](http://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="5acb6-128">FhirVersion (Microsoft のコードでは、複数のバージョンをサポートするために、どのバージョンをピボットする必要があるかを理解する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="5acb6-128">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="5acb6-129">この[https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html)フィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5acb6-129">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="5acb6-130">診療</span><span class="sxs-lookup"><span data-stu-id="5acb6-130">Patient</span></span>

<span data-ttu-id="5acb6-131">以下は、 [Argonaut の患者プロファイル](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)フィールドのサブセットである、最小の必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="5acb6-131">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

1. <span data-ttu-id="5acb6-132">家族</span><span class="sxs-lookup"><span data-stu-id="5acb6-132">Name.Family</span></span>
2. <span data-ttu-id="5acb6-133">名前。指定された</span><span class="sxs-lookup"><span data-stu-id="5acb6-133">Name.Given</span></span>
3. <span data-ttu-id="5acb6-134">女性</span><span class="sxs-lookup"><span data-stu-id="5acb6-134">Gender</span></span>
4. <span data-ttu-id="5acb6-135">地</span><span class="sxs-lookup"><span data-stu-id="5acb6-135">BirthDate</span></span>
5. <span data-ttu-id="5acb6-136">MRN (識別子)</span><span class="sxs-lookup"><span data-stu-id="5acb6-136">MRN (Identifier)</span></span>

<span data-ttu-id="5acb6-137">優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリも次のフィールドを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="5acb6-137">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="5acb6-138">名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5acb6-138">Name.Use</span></span>
2. <span data-ttu-id="5acb6-139">名前プレフィックス</span><span class="sxs-lookup"><span data-stu-id="5acb6-139">Name.Prefix</span></span>
3. <span data-ttu-id="5acb6-140">CareProvider (患者リソースのこの参照には、次の例に示す表示フィールドを含める必要があります)。</span><span class="sxs-lookup"><span data-stu-id="5acb6-140">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

* * *

    <span data-ttu-id="5acb6-141">要求: <fhir-server>/Patient/<患者 id> を取得する</span><span class="sxs-lookup"><span data-stu-id="5acb6-141">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="5acb6-142">応答: {"resourceType": "患者"、"id": "<>"、"</span><span class="sxs-lookup"><span data-stu-id="5acb6-142">Response: { "resourceType": "Patient", "id": "<patient-id>", .</span></span>
      <span data-ttu-id="5acb6-143">.</span><span class="sxs-lookup"><span data-stu-id="5acb6-143">.</span></span>
      <span data-ttu-id="5acb6-144">.</span><span class="sxs-lookup"><span data-stu-id="5acb6-144">.</span></span>
      <span data-ttu-id="5acb6-145">"name": [{"use": "オフィシャル", "prefix": ["Mr"], "family": ["Chau"], "指定された": ["Hugh"]}], "識別子": [{"use": "", "と入力します。 {" コード ": [{"http://hl7.org/fhir/v2/0203system ":" "、" code ":" "、" code ":" Mr "}]}、" 性別 ":" careProvider ":" 1957-06-05 "、" ": [{" display ":" 鈴木 Doe "}],} 1234567</span><span class="sxs-lookup"><span data-stu-id="5acb6-145">"name": [ { "use": "official", "prefix": [ "Mr" ], "family": [ "Chau" ], "given": [ "Hugh" ] } ], "identifier": [ { "use": "official", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR" } ] }, "value": "1234567" } ], "gender": "male", "birthDate": "1957-06-05", "careProvider": [{ "display": "Jane Doe" }], }</span></span>

* * *

<span data-ttu-id="5acb6-146">リソース検索では、/Patient/_search と次のパラメーターで POST メソッドを使います。</span><span class="sxs-lookup"><span data-stu-id="5acb6-146">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="5acb6-147">id</span><span class="sxs-lookup"><span data-stu-id="5acb6-147">id</span></span>
2. <span data-ttu-id="5acb6-148">ファミリ: contains = (ファミリ名に値が含まれているすべての患者を検索します。)</span><span class="sxs-lookup"><span data-stu-id="5acb6-148">family:contains=(searches for all patients whose family name contains the value.)</span></span>
3. <span data-ttu-id="5acb6-149">指定さ\<れた = substring></span><span class="sxs-lookup"><span data-stu-id="5acb6-149">given=\<substring></span></span>
4. <span data-ttu-id="5acb6-150">name =\<substring></span><span class="sxs-lookup"><span data-stu-id="5acb6-150">name=\<substring></span></span>
5. <span data-ttu-id="5acb6-151">生年月日 = (完全一致)</span><span class="sxs-lookup"><span data-stu-id="5acb6-151">birthdate=(exact match)</span></span>
6. <span data-ttu-id="5acb6-152">\_count (返される結果の最大数)</span><span class="sxs-lookup"><span data-stu-id="5acb6-152">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="5acb6-153">応答には、検索結果として返されるレコードの合計数が含まれ\_ている必要があります。カウントは、返されるレコードの数を制限するために PatientsApp によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="5acb6-153">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="5acb6-154">識別子 =\<mrn></span><span class="sxs-lookup"><span data-stu-id="5acb6-154">identifier=\<mrn></span></span>

<span data-ttu-id="5acb6-155">目標は、次のようにして患者の検索とフィルター処理を行うことができるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="5acb6-155">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="5acb6-156">ID: これは、FHIR のすべてのリソースが持つリソース ID です。</span><span class="sxs-lookup"><span data-stu-id="5acb6-156">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="5acb6-157">MRN: 診療員が知っている患者の実際の識別子です。</span><span class="sxs-lookup"><span data-stu-id="5acb6-157">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="5acb6-158">この MRN は、FHIR の識別子リソース内の識別子の種類に基づいていることを理解しています。</span><span class="sxs-lookup"><span data-stu-id="5acb6-158">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="5acb6-159">名前</span><span class="sxs-lookup"><span data-stu-id="5acb6-159">Name</span></span>
- <span data-ttu-id="5acb6-160">地</span><span class="sxs-lookup"><span data-stu-id="5acb6-160">Birthdate</span></span>

<span data-ttu-id="5acb6-161">この通話の次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5acb6-161">See the following example  of this call.</span></span>

* * *

    <span data-ttu-id="5acb6-162">要求 <: fhir-server>/Patient/_search 要求本文: 指定 = hugh&ファミリ = chau</span><span class="sxs-lookup"><span data-stu-id="5acb6-162">Request: POST <fhir-server>/Patient/_search Request Body: given=hugh&family=chau</span></span>
    
    <span data-ttu-id="5acb6-163">応答: {"resourceType": "バンドル"、"id": "<バンドル id>",。</span><span class="sxs-lookup"><span data-stu-id="5acb6-163">Response: { "resourceType": "Bundle", "id": "<bundle-id>", .</span></span>
      <span data-ttu-id="5acb6-164">.</span><span class="sxs-lookup"><span data-stu-id="5acb6-164">.</span></span>
      <span data-ttu-id="5acb6-165">.</span><span class="sxs-lookup"><span data-stu-id="5acb6-165">.</span></span>
      <span data-ttu-id="5acb6-166">"entry": [{"リソース": {"resourceType": "患者"、"id": "<>"、"name": [{"text": "Hugh Chau", "family": ["Chau"], "指定された": ["Hugh"]}, "性別": "男性", "生年月日": "1957-06-05": "検索": {""</span><span class="sxs-lookup"><span data-stu-id="5acb6-166">"entry": [ { "resource": { "resourceType": "Patient", "id": "<patient-id>", "name": [ { "text": "Hugh Chau", "family": [ "Chau" ], "given": [ "Hugh" ] } ], "gender": "male", "birthDate": "1957-06-05" }, "search": { "mode": "match" } } ] }</span></span>

* * *

<span data-ttu-id="5acb6-167">この[https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html)フィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5acb6-167">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="5acb6-168">観察</span><span class="sxs-lookup"><span data-stu-id="5acb6-168">Observation</span></span>

<span data-ttu-id="5acb6-169">以下は、必須の最小フィールドであり、Argonaut の重要な署名プロファイルのサブセットです。</span><span class="sxs-lookup"><span data-stu-id="5acb6-169">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 1. <span data-ttu-id="5acb6-170">発効 (日付と時刻)</span><span class="sxs-lookup"><span data-stu-id="5acb6-170">Effective (date time or period)</span></span>
 2. <span data-ttu-id="5acb6-171">コードの記述</span><span class="sxs-lookup"><span data-stu-id="5acb6-171">Code.Coding.Code</span></span>
 3. <span data-ttu-id="5acb6-172">Valu不定の値</span><span class="sxs-lookup"><span data-stu-id="5acb6-172">ValueQuantity.Value</span></span>

<span data-ttu-id="5acb6-173">優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリも次のフィールドを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="5acb6-173">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 1. <span data-ttu-id="5acb6-174">コード。ディスプレイ</span><span class="sxs-lookup"><span data-stu-id="5acb6-174">Code.Coding.Display</span></span>
 2. <span data-ttu-id="5acb6-175">Valuの単位</span><span class="sxs-lookup"><span data-stu-id="5acb6-175">ValueQuantity.Unit</span></span>

<span data-ttu-id="5acb6-176">コンポーネントの所見を使う場合は、各コンポーネントの観測に同じロジックが適用されます。</span><span class="sxs-lookup"><span data-stu-id="5acb6-176">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="5acb6-177">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="5acb6-177">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="5acb6-178">患者 =\<患者 id\></span><span class="sxs-lookup"><span data-stu-id="5acb6-178">patient=\<patient id\></span></span>
2. <span data-ttu-id="5acb6-179">sort: desc =\<フィールドの例</span><span class="sxs-lookup"><span data-stu-id="5acb6-179">sort:desc=\<field ex.</span></span> <span data-ttu-id="5acb6-180">期日\></span><span class="sxs-lookup"><span data-stu-id="5acb6-180">date\></span></span>

<span data-ttu-id="5acb6-181">目標は、患者の最新のバイタル・サインを取得できるようにすることです (観測された VitalSigns)。</span><span class="sxs-lookup"><span data-stu-id="5acb6-181">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

* * *

    <span data-ttu-id="5acb6-182">要求: <fhir-server>/監視? 患者 =<患者の>&_sort:d esc = date&category = バイタルサイン</span><span class="sxs-lookup"><span data-stu-id="5acb6-182">Request: GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs</span></span>
    
    <span data-ttu-id="5acb6-183">応答: {"resourceType": "バンドル"、"id": "<バンドル id>", "「"」と入力して、「検索」、「集計」、「20」、「入力」の順に入力します。 [{"リソース": {"resourceType": "<" と "id": "リソース id>", "カテゴリ": {"コード": {"コーディング": [{"system": "http://loinc.org", "code": "39156-5", "display": "", "表示": "bmi"} ":" effectiveDateTime ":" 2009-12-01 "," valu"指定した値": {"値": 34.4, "unit": "kg/m2", "システム": "http://unitsofmeasure.org", "code": "kg/m2"}},},}</span><span class="sxs-lookup"><span data-stu-id="5acb6-183">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": { "coding": [ { code": "vital-signs" } ], }, "code": { "coding": [ { "system": "http://loinc.org", "code": "39156-5", "display": "bmi" } ], }, "effectiveDateTime": "2009-12-01", "valueQuantity": { "value": 34.4, "unit": "kg/m2", "system": "http://unitsofmeasure.org", "code": "kg/m2" } }, }, .</span></span>
        <span data-ttu-id="5acb6-184">.</span><span class="sxs-lookup"><span data-stu-id="5acb6-184">.</span></span>
        <span data-ttu-id="5acb6-185">.</span><span class="sxs-lookup"><span data-stu-id="5acb6-185">.</span></span>
      <span data-ttu-id="5acb6-186">] }</span><span class="sxs-lookup"><span data-stu-id="5acb6-186">] }</span></span>

* * *

<span data-ttu-id="5acb6-187">この[https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html)フィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5acb6-187">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="5acb6-188">状態</span><span class="sxs-lookup"><span data-stu-id="5acb6-188">Condition</span></span>

<span data-ttu-id="5acb6-189">以下は、 [Argonaut 条件プロファイル](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)の一部である最小必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="5acb6-189">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="5acb6-190">コード。 [0]。表示</span><span class="sxs-lookup"><span data-stu-id="5acb6-190">Code.Coding[0].Display</span></span>

<span data-ttu-id="5acb6-191">優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリでは、次のフィールドも読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="5acb6-191">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="5acb6-192">記録された日付</span><span class="sxs-lookup"><span data-stu-id="5acb6-192">Date Recorded</span></span>
2. <span data-ttu-id="5acb6-193">程度</span><span class="sxs-lookup"><span data-stu-id="5acb6-193">Severity</span></span>

<span data-ttu-id="5acb6-194">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="5acb6-194">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="5acb6-195">患者 =\<患者 id の></span><span class="sxs-lookup"><span data-stu-id="5acb6-195">patient=\<patient id></span></span>
2. <span data-ttu-id="5acb6-196">_count =\<最大結果></span><span class="sxs-lookup"><span data-stu-id="5acb6-196">_count=\<max results></span></span>

<span data-ttu-id="5acb6-197">この通話の次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5acb6-197">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="5acb6-198">要求: fhir-server>/条件? 患者 =<患者 id>&_count = 10 を取得 <</span><span class="sxs-lookup"><span data-stu-id="5acb6-198">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="5acb6-199">応答: {"resourceType": "バンドル"、"id": "<バンドル id>"、"種類": "searchset"、"合計": 1, "入力": [{"リソース": "{" リソース ": {" resourceType ":" 条件 "" id ":" <リソース id> "," code ": {" syst ":" {"http://snomed.info/sct": "386033004"、"コード": "", "表示": "", "Neuropathy": "2018-09-17"、"dateRecorded": ""、"深刻度": {"em ":http://snomed.info/sct" "," コード ":" 24484000 "," 表示 ":" 重大 "}"}},}]}</span><span class="sxs-lookup"><span data-stu-id="5acb6-199">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Condition",         "id": "<resource-id>",         "code": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "386033004",               "display": "Neuropathy (nerve damage)"             }           ]         },         "dateRecorded": "2018-09-17",         "severity": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "24484000",               "display": "Severe"             }           ]         }       },     }   ] }</span></span>

* * *

<span data-ttu-id="5acb6-200">この[https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html)フィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5acb6-200">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="5acb6-201">状況</span><span class="sxs-lookup"><span data-stu-id="5acb6-201">Encounter</span></span>

<span data-ttu-id="5acb6-202">"US Core" というプロファイルのサブセットである、最低限必要なフィールドは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5acb6-202">These are the minimum required fields, which are a subset of the US Core Encounter profile “must have” fields:</span></span>

1. <span data-ttu-id="5acb6-203">状態</span><span class="sxs-lookup"><span data-stu-id="5acb6-203">Status</span></span>
2. <span data-ttu-id="5acb6-204">[0] と入力します。コーディング [0]。表示</span><span class="sxs-lookup"><span data-stu-id="5acb6-204">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="5acb6-205">さらに、US Core の次のフィールドは、プロファイルの "サポートが必要" フィールドを示しています。</span><span class="sxs-lookup"><span data-stu-id="5acb6-205">In addition, the following fields from US Core Encounter profile’s “must support” fields</span></span>

1. <span data-ttu-id="5acb6-206">期間. 開始日</span><span class="sxs-lookup"><span data-stu-id="5acb6-206">Period.Start</span></span>
2. <span data-ttu-id="5acb6-207">場所 [0]場所。表示</span><span class="sxs-lookup"><span data-stu-id="5acb6-207">Location[0].Location.Display</span></span>

<span data-ttu-id="5acb6-208">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="5acb6-208">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="5acb6-209">患者 =\<患者 id の></span><span class="sxs-lookup"><span data-stu-id="5acb6-209">patient=\<patient id></span></span>
2. <span data-ttu-id="5acb6-210">_sort: desc =\<フィールド ex</span><span class="sxs-lookup"><span data-stu-id="5acb6-210">_sort:desc=\<field ex.</span></span> <span data-ttu-id="5acb6-211">日付></span><span class="sxs-lookup"><span data-stu-id="5acb6-211">date></span></span>
3. <span data-ttu-id="5acb6-212">_count =\<最大結果></span><span class="sxs-lookup"><span data-stu-id="5acb6-212">_count=\<max results></span></span>

<span data-ttu-id="5acb6-213">目標は、患者の最後の既知の場所を取得できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="5acb6-213">The goal is to be able to retrieve the patient’s last known location.</span></span> <span data-ttu-id="5acb6-214">各検出は、位置情報リソースを参照します。</span><span class="sxs-lookup"><span data-stu-id="5acb6-214">Each encounter references a location resource.</span></span> <span data-ttu-id="5acb6-215">参照には、場所の表示フィールドも含まれます。</span><span class="sxs-lookup"><span data-stu-id="5acb6-215">The reference shall also include the location’s display field.</span></span> <span data-ttu-id="5acb6-216">この通話の次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5acb6-216">See the following example of this call.</span></span>
* * *

    <span data-ttu-id="5acb6-217">要求: fhir-server>/<を取得します。患者 =<患者-id>&_sort:d esc = date&_count = 1</span><span class="sxs-lookup"><span data-stu-id="5acb6-217">Request: GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1</span></span>
    
    <span data-ttu-id="5acb6-218">応答: {"resourcetype": "このバンドル"、"種類": "searchset"、"total": [{"リソース": {"リソース": {"resourceType": "リソース id>"、"id": "<リソース id:" {"use": "オフィシャル", "値": "値"<id>"}", "状態": "" が表示 "と入力します。 [{" 表示 ": [{" display ":" 予定 "}]、"! "、" 患者 "という: {" 参照 ":" 患者 "と" <": {" start ":" 09/17/2018 1:00:00 PM "}," 場所 ": [{>             "場所": {"display": "クリニック-ENT"},} "}}]}</span><span class="sxs-lookup"><span data-stu-id="5acb6-218">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Encounter",         "id": "<resource-id>",         "identifier": [{ "use": "official", "value": "<id>" }],         "status": "arrived",         "type": [           {             "coding": [{ "display": "Appointment" }],           }         ],         "patient": { "reference": "Patient/<patient-id>" },         "period": { "start": "09/17/2018 1:00:00 PM" },         "location": [           {             "location": { "display": "Clinic - ENT" },           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="5acb6-219">この[https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm)フィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5acb6-219">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="5acb6-220">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="5acb6-220">AllergyIntolerance</span></span>

<span data-ttu-id="5acb6-221">以下は、Argonaut AllergyIntolerance profile のサブセットである最小必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="5acb6-221">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

1. <span data-ttu-id="5acb6-222">コード。テキスト</span><span class="sxs-lookup"><span data-stu-id="5acb6-222">Code.Text</span></span>
2. <span data-ttu-id="5acb6-223">コード。 [0]。表示</span><span class="sxs-lookup"><span data-stu-id="5acb6-223">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="5acb6-224">状態</span><span class="sxs-lookup"><span data-stu-id="5acb6-224">Status</span></span>

<span data-ttu-id="5acb6-225">優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリも次のフィールドを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="5acb6-225">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="5acb6-226">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="5acb6-226">RecordedDate</span></span>
2. <span data-ttu-id="5acb6-227">注テキスト</span><span class="sxs-lookup"><span data-stu-id="5acb6-227">Note.Text</span></span>
3. <span data-ttu-id="5acb6-228">反力 [..]物質。テキスト</span><span class="sxs-lookup"><span data-stu-id="5acb6-228">Reaction[..].Substance.Text</span></span>
4. <span data-ttu-id="5acb6-229">反力 [..]影響 [..]テキスト</span><span class="sxs-lookup"><span data-stu-id="5acb6-229">Reaction[..].Manifestation[..].Text</span></span>
5. <span data-ttu-id="5acb6-230">テキストの Div</span><span class="sxs-lookup"><span data-stu-id="5acb6-230">Text.Div</span></span>

<span data-ttu-id="5acb6-231">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="5acb6-231">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="5acb6-232">患者 = \<患者 id の></span><span class="sxs-lookup"><span data-stu-id="5acb6-232">Patient =  \<patient id></span></span>

<span data-ttu-id="5acb6-233">この通話の次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5acb6-233">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="5acb6-234">要求: <fhir-server>/AllergyIntolerance? 患者 =<患者 id を取得></span><span class="sxs-lookup"><span data-stu-id="5acb6-234">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="5acb6-235">応答: {"resourceType": "バンドル"、"id": "<バンドル-id>"、"種類"、"searchset"、"total": ""、""、"AllergyIntolerance": "{" resource ":" {"リソース": "" <"、" id ":" リソース id> "、" recordedDate ":" 2018-09-17T07:00: 00.000 Z "," 物質 ": {" text ":" Cashew ナット "}," 状態 ":" 確認 "," 反応 ": [{" テキスト ":" "が表示" と "応答": "" "" という:on ": [{" text ":" Anaphylactic 反 "}]}"}} "}</span><span class="sxs-lookup"><span data-stu-id="5acb6-235">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "recordedDate": "2018-09-17T07:00:00.000Z",         "substance": {           "text": "Cashew nuts"         },         "status": "confirmed",         "reaction": [           {             "substance": {               "text": "cashew nut allergenic extract Injectable Product"             },             "manifestation": [               {                 "text": "Anaphylactic reaction"               }             ]           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="5acb6-236">この[https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html)フィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5acb6-236">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="5acb6-237">投薬注文</span><span class="sxs-lookup"><span data-stu-id="5acb6-237">Medication Order</span></span>

<span data-ttu-id="5acb6-238">以下は、Argonaut MedicationOrder profile のサブセットである最小必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="5acb6-238">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

1. <span data-ttu-id="5acb6-239">記録された日付</span><span class="sxs-lookup"><span data-stu-id="5acb6-239">DateWritten</span></span>
2. <span data-ttu-id="5acb6-240">Prescriber</span><span class="sxs-lookup"><span data-stu-id="5acb6-240">Prescriber.Display</span></span>
3. <span data-ttu-id="5acb6-241">投薬 (参照の場合)</span><span class="sxs-lookup"><span data-stu-id="5acb6-241">Medication.Display (if reference)</span></span>
4. <span data-ttu-id="5acb6-242">投薬 (概念の場合)</span><span class="sxs-lookup"><span data-stu-id="5acb6-242">Medication.Text (if concept)</span></span>

<span data-ttu-id="5acb6-243">優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリでは、次のフィールドも読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="5acb6-243">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="5acb6-244">DateEnded</span><span class="sxs-lookup"><span data-stu-id="5acb6-244">DateEnded</span></span>
2. <span data-ttu-id="5acb6-245">DosageInstruction。</span><span class="sxs-lookup"><span data-stu-id="5acb6-245">DosageInstruction.Text</span></span>
3. <span data-ttu-id="5acb6-246">テキストの Div</span><span class="sxs-lookup"><span data-stu-id="5acb6-246">Text.Div</span></span>

<span data-ttu-id="5acb6-247">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="5acb6-247">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="5acb6-248">患者 =\<患者 id の></span><span class="sxs-lookup"><span data-stu-id="5acb6-248">patient=\<patient id></span></span>
2. <span data-ttu-id="5acb6-249">_count =\<最大結果></span><span class="sxs-lookup"><span data-stu-id="5acb6-249">_count=\<max results></span></span>

<span data-ttu-id="5acb6-250">この通話の次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5acb6-250">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="5acb6-251">要求: <fhir-server>/MedicationOrder? 患者 =<患者 id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="5acb6-251">Request: GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="5acb6-252">応答: {"resourceType": "バンドル"、"id": "<バンドル id>"、"種類": "searchset"、"合計": ""、"" と入力 ": [{" リソース ": {" リソース ": {" resourceType ":" MedicationOrder "、" id ":" <リソース id> "," dateWritten ":" 2018-09-17 "," medicationCodeableConcept ": {" text ":" Lisinopril 20 MG 口頭タブレット "}," ": {" display ":" Jane Doe "}," dosageInstruction: "{" ":" 1 daily "}]}}}}}}</span><span class="sxs-lookup"><span data-stu-id="5acb6-252">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "MedicationOrder",         "id": "<resource-id>",         "dateWritten": "2018-09-17",         "medicationCodeableConcept": {           "text": "Lisinopril 20 MG Oral Tablet"         },         "prescriber": {           "display": "Jane Doe"         },         "dosageInstruction": [           {             "text": "1 daily"           }         ]       }     }   ] }</span></span>

* * *  

<span data-ttu-id="5acb6-253">この[https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html)フィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5acb6-253">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="5acb6-254">サポート</span><span class="sxs-lookup"><span data-stu-id="5acb6-254">Coverage</span></span>

<span data-ttu-id="5acb6-255">以下は、US Core または Argonaut のプロファイルでカバーされていない最低限の必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="5acb6-255">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="5acb6-256">給料または</span><span class="sxs-lookup"><span data-stu-id="5acb6-256">Payor</span></span>

<span data-ttu-id="5acb6-257">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="5acb6-257">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="5acb6-258">患者 =\<患者 id の></span><span class="sxs-lookup"><span data-stu-id="5acb6-258">patient=\<patient id></span></span>

<span data-ttu-id="5acb6-259">この通話の次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5acb6-259">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="5acb6-260">要求: <fhir-server>/利用可能かどうかを確認してください。患者 =<患者 id></span><span class="sxs-lookup"><span data-stu-id="5acb6-260">Request: GET <fhir-server>/Coverage?patient=<patient-id></span></span>
    
    <span data-ttu-id="5acb6-261">応答: {"resourceType": "バンドル"、"type": "検索セット", "集計": [{"リソース": "リソース": "<"、"id": "リソース id>"、"id": "" プラン ":" 第1の保険がありません "、" サブスクリプション ":" 患者/<の患者 id> "}}}]}</span><span class="sxs-lookup"><span data-stu-id="5acb6-261">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Coverage",         "id": "<resource-id>",         "plan": "No Primary Insurance",         "subscriber": { "reference": "Patient/<patient-id>" }       }     }   ] }</span></span>

* * *

<span data-ttu-id="5acb6-262">この[https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html)フィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5acb6-262">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="5acb6-263">場所</span><span class="sxs-lookup"><span data-stu-id="5acb6-263">Location</span></span>

<span data-ttu-id="5acb6-264">このリソース[は、リソースの参照](#encounter)としてのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="5acb6-264">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="5acb6-265">この[https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html)フィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5acb6-265">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
