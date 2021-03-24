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
description: FHIR API を使用して、電子医療記録を Microsoft Teams 患者アプリに統合する方法について説明します。
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 2b4878f67b7738a13e3c1385ee0713d6e3e3d481
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096211"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a><span data-ttu-id="8206c-103">電子医療記録を Microsoft Teams に統合する</span><span class="sxs-lookup"><span data-stu-id="8206c-103">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="8206c-104">2020 年 10 月 30 日より、患者アプリは廃止され、Teams の[リスト アプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)に置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="8206c-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="8206c-105">患者アプリのデータは、チームを支援する Office 365 グループのグループ メールボックスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="8206c-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="8206c-106">患者アプリに関連付けられているすべてのデータはこのグループに保持されますが、ユーザー インターフェイスからアクセスすることはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="8206c-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="8206c-107">ユーザーは、[リスト アプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)を使用してリストを再作成できます。</span><span class="sxs-lookup"><span data-stu-id="8206c-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="8206c-108">リストを使用すると、医療機関のケア チームは、ラウンドや学際的なチーム会議から一般的な患者の監視に至るまでのシナリオで患者リストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="8206c-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="8206c-109">開始するには、リストの患者テンプレートを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8206c-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="8206c-110">組織でリスト アプリを管理する方法の詳細については、「[リスト アプリの管理](../../manage-lists-app.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8206c-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="8206c-111">この記事は、医療情報システムの上で FHIR API を使用して Microsoft Teams に接続することに関心がある一般的な医療 IT 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="8206c-111">This article is intended for a general healthcare IT developer interested in using FHIR APIs on top of a medical information system to connect to Microsoft Teams.</span></span> <span data-ttu-id="8206c-112">これにより、医療組織のニーズに合ったケア協調シナリオが可能になります。</span><span class="sxs-lookup"><span data-stu-id="8206c-112">This would enable care coordination scenarios that match the needs of a healthcare organization.</span></span>

<span data-ttu-id="8206c-113">リンクされた記事では、Microsoft Teams Patients アプリの FHIR インターフェイス仕様について説明し、次のセクションでは、FHIR サーバーをセットアップし、開発環境またはテナントの患者アプリに接続するために必要な理由について説明します。</span><span class="sxs-lookup"><span data-stu-id="8206c-113">Linked articles document the FHIR interface specifications for the Microsoft Teams Patients app, and following sections explain what is required for setting up a FHIR server and connecting to the Patients app in your development environment or tenant.</span></span> <span data-ttu-id="8206c-114">また、選択した FHIR サーバーのドキュメントを理解する必要があります。これは、サポートされているオプションの 1 つである必要があります。</span><span class="sxs-lookup"><span data-stu-id="8206c-114">You will also need to be familiar with the documentation of the FHIR server you have chosen, which must be one of the supported options:</span></span>

- <span data-ttu-id="8206c-115">Datica [(CMI](https://datica.com/compliant-managed-integration/) サービスを通じて)</span><span class="sxs-lookup"><span data-stu-id="8206c-115">Datica (through their [CMI](https://datica.com/compliant-managed-integration/) offering)</span></span>
- <span data-ttu-id="8206c-116">Infor Cloverleaf [(Infor FHIR Bridge を通る](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span><span class="sxs-lookup"><span data-stu-id="8206c-116">Infor Cloverleaf (through the [Infor FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span></span>
- <span data-ttu-id="8206c-117">Redox [(R^FHIR サーバー経由](https://www.redoxengine.com/fhir/))</span><span class="sxs-lookup"><span data-stu-id="8206c-117">Redox (through the [R^FHIR server](https://www.redoxengine.com/fhir/))</span></span>
- <span data-ttu-id="8206c-118">Dapasoft [(FHIR の場合は、](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/)</span><span class="sxs-lookup"><span data-stu-id="8206c-118">Dapasoft (through [Corolar on FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span></span>

> [!NOTE]
> <span data-ttu-id="8206c-119">このプロセスには、Microsoft Teams 管理センターまたは PowerShell コマンドレットを使用して機能を有効にする手順は含まれています。</span><span class="sxs-lookup"><span data-stu-id="8206c-119">This process does not includes steps that use the Microsoft Teams admin center or PowerShell cmdlets to enable features.</span></span> <span data-ttu-id="8206c-120">構成は、FHIR サーバー/サービス側と患者アプリ クライアントで完全に行われます。</span><span class="sxs-lookup"><span data-stu-id="8206c-120">The configuration is entirely done on the FHIR server/service side and in the Patients app client.</span></span>

<span data-ttu-id="8206c-121">次に示すのは、患者アプリのアーキテクチャです。</span><span class="sxs-lookup"><span data-stu-id="8206c-121">Illustrated below is the architecture of the Patients app:</span></span>

![患者アプリのアーキテクチャの図](../../media/patients-app-architecture.png)

<span data-ttu-id="8206c-123">次のセクションでは、患者アプリと統合するために FHIR サーバー (または EHR で FHIR API を有効にする) が満たす必要がある、患者アプリの FHIR 専用データ アクセスレイヤーの要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="8206c-123">The following sections explain the requirements of the FHIR-only data access layer for the Patients app that a FHIR server (or EHR enabled FHIR APIs) must meet in order to integrate with the Patients app, including the following:</span></span>

- <span data-ttu-id="8206c-124">ユーザー認証に関する期待</span><span class="sxs-lookup"><span data-stu-id="8206c-124">Expectations around user authentication</span></span>
- <span data-ttu-id="8206c-125">統合インターフェイスの機能要件と技術的要件</span><span class="sxs-lookup"><span data-stu-id="8206c-125">Functional and technical requirements of the integration interface</span></span>
- <span data-ttu-id="8206c-126">パフォーマンスと信頼性に関する期待</span><span class="sxs-lookup"><span data-stu-id="8206c-126">Expectations around performance and reliability</span></span>
- <span data-ttu-id="8206c-127">患者アプリでサポートされる FHIR リソースに関する期待</span><span class="sxs-lookup"><span data-stu-id="8206c-127">Expectations around FHIR resources to be supported for the Patients app</span></span>
- <span data-ttu-id="8206c-128">統合プロセスと期待される契約モデル</span><span class="sxs-lookup"><span data-stu-id="8206c-128">Process for integration and the expected engagement model</span></span>
- <span data-ttu-id="8206c-129">FHIR の使用を開始する方法と、患者アプリで直面する一般的な課題</span><span class="sxs-lookup"><span data-stu-id="8206c-129">How to get started with FHIR and some common challenges faced with the Patients app</span></span>
- <span data-ttu-id="8206c-130">患者アプリの次の反復に関する将来の要件</span><span class="sxs-lookup"><span data-stu-id="8206c-130">Future requirements for the next iteration of the Patients app</span></span>

> [!NOTE]
> <span data-ttu-id="8206c-131">次のセクションでは、"partner" または "Interop partner" という単語は、FHIR を介して患者アプリの EHR システムに統合できるサードパーティ組織を参照するために使用され、記載されている仕様に合わせて FHIR Server を実装しています。</span><span class="sxs-lookup"><span data-stu-id="8206c-131">In the following sections, the word "partner" or "Interop partner" is used to refer to any 3rd party Organization that enables integration to EHR systems for the Patients app through FHIR and is implementing a FHIR Server to match the listed specifications.</span></span>

## <a name="functional-and-technical-requirements"></a><span data-ttu-id="8206c-132">機能要件と技術要件</span><span class="sxs-lookup"><span data-stu-id="8206c-132">Functional and technical requirements</span></span>  

### <a name="authentication"></a><span data-ttu-id="8206c-133">認証</span><span class="sxs-lookup"><span data-stu-id="8206c-133">Authentication</span></span>  

<span data-ttu-id="8206c-134">ユーザー レベルの承認がサポートされなくても、ユーザー レベルの承認をサポートするアプリ レベルの承認は、EHR システムがユーザー レベルの承認を実装している場合でも、FHIR を通じてデータ変換を実行し、EHR データへの接続を公開する、より一般的にサポートされている方法です。</span><span class="sxs-lookup"><span data-stu-id="8206c-134">App-level authorization *with no support for user level authorization* is the more commonly supported way to perform data transformations and expose connections to EHR data through FHIR, even though the EHR system might implement user level authorization.</span></span> <span data-ttu-id="8206c-135">相互運用サービス (パートナー) は EHR データへのアクセスを昇格し、適切な FHIR リソースと同じデータを公開すると、相互運用サービスまたはプラットフォームと統合された Interop Service Consumer (The Patients アプリ) に渡される承認コンテキストはありません。</span><span class="sxs-lookup"><span data-stu-id="8206c-135">The Interop Service (Partner) gets elevated access to the EHR data, and when they expose the same data as the appropriate FHIR resources there is no authorization context passed on to the Interop Service Consumer (the Patients app) integrating with the Interop Service or Platform.</span></span> <span data-ttu-id="8206c-136">患者アプリはユーザー レベルの承認を強制できますが、患者アプリと相互運用パートナーのサービス間のアプリケーション認証をサポートします。</span><span class="sxs-lookup"><span data-stu-id="8206c-136">The Patients app will not be able to enforce user level authorization, but does support application to application authentication between the Patients app and the Interop partner's service.</span></span>

<span data-ttu-id="8206c-137">アプリケーション間認証モデルの説明を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="8206c-137">The Application to Application authentication model is described below:</span></span>

<span data-ttu-id="8206c-138">サービス間認証は、OAuth 2.0 クライアント資格情報フロー [を通じて行う必要があります](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)。</span><span class="sxs-lookup"><span data-stu-id="8206c-138">Service to service authentication should be done through OAuth 2.0 [Client Credential flow](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/).</span></span> <span data-ttu-id="8206c-139">パートナー サービスは、次の情報を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8206c-139">The partner service needs to provide the following:</span></span>

1. <span data-ttu-id="8206c-140">パートナー サービスを使用すると、患者アプリがパートナーとアカウントを作成できます。これにより、患者アプリはパートナーの認証サーバーの認証登録ポータルを介して管理される client_id と client_secret を生成して所有することができます。</span><span class="sxs-lookup"><span data-stu-id="8206c-140">The Partner service enables the Patients app to create an account with the Partner, which enables the Patients app to generate and own client_id and client_secret, managed via an Auth registration portal on the partner's Authentication server.</span></span>

2. <span data-ttu-id="8206c-141">パートナー サービスは認証/承認システムを所有します。このシステムは、提供されたクライアント資格情報を受け入れて検証 (認証) し、次に示すスコープでテナントヒントを含むアクセス トークンを返します。</span><span class="sxs-lookup"><span data-stu-id="8206c-141">The Partner service owns the Authentication/Authorization system, which accepts and verifies (authenticates) the client credentials provided and gives back an access token with tenant hint in scope, as described below.</span></span>

3. <span data-ttu-id="8206c-142">セキュリティ上の理由から、または秘密違反が発生した場合、患者アプリは秘密を再生成し、古い秘密を無効化または削除することができます (同じ例は Azure Portal で利用できます - AAD アプリ登録)。</span><span class="sxs-lookup"><span data-stu-id="8206c-142">For security reasons or in a case of a secret breach, the Patients app can re-generate the secret and invalidate or delete the old secret (example of the same is available in Azure Portal - AAD App Registration).</span></span>

4. <span data-ttu-id="8206c-143">準拠ステートメントをホストするメタデータ エンドポイントは認証されていない必要があります。認証トークンなしでアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="8206c-143">The metadata endpoint hosting the conformance statement should be un-authenticated, it should be accessible without authentication token.</span></span>

5. <span data-ttu-id="8206c-144">パートナー サービスは、患者アプリのトークン エンドポイントを提供し、クライアント資格情報フローを使用してアクセス トークンを要求します。</span><span class="sxs-lookup"><span data-stu-id="8206c-144">The Partner service provides the token endpoint for the Patients app to request an access token using a client credential flow.</span></span> <span data-ttu-id="8206c-145">承認サーバーごとのトークン URL は、次の例のように FHIR サーバー上のメタデータからフェッチされる FHIR 準拠 (機能) ステートメントの一部である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8206c-145">The token URL as per authorization server should be part of the FHIR conformance (capability) statement fetched from metadata on the FHIR server as in this example:</span></span>

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

<span data-ttu-id="8206c-146">アクセス トークンの要求は、次のパラメーターで構成されます。</span><span class="sxs-lookup"><span data-stu-id="8206c-146">A request for an access token consists of the following parameters:</span></span>

```http
POST /token HTTP/1.1
Host: authorization-server.com

grant-type=client_credentials
&client_id=xxxxxxxxxx
&client_secret=xxxxxxxxxx
```

<span data-ttu-id="8206c-147">パートナー サービスは、パートナー client_id認証client_secret認証登録ポータルを介して管理される患者用アプリの機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="8206c-147">The Partner service provides the client_id and client_secret for Patients app, managed via an Auth registration portal on the partner's side.</span></span> <span data-ttu-id="8206c-148">パートナー サービスは、クライアント資格情報フローを使用してアクセス トークンを要求するエンドポイントを提供します。</span><span class="sxs-lookup"><span data-stu-id="8206c-148">The Partner service provides the endpoint to request access token using a client credential flow.</span></span> <span data-ttu-id="8206c-149">正常に応答するには、パラメーター token_type、access_token、expires_inする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8206c-149">A successful response must include the token_type, access_token and expires_in parameters.</span></span>

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a><span data-ttu-id="8206c-150">ルーティング: AAD テナントをプロバイダー エンドポイントにマッピングする</span><span class="sxs-lookup"><span data-stu-id="8206c-150">Routing: Mapping AAD Tenant to the Provider endpoint</span></span>

<span data-ttu-id="8206c-151">患者アプリは、単一のエンドポイントを介してパートナー サービスに接続します。</span><span class="sxs-lookup"><span data-stu-id="8206c-151">The Patients app connects to a partner service through a single endpoint.</span></span> <span data-ttu-id="8206c-152">パートナー サービスは、各 Microsoft 顧客 (AAD テナント ID) をパートナー サービスが動作している各医療プロバイダー (FHIR サーバー) にマップするメカニズムを所有し、維持します。</span><span class="sxs-lookup"><span data-stu-id="8206c-152">The Partner service owns and maintains a mechanism to map each Microsoft customer (AAD Tenant ID) to a respective healthcare Provider (FHIR server) that the Partner service is working with.</span></span>

<span data-ttu-id="8206c-153">AAD テナントをプロバイダー エンドポイントにマッピングするには、AAD テナント ID (GUID) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="8206c-153">Mapping the AAD tenant to a provider endpoint uses the AAD Tenant ID (GUID).</span></span> <span data-ttu-id="8206c-154">患者アプリは、要求ごとにアクセス トークンを要求しながら、スコープ内のテナント ID を渡します。</span><span class="sxs-lookup"><span data-stu-id="8206c-154">The Patients app passes the Tenant ID in scope, while requesting an access-token for each request.</span></span> <span data-ttu-id="8206c-155">パートナー サービスは、テナント ID のプロバイダー エンドポイントへのマッピングを保持し、テナント ID に基づいて要求をプロバイダー エンドポイントにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="8206c-155">The Partner service keeps the mapping of Tenant ID to Provider endpoint and redirects requests to a provider endpoint based on the Tenant ID.</span></span> <span data-ttu-id="8206c-156">これを行うには、パートナーはエンドで構成をサポートします (プロバイダー組織の相互運用プラットフォームへのオンボーディングの一環として、手動で、またはポータル経由で行います)。</span><span class="sxs-lookup"><span data-stu-id="8206c-156">To do this, the partner supports the configuration on their end (manually or via a portal as part of onboarding of provider organizations to their Interop Platform).</span></span>

<span data-ttu-id="8206c-157">認証とルーティングのワークフローを次に示します。</span><span class="sxs-lookup"><span data-stu-id="8206c-157">The Authentication and Routing workflow is shown below:</span></span>

![認証とルーティングのワークフローの図](../../media/Patient-app-6.png)

1. <span data-ttu-id="8206c-159">送信によるアプリ アクセス トークンの要求:</span><span class="sxs-lookup"><span data-stu-id="8206c-159">Request for app access token by sending:</span></span>
 
    ```
    {   grant_type: client_credentials,
        client_id: xxxxxx, 
        client_secret: xxxxxx,
        scope: {Provider Identifier, Ex: tenant ID}
    }
    ```

2. <span data-ttu-id="8206c-160">アプリ トークンで返信する:</span><span class="sxs-lookup"><span data-stu-id="8206c-160">Reply with an app token:</span></span>

    ```
    {  access_token: {JWT, with scope: tenant ID},
       expires_in: 156678,
       token_type: "Bearer",
    }
    ```

3. <span data-ttu-id="8206c-161">Access トークンを使用して保護されたデータを要求します。</span><span class="sxs-lookup"><span data-stu-id="8206c-161">Request protected data with Access token.</span></span>

4. <span data-ttu-id="8206c-162">承認メッセージ: スコープ内のテナント ID からルーティングする適切な FHIR サーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="8206c-162">Authorization message: Select the appropriate FHIR server to route to from tenant ID in scope.</span></span>

5. <span data-ttu-id="8206c-163">アプリ トークンで認証した後、承認された FHIR サーバーからアプリで保護されたデータを送信します。</span><span class="sxs-lookup"><span data-stu-id="8206c-163">Sends the app protected  data from the authorized FHIR server after authenticating with the app token.</span></span>

## <a name="interfaces"></a><span data-ttu-id="8206c-164">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8206c-164">Interfaces</span></span>

<span data-ttu-id="8206c-165">患者アプリで使用される特定の呼び出しとフィールドは、次の記事に記載されています。</span><span class="sxs-lookup"><span data-stu-id="8206c-165">Specific calls and fields used by the Patients app are documented in the following articles.</span></span> <span data-ttu-id="8206c-166">FHIR サーバー/FHIR API に該当するインターフェイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="8206c-166">Select the interface applicable to your FHIR server/FHIR APIs.</span></span>

- [<span data-ttu-id="8206c-167">DSTU2 インターフェイスの仕様</span><span class="sxs-lookup"><span data-stu-id="8206c-167">DSTU2 interface specification</span></span>](dstu2-interface.md)
- [<span data-ttu-id="8206c-168">STU3 インターフェイスの仕様</span><span class="sxs-lookup"><span data-stu-id="8206c-168">STU3 interface specification</span></span>](stu3-interface.md)

## <a name="performance-and-reliability"></a><span data-ttu-id="8206c-169">パフォーマンスと信頼性</span><span class="sxs-lookup"><span data-stu-id="8206c-169">Performance and Reliability</span></span>

<span data-ttu-id="8206c-170">患者アプリがプライベート プレビューに表示されている間、エンドツーエンドのパフォーマンスに保証はありません。</span><span class="sxs-lookup"><span data-stu-id="8206c-170">While the Patients app is in private preview, there are no guarantees on the end-to-end performance.</span></span> <span data-ttu-id="8206c-171">パフォーマンスの要因には、正常性システムの環境での EHR から、FHIR Server や Office 365 エコシステムや患者アプリを含む相互運用パートナーとそのインフラストラクチャへの、ワークフローに関係するすべてのホップの相対的な遅延が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8206c-171">Factors in performance include the relative latencies of all the hops involved in the workflow, starting from the EHR in the health system's environment, to the Interop partner and their infra, including the FHIR Server and across to the Office 365 ecosystem and Patients app.</span></span>

![相互運用パートナーのパフォーマンスの図](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a><span data-ttu-id="8206c-173">FHIR の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="8206c-173">Get started with FHIR</span></span>  

<span data-ttu-id="8206c-174">FHIR を使い始め、Microsoft Teams EHR 統合インターフェイスに公開できる FHIR サーバーに簡単にアクセスする必要がある場合、Microsoft には、すべての開発者が使用できるオープン ソースの FHIR サーバーがあります。</span><span class="sxs-lookup"><span data-stu-id="8206c-174">If you're new to FHIR and need easy access to a FHIR Server that you can expose to the Microsoft Teams EHR integration interface, Microsoft has an open-source FHIR Server available for all developers to use.</span></span> <span data-ttu-id="8206c-175">Microsoft から利用可能なオープン ソースの FHIR Server の詳細 [については、「FHIR Server for Azure](/azure/healthcare-apis/overview-open-source-server) とは何か」の記事を参照し、組織に展開してください。</span><span class="sxs-lookup"><span data-stu-id="8206c-175">Please see the [What is FHIR Server for Azure](/azure/healthcare-apis/overview-open-source-server) article to learn more about the open source FHIR Server available from Microsoft and deploy it for your organizations.</span></span>

<span data-ttu-id="8206c-176">HSPC Open Sandbox EHR 環境を使用して EHR を作成することもできます。EHR は開いている FHIR サーバーもサポートし、これを使用して患者アプリで遊び回ります。</span><span class="sxs-lookup"><span data-stu-id="8206c-176">You can also use the HSPC Open sandbox EHR environment to create an an EHR which also supports an open FHIR Server and use this to play around with the Patients app.</span></span> <span data-ttu-id="8206c-177">HSPC サンドボックスのドキュメント [を参照することをお勧めします](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox)。</span><span class="sxs-lookup"><span data-stu-id="8206c-177">We recommend that you read through the [HSPC Sandbox documentation](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox).</span></span> <span data-ttu-id="8206c-178">サンドボックスは、患者の作成、追加、編集を簡単に行える UI 指向のユーザー向けの方法を提供するだけでなく、使用を開始するためのいくつかのサンプルも提供します。</span><span class="sxs-lookup"><span data-stu-id="8206c-178">Not only does the sandbox provide an easy, UI oriented, and user friendly way of creating, adding and editing Patients, it also gives you several samples to get started.</span></span>