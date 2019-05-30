---
title: Patients アプリの概要
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
ms.openlocfilehash: d2177e4201a1c7d7087a4c04ffffbbf52dd7366c
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548311"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a><span data-ttu-id="9717a-103">電子医療記録を Microsoft Teams に統合する</span><span class="sxs-lookup"><span data-stu-id="9717a-103">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)] 

<span data-ttu-id="9717a-104">プライベートプレビューに参加するには、「[プライベートプレビューに登録](#enroll-in-the-private-preview)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9717a-104">To participate in the private preview, see [Enroll in the private preview](#enroll-in-the-private-preview).</span></span>

<span data-ttu-id="9717a-105">この記事は、医療情報システム上で FHIR Api を使用して Microsoft Teams に接続することに関心を持っている一般的なヘルスケアの IT 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="9717a-105">This article is intended for a general healthcare IT developer interested in using FHIR APIs on top of a medical information system to connect to Microsoft Teams.</span></span> <span data-ttu-id="9717a-106">これにより、医療機関のニーズに合ったケアの調整シナリオが可能になります。</span><span class="sxs-lookup"><span data-stu-id="9717a-106">This would enable care coordination scenarios that match the needs of a healthcare organization.</span></span>

<span data-ttu-id="9717a-107">リンクされた記事ドキュメント「Microsoft Teams の患者」アプリの FHIR インターフェイスの仕様について説明し、以降のセクションでは、FHIR サーバーの設定と開発環境またはテナントでの患者アプリへの接続に必要なものについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9717a-107">Linked articles document the FHIR interface specifications for the Microsoft Teams Patients app, and following sections explain what is required for setting up a FHIR server and connecting to the Patients app in your development environment or tenant.</span></span> <span data-ttu-id="9717a-108">また、選択した FHIR サーバーのドキュメントについて理解している必要があります。これは、サポートされているオプションのいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9717a-108">You will also need to be familiar with the documentation of the FHIR server you have chosen, which must be one of the supported options:</span></span>
- <span data-ttu-id="9717a-109">Datica ( [CMI](https://datica.com/compliant-managed-integration/)サービス経由)</span><span class="sxs-lookup"><span data-stu-id="9717a-109">Datica (through their [CMI](https://datica.com/compliant-managed-integration/) offering)</span></span>
- <span data-ttu-id="9717a-110">Infor Cloverleaf ( [Infor FHIR ブリッジ](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html)経由)</span><span class="sxs-lookup"><span data-stu-id="9717a-110">Infor Cloverleaf (through the [Infor FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span></span>
- <span data-ttu-id="9717a-111">Redox ( [r ^ FHIR サーバ](https://www.redoxengine.com/fhir/)を経由)</span><span class="sxs-lookup"><span data-stu-id="9717a-111">Redox (through the [R^FHIR server](https://www.redoxengine.com/fhir/))</span></span>
- <span data-ttu-id="9717a-112">Dapasoft (の場合は、 [FHIR の](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/)場合)</span><span class="sxs-lookup"><span data-stu-id="9717a-112">Dapasoft (through [Corolar on FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span></span>

> [!NOTE]
> <span data-ttu-id="9717a-113">このプロセスには、Microsoft Teams 管理センターまたは PowerShell コマンドレットを使用して機能を有効にする手順は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="9717a-113">This process does not includes steps that use the Microsoft Teams admin center or PowerShell cmdlets to enable features.</span></span> <span data-ttu-id="9717a-114">構成は、FHIR サーバー/サービス側と患者のアプリクライアントで行われます。</span><span class="sxs-lookup"><span data-stu-id="9717a-114">The configuration is entirely done on the FHIR server/service side and in the Patients app client.</span></span>

<span data-ttu-id="9717a-115">次に、患者アプリのアーキテクチャを示します。</span><span class="sxs-lookup"><span data-stu-id="9717a-115">Illustrated below is the architecture of the Patients app:</span></span>

![患者のアプリアーキテクチャの図](../../media/patients-app-architecture.png)

<span data-ttu-id="9717a-117">以下のセクションでは、患者アプリと統合するために、FHIR server (または EHR が有効な FHIR Api) が満たす必要のある、FHIR 専用データアクセスレイヤーの要件について説明します。これには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9717a-117">The following sections explain the requirements of the FHIR-only data access layer for the Patients app that a FHIR server (or EHR enabled FHIR APIs) must meet in order to integrate with the Patients app, including the following:</span></span>

- <span data-ttu-id="9717a-118">ユーザー認証に関する期待</span><span class="sxs-lookup"><span data-stu-id="9717a-118">Expectations around user authentication</span></span>
- <span data-ttu-id="9717a-119">統合インターフェイスの機能と技術の要件</span><span class="sxs-lookup"><span data-stu-id="9717a-119">Functional and technical requirements of the integration interface</span></span>
- <span data-ttu-id="9717a-120">パフォーマンスと信頼性に関する期待</span><span class="sxs-lookup"><span data-stu-id="9717a-120">Expectations around performance and reliability</span></span>
- <span data-ttu-id="9717a-121">患者アプリでサポートされる FHIR リソースに対する期待</span><span class="sxs-lookup"><span data-stu-id="9717a-121">Expectations around FHIR resources to be supported for the Patients app</span></span>
- <span data-ttu-id="9717a-122">統合のプロセスと想定される契約モデル</span><span class="sxs-lookup"><span data-stu-id="9717a-122">Process for integration and the expected engagement model</span></span>
- <span data-ttu-id="9717a-123">患者アプリのプライベートプレビューで自分と顧客を登録する方法</span><span class="sxs-lookup"><span data-stu-id="9717a-123">How to enroll yourself and your customer in the private preview of the Patients app</span></span>
- <span data-ttu-id="9717a-124">FHIR の使用を開始する方法と、患者アプリで直面する一般的な課題</span><span class="sxs-lookup"><span data-stu-id="9717a-124">How to get started with FHIR and some common challenges faced with the Patients app</span></span>
- <span data-ttu-id="9717a-125">患者アプリの次回のイテレーションに関する将来の要件</span><span class="sxs-lookup"><span data-stu-id="9717a-125">Future requirements for the next iteration of the Patients app</span></span>

> [!NOTE]
> <span data-ttu-id="9717a-126">以下のセクションでは、"パートナー" または "相互運用パートナー" という単語を使用して、患者アプリの EHR システムと FHIR の統合を可能にするサードパーティ組織を参照しています。また、リストされている仕様に合わせて FHIR サーバーが実装されています。</span><span class="sxs-lookup"><span data-stu-id="9717a-126">In the following sections, the word "partner" or "Interop partner" is used to refer to any 3rd party Organization that enables integration to EHR systems for the Patients app through FHIR and is implementing a FHIR Server to match the listed specifications.</span></span>

## <a name="functional-and-technical-requirements"></a><span data-ttu-id="9717a-127">機能と技術の要件</span><span class="sxs-lookup"><span data-stu-id="9717a-127">Functional and technical requirements</span></span>  

### <a name="authentication"></a><span data-ttu-id="9717a-128">認証</span><span class="sxs-lookup"><span data-stu-id="9717a-128">Authentication</span></span>  

<span data-ttu-id="9717a-129">*ユーザーレベルの承認をサポートしていない*アプリレベルの承認は、ehr システムでユーザーレベルの承認が実装されている場合でも、データ変換を実行し、ehr データへの接続を公開するための、より一般的にサポートされている方法です。.</span><span class="sxs-lookup"><span data-stu-id="9717a-129">App-level authorization *with no support for user level authorization* is the more commonly supported way to perform data transformations and expose connections to EHR data through FHIR, even though the EHR system might implement user level authorization.</span></span> <span data-ttu-id="9717a-130">相互運用サービス (パートナー) は、EHR データへのアクセス権を昇格させ、そのデータを適切な FHIR リソースとして公開すると、相互運用サービスコンシューマー (患者アプリ) に対して認証コンテキストが渡されることはありません。サービスまたはプラットフォーム。</span><span class="sxs-lookup"><span data-stu-id="9717a-130">The Interop Service (Partner) gets elevated access to the EHR data, and when they expose the same data as the appropriate FHIR resources there is no authorization context passed on to the Interop Service Consumer (the Patients app) integrating with the Interop Service or Platform.</span></span> <span data-ttu-id="9717a-131">患者のアプリでは、ユーザーレベルの承認を強制することはできませんが、患者のアプリと相互運用パートナーのサービス間でのアプリケーションの認証をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="9717a-131">The Patients app will not be able to enforce user level authorization, but does support application to application authentication between the Patients app and the Interop partner’s service.</span></span>

<span data-ttu-id="9717a-132">アプリケーション間のアプリケーション認証モデルについては、次の説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9717a-132">The Application to Application authentication model is described below:</span></span>

<span data-ttu-id="9717a-133">サービス間認証は、OAuth 2.0[クライアントの資格情報フロー](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)を通じて実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9717a-133">Service to service authentication should be done through OAuth 2.0 [Client Credential flow](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/).</span></span> <span data-ttu-id="9717a-134">パートナーサービスは、次の情報を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9717a-134">The partner service needs to provide the following:</span></span>

1. <span data-ttu-id="9717a-135">パートナーサービスは、患者アプリがパートナーとのアカウントを作成できるようにします。これにより、患者アプリは、パートナーの認証サーバー上の認証登録ポータルを通じて管理される client_id と client_secret を生成し、所有することができます。</span><span class="sxs-lookup"><span data-stu-id="9717a-135">The Partner service enables the Patients app to create an account with the Partner, which  enables the Patients app to generate and own client_id and client_secret, managed via an Auth registration portal on the partner’s Authentication server.</span></span>
2. <span data-ttu-id="9717a-136">パートナーサービスは、次に示すように、提供された認証/承認システムを所有しており、指定されたクライアントの資格情報を受け入れて検証 (認証) し、テナントヒントを含むアクセストークンを返します。</span><span class="sxs-lookup"><span data-stu-id="9717a-136">The Partner service owns the Authentication/Authorization system, which   accepts and verifies (authenticates) the client credentials provided and gives back an access token with tenant hint in scope, as described below.</span></span>
3. <span data-ttu-id="9717a-137">セキュリティ上の理由により、または秘密の違反が発生した場合、患者アプリは秘密を再生成し、古いシークレットを無効化または削除することができます (例: Azure Portal で利用可能な場合)。</span><span class="sxs-lookup"><span data-stu-id="9717a-137">For security reasons or in a case of a secret breach, the Patients app can re-generate the secret and invalidate or delete the old secret (Example of the same is available in Azure Portal - AAD App Registration)</span></span>
4. <span data-ttu-id="9717a-138">準拠ステートメントをホストしているメタデータエンドポイントは、認証トークンなしでアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="9717a-138">The metadata endpoint hosting the conformance statement should be un-authenticated, it should be accessible without authentication token.</span></span>
5. <span data-ttu-id="9717a-139">パートナーサービスは、患者アプリのトークンエンドポイントを提供し、クライアントの資格情報フローを使ってアクセストークンを要求します。</span><span class="sxs-lookup"><span data-stu-id="9717a-139">The Partner service provides the token endpoint for the Patients app to request an access token using a client credential flow.</span></span> <span data-ttu-id="9717a-140">次の例のように、認証サーバーごとのトークン url は、FHIR サーバーのメタデータから取得された、FHIR 準拠 (機能) ステートメントの一部である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9717a-140">The token url as per authorization server should be part of the FHIR conformance (capability) statement fetched from metadata on the FHIR server as in this example:</span></span>

![コードサンプルのトークン URL のスクリーンショット](../../media/Patient-app-5.png)

<span data-ttu-id="9717a-142">アクセストークンの要求は、次のパラメーターで構成されます。</span><span class="sxs-lookup"><span data-stu-id="9717a-142">A request for an access token consists of the following parameters:</span></span>

* * *

    <span data-ttu-id="9717a-143">POST/token HTTP/1.1 Host: authorization-server.com</span><span class="sxs-lookup"><span data-stu-id="9717a-143">POST /token HTTP/1.1 Host: authorization-server.com</span></span>

    <span data-ttu-id="9717a-144">grant-type = client_credentials &client_id = xxxxxxxxxx &client_secret = xxxxxxxxxx</span><span class="sxs-lookup"><span data-stu-id="9717a-144">grant-type=client_credentials &client_id=xxxxxxxxxx &client_secret=xxxxxxxxxx</span></span>

* * *

<span data-ttu-id="9717a-145">パートナーサービスは、パートナーの側の認証登録ポータルで管理されている、client_id と client_secret の患者アプリを提供します。</span><span class="sxs-lookup"><span data-stu-id="9717a-145">The Partner service provides the client_id and client_secret for Patients app, managed via an Auth registration portal on the partner’s side.</span></span> <span data-ttu-id="9717a-146">パートナーサービスは、クライアントの資格情報フローを使用してアクセストークンを要求するエンドポイントを提供します。</span><span class="sxs-lookup"><span data-stu-id="9717a-146">The Partner service provides the endpoint to request access token using a client credential flow.</span></span> <span data-ttu-id="9717a-147">成功応答には、token_type、access_token、expires_in の各パラメーターが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9717a-147">A successful response must include the token_type, access_token and expires_in parameters.</span></span>

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a><span data-ttu-id="9717a-148">ルーティング: のプロバイダーエンドポイントへの AAD テナントのマッピング</span><span class="sxs-lookup"><span data-stu-id="9717a-148">Routing: Mapping AAD Tenant to the Provider endpoint</span></span>

<span data-ttu-id="9717a-149">患者アプリは、1つのエンドポイントを通じてパートナーサービスに接続します。</span><span class="sxs-lookup"><span data-stu-id="9717a-149">The Patients app connects to a partner service through a single endpoint.</span></span> <span data-ttu-id="9717a-150">パートナーサービスは、パートナーサービスが作業している各 Microsoft 顧客 (AAD テナント ID) をそれぞれの医療機関 (FHIR サーバー) にマップするメカニズムを所有し、管理します。</span><span class="sxs-lookup"><span data-stu-id="9717a-150">The Partner service owns and maintains a mechanism to map each Microsoft customer (AAD Tenant ID) to a respective healthcare Provider (FHIR server) that the Partner service is working with.</span></span>

<span data-ttu-id="9717a-151">AAD テナントをプロバイダーエンドポイントにマッピングすると、AAD テナント ID (GUID) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="9717a-151">Mapping the AAD tenant to a provider endpoint uses the AAD Tenant ID (GUID).</span></span> <span data-ttu-id="9717a-152">患者アプリは、各要求のアクセストークンを要求しながら、スコープ内でテナント ID を渡します。</span><span class="sxs-lookup"><span data-stu-id="9717a-152">The Patients app passes the Tenant ID in scope, while requesting an access-token for each request.</span></span> <span data-ttu-id="9717a-153">パートナーサービスは、テナント id とプロバイダーエンドポイントのマッピングを維持し、テナント ID に基づいて要求をプロバイダーエンドポイントにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="9717a-153">The Partner service keeps the mapping of Tenant ID to Provider endpoint and redirects requests to a provider endpoint based on the Tenant ID.</span></span> <span data-ttu-id="9717a-154">これを行うには、パートナーがエンドでの構成を (手動で、または、プロバイダ組織のオンボードから相互運用プラットフォームへの入り口の一部として) サポートします。</span><span class="sxs-lookup"><span data-stu-id="9717a-154">To do this, the partner supports the configuration on their end (manually or via a portal as part of onboarding of provider organizations to their Interop Platform).</span></span>

<span data-ttu-id="9717a-155">認証とルーティングのワークフローは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9717a-155">The Authentication and Routing workflow is shown below:</span></span>

![認証とルーティングワークフローの図](../../media/Patient-app-6.png)

1. <span data-ttu-id="9717a-157">送信することにより、アプリアクセストークンを要求します。</span><span class="sxs-lookup"><span data-stu-id="9717a-157">Request for app access token by sending:</span></span>
 
        {   grant_type: client_credentials,
            client_id: xxxxxx, 
            client_secret: xxxxxx,
            scope: {Provider Identifier, Ex: tenant ID}
        }

2. <span data-ttu-id="9717a-158">アプリトークンを使って返信する:</span><span class="sxs-lookup"><span data-stu-id="9717a-158">Reply with an app token:</span></span>

        {  access_token: {JWT, with scope: tenant ID},
           expires_in: 156678,
           token_type: "Bearer",
        }

3. <span data-ttu-id="9717a-159">アクセストークンを使用して、保護されたデータを要求します。</span><span class="sxs-lookup"><span data-stu-id="9717a-159">Request protected data with Access token.</span></span>
4. <span data-ttu-id="9717a-160">承認メッセージ: 範囲内のテナント ID から適切な FHIR サーバーを選択してルーティングする</span><span class="sxs-lookup"><span data-stu-id="9717a-160">Authorization message: Select the appropriate FHIR server to route to from tenant ID in scope</span></span>
5. <span data-ttu-id="9717a-161">アプリトークンを使って認証した後、承認された FHIR サーバーからアプリの保護されたデータを送信します。</span><span class="sxs-lookup"><span data-stu-id="9717a-161">Sends the app protected  data from the authorized FHIR server after authenticating with the app token.</span></span>

## <a name="interfaces"></a><span data-ttu-id="9717a-162">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9717a-162">Interfaces</span></span>

<span data-ttu-id="9717a-163">患者アプリで使用される特定の通話とフィールドについては、次の記事で説明します。</span><span class="sxs-lookup"><span data-stu-id="9717a-163">Specific calls and fields used by the Patients app are documented in the following articles.</span></span> <span data-ttu-id="9717a-164">FHIR サーバー/FHIR Api に適用可能なインターフェイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="9717a-164">Select the interface applicable to your FHIR server/FHIR APIs.</span></span>

- [<span data-ttu-id="9717a-165">DSTU2 インターフェイスの仕様</span><span class="sxs-lookup"><span data-stu-id="9717a-165">DSTU2 interface specification</span></span>](dstu2-interface.md)
- [<span data-ttu-id="9717a-166">STU3 インターフェイスの仕様</span><span class="sxs-lookup"><span data-stu-id="9717a-166">STU3 interface specification</span></span>](stu3-interface.md)

## <a name="performance-and-reliability"></a><span data-ttu-id="9717a-167">パフォーマンスと信頼性</span><span class="sxs-lookup"><span data-stu-id="9717a-167">Performance and Reliability</span></span>

<span data-ttu-id="9717a-168">患者のアプリはプライベートプレビュー版ですが、エンドツーエンドのパフォーマンスに保証はありません。</span><span class="sxs-lookup"><span data-stu-id="9717a-168">While the Patients app is in private preview, there are no guarantees on the end-to-end performance.</span></span> <span data-ttu-id="9717a-169">パフォーマンスの要因としては、正常性システムの環境内の EHR から、相互運用性パートナーとそのインフラストラクチャ (FHIR サーバーを含む)、および Office 365 エコシステムを含む、ワークフローに関連するすべてのホップの相対的な待ち時間が含まれます。患者アプリ。</span><span class="sxs-lookup"><span data-stu-id="9717a-169">Factors in performance include the relative latencies of all the hops involved in the workflow, starting from the EHR in the health system's environment, to the Interop partner and their infra, including the FHIR Server and across to the Office 365 ecosystem and Patients app.</span></span>

![相互運用パートナーのパフォーマンスの図](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a><span data-ttu-id="9717a-171">FHIR の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="9717a-171">Get started with FHIR</span></span>  

<span data-ttu-id="9717a-172">FHIR を初めて使用して、Microsoft Teams の EHR 統合インターフェイスに公開できる FHIR サーバーに簡単にアクセスする必要がある場合は、Microsoft によって、すべての開発者が使用できるオープンソース FHIR サーバーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="9717a-172">If you're new to FHIR and need easy access to a FHIR Server that you can expose to the Microsoft Teams EHR integration interface, Microsoft has an open-source FHIR Server available for all developers to use.</span></span> <span data-ttu-id="9717a-173">Microsoft から提供されているオープンソース FHIR サーバーの詳細については、「 [Azure 用 FHIR サーバーとは](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server)」の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9717a-173">Please see the [What is FHIR Server for Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) article to learn more about the open source FHIR Server available from Microsoft and deploy it for your organizations.</span></span>

<span data-ttu-id="9717a-174">HSPC オープンサンドボックス EHR 環境を使用して、オープンな FHIR サーバーもサポートしている EHR を作成し、これを使って患者のアプリでプレイすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9717a-174">You can also use the HSPC Open sandbox EHR environment to create an an EHR which also supports an open FHIR Server and use this to play around with the Patients app.</span></span> <span data-ttu-id="9717a-175">[Hspc サンドボックスのドキュメント](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox)をご覧になることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9717a-175">We recommend that you read through the [HSPC Sandbox documentation](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox).</span></span> <span data-ttu-id="9717a-176">サンドボックスは、簡単で UI 指向であり、患者の作成、追加、編集を行うためのわかりやすい方法を提供するだけでなく、使用を開始するためのサンプルもいくつか提供しています。</span><span class="sxs-lookup"><span data-stu-id="9717a-176">Not only does the sandbox provide an easy, UI oriented, and user friendly way of creating, adding and editing Patients, it also gives you several samples to get started.</span></span>  

## <a name="enroll-in-the-private-preview"></a><span data-ttu-id="9717a-177">プライベートプレビューに登録する</span><span class="sxs-lookup"><span data-stu-id="9717a-177">Enroll in the private preview</span></span>

<span data-ttu-id="9717a-178">オープンソース FHIR サーバーを作成した後は、次の手順に従って、テナント内の患者アプリに簡単に接続できます。</span><span class="sxs-lookup"><span data-stu-id="9717a-178">Once you've created the open source FHIR Server, it's really easy to connect to the Patients app inside of your tenant by following the steps mentioned below:</span></span>

1. <span data-ttu-id="9717a-179">以下の最初の詳細をご確認[ください](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20private%20preview)。</span><span class="sxs-lookup"><span data-stu-id="9717a-179">[Contact us](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20private%20preview) with the following initial details:</span></span>  
    - <span data-ttu-id="9717a-180">お名前 \*</span><span class="sxs-lookup"><span data-stu-id="9717a-180">Your Name</span></span>
    - <span data-ttu-id="9717a-181">自分の位置</span><span class="sxs-lookup"><span data-stu-id="9717a-181">Your Position</span></span>
    - <span data-ttu-id="9717a-182">代表する会社または組織</span><span class="sxs-lookup"><span data-stu-id="9717a-182">The company or organization you represent</span></span>
    - <span data-ttu-id="9717a-183">EHR との統合のための患者アプリに関心を持っている理由</span><span class="sxs-lookup"><span data-stu-id="9717a-183">Why you are interested in the Patients app for EHR integration</span></span>

    <span data-ttu-id="9717a-184">さらに多くの質問がある場合は、すぐにお客様にご連絡いたします。また、プライベートプレビュー用にセットアップする手順についてもご案内します。</span><span class="sxs-lookup"><span data-stu-id="9717a-184">We will get back to you as soon as possible with more questions and guide you through a process to get set up for the private preview.</span></span>

2. <span data-ttu-id="9717a-185">患者のアプリを試すテナントで、カスタムアプリのサイドローディングが有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9717a-185">Ensure that sideloading of custom apps is enabled in the tenant where you are going to try out the Patients app.</span></span> <span data-ttu-id="9717a-186">この機能を Teams 管理センターからお客様のテナントに対して有効にする方法については、「[アプリのアクセス許可ポリシー](../../admin-settings.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9717a-186">Please refer to [App permission policies](../../admin-settings.md) to learn how to turn this on from the Teams Admin center for your or your customer's tenant.</span></span>

3. <span data-ttu-id="9717a-187">サイドローディングは、ケアと患者の丸めのシナリオで使用されるテナント内のチームに、Microsoft から取得する患者のアプリマニフェストを示しています (メールを処理した後)。</span><span class="sxs-lookup"><span data-stu-id="9717a-187">Sideload the Patients app manifest that you will get from Microsoft (after we process your email to us) into a team in the tenant that is going to be used for care-coordination and patient rounding scenarios.</span></span> <span data-ttu-id="9717a-188">アプリのサイドロードの詳細な手順については、「[アプリパッケージを Microsoft Teams にアップロード](/microsoftteams/platform/concepts/apps/apps-upload)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9717a-188">Detailed instructions around how to side-load an app are in [Upload an app package to Microsoft Teams](/microsoftteams/platform/concepts/apps/apps-upload)</span></span>

4. <span data-ttu-id="9717a-189">チーム所有者として [全般] チャネルに移動し、[患者] タブをクリックします。次に、EHR モードと手動モードの2つのオプションが表示される最初の実行環境が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9717a-189">Navigate to the general channel as the Team owner and then click on the Patients tab. You should see a first run experience that will present two options i.e. EHR Mode and Manual Mode.</span></span> <span data-ttu-id="9717a-190">[EHR]**モード**を選び、Fhir サーバーのエンドポイント (前述の仕様に含まれているすべての必要なデータとリソースが前に設定されています) を Link フィールドにコピーして、その接続に FHIR サーバーを表す名前を付けてください。</span><span class="sxs-lookup"><span data-stu-id="9717a-190">Please select the **EHR mode** and copy the FHIR Server endpoint (that you've just setup earlier with all the required data and resources per the specifications above) into the Link field and give the connection a name that well represents the FHIR Server.</span></span> <span data-ttu-id="9717a-191">[接続] をクリックすると、すべての機能を使い始めることができます。</span><span class="sxs-lookup"><span data-stu-id="9717a-191">Click on Connect, and everything should be ready to go.</span></span>

    ![患者のアプリのサーバー設定のスクリーンショット](../../media/patients-server.png)

5. <span data-ttu-id="9717a-193">このアプリを使って FHIR サーバー/EHR から患者を検索し、それをリストに追加して、問題が解決しない場合は[フィードバック](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20feedback)を送信してください。</span><span class="sxs-lookup"><span data-stu-id="9717a-193">Start using the app to search for Patients from the FHIR Server/EHR and add them to a list and please [give us feedback](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20feedback) if something doesn't work.</span></span> <span data-ttu-id="9717a-194">また、患者の > FHIR サーバーフローの完全認証バージョンを確立するには、前に説明したメール要求を通じて、Microsoft Teams for the 医療製品エンジニアリングのオフライン操作を行ってください。この機能を有効にするには、FHIR インターフェイスドキュメントで説明した認証要件に従ってください。</span><span class="sxs-lookup"><span data-stu-id="9717a-194">Also, to establish a fully authenticated version of the Patients app -> FHIR Server flow, please engage in offline dialogue with Microsoft Teams for healthcare product engineering, through the email request mentioned earlier to clarify requirements and we will help enable this for you per the Authentication requirements described above in the FHIR Interface document.</span></span>  


