---
title: 患者アプリの概要
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
description: FHIR Api を使用して、電子医療記録を Microsoft Teams の患者アプリに統合する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 29bb5b32cdd6e2f0d819adcc610639929921d078
ms.sourcegitcommit: 3b54a56ec1fe4366580621e19cdbb6a833a01161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2020
ms.locfileid: "48361387"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a><span data-ttu-id="06c2e-103">電子医療記録を Microsoft Teams に統合する</span><span class="sxs-lookup"><span data-stu-id="06c2e-103">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="06c2e-104">**2020年10月15日に有効な患者アプリは廃止され、ユーザーは Teams app store からインストールできなくなります。今すぐ Teams の [リストアプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) を使い始めることをお勧めします。**</span><span class="sxs-lookup"><span data-stu-id="06c2e-104">**Effective October 15, 2020, the Patients app will be deprecated and users will no longer be able to install it from the Teams app store. We encourage you to start using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams today.**</span></span>
>
><span data-ttu-id="06c2e-105">患者のアプリデータは、チームをバックアップする Office 365 グループのグループメールボックスに格納されます。</span><span class="sxs-lookup"><span data-stu-id="06c2e-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="06c2e-106">患者のアプリが廃止されると、そのアプリに関連付けられたデータはすべてこのグループに保持されますが、ユーザーインターフェイスを使ってアクセスすることはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="06c2e-106">When the Patients app is retired, all data associated with it will be retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="06c2e-107">現在のユーザーは、 [リストアプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)を使ってリストを再作成できます。</span><span class="sxs-lookup"><span data-stu-id="06c2e-107">Current users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="06c2e-108">[リストアプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)は、すべての Teams ユーザー用にプレインストールされており、すべてのチームとチャネルでタブとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="06c2e-108">The [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="06c2e-109">リストを使用すると、ケアチームは、組み込みの [患者] テンプレートを使用して、最初から、または Excel にデータをインポートして、患者リストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="06c2e-109">With Lists, care teams can create patient lists using the built-in Patients template, from scratch, or by importing data to Excel.</span></span> <span data-ttu-id="06c2e-110">組織でのリストアプリの管理方法の詳細については、「 [リストアプリを管理](../../manage-lists-app.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06c2e-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="06c2e-111">この記事は、医療情報システム上で FHIR Api を使用して Microsoft Teams に接続することに関心を持っている一般的なヘルスケアの IT 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="06c2e-111">This article is intended for a general healthcare IT developer interested in using FHIR APIs on top of a medical information system to connect to Microsoft Teams.</span></span> <span data-ttu-id="06c2e-112">これにより、医療機関のニーズに合ったケアの調整シナリオが可能になります。</span><span class="sxs-lookup"><span data-stu-id="06c2e-112">This would enable care coordination scenarios that match the needs of a healthcare organization.</span></span>

<span data-ttu-id="06c2e-113">リンクされた記事ドキュメント「Microsoft Teams の患者」アプリの FHIR インターフェイスの仕様について説明し、以降のセクションでは、FHIR サーバーの設定と開発環境またはテナントでの患者アプリへの接続に必要なものについて説明します。</span><span class="sxs-lookup"><span data-stu-id="06c2e-113">Linked articles document the FHIR interface specifications for the Microsoft Teams Patients app, and following sections explain what is required for setting up a FHIR server and connecting to the Patients app in your development environment or tenant.</span></span> <span data-ttu-id="06c2e-114">また、選択した FHIR サーバーのドキュメントについて理解している必要があります。これは、サポートされているオプションのいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="06c2e-114">You will also need to be familiar with the documentation of the FHIR server you have chosen, which must be one of the supported options:</span></span>
- <span data-ttu-id="06c2e-115">Datica ( [CMI](https://datica.com/compliant-managed-integration/) サービス経由)</span><span class="sxs-lookup"><span data-stu-id="06c2e-115">Datica (through their [CMI](https://datica.com/compliant-managed-integration/) offering)</span></span>
- <span data-ttu-id="06c2e-116">Infor Cloverleaf ( [Infor FHIR ブリッジ](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html)経由)</span><span class="sxs-lookup"><span data-stu-id="06c2e-116">Infor Cloverleaf (through the [Infor FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span></span>
- <span data-ttu-id="06c2e-117">Redox ( [r ^ FHIR サーバ](https://www.redoxengine.com/fhir/)を経由)</span><span class="sxs-lookup"><span data-stu-id="06c2e-117">Redox (through the [R^FHIR server](https://www.redoxengine.com/fhir/))</span></span>
- <span data-ttu-id="06c2e-118">Dapasoft (の場合は、 [FHIR の](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/)場合)</span><span class="sxs-lookup"><span data-stu-id="06c2e-118">Dapasoft (through [Corolar on FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span></span>

> [!NOTE]
> <span data-ttu-id="06c2e-119">このプロセスには、Microsoft Teams 管理センターまたは PowerShell コマンドレットを使用して機能を有効にする手順は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="06c2e-119">This process does not includes steps that use the Microsoft Teams admin center or PowerShell cmdlets to enable features.</span></span> <span data-ttu-id="06c2e-120">構成は、FHIR サーバー/サービス側と患者のアプリクライアントで行われます。</span><span class="sxs-lookup"><span data-stu-id="06c2e-120">The configuration is entirely done on the FHIR server/service side and in the Patients app client.</span></span>

<span data-ttu-id="06c2e-121">次に、患者アプリのアーキテクチャを示します。</span><span class="sxs-lookup"><span data-stu-id="06c2e-121">Illustrated below is the architecture of the Patients app:</span></span>

![患者のアプリアーキテクチャの図](../../media/patients-app-architecture.png)

<span data-ttu-id="06c2e-123">以下のセクションでは、患者アプリと統合するために、FHIR server (または EHR が有効な FHIR Api) が満たす必要のある、FHIR 専用データアクセスレイヤーの要件について説明します。これには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="06c2e-123">The following sections explain the requirements of the FHIR-only data access layer for the Patients app that a FHIR server (or EHR enabled FHIR APIs) must meet in order to integrate with the Patients app, including the following:</span></span>

- <span data-ttu-id="06c2e-124">ユーザー認証に関する期待</span><span class="sxs-lookup"><span data-stu-id="06c2e-124">Expectations around user authentication</span></span>
- <span data-ttu-id="06c2e-125">統合インターフェイスの機能と技術の要件</span><span class="sxs-lookup"><span data-stu-id="06c2e-125">Functional and technical requirements of the integration interface</span></span>
- <span data-ttu-id="06c2e-126">パフォーマンスと信頼性に関する期待</span><span class="sxs-lookup"><span data-stu-id="06c2e-126">Expectations around performance and reliability</span></span>
- <span data-ttu-id="06c2e-127">患者アプリでサポートされる FHIR リソースに対する期待</span><span class="sxs-lookup"><span data-stu-id="06c2e-127">Expectations around FHIR resources to be supported for the Patients app</span></span>
- <span data-ttu-id="06c2e-128">統合のプロセスと想定される契約モデル</span><span class="sxs-lookup"><span data-stu-id="06c2e-128">Process for integration and the expected engagement model</span></span>
- <span data-ttu-id="06c2e-129">FHIR の使用を開始する方法と、患者アプリで直面する一般的な課題</span><span class="sxs-lookup"><span data-stu-id="06c2e-129">How to get started with FHIR and some common challenges faced with the Patients app</span></span>
- <span data-ttu-id="06c2e-130">患者アプリの次回のイテレーションに関する将来の要件</span><span class="sxs-lookup"><span data-stu-id="06c2e-130">Future requirements for the next iteration of the Patients app</span></span>

> [!NOTE]
> <span data-ttu-id="06c2e-131">以下のセクションでは、"パートナー" または "相互運用パートナー" という単語を使用して、患者アプリの EHR システムと FHIR の統合を可能にするサードパーティ組織を参照しています。また、リストされている仕様に合わせて FHIR サーバーが実装されています。</span><span class="sxs-lookup"><span data-stu-id="06c2e-131">In the following sections, the word "partner" or "Interop partner" is used to refer to any 3rd party Organization that enables integration to EHR systems for the Patients app through FHIR and is implementing a FHIR Server to match the listed specifications.</span></span>

## <a name="functional-and-technical-requirements"></a><span data-ttu-id="06c2e-132">機能と技術の要件</span><span class="sxs-lookup"><span data-stu-id="06c2e-132">Functional and technical requirements</span></span>  

### <a name="authentication"></a><span data-ttu-id="06c2e-133">認証</span><span class="sxs-lookup"><span data-stu-id="06c2e-133">Authentication</span></span>  

<span data-ttu-id="06c2e-134">*ユーザーレベル認証をサポートしていない*アプリレベルの承認は、ehr システムでユーザーレベルの承認が実装されている場合でも、データ変換を実行し、ehr データへの接続を公開するための、より一般的にサポートされている方法です。</span><span class="sxs-lookup"><span data-stu-id="06c2e-134">App-level authorization *with no support for user level authorization* is the more commonly supported way to perform data transformations and expose connections to EHR data through FHIR, even though the EHR system might implement user level authorization.</span></span> <span data-ttu-id="06c2e-135">相互運用サービス (パートナー) は、EHR データへのアクセス権を昇格させ、それらが適切な FHIR リソースと同じデータを公開したときに、相互運用サービスまたはプラットフォームとの統合によって、相互運用サービスコンシューマー (患者アプリ) に承認コンテキストが渡されることはありません。</span><span class="sxs-lookup"><span data-stu-id="06c2e-135">The Interop Service (Partner) gets elevated access to the EHR data, and when they expose the same data as the appropriate FHIR resources there is no authorization context passed on to the Interop Service Consumer (the Patients app) integrating with the Interop Service or Platform.</span></span> <span data-ttu-id="06c2e-136">患者のアプリでは、ユーザーレベルの承認を強制することはできませんが、患者のアプリと相互運用パートナーのサービス間でのアプリケーションの認証をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="06c2e-136">The Patients app will not be able to enforce user level authorization, but does support application to application authentication between the Patients app and the Interop partner's service.</span></span>

<span data-ttu-id="06c2e-137">アプリケーション間のアプリケーション認証モデルについては、次の説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06c2e-137">The Application to Application authentication model is described below:</span></span>

<span data-ttu-id="06c2e-138">サービス間認証は、OAuth 2.0 [クライアントの資格情報フロー](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)を通じて実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="06c2e-138">Service to service authentication should be done through OAuth 2.0 [Client Credential flow](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/).</span></span> <span data-ttu-id="06c2e-139">パートナーサービスは、次の情報を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="06c2e-139">The partner service needs to provide the following:</span></span>

1. <span data-ttu-id="06c2e-140">パートナーサービスは、患者アプリがパートナーとのアカウントを作成できるようにします。これにより、患者アプリは、パートナーの認証サーバー上の認証登録ポータルによって管理される client_id と client_secret を生成し、所有することができます。</span><span class="sxs-lookup"><span data-stu-id="06c2e-140">The Partner service enables the Patients app to create an account with the Partner, which enables the Patients app to generate and own client_id and client_secret, managed via an Auth registration portal on the partner's Authentication server.</span></span>
2. <span data-ttu-id="06c2e-141">パートナーサービスは、次に示すように、提供された認証/承認システムを所有しており、指定されたクライアントの資格情報を受け入れて検証 (認証) し、テナントヒントを含むアクセストークンを返します。</span><span class="sxs-lookup"><span data-stu-id="06c2e-141">The Partner service owns the Authentication/Authorization system, which accepts and verifies (authenticates) the client credentials provided and gives back an access token with tenant hint in scope, as described below.</span></span>
3. <span data-ttu-id="06c2e-142">セキュリティ上の理由により、または秘密の違反が発生した場合、患者アプリはシークレットを再生成し、古いシークレットを無効化または削除することができます (例として、Azure Portal で利用可能な場合)。</span><span class="sxs-lookup"><span data-stu-id="06c2e-142">For security reasons or in a case of a secret breach, the Patients app can re-generate the secret and invalidate or delete the old secret (example of the same is available in Azure Portal - AAD App Registration).</span></span>
4. <span data-ttu-id="06c2e-143">準拠ステートメントをホストしているメタデータエンドポイントは、認証トークンなしでアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="06c2e-143">The metadata endpoint hosting the conformance statement should be un-authenticated, it should be accessible without authentication token.</span></span>
5. <span data-ttu-id="06c2e-144">パートナーサービスは、患者アプリのトークンエンドポイントを提供し、クライアントの資格情報フローを使ってアクセストークンを要求します。</span><span class="sxs-lookup"><span data-stu-id="06c2e-144">The Partner service provides the token endpoint for the Patients app to request an access token using a client credential flow.</span></span> <span data-ttu-id="06c2e-145">次の例のように、認証サーバーごとのトークン url は、FHIR サーバーのメタデータから取得された、FHIR 準拠 (機能) ステートメントの一部である必要があります。</span><span class="sxs-lookup"><span data-stu-id="06c2e-145">The token url as per authorization server should be part of the FHIR conformance (capability) statement fetched from metadata on the FHIR server as in this example:</span></span>

* * *
    <span data-ttu-id="06c2e-146">{"resourceType": "CapabilityStatement"。</span><span class="sxs-lookup"><span data-stu-id="06c2e-146">{ "resourceType": "CapabilityStatement", .</span></span>
        <span data-ttu-id="06c2e-147">.</span><span class="sxs-lookup"><span data-stu-id="06c2e-147">.</span></span>
        <span data-ttu-id="06c2e-148">.</span><span class="sxs-lookup"><span data-stu-id="06c2e-148">.</span></span>
        <span data-ttu-id="06c2e-149">"rest": [{"mode": "server"、"security": {"extension": [{"extension": [{"url": "トークン", "valueUri": " https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/token "}, {"url": "承認", "valueUri": ""} "の" url ":" "}", "" {":" "," "{": " https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/authorize http://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris https://hl7.org/fhir/ValueSet/restful-security-service ", "code": [{]</span><span class="sxs-lookup"><span data-stu-id="06c2e-149">"rest": [ { "mode": "server", "security": { "extension": [ { "extension": [ { "url": "token", "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/token" }, { "url": "authorize", "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/authorize" } ], "url": "http://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris" } ], "service": [ { "coding": [ { "system": "https://hl7.org/fhir/ValueSet/restful-security-service", "code": "OAuth" } ] } ] }, .</span></span>
                <span data-ttu-id="06c2e-150">.</span><span class="sxs-lookup"><span data-stu-id="06c2e-150">.</span></span>
                <span data-ttu-id="06c2e-151">.</span><span class="sxs-lookup"><span data-stu-id="06c2e-151">.</span></span>
            <span data-ttu-id="06c2e-152">} ] }</span><span class="sxs-lookup"><span data-stu-id="06c2e-152">} ] }</span></span>

* * *

<span data-ttu-id="06c2e-153">アクセストークンの要求は、次のパラメーターで構成されます。</span><span class="sxs-lookup"><span data-stu-id="06c2e-153">A request for an access token consists of the following parameters:</span></span>

* * *

    <span data-ttu-id="06c2e-154">POST/token HTTP/1.1 Host: authorization-server.com</span><span class="sxs-lookup"><span data-stu-id="06c2e-154">POST /token HTTP/1.1 Host: authorization-server.com</span></span>

    <span data-ttu-id="06c2e-155">grant-type = client_credentials &client_id = xxxxxxxxxx &client_secret = xxxxxxxxxx</span><span class="sxs-lookup"><span data-stu-id="06c2e-155">grant-type=client_credentials &client_id=xxxxxxxxxx &client_secret=xxxxxxxxxx</span></span>

* * *

<span data-ttu-id="06c2e-156">パートナーサービスは、パートナー側の認証登録ポータルで管理されている、患者アプリの client_id と client_secret を提供します。</span><span class="sxs-lookup"><span data-stu-id="06c2e-156">The Partner service provides the client_id and client_secret for Patients app, managed via an Auth registration portal on the partner's side.</span></span> <span data-ttu-id="06c2e-157">パートナーサービスは、クライアントの資格情報フローを使用してアクセストークンを要求するエンドポイントを提供します。</span><span class="sxs-lookup"><span data-stu-id="06c2e-157">The Partner service provides the endpoint to request access token using a client credential flow.</span></span> <span data-ttu-id="06c2e-158">正常な応答には、token_type、access_token、expires_in の各パラメーターが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="06c2e-158">A successful response must include the token_type, access_token and expires_in parameters.</span></span>

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a><span data-ttu-id="06c2e-159">ルーティング: のプロバイダーエンドポイントへの AAD テナントのマッピング</span><span class="sxs-lookup"><span data-stu-id="06c2e-159">Routing: Mapping AAD Tenant to the Provider endpoint</span></span>

<span data-ttu-id="06c2e-160">患者アプリは、1つのエンドポイントを通じてパートナーサービスに接続します。</span><span class="sxs-lookup"><span data-stu-id="06c2e-160">The Patients app connects to a partner service through a single endpoint.</span></span> <span data-ttu-id="06c2e-161">パートナーサービスは、パートナーサービスが作業している各 Microsoft 顧客 (AAD テナント ID) をそれぞれの医療機関 (FHIR サーバー) にマップするメカニズムを所有し、管理します。</span><span class="sxs-lookup"><span data-stu-id="06c2e-161">The Partner service owns and maintains a mechanism to map each Microsoft customer (AAD Tenant ID) to a respective healthcare Provider (FHIR server) that the Partner service is working with.</span></span>

<span data-ttu-id="06c2e-162">AAD テナントをプロバイダーエンドポイントにマッピングすると、AAD テナント ID (GUID) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="06c2e-162">Mapping the AAD tenant to a provider endpoint uses the AAD Tenant ID (GUID).</span></span> <span data-ttu-id="06c2e-163">患者アプリは、各要求のアクセストークンを要求しながら、スコープ内でテナント ID を渡します。</span><span class="sxs-lookup"><span data-stu-id="06c2e-163">The Patients app passes the Tenant ID in scope, while requesting an access-token for each request.</span></span> <span data-ttu-id="06c2e-164">パートナーサービスは、テナント id とプロバイダーエンドポイントのマッピングを維持し、テナント ID に基づいて要求をプロバイダーエンドポイントにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="06c2e-164">The Partner service keeps the mapping of Tenant ID to Provider endpoint and redirects requests to a provider endpoint based on the Tenant ID.</span></span> <span data-ttu-id="06c2e-165">これを行うには、パートナーがエンドでの構成を (手動で、または、プロバイダ組織のオンボードから相互運用プラットフォームへの入り口の一部として) サポートします。</span><span class="sxs-lookup"><span data-stu-id="06c2e-165">To do this, the partner supports the configuration on their end (manually or via a portal as part of onboarding of provider organizations to their Interop Platform).</span></span>

<span data-ttu-id="06c2e-166">認証とルーティングのワークフローは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="06c2e-166">The Authentication and Routing workflow is shown below:</span></span>

![認証とルーティングワークフローの図](../../media/Patient-app-6.png)

1. <span data-ttu-id="06c2e-168">送信することにより、アプリアクセストークンを要求します。</span><span class="sxs-lookup"><span data-stu-id="06c2e-168">Request for app access token by sending:</span></span>
 
        {   grant_type: client_credentials,
            client_id: xxxxxx, 
            client_secret: xxxxxx,
            scope: {Provider Identifier, Ex: tenant ID}
        }

2. <span data-ttu-id="06c2e-169">アプリトークンを使って返信する:</span><span class="sxs-lookup"><span data-stu-id="06c2e-169">Reply with an app token:</span></span>

        {  access_token: {JWT, with scope: tenant ID},
           expires_in: 156678,
           token_type: "Bearer",
        }

3. <span data-ttu-id="06c2e-170">アクセストークンを使用して、保護されたデータを要求します。</span><span class="sxs-lookup"><span data-stu-id="06c2e-170">Request protected data with Access token.</span></span>
4. <span data-ttu-id="06c2e-171">承認メッセージ: 範囲内のテナント ID から適切な FHIR サーバーを選択してルーティングする</span><span class="sxs-lookup"><span data-stu-id="06c2e-171">Authorization message: Select the appropriate FHIR server to route to from tenant ID in scope</span></span>
5. <span data-ttu-id="06c2e-172">アプリトークンを使って認証した後、承認された FHIR サーバーからアプリの保護されたデータを送信します。</span><span class="sxs-lookup"><span data-stu-id="06c2e-172">Sends the app protected  data from the authorized FHIR server after authenticating with the app token.</span></span>

## <a name="interfaces"></a><span data-ttu-id="06c2e-173">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="06c2e-173">Interfaces</span></span>

<span data-ttu-id="06c2e-174">患者アプリで使用される特定の通話とフィールドについては、次の記事で説明します。</span><span class="sxs-lookup"><span data-stu-id="06c2e-174">Specific calls and fields used by the Patients app are documented in the following articles.</span></span> <span data-ttu-id="06c2e-175">FHIR サーバー/FHIR Api に適用可能なインターフェイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="06c2e-175">Select the interface applicable to your FHIR server/FHIR APIs.</span></span>

- [<span data-ttu-id="06c2e-176">DSTU2 インターフェイスの仕様</span><span class="sxs-lookup"><span data-stu-id="06c2e-176">DSTU2 interface specification</span></span>](dstu2-interface.md)
- [<span data-ttu-id="06c2e-177">STU3 インターフェイスの仕様</span><span class="sxs-lookup"><span data-stu-id="06c2e-177">STU3 interface specification</span></span>](stu3-interface.md)

## <a name="performance-and-reliability"></a><span data-ttu-id="06c2e-178">パフォーマンスと信頼性</span><span class="sxs-lookup"><span data-stu-id="06c2e-178">Performance and Reliability</span></span>

<span data-ttu-id="06c2e-179">患者のアプリはプライベートプレビュー版ですが、エンドツーエンドのパフォーマンスに保証はありません。</span><span class="sxs-lookup"><span data-stu-id="06c2e-179">While the Patients app is in private preview, there are no guarantees on the end-to-end performance.</span></span> <span data-ttu-id="06c2e-180">パフォーマンスの要因としては、正常性システムの環境内の EHR から、相互運用パートナーとそのインフラストラクチャ (FHIR サーバーを含む)、および Office 365 エコシステムと患者アプリまで、ワークフローに関連するすべてのホップの相対的な待ち時間が含まれます。</span><span class="sxs-lookup"><span data-stu-id="06c2e-180">Factors in performance include the relative latencies of all the hops involved in the workflow, starting from the EHR in the health system's environment, to the Interop partner and their infra, including the FHIR Server and across to the Office 365 ecosystem and Patients app.</span></span>

![相互運用パートナーのパフォーマンスの図](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a><span data-ttu-id="06c2e-182">FHIR の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="06c2e-182">Get started with FHIR</span></span>  

<span data-ttu-id="06c2e-183">FHIR を初めて使用して、Microsoft Teams の EHR 統合インターフェイスに公開できる FHIR サーバーに簡単にアクセスする必要がある場合は、Microsoft によって、すべての開発者が使用できるオープンソース FHIR サーバーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="06c2e-183">If you're new to FHIR and need easy access to a FHIR Server that you can expose to the Microsoft Teams EHR integration interface, Microsoft has an open-source FHIR Server available for all developers to use.</span></span> <span data-ttu-id="06c2e-184">Microsoft から提供されているオープンソース FHIR サーバーの詳細については、「 [Azure 用 FHIR サーバーとは](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) 」の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06c2e-184">Please see the [What is FHIR Server for Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) article to learn more about the open source FHIR Server available from Microsoft and deploy it for your organizations.</span></span>

<span data-ttu-id="06c2e-185">HSPC オープンサンドボックス EHR 環境を使用して、オープンな FHIR サーバーもサポートしている EHR を作成し、これを使って患者のアプリでプレイすることもできます。</span><span class="sxs-lookup"><span data-stu-id="06c2e-185">You can also use the HSPC Open sandbox EHR environment to create an an EHR which also supports an open FHIR Server and use this to play around with the Patients app.</span></span> <span data-ttu-id="06c2e-186">[Hspc サンドボックスのドキュメント](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox)をご覧になることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="06c2e-186">We recommend that you read through the [HSPC Sandbox documentation](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox).</span></span> <span data-ttu-id="06c2e-187">サンドボックスは、簡単で UI 指向であり、患者の作成、追加、編集を行うためのわかりやすい方法を提供するだけでなく、使用を開始するためのサンプルもいくつか提供しています。</span><span class="sxs-lookup"><span data-stu-id="06c2e-187">Not only does the sandbox provide an easy, UI oriented, and user friendly way of creating, adding and editing Patients, it also gives you several samples to get started.</span></span> 