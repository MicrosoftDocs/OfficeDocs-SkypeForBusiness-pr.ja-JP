---
title: 患者アプリケーションの概要
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
ms.openlocfilehash: f157061666dc72a8420b9b9331387b42d6918cea
ms.sourcegitcommit: b2acf18ba6487154ebb4ee46938e96dc56cb2c9a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2019
ms.locfileid: "33865039"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a><span data-ttu-id="4ac00-103">電子医療記録を Microsoft Teams に統合する</span><span class="sxs-lookup"><span data-stu-id="4ac00-103">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)] 

<span data-ttu-id="4ac00-104">プライベート プレビューに参加するには、[プライベートのプレビューでの登録](#enroll-in-the-private-preview)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ac00-104">To participate in the private preview, see [Enroll in the private preview](#enroll-in-the-private-preview).</span></span>

<span data-ttu-id="4ac00-105">この資料は、一般的な医療情報の IT 開発者がマイクロソフトのチームに接続するための医療情報システムの上に FHIR Api を使用する必要です。</span><span class="sxs-lookup"><span data-stu-id="4ac00-105">This article is intended for a general healthcare IT developer interested in using FHIR APIs on top of a medical information system to connect to Microsoft Teams.</span></span> <span data-ttu-id="4ac00-106">これは、結果、医療機関のニーズに合ったケア調整シナリオです。</span><span class="sxs-lookup"><span data-stu-id="4ac00-106">This would enable care coordination scenarios that match the needs of a healthcare organization.</span></span>

<span data-ttu-id="4ac00-107">リンク先の記事がチーム患者の Microsoft アプリケーションでは、FHIR インターフェイスの仕様を文書化し、次のセクションでは、FHIR サーバーをセットアップして、開発環境またはテナントで患者のアプリケーションへの接続に必要なものについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4ac00-107">Linked articles document the FHIR interface specifications for the Microsoft Teams Patients app, and following sections explain what is required for setting up a FHIR server and connecting to the Patients app in your development environment or tenant.</span></span> <span data-ttu-id="4ac00-108">必要を理解するを選択したら、FHIR のサーバのマニュアル、サポートされているオプションのいずれかでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="4ac00-108">You will also need to be familiar with the documentation of the FHIR server you have chosen, which must be one of the supported options:</span></span>
- <span data-ttu-id="4ac00-109">を通じて自社の[CMI](https://datica.com/compliant-managed-integration/)製品) Datica</span><span class="sxs-lookup"><span data-stu-id="4ac00-109">Datica (through their [CMI](https://datica.com/compliant-managed-integration/) offering)</span></span>
- <span data-ttu-id="4ac00-110">情報のクローバー型インターチェンジを[避けます FHIR ブリッジ](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span><span class="sxs-lookup"><span data-stu-id="4ac00-110">Infor Cloverleaf (through the [Infor FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span></span>
- <span data-ttu-id="4ac00-111">Redox (を通じて、 [R ^ FHIR server](https://www.redoxengine.com/fhir/))</span><span class="sxs-lookup"><span data-stu-id="4ac00-111">Redox (through the [R^FHIR server](https://www.redoxengine.com/fhir/))</span></span>
- <span data-ttu-id="4ac00-112">( [FHIR の Corolar](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/)) から Dapasoft</span><span class="sxs-lookup"><span data-stu-id="4ac00-112">Dapasoft (through [Corolar on FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span></span>

> [!NOTE]
> <span data-ttu-id="4ac00-113">このプロセスは、マイクロソフトのチーム管理センターまたは PowerShell コマンドレットを使用して、機能を有効にする手順を含んでいません。</span><span class="sxs-lookup"><span data-stu-id="4ac00-113">This process does not includes steps that use the Microsoft Teams admin center or PowerShell cmdlets to enable features.</span></span> <span data-ttu-id="4ac00-114">構成は、サーバーまたはサービス側で FHIR と患者のアプリケーション クライアントでのみ行われます。</span><span class="sxs-lookup"><span data-stu-id="4ac00-114">The configuration is entirely done on the FHIR server/service side and in the Patients app client.</span></span>

<span data-ttu-id="4ac00-115">患者アプリケーションのアーキテクチャは、次に示します。</span><span class="sxs-lookup"><span data-stu-id="4ac00-115">Illustrated below is the architecture of the Patients app:</span></span>

![患者のアプリケーション アーキテクチャ](../../media/patients-app-architecture.png)

<span data-ttu-id="4ac00-117">次に、FHIR 専用データ アクセス層の患者のアプリケーションの要件について説明する FHIR サーバー (または、EHR は、FHIR Api を有効になって) 次を含む、患者のアプリケーションと統合するために満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ac00-117">The following sections explain the requirements of the FHIR-only data access layer for the Patients app that a FHIR server (or EHR enabled FHIR APIs) must meet in order to integrate with the Patients app, including the following:</span></span>

- <span data-ttu-id="4ac00-118">ユーザー認証に関する要望</span><span class="sxs-lookup"><span data-stu-id="4ac00-118">Expectations around user authentication</span></span>
- <span data-ttu-id="4ac00-119">統合インターフェイスの機能および技術の要件</span><span class="sxs-lookup"><span data-stu-id="4ac00-119">Functional and technical requirements of the integration interface</span></span>
- <span data-ttu-id="4ac00-120">パフォーマンスと信頼性に関する要望</span><span class="sxs-lookup"><span data-stu-id="4ac00-120">Expectations around performance and reliability</span></span>
- <span data-ttu-id="4ac00-121">患者のアプリケーションをサポートする FHIR リソースを期待</span><span class="sxs-lookup"><span data-stu-id="4ac00-121">Expectations around FHIR resources to be supported for the Patients app</span></span>
- <span data-ttu-id="4ac00-122">プロセスを統合し、必要な活動モデル</span><span class="sxs-lookup"><span data-stu-id="4ac00-122">Process for integration and the expected engagement model</span></span>
- <span data-ttu-id="4ac00-123">自分自身と患者のアプリケーションのプライベートのプレビューで、顧客を登録する方法</span><span class="sxs-lookup"><span data-stu-id="4ac00-123">How to enroll yourself and your customer in the private preview of the Patients app</span></span>
- <span data-ttu-id="4ac00-124">FHIR と患者のアプリケーションに直面したいくつかの一般的な課題を開始する方法</span><span class="sxs-lookup"><span data-stu-id="4ac00-124">How to get started with FHIR and some common challenges faced with the Patients app</span></span>
- <span data-ttu-id="4ac00-125">患者アプリケーションの次のイテレーションの将来的な要件</span><span class="sxs-lookup"><span data-stu-id="4ac00-125">Future requirements for the next iteration of the Patients app</span></span>

> [!NOTE]
> <span data-ttu-id="4ac00-126">次のセクションでは、単語「partner」または「相互運用パートナー」ために、サードパーティ製の FHIR を通じて患者アプリの EHR システムに統合し、一覧表示されている仕様と一致する FHIR サーバーの実装組織を参照していますください。</span><span class="sxs-lookup"><span data-stu-id="4ac00-126">In the following sections, the word "partner" or "Interop partner" is used to refer to any 3rd party Organization that enables integration to EHR systems for the Patients app through FHIR and is implementing a FHIR Server to match the listed specifications.</span></span>

## <a name="functional-and-technical-requirements"></a><span data-ttu-id="4ac00-127">機能および技術要件</span><span class="sxs-lookup"><span data-stu-id="4ac00-127">Functional and technical requirements</span></span>  

### <a name="authentication"></a><span data-ttu-id="4ac00-128">認証</span><span class="sxs-lookup"><span data-stu-id="4ac00-128">Authentication</span></span>  

<span data-ttu-id="4ac00-129">アプリケーション レベルの認証*とユーザー レベルの認証はサポートされていません*より一般的にサポートされているデータの変換を実行し、FHIR を使用して EHR データへの接続を公開する方法も、EHR システムは、ユーザー レベルの認証を実装可能性があります。.</span><span class="sxs-lookup"><span data-stu-id="4ac00-129">App-level authorization *with no support for user level authorization* is the more commonly supported way to perform data transformations and expose connections to EHR data through FHIR, even though the EHR system might implement user level authorization.</span></span> <span data-ttu-id="4ac00-130">相互運用性サービス (パートナー) は、相互運用機能との統合 EHR データ、および相互運用機能サービスの利用者 (患者のアプリケーション) に渡される認証コンテキストがありません FHIR、適切なリソースと同じデータを公開するときに管理者特権へのアクセスを取得します。サービスまたはプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="4ac00-130">The Interop Service (Partner) gets elevated access to the EHR data, and when they expose the same data as the appropriate FHIR resources there is no authorization context passed on to the Interop Service Consumer (the Patients app) integrating with the Interop Service or Platform.</span></span> <span data-ttu-id="4ac00-131">患者のアプリケーションはユーザー レベルの認証を強制することはできませんが、患者のアプリケーションと相互運用機能のパートナーのサービスの間でのアプリケーションの認証をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="4ac00-131">The Patients app will not be able to enforce user level authorization, but does support application to application authentication between the Patients app and the Interop partner’s service.</span></span>

<span data-ttu-id="4ac00-132">アプリケーションの認証モデルは、以下に示します。</span><span class="sxs-lookup"><span data-stu-id="4ac00-132">The Application to Application authentication model is described below:</span></span>

<span data-ttu-id="4ac00-133">サービス サービスの認証を行うには、OAuth 2.0 の[クライアントの資格情報のフロー](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)。</span><span class="sxs-lookup"><span data-stu-id="4ac00-133">Service to service authentication should be done through OAuth 2.0 [Client Credential flow](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/).</span></span> <span data-ttu-id="4ac00-134">パートナー サービスは、次を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ac00-134">The partner service needs to provide the following:</span></span>

1. <span data-ttu-id="4ac00-135">パートナー サービスは、パートナー、患者、アプリケーションの生成を有効にして独自の client_id と client_secret、管理パートナーの認証サーバー上の認証登録ポータル経由でアカウントを作成するのには患者のアプリケーションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4ac00-135">The Partner service enables the Patients app to create an account with the Partner, which  enables the Patients app to generate and own client_id and client_secret, managed via an Auth registration portal on the partner’s Authentication server.</span></span>
2. <span data-ttu-id="4ac00-136">パートナー サービスを受け取り、検証、認証システムを所有している (認証) クライアントが資格情報を提供し、提供、アクセス トークンのスコープ内のテナントのヒントを次のようにします。</span><span class="sxs-lookup"><span data-stu-id="4ac00-136">The Partner service owns the Authentication/Authorization system, which   accepts and verifies (authenticates) the client credentials provided and gives back an access token with tenant hint in scope, as described below.</span></span>
3. <span data-ttu-id="4ac00-137">セキュリティ上の理由または秘密の侵害の場合に、患者アプリケーション シークレットを再生成しを無効にしたり削除したりできます (同じ例は、Azure ポータルの AAD アプリケーションの登録で利用可能な) 古いシークレット</span><span class="sxs-lookup"><span data-stu-id="4ac00-137">For security reasons or in a case of a secret breach, the Patients app can re-generate the secret and invalidate or delete the old secret (Example of the same is available in Azure Portal - AAD App Registration)</span></span>
4. <span data-ttu-id="4ac00-138">適合に関する声明をホストしているメタデータのエンドポイントは thenticated を解除する必要があります、認証トークンにアクセス可能な場合があります。</span><span class="sxs-lookup"><span data-stu-id="4ac00-138">The metadata endpoint hosting the conformance statement should be un-authenticated, it should be accessible without authentication token.</span></span>
5. <span data-ttu-id="4ac00-139">パートナー サービスは、クライアント資格情報のフローを使用してアクセス トークンを要求する患者のアプリケーションのトークンのエンドポイントを提供します。</span><span class="sxs-lookup"><span data-stu-id="4ac00-139">The Partner service provides the token endpoint for the Patients app to request an access token using a client credential flow.</span></span> <span data-ttu-id="4ac00-140">承認サーバーにトークンの url は、この例のように FHIR サーバー上のメタデータのフェッチ、FHIR 準拠 (機能) のステートメントの一部にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ac00-140">The token url as per authorization server should be part of the FHIR conformance (capability) statement fetched from metadata on the FHIR server as in this example:</span></span>

![患者アプリ 5](../../media/Patient-app-5.png)

<span data-ttu-id="4ac00-142">アクセス トークンの要求は、次のパラメーターで構成されます。</span><span class="sxs-lookup"><span data-stu-id="4ac00-142">A request for an access token consists of the following parameters:</span></span>

* * *

    <span data-ttu-id="4ac00-143">投稿/token/で HTTP 1.1 ホスト: 承認 server.com</span><span class="sxs-lookup"><span data-stu-id="4ac00-143">POST /token HTTP/1.1 Host: authorization-server.com</span></span>

    <span data-ttu-id="4ac00-144">交付タイプ = client_credentials &client_id = xxxxxxxxxx &client_secret = xxxxxxxxxx</span><span class="sxs-lookup"><span data-stu-id="4ac00-144">grant-type=client_credentials &client_id=xxxxxxxxxx &client_secret=xxxxxxxxxx</span></span>

* * *

<span data-ttu-id="4ac00-145">パートナー サービスは、患者のアプリケーション、パートナーの側での認証登録ポータルを介して管理の client_id と client_secret を提供します。</span><span class="sxs-lookup"><span data-stu-id="4ac00-145">The Partner service provides the client_id and client_secret for Patients app, managed via an Auth registration portal on the partner’s side.</span></span> <span data-ttu-id="4ac00-146">パートナー サービスは、クライアント資格情報のフローを使用して要求のアクセス トークンにエンドポイントを提供します。</span><span class="sxs-lookup"><span data-stu-id="4ac00-146">The Partner service provides the endpoint to request access token using a client credential flow.</span></span> <span data-ttu-id="4ac00-147">正常な応答は、token_type、access_token および expires_in パラメーターを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ac00-147">A successful response must include the token_type, access_token and expires_in parameters.</span></span>

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a><span data-ttu-id="4ac00-148">プロバイダー エンドポイントにマッピング AAD テナントをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="4ac00-148">Routing: Mapping AAD Tenant to the Provider endpoint</span></span>

<span data-ttu-id="4ac00-149">患者のアプリケーションは、1 つのエンドポイントを介してパートナー サービスに接続します。</span><span class="sxs-lookup"><span data-stu-id="4ac00-149">The Patients app connects to a partner service through a single endpoint.</span></span> <span data-ttu-id="4ac00-150">パートナー サービスが所有し、パートナーのサービスを使用する各医療機関 (FHIR サーバー) に各 Microsoft 顧客 (AAD テナント ID) をマップするためのメカニズムを維持します。</span><span class="sxs-lookup"><span data-stu-id="4ac00-150">The Partner service owns and maintains a mechanism to map each Microsoft customer (AAD Tenant ID) to a respective healthcare Provider (FHIR server) that the Partner service is working with.</span></span>

<span data-ttu-id="4ac00-151">AAD テナントをプロバイダー エンドポイントにマッピングすると、AAD テナント ID (GUID) が使用します。</span><span class="sxs-lookup"><span data-stu-id="4ac00-151">Mapping the AAD tenant to a provider endpoint uses the AAD Tenant ID (GUID).</span></span> <span data-ttu-id="4ac00-152">患者のアプリケーションは、要求ごとにアクセス トークンを要求しているときに、スコープ内のテナント ID を渡します。</span><span class="sxs-lookup"><span data-stu-id="4ac00-152">The Patients app passes the Tenant ID in scope, while requesting an access-token for each request.</span></span> <span data-ttu-id="4ac00-153">パートナー サービスは、プロバイダー エンドポイントへのテナント ID へのマッピングを保持し、テナント ID に基づいて、プロバイダー エンドポイントに要求をリダイレクト</span><span class="sxs-lookup"><span data-stu-id="4ac00-153">The Partner service keeps the mapping of Tenant ID to Provider endpoint and redirects requests to a provider endpoint based on the Tenant ID.</span></span> <span data-ttu-id="4ac00-154">これを行うには、(手動でまたはのプロバイダー組織は、相互運用機能のプラットフォームの一部としてポータルを経由して)、パートナーは、最後の構成をサポートします。</span><span class="sxs-lookup"><span data-stu-id="4ac00-154">To do this, the partner supports the configuration on their end (manually or via a portal as part of onboarding of provider organizations to their Interop Platform).</span></span>

<span data-ttu-id="4ac00-155">認証およびルーティングのワークフローを次に示します。</span><span class="sxs-lookup"><span data-stu-id="4ac00-155">The Authentication and Routing workflow is shown below:</span></span>

![患者アプリ 6](../../media/Patient-app-6.png)

1. <span data-ttu-id="4ac00-157">送信することによってアプリケーションのアクセス トークンを要求します。</span><span class="sxs-lookup"><span data-stu-id="4ac00-157">Request for app access token by sending:</span></span>
 
        {   grant_type: client_credentials,
            client_id: xxxxxx, 
            client_secret: xxxxxx,
            scope: {Provider Identifier, Ex: tenant ID}
        }

2. <span data-ttu-id="4ac00-158">アプリケーション トークンで応答します。</span><span class="sxs-lookup"><span data-stu-id="4ac00-158">Reply with an app token:</span></span>

        {  access_token: {JWT, with scope: tenant ID},
           expires_in: 156678,
           token_type: "Bearer",
        }

3. <span data-ttu-id="4ac00-159">アクセス トークンを使用して保護されたデータを要求します。</span><span class="sxs-lookup"><span data-stu-id="4ac00-159">Request protected data with Access token.</span></span>
4. <span data-ttu-id="4ac00-160">承認メッセージ: サーバーを選択して、適切な FHIR のスコープ内のテナント ID へのルーティング</span><span class="sxs-lookup"><span data-stu-id="4ac00-160">Authorization message: Select the appropriate FHIR server to route to from tenant ID in scope</span></span>
5. <span data-ttu-id="4ac00-161">アプリケーション トークンを認証した後、FHIR サーバーを承認されたから保護されているアプリケーション データを送信します。</span><span class="sxs-lookup"><span data-stu-id="4ac00-161">Sends the app protected  data from the authorized FHIR server after authenticating with the app token.</span></span>

## <a name="interfaces"></a><span data-ttu-id="4ac00-162">インタ フェース</span><span class="sxs-lookup"><span data-stu-id="4ac00-162">Interfaces</span></span>

<span data-ttu-id="4ac00-163">特定の呼び出しと患者のアプリケーションで使用されるフィールドは、次の資料に記載されています。</span><span class="sxs-lookup"><span data-stu-id="4ac00-163">Specific calls and fields used by the Patients app are documented in the following articles.</span></span> <span data-ttu-id="4ac00-164">FHIR サーバーと FHIR の Api に該当するインターフェイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="4ac00-164">Select the interface applicable to your FHIR server/FHIR APIs.</span></span>

- [<span data-ttu-id="4ac00-165">DSTU2 インターフェイスの仕様</span><span class="sxs-lookup"><span data-stu-id="4ac00-165">DSTU2 interface specification</span></span>](dstu2-interface.md)
- [<span data-ttu-id="4ac00-166">STU3 インターフェイスの仕様</span><span class="sxs-lookup"><span data-stu-id="4ac00-166">STU3 interface specification</span></span>](stu3-interface.md)

## <a name="performance-and-reliability"></a><span data-ttu-id="4ac00-167">パフォーマンスと信頼性</span><span class="sxs-lookup"><span data-stu-id="4ac00-167">Performance and Reliability</span></span>

<span data-ttu-id="4ac00-168">患者のアプリケーションは、プライベートのプレビュー中は、エンド ・ ツー ・ エンドのパフォーマンスの保証はありません。</span><span class="sxs-lookup"><span data-stu-id="4ac00-168">While the Patients app is in private preview, there are no guarantees on the end-to-end performance.</span></span> <span data-ttu-id="4ac00-169">パフォーマンスの要因には、相互運用機能のパートナー ・ ヘルス ・ システムの環境では、EHR の開始、ワークフローに関連するすべてのホップの相対遅延時間が含まれますと、インフラストラクチャ、FHIR サーバーを含む、で Office 365 のエコシステムにし、。患者のアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="4ac00-169">Factors in performance include the relative latencies of all the hops involved in the workflow, starting from the EHR in the health system's environment, to the Interop partner and their infra, including the FHIR Server and across to the Office 365 ecosystem and Patients app.</span></span>

![相互運用パートナー](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a><span data-ttu-id="4ac00-171">FHIR を開始します。</span><span class="sxs-lookup"><span data-stu-id="4ac00-171">Get started with FHIR</span></span>  

<span data-ttu-id="4ac00-172">FHIR にマイクロソフト チームの EHR の統合インターフェイスを公開することができます FHIR サーバーに簡単にアクセスすると、マイクロソフトではオープン ソースの FHIR サーバーが使用するすべての開発者向けに用意します。</span><span class="sxs-lookup"><span data-stu-id="4ac00-172">If you're new to FHIR and need easy access to a FHIR Server that you can expose to the Microsoft Teams EHR integration interface, Microsoft has an open-source FHIR Server available for all developers to use.</span></span> <span data-ttu-id="4ac00-173">FHIR サーバーが Microsoft から利用可能なオープン ・ ソースの詳細について、組織の展開と[Azure の FHIR サーバーは、どのような](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server)資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ac00-173">Please see the [What is FHIR Server for Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) article to learn more about the open source FHIR Server available from Microsoft and deploy it for your organizations.</span></span>

<span data-ttu-id="4ac00-174">環境を使用できます、HSPC を開くサンド ボックス EHR を作成するにも、開いている FHIR サーバーをサポートし、これを使用して患者のアプリで遊んでいる、EHR。</span><span class="sxs-lookup"><span data-stu-id="4ac00-174">You can also use the HSPC Open sandbox EHR environment to create an an EHR which also supports an open FHIR Server and use this to play around with the Patients app.</span></span> <span data-ttu-id="4ac00-175">[HSPC のサンド ボックスのマニュアル](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox)を読むことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4ac00-175">We recommend that you read through the [HSPC Sandbox documentation](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox).</span></span> <span data-ttu-id="4ac00-176">だけでなく、サンド ボックスを提供して、簡単に、UI 指向であり、作成、追加、および患者の編集、ユーザー フレンドリな方法も提供を開始するいくつかのサンプルです。</span><span class="sxs-lookup"><span data-stu-id="4ac00-176">Not only does the sandbox provide an easy, UI oriented, and user friendly way of creating, adding and editing Patients, it also gives you several samples to get started.</span></span>  

## <a name="enroll-in-the-private-preview"></a><span data-ttu-id="4ac00-177">プライベート プレビューに登録します。</span><span class="sxs-lookup"><span data-stu-id="4ac00-177">Enroll in the private preview</span></span>

<span data-ttu-id="4ac00-178">FHIR サーバーのソースを開く、作成した後は、以下に説明する手順を実行して、テナント内の患者のアプリケーションに接続するのには実に簡単です。</span><span class="sxs-lookup"><span data-stu-id="4ac00-178">Once you've created the open source FHIR Server, it's really easy to connect to the Patients app inside of your tenant by following the steps mentioned below:</span></span>

1. <span data-ttu-id="4ac00-179">次の最初の詳細の[お問い合わせ](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20private%20preview):</span><span class="sxs-lookup"><span data-stu-id="4ac00-179">[Contact us](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20private%20preview) with the following initial details:</span></span>  
    - <span data-ttu-id="4ac00-180">お名前 \*</span><span class="sxs-lookup"><span data-stu-id="4ac00-180">Your Name</span></span>
    - <span data-ttu-id="4ac00-181">位置</span><span class="sxs-lookup"><span data-stu-id="4ac00-181">Your Position</span></span>
    - <span data-ttu-id="4ac00-182">会社または組織を表す</span><span class="sxs-lookup"><span data-stu-id="4ac00-182">The company or organization you represent</span></span>
    - <span data-ttu-id="4ac00-183">EHR の統合のための患者のアプリに興味のある理由</span><span class="sxs-lookup"><span data-stu-id="4ac00-183">Why you are interested in the Patients app for EHR integration</span></span>

    <span data-ttu-id="4ac00-184">戻るをできるだけ早くその他の質問で、プライベート プレビュー設定を取得するプロセスについて説明しては。</span><span class="sxs-lookup"><span data-stu-id="4ac00-184">We will get back to you as soon as possible with more questions and guide you through a process to get set up for the private preview.</span></span>

2. <span data-ttu-id="4ac00-185">カスタムを sideloading ことを確認どこに患者のアプリを試すテナントでアプリケーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="4ac00-185">Ensure that sideloading of custom apps is enabled in the tenant where you are going to try out the Patients app.</span></span> <span data-ttu-id="4ac00-186">[アプリケーションのアクセス許可ポリシー](../../admin-settings.md)を有効にするチームの管理センターから、または、お客様のテナントの方法についてを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ac00-186">Please refer to [App permission policies](../../admin-settings.md) to learn how to turn this on from the Teams Admin center for your or your customer's tenant.</span></span>

3. <span data-ttu-id="4ac00-187">Sideload 患者のアプリケーション マニフェストはから入手することマイクロソフト (後に、電子メールの処理) に注意を払って調整と患者の丸めのシナリオに使用するテナントのチームに。</span><span class="sxs-lookup"><span data-stu-id="4ac00-187">Sideload the Patients app manifest that you will get from Microsoft (after we process your email to us) into a team in the tenant that is going to be used for care-coordination and patient rounding scenarios.</span></span> <span data-ttu-id="4ac00-188">側アプリケーションをロードする方法の詳細については[マイクロソフトのチームに、アプリケーション パッケージをアップロードするの](/microsoftteams/platform/concepts/apps/apps-upload)には</span><span class="sxs-lookup"><span data-stu-id="4ac00-188">Detailed instructions around how to side-load an app are in [Upload an app package to Microsoft Teams](/microsoftteams/platform/concepts/apps/apps-upload)</span></span>

4. <span data-ttu-id="4ac00-189">チームの所有者は、一般的なチャネルに移動し、[患者] タブをクリックします。EHR モードと手動モードの 2 つを提供する最初の実行エクスペリエンス オプションなどが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4ac00-189">Navigate to the general channel as the Team owner and then click on the Patients tab. You should see a first run experience that will present two options i.e. EHR Mode and Manual Mode.</span></span> <span data-ttu-id="4ac00-190">**EHR のモード**を選択し、エンドポイントをコピー、FHIR サーバー (以前のバージョンに、すべての必要なデータと仕様上あたりのリソースだけでセットアップした結果)、[リンク] フィールドに、接続にも、FHIR サーバーを表す名前を付けてしてください。</span><span class="sxs-lookup"><span data-stu-id="4ac00-190">Please select the **EHR mode** and copy the FHIR Server endpoint (that you've just setup earlier with all the required data and resources per the specifications above) into the Link field and give the connection a name that well represents the FHIR Server.</span></span> <span data-ttu-id="4ac00-191">接続] をクリックし、移動する準備がすべて必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ac00-191">Click on Connect, and everything should be ready to go.</span></span>

    ![患者のアプリケーション サーバーの設定](../../media/patients-server.png)

5. <span data-ttu-id="4ac00-193">検索してから、FHIR サーバー/EHR の患者のリストに追加し、何かが機能しない場合、[フィードバック](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20feedback)をしてください、アプリケーションを使用して起動します。</span><span class="sxs-lookup"><span data-stu-id="4ac00-193">Start using the app to search for Patients from the FHIR Server/EHR and add them to a list and please [give us feedback](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20feedback) if something doesn't work.</span></span> <span data-ttu-id="4ac00-194">また、患者のアプリケーションの完全に認証されたバージョンを確立するために-_gt FHIR サーバーの流れ、相談してくださいを通じて医療の製品がエンジニア リング用には、マイクロソフトのチームでオフライン ダイアログ ボックスで電子メールの要求が前述の要件を明確にすると、我々 は。これを有効にする FHIR インターフェイスのドキュメントで説明した認証要件を支援します。</span><span class="sxs-lookup"><span data-stu-id="4ac00-194">Also, to establish a fully authenticated version of the Patients app -> FHIR Server flow, please engage in offline dialogue with Microsoft Teams for healthcare product engineering, through the email request mentioned earlier to clarify requirements and we will help enable this for you per the Authentication requirements described above in the FHIR Interface document.</span></span>  


