---
title: Skype for Business で先進認証 (ADAL) を使用する方法
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5ca71746-ead6-4e8c-90b1-461e846d1f4a
description: 現代の認証 (これは、Active Directory 認証ライブラリ (ADAL) と OAuth 2.0 に基づく) 2016年 3 月を参照しているを使用する方法を説明するビジネス サーバー 2015 の Skype のビジネス用の Skype 用の累積的な更新です。
ms.openlocfilehash: efd0e35ce92143e9fb5fda03301eb51d2926c979
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a><span data-ttu-id="60002-103">Skype for Business で先進認証 (ADAL) を使用する方法</span><span class="sxs-lookup"><span data-stu-id="60002-103">How to use Modern Authentication (ADAL) with Skype for Business</span></span>
 
<span data-ttu-id="60002-104">現代の認証 (これは、Active Directory 認証ライブラリ (ADAL) と OAuth 2.0 に基づく) 2016年 3 月を参照しているを使用する方法を説明するビジネス サーバー 2015 の Skype のビジネス用の Skype 用の累積的な更新です。</span><span class="sxs-lookup"><span data-stu-id="60002-104">This article explains how to use Modern Authentication (which is based on the Active Directory Authentication Library (ADAL) and OAuth 2.0) that can be found in the March 2016 Cumulative Update for Skype for Business for Skype for Business Server 2015.</span></span>
  
## <a name="whats-in-this-article"></a><span data-ttu-id="60002-105">この記事の内容</span><span class="sxs-lookup"><span data-stu-id="60002-105">What's in this article?</span></span>

[<span data-ttu-id="60002-106">ADAL とは</span><span class="sxs-lookup"><span data-stu-id="60002-106">What is ADAL?</span></span>](use-adal.md#BKMK_ADAL)
  
[<span data-ttu-id="60002-107">プールで ADAL を構成し、ADFS をセキュリティ トークン サーバーとして設定する</span><span class="sxs-lookup"><span data-stu-id="60002-107">Configure ADAL in your pool and set ADFS as security token server</span></span>](use-adal.md#BKMK_Config)
  
[<span data-ttu-id="60002-108">ADAL サインイン有効化のその他のオプション (Office クライアント アプリケーションなど)</span><span class="sxs-lookup"><span data-stu-id="60002-108">Other Options for Enabling ADAL sign-in (like Office client apps)</span></span>](use-adal.md#BKMK_Options)
  
[<span data-ttu-id="60002-109">先進認証 / ADAL がサポートされていないクライアント</span><span class="sxs-lookup"><span data-stu-id="60002-109">Clients where Modern Authentication / ADAL isn't Supported</span></span>](use-adal.md#BKMK_Support)
  
## <a name="what-is-adal"></a><span data-ttu-id="60002-110">ADAL とは</span><span class="sxs-lookup"><span data-stu-id="60002-110">What is ADAL?</span></span>
<span data-ttu-id="60002-111"><a name="BKMK_ADAL"> </a></span><span class="sxs-lookup"><span data-stu-id="60002-111"></span></span>

<span data-ttu-id="60002-112">ADAL は、'Active Directory Authentication Library (Active Directory 認証ライブラリ)' の頭文字であり、OAuth 2.0 と共に、先進認証の基礎となるものです。</span><span class="sxs-lookup"><span data-stu-id="60002-112">ADAL is the acronym for the 'Active Directory Authentication Library', and, along with OAuth 2.0, it is an underpinning of Modern Authentication.</span></span> <span data-ttu-id="60002-113">このコード ライブラリは、(ビジネス用の Skype) のようなセキュリティ トークンを使用してクライアント ・ アプリケーションに利用可能なディレクトリにセキュリティで保護されたリソースを作成するよう設計されています。</span><span class="sxs-lookup"><span data-stu-id="60002-113">This code library is designed to make secured resources in your directory available to client applications (like Skype for Business) via security tokens.</span></span> <span data-ttu-id="60002-114">ADAL は OAuth 2.0 と連携して、多要素認証 (MFA) やさまざまな形式の SAML Auth など、多様な認証および承認シナリオを可能にします。</span><span class="sxs-lookup"><span data-stu-id="60002-114">ADAL works with OAuth 2.0 to enable more authentication and authorization scenarios, like Multi-factor Authentication (MFA), and more forms of SAML Auth.</span></span>
  
<span data-ttu-id="60002-115">先進認証は、クライアントとして動作するさまざまなアプリがリソースのセキュリティ保護の手段として利用しています。</span><span class="sxs-lookup"><span data-stu-id="60002-115">A variety of apps that act as clients can leverage Modern Authentication for help in getting to secured resources.</span></span> <span data-ttu-id="60002-116">ビジネス サーバー 2015 の Skype は、オンプレミスのクライアントとオンプレミスのサーバー間でユーザーにリソースへの承認の適切なレベルを提供するためにこの技術を使用します。</span><span class="sxs-lookup"><span data-stu-id="60002-116">In Skype for Business Server 2015, this technology is used between on-premises clients and on-premises servers in order to give users a proper level of authorization to resources.</span></span>
  
<span data-ttu-id="60002-117">先進認証の通信 (ADAL と OAuth 2.0 をベースに使用) には次のような共通要素があります。</span><span class="sxs-lookup"><span data-stu-id="60002-117">Modern Authentication conversations (which are based on ADAL and OAuth 2.0) have some elements in common.</span></span>
  
- <span data-ttu-id="60002-118">リソースの要求を行うクライアントが、この場合、クライアントは、ビジネスの Skype です。</span><span class="sxs-lookup"><span data-stu-id="60002-118">There is a client making a request for a resource, in this case, the client is Skype for Business.</span></span>
    
- <span data-ttu-id="60002-119">クライアントが特定のレベルのアクセスを必要とするリソースがある、ディレクトリ サービスがこのリソースがセキュリティで保護されたリソースのビジネス サーバー 2015 の Skype はここで。</span><span class="sxs-lookup"><span data-stu-id="60002-119">There is a resource to which the client needs a specific level of access, and this resource is secured by a directory service, in this case the resource is Skype for Business Server 2015.</span></span>
    
- <span data-ttu-id="60002-120">OAuth の接続、つまり、他の接続がリソースにアクセスするユーザーを*承認*するのには専用です。</span><span class="sxs-lookup"><span data-stu-id="60002-120">There is an OAuth connection, in other words, a connection that is dedicated to  *authorizing*  a user to access a resource.</span></span> <span data-ttu-id="60002-121">(OAuth は 'サーバー' への認証に、わかりやすい名前で知られています、S2S と省略は、多くの場合)。</span><span class="sxs-lookup"><span data-stu-id="60002-121">(OAuth is also known by the more descriptive name, 'Server-to-Server' auth, and is often abbreviated as S2S.)</span></span>
    
<span data-ttu-id="60002-122">ビジネス サーバー 2015 最新認証 (ADAL) 会話の Skype、Skype ビジネス サーバー 2015 の ADFS (Windows Server 2012 R2 の ad FS 3.0) を介して通信します。</span><span class="sxs-lookup"><span data-stu-id="60002-122">In Skype for Business Server 2015 Modern Authentication (ADAL) conversations, Skype for Business Server 2015 communicates through ADFS (ADFS 3.0 in Windows Server 2012 R2).</span></span> <span data-ttu-id="60002-123">認証は、別の ID プロバイダー (IdP) を使用して行うことも可能ですが、Skype for Business Server は、ADFS と直接通信するよう構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60002-123">The authentication may happen using some other Identity Provider (IdP), but Skype for Business server needs to be configured to communicate with ADFS, directly.</span></span> <span data-ttu-id="60002-124">ビジネス サーバー 2015 の Skype 上で動作する ADFS を構成していない場合は、 [ad FS のインストール](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx)を完了してください。</span><span class="sxs-lookup"><span data-stu-id="60002-124">If you haven't configured ADFS to work with Skype for Business Server 2015 please complete the [ADFS installation](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).</span></span>
  
<span data-ttu-id="60002-125">ADAL は、2016年 3 月に含まれているビジネス サーバー 2015 年の Skype 用の累積的な更新および年 2016年 3 月のビジネスの**必要があります**Skype の累積的な更新プログラムをインストールし、正しい構成のために必要な。</span><span class="sxs-lookup"><span data-stu-id="60002-125">ADAL is included in the March 2016 Cumulative Update for Skype for Business Server 2015, and the March 2016 Cumulative Update for Skype for Business **must** be installed and is needed for successful configuration.</span></span>
  
> [!NOTE]
> <span data-ttu-id="60002-126">初期のリリースでは、オンプレミス環境での先進認証は、混成の Skype トポロジーが使用されていない場合のみのサポートとなります。</span><span class="sxs-lookup"><span data-stu-id="60002-126">During the initial release, Modern Authentication in an on-premises environment is supported only if there is no mixed Skype topology involved.</span></span> <span data-ttu-id="60002-127">環境がビジネス サーバー 2015 の Skype では純粋である場合などです。</span><span class="sxs-lookup"><span data-stu-id="60002-127">For example, if the environment is purely Skype for Business Server 2015.</span></span> <span data-ttu-id="60002-128">この記述は、変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="60002-128">This statement may be subject to change.</span></span> 
  
<span data-ttu-id="60002-129">正しい構成には、.ps1 ファイルと ADAL で使用するコマンドが収録された PowerShell パッケージをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="60002-129">A PowerShell package including .ps1 files with the commands used by ADAL must be downloaded for successful configuration.</span></span>
  
### <a name="configure-adal-in-your-pool-and-set-adfs-as-security-token-server"></a><span data-ttu-id="60002-130">プールで ADAL を構成し、ADFS をセキュリティ トークン サーバーとして設定する</span><span class="sxs-lookup"><span data-stu-id="60002-130">Configure ADAL in your pool and set ADFS as security token server</span></span>
<span data-ttu-id="60002-131"><a name="BKMK_Config"> </a></span><span class="sxs-lookup"><span data-stu-id="60002-131"></span></span>

<span data-ttu-id="60002-132">このプロセスでは、ADAL 用に構成されているビジネス サーバー 2015 プールに、Skype を ad FS のインストールを接続します。</span><span class="sxs-lookup"><span data-stu-id="60002-132">In this process, you connect your installation of ADFS to a Skype for Business Server 2015 pool that is configured for ADAL.</span></span>
  
1. <span data-ttu-id="60002-133">2016年 3 月をインストールする Skype、Skype をビジネス サーバー 2015 のプールのために、ビジネス サーバー 2015 または Standard Edition サーバーの累積的な更新プログラムです。</span><span class="sxs-lookup"><span data-stu-id="60002-133">Install the March 2016 Cumulative Update for Skype for Business Server 2015 to your Skype for Business Server 2015 pool or Standard Edition server.</span></span> <span data-ttu-id="60002-134">(スケジュール メンテナンス ウィンドウでは、必要に応じて、自動インストールの Windows Update を実行する。)</span><span class="sxs-lookup"><span data-stu-id="60002-134">(Schedule maintenance windows, as needed, to run Windows Update for the automatic installation.)</span></span>
    
2. <span data-ttu-id="60002-135">オンプレミス ad FS サーバーに、スクリプトのセットアップ-AdfsOAuthTrustForSfB[をダウンロードします](https://aka.ms/sfbadalscripts)。</span><span class="sxs-lookup"><span data-stu-id="60002-135">On your on-premises ADFS server(s), [download](https://aka.ms/sfbadalscripts) the Setup-AdfsOAuthTrustForSfB script.</span></span> <span data-ttu-id="60002-136">(ADFS ファームまたは独立の ADFS サーバーごとに実行するこの必要があります。</span><span class="sxs-lookup"><span data-stu-id="60002-136">(This needs to be done per ADFS farm or independent ADFS server(s).</span></span> <span data-ttu-id="60002-137">これは、必要はありません ADFS プロキシまたはプロキシで実行する)。</span><span class="sxs-lookup"><span data-stu-id="60002-137">It does not need to be done on ADFS Proxy or proxies).</span></span>
    
3. <span data-ttu-id="60002-138">内部のメモを行い、完全修飾ドメイン名 (Fqdn) をビジネス サーバー 2015 プールまたは Standard Edition サーバーは、Skype 用に外部の Web サービスです。</span><span class="sxs-lookup"><span data-stu-id="60002-138">Make a note of the internal and external Web Service fully qualified domain names (FQDNs) for your Skype for Business Server 2015 pool or Standard Edition server.</span></span> <span data-ttu-id="60002-139">この作業はすべての Skype for Business プールに必要です。</span><span class="sxs-lookup"><span data-stu-id="60002-139">This needs to be done for all the Skype for Business Pools.</span></span>
    
4. <span data-ttu-id="60002-p109">ADFS サーバーの PowerShell から、Setup-AdfsOAuthTrustForSfB を実行します。内部および外部の Web サービスの FQDN の正しい URL を入力する必要があります。以下は、実行例です。</span><span class="sxs-lookup"><span data-stu-id="60002-p109">From PowerShell on the ADFS Server(s), run the Setup-AdfsOAuthTrustForSfB. You will need to enter the proper URLs for the internal and external Web Service FQDNs. Here's an example:</span></span>
    
     `Setup-AdfsOAuthTrustForSfB.ps1 -poolIDs https://contosoSkype.contoso.com,https://contoso01Skype.contosoIn.com`
    
    <span data-ttu-id="60002-143">任意の追加のプール、Skype をビジネス サーバー 2015 依存する関係者を信頼して ADFS でのプールの Web サービスの Url を手動で追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60002-143">For any additional pools, you will need to add the Pool Web Services URLs manually to the Skype for Business Server 2015 Relying Party Trust in ADFS.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="60002-144">プールにパッシブ認証を使用して、ADAL も使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="60002-144">It isn't possible to use Passive Authentication for a Pool and also use ADAL.</span></span> <span data-ttu-id="60002-145">ADAL を使用するには、パッシブ認証を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="60002-145">You must disable Passive Authentication in order to use ADAL.</span></span> <span data-ttu-id="60002-146">プールの認証を設定する方法について、PowerShell コマンドレットは、[この](https://technet.microsoft.com/en-us/library/gg398396.aspx)資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60002-146">For PowerShell cmdlets on how to set authentication for a Pool see [this](https://technet.microsoft.com/en-us/library/gg398396.aspx) article.</span></span>
  
    > [!TIP]
    > <span data-ttu-id="60002-147">追加のプールが存在する場合、依存する関係者を信頼する ADFS で[識別子](https://technet.microsoft.com/en-us/library/gg557759%28v=ws.10%29.aspx)として追加する必要があります > には、ADFS サーバーと ad FS の管理] を開きます。</span><span class="sxs-lookup"><span data-stu-id="60002-147">If you have additional pools you need to add them as [Identifiers](https://technet.microsoft.com/en-us/library/gg557759%28v=ws.10%29.aspx) to the Relying Party Trust in ADFS.> Go to your ADFS server and open ADFS Management.</span></span> <span data-ttu-id="60002-148">信頼関係を拡大\>証明書利用者の関係者の信頼関係です。</span><span class="sxs-lookup"><span data-stu-id="60002-148">Expand Trust Relationships \> Relying Party Trusts.</span></span> <span data-ttu-id="60002-149">依存関係者に表示されている信頼とプロパティを右クリックして右クリックし\>識別子\>プール個の追加の URL を入力\>[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60002-149">Right-click the Relying Party Trust that's listed and right-click for Properties \> Identifiers \> type the additional Pool URL(s) \> click Add.</span></span> 
  
5. <span data-ttu-id="60002-150">ビジネス サーバー 2015 のフロント エンドまたは Standard Edition サーバーに対して、Skype に戻ります。</span><span class="sxs-lookup"><span data-stu-id="60002-150">Return to your Skype for Business Server 2015 Front End or Standard Edition server server.</span></span> <span data-ttu-id="60002-151">ここから OAuth サーバーを作成し、ビジネスの Skype を操作するには、その OAuth 構成を変更するコマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60002-151">From here you must run cmdlets that create an OAuth server and modify that OAuth configuration to work with Skype for Business.</span></span> <span data-ttu-id="60002-152">Skype ビジネス サーバー 2015 の展開ごとに 1 回この手順を行う必要があるだけです。</span><span class="sxs-lookup"><span data-stu-id="60002-152">You only need to do this step once per Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="60002-153">以下は、実行例です。</span><span class="sxs-lookup"><span data-stu-id="60002-153">Here is an example:</span></span>
    
     `New-CsOAuthServer -Identity sts.contosoIn.com -Type ADFS -MetadataURL https://sts.contosoIn.com/FederationMetadata/2007-06/FederationMetadata.xml`
    
    > [!TIP]
    > <span data-ttu-id="60002-154">このコマンドを参照してください 'Id' の URL は、実際には、ADFS フェデレーション サービス名でわかる ADFS 管理サービスを右クリックすると\>のプロパティです。</span><span class="sxs-lookup"><span data-stu-id="60002-154">The 'Identity' URL you see in this command is actually the ADFS Federation Service Name you can see in ADFS Management when you right-click Service \> Properties.</span></span> <span data-ttu-id="60002-155">'型' は、ADFS では常に、'MetadataURL' は、常に\<、ADFS サービス名\>+"/FederationMetadata/2007-06/FederationMetadata.xml"です。</span><span class="sxs-lookup"><span data-stu-id="60002-155">The 'Type' is always ADFS, and the 'MetadataURL' is always \<Your ADFS service name\> + "/FederationMetadata/2007-06/FederationMetadata.xml".</span></span> 
  
     `Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity sts.contosoIn.com`
    
6. <span data-ttu-id="60002-156">Skype ビジネス サーバー 2015 のフロント エンドまたは Standard Edition サーバーでは、まだ上のユーザーと、プールの FQDN、SIP アドレスを入力して新しい構成をテストします。</span><span class="sxs-lookup"><span data-stu-id="60002-156">Still on your Skype for Business Server 2015 Front End or Standard Edition server, test the new configuration by entering the SIP address of a user and the pool FQDN.</span></span> <span data-ttu-id="60002-157">Skype ビジネス サーバー 2015 の展開ごとに 1 回この手順を行う必要があるだけです。</span><span class="sxs-lookup"><span data-stu-id="60002-157">You only need to do this step once per Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="60002-158">以下は、実行例です。</span><span class="sxs-lookup"><span data-stu-id="60002-158">This is an example:</span></span>
    
     `Test-CsRegistration -UserSipAddress AyakaY@contosoIns.com -TargetFqdn Pool1.contoso.com -Authentication OAuthInteractive`
    
7. <span data-ttu-id="60002-p115">入力を求められたら、テスト ユーザーの資格情報を入力し、テストが正常に終了することを確認します。</span><span class="sxs-lookup"><span data-stu-id="60002-p115">When prompted, be sure to enter the credentials of the test user. Verify that the test completes successfully.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="60002-161">STS URL は、ADFS*内部的*に解決するときにプロンプトが表示されますが**Windows のセキュリティ**の確認になります。</span><span class="sxs-lookup"><span data-stu-id="60002-161">When your STS URL resolves to ADFS  *internally*  , the prompt you will see will be a **Windows Security** prompt.</span></span> <span data-ttu-id="60002-162">一方、URL が外部で解決した場合は、[**Sign in**] という名前のプロンプトになります。</span><span class="sxs-lookup"><span data-stu-id="60002-162">If the URL resolves externally, you'll see a prompt named **Sign in**.</span></span> <span data-ttu-id="60002-163">通常、ここで望ましいのは [**Windows Security**] プロンプトです。</span><span class="sxs-lookup"><span data-stu-id="60002-163">Typically, we would want a **Windows Security** prompt here.</span></span> <span data-ttu-id="60002-164">この動作は、特にフォーム ベース認証 (FBA) を実装していると、一貫しません。</span><span class="sxs-lookup"><span data-stu-id="60002-164">Note that this behaviour varies, particularly if you implemented Forms-Based Authentication (or FBA).</span></span>
  
<span data-ttu-id="60002-p117">また、STS URL が内部の ADFS に対して解決し、ブラウザーで統合 Windows 認証が有効になっていると、多くのユーザーがサインインするコンピューターでは、ブラウザーが、特定のブラウザー セキュリティ ゾーンでは資格情報を入力するよう明示的に構成されていない限り、認証に失敗することがあるので注意が必要です。キオスクを例に考えてみましょう。オペレーティング システムにログインしたアカウントは、Skype for Business クライアントにログインしているユーザー アカウントとは異なる場合があります。その場合、ここに記載のエラーが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="60002-p117">Also be aware, when the STS URL resolves to an internal ADFS server and Windows Integrated authentication is enabled in browsers, computers where many different users sign in to client applications may have failures to authenticate unless the browser is explicitly configured to prompt users for their credentials in a given browser Security Zone. Think of a kiosk as an example. The account that is logged in to the Operating System may be different than the user account logging into the Skype for Business client. If this is the case, you may see the failures described here.</span></span>
    
<span data-ttu-id="60002-169">参照してくださいし、] をクリックして Internet Explorer では、このブラウザー設定を変更することができます\>ツール (または着陸装置)\>インター ネット オプション\>[セキュリティ] タブ\>と、セキュリティ ゾーン (イントラネット)。</span><span class="sxs-lookup"><span data-stu-id="60002-169">You can see and change this browser setting in Internet Explorer by clicking \> Tools (or the Gear) \> Internet Options \> Security tab \> and the Security Zone (such as Local Intranet).</span></span> <span data-ttu-id="60002-170">このダイアログで、[レベルのカスタマイズ] ボタンをクリックし、[設定] ダイアログのリストの最後までスクロールします。</span><span class="sxs-lookup"><span data-stu-id="60002-170">From this dialog, click the Custom level button and scroll to the end of the list in the Settings dialog.</span></span> <span data-ttu-id="60002-171">[ユーザー認証] で\>ログイン\>'ユーザー名とパスワードの入力を求める] オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="60002-171">Under User Authentication \> Login \> you'll see an option to 'Prompt for user name and password'.</span></span> <span data-ttu-id="60002-172">Skype for Business クライアントを起動したユーザーが、コンピューターにログインしているユーザーと異なる (アカウントが異なる) キオスクを使用している場合は、グループ ポリシーでこれらのマシンに対してこのオプションをオンにしてテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="60002-172">If you have kiosks where the user who starts the Skype for Business client is different (has a different account) from the user logged into the computer, you may want to test setting this option to 'ON' for these machines in a Group Policy.</span></span>
    
<span data-ttu-id="60002-173">最後に、重要な点ですが、セキュリティ システムが情報を収集する中で、アカウントの認証または承認を必要とする場合、視覚情報の入力を複数回求められる場合があります。</span><span class="sxs-lookup"><span data-stu-id="60002-173">Finally, and importantly, you may experience more than one prompt as the security system collects the information it needs to authenticate or authorize your account.</span></span>
    
### <a name="other-options-for-enabling-adal-sign-in-like-office-client-apps"></a><span data-ttu-id="60002-174">ADAL サインイン有効化のその他のオプション (Office クライアント アプリケーションなど)</span><span class="sxs-lookup"><span data-stu-id="60002-174">Other Options for Enabling ADAL sign-in (like Office client apps)</span></span>
<span data-ttu-id="60002-175"><a name="BKMK_Options"> </a></span><span class="sxs-lookup"><span data-stu-id="60002-175"></span></span>

<span data-ttu-id="60002-176">ADAL はビジネスのため、Skype の設定 (自動的に) およびプラットフォーム間でクライアント アプリケーションを Office 2016、Exchange オンライン (場所は 'On' 既定で)、または Office 2013 のクライアントで利用することがあります。</span><span class="sxs-lookup"><span data-stu-id="60002-176">Now that ADAL is configured for your Skype for Business and (automatically) for Office 2016 client apps across platforms, you may want to leverage it for Exchange Online (where it is not 'On' by default), or in Office 2013 clients.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="60002-177">クライアント アプリケーションからの先進認証サインインで想定されることを確認する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="60002-177">Need to know what to expect from Modern Authentication sign-ins from your client apps?</span></span> <span data-ttu-id="60002-178">[Office 2013 および Office 2016 のクライアント アプリケーションの現在の認証のしくみ](https://support.office.com/en-us/article/How-modern-authentication-works-for-Office-2013-and-Office-2016-client-apps-e4c45989-4b1a-462e-a81b-2a13191cf517?ui=en-US&amp;rs=en-US&amp;ad=US)を見てください。</span><span class="sxs-lookup"><span data-stu-id="60002-178">Take a look at [How modern authentication works for Office 2013 and Office 2016 client apps](https://support.office.com/en-us/article/How-modern-authentication-works-for-Office-2013-and-Office-2016-client-apps-e4c45989-4b1a-462e-a81b-2a13191cf517?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span> 
  
<span data-ttu-id="60002-179">Exchange Online の最新の認証を有効に、いくつかの PowerShell コマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60002-179">To turn Modern Authentication on for Exchange Online, you'll need to run some PowerShell cmdlets.</span></span> <span data-ttu-id="60002-180">Office 2013 のクライアント アプリケーションの場合は、クライアント コンピューター上のいくつかのレジストリ キーを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60002-180">In the case of Office 2013 client apps, you will need to change some registry keys on client machines.</span></span>
  
- <span data-ttu-id="60002-181">Exchange Online に接続し、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="60002-181">Connect to Exchange Online and run the following cmdlets:</span></span>
    
     `Set-OrganizationConfig -OAuth2ClientProfileEnabled:$true`
    
     `Get-OrganizationConfig | ft name, *OAuth*`
    
- <span data-ttu-id="60002-182">次のレジストリ キーを、先進認証を有効にしたいデバイスまたはコンピューターごとに設定します。</span><span class="sxs-lookup"><span data-stu-id="60002-182">Set these registry keys for every device or computer on which you want to enable Modern Authentication.</span></span> <span data-ttu-id="60002-183">規模の大きな組織では GPO が必要になります。</span><span class="sxs-lookup"><span data-stu-id="60002-183">You will need a GPO in larger organizations.</span></span> <span data-ttu-id="60002-184">GPO を作成する方法についてを参照してください、'を作成するドメインの結合されたコンピューターでレジストリを変更するグループ ポリシー オブジェクト][この](https://support.office.com/en-us/article/Switching-between-the-Skype-for-Business-and-the-Lync-client-user-interfaces-a2394a4c-7522-484c-a047-7b3289742be0)資料の。</span><span class="sxs-lookup"><span data-stu-id="60002-184">For information on how to make a GPO, see the 'Create a Group Policy Object to modify the registry on a domain joined computer' of [this ](https://support.office.com/en-us/article/Switching-between-the-Skype-for-Business-and-the-Lync-client-user-interfaces-a2394a4c-7522-484c-a047-7b3289742be0)article.</span></span>
    
||||
|:-----|:-----|:-----|
|<span data-ttu-id="60002-185">レジストリ キー</span><span class="sxs-lookup"><span data-stu-id="60002-185">Registry Key</span></span>  <br/> |<span data-ttu-id="60002-186">型 </span><span class="sxs-lookup"><span data-stu-id="60002-186">Type</span></span>  <br/> |<span data-ttu-id="60002-187">値</span><span class="sxs-lookup"><span data-stu-id="60002-187">Value</span></span>  <br/> |
|<span data-ttu-id="60002-188">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="60002-188">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span>  <br/> |<span data-ttu-id="60002-189">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="60002-189">REG_DWORD</span></span>  <br/> |<span data-ttu-id="60002-190">1</span><span class="sxs-lookup"><span data-stu-id="60002-190">1</span></span>  <br/> |
|<span data-ttu-id="60002-191">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span><span class="sxs-lookup"><span data-stu-id="60002-191">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span></span>  <br/> |<span data-ttu-id="60002-192">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="60002-192">REG_DWORD</span></span>  <br/> |<span data-ttu-id="60002-193">1</span><span class="sxs-lookup"><span data-stu-id="60002-193">1</span></span>  <br/> |
   
<span data-ttu-id="60002-194">これらのキーを設定すると、 [Office 365 で多因子認証認証 (MFA) を使用](https://support.office.com/en-us/article/Set-up-multi-factor-authentication-for-Office-365-8f0454b2-f51a-4d9c-bcde-2c48e41621c6?ui=en-US&amp;rs=en-US&amp;ad=US)するのには、Office 2013 アプリケーションを設定します。</span><span class="sxs-lookup"><span data-stu-id="60002-194">Once these keys are set, set your Office 2013 apps to [use Multifactor Authentication (MFA) with Office 365](https://support.office.com/en-us/article/Set-up-multi-factor-authentication-for-Office-365-8f0454b2-f51a-4d9c-bcde-2c48e41621c6?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!TIP]
> <span data-ttu-id="60002-195">Office 2013 用のデバイスに最新の認証を無効にするには、ゼロの値に HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL レジストリ キーを設定します。</span><span class="sxs-lookup"><span data-stu-id="60002-195">To disable Modern Authentication on devices for Office 2013, set the HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL registry key to a value of zero.</span></span> <span data-ttu-id="60002-196">ようなレジストリ キー (HKCU\SOFTWARE\Microsoft\Office\ **16.0** \Common\Identity\EnableADAL) は、Office 2016 のデバイスの最新の認証を無効にするのにも使用するに注意します。</span><span class="sxs-lookup"><span data-stu-id="60002-196">Be aware that a similar Registry key (HKCU\SOFTWARE\Microsoft\Office\ **16.0** \Common\Identity\EnableADAL) can also be used to disable Modern Authentication on devices for Office 2016.</span></span>
  
### <a name="clients-where-modern-authentication--adal-isnt-supported"></a><span data-ttu-id="60002-197">先進認証 / ADAL がサポートされていないクライアント</span><span class="sxs-lookup"><span data-stu-id="60002-197">Clients where Modern Authentication / ADAL isn't Supported</span></span>
<span data-ttu-id="60002-198"><a name="BKMK_Support"> </a></span><span class="sxs-lookup"><span data-stu-id="60002-198"></span></span>

<span data-ttu-id="60002-p123">クライアントのバージョンによっては、OAuth をサポートしていないものがあります。コントロール パネルで Office クライアントのバージョンを確認できます。[プログラムの追加と削除] でバージョン番号を確認したら、以下に記載のバージョンと突き合わせてください。</span><span class="sxs-lookup"><span data-stu-id="60002-p123">Some client versions don't support OAuth. You can check your version of Office client in Control Panel where you Add and Remove programs in order to compare your version number to the versions (or ranges of versions) listed here:</span></span>
  
- <span data-ttu-id="60002-201">Office クライアント 15.0 です。0000-4766。\*</span><span class="sxs-lookup"><span data-stu-id="60002-201">Office Client 15.0.[0000-4766].\*</span></span>
    
- <span data-ttu-id="60002-202">Office クライアント 16.0。0000-4293。\*</span><span class="sxs-lookup"><span data-stu-id="60002-202">Office Client 16.0.[0000-4293].\*</span></span>
    
- <span data-ttu-id="60002-203">Office クライアント 16.0.6001.[0000-1032]</span><span class="sxs-lookup"><span data-stu-id="60002-203">Office Client 16.0.6001.[0000-1032]</span></span>
    
- <span data-ttu-id="60002-204">Office クライアント 16.0。6000-6224。\*</span><span class="sxs-lookup"><span data-stu-id="60002-204">Office Client 16.0.[6000-6224].\*</span></span>
    

