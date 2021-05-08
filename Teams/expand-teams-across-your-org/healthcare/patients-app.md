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
description: FHIR API を使用して、電子医療記録を Microsoft Teams患者アプリに統合する方法について説明します。
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 2b4878f67b7738a13e3c1385ee0713d6e3e3d481
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096211"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a><span data-ttu-id="c18cd-103">電子医療記録を Microsoft Teams に統合する</span><span class="sxs-lookup"><span data-stu-id="c18cd-103">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="c18cd-104">2020 年 10 月 30 日より、患者アプリは廃止され、Teams の[リスト アプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)に置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="c18cd-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="c18cd-105">患者アプリのデータは、チームを支援する Office 365 グループのグループ メールボックスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="c18cd-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="c18cd-106">患者アプリに関連付けられているすべてのデータはこのグループに保持されますが、ユーザー インターフェイスからアクセスすることはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="c18cd-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="c18cd-107">ユーザーは、[リスト アプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)を使用してリストを再作成できます。</span><span class="sxs-lookup"><span data-stu-id="c18cd-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="c18cd-108">リストを使用すると、医療機関のケア チームは、ラウンドや学際的なチーム会議から一般的な患者の監視に至るまでのシナリオで患者リストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c18cd-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="c18cd-109">開始するには、リストの患者テンプレートを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c18cd-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="c18cd-110">組織でリスト アプリを管理する方法の詳細については、「[リスト アプリの管理](../../manage-lists-app.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c18cd-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="c18cd-111">この記事は、医療情報システムの上で FHIR API を使用して医療情報システムに接続することに関心がある一般的な医療 IT 開発者を対象Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="c18cd-111">This article is intended for a general healthcare IT developer interested in using FHIR APIs on top of a medical information system to connect to Microsoft Teams.</span></span> <span data-ttu-id="c18cd-112">これにより、医療組織のニーズに合ったケア調整シナリオが可能になります。</span><span class="sxs-lookup"><span data-stu-id="c18cd-112">This would enable care coordination scenarios that match the needs of a healthcare organization.</span></span>

<span data-ttu-id="c18cd-113">リンクされた記事では、Microsoft Teams Patients アプリの FHIR インターフェイス仕様について説明し、以下のセクションでは、FHIR サーバーを設定し、開発環境またはテナント内の Patients アプリに接続するために必要な内容について説明します。</span><span class="sxs-lookup"><span data-stu-id="c18cd-113">Linked articles document the FHIR interface specifications for the Microsoft Teams Patients app, and following sections explain what is required for setting up a FHIR server and connecting to the Patients app in your development environment or tenant.</span></span> <span data-ttu-id="c18cd-114">また、選択した FHIR サーバーのドキュメントを理解する必要があります。これは、サポートされているオプションの 1 つである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c18cd-114">You will also need to be familiar with the documentation of the FHIR server you have chosen, which must be one of the supported options:</span></span>

- <span data-ttu-id="c18cd-115">Datica [(CMI](https://datica.com/compliant-managed-integration/) オファリングを通じて)</span><span class="sxs-lookup"><span data-stu-id="c18cd-115">Datica (through their [CMI](https://datica.com/compliant-managed-integration/) offering)</span></span>
- <span data-ttu-id="c18cd-116">Infor Cloverleaf [(Infor FHIR ブリッジ経由](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span><span class="sxs-lookup"><span data-stu-id="c18cd-116">Infor Cloverleaf (through the [Infor FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span></span>
- <span data-ttu-id="c18cd-117">Redox [(R^FHIR サーバー経由](https://www.redoxengine.com/fhir/))</span><span class="sxs-lookup"><span data-stu-id="c18cd-117">Redox (through the [R^FHIR server](https://www.redoxengine.com/fhir/))</span></span>
- <span data-ttu-id="c18cd-118">Dapasoft [(FHIR の Corolar 経由](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span><span class="sxs-lookup"><span data-stu-id="c18cd-118">Dapasoft (through [Corolar on FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span></span>

> [!NOTE]
> <span data-ttu-id="c18cd-119">このプロセスには、管理センターまたは PowerShell コマンドレットMicrosoft Teams機能を有効にする手順は含まれています。</span><span class="sxs-lookup"><span data-stu-id="c18cd-119">This process does not includes steps that use the Microsoft Teams admin center or PowerShell cmdlets to enable features.</span></span> <span data-ttu-id="c18cd-120">構成は、FHIR サーバー/サービス側と Patients アプリ クライアントで完全に行われます。</span><span class="sxs-lookup"><span data-stu-id="c18cd-120">The configuration is entirely done on the FHIR server/service side and in the Patients app client.</span></span>

<span data-ttu-id="c18cd-121">次に示すのは、Patients アプリのアーキテクチャです。</span><span class="sxs-lookup"><span data-stu-id="c18cd-121">Illustrated below is the architecture of the Patients app:</span></span>

![Patients アプリのアーキテクチャの図](../../media/patients-app-architecture.png)

<span data-ttu-id="c18cd-123">次のセクションでは、次のような、FHIR サーバー (または EHR 対応 FHIR API) が Patients アプリと統合するために満たす必要がある、Patients アプリの FHIR 専用データ アクセス 層の要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="c18cd-123">The following sections explain the requirements of the FHIR-only data access layer for the Patients app that a FHIR server (or EHR enabled FHIR APIs) must meet in order to integrate with the Patients app, including the following:</span></span>

- <span data-ttu-id="c18cd-124">ユーザー認証に関する期待</span><span class="sxs-lookup"><span data-stu-id="c18cd-124">Expectations around user authentication</span></span>
- <span data-ttu-id="c18cd-125">統合インターフェイスの機能要件と技術要件</span><span class="sxs-lookup"><span data-stu-id="c18cd-125">Functional and technical requirements of the integration interface</span></span>
- <span data-ttu-id="c18cd-126">パフォーマンスと信頼性に関する期待</span><span class="sxs-lookup"><span data-stu-id="c18cd-126">Expectations around performance and reliability</span></span>
- <span data-ttu-id="c18cd-127">Patients アプリでサポートされる FHIR リソースに関する期待</span><span class="sxs-lookup"><span data-stu-id="c18cd-127">Expectations around FHIR resources to be supported for the Patients app</span></span>
- <span data-ttu-id="c18cd-128">統合プロセスと予想されるエンゲージメント モデル</span><span class="sxs-lookup"><span data-stu-id="c18cd-128">Process for integration and the expected engagement model</span></span>
- <span data-ttu-id="c18cd-129">FHIR の使用を開始する方法と、Patients アプリで直面する一般的な課題</span><span class="sxs-lookup"><span data-stu-id="c18cd-129">How to get started with FHIR and some common challenges faced with the Patients app</span></span>
- <span data-ttu-id="c18cd-130">Patients アプリの次のイテレーションに関する将来の要件</span><span class="sxs-lookup"><span data-stu-id="c18cd-130">Future requirements for the next iteration of the Patients app</span></span>

> [!NOTE]
> <span data-ttu-id="c18cd-131">次のセクションでは、"partner" または "Interop partner" という単語は、FHIR を介して Patients アプリの EHR システムへの統合を可能にし、記載されている仕様に合わせて FHIR Server を実装しているサードパーティの組織を参照するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c18cd-131">In the following sections, the word "partner" or "Interop partner" is used to refer to any 3rd party Organization that enables integration to EHR systems for the Patients app through FHIR and is implementing a FHIR Server to match the listed specifications.</span></span>

## <a name="functional-and-technical-requirements"></a><span data-ttu-id="c18cd-132">機能要件と技術要件</span><span class="sxs-lookup"><span data-stu-id="c18cd-132">Functional and technical requirements</span></span>  

### <a name="authentication"></a><span data-ttu-id="c18cd-133">認証</span><span class="sxs-lookup"><span data-stu-id="c18cd-133">Authentication</span></span>  

<span data-ttu-id="c18cd-134">ユーザー レベルの承認をサポートするアプリ レベルの承認は、EHR システムがユーザー レベルの承認を実装している場合でも、FHIR を介してデータ変換を実行し、EHR データへの接続を公開する、より一般的にサポートされる方法です。</span><span class="sxs-lookup"><span data-stu-id="c18cd-134">App-level authorization *with no support for user level authorization* is the more commonly supported way to perform data transformations and expose connections to EHR data through FHIR, even though the EHR system might implement user level authorization.</span></span> <span data-ttu-id="c18cd-135">Interop Service (パートナー) は EHR データへの昇格されたアクセス権を取得し、適切な FHIR リソースと同じデータを公開すると、Interop Service または Platform と統合された Interop Service Consumer (Patients アプリ) に渡される承認コンテキストはありません。</span><span class="sxs-lookup"><span data-stu-id="c18cd-135">The Interop Service (Partner) gets elevated access to the EHR data, and when they expose the same data as the appropriate FHIR resources there is no authorization context passed on to the Interop Service Consumer (the Patients app) integrating with the Interop Service or Platform.</span></span> <span data-ttu-id="c18cd-136">Patients アプリはユーザー レベルの承認を強制できますが、Patients アプリと Interop パートナーのサービス間のアプリケーション認証をサポートします。</span><span class="sxs-lookup"><span data-stu-id="c18cd-136">The Patients app will not be able to enforce user level authorization, but does support application to application authentication between the Patients app and the Interop partner's service.</span></span>

<span data-ttu-id="c18cd-137">アプリケーション間認証モデルの説明は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c18cd-137">The Application to Application authentication model is described below:</span></span>

<span data-ttu-id="c18cd-138">サービス間認証は、OAuth 2.0 クライアント資格情報フロー [を通じて行う必要があります](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)。</span><span class="sxs-lookup"><span data-stu-id="c18cd-138">Service to service authentication should be done through OAuth 2.0 [Client Credential flow](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/).</span></span> <span data-ttu-id="c18cd-139">パートナー サービスは、次の情報を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c18cd-139">The partner service needs to provide the following:</span></span>

1. <span data-ttu-id="c18cd-140">パートナー サービスを使用すると、Patients アプリはパートナーとアカウントを作成できます。これにより、Patients アプリはパートナーの認証サーバーの認証登録ポータルを使用して管理する client_id と client_secret を生成して所有できます。</span><span class="sxs-lookup"><span data-stu-id="c18cd-140">The Partner service enables the Patients app to create an account with the Partner, which enables the Patients app to generate and own client_id and client_secret, managed via an Auth registration portal on the partner's Authentication server.</span></span>

2. <span data-ttu-id="c18cd-141">パートナー サービスは認証/承認システムを所有しています。このシステムは、指定されたクライアント資格情報を受け入れて検証 (認証) し、次に示すテナント ヒントをスコープに含むアクセス トークンを返します。</span><span class="sxs-lookup"><span data-stu-id="c18cd-141">The Partner service owns the Authentication/Authorization system, which accepts and verifies (authenticates) the client credentials provided and gives back an access token with tenant hint in scope, as described below.</span></span>

3. <span data-ttu-id="c18cd-142">セキュリティ上の理由から、またはシークレット違反が発生した場合、Patients アプリはシークレットを再生成し、古いシークレットを無効化または削除できます (同じ例は、Azure Portal - AAD アプリ登録で利用できます)。</span><span class="sxs-lookup"><span data-stu-id="c18cd-142">For security reasons or in a case of a secret breach, the Patients app can re-generate the secret and invalidate or delete the old secret (example of the same is available in Azure Portal - AAD App Registration).</span></span>

4. <span data-ttu-id="c18cd-143">準拠ステートメントをホストするメタデータ エンドポイントは認証されていない必要があります。認証トークンなしでアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c18cd-143">The metadata endpoint hosting the conformance statement should be un-authenticated, it should be accessible without authentication token.</span></span>

5. <span data-ttu-id="c18cd-144">パートナー サービスは、クライアント資格情報フローを使用してアクセス トークンを要求する、Patients アプリのトークン エンドポイントを提供します。</span><span class="sxs-lookup"><span data-stu-id="c18cd-144">The Partner service provides the token endpoint for the Patients app to request an access token using a client credential flow.</span></span> <span data-ttu-id="c18cd-145">承認サーバーごとのトークン URL は、次の例のように、FHIR サーバーのメタデータからフェッチされた FHIR 準拠 (機能) ステートメントの一部である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c18cd-145">The token URL as per authorization server should be part of the FHIR conformance (capability) statement fetched from metadata on the FHIR server as in this example:</span></span>

    ```
    {
        "resourceType": "CapabilityStatement",
        .
        .
        .
        "rest": [
            {
                "mode": "server",
                "security": {
                    "extension": [
                        {
                            "extension": [
                                {
                                    "url": "token",
                                    "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/token"
                                },
                                {
                                    "url": "authorize",
                                    "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/authorize"
                                }
                            ],
                            "url": "http://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris"
                        }
                    ],
                    "service": [
                        {
                            "coding": [
                                {
                                    "system": "https://hl7.org/fhir/ValueSet/restful-security-service",
                                    "code": "OAuth"
                                }
                            ]
                        }
                    ]
                },
                .
                .
                .
            }
        ]
    }
    ```

<span data-ttu-id="c18cd-146">アクセス トークンの要求は、次のパラメーターで構成されます。</span><span class="sxs-lookup"><span data-stu-id="c18cd-146">A request for an access token consists of the following parameters:</span></span>

```http
POST /token HTTP/1.1
Host: authorization-server.com

grant-type=client_credentials
&client_id=xxxxxxxxxx
&client_secret=xxxxxxxxxx
```

<span data-ttu-id="c18cd-147">パートナー サービスは、パートナー側client_id認証client_secretポータルを使用して管理される、Patients アプリのアプリケーションとサービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="c18cd-147">The Partner service provides the client_id and client_secret for Patients app, managed via an Auth registration portal on the partner's side.</span></span> <span data-ttu-id="c18cd-148">パートナー サービスは、クライアント資格情報フローを使用してアクセス トークンを要求するエンドポイントを提供します。</span><span class="sxs-lookup"><span data-stu-id="c18cd-148">The Partner service provides the endpoint to request access token using a client credential flow.</span></span> <span data-ttu-id="c18cd-149">成功した応答には、token_type パラメーター、access_tokenパラメーター expires_inがあります。</span><span class="sxs-lookup"><span data-stu-id="c18cd-149">A successful response must include the token_type, access_token and expires_in parameters.</span></span>

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a><span data-ttu-id="c18cd-150">ルーティング: AAD テナントをプロバイダー エンドポイントにマッピングする</span><span class="sxs-lookup"><span data-stu-id="c18cd-150">Routing: Mapping AAD Tenant to the Provider endpoint</span></span>

<span data-ttu-id="c18cd-151">Patients アプリは、1 つのエンドポイントを介してパートナー サービスに接続します。</span><span class="sxs-lookup"><span data-stu-id="c18cd-151">The Patients app connects to a partner service through a single endpoint.</span></span> <span data-ttu-id="c18cd-152">パートナー サービスは、各 Microsoft 顧客 (AAD テナント ID) を、パートナー サービスが操作しているそれぞれの医療プロバイダー (FHIR サーバー) にマップするメカニズムを所有および管理します。</span><span class="sxs-lookup"><span data-stu-id="c18cd-152">The Partner service owns and maintains a mechanism to map each Microsoft customer (AAD Tenant ID) to a respective healthcare Provider (FHIR server) that the Partner service is working with.</span></span>

<span data-ttu-id="c18cd-153">AAD テナントをプロバイダー エンドポイントにマッピングするには、AAD テナント ID (GUID) を使用します。</span><span class="sxs-lookup"><span data-stu-id="c18cd-153">Mapping the AAD tenant to a provider endpoint uses the AAD Tenant ID (GUID).</span></span> <span data-ttu-id="c18cd-154">Patients アプリは、要求ごとにアクセス トークンを要求しながら、スコープ内のテナント ID を渡します。</span><span class="sxs-lookup"><span data-stu-id="c18cd-154">The Patients app passes the Tenant ID in scope, while requesting an access-token for each request.</span></span> <span data-ttu-id="c18cd-155">パートナー サービスは、テナント ID のプロバイダー エンドポイントへのマッピングを保持し、テナント ID に基づいて要求をプロバイダー エンドポイントにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="c18cd-155">The Partner service keeps the mapping of Tenant ID to Provider endpoint and redirects requests to a provider endpoint based on the Tenant ID.</span></span> <span data-ttu-id="c18cd-156">これを行うには、パートナーはエンドで構成をサポートします (プロバイダー組織の Interop Platform へのオンボードの一環として、手動またはポータルを使用)。</span><span class="sxs-lookup"><span data-stu-id="c18cd-156">To do this, the partner supports the configuration on their end (manually or via a portal as part of onboarding of provider organizations to their Interop Platform).</span></span>

<span data-ttu-id="c18cd-157">認証とルーティングのワークフローを次に示します。</span><span class="sxs-lookup"><span data-stu-id="c18cd-157">The Authentication and Routing workflow is shown below:</span></span>

![認証とルーティングのワークフローの図](../../media/Patient-app-6.png)

1. <span data-ttu-id="c18cd-159">次を送信してアプリ アクセス トークンを要求します。</span><span class="sxs-lookup"><span data-stu-id="c18cd-159">Request for app access token by sending:</span></span>
 
    ```
    {   grant_type: client_credentials,
        client_id: xxxxxx, 
        client_secret: xxxxxx,
        scope: {Provider Identifier, Ex: tenant ID}
    }
    ```

2. <span data-ttu-id="c18cd-160">アプリ トークンで返信する:</span><span class="sxs-lookup"><span data-stu-id="c18cd-160">Reply with an app token:</span></span>

    ```
    {  access_token: {JWT, with scope: tenant ID},
       expires_in: 156678,
       token_type: "Bearer",
    }
    ```

3. <span data-ttu-id="c18cd-161">アクセス トークンを使用して保護されたデータを要求します。</span><span class="sxs-lookup"><span data-stu-id="c18cd-161">Request protected data with Access token.</span></span>

4. <span data-ttu-id="c18cd-162">承認メッセージ: スコープ内のテナント ID からにルーティングする適切な FHIR サーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c18cd-162">Authorization message: Select the appropriate FHIR server to route to from tenant ID in scope.</span></span>

5. <span data-ttu-id="c18cd-163">アプリ トークンで認証した後、承認された FHIR サーバーからアプリで保護されたデータを送信します。</span><span class="sxs-lookup"><span data-stu-id="c18cd-163">Sends the app protected  data from the authorized FHIR server after authenticating with the app token.</span></span>

## <a name="interfaces"></a><span data-ttu-id="c18cd-164">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c18cd-164">Interfaces</span></span>

<span data-ttu-id="c18cd-165">Patients アプリで使用される特定の呼び出しとフィールドについては、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c18cd-165">Specific calls and fields used by the Patients app are documented in the following articles.</span></span> <span data-ttu-id="c18cd-166">FHIR サーバー/FHIR API に適用可能なインターフェイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="c18cd-166">Select the interface applicable to your FHIR server/FHIR APIs.</span></span>

- [<span data-ttu-id="c18cd-167">DSTU2 インターフェイスの仕様</span><span class="sxs-lookup"><span data-stu-id="c18cd-167">DSTU2 interface specification</span></span>](dstu2-interface.md)
- [<span data-ttu-id="c18cd-168">STU3 インターフェイスの仕様</span><span class="sxs-lookup"><span data-stu-id="c18cd-168">STU3 interface specification</span></span>](stu3-interface.md)

## <a name="performance-and-reliability"></a><span data-ttu-id="c18cd-169">パフォーマンスと信頼性</span><span class="sxs-lookup"><span data-stu-id="c18cd-169">Performance and Reliability</span></span>

<span data-ttu-id="c18cd-170">Patients アプリはプライベート プレビュー中ですが、エンド to エンドのパフォーマンスに関する保証はありません。</span><span class="sxs-lookup"><span data-stu-id="c18cd-170">While the Patients app is in private preview, there are no guarantees on the end-to-end performance.</span></span> <span data-ttu-id="c18cd-171">パフォーマンスの要因には、正常性システムの環境内の EHR から、Interop パートナーとそのインフラストラクチャ (FHIR Server を含む)、および Office 365 エコシステムおよび Patients アプリまで、ワークフローに関連するすべてのホップの相対的な待機時間が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c18cd-171">Factors in performance include the relative latencies of all the hops involved in the workflow, starting from the EHR in the health system's environment, to the Interop partner and their infra, including the FHIR Server and across to the Office 365 ecosystem and Patients app.</span></span>

![相互運用パートナーのパフォーマンスの図](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a><span data-ttu-id="c18cd-173">FHIR の使用</span><span class="sxs-lookup"><span data-stu-id="c18cd-173">Get started with FHIR</span></span>  

<span data-ttu-id="c18cd-174">FHIR を使い始め、Microsoft Teams EHR 統合インターフェイスに公開できる FHIR Server に簡単にアクセスする必要がある場合、Microsoft には、すべての開発者が使用できるオープン ソースの FHIR Server があります。</span><span class="sxs-lookup"><span data-stu-id="c18cd-174">If you're new to FHIR and need easy access to a FHIR Server that you can expose to the Microsoft Teams EHR integration interface, Microsoft has an open-source FHIR Server available for all developers to use.</span></span> <span data-ttu-id="c18cd-175">Microsoft から提供 [されているオープン ソースの FHIR Server](/azure/healthcare-apis/overview-open-source-server) の詳細と組織向けデプロイについては、「Azure の FHIR Server とは」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c18cd-175">Please see the [What is FHIR Server for Azure](/azure/healthcare-apis/overview-open-source-server) article to learn more about the open source FHIR Server available from Microsoft and deploy it for your organizations.</span></span>

<span data-ttu-id="c18cd-176">HSPC Open Sandbox EHR 環境を使用して、開いている FHIR サーバーもサポートする EHR を作成し、これを使用して Patients アプリを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="c18cd-176">You can also use the HSPC Open sandbox EHR environment to create an an EHR which also supports an open FHIR Server and use this to play around with the Patients app.</span></span> <span data-ttu-id="c18cd-177">HSPC Sandbox のドキュメント [を参照することをお勧めします](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox)。</span><span class="sxs-lookup"><span data-stu-id="c18cd-177">We recommend that you read through the [HSPC Sandbox documentation](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox).</span></span> <span data-ttu-id="c18cd-178">サンドボックスでは、患者の作成、追加、編集を簡単で UI 指向でユーザーにわかりやすい方法で行えるだけでなく、使用を開始するためのサンプルもいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="c18cd-178">Not only does the sandbox provide an easy, UI oriented, and user friendly way of creating, adding and editing Patients, it also gives you several samples to get started.</span></span>