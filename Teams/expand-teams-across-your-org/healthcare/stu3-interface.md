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
ms.openlocfilehash: bcae5b6fae3da469aaaa35b3a0494273fa8d29ba
ms.sourcegitcommit: a28232f16bfefe6414d1f5a54d5f8c8665eb0e23
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277211"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="fa182-103">STU3 インターフェイスの仕様</span><span class="sxs-lookup"><span data-stu-id="fa182-103">STU3 interface specification</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fa182-104">**2020年9月30日の有効な患者アプリは廃止され、ユーザーは Teams app store からインストールできなくなります。今すぐ Teams の [リストアプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) を使い始めることをお勧めします。**</span><span class="sxs-lookup"><span data-stu-id="fa182-104">**Effective September 30, 2020, the Patients app will be deprecated and users will no longer be able to install it from the Teams app store. We encourage you to start using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams today.**</span></span>
>
><span data-ttu-id="fa182-105">患者のアプリデータは、チームをバックアップする Office 365 グループのグループメールボックスに格納されます。</span><span class="sxs-lookup"><span data-stu-id="fa182-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="fa182-106">患者のアプリが廃止されると、そのアプリに関連付けられたデータはすべてこのグループに保持されますが、ユーザーインターフェイスを使ってアクセスすることはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="fa182-106">When the Patients app is retired, all data associated with it will be retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="fa182-107">現在のユーザーは、 [リストアプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)を使ってリストを再作成できます。</span><span class="sxs-lookup"><span data-stu-id="fa182-107">Current users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="fa182-108">[リストアプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)は、すべての Teams ユーザー用にプレインストールされており、すべてのチームとチャネルでタブとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="fa182-108">The [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="fa182-109">リストを使用すると、ケアチームは、組み込みの [患者] テンプレートを使用して、最初から、または Excel にデータをインポートして、患者リストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="fa182-109">With Lists, care teams can create patient lists using the built-in Patients template, from scratch, or by importing data to Excel.</span></span> <span data-ttu-id="fa182-110">組織でのリストアプリの管理方法の詳細については、「 [リストアプリを管理](../../manage-lists-app.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa182-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="fa182-111">Microsoft Teams の患者と連携するように FHIR サーバーを設定または再構成するには、アプリがアクセスする必要があるデータを把握する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa182-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="fa182-112">FHIR サーバーでは、次のリソースについて、バンドルを使った POST 要求をサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa182-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="fa182-113">診療</span><span class="sxs-lookup"><span data-stu-id="fa182-113">Patient</span></span>](#patient)
- [<span data-ttu-id="fa182-114">観察</span><span class="sxs-lookup"><span data-stu-id="fa182-114">Observation</span></span>](#observation)
- [<span data-ttu-id="fa182-115">状態</span><span class="sxs-lookup"><span data-stu-id="fa182-115">Condition</span></span>](#condition)
- [<span data-ttu-id="fa182-116">状況</span><span class="sxs-lookup"><span data-stu-id="fa182-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="fa182-117">Allergy Intolerance</span><span class="sxs-lookup"><span data-stu-id="fa182-117">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="fa182-118">サポート</span><span class="sxs-lookup"><span data-stu-id="fa182-118">Coverage</span></span>](#coverage)
- <span data-ttu-id="fa182-119">[投薬ステートメント](#medication-request) (PATIENTSAPP の DSTU2 バージョンの MedicationOrder を置き換えます)</span><span class="sxs-lookup"><span data-stu-id="fa182-119">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="fa182-120">場所 (このリソースから必要な情報は、発生する可能性があります)</span><span class="sxs-lookup"><span data-stu-id="fa182-120">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="fa182-121">患者のリソースは唯一の必須リソースです (アプリがまったく読み込まれなくなります)。ただし、Microsoft Teams の患者アプリを使用して、最も優れたエンドユーザーエクスペリエンスを実現するために、以下に記載されている仕様ごとに、上記のすべてのリソースのサポートを実装することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fa182-121">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="fa182-122">複数のリソースの Microsoft Teams の患者アプリからのクエリは、FHIR サーバーの URL に対する要求のバンドル (バッチ) を投稿するものとします。</span><span class="sxs-lookup"><span data-stu-id="fa182-122">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="fa182-123">サーバーは各要求を処理し、各要求によって一致したリソースのバンドルを返します。</span><span class="sxs-lookup"><span data-stu-id="fa182-123">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="fa182-124">詳細と例については、「」を参照してください [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) 。</span><span class="sxs-lookup"><span data-stu-id="fa182-124">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="fa182-125">機能ステートメント</span><span class="sxs-lookup"><span data-stu-id="fa182-125">Capability Statement</span></span>

<span data-ttu-id="fa182-126">最低限必要なフィールドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="fa182-126">These are the minimum required fields:</span></span>

1. <span data-ttu-id="fa182-127">後</span><span class="sxs-lookup"><span data-stu-id="fa182-127">REST</span></span>
   1. <span data-ttu-id="fa182-128">モード</span><span class="sxs-lookup"><span data-stu-id="fa182-128">Mode</span></span>
   2. <span data-ttu-id="fa182-129">通信</span><span class="sxs-lookup"><span data-stu-id="fa182-129">Interaction</span></span>
   3. <span data-ttu-id="fa182-130">リソース: 種類</span><span class="sxs-lookup"><span data-stu-id="fa182-130">Resource: Type</span></span>
   4. <span data-ttu-id="fa182-131">セキュリティ: [OAuth uri 用の拡張子](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="fa182-131">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="fa182-132">FhirVersion (コードは、どのバージョンをピボットするかを理解するために必要です。)</span><span class="sxs-lookup"><span data-stu-id="fa182-132">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="fa182-133">[https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa182-133">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="fa182-134">診療</span><span class="sxs-lookup"><span data-stu-id="fa182-134">Patient</span></span>

<span data-ttu-id="fa182-135">以下は、Argonaut の患者プロファイルフィールドのサブセットである、必要な最小フィールドを示しています。</span><span class="sxs-lookup"><span data-stu-id="fa182-135">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

1. <span data-ttu-id="fa182-136">名前。指定された</span><span class="sxs-lookup"><span data-stu-id="fa182-136">Name.Given</span></span>
2. <span data-ttu-id="fa182-137">家族</span><span class="sxs-lookup"><span data-stu-id="fa182-137">Name.Family</span></span>
3. <span data-ttu-id="fa182-138">女性</span><span class="sxs-lookup"><span data-stu-id="fa182-138">Gender</span></span>
4. <span data-ttu-id="fa182-139">地</span><span class="sxs-lookup"><span data-stu-id="fa182-139">BirthDate</span></span>
5. <span data-ttu-id="fa182-140">MRN (識別子)</span><span class="sxs-lookup"><span data-stu-id="fa182-140">MRN (Identifier)</span></span>

<span data-ttu-id="fa182-141">優れたユーザーエクスペリエンスを実現するために、 [Argonaut フィールド](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)に加えて、患者アプリでは、次のフィールドも読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="fa182-141">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="fa182-142">名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="fa182-142">Name.Use</span></span>
2. <span data-ttu-id="fa182-143">名前プレフィックス</span><span class="sxs-lookup"><span data-stu-id="fa182-143">Name.Prefix</span></span>
3. <span data-ttu-id="fa182-144">[一般の専門スタッフ]-すべての専門スタッフ参照が患者リソースに含まれている必要があります (表示フィールドのみ)。</span><span class="sxs-lookup"><span data-stu-id="fa182-144">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="fa182-145">リソース検索では、/Patient/_search と次のパラメーターで POST メソッドを使います。</span><span class="sxs-lookup"><span data-stu-id="fa182-145">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="fa182-146">id</span><span class="sxs-lookup"><span data-stu-id="fa182-146">id</span></span>
2. <span data-ttu-id="fa182-147">family = (ファミリ名に値が含まれているすべての患者を検索)</span><span class="sxs-lookup"><span data-stu-id="fa182-147">family=(searches for all patients whose family name contains the value)</span></span>
3. <span data-ttu-id="fa182-148">指定 =\<substring></span><span class="sxs-lookup"><span data-stu-id="fa182-148">given=\<substring></span></span>
4. <span data-ttu-id="fa182-149">生年月日 = (完全一致)</span><span class="sxs-lookup"><span data-stu-id="fa182-149">birthdate=(exact match)</span></span>
5. <span data-ttu-id="fa182-150">性別 = (いずれかの管理者の性別の値)</span><span class="sxs-lookup"><span data-stu-id="fa182-150">gender=(values being one of the administrative-gender)</span></span>
6. <span data-ttu-id="fa182-151">\_count (返される結果の最大数)</span><span class="sxs-lookup"><span data-stu-id="fa182-151">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="fa182-152">応答には、 \_ 返されるレコードの数を制限するために、検索とカウントの結果として返されるレコードの合計数が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa182-152">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="fa182-153">識別子 =\<mrn></span><span class="sxs-lookup"><span data-stu-id="fa182-153">identifier=\<mrn></span></span>

<span data-ttu-id="fa182-154">目標は、次のようにして患者の検索とフィルター処理を行うことができるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="fa182-154">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="fa182-155">ID: これは、FHIR のすべてのリソースが持つリソース ID です。</span><span class="sxs-lookup"><span data-stu-id="fa182-155">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="fa182-156">MRN: 診療員が知っている患者の実際の識別子です。</span><span class="sxs-lookup"><span data-stu-id="fa182-156">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="fa182-157">この MRN は、FHIR の識別子リソース内の識別子の種類に基づいています。</span><span class="sxs-lookup"><span data-stu-id="fa182-157">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="fa182-158">名前</span><span class="sxs-lookup"><span data-stu-id="fa182-158">Name</span></span>
- <span data-ttu-id="fa182-159">地</span><span class="sxs-lookup"><span data-stu-id="fa182-159">Birthdate</span></span>

<span data-ttu-id="fa182-160">次の通話の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa182-160">See the following example of the call:</span></span>

* * *

    <span data-ttu-id="fa182-161">要求: <fhir-server>/Patient/_search 要求本文: 指定 = ruth&ファミリ = 黒</span><span class="sxs-lookup"><span data-stu-id="fa182-161">Request: POST <fhir-server>/Patient/_search Request Body: given=ruth&family=black</span></span>
    
    <span data-ttu-id="fa182-162">応答: {"resourceType": "バンドル"、"id": "<バンドル id>"、"メタ": {"lastUpdated": "2019-01-14T23: 45.052 + 00:00"}, "種類": "searchset", "total": [{"relation": [{"relation": "/patient/_search"} "," entry ":):" @ "" {":" self ":> <[{" fullUrl ": <fhir-server>/Patient/<患者 id>", "リソース": {"resourceType": "<"、"id": ">" という、"" という "、" meta ": {" versionId ":" 1 "、" 最終更新 ":" 2017-10-18T18:32: 37.000 + 00:00 "}," テキスト ": {" 状態 ":" 生成された "," div ":"</span><span class="sxs-lookup"><span data-stu-id="fa182-162">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "meta": { "lastUpdated": "2019-01-14T23:44:45.052+00:00" }, "type": "searchset", "total": 1, "link": [ { "relation": "self", "url": <fhir-server>/Patient/_search" } ], "entry": [ { "fullUrl": <fhir-server>/Patient/<patient-id>", "resource": { "resourceType": "Patient", "id": "<patient-id>", "meta": { "versionId": "1", "lastUpdated": "2017-10-18T18:32:37.000+00:00" }, "text": { "status": "generated", "div": "</span></span><div><span data-ttu-id="fa182-163">i</span><span class="sxs-lookup"><span data-stu-id="fa182-163">\n</span></span>        <p><span data-ttu-id="fa182-164">Ruth ブラック</span><span class="sxs-lookup"><span data-stu-id="fa182-164">Ruth Black</span></span></p><span data-ttu-id="fa182-165">i</span><span class="sxs-lookup"><span data-stu-id="fa182-165">\n</span></span>      </div><span data-ttu-id="fa182-166">"}," 識別子 ": [{" use ":" 通常 "と入力します。 {" コード ": [{" システム ":" "," code ":" "," code ":" "," https://hl7.org/fhir/v2/0203 display "userSelected": false} "," text ":" 医療記録番号 "}," system ":" "" "値": "1234567"}], "Ruth": "{" use ":" "{" use ":" "{" use ":" "{" use ":" ' http://hospital.smarthealthit.org</span><span class="sxs-lookup"><span data-stu-id="fa182-166">" }, "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR", "display": "Medical record number", "userSelected": false } ], "text": "Medical record number" }, "system": "http://hospital.smarthealthit.org", "value": "1234567" } ], "active": true, "name": [ { "use": "official", "family": "Black", "given": [ "Ruth", "C."</span></span>
    <span data-ttu-id="fa182-167">]}]、"電気通信": [{"システム": "電話"、"値": "800-599-2739"、"use": "home"}、"ruth.black@example.com": "800-808-7785"、"値": ""、"使用": ""、"次の値:" "、" 次の値 ":" "、" "、" 女性 "," 生年月日 ":" 1951-08-23 "、" 住所 ": [{" use ":" home "," line ": [" ""、"市": ""、"市区町村" "," 都道府県 ":" OK "," 郵便番号 ":" 74066 "," 国名 ":" USA "}]}," 検索 ": {" mode ":" match "}}}}}</span><span class="sxs-lookup"><span data-stu-id="fa182-167">] } ], "telecom": [ { "system": "phone", "value": "800-599-2739", "use": "home" }, { "system": "phone", "value": "800-808-7785", "use": "mobile" }, { "system": "email", "value": "ruth.black@example.com" } ], "gender": "female", "birthDate": "1951-08-23", "address": [ { "use": "home", "line": [ "26 South RdApt 22" ], "city": "Sapulpa", "state": "OK", "postalCode": "74066", "country": "USA" } ] }, "search": { "mode": "match" } } ] }</span></span>

* * *

    <span data-ttu-id="fa182-168">要求: <fhir-server>/Patient/<患者 id> を取得する</span><span class="sxs-lookup"><span data-stu-id="fa182-168">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="fa182-169">応答: {"resourceType": "患者"、"id": "<患者の>", "識別子": [{"use": "{" use ":" 通常 "、" type ": {" コード ": [{" system ":" https://hl7.org/fhir/v2/0203 "、" code ":" MR "、}"、"text": "医学レコード番号"}, "値": "1234567"}], "Adams" "{" use ":" "{" use ":" "{" use "" "": "'</span><span class="sxs-lookup"><span data-stu-id="fa182-169">Response: { "resourceType": "Patient", "id": "<patient-id>", "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR", } ], "text": "Medical record number" }, "value": "1234567" } ], "name": [ { "use": "official", "family": "Adams", "given": [ "Daniel", "X."</span></span> <span data-ttu-id="fa182-170">]}], "性別": "男性", "生年月日": "1925-12-23",}</span><span class="sxs-lookup"><span data-stu-id="fa182-170">] } ], "gender": "male", "birthDate": "1925-12-23", }</span></span>

* * *

<span data-ttu-id="fa182-171">[https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa182-171">See [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="fa182-172">観察</span><span class="sxs-lookup"><span data-stu-id="fa182-172">Observation</span></span>

<span data-ttu-id="fa182-173">これらのフィールドは、 [Argonaut](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)に必要な最低限の条件を示しています。</span><span class="sxs-lookup"><span data-stu-id="fa182-173">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

1. <span data-ttu-id="fa182-174">発効 (日付と時刻)</span><span class="sxs-lookup"><span data-stu-id="fa182-174">Effective (date time or period)</span></span>
2. <span data-ttu-id="fa182-175">コードの記述</span><span class="sxs-lookup"><span data-stu-id="fa182-175">Code.Coding.Code</span></span>
3. <span data-ttu-id="fa182-176">Valu不定の値</span><span class="sxs-lookup"><span data-stu-id="fa182-176">ValueQuantity.Value</span></span>

<span data-ttu-id="fa182-177">優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリでは、次のフィールドも読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="fa182-177">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="fa182-178">コード。ディスプレイ</span><span class="sxs-lookup"><span data-stu-id="fa182-178">Code.Coding.Display</span></span>
2. <span data-ttu-id="fa182-179">Valuの単位</span><span class="sxs-lookup"><span data-stu-id="fa182-179">ValueQuantity.Unit</span></span>

<span data-ttu-id="fa182-180">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="fa182-180">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="fa182-181">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="fa182-181">patient=\<patient id></span></span>
2. <span data-ttu-id="fa182-182">_sort =-date</span><span class="sxs-lookup"><span data-stu-id="fa182-182">_sort=-date</span></span>
3. <span data-ttu-id="fa182-183">category ("カテゴリ = バイタル-記号") を照会して、重要な記号の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="fa182-183">category (we will query for "category=vital-signs") to retrieve the list of vital signs.</span></span>

<span data-ttu-id="fa182-184">次の通話の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa182-184">Refer to this example of the call:</span></span>

* * *

    <span data-ttu-id="fa182-185">要求: fhir-server>/監視? 患者 =<患者-id>&カテゴリ = バイバイ <</span><span class="sxs-lookup"><span data-stu-id="fa182-185">Request: GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs</span></span>
    
    <span data-ttu-id="fa182-186">応答: {"resourceType": "バンドル"、"id": "<バンドル id>"、"type" と入力します。検索セット "," 集計 ":" {"リソース": {"resourceType": "観測"、"id": "<リソース id>", "分類": [{"システム": [{"]" という値: [{"システム": "{" "コード": "" {" https://hl7.org/fhir/observation-category )" コード ": {" コード ": [{" system ":" "," code ":" http://loinc.org 8867-4 "、" 表示 ":" heart_rate "}]}、" effectiveDateTime ":" 2009-04-08T00:00:00-06:00 "," Valuvaluアンチ ty ": {" value ": 72.0," unit ":" {拍}/最小 "," システム ":" http://unitsofmeasure.org ",}}},</span><span class="sxs-lookup"><span data-stu-id="fa182-186">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": [ { "coding": [ { "system": "https://hl7.org/fhir/observation-category", "code": "vital-signs" } ], } ], "code": { "coding": [ { "system": "http://loinc.org", "code": "8867-4", "display": "heart_rate" } ] }, "effectiveDateTime": "2009-04-08T00:00:00-06:00", "valueQuantity": { "value": 72.0, "unit": "{beats}/min", "system": "http://unitsofmeasure.org", } } }, .</span></span>
        <span data-ttu-id="fa182-187">.</span><span class="sxs-lookup"><span data-stu-id="fa182-187">.</span></span>
        <span data-ttu-id="fa182-188">.</span><span class="sxs-lookup"><span data-stu-id="fa182-188">.</span></span>
      <span data-ttu-id="fa182-189">] }</span><span class="sxs-lookup"><span data-stu-id="fa182-189">] }</span></span>

* * *

<span data-ttu-id="fa182-190">[https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa182-190">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="fa182-191">状態</span><span class="sxs-lookup"><span data-stu-id="fa182-191">Condition</span></span>

<span data-ttu-id="fa182-192">[Argonaut 条件プロファイル](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)のサブセットである最小必須フィールドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="fa182-192">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

1. <span data-ttu-id="fa182-193">コード。 [0]。表示</span><span class="sxs-lookup"><span data-stu-id="fa182-193">Code.Coding[0].Display</span></span>

<span data-ttu-id="fa182-194">優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリでは、次のフィールドも読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="fa182-194">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="fa182-195">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="fa182-195">AssertedDate</span></span>
2. <span data-ttu-id="fa182-196">程度</span><span class="sxs-lookup"><span data-stu-id="fa182-196">Severity</span></span>

<span data-ttu-id="fa182-197">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="fa182-197">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="fa182-198">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="fa182-198">patient=\<patient id></span></span>
2. <span data-ttu-id="fa182-199">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="fa182-199">_count=\<max results></span></span>

<span data-ttu-id="fa182-200">この通話の次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa182-200">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="fa182-201">要求: fhir-server>/条件? 患者 =<患者 id>&_count = 10 を取得 <</span><span class="sxs-lookup"><span data-stu-id="fa182-201">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="fa182-202">応答: {"resourceType": "バンドル", "id": "<バンドル id>"、"種類"、"searchset"、"集計": [{"リソース": {"resourceType": [{"リソース": {"resourceType": "id": "id": "<リソース id>"、"コード": "" http://snomed.info/sct , "コード": "185903001", "表示": "influenza immunization"、"}"、"severity": {"assertedDate": "" http://snomed.info/sct 、"code": ""、"code": "24484000"、"表示": "", "表示": "" "" 2018-04-04</span><span class="sxs-lookup"><span data-stu-id="fa182-202">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 2, "entry": [ { "resource": { "resourceType": "Condition", "id": "<resource-id>", "code": { "coding": [ { "system": "http://snomed.info/sct", "code": "185903001", "display": "Needs influenza immunization", } ] }, "severity": { "coding": [ { "system": "http://snomed.info/sct", "code": "24484000", "display": "Severe" } ] }, "assertedDate": "2018-04-04" } }, .</span></span>
        <span data-ttu-id="fa182-203">.</span><span class="sxs-lookup"><span data-stu-id="fa182-203">.</span></span>
        <span data-ttu-id="fa182-204">.</span><span class="sxs-lookup"><span data-stu-id="fa182-204">.</span></span>
      <span data-ttu-id="fa182-205">] }</span><span class="sxs-lookup"><span data-stu-id="fa182-205">] }</span></span>

* * *
<span data-ttu-id="fa182-206">[https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa182-206">See [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="fa182-207">状況</span><span class="sxs-lookup"><span data-stu-id="fa182-207">Encounter</span></span>

<span data-ttu-id="fa182-208">" [US Core](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) " というプロファイルのサブセットである最小必須フィールドは、"フィールドが含まれている必要があります" である必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa182-208">These are the minimum required fields, which are a subset of the [US Core Encounter profile](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have" fields).</span></span>

1. <span data-ttu-id="fa182-209">状態</span><span class="sxs-lookup"><span data-stu-id="fa182-209">Status</span></span>
2. <span data-ttu-id="fa182-210">[0] と入力します。コーディング [0]。表示</span><span class="sxs-lookup"><span data-stu-id="fa182-210">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="fa182-211">さらに、US Core の次のフィールドは、プロファイルの "サポートが必要" フィールドを示しています。</span><span class="sxs-lookup"><span data-stu-id="fa182-211">In addition, the following fields from US Core Encounter profile's "must support" fields:</span></span>

1. <span data-ttu-id="fa182-212">期間. 開始日</span><span class="sxs-lookup"><span data-stu-id="fa182-212">Period.Start</span></span>
2. <span data-ttu-id="fa182-213">場所 [0]場所。表示</span><span class="sxs-lookup"><span data-stu-id="fa182-213">Location[0].Location.Display</span></span>

<span data-ttu-id="fa182-214">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="fa182-214">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="fa182-215">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="fa182-215">patient=\<patient id></span></span>
2. <span data-ttu-id="fa182-216">_sort: desc =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="fa182-216">_sort:desc=\<field ex. date></span></span>
3. <span data-ttu-id="fa182-217">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="fa182-217">_count=\<max results></span></span>

<span data-ttu-id="fa182-218">目標は、患者の最後の既知の場所を取得できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="fa182-218">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="fa182-219">各検出は、位置情報リソースを参照します。</span><span class="sxs-lookup"><span data-stu-id="fa182-219">Each encounter references a location resource.</span></span> <span data-ttu-id="fa182-220">参照には、場所の表示フィールドも含まれます。</span><span class="sxs-lookup"><span data-stu-id="fa182-220">The reference shall also include the location's display field.</span></span>

<span data-ttu-id="fa182-221">[https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa182-221">See [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="fa182-222">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="fa182-222">AllergyIntolerance</span></span>

<span data-ttu-id="fa182-223">以下は、 [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile のサブセットである最小必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="fa182-223">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

1. <span data-ttu-id="fa182-224">コード。テキスト</span><span class="sxs-lookup"><span data-stu-id="fa182-224">Code.Text</span></span>
2. <span data-ttu-id="fa182-225">コード。 [0]。表示</span><span class="sxs-lookup"><span data-stu-id="fa182-225">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="fa182-226">ClinicalStatus/VerificationStatus (両方とも読む)</span><span class="sxs-lookup"><span data-stu-id="fa182-226">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="fa182-227">優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリは次のフィールドも読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="fa182-227">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

1. <span data-ttu-id="fa182-228">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="fa182-228">AssertedDate</span></span>
2. <span data-ttu-id="fa182-229">注テキスト</span><span class="sxs-lookup"><span data-stu-id="fa182-229">Note.Text</span></span>
3. <span data-ttu-id="fa182-230">反</span><span class="sxs-lookup"><span data-stu-id="fa182-230">Reaction</span></span>
    1. <span data-ttu-id="fa182-231">物質 (1 つのコーディング要素)</span><span class="sxs-lookup"><span data-stu-id="fa182-231">Substance (one coding element)</span></span>
    2. <span data-ttu-id="fa182-232">影響 (1 つのコード要素)</span><span class="sxs-lookup"><span data-stu-id="fa182-232">Manifestation (one coding element)</span></span>

<span data-ttu-id="fa182-233">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="fa182-233">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="fa182-234">患者 =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="fa182-234">Patient =  \<patient id></span></span>

<span data-ttu-id="fa182-235">次の通話の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa182-235">See the following example of the call:</span></span> 

* * *

    <span data-ttu-id="fa182-236">要求: <fhir-server>/AllergyIntolerance? 患者 =<患者 id を取得></span><span class="sxs-lookup"><span data-stu-id="fa182-236">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="fa182-237">応答: {"resourceType": "バンドル"、"id": "<バンドル id>"、"種類": "searchset"、"合計": 1, "エントリ": [{"リソース": "AllergyIntolerance"、"id": "<リソース id>"、"verificationStatus": "clinicalStatus": ""、"": "確認"、"コード": ""、"": " http://rxnav.nlm.nih.gov/REST/Ndfrt ", "code": "" N0000175503 "," display ":" sulfonamide antibacterial "," sulfonamide antibacterial "}," assertedDate ":" 2018-01-01T00:00:00-07:00:00:00:00 "," 反応 ": [{" 影響 ": [{" コード ": [{" system ":" http://snomed.info/sct "," code ":" 271807003 "," 表示 ":" "," 表示 ":" "," 表示 ":" "{rash",}], "テキスト": "スキン rash"} "</span><span class="sxs-lookup"><span data-stu-id="fa182-237">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "clinicalStatus": "active",         "verificationStatus": "confirmed",         "code": {           "coding": [             {               "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",               "code": "N0000175503",               "display": "sulfonamide antibacterial",             }           ],           "text": "sulfonamide antibacterial"         },         "assertedDate": "2018-01-01T00:00:00-07:00",         "reaction": [           {             "manifestation": [               {                 "coding": [                   {                     "system": "http://snomed.info/sct",                     "code": "271807003",                     "display": "skin rash",                   }                 ],                 "text": "skin rash"               }             ],           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="fa182-238">[https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa182-238">See [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="fa182-239">投薬要求</span><span class="sxs-lookup"><span data-stu-id="fa182-239">Medication Request</span></span>

<span data-ttu-id="fa182-240">以下は、 [US Core 投薬要求プロファイル](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)のサブセットである最小必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="fa182-240">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

1. <span data-ttu-id="fa182-241">投薬 (参照の場合)</span><span class="sxs-lookup"><span data-stu-id="fa182-241">Medication.Display (if Reference)</span></span>
2. <span data-ttu-id="fa182-242">投薬 (CodableConcept の場合)</span><span class="sxs-lookup"><span data-stu-id="fa182-242">Medication.Text (if CodableConcept)</span></span>
3. <span data-ttu-id="fa182-243">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="fa182-243">AuthoredOn</span></span>
4. <span data-ttu-id="fa182-244">要求者。ディスプレイ</span><span class="sxs-lookup"><span data-stu-id="fa182-244">Requester.Agent.Display</span></span>

<span data-ttu-id="fa182-245">優れたユーザーエクスペリエンスを実現するには、米国内のコアフィールドに加えて、患者のアプリでも次のフィールドを読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="fa182-245">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="fa182-246">DosageInstruction [..]テキスト</span><span class="sxs-lookup"><span data-stu-id="fa182-246">DosageInstruction[..].Text</span></span>
2. <span data-ttu-id="fa182-247">テキスト</span><span class="sxs-lookup"><span data-stu-id="fa182-247">Text</span></span>

<span data-ttu-id="fa182-248">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="fa182-248">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="fa182-249">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="fa182-249">patient=\<patient id></span></span>
2. <span data-ttu-id="fa182-250">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="fa182-250">_count=\<max results></span></span>

<span data-ttu-id="fa182-251">[https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa182-251">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="fa182-252">サポート</span><span class="sxs-lookup"><span data-stu-id="fa182-252">Coverage</span></span>

<span data-ttu-id="fa182-253">以下は、US Core または Argonaut のプロファイルでカバーされていない最低限の必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="fa182-253">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="fa182-254">グループ化、少なくとも1つの要素を</span><span class="sxs-lookup"><span data-stu-id="fa182-254">Grouping, at least one element with</span></span>
    1. <span data-ttu-id="fa182-255">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="fa182-255">GroupDisplay</span></span>
    2. <span data-ttu-id="fa182-256">Plan ディスプレイ</span><span class="sxs-lookup"><span data-stu-id="fa182-256">PlanDisplay</span></span>
2. <span data-ttu-id="fa182-257">ピリオド</span><span class="sxs-lookup"><span data-stu-id="fa182-257">Period</span></span>
3. <span data-ttu-id="fa182-258">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="fa182-258">SubscriberId</span></span>

<span data-ttu-id="fa182-259">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="fa182-259">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="fa182-260">患者 = \<patient id></span><span class="sxs-lookup"><span data-stu-id="fa182-260">Patient = \<patient id></span></span>

<span data-ttu-id="fa182-261">[https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa182-261">See [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
