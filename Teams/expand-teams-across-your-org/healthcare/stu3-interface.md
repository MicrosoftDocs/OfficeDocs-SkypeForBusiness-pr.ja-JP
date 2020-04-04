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
description: Microsoft Teams の患者アプリと連携するように FHIR サーバーを設定または再構成するなど、Teams での STU3 インターフェイスの仕様について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 35d887575ffb894b7a47e50511e6bd6c3a9a75d1
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2020
ms.locfileid: "43141200"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="66f03-103">STU3 インターフェイスの仕様</span><span class="sxs-lookup"><span data-stu-id="66f03-103">STU3 interface specification</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="66f03-104">Microsoft Teams の患者と連携するように FHIR サーバーを設定または再構成するには、アプリがアクセスする必要があるデータを把握する必要があります。</span><span class="sxs-lookup"><span data-stu-id="66f03-104">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="66f03-105">FHIR サーバーでは、次のリソースについて、バンドルを使った POST 要求をサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="66f03-105">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="66f03-106">診療</span><span class="sxs-lookup"><span data-stu-id="66f03-106">Patient</span></span>](#patient)
- [<span data-ttu-id="66f03-107">観察</span><span class="sxs-lookup"><span data-stu-id="66f03-107">Observation</span></span>](#observation)
- [<span data-ttu-id="66f03-108">状態</span><span class="sxs-lookup"><span data-stu-id="66f03-108">Condition</span></span>](#condition)
- [<span data-ttu-id="66f03-109">状況</span><span class="sxs-lookup"><span data-stu-id="66f03-109">Encounter</span></span>](#encounter)
- [<span data-ttu-id="66f03-110">Allergy Intolerance</span><span class="sxs-lookup"><span data-stu-id="66f03-110">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="66f03-111">サポート</span><span class="sxs-lookup"><span data-stu-id="66f03-111">Coverage</span></span>](#coverage)
- <span data-ttu-id="66f03-112">[投薬ステートメント](#medication-request)(PATIENTSAPP の DSTU2 バージョンの MedicationOrder を置き換えます)</span><span class="sxs-lookup"><span data-stu-id="66f03-112">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="66f03-113">場所 (このリソースから必要な情報は、発生する可能性があります)</span><span class="sxs-lookup"><span data-stu-id="66f03-113">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="66f03-114">患者のリソースは唯一の必須リソースです (アプリがまったく読み込まれなくなります)。ただし、Microsoft Teams の患者アプリを使用して、最も優れたエンドユーザーエクスペリエンスを実現するために、以下に記載されている仕様ごとに、上記のすべてのリソースのサポートを実装することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="66f03-114">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="66f03-115">複数のリソースの Microsoft Teams の患者アプリからのクエリは、FHIR サーバーの URL に対する要求のバンドル (バッチ) を投稿するものとします。</span><span class="sxs-lookup"><span data-stu-id="66f03-115">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="66f03-116">サーバーは各要求を処理し、各要求によって一致したリソースのバンドルを返します。</span><span class="sxs-lookup"><span data-stu-id="66f03-116">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="66f03-117">詳細と例については[https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction)、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66f03-117">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="66f03-118">機能ステートメント</span><span class="sxs-lookup"><span data-stu-id="66f03-118">Capability Statement</span></span>

<span data-ttu-id="66f03-119">最低限必要なフィールドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="66f03-119">These are the minimum required fields:</span></span>

1. <span data-ttu-id="66f03-120">後</span><span class="sxs-lookup"><span data-stu-id="66f03-120">REST</span></span>
   1. <span data-ttu-id="66f03-121">モード</span><span class="sxs-lookup"><span data-stu-id="66f03-121">Mode</span></span>
   2. <span data-ttu-id="66f03-122">通信</span><span class="sxs-lookup"><span data-stu-id="66f03-122">Interaction</span></span>
   3. <span data-ttu-id="66f03-123">リソース: 種類</span><span class="sxs-lookup"><span data-stu-id="66f03-123">Resource: Type</span></span>
   4. <span data-ttu-id="66f03-124">セキュリティ: [OAuth uri 用の拡張子](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="66f03-124">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="66f03-125">FhirVersion (コードは、どのバージョンをピボットするかを理解するために必要です。)</span><span class="sxs-lookup"><span data-stu-id="66f03-125">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="66f03-126">この[https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html)フィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66f03-126">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="66f03-127">診療</span><span class="sxs-lookup"><span data-stu-id="66f03-127">Patient</span></span>

<span data-ttu-id="66f03-128">以下は、Argonaut の患者プロファイルフィールドのサブセットである、必要な最小フィールドを示しています。</span><span class="sxs-lookup"><span data-stu-id="66f03-128">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

1. <span data-ttu-id="66f03-129">名前。指定された</span><span class="sxs-lookup"><span data-stu-id="66f03-129">Name.Given</span></span>
2. <span data-ttu-id="66f03-130">家族</span><span class="sxs-lookup"><span data-stu-id="66f03-130">Name.Family</span></span>
3. <span data-ttu-id="66f03-131">女性</span><span class="sxs-lookup"><span data-stu-id="66f03-131">Gender</span></span>
4. <span data-ttu-id="66f03-132">地</span><span class="sxs-lookup"><span data-stu-id="66f03-132">BirthDate</span></span>
5. <span data-ttu-id="66f03-133">MRN (識別子)</span><span class="sxs-lookup"><span data-stu-id="66f03-133">MRN (Identifier)</span></span>

<span data-ttu-id="66f03-134">優れたユーザーエクスペリエンスを実現するために、 [Argonaut フィールド](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)に加えて、患者アプリでは、次のフィールドも読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="66f03-134">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="66f03-135">名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="66f03-135">Name.Use</span></span>
2. <span data-ttu-id="66f03-136">名前プレフィックス</span><span class="sxs-lookup"><span data-stu-id="66f03-136">Name.Prefix</span></span>
3. <span data-ttu-id="66f03-137">[一般の専門スタッフ]-すべての専門スタッフ参照が患者リソースに含まれている必要があります (表示フィールドのみ)。</span><span class="sxs-lookup"><span data-stu-id="66f03-137">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="66f03-138">リソース検索では、/Patient/_search と次のパラメーターで POST メソッドを使います。</span><span class="sxs-lookup"><span data-stu-id="66f03-138">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="66f03-139">id</span><span class="sxs-lookup"><span data-stu-id="66f03-139">id</span></span>
2. <span data-ttu-id="66f03-140">family = (ファミリ名に値が含まれているすべての患者を検索)</span><span class="sxs-lookup"><span data-stu-id="66f03-140">family=(searches for all patients whose family name contains the value)</span></span>
3. <span data-ttu-id="66f03-141">指定さ\<れた = substring></span><span class="sxs-lookup"><span data-stu-id="66f03-141">given=\<substring></span></span>
4. <span data-ttu-id="66f03-142">生年月日 = (完全一致)</span><span class="sxs-lookup"><span data-stu-id="66f03-142">birthdate=(exact match)</span></span>
5. <span data-ttu-id="66f03-143">性別 = (いずれかの管理者の性別の値)</span><span class="sxs-lookup"><span data-stu-id="66f03-143">gender=(values being one of the administrative-gender)</span></span>
6. <span data-ttu-id="66f03-144">\_count (返される結果の最大数)</span><span class="sxs-lookup"><span data-stu-id="66f03-144">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="66f03-145">応答には、返されるレコードの数を制限するために、検索と\_カウントの結果として返されるレコードの合計数が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="66f03-145">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="66f03-146">識別子 =\<mrn></span><span class="sxs-lookup"><span data-stu-id="66f03-146">identifier=\<mrn></span></span>

<span data-ttu-id="66f03-147">目標は、次のようにして患者の検索とフィルター処理を行うことができるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="66f03-147">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="66f03-148">ID: これは、FHIR のすべてのリソースが持つリソース ID です。</span><span class="sxs-lookup"><span data-stu-id="66f03-148">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="66f03-149">MRN: 診療員が知っている患者の実際の識別子です。</span><span class="sxs-lookup"><span data-stu-id="66f03-149">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="66f03-150">この MRN は、FHIR の識別子リソース内の識別子の種類に基づいています。</span><span class="sxs-lookup"><span data-stu-id="66f03-150">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="66f03-151">名前</span><span class="sxs-lookup"><span data-stu-id="66f03-151">Name</span></span>
- <span data-ttu-id="66f03-152">地</span><span class="sxs-lookup"><span data-stu-id="66f03-152">Birthdate</span></span>

<span data-ttu-id="66f03-153">次の通話の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66f03-153">See the following example of the call:</span></span>

* * *

    <span data-ttu-id="66f03-154">要求: <fhir-server>/Patient/_search 要求本文: 指定 = ruth&ファミリ = 黒</span><span class="sxs-lookup"><span data-stu-id="66f03-154">Request: POST <fhir-server>/Patient/_search Request Body: given=ruth&family=black</span></span>
    
    <span data-ttu-id="66f03-155">応答: {"resourceType": "バンドル"、"id": "<バンドル id>"、"メタ": {"lastUpdated": "2019-01-14T23: 45.052 + 00:00"}, "種類": "searchset", "total": [{"relation": [{"relation": "/patient/_search"} "," entry ":):" @ "" {":" self ":> <[{" fullUrl ": <fhir-server>/Patient/<患者 id>", "リソース": {"resourceType": "<"、"id": ">" という、"" という "、" meta ": {" versionId ":" 1 "、" 最終更新 ":" 2017-10-18T18:32: 37.000 + 00:00 "}," テキスト ": {" 状態 ":" 生成された "," div ":"</span><span class="sxs-lookup"><span data-stu-id="66f03-155">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "meta": { "lastUpdated": "2019-01-14T23:44:45.052+00:00" }, "type": "searchset", "total": 1, "link": [ { "relation": "self", "url": <fhir-server>/Patient/_search" } ], "entry": [ { "fullUrl": <fhir-server>/Patient/<patient-id>", "resource": { "resourceType": "Patient", "id": "<patient-id>", "meta": { "versionId": "1", "lastUpdated": "2017-10-18T18:32:37.000+00:00" }, "text": { "status": "generated", "div": "</span></span><div><span data-ttu-id="66f03-156">i</span><span class="sxs-lookup"><span data-stu-id="66f03-156">\n</span></span>        <p><span data-ttu-id="66f03-157">Ruth ブラック</span><span class="sxs-lookup"><span data-stu-id="66f03-157">Ruth Black</span></span></p><span data-ttu-id="66f03-158">i</span><span class="sxs-lookup"><span data-stu-id="66f03-158">\n</span></span>      </div><span data-ttu-id="66f03-159">"}," 識別子 ": [{" use ":" 通常 "と入力します。 {" コード ": [{" システム ":"https://hl7.org/fhir/v2/0203"," code ":" "," code ":" "," Display "userselected": false} "," text ":" 医療記録番号 "}," system ":"http://hospital.smarthealthit.org"" "値": "1234567"}], "Ruth": "{" use ":" "{" use ":" "{" use ":" "{" use ":" '</span><span class="sxs-lookup"><span data-stu-id="66f03-159">" }, "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR", "display": "Medical record number", "userSelected": false } ], "text": "Medical record number" }, "system": "http://hospital.smarthealthit.org", "value": "1234567" } ], "active": true, "name": [ { "use": "official", "family": "Black", "given": [ "Ruth", "C."</span></span>
    <span data-ttu-id="66f03-160">]}]、"電気通信": [{"システム": "電話"、"値": "800-599-2739"、"use": "home"}、"ruth.black@example.com": "800-808-7785"、"値": ""、"使用": ""、"次の値:" "、" 次の値 ":" "、" "、" 女性 "," 生年月日 ":" 1951-08-23 "、" 住所 ": [{" use ":" home "," line ": [" ""、"市": ""、"市区町村" "," 都道府県 ":" OK "," 郵便番号 ":" 74066 "," 国名 ":" USA "}]}," 検索 ": {" mode ":" match "}}}}}</span><span class="sxs-lookup"><span data-stu-id="66f03-160">] } ], "telecom": [ { "system": "phone", "value": "800-599-2739", "use": "home" }, { "system": "phone", "value": "800-808-7785", "use": "mobile" }, { "system": "email", "value": "ruth.black@example.com" } ], "gender": "female", "birthDate": "1951-08-23", "address": [ { "use": "home", "line": [ "26 South RdApt 22" ], "city": "Sapulpa", "state": "OK", "postalCode": "74066", "country": "USA" } ] }, "search": { "mode": "match" } } ] }</span></span>

* * *

    <span data-ttu-id="66f03-161">要求: <fhir-server>/Patient/<患者 id> を取得する</span><span class="sxs-lookup"><span data-stu-id="66f03-161">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="66f03-162">応答: {"resourceType": "患者"、"id": "<患者の>", "識別子": [{"use": "{" use ":" 通常 "、" type ": {" コード ": [{https://hl7.org/fhir/v2/0203" system ":" "、" code ":" MR "、}"、"text": "医学レコード番号"}, "値": "1234567"}], "Adams" "{" use ":" "{" use ":" "{" use "" "": "'</span><span class="sxs-lookup"><span data-stu-id="66f03-162">Response: { "resourceType": "Patient", "id": "<patient-id>", "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR", } ], "text": "Medical record number" }, "value": "1234567" } ], "name": [ { "use": "official", "family": "Adams", "given": [ "Daniel", "X."</span></span> <span data-ttu-id="66f03-163">]}], "性別": "男性", "生年月日": "1925-12-23",}</span><span class="sxs-lookup"><span data-stu-id="66f03-163">] } ], "gender": "male", "birthDate": "1925-12-23", }</span></span>

* * *

<span data-ttu-id="66f03-164">この[https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html)フィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66f03-164">See [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="66f03-165">観察</span><span class="sxs-lookup"><span data-stu-id="66f03-165">Observation</span></span>

<span data-ttu-id="66f03-166">これらのフィールドは、 [Argonaut](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)に必要な最低限の条件を示しています。</span><span class="sxs-lookup"><span data-stu-id="66f03-166">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

1. <span data-ttu-id="66f03-167">発効 (日付と時刻)</span><span class="sxs-lookup"><span data-stu-id="66f03-167">Effective (date time or period)</span></span>
2. <span data-ttu-id="66f03-168">コードの記述</span><span class="sxs-lookup"><span data-stu-id="66f03-168">Code.Coding.Code</span></span>
3. <span data-ttu-id="66f03-169">Valu不定の値</span><span class="sxs-lookup"><span data-stu-id="66f03-169">ValueQuantity.Value</span></span>

<span data-ttu-id="66f03-170">優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリでは、次のフィールドも読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="66f03-170">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="66f03-171">コード。ディスプレイ</span><span class="sxs-lookup"><span data-stu-id="66f03-171">Code.Coding.Display</span></span>
2. <span data-ttu-id="66f03-172">Valuの単位</span><span class="sxs-lookup"><span data-stu-id="66f03-172">ValueQuantity.Unit</span></span>

<span data-ttu-id="66f03-173">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="66f03-173">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="66f03-174">患者 =\<患者 id の></span><span class="sxs-lookup"><span data-stu-id="66f03-174">patient=\<patient id></span></span>
2. <span data-ttu-id="66f03-175">_sort =-date</span><span class="sxs-lookup"><span data-stu-id="66f03-175">_sort=-date</span></span>
3. <span data-ttu-id="66f03-176">category ("カテゴリ = バイタル-記号") を照会して、重要な記号の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="66f03-176">category (we will query for "category=vital-signs") to retrieve the list of vital signs.</span></span>

<span data-ttu-id="66f03-177">次の通話の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66f03-177">Refer to this example of the call:</span></span>

* * *

    <span data-ttu-id="66f03-178">要求: fhir-server>/監視? 患者 =<患者-id>&カテゴリ = バイバイ <</span><span class="sxs-lookup"><span data-stu-id="66f03-178">Request: GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs</span></span>
    
    <span data-ttu-id="66f03-179">応答: {"resourceType": "バンドル"、"id": "<バンドル id>"、"type" と入力します。検索セット "," 集計 ":" {"リソース": {"resourceType": "観測"、"id": "<リソース id>", "分類": [{"システム": [{"]" という値: [{"https://hl7.org/fhir/observation-categoryシステム": "{" "コード": "" {")" コード ": {" コード ": [{" system ":"http://loinc.org"," code ":" 8867-4 "、" 表示 ":" heart_rate "}]}、" effectiveDateTime ":" 2009-04-08t00:00:00-06:00 "," valuvaluアンチ ty ": {" value ": 72.0," unit ":" {拍}/最小 "," システム ":"http://unitsofmeasure.org",}}},</span><span class="sxs-lookup"><span data-stu-id="66f03-179">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": [ { "coding": [ { "system": "https://hl7.org/fhir/observation-category", "code": "vital-signs" } ], } ], "code": { "coding": [ { "system": "http://loinc.org", "code": "8867-4", "display": "heart_rate" } ] }, "effectiveDateTime": "2009-04-08T00:00:00-06:00", "valueQuantity": { "value": 72.0, "unit": "{beats}/min", "system": "http://unitsofmeasure.org", } } }, .</span></span>
        <span data-ttu-id="66f03-180">.</span><span class="sxs-lookup"><span data-stu-id="66f03-180">.</span></span>
        <span data-ttu-id="66f03-181">.</span><span class="sxs-lookup"><span data-stu-id="66f03-181">.</span></span>
      <span data-ttu-id="66f03-182">] }</span><span class="sxs-lookup"><span data-stu-id="66f03-182">] }</span></span>

* * *

<span data-ttu-id="66f03-183">この[https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html)フィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66f03-183">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="66f03-184">状態</span><span class="sxs-lookup"><span data-stu-id="66f03-184">Condition</span></span>

<span data-ttu-id="66f03-185">[Argonaut 条件プロファイル](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)のサブセットである最小必須フィールドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="66f03-185">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

1. <span data-ttu-id="66f03-186">コード。 [0]。表示</span><span class="sxs-lookup"><span data-stu-id="66f03-186">Code.Coding[0].Display</span></span>

<span data-ttu-id="66f03-187">優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリでは、次のフィールドも読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="66f03-187">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="66f03-188">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="66f03-188">AssertedDate</span></span>
2. <span data-ttu-id="66f03-189">程度</span><span class="sxs-lookup"><span data-stu-id="66f03-189">Severity</span></span>

<span data-ttu-id="66f03-190">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="66f03-190">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="66f03-191">患者 =\<患者 id の></span><span class="sxs-lookup"><span data-stu-id="66f03-191">patient=\<patient id></span></span>
2. <span data-ttu-id="66f03-192">_count =\<最大結果></span><span class="sxs-lookup"><span data-stu-id="66f03-192">_count=\<max results></span></span>

<span data-ttu-id="66f03-193">この通話の次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66f03-193">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="66f03-194">要求: fhir-server>/条件? 患者 =<患者 id>&_count = 10 を取得 <</span><span class="sxs-lookup"><span data-stu-id="66f03-194">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="66f03-195">応答: {"resourceType": "バンドル", "id": "<バンドル id>"、"種類"、"searchset"、"集計": [{"リソース": {"resourceType": [{"リソース": {"resourceType": "id": "id": "<リソース id>"、"コード": ""http://snomed.info/sct, "コード": "185903001", "表示": "influenza immunization"、"}"、"severity": {"assertedDate": ""http://snomed.info/sct、"code": ""、"code": "24484000"、"表示": "", "表示": "" "" 2018-04-04</span><span class="sxs-lookup"><span data-stu-id="66f03-195">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 2, "entry": [ { "resource": { "resourceType": "Condition", "id": "<resource-id>", "code": { "coding": [ { "system": "http://snomed.info/sct", "code": "185903001", "display": "Needs influenza immunization", } ] }, "severity": { "coding": [ { "system": "http://snomed.info/sct", "code": "24484000", "display": "Severe" } ] }, "assertedDate": "2018-04-04" } }, .</span></span>
        <span data-ttu-id="66f03-196">.</span><span class="sxs-lookup"><span data-stu-id="66f03-196">.</span></span>
        <span data-ttu-id="66f03-197">.</span><span class="sxs-lookup"><span data-stu-id="66f03-197">.</span></span>
      <span data-ttu-id="66f03-198">] }</span><span class="sxs-lookup"><span data-stu-id="66f03-198">] }</span></span>

* * *
<span data-ttu-id="66f03-199">この[https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html)フィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66f03-199">See [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="66f03-200">状況</span><span class="sxs-lookup"><span data-stu-id="66f03-200">Encounter</span></span>

<span data-ttu-id="66f03-201">" [US Core](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) " というプロファイルのサブセットである最小必須フィールドは、"フィールドが含まれている必要があります" である必要があります。</span><span class="sxs-lookup"><span data-stu-id="66f03-201">These are the minimum required fields, which are a subset of the [US Core Encounter profile](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have" fields).</span></span>

1. <span data-ttu-id="66f03-202">状態</span><span class="sxs-lookup"><span data-stu-id="66f03-202">Status</span></span>
2. <span data-ttu-id="66f03-203">[0] と入力します。コーディング [0]。表示</span><span class="sxs-lookup"><span data-stu-id="66f03-203">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="66f03-204">さらに、US Core の次のフィールドは、プロファイルの "サポートが必要" フィールドを示しています。</span><span class="sxs-lookup"><span data-stu-id="66f03-204">In addition, the following fields from US Core Encounter profile's "must support" fields:</span></span>

1. <span data-ttu-id="66f03-205">期間. 開始日</span><span class="sxs-lookup"><span data-stu-id="66f03-205">Period.Start</span></span>
2. <span data-ttu-id="66f03-206">場所 [0]場所。表示</span><span class="sxs-lookup"><span data-stu-id="66f03-206">Location[0].Location.Display</span></span>

<span data-ttu-id="66f03-207">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="66f03-207">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="66f03-208">患者 =\<患者 id の></span><span class="sxs-lookup"><span data-stu-id="66f03-208">patient=\<patient id></span></span>
2. <span data-ttu-id="66f03-209">_sort: desc =\<フィールド ex</span><span class="sxs-lookup"><span data-stu-id="66f03-209">_sort:desc=\<field ex.</span></span> <span data-ttu-id="66f03-210">日付></span><span class="sxs-lookup"><span data-stu-id="66f03-210">date></span></span>
3. <span data-ttu-id="66f03-211">_count =\<最大結果></span><span class="sxs-lookup"><span data-stu-id="66f03-211">_count=\<max results></span></span>

<span data-ttu-id="66f03-212">目標は、患者の最後の既知の場所を取得できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="66f03-212">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="66f03-213">各検出は、位置情報リソースを参照します。</span><span class="sxs-lookup"><span data-stu-id="66f03-213">Each encounter references a location resource.</span></span> <span data-ttu-id="66f03-214">参照には、場所の表示フィールドも含まれます。</span><span class="sxs-lookup"><span data-stu-id="66f03-214">The reference shall also include the location's display field.</span></span>

<span data-ttu-id="66f03-215">この[https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html)フィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66f03-215">See [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="66f03-216">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="66f03-216">AllergyIntolerance</span></span>

<span data-ttu-id="66f03-217">以下は、 [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile のサブセットである最小必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="66f03-217">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

1. <span data-ttu-id="66f03-218">コード。テキスト</span><span class="sxs-lookup"><span data-stu-id="66f03-218">Code.Text</span></span>
2. <span data-ttu-id="66f03-219">コード。 [0]。表示</span><span class="sxs-lookup"><span data-stu-id="66f03-219">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="66f03-220">ClinicalStatus/VerificationStatus (両方とも読む)</span><span class="sxs-lookup"><span data-stu-id="66f03-220">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="66f03-221">優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリは次のフィールドも読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="66f03-221">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

1. <span data-ttu-id="66f03-222">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="66f03-222">AssertedDate</span></span>
2. <span data-ttu-id="66f03-223">注テキスト</span><span class="sxs-lookup"><span data-stu-id="66f03-223">Note.Text</span></span>
3. <span data-ttu-id="66f03-224">反</span><span class="sxs-lookup"><span data-stu-id="66f03-224">Reaction</span></span>
    1. <span data-ttu-id="66f03-225">物質 (1 つのコーディング要素)</span><span class="sxs-lookup"><span data-stu-id="66f03-225">Substance (one coding element)</span></span>
    2. <span data-ttu-id="66f03-226">影響 (1 つのコード要素)</span><span class="sxs-lookup"><span data-stu-id="66f03-226">Manifestation (one coding element)</span></span>

<span data-ttu-id="66f03-227">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="66f03-227">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="66f03-228">患者 = \<患者 id の></span><span class="sxs-lookup"><span data-stu-id="66f03-228">Patient =  \<patient id></span></span>

<span data-ttu-id="66f03-229">次の通話の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66f03-229">See the following example of the call:</span></span> 

* * *

    <span data-ttu-id="66f03-230">要求: <fhir-server>/AllergyIntolerance? 患者 =<患者 id を取得></span><span class="sxs-lookup"><span data-stu-id="66f03-230">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="66f03-231">応答: {"resourceType": "バンドル"、"id": "<バンドル id>"、"種類": "searchset"、"合計": 1, "エントリ": [{"リソース": "AllergyIntolerance"、"id": "<リソース id>"、"verificationStatus": "clinicalStatus": ""、"": "確認"、"コード": "http://rxnav.nlm.nih.gov/REST/Ndfrt"、"": "", "code": "" N0000175503 "," display ":" sulfonamide antibacterial "," sulfonamide antibacterial "}," assertedDate ":" 2018-01-01T00:00:00-07:00:00:00:00 "," 反応 ": [{" 影響 ": [{" コード ": [{" system ":"http://snomed.info/sct"," code ":" 271807003 "," 表示 ":" "," 表示 ":" "," 表示 ":" "{rash",}], "テキスト": "スキン rash"} "</span><span class="sxs-lookup"><span data-stu-id="66f03-231">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "clinicalStatus": "active",         "verificationStatus": "confirmed",         "code": {           "coding": [             {               "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",               "code": "N0000175503",               "display": "sulfonamide antibacterial",             }           ],           "text": "sulfonamide antibacterial"         },         "assertedDate": "2018-01-01T00:00:00-07:00",         "reaction": [           {             "manifestation": [               {                 "coding": [                   {                     "system": "http://snomed.info/sct",                     "code": "271807003",                     "display": "skin rash",                   }                 ],                 "text": "skin rash"               }             ],           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="66f03-232">この[https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html)フィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66f03-232">See [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="66f03-233">投薬要求</span><span class="sxs-lookup"><span data-stu-id="66f03-233">Medication Request</span></span>

<span data-ttu-id="66f03-234">以下は、 [US Core 投薬要求プロファイル](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)のサブセットである最小必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="66f03-234">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

1. <span data-ttu-id="66f03-235">投薬 (参照の場合)</span><span class="sxs-lookup"><span data-stu-id="66f03-235">Medication.Display (if Reference)</span></span>
2. <span data-ttu-id="66f03-236">投薬 (CodableConcept の場合)</span><span class="sxs-lookup"><span data-stu-id="66f03-236">Medication.Text (if CodableConcept)</span></span>
3. <span data-ttu-id="66f03-237">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="66f03-237">AuthoredOn</span></span>
4. <span data-ttu-id="66f03-238">要求者。ディスプレイ</span><span class="sxs-lookup"><span data-stu-id="66f03-238">Requester.Agent.Display</span></span>

<span data-ttu-id="66f03-239">優れたユーザーエクスペリエンスを実現するには、米国内のコアフィールドに加えて、患者のアプリでも次のフィールドを読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="66f03-239">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="66f03-240">DosageInstruction [..]テキスト</span><span class="sxs-lookup"><span data-stu-id="66f03-240">DosageInstruction[..].Text</span></span>
2. <span data-ttu-id="66f03-241">テキスト</span><span class="sxs-lookup"><span data-stu-id="66f03-241">Text</span></span>

<span data-ttu-id="66f03-242">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="66f03-242">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="66f03-243">患者 =\<患者 id の></span><span class="sxs-lookup"><span data-stu-id="66f03-243">patient=\<patient id></span></span>
2. <span data-ttu-id="66f03-244">_count =\<最大結果></span><span class="sxs-lookup"><span data-stu-id="66f03-244">_count=\<max results></span></span>

<span data-ttu-id="66f03-245">この[https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html)フィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66f03-245">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="66f03-246">サポート</span><span class="sxs-lookup"><span data-stu-id="66f03-246">Coverage</span></span>

<span data-ttu-id="66f03-247">以下は、US Core または Argonaut のプロファイルでカバーされていない最低限の必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="66f03-247">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="66f03-248">グループ化、少なくとも1つの要素を</span><span class="sxs-lookup"><span data-stu-id="66f03-248">Grouping, at least one element with</span></span>
    1. <span data-ttu-id="66f03-249">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="66f03-249">GroupDisplay</span></span>
    2. <span data-ttu-id="66f03-250">Plan ディスプレイ</span><span class="sxs-lookup"><span data-stu-id="66f03-250">PlanDisplay</span></span>
2. <span data-ttu-id="66f03-251">ピリオド</span><span class="sxs-lookup"><span data-stu-id="66f03-251">Period</span></span>
3. <span data-ttu-id="66f03-252">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="66f03-252">SubscriberId</span></span>

<span data-ttu-id="66f03-253">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="66f03-253">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="66f03-254">患者 = \<患者 id の></span><span class="sxs-lookup"><span data-stu-id="66f03-254">Patient = \<patient id></span></span>

<span data-ttu-id="66f03-255">この[https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html)フィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66f03-255">See [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
