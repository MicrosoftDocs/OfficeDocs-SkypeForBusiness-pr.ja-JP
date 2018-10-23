---
title: Skype for Business で先進認証 (ADAL) を使用する方法
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5ca71746-ead6-4e8c-90b1-461e846d1f4a
description: 現代の認証 (これは、Active Directory 認証ライブラリ (ADAL) と OAuth 2.0 に基づく) 2016年 3 月を参照しているを使用する方法を説明するビジネス サーバー 2015 の Skype のビジネス用の Skype 用の累積的な更新です。
ms.openlocfilehash: 70878092baaee9414c8acada21a89ceea6587658
ms.sourcegitcommit: 6251a2c659909c3972ca2ea0a2bcdab4f334df34
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2018
ms.locfileid: "25692762"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a><span data-ttu-id="d8ba9-103">How to use Modern Authentication (ADAL) with Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d8ba9-103">How to use Modern Authentication (ADAL) with Skype for Business</span></span>
 
<span data-ttu-id="d8ba9-104">現代の認証 (これは、Active Directory 認証ライブラリ (ADAL) と OAuth 2.0 に基づく) 2016年 3 月を参照しているを使用する方法を説明するビジネス サーバー 2015 年または最初から、Skype のビジネス用の Skype 用の累積的な更新ビジネス サーバー 2019 の Skype をリリースします。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-104">This article explains how to use Modern Authentication (which is based on the Active Directory Authentication Library (ADAL) and OAuth 2.0) that can be found in the March 2016 Cumulative Update for Skype for Business for Skype for Business Server 2015, or from initial release for Skype for Business Server 2019.</span></span>
  
## <a name="whats-in-this-article"></a><span data-ttu-id="d8ba9-105">この記事の内容</span><span class="sxs-lookup"><span data-stu-id="d8ba9-105">What's in this article?</span></span>

[<span data-ttu-id="d8ba9-106">プールで ADAL を構成し、ADFS をセキュリティ トークン サーバーとして設定する</span><span class="sxs-lookup"><span data-stu-id="d8ba9-106">Configure ADAL in your pool and set ADFS as security token server</span></span>](use-adal.md#BKMK_Config)
  
[<span data-ttu-id="d8ba9-107">ADAL サインイン有効化のその他のオプション (Office クライアント アプリケーションなど)</span><span class="sxs-lookup"><span data-stu-id="d8ba9-107">Other Options for Enabling ADAL sign-in (like Office client apps)</span></span>](use-adal.md#BKMK_Options)
  
[<span data-ttu-id="d8ba9-108">先進認証 / ADAL がサポートされていないクライアント</span><span class="sxs-lookup"><span data-stu-id="d8ba9-108">Clients where Modern Authentication / ADAL isn't Supported</span></span>](use-adal.md#BKMK_Support)
  
### <a name="configure-adal-in-your-pool-and-set-adfs-as-security-token-server"></a><span data-ttu-id="d8ba9-109">プールで ADAL を構成し、ADFS をセキュリティ トークン サーバーとして設定する</span><span class="sxs-lookup"><span data-stu-id="d8ba9-109">Configure ADAL in your pool and set ADFS as security token server</span></span>
<span data-ttu-id="d8ba9-110"><a name="BKMK_Config"> </a></span><span class="sxs-lookup"><span data-stu-id="d8ba9-110"></span></span>

<span data-ttu-id="d8ba9-111">このプロセスでは、ADAL 用に構成されているビジネス サーバー プールに、Skype を ad FS のインストールを接続します。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-111">In this process, you connect your installation of ADFS to a Skype for Business Server pool that is configured for ADAL.</span></span>
  
1. <span data-ttu-id="d8ba9-112">2016年 3 月をインストール Skype ビジネス サーバー プールのため、Skype をビジネスのサーバー 2015 または Standard Edition サーバーの累積的な更新プログラムです。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-112">Install the March 2016 Cumulative Update for Skype for Business Server 2015 to your Skype for Business Server pool or Standard Edition server.</span></span> <span data-ttu-id="d8ba9-113">に、2016 年 3 月の  の累積更新プログラムをインストールします (必要に応じて、Windows Update を自動インストールで実行するよう、メンテナンス期間をスケジューリングします)。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-113">(Schedule maintenance windows, as needed, to run Windows Update for the automatic installation.)</span></span>
    
2. <span data-ttu-id="d8ba9-114">オンプレミス ad FS サーバーに、スクリプトのセットアップ-AdfsOAuthTrustForSfB[をダウンロードします](https://aka.ms/sfbadalscripts)。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-114">On your on-premises ADFS server(s), [download](https://aka.ms/sfbadalscripts) the Setup-AdfsOAuthTrustForSfB script.</span></span> <span data-ttu-id="d8ba9-115">(ADFS ファームまたは独立の ADFS サーバーごとに実行するこの必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-115">(This needs to be done per ADFS farm or independent ADFS server(s).</span></span> <span data-ttu-id="d8ba9-116">これは、必要はありません ADFS プロキシまたはプロキシで実行する)。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-116">It does not need to be done on ADFS Proxy or proxies).</span></span>
    
3. <span data-ttu-id="d8ba9-117">内部のメモを行い、完全修飾ドメイン名 (Fqdn) をビジネス サーバー プールまたは Standard Edition サーバーは、Skype 用に外部の Web サービスです。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-117">Make a note of the internal and external Web Service fully qualified domain names (FQDNs) for your Skype for Business Server pool or Standard Edition server.</span></span> <span data-ttu-id="d8ba9-118">この作業はすべての Skype for Business プールに必要です。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-118">This needs to be done for all the Skype for Business Pools.</span></span>
    
4. <span data-ttu-id="d8ba9-p104">ADFS サーバーの PowerShell から、Setup-AdfsOAuthTrustForSfB を実行します。内部および外部の Web サービスの FQDN の正しい URL を入力する必要があります。以下は、実行例です。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-p104">From PowerShell on the ADFS Server(s), run the Setup-AdfsOAuthTrustForSfB. You will need to enter the proper URLs for the internal and external Web Service FQDNs. Here's an example:</span></span>
    
     `Setup-AdfsOAuthTrustForSfB.ps1 -poolIDs https://contosoSkype.contoso.com,https://contoso01Skype.contosoIn.com`
    
    <span data-ttu-id="d8ba9-122">任意の追加のプール、Skype をビジネス サーバー依存関係者を信頼して ADFS でのプールの Web サービスの Url を手動で追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-122">For any additional pools, you will need to add the Pool Web Services URLs manually to the Skype for Business Server Relying Party Trust in ADFS.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d8ba9-123">プールにパッシブ認証を使用して、ADAL も使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-123">It isn't possible to use Passive Authentication for a Pool and also use ADAL.</span></span> <span data-ttu-id="d8ba9-124">ADAL を使用するには、パッシブ認証を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-124">You must disable Passive Authentication in order to use ADAL.</span></span> <span data-ttu-id="d8ba9-125">PowerShell コマンドレットでプールに対して認証を設定する方法については、[この記事](https://technet.microsoft.com/en-us/library/gg398396.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-125">For PowerShell cmdlets on how to set authentication for a Pool see [this](https://technet.microsoft.com/en-us/library/gg398396.aspx) article.</span></span>
  
    > [!TIP]
    > <span data-ttu-id="d8ba9-126">追加のプールが存在する場合、依存する関係者を信頼する ADFS で[識別子](https://technet.microsoft.com/en-us/library/gg557759%28v=ws.10%29.aspx)として追加する必要があります > には、ADFS サーバーと ad FS の管理] を開きます。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-126">If you have additional pools you need to add them as [Identifiers](https://technet.microsoft.com/en-us/library/gg557759%28v=ws.10%29.aspx) to the Relying Party Trust in ADFS.> Go to your ADFS server and open ADFS Management.</span></span> <span data-ttu-id="d8ba9-127">信頼関係を拡大\>証明書利用者の関係者の信頼関係です。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-127">Expand Trust Relationships \> Relying Party Trusts.</span></span> <span data-ttu-id="d8ba9-128">依存関係者に表示されている信頼とプロパティを右クリックして右クリックし\>識別子\>プール個の追加の URL を入力\>[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-128">Right-click the Relying Party Trust that's listed and right-click for Properties \> Identifiers \> type the additional Pool URL(s) \> click Add.</span></span> 
  
5. <span data-ttu-id="d8ba9-129">ビジネス サーバーのフロント エンドまたは Standard Edition サーバーに対して、Skype に戻ります。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-129">Return to your Skype for Business Server Front End or Standard Edition server server.</span></span> <span data-ttu-id="d8ba9-130">ここから OAuth サーバーを作成し、ビジネスの Skype を操作するには、その OAuth 構成を変更するコマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-130">From here you must run cmdlets that create an OAuth server and modify that OAuth configuration to work with Skype for Business.</span></span> <span data-ttu-id="d8ba9-131">ビジネス サーバー配置の Skype に 1 回この手順を行う必要があるだけです。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-131">You only need to do this step once per Skype for Business Server deployment.</span></span> <span data-ttu-id="d8ba9-132">以下は、実行例です。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-132">Here is an example:</span></span>
    
     `New-CsOAuthServer -Identity sts.contosoIn.com -Type ADFS -MetadataURL https://sts.contosoIn.com/FederationMetadata/2007-06/FederationMetadata.xml`
    
    > [!TIP]
    > <span data-ttu-id="d8ba9-133">このコマンドを参照してください 'Id' の URL は、実際には、ADFS フェデレーション サービス名でわかる ADFS 管理サービスを右クリックすると\>のプロパティです。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-133">The 'Identity' URL you see in this command is actually the ADFS Federation Service Name you can see in ADFS Management when you right-click Service \> Properties.</span></span> <span data-ttu-id="d8ba9-134">'型' は、ADFS では常に、'MetadataURL' は、常に\<、ADFS サービス名\>+"/FederationMetadata/2007-06/FederationMetadata.xml"です。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-134">The 'Type' is always ADFS, and the 'MetadataURL' is always \<Your ADFS service name\> + "/FederationMetadata/2007-06/FederationMetadata.xml".</span></span> 
  
     `Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity sts.contosoIn.com`
    
6. <span data-ttu-id="d8ba9-135">Skype ビジネス サーバーのフロント エンドまたは Standard Edition サーバーでは、まだ上のユーザーと、プールの FQDN、SIP アドレスを入力して新しい構成をテストします。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-135">Still on your Skype for Business Server Front End or Standard Edition server, test the new configuration by entering the SIP address of a user and the pool FQDN.</span></span> <span data-ttu-id="d8ba9-136">ビジネス サーバー配置の Skype に 1 回この手順を行う必要があるだけです。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-136">You only need to do this step once per Skype for Business Server deployment.</span></span> <span data-ttu-id="d8ba9-137">以下は、実行例です。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-137">This is an example:</span></span>
    
     `Test-CsRegistration -UserSipAddress AyakaY@contosoIns.com -TargetFqdn Pool1.contoso.com -Authentication OAuthInteractive`
    
7. <span data-ttu-id="d8ba9-138">ダイアログ ボックスが表示されたら、必ずテスト ユーザーの資格情報を入力してください。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-138">When prompted, be sure to enter the credentials of the test user.</span></span> <span data-ttu-id="d8ba9-139">テストが正常に完了していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-139">Verify that the test completes successfully.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d8ba9-140">STS URL は、ADFS*内部的*に解決するときにプロンプトが表示されますが**Windows のセキュリティ**の確認になります。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-140">When your STS URL resolves to ADFS  *internally*  , the prompt you will see will be a **Windows Security** prompt.</span></span> <span data-ttu-id="d8ba9-141">一方、URL が外部で解決した場合は、[**Sign in**] という名前のプロンプトになります。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-141">If the URL resolves externally, you'll see a prompt named **Sign in**.</span></span> <span data-ttu-id="d8ba9-142">通常、ここで望ましいのは [**Windows Security**] プロンプトです。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-142">Typically, we would want a **Windows Security** prompt here.</span></span> <span data-ttu-id="d8ba9-143">この動作は、特にフォーム ベース認証 (FBA) を実装していると、一貫しません。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-143">Note that this behaviour varies, particularly if you implemented Forms-Based Authentication (or FBA).</span></span>
  
<span data-ttu-id="d8ba9-p112">また、STS URL が内部の ADFS に対して解決し、ブラウザーで統合 Windows 認証が有効になっていると、多くのユーザーがサインインするコンピューターでは、ブラウザーが、特定のブラウザー セキュリティ ゾーンでは資格情報を入力するよう明示的に構成されていない限り、認証に失敗することがあるので注意が必要です。キオスクを例に考えてみましょう。オペレーティング システムにログインしたアカウントは、Skype for Business クライアントにログインしているユーザー アカウントとは異なる場合があります。その場合、ここに記載のエラーが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-p112">Also be aware, when the STS URL resolves to an internal ADFS server and Windows Integrated authentication is enabled in browsers, computers where many different users sign in to client applications may have failures to authenticate unless the browser is explicitly configured to prompt users for their credentials in a given browser Security Zone. Think of a kiosk as an example. The account that is logged in to the Operating System may be different than the user account logging into the Skype for Business client. If this is the case, you may see the failures described here.</span></span>
    
<span data-ttu-id="d8ba9-148">参照してくださいし、] をクリックして Internet Explorer では、このブラウザー設定を変更することができます\>ツール (または着陸装置)\>インター ネット オプション\>[セキュリティ] タブ\>と、セキュリティ ゾーン (イントラネット)。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-148">You can see and change this browser setting in Internet Explorer by clicking \> Tools (or the Gear) \> Internet Options \> Security tab \> and the Security Zone (such as Local Intranet).</span></span> <span data-ttu-id="d8ba9-149">このダイアログで、[レベルのカスタマイズ] ボタンをクリックし、[設定] ダイアログのリストの最後までスクロールします。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-149">From this dialog, click the Custom level button and scroll to the end of the list in the Settings dialog.</span></span> <span data-ttu-id="d8ba9-150">[ユーザー認証] で\>ログイン\>'ユーザー名とパスワードの入力を求める] オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-150">Under User Authentication \> Login \> you'll see an option to 'Prompt for user name and password'.</span></span> <span data-ttu-id="d8ba9-151">Skype for Business クライアントを起動したユーザーが、コンピューターにログインしているユーザーと異なる (アカウントが異なる) キオスクを使用している場合は、グループ ポリシーでこれらのマシンに対してこのオプションをオンにしてテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-151">If you have kiosks where the user who starts the Skype for Business client is different (has a different account) from the user logged into the computer, you may want to test setting this option to 'ON' for these machines in a Group Policy.</span></span>
    
<span data-ttu-id="d8ba9-152">最後に、重要な点ですが、セキュリティ システムが情報を収集する中で、アカウントの認証または承認を必要とする場合、視覚情報の入力を複数回求められる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-152">Finally, and importantly, you may experience more than one prompt as the security system collects the information it needs to authenticate or authorize your account.</span></span>
    
### <a name="other-options-for-enabling-adal-sign-in-like-office-client-apps"></a><span data-ttu-id="d8ba9-153">ADAL サインイン有効化のその他のオプション (Office クライアント アプリケーションなど)</span><span class="sxs-lookup"><span data-stu-id="d8ba9-153">Other Options for Enabling ADAL sign-in (like Office client apps)</span></span>
<span data-ttu-id="d8ba9-154"><a name="BKMK_Options"> </a></span><span class="sxs-lookup"><span data-stu-id="d8ba9-154"></span></span>

<span data-ttu-id="d8ba9-155">ADAL はビジネスのため、Skype の設定 (自動的に) およびプラットフォーム間でクライアント アプリケーションを Office 2016、Exchange オンライン (場所は 'On' 既定で)、または Office 2013 のクライアントで利用することがあります。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-155">Now that ADAL is configured for your Skype for Business and (automatically) for Office 2016 client apps across platforms, you may want to leverage it for Exchange Online (where it is not 'On' by default), or in Office 2013 clients.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d8ba9-156">クライアント アプリケーションからの先進認証サインインで想定されることを確認する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="d8ba9-156">Need to know what to expect from Modern Authentication sign-ins from your client apps?</span></span> <span data-ttu-id="d8ba9-157">[Office 2013 および Office 2016 のクライアント アプリケーションの現在の認証のしくみ](https://support.office.com/en-us/article/How-modern-authentication-works-for-Office-2013-and-Office-2016-client-apps-e4c45989-4b1a-462e-a81b-2a13191cf517?ui=en-US&amp;rs=en-US&amp;ad=US)を見てください。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-157">Take a look at [How modern authentication works for Office 2013 and Office 2016 client apps](https://support.office.com/en-us/article/How-modern-authentication-works-for-Office-2013-and-Office-2016-client-apps-e4c45989-4b1a-462e-a81b-2a13191cf517?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span> 
  
<span data-ttu-id="d8ba9-158">Exchange Online の最新の認証を有効に、いくつかの PowerShell コマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-158">To turn Modern Authentication on for Exchange Online, you'll need to run some PowerShell cmdlets.</span></span> <span data-ttu-id="d8ba9-159">Office 2013 のクライアント アプリケーションの場合は、クライアント コンピューター上のいくつかのレジストリ キーを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-159">In the case of Office 2013 client apps, you will need to change some registry keys on client machines.</span></span>
  
- <span data-ttu-id="d8ba9-160">Exchange Online に接続し、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-160">Connect to Exchange Online and run the following cmdlets:</span></span>
    
     `Set-OrganizationConfig -OAuth2ClientProfileEnabled:$true`
    
     `Get-OrganizationConfig | ft name, *OAuth*`
    
- <span data-ttu-id="d8ba9-161">次のレジストリ キーを、先進認証を有効にしたいデバイスまたはコンピューターごとに設定します。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-161">Set these registry keys for every device or computer on which you want to enable Modern Authentication.</span></span> <span data-ttu-id="d8ba9-162">規模の大きな組織では GPO が必要になります。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-162">You will need a GPO in larger organizations.</span></span> <span data-ttu-id="d8ba9-163">GPO を作成する方法についてを参照してください、'を作成するドメインの結合されたコンピューターでレジストリを変更するグループ ポリシー オブジェクト][この](https://support.office.com/en-us/article/Switching-between-the-Skype-for-Business-and-the-Lync-client-user-interfaces-a2394a4c-7522-484c-a047-7b3289742be0)資料の。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-163">For information on how to make a GPO, see the 'Create a Group Policy Object to modify the registry on a domain joined computer' of [this ](https://support.office.com/en-us/article/Switching-between-the-Skype-for-Business-and-the-Lync-client-user-interfaces-a2394a4c-7522-484c-a047-7b3289742be0)article.</span></span>
    
|<span data-ttu-id="d8ba9-164">レジストリ キー</span><span class="sxs-lookup"><span data-stu-id="d8ba9-164">Registry Key</span></span>  <br/> |<span data-ttu-id="d8ba9-165">型</span><span class="sxs-lookup"><span data-stu-id="d8ba9-165">Type</span></span>  <br/> |<span data-ttu-id="d8ba9-166">値</span><span class="sxs-lookup"><span data-stu-id="d8ba9-166">Value</span></span>  <br/> |
|:-----|:-----|:-----|
|<span data-ttu-id="d8ba9-167">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="d8ba9-167">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span>  <br/> |<span data-ttu-id="d8ba9-168">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="d8ba9-168">REG_DWORD</span></span>  <br/> |<span data-ttu-id="d8ba9-169">1</span><span class="sxs-lookup"><span data-stu-id="d8ba9-169">1</span></span>  <br/> |
|<span data-ttu-id="d8ba9-170">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span><span class="sxs-lookup"><span data-stu-id="d8ba9-170">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span></span>  <br/> |<span data-ttu-id="d8ba9-171">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="d8ba9-171">REG_DWORD</span></span>  <br/> |<span data-ttu-id="d8ba9-172">1</span><span class="sxs-lookup"><span data-stu-id="d8ba9-172">1</span></span>  <br/> |
   
<span data-ttu-id="d8ba9-173">これらのキーを設定すると、 [Office 365 で多因子認証認証 (MFA) を使用](https://support.office.com/en-us/article/Set-up-multi-factor-authentication-for-Office-365-8f0454b2-f51a-4d9c-bcde-2c48e41621c6?ui=en-US&amp;rs=en-US&amp;ad=US)する Office アプリケーションを設定します。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-173">Once these keys are set, set your Office apps to [use Multifactor Authentication (MFA) with Office 365](https://support.office.com/en-us/article/Set-up-multi-factor-authentication-for-Office-365-8f0454b2-f51a-4d9c-bcde-2c48e41621c6?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!TIP]
> <span data-ttu-id="d8ba9-174">Office 2013 用のデバイスに最新の認証を無効にするには、ゼロの値に HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL レジストリ キーを設定します。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-174">To disable Modern Authentication on devices for Office 2013, set the HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL registry key to a value of zero.</span></span> <span data-ttu-id="d8ba9-175">ようなレジストリ キー (HKCU\SOFTWARE\Microsoft\Office\ **16.0** \Common\Identity\EnableADAL) は、Office 2016 のデバイスの最新の認証を無効にするのにも使用するに注意します。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-175">Be aware that a similar Registry key (HKCU\SOFTWARE\Microsoft\Office\ **16.0** \Common\Identity\EnableADAL) can also be used to disable Modern Authentication on devices for Office 2016.</span></span>
  
### <a name="clients-where-modern-authentication--adal-isnt-supported"></a><span data-ttu-id="d8ba9-176">先進認証 / ADAL がサポートされていないクライアント</span><span class="sxs-lookup"><span data-stu-id="d8ba9-176">Clients where Modern Authentication / ADAL isn't Supported</span></span>
<span data-ttu-id="d8ba9-177"><a name="BKMK_Support"> </a></span><span class="sxs-lookup"><span data-stu-id="d8ba9-177"></span></span>

<span data-ttu-id="d8ba9-p118">クライアントのバージョンによっては、OAuth をサポートしていないものがあります。コントロール パネルで Office クライアントのバージョンを確認できます。[プログラムの追加と削除] でバージョン番号を確認したら、以下に記載のバージョンと突き合わせてください。</span><span class="sxs-lookup"><span data-stu-id="d8ba9-p118">Some client versions don't support OAuth. You can check your version of Office client in Control Panel where you Add and Remove programs in order to compare your version number to the versions (or ranges of versions) listed here:</span></span>
  
- <span data-ttu-id="d8ba9-180">Office クライアント 15.0 です。0000-4766。\*</span><span class="sxs-lookup"><span data-stu-id="d8ba9-180">Office Client 15.0.[0000-4766].\*</span></span>
    
- <span data-ttu-id="d8ba9-181">Office クライアント 16.0。0000-4293。\*</span><span class="sxs-lookup"><span data-stu-id="d8ba9-181">Office Client 16.0.[0000-4293].\*</span></span>
    
- <span data-ttu-id="d8ba9-182">Office クライアント 16.0.6001.[0000-1032]</span><span class="sxs-lookup"><span data-stu-id="d8ba9-182">Office Client 16.0.6001.[0000-1032]</span></span>
    
- <span data-ttu-id="d8ba9-183">Office クライアント 16.0。6000-6224。\*</span><span class="sxs-lookup"><span data-stu-id="d8ba9-183">Office Client 16.0.[6000-6224].\*</span></span>
    

