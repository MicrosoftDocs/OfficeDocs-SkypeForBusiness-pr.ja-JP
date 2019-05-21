---
title: 患者のアプリと EHR の統合 STU3 インターフェイス
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
description: Microsoft Teams の患者向けアプリ EHR の統合
ms.openlocfilehash: 34fd6bb1ecaf788a55aca877c671c9a51cb07944
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2019
ms.locfileid: "33643117"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="ec044-103">STU3 インターフェイスの仕様</span><span class="sxs-lookup"><span data-stu-id="ec044-103">STU3 interface specification</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="ec044-104">Microsoft Teams の患者と連携するように FHIR サーバーを設定または再構成するには、アプリがアクセスする必要があるデータを把握する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec044-104">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="ec044-105">FHIR サーバーでは、次のリソースについて、バンドルを使った POST 要求をサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec044-105">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="ec044-106">診療</span><span class="sxs-lookup"><span data-stu-id="ec044-106">Patient</span></span>](#patient)
- [<span data-ttu-id="ec044-107">観察</span><span class="sxs-lookup"><span data-stu-id="ec044-107">Observation</span></span>](#observation)
- [<span data-ttu-id="ec044-108">状態</span><span class="sxs-lookup"><span data-stu-id="ec044-108">Condition</span></span>](#condition)
- [<span data-ttu-id="ec044-109">状況</span><span class="sxs-lookup"><span data-stu-id="ec044-109">Encounter</span></span>](#encounter)
- [<span data-ttu-id="ec044-110">Allergy Intolerance</span><span class="sxs-lookup"><span data-stu-id="ec044-110">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="ec044-111">サポート</span><span class="sxs-lookup"><span data-stu-id="ec044-111">Coverage</span></span>](#coverage)
- <span data-ttu-id="ec044-112">[投薬ステートメント](#medication-request)(DSTU2 バージョンの PatientsApp の MedicationOrder を置き換えます)</span><span class="sxs-lookup"><span data-stu-id="ec044-112">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="ec044-113">場所 (このリソースから必要な情報は、発生する可能性があります)</span><span class="sxs-lookup"><span data-stu-id="ec044-113">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="ec044-114">患者のリソースは唯一の必須リソースです (アプリがまったく読み込まれなくなります)。ただし、Microsoft Teams の患者アプリを使用して、最も優れたエンドユーザーエクスペリエンスを実現するために、以下に記載されている仕様ごとに、上記のすべてのリソースのサポートを実装することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ec044-114">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="ec044-115">複数のリソースの Microsoft Teams の患者アプリからのクエリは、FHIR サーバーの URL に対する要求のバンドル (バッチ) を投稿するものとします。</span><span class="sxs-lookup"><span data-stu-id="ec044-115">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="ec044-116">サーバーは各要求を処理し、各要求によって一致したリソースのバンドルを返します。</span><span class="sxs-lookup"><span data-stu-id="ec044-116">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="ec044-117">詳細と例については[https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction)、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec044-117">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="ec044-118">機能ステートメント</span><span class="sxs-lookup"><span data-stu-id="ec044-118">Capability Statement</span></span>

<span data-ttu-id="ec044-119">最低限必要なフィールドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="ec044-119">These are the minimum required fields:</span></span>

1. <span data-ttu-id="ec044-120">後</span><span class="sxs-lookup"><span data-stu-id="ec044-120">REST</span></span>
   1. <span data-ttu-id="ec044-121">Mode</span><span class="sxs-lookup"><span data-stu-id="ec044-121">Mode</span></span>
   2. <span data-ttu-id="ec044-122">通信</span><span class="sxs-lookup"><span data-stu-id="ec044-122">Interaction</span></span>
   3. <span data-ttu-id="ec044-123">リソース: 種類</span><span class="sxs-lookup"><span data-stu-id="ec044-123">Resource: Type</span></span>
   4. <span data-ttu-id="ec044-124">セキュリティ: [OAuth uri 用の拡張子](http://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="ec044-124">Security: [Extension for OAuth URIs](http://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="ec044-125">FhirVersion (コードは、どのバージョンをピボットするかを理解するために必要です。)</span><span class="sxs-lookup"><span data-stu-id="ec044-125">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="ec044-126">この[https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html)フィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec044-126">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="ec044-127">診療</span><span class="sxs-lookup"><span data-stu-id="ec044-127">Patient</span></span>

<span data-ttu-id="ec044-128">以下は、Argonaut の患者プロファイルフィールドのサブセットである、必要な最小フィールドを示しています。</span><span class="sxs-lookup"><span data-stu-id="ec044-128">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

1. <span data-ttu-id="ec044-129">名前。指定された</span><span class="sxs-lookup"><span data-stu-id="ec044-129">Name.Given</span></span>
2. <span data-ttu-id="ec044-130">家族</span><span class="sxs-lookup"><span data-stu-id="ec044-130">Name.Family</span></span>
3. <span data-ttu-id="ec044-131">女性</span><span class="sxs-lookup"><span data-stu-id="ec044-131">Gender</span></span>
4. <span data-ttu-id="ec044-132">地</span><span class="sxs-lookup"><span data-stu-id="ec044-132">BirthDate</span></span>
5. <span data-ttu-id="ec044-133">MRN (識別子)</span><span class="sxs-lookup"><span data-stu-id="ec044-133">MRN (Identifier)</span></span>

<span data-ttu-id="ec044-134">優れたユーザーエクスペリエンスを実現するために、 [Argonaut フィールド](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)に加えて、患者アプリでは、次のフィールドも読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="ec044-134">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="ec044-135">名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ec044-135">Name.Use</span></span>
2. <span data-ttu-id="ec044-136">名前プレフィックス</span><span class="sxs-lookup"><span data-stu-id="ec044-136">Name.Prefix</span></span>
3. <span data-ttu-id="ec044-137">[一般の専門スタッフ]-すべての専門スタッフ参照が患者リソースに含まれている必要があります (表示フィールドのみ)。</span><span class="sxs-lookup"><span data-stu-id="ec044-137">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="ec044-138">リソース検索では、/Patient/_search と次のパラメーターで POST メソッドを使います。</span><span class="sxs-lookup"><span data-stu-id="ec044-138">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="ec044-139">id</span><span class="sxs-lookup"><span data-stu-id="ec044-139">id</span></span>
2. <span data-ttu-id="ec044-140">family = (ファミリ名に値が含まれているすべての患者を検索)</span><span class="sxs-lookup"><span data-stu-id="ec044-140">family=(searches for all patients whose family name contains the value)</span></span>
3. <span data-ttu-id="ec044-141">指定 =\<substring></span><span class="sxs-lookup"><span data-stu-id="ec044-141">given=\<substring></span></span>
4. <span data-ttu-id="ec044-142">生年月日 = (完全一致)</span><span class="sxs-lookup"><span data-stu-id="ec044-142">birthdate=(exact match)</span></span>
5. <span data-ttu-id="ec044-143">性別 = (いずれかの管理者の性別の値)</span><span class="sxs-lookup"><span data-stu-id="ec044-143">gender=(values being one of the administrative-gender)</span></span>
6. <span data-ttu-id="ec044-144">\_count (返される結果の最大数)</span><span class="sxs-lookup"><span data-stu-id="ec044-144">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="ec044-145">応答には、返されるレコードの数を制限するために、検索と\_カウントの結果として返されるレコードの合計数が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec044-145">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="ec044-146">識別子 =\<mrn></span><span class="sxs-lookup"><span data-stu-id="ec044-146">identifier=\<mrn></span></span>

<span data-ttu-id="ec044-147">目標は、次のようにして患者の検索とフィルター処理を行うことができるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="ec044-147">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="ec044-148">ID: これは、FHIR のすべてのリソースが持つリソース ID です。</span><span class="sxs-lookup"><span data-stu-id="ec044-148">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="ec044-149">MRN: 診療員が知っている患者の実際の識別子です。</span><span class="sxs-lookup"><span data-stu-id="ec044-149">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="ec044-150">この MRN は、FHIR の識別子リソース内の識別子の種類に基づいています。</span><span class="sxs-lookup"><span data-stu-id="ec044-150">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="ec044-151">名前</span><span class="sxs-lookup"><span data-stu-id="ec044-151">Name</span></span>
- <span data-ttu-id="ec044-152">地</span><span class="sxs-lookup"><span data-stu-id="ec044-152">Birthdate</span></span>

<span data-ttu-id="ec044-153">次の通話の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec044-153">See the following example of the call:</span></span>

* * *

    <span data-ttu-id="ec044-154">要求: POST <fhir-server>/患者/_search 要求本文: 指定 = ruth&family = 黒</span><span class="sxs-lookup"><span data-stu-id="ec044-154">Request: POST <fhir-server>/Patient/_search Request Body: given=ruth&family=black</span></span>
    
    <span data-ttu-id="ec044-155">応答: {"resourceType": "バンドル"、"id": "<bundle-id>"、"meta": {"最終更新日": "2019-01-14T23: 45.052 + 00:00"}, "種類": "searchset", "total": [{"relation": [{"relation": "<fhir"、"url": [{"relation": "self", "url": ""fullUrl": <fhir-server>/患者/<patient-id> "," リソース ": {" resourceType ":" 患者 "、" id ":" <patient-id> "、" meta ": {" versionId ":" 1 "、" 最終更新 ":" 2017-10-18T18:32: 37.000 + 00:00 "}," テキスト ": {" 状態 ":" 生成されました "," div": "</span><span class="sxs-lookup"><span data-stu-id="ec044-155">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "meta": { "lastUpdated": "2019-01-14T23:44:45.052+00:00" }, "type": "searchset", "total": 1, "link": [ { "relation": "self", "url": <fhir-server>/Patient/_search" } ], "entry": [ { "fullUrl": <fhir-server>/Patient/<patient-id>", "resource": { "resourceType": "Patient", "id": "<patient-id>", "meta": { "versionId": "1", "lastUpdated": "2017-10-18T18:32:37.000+00:00" }, "text": { "status": "generated", "div": "</span></span><div><span data-ttu-id="ec044-156">i</span><span class="sxs-lookup"><span data-stu-id="ec044-156">\n</span></span>        <p><span data-ttu-id="ec044-157">Ruth ブラック</span><span class="sxs-lookup"><span data-stu-id="ec044-157">Ruth Black</span></span></p><span data-ttu-id="ec044-158">i</span><span class="sxs-lookup"><span data-stu-id="ec044-158">\n</span></span>      </div><span data-ttu-id="ec044-159">"}," 識別子 ": [{" use ":" 通常 "、" type "。 {" コード ": [{" システム ":"http://hl7.org/fhir/v2/0203"、" "表示": "医学レコード番号"、"ユーザーが選択": "医療記録番号"}、"システム": ""、"値": "医療記録番号"}、"http://hospital.smarthealthit.orgシステム": "1234567"}]、"active": true、"name ": [{" use ":" オフィシャル "," family ":" Black "," 指定された ": [" Ruth "," C "</span><span class="sxs-lookup"><span data-stu-id="ec044-159">" }, "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR", "display": "Medical record number", "userSelected": false } ], "text": "Medical record number" }, "system": "http://hospital.smarthealthit.org", "value": "1234567" } ], "active": true, "name": [ { "use": "official", "family": "Black", "given": [ "Ruth", "C."</span></span>
    <span data-ttu-id="ec044-160">]}], "電気通信": [{"システム": "電話"、"値": "800-599-2739", "use": "home"}、{"system": "電話"、"値": "800-808-7785"、"使用": ""、"次の値": ""、""、"ruth.black@example.com"、""、"女性"、"女性"、"性別": "1951-08-23" "住所 ": [{" use ":" home "," line ": [" "市区町村": "" 在籍県 "," 都道府県 ":" 74066 "," 都道府県 ":" "," 市区町村 ":" "," 都道府県 ":" "," 国 ":" "," 国名 ":" アメリカ "</span><span class="sxs-lookup"><span data-stu-id="ec044-160">] } ], "telecom": [ { "system": "phone", "value": "800-599-2739", "use": "home" }, { "system": "phone", "value": "800-808-7785", "use": "mobile" }, { "system": "email", "value": "ruth.black@example.com" } ], "gender": "female", "birthDate": "1951-08-23", "address": [ { "use": "home", "line": [ "26 South RdApt 22" ], "city": "Sapulpa", "state": "OK", "postalCode": "74066", "country": "USA" } ] }, "search": { "mode": "match" } } ] }</span></span>

* * *

    <span data-ttu-id="ec044-161">要求: GET <fhir-server>/患者/<patient-id></span><span class="sxs-lookup"><span data-stu-id="ec044-161">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="ec044-162">応答: {"resourceType": "患者"、"id": "<patient-id>"、"識別子": [{"use": "通常"、"type": {"code": "http://hl7.org/fhir/v2/0203"、"code": ""、"code": ""、""、""、""、"" ""、""、""、1234567 ""、""、""、""、""、""、""、""、家族 ":" Adams "," 指定された ":" ダニエル "," X "</span><span class="sxs-lookup"><span data-stu-id="ec044-162">Response: { "resourceType": "Patient", "id": "<patient-id>", "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR", } ], "text": "Medical record number" }, "value": "1234567" } ], "name": [ { "use": "official", "family": "Adams", "given": [ "Daniel", "X."</span></span> <span data-ttu-id="ec044-163">]}], "性別": "男性", "生年月日": "1925-12-23",}</span><span class="sxs-lookup"><span data-stu-id="ec044-163">] } ], "gender": "male", "birthDate": "1925-12-23", }</span></span>

* * *

<span data-ttu-id="ec044-164">この[http://hl7.org/fhir/stu3/patient.html](http://hl7.org/fhir/stu3/patient.html)フィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec044-164">See [http://hl7.org/fhir/stu3/patient.html](http://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="ec044-165">観察</span><span class="sxs-lookup"><span data-stu-id="ec044-165">Observation</span></span>

<span data-ttu-id="ec044-166">これらのフィールドは、 [Argonaut](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)に必要な最低限の条件を示しています。</span><span class="sxs-lookup"><span data-stu-id="ec044-166">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

1. <span data-ttu-id="ec044-167">発効 (日付と時刻)</span><span class="sxs-lookup"><span data-stu-id="ec044-167">Effective (date time or period)</span></span>
2. <span data-ttu-id="ec044-168">コードの記述</span><span class="sxs-lookup"><span data-stu-id="ec044-168">Code.Coding.Code</span></span>
3. <span data-ttu-id="ec044-169">Valu不定の値</span><span class="sxs-lookup"><span data-stu-id="ec044-169">ValueQuantity.Value</span></span>

<span data-ttu-id="ec044-170">優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリでは、次のフィールドも読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="ec044-170">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="ec044-171">コード。ディスプレイ</span><span class="sxs-lookup"><span data-stu-id="ec044-171">Code.Coding.Display</span></span>
2. <span data-ttu-id="ec044-172">Valuの単位</span><span class="sxs-lookup"><span data-stu-id="ec044-172">ValueQuantity.Unit</span></span>

<span data-ttu-id="ec044-173">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="ec044-173">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="ec044-174">患者 =\<患者 id></span><span class="sxs-lookup"><span data-stu-id="ec044-174">patient=\<patient id></span></span>
2. <span data-ttu-id="ec044-175">_ sort =-date</span><span class="sxs-lookup"><span data-stu-id="ec044-175">_sort=-date</span></span>
3. <span data-ttu-id="ec044-176">category ("カテゴリ = バイタル-記号") を照会して、重要な記号の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="ec044-176">category (we will query for “category=vital-signs”) to retrieve the list of vital signs.</span></span>

<span data-ttu-id="ec044-177">次の通話の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec044-177">Refer to this example of the call:</span></span>

* * *

    <span data-ttu-id="ec044-178">リクエスト: GET <fhir-server>/観測? 患者 = <patient-id>&category = バイタル・サイン</span><span class="sxs-lookup"><span data-stu-id="ec044-178">Request: GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs</span></span>
    
    <span data-ttu-id="ec044-179">応答: {"resourceType": "バンドル", "id": "<bundle-id>", "type": "searchset", "集計": "検索": {"リソース": {"リソース": {"resourceType": "<resource"、"id": [{"": [{"システム"]: [{"システム": "http://hl7.org/fhir/observation-category", "code"]: ""}"、"}"、"code": {"code": {"code": [{"systemhttp://loinc.org": "", "code": "" 8867-4 "," display ":" heart_rate "}]}," effectiveDateTime ":" 2009-04-08T00:00:00-06 ": {" value ": 72.0," unit ":" {拍} ":" {拍} ":" {拍} "http://unitsofmeasure.org" {拍} "</span><span class="sxs-lookup"><span data-stu-id="ec044-179">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": [ { "coding": [ { "system": "http://hl7.org/fhir/observation-category", "code": "vital-signs" } ], } ], "code": { "coding": [ { "system": "http://loinc.org", "code": "8867-4", "display": "heart_rate" } ] }, "effectiveDateTime": "2009-04-08T00:00:00-06:00", "valueQuantity": { "value": 72.0, "unit": "{beats}/min", "system": "http://unitsofmeasure.org", } } }, .</span></span>
        <span data-ttu-id="ec044-180">.</span><span class="sxs-lookup"><span data-stu-id="ec044-180"></span></span>
        <span data-ttu-id="ec044-181">.</span><span class="sxs-lookup"><span data-stu-id="ec044-181"></span></span>
      <span data-ttu-id="ec044-182">] }</span><span class="sxs-lookup"><span data-stu-id="ec044-182"></span></span>

* * *

<span data-ttu-id="ec044-183">この[https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html)フィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec044-183">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="ec044-184">状態</span><span class="sxs-lookup"><span data-stu-id="ec044-184">Condition</span></span>

<span data-ttu-id="ec044-185">[Argonaut 条件プロファイル](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)のサブセットである最小必須フィールドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="ec044-185">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

1. <span data-ttu-id="ec044-186">コード。 [0]。表示</span><span class="sxs-lookup"><span data-stu-id="ec044-186">Code.Coding[0].Display</span></span>

<span data-ttu-id="ec044-187">優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリでは、次のフィールドも読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="ec044-187">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="ec044-188">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="ec044-188">AssertedDate</span></span>
2. <span data-ttu-id="ec044-189">程度</span><span class="sxs-lookup"><span data-stu-id="ec044-189">Severity</span></span>

<span data-ttu-id="ec044-190">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="ec044-190">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="ec044-191">患者 =\<患者 id></span><span class="sxs-lookup"><span data-stu-id="ec044-191">patient=\<patient id></span></span>
2. <span data-ttu-id="ec044-192">_ count =\<max results></span><span class="sxs-lookup"><span data-stu-id="ec044-192">_count=\<max results></span></span>

<span data-ttu-id="ec044-193">この通話の次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec044-193">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="ec044-194">要求: GET <fhir-server>/Condition? 患者 = <patient-id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="ec044-194">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="ec044-195">応答: {"resourceType": "バンドル"、"id": "<bundle-id>", "type": "searchset", "集計": "{" リソース ": {" リソース ": {" resourceType ":" <resource "," id ":" "," id ":" ":" ":"http://snomed.info/sct"、" コード ":" 185903001 "display ":" は、influenza immunization "、}" のようになっている必要があります。 {"assertedDate": "http://snomed.info/sct"、"code": ""、"code": "24484000"、"表示": ""、"": ""、"2018-04-04"}}、。</span><span class="sxs-lookup"><span data-stu-id="ec044-195">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 2, "entry": [ { "resource": { "resourceType": "Condition", "id": "<resource-id>", "code": { "coding": [ { "system": "http://snomed.info/sct", "code": "185903001", "display": "Needs influenza immunization", } ] }, "severity": { "coding": [ { "system": "http://snomed.info/sct", "code": "24484000", "display": "Severe" } ] }, "assertedDate": "2018-04-04" } }, .</span></span>
        <span data-ttu-id="ec044-196">.</span><span class="sxs-lookup"><span data-stu-id="ec044-196"></span></span>
        <span data-ttu-id="ec044-197">.</span><span class="sxs-lookup"><span data-stu-id="ec044-197"></span></span>
      <span data-ttu-id="ec044-198">] }</span><span class="sxs-lookup"><span data-stu-id="ec044-198"></span></span>

* * *
<span data-ttu-id="ec044-199">この[http://hl7.org/fhir/stu3/condition.html](http://hl7.org/fhir/stu3/condition.html)フィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec044-199">See [http://hl7.org/fhir/stu3/condition.html](http://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="ec044-200">状況</span><span class="sxs-lookup"><span data-stu-id="ec044-200">Encounter</span></span>

<span data-ttu-id="ec044-201">" [US Core](http://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) " というプロファイルのサブセットである最小必須フィールドは、"フィールドが含まれている必要があります" である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec044-201">These are the minimum required fields, which are a subset of the [US Core Encounter profile](http://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) “must have” fields).</span></span>

1. <span data-ttu-id="ec044-202">状態</span><span class="sxs-lookup"><span data-stu-id="ec044-202">Status</span></span>
2. <span data-ttu-id="ec044-203">[0] と入力します。コーディング [0]。表示</span><span class="sxs-lookup"><span data-stu-id="ec044-203">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="ec044-204">さらに、US Core の次のフィールドは、プロファイルの "サポートが必要" フィールドを示しています。</span><span class="sxs-lookup"><span data-stu-id="ec044-204">In addition, the following fields from US Core Encounter profile’s “must support” fields:</span></span>

1. <span data-ttu-id="ec044-205">期間. 開始日</span><span class="sxs-lookup"><span data-stu-id="ec044-205">Period.Start</span></span>
2. <span data-ttu-id="ec044-206">場所 [0]場所。表示</span><span class="sxs-lookup"><span data-stu-id="ec044-206">Location[0].Location.Display</span></span>

<span data-ttu-id="ec044-207">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="ec044-207">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="ec044-208">患者 =\<患者 id></span><span class="sxs-lookup"><span data-stu-id="ec044-208">patient=\<patient id></span></span>
2. <span data-ttu-id="ec044-209">(並べ替え: desc =\<フィールドの例)</span><span class="sxs-lookup"><span data-stu-id="ec044-209">_sort:desc=\<field ex.</span></span> <span data-ttu-id="ec044-210">date></span><span class="sxs-lookup"><span data-stu-id="ec044-210">date></span></span>
3. <span data-ttu-id="ec044-211">_ count =\<max results></span><span class="sxs-lookup"><span data-stu-id="ec044-211">_count=\<max results></span></span>

<span data-ttu-id="ec044-212">目標は、患者の最後の既知の場所を取得できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="ec044-212">The goal is to be able to retrieve the patient’s last known location.</span></span> <span data-ttu-id="ec044-213">各検出は、位置情報リソースを参照します。</span><span class="sxs-lookup"><span data-stu-id="ec044-213">Each encounter references a location resource.</span></span> <span data-ttu-id="ec044-214">参照には、場所の表示フィールドも含まれます。</span><span class="sxs-lookup"><span data-stu-id="ec044-214">The reference shall also include the location’s display field.</span></span>

<span data-ttu-id="ec044-215">この[http://hl7.org/fhir/stu3/encounter.html](http://hl7.org/fhir/stu3/encounter.html)フィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec044-215">See [http://hl7.org/fhir/stu3/encounter.html](http://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="ec044-216">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="ec044-216">AllergyIntolerance</span></span>

<span data-ttu-id="ec044-217">以下は、 [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile のサブセットである最小必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="ec044-217">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

1. <span data-ttu-id="ec044-218">コード。テキスト</span><span class="sxs-lookup"><span data-stu-id="ec044-218">Code.Text</span></span>
2. <span data-ttu-id="ec044-219">コード。 [0]。表示</span><span class="sxs-lookup"><span data-stu-id="ec044-219">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="ec044-220">ClinicalStatus/VerificationStatus (両方とも読む)</span><span class="sxs-lookup"><span data-stu-id="ec044-220">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="ec044-221">優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリは次のフィールドも読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="ec044-221">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

1. <span data-ttu-id="ec044-222">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="ec044-222">AssertedDate</span></span>
2. <span data-ttu-id="ec044-223">注テキスト</span><span class="sxs-lookup"><span data-stu-id="ec044-223">Note.Text</span></span>
3. <span data-ttu-id="ec044-224">反</span><span class="sxs-lookup"><span data-stu-id="ec044-224">Reaction</span></span>
    1. <span data-ttu-id="ec044-225">物質 (1 つのコーディング要素)</span><span class="sxs-lookup"><span data-stu-id="ec044-225">Substance (one coding element)</span></span>
    2. <span data-ttu-id="ec044-226">影響 (1 つのコード要素)</span><span class="sxs-lookup"><span data-stu-id="ec044-226">Manifestation (one coding element)</span></span>

<span data-ttu-id="ec044-227">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="ec044-227">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="ec044-228">患者 = \<患者 id></span><span class="sxs-lookup"><span data-stu-id="ec044-228">Patient =  \<patient id></span></span>

<span data-ttu-id="ec044-229">次の通話の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec044-229">See the following example of the call:</span></span> 

* * *

    <span data-ttu-id="ec044-230">要求: GET <fhir-server>/AllergyIntolerance? 患者 = <patient-id></span><span class="sxs-lookup"><span data-stu-id="ec044-230">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="ec044-231">応答: {"resourceType": "<bundle"、"id": "id>"、"type": "searchset"、"total": "searchset"、"AllergyIntolerance": ""、"id": ""、"id": "<resource-id>", "clinicalStatus": "active", "verificationStatus ":" 確認 "," コード ": {" コード ":" {"システム": "http://rxnav.nlm.nih.gov/REST/Ndfrt"、"コード": "N0000175503"、"表示": "sulfonamide antibacterial"、"テキスト": ""ibacterial "}," assertedDate ":" 2018-01-:00 "," 反応 ": [{" 影響 ": [{" ": [{" ": [{" "http://snomed.info/sct: [{" code ": [{"] "271807003"、"表示": "スキン rash"、}]、"テキスト": "スキン rash"} "、}"}} "}</span><span class="sxs-lookup"><span data-stu-id="ec044-231">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "clinicalStatus": "active",         "verificationStatus": "confirmed",         "code": {           "coding": [             {               "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",               "code": "N0000175503",               "display": "sulfonamide antibacterial",             }           ],           "text": "sulfonamide antibacterial"         },         "assertedDate": "2018-01-01T00:00:00-07:00",         "reaction": [           {             "manifestation": [               {                 "coding": [                   {                     "system": "http://snomed.info/sct",                     "code": "271807003",                     "display": "skin rash",                   }                 ],                 "text": "skin rash"               }             ],           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="ec044-232">この[http://hl7.org/fhir/stu3/allergyintolerance.html](http://hl7.org/fhir/stu3/allergyintolerance.html)フィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec044-232">See [http://hl7.org/fhir/stu3/allergyintolerance.html](http://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="ec044-233">投薬要求</span><span class="sxs-lookup"><span data-stu-id="ec044-233">Medication Request</span></span>

<span data-ttu-id="ec044-234">以下は、 [US Core 投薬要求プロファイル](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)のサブセットである最小必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="ec044-234">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

1. <span data-ttu-id="ec044-235">投薬 (参照の場合)</span><span class="sxs-lookup"><span data-stu-id="ec044-235">Medication.Display (if Reference)</span></span>
2. <span data-ttu-id="ec044-236">投薬 (CodableConcept の場合)</span><span class="sxs-lookup"><span data-stu-id="ec044-236">Medication.Text (if CodableConcept)</span></span>
3. <span data-ttu-id="ec044-237">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="ec044-237">AuthoredOn</span></span>
4. <span data-ttu-id="ec044-238">要求者。ディスプレイ</span><span class="sxs-lookup"><span data-stu-id="ec044-238">Requester.Agent.Display</span></span>

<span data-ttu-id="ec044-239">優れたユーザーエクスペリエンスを実現するには、米国内のコアフィールドに加えて、患者のアプリでも次のフィールドを読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="ec044-239">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="ec044-240">DosageInstruction [..]テキスト</span><span class="sxs-lookup"><span data-stu-id="ec044-240">DosageInstruction[..].Text</span></span>
2. <span data-ttu-id="ec044-241">テキスト</span><span class="sxs-lookup"><span data-stu-id="ec044-241">Text</span></span>

<span data-ttu-id="ec044-242">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="ec044-242">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="ec044-243">患者 =\<患者 id></span><span class="sxs-lookup"><span data-stu-id="ec044-243">patient=\<patient id></span></span>
2. <span data-ttu-id="ec044-244">_ count =\<max results></span><span class="sxs-lookup"><span data-stu-id="ec044-244">_count=\<max results></span></span>

<span data-ttu-id="ec044-245">この[https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html)フィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec044-245">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="ec044-246">サポート</span><span class="sxs-lookup"><span data-stu-id="ec044-246">Coverage</span></span>

<span data-ttu-id="ec044-247">以下は、US Core または Argonaut のプロファイルでカバーされていない最低限の必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="ec044-247">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="ec044-248">グループ化、少なくとも1つの要素を</span><span class="sxs-lookup"><span data-stu-id="ec044-248">Grouping, at least one element with</span></span>
    1. <span data-ttu-id="ec044-249">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="ec044-249">GroupDisplay</span></span>
    2. <span data-ttu-id="ec044-250">Plan ディスプレイ</span><span class="sxs-lookup"><span data-stu-id="ec044-250">PlanDisplay</span></span>
2. <span data-ttu-id="ec044-251">ピリオド</span><span class="sxs-lookup"><span data-stu-id="ec044-251">Period</span></span>
3. <span data-ttu-id="ec044-252">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="ec044-252">SubscriberId</span></span>

<span data-ttu-id="ec044-253">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="ec044-253">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="ec044-254">患者 = \<患者 id></span><span class="sxs-lookup"><span data-stu-id="ec044-254">Patient = \<patient id></span></span>

<span data-ttu-id="ec044-255">この[http://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html)フィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec044-255">See [http://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
