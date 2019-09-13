---
title: Skype for Business Server で Web ダウンロード可能なクライアントを展開する
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: '概要: skype for Business Web App および skype for Business で使用される Skype 会議アプリを展開します。'
ms.openlocfilehash: 273ffca9ae91973fe9e3953efc914364de382ed4
ms.sourcegitcommit: 8a20cb7bd1d23e2cf2987f55039748bad60f501b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2019
ms.locfileid: "36972878"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a><span data-ttu-id="be2c3-103">Skype for Business Server で Web ダウンロード可能なクライアントを展開する</span><span class="sxs-lookup"><span data-stu-id="be2c3-103">Deploy Web downloadable clients in Skype for Business Server</span></span>

<span data-ttu-id="be2c3-104">**概要:** Skype for Business 2015 Web App および skype for business Server で使用される Skype 会議アプリを展開します。</span><span class="sxs-lookup"><span data-stu-id="be2c3-104">**Summary:** Deploy the Skype for Business 2015 Web App and Skype Meetings App used with Skype for Business Server.</span></span>

<span data-ttu-id="be2c3-105">Skype for Business Web App は、Skype for Business Server を実行しているサーバーにインストールされたインターネットインフォメーションサービス (IIS) web クライアントであり、既定では、Skype for business クライアントをまだ持っていないユーザーとの会議のために、既定ではオンデマンドで展開されます。</span><span class="sxs-lookup"><span data-stu-id="be2c3-105">Skype for Business Web App is an Internet Information Services (IIS) web client that is installed on the server running Skype for Business Server and by default it is deployed on demand to meeting users who do not already have the Skype for Business client.</span></span> <span data-ttu-id="be2c3-106">このような会議ユーザーは通常ネットワークの外部から接続します。</span><span class="sxs-lookup"><span data-stu-id="be2c3-106">These meeting users are more often than not connecting from outside your network.</span></span> <span data-ttu-id="be2c3-107">ユーザーが会議 URL をクリックしたときに、Skype for business クライアントがインストールされていない場合は、最新バージョンの Skype for Business Web App、Skype 会議アプリ、または Skype for Business for Mac を使用して、会議に参加するためのオプションをユーザーに提示します。</span><span class="sxs-lookup"><span data-stu-id="be2c3-107">Whenever a user clicks a meeting URL but does not have the Skype for Business client installed, the user is presented with the option to join the meeting by using the latest version of Skype for Business Web App, Skype Meetings App, or Skype for Business for Mac.</span></span>

<span data-ttu-id="be2c3-108">Skype for Business Web App の音声、ビデオ、共有機能には、ユーザーのブラウザーでプラグインとして使用される Microsoft ActiveX コントロールが必要です。</span><span class="sxs-lookup"><span data-stu-id="be2c3-108">The voice, video, and sharing features in Skype for Business Web App require a Microsoft ActiveX control that is used as a plugin by the user's browser.</span></span> <span data-ttu-id="be2c3-109">事前に ActiveX コントロールをインストールするか、メッセージが表示されたときにユーザーがインストールできるようにすることができます。これは、Skype for Business Web App を初めて使用したとき、または ActiveX コントロールを必要とする機能に初めてアクセスしたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="be2c3-109">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Skype for Business Web App or the first time they access a feature that requires the ActiveX control.</span></span>

> [!NOTE]
> <span data-ttu-id="be2c3-110">Skype for Business Server Edge Server の展開では、Skype for Business Web App クライアントアクセスには境界ネットワーク内の HTTPS 逆プロキシが必要です。</span><span class="sxs-lookup"><span data-stu-id="be2c3-110">In Skype for Business Server Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Skype for Business Web App client access.</span></span> <span data-ttu-id="be2c3-111">簡易 URL を発行する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="be2c3-111">You must also publish simple URLs.</span></span> <span data-ttu-id="be2c3-112">詳細については、「 [Skype For Business Server の単純な url に対し](../../plan-your-deployment/network-requirements/simple-urls.md)て[リバースプロキシサーバー](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx)と DNS 要件を設定する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be2c3-112">For details, see [Setting Up Reverse Proxy Servers](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) and [DNS requirements for simple URLs in Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).</span></span>

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a><span data-ttu-id="be2c3-113">Skype for Business Web App の多要素認証を有効にする</span><span class="sxs-lookup"><span data-stu-id="be2c3-113">Enable Multi-Factor Authentication for Skype for Business Web App</span></span>
<span data-ttu-id="be2c3-114"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="be2c3-114"></span></span>

<span data-ttu-id="be2c3-115">Skype for Business Web App、Skype 会議アプリ、Skype for Business for Mac は多要素認証をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="be2c3-115">Skype for Business Web App,  Skype Meetings App, and Skype for Business for Mac support multi-factor authentication.</span></span> <span data-ttu-id="be2c3-116">ユーザー名とパスワードに加えて、Skype for Business 会議にサインインしたときに外部ネットワークから参加するユーザーを認証するために、スマートカードや Pin などの追加の認証方法が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="be2c3-116">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Skype for Business meetings.</span></span> <span data-ttu-id="be2c3-117">多要素認証を有効にするには、Active Directory フェデレーションサービス (AD FS) フェデレーションサーバーを展開し、Skype for Business Server でパッシブ認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="be2c3-117">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Skype for Business Server.</span></span> <span data-ttu-id="be2c3-118">AD FS を構成した後、Skype for Business 会議に参加しようとしている外部ユーザーには、ユーザー名とパスワードの問題と、その他の認証方法と共にその他の認証方法が含まれた、AD FS 多要素認証の web ページが表示されます。が設定されました。</span><span class="sxs-lookup"><span data-stu-id="be2c3-118">After AD FS is configured, external users who attempt to join Skype for Business meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="be2c3-119">多要素認証の AD FS を構成する場合の重要な考慮事項を次に示します。</span><span class="sxs-lookup"><span data-stu-id="be2c3-119">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span>

- <span data-ttu-id="be2c3-p105">ADFS の多要素認証は、会議の参加者と開催者がともに同じ組織内に存在しているか、AD FS フェデレーション組織からのものである場合に機能します。ADFS の多要素認証は、Lync サーバーの Web インフラストラクチャでは現在サポートされていないため、Lync のフェデレーション ユーザーに対しては機能しません。</span><span class="sxs-lookup"><span data-stu-id="be2c3-p105">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization. Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span>

- <span data-ttu-id="be2c3-122">ハードウェアロードバランサーを使用している場合は、Skype for Business Web App クライアントまたは会議アプリクライアントからのすべての要求が同じフロントエンドサーバーによって処理されるように、ロードバランサーの cookie の永続化を有効にします。</span><span class="sxs-lookup"><span data-stu-id="be2c3-122">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Skype for Business Web App or Meetings App clients are handled by the same Front End Server.</span></span>

- <span data-ttu-id="be2c3-123">Skype for Business Server と AD FS サーバー間で証明書利用者の信頼を確立する場合は、Skype for Business 会議の最大長に収まる長さのトークン寿命を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="be2c3-123">When you establish a relying party trust between Skype for Business Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Skype for Business meetings.</span></span> <span data-ttu-id="be2c3-124">通常、トークンの存続期間は 240 分で十分です。</span><span class="sxs-lookup"><span data-stu-id="be2c3-124">Typically, a token life of 240 minutes is sufficient.</span></span>

- <span data-ttu-id="be2c3-125">この構成は、Lync モバイル クライアントには適用されません。</span><span class="sxs-lookup"><span data-stu-id="be2c3-125">This configuration does not apply to Lync mobile clients.</span></span>

### <a name="configure-multi-factor-authentication"></a><span data-ttu-id="be2c3-126">多要素認証を構成する</span><span class="sxs-lookup"><span data-stu-id="be2c3-126">Configure Multi-Factor Authentication</span></span>

1. <span data-ttu-id="be2c3-127">AD FS フェデレーション サーバーの役割をインストールします。</span><span class="sxs-lookup"><span data-stu-id="be2c3-127">Install an AD FS federation server role.</span></span> <span data-ttu-id="be2c3-128">詳細については、 [Active Directory フェデレーションサービス2.0 展開ガイド](https://go.microsoft.com/fwlink/p/?linkid=267511)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be2c3-128">For details, see the [Active Directory Federation Services 2.0 Deployment Guide](https://go.microsoft.com/fwlink/p/?linkid=267511)</span></span>

2. <span data-ttu-id="be2c3-129">AD FS の証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="be2c3-129">Create certificates for AD FS.</span></span> <span data-ttu-id="be2c3-130">詳細については、「AD FS の計画と展開」の「[フェデレーションサーバーの証明書」](https://go.microsoft.com/fwlink/p/?LinkId=285376)セクションを参照してください。シングルサインオンのトピックで使うことができます。</span><span class="sxs-lookup"><span data-stu-id="be2c3-130">For more information, see ["Federation server certificates"](https://go.microsoft.com/fwlink/p/?LinkId=285376) section of the Plan for and deploy AD FS for use with single sign-on topic.</span></span>

3. <span data-ttu-id="be2c3-131">Windows PowerShell コマンドラインインターフェイスで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="be2c3-131">From the Windows PowerShell command-line interface, run the following command:</span></span>

    ```
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. <span data-ttu-id="be2c3-132">次のコマンドを実行し、パートナーシップを確立します。</span><span class="sxs-lookup"><span data-stu-id="be2c3-132">Establish a partnership by running the following command:</span></span>

    ```
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. <span data-ttu-id="be2c3-133">以下の証明書利用者のルールを設定します。</span><span class="sxs-lookup"><span data-stu-id="be2c3-133">Set the following relying party rules:</span></span>

    ```
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a><span data-ttu-id="be2c3-134">BranchCache を無効にする </span><span class="sxs-lookup"><span data-stu-id="be2c3-134">Disable BranchCache</span></span>
<span data-ttu-id="be2c3-135"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="be2c3-135"></span></span>

<span data-ttu-id="be2c3-136">Windows 7 および Windows Server 2008 R2 の BranchCache 機能は、Skype for Business Web App web コンポーネントを干渉する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="be2c3-136">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Skype for Business Web App web components.</span></span> <span data-ttu-id="be2c3-137">Skype for Business Web App ユーザーの問題を回避するには、BranchCache が有効になっていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="be2c3-137">To prevent issues for Skype for Business Web App users, make sure that BranchCache is not enabled.</span></span>

<span data-ttu-id="be2c3-138">BranchCache の無効化の詳細については、「 [branchcache の展開ガイド](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be2c3-138">For details about disabling BranchCache, see the [BranchCache Deployment Guide](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).</span></span>

## <a name="verifying-skype-for-business-web-app-deployment"></a><span data-ttu-id="be2c3-139">Skype for Business Web App の展開を確認する</span><span class="sxs-lookup"><span data-stu-id="be2c3-139">Verifying Skype for Business Web App Deployment</span></span>
<span data-ttu-id="be2c3-140"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="be2c3-140"></span></span>

<span data-ttu-id="be2c3-141">Test-CsUcwaConference コマンドレットを使用すると、2 人のテスト ユーザーが統合コミュニケーション Web API (UCWA) を使用して電話会議に参加できることを検証できます。</span><span class="sxs-lookup"><span data-stu-id="be2c3-141">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="be2c3-142">このコマンドレットの詳細については、「Skype for Business Server 管理シェルのドキュメントの[CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be2c3-142">For details about this cmdlet, see [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) in the Skype for Business Server Management Shell documentation.</span></span>

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a><span data-ttu-id="be2c3-143">Windows Server 2008 R2 でのプラグインのインストールのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="be2c3-143">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>
<span data-ttu-id="be2c3-144"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="be2c3-144"></span></span>

<span data-ttu-id="be2c3-145">Windows Server 2008 R2 を実行しているコンピューターでプラグインのインストールが失敗した場合は、Internet Explorer のセキュリティ設定または DisableMSI のレジストリキー設定を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be2c3-145">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>

### <a name="modify-the-security-setting-in-internet-explorer"></a><span data-ttu-id="be2c3-146">Internet Explorer のセキュリティ設定を変更する</span><span class="sxs-lookup"><span data-stu-id="be2c3-146">Modify the security setting in Internet Explorer</span></span>

1. <span data-ttu-id="be2c3-147">Internet Explorer を開きます。</span><span class="sxs-lookup"><span data-stu-id="be2c3-147">Open Internet Explorer.</span></span>

2. <span data-ttu-id="be2c3-148">[**ツール**]、[**インターネット オプション**]、[**詳細設定**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="be2c3-148">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>

3. <span data-ttu-id="be2c3-149">[**セキュリティ**] セクションまで下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="be2c3-149">Scroll down to the **Security** section.</span></span>

4. <span data-ttu-id="be2c3-150">[**暗号化されたページをディスクに保存しない**] チェック ボックスをオフにして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="be2c3-150">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="be2c3-151">この設定を選択すると、Skype for Business Web App から添付ファイルをダウンロードしようとしたときにもエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="be2c3-151">If selected, this setting will also cause an error when trying to download an attachment from Skype for Business Web App.</span></span>

5. <span data-ttu-id="be2c3-p111">会議にもう一度参加します。エラーが発生することなくプラグインがダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="be2c3-p111">Rejoin the meeting. The plug-in should download without errors.</span></span>

### <a name="modify-the-disablemsi-registry-setting"></a><span data-ttu-id="be2c3-154">DisableMSI レジストリ設定を変更する</span><span class="sxs-lookup"><span data-stu-id="be2c3-154">Modify the DisableMSI Registry setting</span></span>

1. <span data-ttu-id="be2c3-155">[**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="be2c3-155">Click **Start**, and then click **Run**.</span></span>

2. <span data-ttu-id="be2c3-156">レジストリ エディターにアクセスするには、「**regedit**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="be2c3-156">To access the Registry Editor, type **regedit**.</span></span>

3. <span data-ttu-id="be2c3-157">HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer に移動します。</span><span class="sxs-lookup"><span data-stu-id="be2c3-157">Navigate to HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span></span>

4. <span data-ttu-id="be2c3-158">種類 REG_DWORD の DisableMSI レジストリ キーを編集または追加し、0 に設定します。</span><span class="sxs-lookup"><span data-stu-id="be2c3-158">Edit or add the DisableMSI registry key of type REG_DWORD and set it to 0.</span></span>

5. <span data-ttu-id="be2c3-159">会議にもう一度参加します。</span><span class="sxs-lookup"><span data-stu-id="be2c3-159">Rejoin the meeting.</span></span>

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a><span data-ttu-id="be2c3-160">Skype for Business Web App の代わりに Skype 会議アプリを有効にする (オプション、Skype for Business Server 2015 のみ)</span><span class="sxs-lookup"><span data-stu-id="be2c3-160">Enable Skype Meetings App to replace Skype for Business Web App (Optional, Skype for Business Server 2015 only)</span></span>
<span data-ttu-id="be2c3-161"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="be2c3-161"></span></span>

<span data-ttu-id="be2c3-162">この手順はオプションであり、Skype for Business Server 2015 CU5 以降以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="be2c3-162">This procedure is optional, and applies to Skype for Business Server 2015 CU5 and later.</span></span> <span data-ttu-id="be2c3-163">このアプリを使用しない場合、外部ユーザーは Skype for Business Web App を使って会議に参加し続けることができます。</span><span class="sxs-lookup"><span data-stu-id="be2c3-163">If you do not use it, external users will continue to join meetings using Skype for Business Web App.</span></span>

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a><span data-ttu-id="be2c3-164">簡素化された会議参加と Skype 会議アプリを有効にする</span><span class="sxs-lookup"><span data-stu-id="be2c3-164">Enable simplified meeting join and Skype Meetings App</span></span>

1. <span data-ttu-id="be2c3-165">コンテンツ配信ネットワーク (CDN) へのアクセスを有効にすると、ユーザーは CDN online に接続して、Skype 会議アプリ (Windows 上) と Skype for Business for Mac (Mac) を入手して、簡単な会議の参加エクスペリエンスを利用することができます。</span><span class="sxs-lookup"><span data-stu-id="be2c3-165">When you enable access to the Content Delivery Network (CDN), users will have the ability to connect to CDN online and get Skype Meetings App (on Windows) and Skype for Business for Mac (on Mac), and will use the simplified meeting join experience.</span></span>

   ```
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. <span data-ttu-id="be2c3-166">会議参加 web ページまたは Skype 会議アプリからのクライアント側のログ利用統計情報を、Microsoft サーバーに送信することを許可します (コマンドは既定で false になります)。</span><span class="sxs-lookup"><span data-stu-id="be2c3-166">Allow client side logging telemetry from the meeting join web page or the Skype Meetings App to be sent to Microsoft servers (the command defaults to false).</span></span>

   ```
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    <span data-ttu-id="be2c3-167">Microsoft に送信される情報は、 [Skype For business のデータ収集方法](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices)に厳密に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="be2c3-167">Information sent to Microsoft is in strict compliance with [Skype for Business data collection practices](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices).</span></span>

3. <span data-ttu-id="be2c3-168">CDN が利用できない場合は、ローカルでホストされている Skype for Business Web App のエクスペリエンスに戻す前に、タイムアウトを設定します。</span><span class="sxs-lookup"><span data-stu-id="be2c3-168">Set the timeout before fall back to the locally hosted Skype for Business Web App experience if CDN isn't available.</span></span> <span data-ttu-id="be2c3-169">既定値は 6 秒です。</span><span class="sxs-lookup"><span data-stu-id="be2c3-169">The default value is 6 seconds.</span></span> <span data-ttu-id="be2c3-170">この値を 0 に設定すると、タイムアウトはなくなります。</span><span class="sxs-lookup"><span data-stu-id="be2c3-170">If this value is set to 0, there will be no timeout.</span></span>

   ```
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> <span data-ttu-id="be2c3-171">Skype for Business Server 2015 累積更新プログラム5の MeetingUxUseCdn では、既定値は False に設定されています。</span><span class="sxs-lookup"><span data-stu-id="be2c3-171">With MeetingUxUseCdn in Skype for Business Server 2015 Cumulative Update 5, the default value is set to False.</span></span> <span data-ttu-id="be2c3-172">Skype for business の管理者が MeetingUxUseCdn を True に設定している場合でも、Skype for Business for Mac クライアントが、フェデレーションパートナーの会議をゲストとして参加できないという問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="be2c3-172">This causes an issue where Skype for Business for Mac client is unable to join non-federated partners' meetings as a guest, even if Skype for Business Admin has set MeetingUxUseCdn to True.</span></span> <span data-ttu-id="be2c3-173">この機能を使用するには、Skype for Business Server 2015 の累積更新プログラム7、6.0.9319.534、またはそれ以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="be2c3-173">For this to work, Skype for Business Server 2015 must have the Cumulative Update 7, 6.0.9319.534, or later.</span></span> <span data-ttu-id="be2c3-174">Skype for business [Server 2015 で skype For Business Web app を置き換えるには、「Skype 会議アプリを有効にする」を](https://support.microsoft.com/kb/4132312)参照してください。</span><span class="sxs-lookup"><span data-stu-id="be2c3-174">See [Enable Skype Meetings App to replace Skype for Business Web App in Skype for Business Server 2015](https://support.microsoft.com/kb/4132312).</span></span>


## <a name="see-also"></a><span data-ttu-id="be2c3-175">関連項目</span><span class="sxs-lookup"><span data-stu-id="be2c3-175">See also</span></span>
<span data-ttu-id="be2c3-176"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="be2c3-176"></span></span>

[<span data-ttu-id="be2c3-177">会議クライアント用の計画 (Web アプリおよび会議アプリ)</span><span class="sxs-lookup"><span data-stu-id="be2c3-177">Plan for Meetings clients (Web App and Meetings App)</span></span>](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[<span data-ttu-id="be2c3-178">Skype for Business Server で会議の参加ページを構成する</span><span class="sxs-lookup"><span data-stu-id="be2c3-178">Configure the meeting join page in Skype for Business Server</span></span>](../../manage/conferencing/meeting-join-page.md)

[<span data-ttu-id="be2c3-179">Microsoft Online Services のプライバシーに関する声明</span><span class="sxs-lookup"><span data-stu-id="be2c3-179">Microsoft Online Services Privacy Statement</span></span>](https://www.microsoft.com/en-us/privacystatement/OnlineServices/Default.aspx)

[<span data-ttu-id="be2c3-180">ライセンス条項とドキュメント</span><span class="sxs-lookup"><span data-stu-id="be2c3-180">Licensing Terms and Documentation</span></span>](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)
