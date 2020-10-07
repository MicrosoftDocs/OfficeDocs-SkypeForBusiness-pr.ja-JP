---
title: 患者のアプリと EHR の統合 DSTU2 インターフェイス
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
description: Microsoft Teams の患者アプリと連携するように FHIR サーバーを設定または再構成するなど、Teams での DSTU2 インターフェイスの仕様について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ab502f66785af7947185fb0fbee0d3a55dd70c67
ms.sourcegitcommit: f4f5ad1391b472d64390180c81c2680f011a8a10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2020
ms.locfileid: "48367607"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="14527-103">DSTU2 インターフェイスの仕様</span><span class="sxs-lookup"><span data-stu-id="14527-103">DSTU2 interface specification</span></span>

> [!IMPORTANT]
> <span data-ttu-id="14527-104">**2020年10月30日の有効な患者アプリは廃止され、ユーザーは Teams app store からインストールできなくなります。今すぐ Teams の [リストアプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) を使い始めることをお勧めします。**</span><span class="sxs-lookup"><span data-stu-id="14527-104">**Effective October 30, 2020, the Patients app will be deprecated and users will no longer be able to install it from the Teams app store. We encourage you to start using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams today.**</span></span>
>
><span data-ttu-id="14527-105">患者のアプリデータは、チームをバックアップする Office 365 グループのグループメールボックスに格納されます。</span><span class="sxs-lookup"><span data-stu-id="14527-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="14527-106">患者のアプリが廃止されると、そのアプリに関連付けられたデータはすべてこのグループに保持されますが、ユーザーインターフェイスを使ってアクセスすることはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="14527-106">When the Patients app is retired, all data associated with it will be retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="14527-107">現在のユーザーは、 [リストアプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)を使ってリストを再作成できます。</span><span class="sxs-lookup"><span data-stu-id="14527-107">Current users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="14527-108">[リストアプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)は、すべての Teams ユーザー用にプレインストールされており、すべてのチームとチャネルでタブとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="14527-108">The [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="14527-109">リストを使用すると、ケアチームは、組み込みの [患者] テンプレートを使用して、最初から、または Excel にデータをインポートして、患者リストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="14527-109">With Lists, care teams can create patient lists using the built-in Patients template, from scratch, or by importing data to Excel.</span></span> <span data-ttu-id="14527-110">組織でのリストアプリの管理方法の詳細については、「 [リストアプリを管理](../../manage-lists-app.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14527-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="14527-111">Microsoft Teams の患者と連携するように FHIR サーバーを設定または再構成するには、アプリがアクセスする必要があるデータを把握する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14527-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="14527-112">FHIR サーバーでは、次のリソースについて、バンドルを使った POST 要求をサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="14527-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="14527-113">診療</span><span class="sxs-lookup"><span data-stu-id="14527-113">Patient</span></span>](#patient)
- [<span data-ttu-id="14527-114">観察</span><span class="sxs-lookup"><span data-stu-id="14527-114">Observation</span></span>](#observation)
- [<span data-ttu-id="14527-115">状態</span><span class="sxs-lookup"><span data-stu-id="14527-115">Condition</span></span>](#condition)
- [<span data-ttu-id="14527-116">状況</span><span class="sxs-lookup"><span data-stu-id="14527-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="14527-117">Allergy intolerance</span><span class="sxs-lookup"><span data-stu-id="14527-117">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="14527-118">サポート</span><span class="sxs-lookup"><span data-stu-id="14527-118">Coverage</span></span>](#coverage)
- [<span data-ttu-id="14527-119">投薬注文</span><span class="sxs-lookup"><span data-stu-id="14527-119">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="14527-120">場所</span><span class="sxs-lookup"><span data-stu-id="14527-120">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="14527-121">患者リソースは唯一の必須リソースであり、アプリがまったく読み込まれません。</span><span class="sxs-lookup"><span data-stu-id="14527-121">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="14527-122">ただし、Microsoft Teams の患者アプリを使用して、最も優れたエンドユーザーエクスペリエンスを実現するために、以下に記載されている仕様ごとに、上記のすべてのリソースのサポートを実装することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="14527-122">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="14527-123">Microsoft Teams の患者アプリから複数のリソースに対するクエリは、FHIR サーバーの URL への要求のバンドル (バッチ) を投稿します。</span><span class="sxs-lookup"><span data-stu-id="14527-123">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="14527-124">サーバーは各要求を処理し、各要求によって一致したリソースのバンドルを返します。</span><span class="sxs-lookup"><span data-stu-id="14527-124">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="14527-125">詳細と例については、「」を参照してください [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) 。</span><span class="sxs-lookup"><span data-stu-id="14527-125">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="14527-126">以下のすべての FHIR リソースは、直接リソース参照によってアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="14527-126">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="14527-127">準拠している必要な最小フィールドセット</span><span class="sxs-lookup"><span data-stu-id="14527-127">Conformance minimum required field set</span></span>

 <span data-ttu-id="14527-128">FHIR サーバーでは、その機能の事実上の概要を把握するために、準拠のステートメントを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14527-128">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="14527-129">DSTU2 FHIR サーバーでは、次のパラメーターが想定されています。</span><span class="sxs-lookup"><span data-stu-id="14527-129">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

1. <span data-ttu-id="14527-130">後</span><span class="sxs-lookup"><span data-stu-id="14527-130">REST</span></span>
   1. <span data-ttu-id="14527-131">モード</span><span class="sxs-lookup"><span data-stu-id="14527-131">Mode</span></span>
   2. <span data-ttu-id="14527-132">通信</span><span class="sxs-lookup"><span data-stu-id="14527-132">Interaction</span></span>
   3. <span data-ttu-id="14527-133">リソース: 種類</span><span class="sxs-lookup"><span data-stu-id="14527-133">Resource: Type</span></span>
   4. <span data-ttu-id="14527-134">セキュリティ: [OAuth uri 用の拡張子](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="14527-134">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="14527-135">FhirVersion (Microsoft のコードでは、複数のバージョンをサポートするために、どのバージョンをピボットする必要があるかを理解する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="14527-135">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="14527-136">[https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14527-136">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="14527-137">診療</span><span class="sxs-lookup"><span data-stu-id="14527-137">Patient</span></span>

<span data-ttu-id="14527-138">以下は、 [Argonaut の患者プロファイル](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) フィールドのサブセットである、最小の必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="14527-138">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

1. <span data-ttu-id="14527-139">家族</span><span class="sxs-lookup"><span data-stu-id="14527-139">Name.Family</span></span>
2. <span data-ttu-id="14527-140">名前。指定された</span><span class="sxs-lookup"><span data-stu-id="14527-140">Name.Given</span></span>
3. <span data-ttu-id="14527-141">女性</span><span class="sxs-lookup"><span data-stu-id="14527-141">Gender</span></span>
4. <span data-ttu-id="14527-142">地</span><span class="sxs-lookup"><span data-stu-id="14527-142">BirthDate</span></span>
5. <span data-ttu-id="14527-143">MRN (識別子)</span><span class="sxs-lookup"><span data-stu-id="14527-143">MRN (Identifier)</span></span>

<span data-ttu-id="14527-144">優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリも次のフィールドを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="14527-144">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="14527-145">名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="14527-145">Name.Use</span></span>
2. <span data-ttu-id="14527-146">名前プレフィックス</span><span class="sxs-lookup"><span data-stu-id="14527-146">Name.Prefix</span></span>
3. <span data-ttu-id="14527-147">CareProvider (患者リソースのこの参照には、次の例に示す表示フィールドを含める必要があります)。</span><span class="sxs-lookup"><span data-stu-id="14527-147">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

* * *

    <span data-ttu-id="14527-148">要求: <fhir-server>/Patient/<患者 id> を取得する</span><span class="sxs-lookup"><span data-stu-id="14527-148">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="14527-149">応答: {"resourceType": "患者"、"id": "<>"、"</span><span class="sxs-lookup"><span data-stu-id="14527-149">Response: { "resourceType": "Patient", "id": "<patient-id>", .</span></span>
      <span data-ttu-id="14527-150">.</span><span class="sxs-lookup"><span data-stu-id="14527-150">.</span></span>
      <span data-ttu-id="14527-151">.</span><span class="sxs-lookup"><span data-stu-id="14527-151">.</span></span>
      <span data-ttu-id="14527-152">"name": [{"use": "オフィシャル", "prefix": ["Mr"], "family": ["Chau"], "指定された": ["Hugh"]}], "識別子": [{"use": "", "と入力します。 {" コード ": [{" system ":" "、" code ":" "、" code ":" Mr "}]}、" 性別 ":" careProvider ":" 1957-06-05 https://hl7.org/fhir/v2/0203 "、" ": [{" display ":" 鈴木 Doe "}],} 1234567</span><span class="sxs-lookup"><span data-stu-id="14527-152">"name": [ { "use": "official", "prefix": [ "Mr" ], "family": [ "Chau" ], "given": [ "Hugh" ] } ], "identifier": [ { "use": "official", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR" } ] }, "value": "1234567" } ], "gender": "male", "birthDate": "1957-06-05", "careProvider": [{ "display": "Jane Doe" }], }</span></span>

* * *

<span data-ttu-id="14527-153">リソース検索では、/Patient/_search と次のパラメーターで POST メソッドを使います。</span><span class="sxs-lookup"><span data-stu-id="14527-153">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="14527-154">id</span><span class="sxs-lookup"><span data-stu-id="14527-154">id</span></span>
2. <span data-ttu-id="14527-155">ファミリ: contains = (ファミリ名に値が含まれているすべての患者を検索します。)</span><span class="sxs-lookup"><span data-stu-id="14527-155">family:contains=(searches for all patients whose family name contains the value.)</span></span>
3. <span data-ttu-id="14527-156">指定 =\<substring></span><span class="sxs-lookup"><span data-stu-id="14527-156">given=\<substring></span></span>
4. <span data-ttu-id="14527-157">name =\<substring></span><span class="sxs-lookup"><span data-stu-id="14527-157">name=\<substring></span></span>
5. <span data-ttu-id="14527-158">生年月日 = (完全一致)</span><span class="sxs-lookup"><span data-stu-id="14527-158">birthdate=(exact match)</span></span>
6. <span data-ttu-id="14527-159">\_count (返される結果の最大数)</span><span class="sxs-lookup"><span data-stu-id="14527-159">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="14527-160">応答には、検索結果として返されるレコードの合計数が含まれている必要があり \_ ます。カウントは、返されるレコードの数を制限するために PatientsApp によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="14527-160">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="14527-161">識別子 =\<mrn></span><span class="sxs-lookup"><span data-stu-id="14527-161">identifier=\<mrn></span></span>

<span data-ttu-id="14527-162">目標は、次のようにして患者の検索とフィルター処理を行うことができるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="14527-162">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="14527-163">ID: これは、FHIR のすべてのリソースが持つリソース ID です。</span><span class="sxs-lookup"><span data-stu-id="14527-163">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="14527-164">MRN: 診療員が知っている患者の実際の識別子です。</span><span class="sxs-lookup"><span data-stu-id="14527-164">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="14527-165">この MRN は、FHIR の識別子リソース内の識別子の種類に基づいていることを理解しています。</span><span class="sxs-lookup"><span data-stu-id="14527-165">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="14527-166">名前</span><span class="sxs-lookup"><span data-stu-id="14527-166">Name</span></span>
- <span data-ttu-id="14527-167">地</span><span class="sxs-lookup"><span data-stu-id="14527-167">Birthdate</span></span>

<span data-ttu-id="14527-168">この通話の次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14527-168">See the following example  of this call.</span></span>

* * *

    <span data-ttu-id="14527-169">要求 <: fhir-server>/Patient/_search 要求本文: 指定 = hugh&ファミリ = chau</span><span class="sxs-lookup"><span data-stu-id="14527-169">Request: POST <fhir-server>/Patient/_search Request Body: given=hugh&family=chau</span></span>
    
    <span data-ttu-id="14527-170">応答: {"resourceType": "バンドル"、"id": "<バンドル id>",。</span><span class="sxs-lookup"><span data-stu-id="14527-170">Response: { "resourceType": "Bundle", "id": "<bundle-id>", .</span></span>
      <span data-ttu-id="14527-171">.</span><span class="sxs-lookup"><span data-stu-id="14527-171">.</span></span>
      <span data-ttu-id="14527-172">.</span><span class="sxs-lookup"><span data-stu-id="14527-172">.</span></span>
      <span data-ttu-id="14527-173">"entry": [{"リソース": {"resourceType": "患者"、"id": "<>"、"name": [{"text": "Hugh Chau", "family": ["Chau"], "指定された": ["Hugh"]}, "性別": "男性", "生年月日": "1957-06-05": "検索": {""</span><span class="sxs-lookup"><span data-stu-id="14527-173">"entry": [ { "resource": { "resourceType": "Patient", "id": "<patient-id>", "name": [ { "text": "Hugh Chau", "family": [ "Chau" ], "given": [ "Hugh" ] } ], "gender": "male", "birthDate": "1957-06-05" }, "search": { "mode": "match" } } ] }</span></span>

* * *

<span data-ttu-id="14527-174">[https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14527-174">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="14527-175">観察</span><span class="sxs-lookup"><span data-stu-id="14527-175">Observation</span></span>

<span data-ttu-id="14527-176">以下は、必須の最小フィールドであり、Argonaut の重要な署名プロファイルのサブセットです。</span><span class="sxs-lookup"><span data-stu-id="14527-176">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 1. <span data-ttu-id="14527-177">発効 (日付と時刻)</span><span class="sxs-lookup"><span data-stu-id="14527-177">Effective (date time or period)</span></span>
 2. <span data-ttu-id="14527-178">コードの記述</span><span class="sxs-lookup"><span data-stu-id="14527-178">Code.Coding.Code</span></span>
 3. <span data-ttu-id="14527-179">Valu不定の値</span><span class="sxs-lookup"><span data-stu-id="14527-179">ValueQuantity.Value</span></span>

<span data-ttu-id="14527-180">優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリも次のフィールドを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="14527-180">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 1. <span data-ttu-id="14527-181">コード。ディスプレイ</span><span class="sxs-lookup"><span data-stu-id="14527-181">Code.Coding.Display</span></span>
 2. <span data-ttu-id="14527-182">Valuの単位</span><span class="sxs-lookup"><span data-stu-id="14527-182">ValueQuantity.Unit</span></span>

<span data-ttu-id="14527-183">コンポーネントの所見を使う場合は、各コンポーネントの観測に同じロジックが適用されます。</span><span class="sxs-lookup"><span data-stu-id="14527-183">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="14527-184">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="14527-184">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="14527-185">患者 =\<patient id\></span><span class="sxs-lookup"><span data-stu-id="14527-185">patient=\<patient id\></span></span>
2. <span data-ttu-id="14527-186">sort: desc =\<field ex. date\></span><span class="sxs-lookup"><span data-stu-id="14527-186">sort:desc=\<field ex. date\></span></span>

<span data-ttu-id="14527-187">目標は、患者の最新のバイタル・サインを取得できるようにすることです (観測された VitalSigns)。</span><span class="sxs-lookup"><span data-stu-id="14527-187">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

* * *

    <span data-ttu-id="14527-188">要求: <fhir-server>/監視? 患者 =<患者の>&_sort:d esc = date&category = バイタルサイン</span><span class="sxs-lookup"><span data-stu-id="14527-188">Request: GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs</span></span>
    
    <span data-ttu-id="14527-189">応答: {"resourceType": "バンドル"、"id": "<バンドル id>", "「"」と入力して、「検索」、「集計」、「20」、「入力」の順に入力します。 [{"リソース": {"resourceType": "<" と "id": "リソース id>", "カテゴリ": {"コード": {"コーディング": [{"system": "", "code": " http://loinc.org 39156-5", "display": "", "表示": "bmi"} ":" effectiveDateTime ":" 2009-12-01 "," valu"指定した値": {"値": 34.4, "unit": "kg/m2", "システム": " http://unitsofmeasure.org ", "code": "kg/m2"}},},}</span><span class="sxs-lookup"><span data-stu-id="14527-189">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": { "coding": [ { code": "vital-signs" } ], }, "code": { "coding": [ { "system": "http://loinc.org", "code": "39156-5", "display": "bmi" } ], }, "effectiveDateTime": "2009-12-01", "valueQuantity": { "value": 34.4, "unit": "kg/m2", "system": "http://unitsofmeasure.org", "code": "kg/m2" } }, }, .</span></span>
        <span data-ttu-id="14527-190">.</span><span class="sxs-lookup"><span data-stu-id="14527-190">.</span></span>
        <span data-ttu-id="14527-191">.</span><span class="sxs-lookup"><span data-stu-id="14527-191">.</span></span>
      <span data-ttu-id="14527-192">] }</span><span class="sxs-lookup"><span data-stu-id="14527-192">] }</span></span>

* * *

<span data-ttu-id="14527-193">[https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14527-193">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="14527-194">状態</span><span class="sxs-lookup"><span data-stu-id="14527-194">Condition</span></span>

<span data-ttu-id="14527-195">以下は、 [Argonaut 条件プロファイル](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)の一部である最小必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="14527-195">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="14527-196">コード。 [0]。表示</span><span class="sxs-lookup"><span data-stu-id="14527-196">Code.Coding[0].Display</span></span>

<span data-ttu-id="14527-197">優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリでは、次のフィールドも読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="14527-197">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="14527-198">記録された日付</span><span class="sxs-lookup"><span data-stu-id="14527-198">Date Recorded</span></span>
2. <span data-ttu-id="14527-199">程度</span><span class="sxs-lookup"><span data-stu-id="14527-199">Severity</span></span>

<span data-ttu-id="14527-200">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="14527-200">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="14527-201">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="14527-201">patient=\<patient id></span></span>
2. <span data-ttu-id="14527-202">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="14527-202">_count=\<max results></span></span>

<span data-ttu-id="14527-203">この通話の次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14527-203">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="14527-204">要求: fhir-server>/条件? 患者 =<患者 id>&_count = 10 を取得 <</span><span class="sxs-lookup"><span data-stu-id="14527-204">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="14527-205">応答: {"resourceType": "のバンドル"、"id": "<バンドル id>"、"入力": "searchset"、"total": ""、"id": "{" リソース ":" "<"、"id": "" リソース id> "、" コード ": {" コード ": [{" system ":" http://snomed.info/sct "," code ":" 386033004 "," 表示 ":" Neuropathy (dateRecorded) "}]}," ":" 2018-09-17 "severity": {"コード": [{"system": " http://snomed.info/sct ", "code": "24484000", "表示": "", "表示": "重大"} "</span><span class="sxs-lookup"><span data-stu-id="14527-205">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Condition",         "id": "<resource-id>",         "code": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "386033004",               "display": "Neuropathy (nerve damage)"             }           ]         },         "dateRecorded": "2018-09-17",         "severity": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "24484000",               "display": "Severe"             }           ]         }       },     }   ] }</span></span>

* * *

<span data-ttu-id="14527-206">[https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14527-206">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="14527-207">状況</span><span class="sxs-lookup"><span data-stu-id="14527-207">Encounter</span></span>

<span data-ttu-id="14527-208">"US Core" というプロファイルのサブセットである、最低限必要なフィールドは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="14527-208">These are the minimum required fields, which are a subset of the US Core Encounter profile "must have" fields:</span></span>

1. <span data-ttu-id="14527-209">状態</span><span class="sxs-lookup"><span data-stu-id="14527-209">Status</span></span>
2. <span data-ttu-id="14527-210">[0] と入力します。コーディング [0]。表示</span><span class="sxs-lookup"><span data-stu-id="14527-210">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="14527-211">さらに、US Core の次のフィールドは、プロファイルの "サポートが必要" フィールドを示しています。</span><span class="sxs-lookup"><span data-stu-id="14527-211">In addition, the following fields from US Core Encounter profile's "must support" fields</span></span>

1. <span data-ttu-id="14527-212">期間. 開始日</span><span class="sxs-lookup"><span data-stu-id="14527-212">Period.Start</span></span>
2. <span data-ttu-id="14527-213">場所 [0]場所。表示</span><span class="sxs-lookup"><span data-stu-id="14527-213">Location[0].Location.Display</span></span>

<span data-ttu-id="14527-214">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="14527-214">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="14527-215">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="14527-215">patient=\<patient id></span></span>
2. <span data-ttu-id="14527-216">_sort: desc =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="14527-216">_sort:desc=\<field ex. date></span></span>
3. <span data-ttu-id="14527-217">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="14527-217">_count=\<max results></span></span>

<span data-ttu-id="14527-218">目標は、患者の最後の既知の場所を取得できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="14527-218">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="14527-219">各検出は、位置情報リソースを参照します。</span><span class="sxs-lookup"><span data-stu-id="14527-219">Each encounter references a location resource.</span></span> <span data-ttu-id="14527-220">参照には、場所の表示フィールドも含まれます。</span><span class="sxs-lookup"><span data-stu-id="14527-220">The reference shall also include the location's display field.</span></span> <span data-ttu-id="14527-221">この通話の次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14527-221">See the following example of this call.</span></span>
* * *

    <span data-ttu-id="14527-222">要求: fhir-server>/<を取得します。患者 =<患者-id>&_sort:d esc = date&_count = 1</span><span class="sxs-lookup"><span data-stu-id="14527-222">Request: GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1</span></span>
    
    <span data-ttu-id="14527-223">応答: {"resourceType": "バンドル", "種類": "searchset", "集計": "{" リソース ": {" resourceType ":" <リソース id> "、" id ":" "を使用": "" という値: [{"use": "" # ":" ")" " <id> 状態": "が表示"、"種類": [{] コード ": [{" display ":" 予定 "}]、}]、" 患者 ": {" 参照 ":" 患者 "と" <">"}, "ピリオド": {"start": "09/17/2018 1:00:00 PM"}, "場所": [{"場所": {"display": "クリニック-ENT"},}</span><span class="sxs-lookup"><span data-stu-id="14527-223">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Encounter",         "id": "<resource-id>",         "identifier": [{ "use": "official", "value": "<id>" }],         "status": "arrived",         "type": [           {             "coding": [{ "display": "Appointment" }],           }         ],         "patient": { "reference": "Patient/<patient-id>" },         "period": { "start": "09/17/2018 1:00:00 PM" },         "location": [           {             "location": { "display": "Clinic - ENT" },           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="14527-224">[https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14527-224">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="14527-225">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="14527-225">AllergyIntolerance</span></span>

<span data-ttu-id="14527-226">以下は、Argonaut AllergyIntolerance profile のサブセットである最小必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="14527-226">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

1. <span data-ttu-id="14527-227">コード。テキスト</span><span class="sxs-lookup"><span data-stu-id="14527-227">Code.Text</span></span>
2. <span data-ttu-id="14527-228">コード。 [0]。表示</span><span class="sxs-lookup"><span data-stu-id="14527-228">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="14527-229">状態</span><span class="sxs-lookup"><span data-stu-id="14527-229">Status</span></span>

<span data-ttu-id="14527-230">優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリも次のフィールドを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="14527-230">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="14527-231">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="14527-231">RecordedDate</span></span>
2. <span data-ttu-id="14527-232">注テキスト</span><span class="sxs-lookup"><span data-stu-id="14527-232">Note.Text</span></span>
3. <span data-ttu-id="14527-233">反力 [..]物質。テキスト</span><span class="sxs-lookup"><span data-stu-id="14527-233">Reaction[..].Substance.Text</span></span>
4. <span data-ttu-id="14527-234">反力 [..]影響 [..]テキスト</span><span class="sxs-lookup"><span data-stu-id="14527-234">Reaction[..].Manifestation[..].Text</span></span>
5. <span data-ttu-id="14527-235">テキストの Div</span><span class="sxs-lookup"><span data-stu-id="14527-235">Text.Div</span></span>

<span data-ttu-id="14527-236">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="14527-236">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="14527-237">患者 =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="14527-237">Patient =  \<patient id></span></span>

<span data-ttu-id="14527-238">この通話の次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14527-238">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="14527-239">要求: <fhir-server>/AllergyIntolerance? 患者 =<患者 id を取得></span><span class="sxs-lookup"><span data-stu-id="14527-239">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="14527-240">応答: {"resourceType": "バンドル"、"id": "<バンドル id>"、"種類": "searchset"、"total": "recordedDate": "{" resource ":" AllergyIntolerance "、" id ":" <リソース id> "、" ":" 2018-17T07:00: 00.000 Z "," 物質 ": {" text ":" Cashew ナット "}," 状態 ":" 確認 "," 反応 ": [{] 物質": {"text": "cashew ナット allergenic extract Injectable Product"}, "影響": [{"テキスト": "{" text ":" {"text": "Anaphylactic 反"}]}</span><span class="sxs-lookup"><span data-stu-id="14527-240">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "recordedDate": "2018-09-17T07:00:00.000Z",         "substance": {           "text": "Cashew nuts"         },         "status": "confirmed",         "reaction": [           {             "substance": {               "text": "cashew nut allergenic extract Injectable Product"             },             "manifestation": [               {                 "text": "Anaphylactic reaction"               }             ]           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="14527-241">[https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14527-241">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="14527-242">投薬注文</span><span class="sxs-lookup"><span data-stu-id="14527-242">Medication Order</span></span>

<span data-ttu-id="14527-243">以下は、Argonaut MedicationOrder profile のサブセットである最小必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="14527-243">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

1. <span data-ttu-id="14527-244">記録された日付</span><span class="sxs-lookup"><span data-stu-id="14527-244">DateWritten</span></span>
2. <span data-ttu-id="14527-245">Prescriber</span><span class="sxs-lookup"><span data-stu-id="14527-245">Prescriber.Display</span></span>
3. <span data-ttu-id="14527-246">投薬 (参照の場合)</span><span class="sxs-lookup"><span data-stu-id="14527-246">Medication.Display (if reference)</span></span>
4. <span data-ttu-id="14527-247">投薬 (概念の場合)</span><span class="sxs-lookup"><span data-stu-id="14527-247">Medication.Text (if concept)</span></span>

<span data-ttu-id="14527-248">優れたユーザーエクスペリエンスを実現するために、Argonaut フィールドに加えて、患者アプリでは、次のフィールドも読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="14527-248">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="14527-249">DateEnded</span><span class="sxs-lookup"><span data-stu-id="14527-249">DateEnded</span></span>
2. <span data-ttu-id="14527-250">DosageInstruction。</span><span class="sxs-lookup"><span data-stu-id="14527-250">DosageInstruction.Text</span></span>
3. <span data-ttu-id="14527-251">テキストの Div</span><span class="sxs-lookup"><span data-stu-id="14527-251">Text.Div</span></span>

<span data-ttu-id="14527-252">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="14527-252">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="14527-253">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="14527-253">patient=\<patient id></span></span>
2. <span data-ttu-id="14527-254">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="14527-254">_count=\<max results></span></span>

<span data-ttu-id="14527-255">この通話の次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14527-255">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="14527-256">要求: <fhir-server>/MedicationOrder? 患者 =<患者 id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="14527-256">Request: GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="14527-257">応答: {"resourceType": "バンドル"、"id": "<バンドル id>"、"種類": "searchset"、"合計": ""、"" と入力 ": [{" リソース ": {" リソース ": {" resourceType ":" MedicationOrder "、" id ":" <リソース id> "," dateWritten ":" 2018-09-17 "," medicationCodeableConcept ": {" text ":" Lisinopril 20 MG 口頭タブレット "}," ": {" display ":" Jane Doe "}," dosageInstruction: "{" ":" 1 daily "}]}}}}}}</span><span class="sxs-lookup"><span data-stu-id="14527-257">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "MedicationOrder",         "id": "<resource-id>",         "dateWritten": "2018-09-17",         "medicationCodeableConcept": {           "text": "Lisinopril 20 MG Oral Tablet"         },         "prescriber": {           "display": "Jane Doe"         },         "dosageInstruction": [           {             "text": "1 daily"           }         ]       }     }   ] }</span></span>

* * *  

<span data-ttu-id="14527-258">[https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14527-258">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="14527-259">サポート</span><span class="sxs-lookup"><span data-stu-id="14527-259">Coverage</span></span>

<span data-ttu-id="14527-260">以下は、US Core または Argonaut のプロファイルでカバーされていない最低限の必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="14527-260">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="14527-261">給料または</span><span class="sxs-lookup"><span data-stu-id="14527-261">Payor</span></span>

<span data-ttu-id="14527-262">リソース検索では、GET メソッドと次のパラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="14527-262">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="14527-263">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="14527-263">patient=\<patient id></span></span>

<span data-ttu-id="14527-264">この通話の次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14527-264">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="14527-265">要求: <fhir-server>/利用可能かどうかを確認してください。患者 =<患者 id></span><span class="sxs-lookup"><span data-stu-id="14527-265">Request: GET <fhir-server>/Coverage?patient=<patient-id></span></span>
    
    <span data-ttu-id="14527-266">応答: {"resourceType": "バンドル"、"type": "検索セット", "集計": [{"リソース": "リソース": "<"、"id": "リソース id>"、"id": "" プラン ":" 第1の保険がありません "、" サブスクリプション ":" 患者/<の患者 id> "}}}]}</span><span class="sxs-lookup"><span data-stu-id="14527-266">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Coverage",         "id": "<resource-id>",         "plan": "No Primary Insurance",         "subscriber": { "reference": "Patient/<patient-id>" }       }     }   ] }</span></span>

* * *

<span data-ttu-id="14527-267">[https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14527-267">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="14527-268">場所</span><span class="sxs-lookup"><span data-stu-id="14527-268">Location</span></span>

<span data-ttu-id="14527-269">このリソース [は、リソースの参照](#encounter) としてのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="14527-269">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="14527-270">[https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html)このフィールドセットのその他の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14527-270">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
