---
title: Skype for Business Server 2015 で Web ダウンロード可能なクライアントを展開する
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 'ビジネス Web アプリケーションの概要: が、Skype を導入し、Skype 会議アプリケーションがビジネスの Skype を使用します。'
ms.openlocfilehash: a81e8744208261934635aee4f8a872a81b179c90
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2018
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server-2015"></a><span data-ttu-id="4ec77-103">Skype for Business Server 2015 で Web ダウンロード可能なクライアントを展開する</span><span class="sxs-lookup"><span data-stu-id="4ec77-103">Deploy Web downloadable clients in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4ec77-104">**の概要:** Skype のビジネス Web アプリケーションの展開し、Skype 会議アプリケーションがビジネスの Skype を使用します。</span><span class="sxs-lookup"><span data-stu-id="4ec77-104">**Summary:** Deploy the Skype for Business Web App and Skype Meetings App used with Skype for Business.</span></span>
  
<span data-ttu-id="4ec77-105">ビジネス Web アプリケーションの Skype は、クライアントのビジネスの Skype をまだ持っていない会議のユーザーにビジネス サーバー 2015 と配備されている既定のオン ・ デマンドで Skype を実行するサーバーでインストールされている、インターネット インフォメーション サービス (IIS) web クライアントです。</span><span class="sxs-lookup"><span data-stu-id="4ec77-105">Skype for Business Web App is an Internet Information Services (IIS) web client that is installed on the server running Skype for Business Server 2015 and default it is deployed on demand to meeting users who do not already have the Skype for Business client.</span></span> <span data-ttu-id="4ec77-106">このような会議ユーザーは通常ネットワークの外部から接続します。</span><span class="sxs-lookup"><span data-stu-id="4ec77-106">These meeting users are more often than not connecting from outside your network.</span></span> <span data-ttu-id="4ec77-107">ユーザーは会議 URL をクリックしたが、ビジネス クライアントがインストールされている Skype がない、常にユーザーにビジネス Web アプリケーションの最新バージョンの Skype を使用してミーティングに参加するためのオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4ec77-107">Whenever a user clicks a meeting URL but does not have the Skype for Business client installed, the user is presented with the option to join the meeting by using the latest version of Skype for Business Web App.</span></span>
  
<span data-ttu-id="4ec77-108">ビジネス Web アプリケーションは、ユーザーのブラウザーでプラグインとして使用される Microsoft ActiveX コントロールを必要とするは、Skype の機能を音声、ビデオ、および共有します。</span><span class="sxs-lookup"><span data-stu-id="4ec77-108">The voice, video, and sharing features in Skype for Business Web App require a Microsoft ActiveX control that is used as a plugin by the user's browser.</span></span> <span data-ttu-id="4ec77-109">ActiveX コントロールを事前にインストールするか、インストールするメッセージが表示されたら、初めてのビジネス Web アプリケーションの Skype を使用する場合は、ユーザーを許可するか、機能にアクセスする最初の時間が必要な ActiveX コントロールです。</span><span class="sxs-lookup"><span data-stu-id="4ec77-109">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Skype for Business Web App or the first time they access a feature that requires the ActiveX control.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4ec77-110">ビジネス 2015 エッジ サーバー展開では Skype は、境界ネットワークでの HTTPS のリバース プロキシは、クライアント アクセスのビジネス Web アプリケーションの Skype の必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ec77-110">In Skype for Business Server 2015 Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Skype for Business Web App client access.</span></span> <span data-ttu-id="4ec77-111">簡易 URL を発行する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="4ec77-111">You must also publish simple URLs.</span></span> <span data-ttu-id="4ec77-112">詳細については、[リバース プロキシ サーバーを設定](http://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx)し、[簡単な Url の計画](http://technet.microsoft.com/library/20e4f4b6-b7ff-4297-b00d-d1211ee800ac.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ec77-112">For details, see [Setting Up Reverse Proxy Servers](http://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) and [Planning for Simple URLs](http://technet.microsoft.com/library/20e4f4b6-b7ff-4297-b00d-d1211ee800ac.aspx).</span></span> 
  
## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a><span data-ttu-id="4ec77-113">Skype のビジネス Web アプリケーション用の多要素認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="4ec77-113">Enable Multi-Factor Authentication for Skype for Business Web App</span></span>
<span data-ttu-id="4ec77-114"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="4ec77-114"></span></span>

<span data-ttu-id="4ec77-115">ビジネス Web アプリケーションの Skype のビジネス サーバー 2015 のバージョンの Skype では、多要素認証をサポートします。</span><span class="sxs-lookup"><span data-stu-id="4ec77-115">The Skype for Business Server 2015 version of Skype for Business Web App supports multi-factor authentication.</span></span> <span data-ttu-id="4ec77-116">だけでなくユーザー名とパスワード、スマート カードまたは外部ネットワークからビジネス ・ ミーティングの Skype にサインインするときに参加するユーザーを認証するために、ピンなどの追加の認証方法を要求できます。</span><span class="sxs-lookup"><span data-stu-id="4ec77-116">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Skype for Business meetings.</span></span> <span data-ttu-id="4ec77-117">Active Directory フェデレーション サービス (AD FS) のフェデレーション サーバーを展開して、Skype のビジネス サーバー 2015 のパッシブの認証を有効にすることによって、多要素認証を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="4ec77-117">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Skype for Business Server 2015.</span></span> <span data-ttu-id="4ec77-118">AD FS を構成すると、Skype をビジネス ・ ミーティングに参加しようとする外部のユーザーが表示され、ユーザー名を格納する、AD FS の多要素認証の web ページとパスワードのこと、追加の認証方法と課題構成します。</span><span class="sxs-lookup"><span data-stu-id="4ec77-118">After AD FS is configured, external users who attempt to join Skype for Business meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4ec77-119">多要素認証の AD FS を構成する場合の重要な考慮事項を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4ec77-119">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span> 
  
- <span data-ttu-id="4ec77-p105">ADFS の多要素認証は、会議の参加者と開催者がともに同じ組織内に存在しているか、AD FS フェデレーション組織からのものである場合に機能します。ADFS の多要素認証は、Lync サーバーの Web インフラストラクチャでは現在サポートされていないため、Lync のフェデレーション ユーザーに対しては機能しません。</span><span class="sxs-lookup"><span data-stu-id="4ec77-p105">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization. Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span>
    
- <span data-ttu-id="4ec77-122">ハードウェア ロード バランサーを使用する場合、Skype のビジネス Web アプリケーション クライアントからのすべての要求は、同じフロント エンド サーバーによって処理されるよう、ロード バランサーの cookie の永続化を有効にします。</span><span class="sxs-lookup"><span data-stu-id="4ec77-122">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Skype for Business Web App client are handled by the same Front End Server.</span></span>
    
- <span data-ttu-id="4ec77-123">Skype ビジネス サーバーおよび AD FS サーバーの間で依存元パーティ信頼関係を確立するときに、ビジネス会議のため、Skype の最大長をスパンするのに十分な長さはトークンの有効期間を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4ec77-123">When you establish a relying party trust between Skype for Business Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Skype for Business meetings.</span></span> <span data-ttu-id="4ec77-124">通常、トークンの存続期間は 240 分で十分です。</span><span class="sxs-lookup"><span data-stu-id="4ec77-124">Typically, a token life of 240 minutes is sufficient.</span></span>
    
- <span data-ttu-id="4ec77-125">この構成は、Lync モバイル クライアントには適用されません。</span><span class="sxs-lookup"><span data-stu-id="4ec77-125">This configuration does not apply to Lync mobile clients.</span></span>
    
### <a name="configure-multi-factor-authentication"></a><span data-ttu-id="4ec77-126">多要素認証を構成する</span><span class="sxs-lookup"><span data-stu-id="4ec77-126">Configure Multi-Factor Authentication</span></span>

1. <span data-ttu-id="4ec77-127">AD FS フェデレーション サーバーの役割をインストールします。</span><span class="sxs-lookup"><span data-stu-id="4ec77-127">Install an AD FS federation server role.</span></span> <span data-ttu-id="4ec77-128">詳細については、 [Active Directory フェデレーション サービス 2.0 展開ガイド 』](https://go.microsoft.com/fwlink/p/?linkid=267511)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ec77-128">For details, see the [Active Directory Federation Services 2.0 Deployment Guide](https://go.microsoft.com/fwlink/p/?linkid=267511)</span></span>
    
2. <span data-ttu-id="4ec77-129">AD FS の証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="4ec77-129">Create certificates for AD FS.</span></span> <span data-ttu-id="4ec77-130">詳細についてを参照してください[「フェデレーション サーバーの証明書」](https://go.microsoft.com/fwlink/p/?LinkId=285376)のセクションのプランのシングル サインオンのトピックで使用するための AD FS の展開とします。</span><span class="sxs-lookup"><span data-stu-id="4ec77-130">For more information, see ["Federation server certificates"](https://go.microsoft.com/fwlink/p/?LinkId=285376) section of the Plan for and deploy AD FS for use with single sign-on topic.</span></span>
    
3. <span data-ttu-id="4ec77-131">Windows PowerShell コマンドライン インターフェイスは、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4ec77-131">From the Windows PowerShell command-line interface, run the following command:</span></span>
    
    ```
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. <span data-ttu-id="4ec77-132">次のコマンドを実行し、パートナーシップを確立します。</span><span class="sxs-lookup"><span data-stu-id="4ec77-132">Establish a partnership by running the following command:</span></span>
    
    ```
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. <span data-ttu-id="4ec77-133">以下の証明書利用者のルールを設定します。</span><span class="sxs-lookup"><span data-stu-id="4ec77-133">Set the following relying party rules:</span></span>
    
    ```
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   ```
 
   ```
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   ```

   ```
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a><span data-ttu-id="4ec77-134">BranchCache を無効にする </span><span class="sxs-lookup"><span data-stu-id="4ec77-134">Disable BranchCache</span></span>
<span data-ttu-id="4ec77-135"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="4ec77-135"></span></span>

<span data-ttu-id="4ec77-136">BranchCache 機能は、Windows 7 および Windows Server 2008 R2 は、ビジネス Web アプリケーションの web コンポーネントの Skype に干渉することができます。</span><span class="sxs-lookup"><span data-stu-id="4ec77-136">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Skype for Business Web App web components.</span></span> <span data-ttu-id="4ec77-137">Skype の問題を防ぐため、ビジネス Web アプリケーションのユーザーに対して、BranchCache が有効になっていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="4ec77-137">To prevent issues for Skype for Business Web App users, make sure that BranchCache is not enabled.</span></span> 
  
<span data-ttu-id="4ec77-138">、Branchcache を使用を無効にする方法の詳細は、Microsoft ダウンロード センターでの word 文書形式で使用可能な BranchCache の展開ガイドを参照してください[http://go.microsoft.com/fwlink/p/?LinkId=268788](http://go.microsoft.com/fwlink/p/?LinkId=268788)と Windows Server 2008 R2 テクニカル ライブラリ内に HTML 形式の[https://go.microsoft.com/fwlink/p/?LinkId=268789](https://go.microsoft.com/fwlink/p/?LinkId=268789)。</span><span class="sxs-lookup"><span data-stu-id="4ec77-138">For details about disabling BranchCache, see the BranchCache Deployment Guide, which is available in Word format at the Microsoft Download Center at [http://go.microsoft.com/fwlink/p/?LinkId=268788](http://go.microsoft.com/fwlink/p/?LinkId=268788) and in HTML format in the Windows Server 2008 R2 Technical Library at [https://go.microsoft.com/fwlink/p/?LinkId=268789](https://go.microsoft.com/fwlink/p/?LinkId=268789).</span></span>
  
## <a name="verifying-skype-for-business-web-app-deployment"></a><span data-ttu-id="4ec77-139">Skype のビジネス Web アプリケーションの配置の確認</span><span class="sxs-lookup"><span data-stu-id="4ec77-139">Verifying Skype for Business Web App Deployment</span></span>
<span data-ttu-id="4ec77-140"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="4ec77-140"></span></span>

<span data-ttu-id="4ec77-141">Test-CsUcwaConference コマンドレットを使用すると、2 人のテスト ユーザーが統合コミュニケーション Web API (UCWA) を使用して電話会議に参加できることを検証できます。</span><span class="sxs-lookup"><span data-stu-id="4ec77-141">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="4ec77-142">詳細については、このコマンドレットは、サーバー管理シェルのビジネス ドキュメントの Skype で[テスト CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ec77-142">For details about this cmdlet, see [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) in the Skype for Business Server Management Shell documentation.</span></span>
  
## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a><span data-ttu-id="4ec77-143">Windows Server 2008 R2 上のプラグインのインストールのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="4ec77-143">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>
<span data-ttu-id="4ec77-144"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="4ec77-144"></span></span>

<span data-ttu-id="4ec77-145">Windows Server 2008 R2 を実行しているコンピューター上のプラグインのインストールが失敗した場合は、Internet Explorer のセキュリティの設定または DisableMSI レジストリ キーの設定を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ec77-145">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>
  
### <a name="modify-the-security-setting-in-internet-explorer"></a><span data-ttu-id="4ec77-146">Internet Explorer のセキュリティ設定を変更する</span><span class="sxs-lookup"><span data-stu-id="4ec77-146">Modify the security setting in Internet Explorer</span></span>

1. <span data-ttu-id="4ec77-147">Internet Explorer を開きます。</span><span class="sxs-lookup"><span data-stu-id="4ec77-147">Open Internet Explorer.</span></span>
    
2. <span data-ttu-id="4ec77-148">[**ツール**]、[**インターネット オプション**]、[**詳細設定**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="4ec77-148">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>
    
3. <span data-ttu-id="4ec77-149">[**セキュリティ**] セクションまで下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="4ec77-149">Scroll down to the **Security** section.</span></span>
    
4. <span data-ttu-id="4ec77-150">[**暗号化されたページをディスクに保存しない**] チェック ボックスをオフにして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4ec77-150">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4ec77-151">選択した場合、この設定もエラーが発生ビジネス Web アプリケーションの Skype から添付ファイルをダウンロードしようとしています。</span><span class="sxs-lookup"><span data-stu-id="4ec77-151">If selected, this setting will also cause an error when trying to download an attachment from Skype for Business Web App.</span></span> 
  
5. <span data-ttu-id="4ec77-p111">会議にもう一度参加します。エラーが発生することなくプラグインがダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="4ec77-p111">Rejoin the meeting. The plug-in should download without errors.</span></span>
    
### <a name="modify-the-disablemsi-registry-setting"></a><span data-ttu-id="4ec77-154">DisableMSI レジストリ設定を変更する</span><span class="sxs-lookup"><span data-stu-id="4ec77-154">Modify the DisableMSI Registry setting</span></span>

1. <span data-ttu-id="4ec77-155">[**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4ec77-155">Click **Start**, and then click **Run**.</span></span>
    
2. <span data-ttu-id="4ec77-156">レジストリ エディターにアクセスするには、「**regedit**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="4ec77-156">To access the Registry Editor, type **regedit**.</span></span>
    
3. <span data-ttu-id="4ec77-157">HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer に移動します。</span><span class="sxs-lookup"><span data-stu-id="4ec77-157">Navigate to HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span></span>
    
4. <span data-ttu-id="4ec77-158">種類 REG_DWORD の DisableMSI レジストリ キーを編集または追加し、0 に設定します。</span><span class="sxs-lookup"><span data-stu-id="4ec77-158">Edit or add the DisableMSI registry key of type REG_DWORD and set it to 0.</span></span>
    
5. <span data-ttu-id="4ec77-159">会議にもう一度参加します。</span><span class="sxs-lookup"><span data-stu-id="4ec77-159">Rejoin the meeting.</span></span>
    
## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional"></a><span data-ttu-id="4ec77-160">Skype 会議アプリを有効にして Skype for Business Web App を置き換える (オプション)</span><span class="sxs-lookup"><span data-stu-id="4ec77-160">Enable Skype Meetings App to replace Skype for Business Web App (Optional)</span></span>
<span data-ttu-id="4ec77-161"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="4ec77-161"></span></span>

<span data-ttu-id="4ec77-162">この手順はオプションです。</span><span class="sxs-lookup"><span data-stu-id="4ec77-162">This procedure is optional.</span></span> <span data-ttu-id="4ec77-163">それを使用しない、外部ユーザーが引き続きビジネス Web アプリケーションの Skype を使用してミーティングに参加します。</span><span class="sxs-lookup"><span data-stu-id="4ec77-163">If you do not use it, external users will continue to join meetings using Skype for Business Web App.</span></span> 
  
### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a><span data-ttu-id="4ec77-164">簡素化された会議参加と Skype 会議アプリを有効にする</span><span class="sxs-lookup"><span data-stu-id="4ec77-164">Enable simplified meeting join and Skype Meetings App</span></span>

1. <span data-ttu-id="4ec77-165">ユーザーが CDN オンラインに接続し、Skype の会議アプリケーションを取得することがあり、単純化を使用して、コンテンツ配信ネットワーク (CDN) へのアクセスを有効にすると、会議の参加経験します。</span><span class="sxs-lookup"><span data-stu-id="4ec77-165">When you enable access to the Content Delivery Network (CDN), users will have the ability to connect to CDN online and get Skype Meetings App, and will use the simplified meeting join experience.</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. <span data-ttu-id="4ec77-166">クライアント側ログ「遠隔測定」会議からを許可する web ページまたはマイクロソフトのサーバー (false コマンドの既定値) に送信する Skype 会議アプリケーションに参加します。</span><span class="sxs-lookup"><span data-stu-id="4ec77-166">Allow client side logging telemetry from the meeting join web page or the Skype Meetings App to be sent to Microsoft servers (the command defaults to false).</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    <span data-ttu-id="4ec77-167">マイクロソフトに送信される情報が、 [Skype](https://support.office.com/en-us/article/Skype-for-Business-data-collection-practices-c17e8ea6-b83b-4345-9401-47a6c8b13aad?ui=en-US&amp;rs=en-US&amp;ad=US)を厳格に遵守します。</span><span class="sxs-lookup"><span data-stu-id="4ec77-167">Information sent to Microsoft is in strict compliance with [Skype for Business data collection practices](https://support.office.com/en-us/article/Skype-for-Business-data-collection-practices-c17e8ea6-b83b-4345-9401-47a6c8b13aad?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
    
3. <span data-ttu-id="4ec77-168">CDN を使用できない場合は、クリアテキストへのフォールバック Skype をローカルにホストされる Web アプリケーションのビジネス経験をする前にタイムアウトを設定します。</span><span class="sxs-lookup"><span data-stu-id="4ec77-168">Set the timeout before fall back to the locally hosted Skype for Business Web App experience if CDN isn't available.</span></span> <span data-ttu-id="4ec77-169">既定値は 6 秒です。</span><span class="sxs-lookup"><span data-stu-id="4ec77-169">The default value is 6 seconds.</span></span> <span data-ttu-id="4ec77-170">この値を 0 に設定すると、タイムアウトはなくなります。</span><span class="sxs-lookup"><span data-stu-id="4ec77-170">If this value is set to 0, there will be no timeout.</span></span>
    
   ```
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

## <a name="see-also"></a><span data-ttu-id="4ec77-171">この手順は役に立ちましたか? 役に立った場合は、この記事の下でお知らせください。役に立たなかった場合は、わかりにくかった部分をお知らせください。いただいたフィードバックを元に手順を再確認します。</span><span class="sxs-lookup"><span data-stu-id="4ec77-171">See also</span></span>
<span data-ttu-id="4ec77-172"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="4ec77-172"></span></span>

#### 

[<span data-ttu-id="4ec77-173">会議クライアント (Web アプリケーションおよび会議アプリケーション) の計画します。</span><span class="sxs-lookup"><span data-stu-id="4ec77-173">Plan for Meetings clients (Web App and Meetings App)</span></span>](../../plan-your-deployment/clients-and-devices/meetings-clients.md)
  
[<span data-ttu-id="4ec77-174">会議クライアント (Web アプリケーションおよび会議アプリケーション) の計画します。</span><span class="sxs-lookup"><span data-stu-id="4ec77-174">Plan for Meetings clients (Web App and Meetings App)</span></span>](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[<span data-ttu-id="4ec77-175">会議参加ページを構成します。</span><span class="sxs-lookup"><span data-stu-id="4ec77-175">Configuring the Meeting Join Page</span></span>](http://technet.microsoft.com/library/45880423-47f4-49af-b825-cbd8e3fc1046.aspx)
  
[<span data-ttu-id="4ec77-176">Microsoft Online Services のプライバシーに関する声明</span><span class="sxs-lookup"><span data-stu-id="4ec77-176">Microsoft Online Services Privacy Statement</span></span>](https://www.microsoft.com/en-us/privacystatement/OnlineServices/Default.aspx)
  
[<span data-ttu-id="4ec77-177">ライセンス契約の条項とマニュアル</span><span class="sxs-lookup"><span data-stu-id="4ec77-177">Licensing Terms and Documentation</span></span>](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)

