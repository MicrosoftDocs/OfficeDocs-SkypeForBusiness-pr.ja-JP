---
title: Skype for Business Server で Web ダウンロード可能なクライアントを展開する
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: '概要: Skype for Business Web App と Skype for Business で使用される Skype 会議アプリを展開します。'
ms.openlocfilehash: 20489dddb244b179908f8c8a565bb1f4d539a5a7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122131"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a><span data-ttu-id="c77cc-103">Skype for Business Server で Web ダウンロード可能なクライアントを展開する</span><span class="sxs-lookup"><span data-stu-id="c77cc-103">Deploy Web downloadable clients in Skype for Business Server</span></span>

<span data-ttu-id="c77cc-104">**概要:** Skype for Business Server で使用される Skype for Business 2015 Web App と Skype 会議アプリを展開します。</span><span class="sxs-lookup"><span data-stu-id="c77cc-104">**Summary:** Deploy the Skype for Business 2015 Web App and Skype Meetings App used with Skype for Business Server.</span></span>

<span data-ttu-id="c77cc-105">Skype for Business Web App は、Skype for Business Server を実行しているサーバーにインストールされているインターネット インフォメーション サービス (IIS) Web クライアントであり、既定では、Skype for Business クライアントを既に持ってない会議ユーザーにオンデマンドで展開されます。</span><span class="sxs-lookup"><span data-stu-id="c77cc-105">Skype for Business Web App is an Internet Information Services (IIS) web client that is installed on the server running Skype for Business Server and by default it is deployed on demand to meeting users who do not already have the Skype for Business client.</span></span> <span data-ttu-id="c77cc-106">これらの会議ユーザーは、ネットワークの外部から接続しないよりも頻繁に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c77cc-106">These meeting users are more often than not connecting from outside your network.</span></span> <span data-ttu-id="c77cc-107">ユーザーが会議の URL をクリックしても Skype for Business クライアントがインストールされていない場合は常に、Skype for Business Web App、Skype Meetings App、または Skype for Business for Mac の最新バージョンを使用して会議に参加するオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c77cc-107">Whenever a user clicks a meeting URL but does not have the Skype for Business client installed, the user is presented with the option to join the meeting by using the latest version of Skype for Business Web App, Skype Meetings App, or Skype for Business for Mac.</span></span>

<span data-ttu-id="c77cc-108">Skype for Business Web App の音声、ビデオ、および共有機能には、ユーザーのブラウザーでプラグインとして使用される Microsoft ActiveX コントロールが必要です。</span><span class="sxs-lookup"><span data-stu-id="c77cc-108">The voice, video, and sharing features in Skype for Business Web App require a Microsoft ActiveX control that is used as a plugin by the user's browser.</span></span> <span data-ttu-id="c77cc-109">ActiveX コントロールを事前にインストールするか、ユーザーが Skype for Business Web App を初めて使用する場合、または ActiveX コントロールを必要とする機能に初めてアクセスするときに、ユーザーにインストールを許可することができます。</span><span class="sxs-lookup"><span data-stu-id="c77cc-109">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Skype for Business Web App or the first time they access a feature that requires the ActiveX control.</span></span>

> [!NOTE]
> <span data-ttu-id="c77cc-110">Skype for Business Server Edge Server 展開では、Skype for Business Web App クライアント アクセスに境界ネットワーク内の HTTPS リバース プロキシが必要です。</span><span class="sxs-lookup"><span data-stu-id="c77cc-110">In Skype for Business Server Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Skype for Business Web App client access.</span></span> <span data-ttu-id="c77cc-111">また、簡易 URL も公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c77cc-111">You must also publish simple URLs.</span></span> <span data-ttu-id="c77cc-112">詳細については、「Skype [](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-reverse-proxy-servers) for Business Server での簡易 URL のリバース プロキシ サーバーと DNS 要件の設定[」を参照してください](../../plan-your-deployment/network-requirements/simple-urls.md)。</span><span class="sxs-lookup"><span data-stu-id="c77cc-112">For details, see [Setting Up Reverse Proxy Servers](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-reverse-proxy-servers) and [DNS requirements for simple URLs in Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).</span></span>

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a><span data-ttu-id="c77cc-113">Skype for Business Web App の多要素認証を有効にする</span><span class="sxs-lookup"><span data-stu-id="c77cc-113">Enable Multi-Factor Authentication for Skype for Business Web App</span></span>
<span data-ttu-id="c77cc-114"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="c77cc-114"><a name="MFA"> </a></span></span>

<span data-ttu-id="c77cc-115">Skype for Business Web App、Skype Meetings App、Skype for Business for Mac は多要素認証をサポートします。</span><span class="sxs-lookup"><span data-stu-id="c77cc-115">Skype for Business Web App,  Skype Meetings App, and Skype for Business for Mac support multi-factor authentication.</span></span> <span data-ttu-id="c77cc-116">ユーザー名とパスワードに加えて、Skype for Business 会議にサインインするときに外部ネットワークから参加しているユーザーを認証するために、スマート カードや PIN などの追加の認証方法を必要とすることができます。</span><span class="sxs-lookup"><span data-stu-id="c77cc-116">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Skype for Business meetings.</span></span> <span data-ttu-id="c77cc-117">多要素認証を有効にするには、Active Directory フェデレーション サービス (AD FS) フェデレーション サーバーを展開し、Skype for Business Server でパッシブ認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="c77cc-117">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Skype for Business Server.</span></span> <span data-ttu-id="c77cc-118">AD FS が構成された後、Skype for Business 会議に参加しようとする外部ユーザーには、ユーザー名とパスワードのチャレンジを含む AD FS 多要素認証 Web ページと、構成した追加の認証方法が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c77cc-118">After AD FS is configured, external users who attempt to join Skype for Business meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c77cc-119">多要素認証の AD FS を構成する場合の重要な考慮事項を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c77cc-119">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span>

- <span data-ttu-id="c77cc-120">多要素 ADFS 認証は、会議参加者と開催者の両方が同じ組織内にある場合、または FS フェデレーション組織の両方AD機能します。</span><span class="sxs-lookup"><span data-stu-id="c77cc-120">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization.</span></span> <span data-ttu-id="c77cc-121">多要素 ADFS 認証は、Lync サーバー Web インフラストラクチャが現在サポートしていないので、Lync フェデレーション ユーザーには機能しません。</span><span class="sxs-lookup"><span data-stu-id="c77cc-121">Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span>

- <span data-ttu-id="c77cc-122">ハードウェア ロード バランサーを使用する場合は、ロード バランサーで Cookie の永続性を有効にして、Skype for Business Web App または Meetings App クライアントからの要求すべてが同じフロントエンド サーバーによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="c77cc-122">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Skype for Business Web App or Meetings App clients are handled by the same Front End Server.</span></span>

- <span data-ttu-id="c77cc-123">Skype for Business Server と AD FS サーバーの間で証明書利用者の信頼を確立する場合は、Skype for Business 会議の最大長にまたがる十分な長さのトークンライフを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c77cc-123">When you establish a relying party trust between Skype for Business Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Skype for Business meetings.</span></span> <span data-ttu-id="c77cc-124">通常、トークンの存続期間は 240 分で十分です。</span><span class="sxs-lookup"><span data-stu-id="c77cc-124">Typically, a token life of 240 minutes is sufficient.</span></span>

- <span data-ttu-id="c77cc-125">この構成は、Lync モバイル クライアントには適用されません。</span><span class="sxs-lookup"><span data-stu-id="c77cc-125">This configuration does not apply to Lync mobile clients.</span></span>

### <a name="configure-multi-factor-authentication"></a><span data-ttu-id="c77cc-126">多要素認証の構成</span><span class="sxs-lookup"><span data-stu-id="c77cc-126">Configure Multi-Factor Authentication</span></span>

1. <span data-ttu-id="c77cc-127">AD FS フェデレーション サーバーの役割をインストールします。</span><span class="sxs-lookup"><span data-stu-id="c77cc-127">Install an AD FS federation server role.</span></span> <span data-ttu-id="c77cc-128">詳細については、「Active Directory フェデレーション サービス [2.0 展開ガイド」を参照してください。](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd807092(v=ws.10))</span><span class="sxs-lookup"><span data-stu-id="c77cc-128">For details, see the [Active Directory Federation Services 2.0 Deployment Guide](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd807092(v=ws.10))</span></span>

2. <span data-ttu-id="c77cc-129">FS の証明書をADします。</span><span class="sxs-lookup"><span data-stu-id="c77cc-129">Create certificates for AD FS.</span></span> <span data-ttu-id="c77cc-130">詳細については、「シングル サインオン [で](/previous-versions/azure/azure-services/jj205462(v=azure.100)) 使用する AD FS の計画と展開」の「フェデレーション サーバー証明書」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c77cc-130">For more information, see ["Federation server certificates"](/previous-versions/azure/azure-services/jj205462(v=azure.100)) section of the Plan for and deploy AD FS for use with single sign-on topic.</span></span>

3. <span data-ttu-id="c77cc-131">コマンド ライン Windows PowerShellから、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c77cc-131">From the Windows PowerShell command-line interface, run the following command:</span></span>

    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. <span data-ttu-id="c77cc-132">次のコマンドを実行し、パートナーシップを確立します。</span><span class="sxs-lookup"><span data-stu-id="c77cc-132">Establish a partnership by running the following command:</span></span>

    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. <span data-ttu-id="c77cc-133">以下の証明書利用者のルールを設定します。</span><span class="sxs-lookup"><span data-stu-id="c77cc-133">Set the following relying party rules:</span></span>

    ```powershell
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a><span data-ttu-id="c77cc-134">BranchCache を無効にする</span><span class="sxs-lookup"><span data-stu-id="c77cc-134">Disable BranchCache</span></span>
<span data-ttu-id="c77cc-135"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="c77cc-135"><a name="MFA"> </a></span></span>

<span data-ttu-id="c77cc-136">Windows 7 および Windows 7 の BranchCache 機能Windows Server 2008 R2 Skype for Business Web App Web コンポーネントに干渉する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c77cc-136">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Skype for Business Web App web components.</span></span> <span data-ttu-id="c77cc-137">Skype for Business Web App ユーザーの問題を防止するには、BranchCache が有効になっていないか確認してください。</span><span class="sxs-lookup"><span data-stu-id="c77cc-137">To prevent issues for Skype for Business Web App users, make sure that BranchCache is not enabled.</span></span>

<span data-ttu-id="c77cc-138">BranchCache の無効化の詳細については [、「BranchCache 展開ガイド」を参照してください](/windows-server/networking/branchcache/deploy/branchcache-deployment-guide)。</span><span class="sxs-lookup"><span data-stu-id="c77cc-138">For details about disabling BranchCache, see the [BranchCache Deployment Guide](/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).</span></span>

## <a name="verifying-skype-for-business-web-app-deployment"></a><span data-ttu-id="c77cc-139">Skype for Business Web App の展開の確認</span><span class="sxs-lookup"><span data-stu-id="c77cc-139">Verifying Skype for Business Web App Deployment</span></span>
<span data-ttu-id="c77cc-140"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="c77cc-140"><a name="MFA"> </a></span></span>

<span data-ttu-id="c77cc-141">Test-CsUcwaConference コマンドレットを使用すると、2 人のテスト ユーザーが統合コミュニケーション Web API (UCWA) を使用して会議に参加できることを検証できます。</span><span class="sxs-lookup"><span data-stu-id="c77cc-141">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="c77cc-142">このコマンドレットの詳細については、「Skype for Business Server Management Shell」のドキュメントの [「Test-CsUcwaConference」](/powershell/module/skype/test-csucwaconference?view=skype-ps) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c77cc-142">For details about this cmdlet, see [Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps) in the Skype for Business Server Management Shell documentation.</span></span>

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a><span data-ttu-id="c77cc-143">トラブルシューティング プラグイン インストール on Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="c77cc-143">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>
<span data-ttu-id="c77cc-144"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="c77cc-144"><a name="MFA"> </a></span></span>

<span data-ttu-id="c77cc-145">Windows Server 2008 R2 を実行しているコンピューターでプラグインのインストールが失敗した場合は、Internet Explorer セキュリティ設定または DisableMSI レジストリ キー設定を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c77cc-145">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>

### <a name="modify-the-security-setting-in-internet-explorer"></a><span data-ttu-id="c77cc-146">[セキュリティ] の設定を変更Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="c77cc-146">Modify the security setting in Internet Explorer</span></span>

1. <span data-ttu-id="c77cc-147">Internet Explorer を開きます。</span><span class="sxs-lookup"><span data-stu-id="c77cc-147">Open Internet Explorer.</span></span>

2. <span data-ttu-id="c77cc-148">[**ツール**]、[**インターネット オプション**]、[**詳細設定**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="c77cc-148">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>

3. <span data-ttu-id="c77cc-149">[**セキュリティ**] セクションまで下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="c77cc-149">Scroll down to the **Security** section.</span></span>

4. <span data-ttu-id="c77cc-150">[**暗号化されたページをディスクに保存しない**] チェック ボックスをオフにし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c77cc-150">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c77cc-151">この設定を選択すると、Skype for Business Web App から添付ファイルをダウンロードしようとするときにもエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="c77cc-151">If selected, this setting will also cause an error when trying to download an attachment from Skype for Business Web App.</span></span>

5. <span data-ttu-id="c77cc-152">会議にもう一度参加します。</span><span class="sxs-lookup"><span data-stu-id="c77cc-152">Rejoin the meeting.</span></span> <span data-ttu-id="c77cc-153">エラーが発生することなくプラグインがダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="c77cc-153">The plug-in should download without errors.</span></span>

### <a name="modify-the-disablemsi-registry-setting"></a><span data-ttu-id="c77cc-154">DisableMSI レジストリ設定を変更する</span><span class="sxs-lookup"><span data-stu-id="c77cc-154">Modify the DisableMSI Registry setting</span></span>

1. <span data-ttu-id="c77cc-155">[**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c77cc-155">Click **Start**, and then click **Run**.</span></span>

2. <span data-ttu-id="c77cc-156">レジストリ エディターにアクセスするには、「**regedit**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="c77cc-156">To access the Registry Editor, type **regedit**.</span></span>

3. <span data-ttu-id="c77cc-157">HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer に移動します。</span><span class="sxs-lookup"><span data-stu-id="c77cc-157">Navigate to HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span></span>

4. <span data-ttu-id="c77cc-158">種類 REG_DWORD の DisableMSI レジストリ キーを編集または追加し、0 に設定します。</span><span class="sxs-lookup"><span data-stu-id="c77cc-158">Edit or add the DisableMSI registry key of type REG_DWORD and set it to 0.</span></span>

5. <span data-ttu-id="c77cc-159">会議にもう一度参加します。</span><span class="sxs-lookup"><span data-stu-id="c77cc-159">Rejoin the meeting.</span></span>

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a><span data-ttu-id="c77cc-160">Skype 会議アプリを有効にして Skype for Business Web App を置き換える (オプション、Skype for Business Server 2015 のみ)</span><span class="sxs-lookup"><span data-stu-id="c77cc-160">Enable Skype Meetings App to replace Skype for Business Web App (Optional, Skype for Business Server 2015 only)</span></span>
<span data-ttu-id="c77cc-161"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="c77cc-161"><a name="SMA_Enable"> </a></span></span>

<span data-ttu-id="c77cc-162">この手順は省略可能で、Skype for Business Server 2015 CU5 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c77cc-162">This procedure is optional, and applies to Skype for Business Server 2015 CU5 and later.</span></span> <span data-ttu-id="c77cc-163">使用しない場合、外部ユーザーは引き続き Skype for Business Web App を使用して会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="c77cc-163">If you do not use it, external users will continue to join meetings using Skype for Business Web App.</span></span>

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a><span data-ttu-id="c77cc-164">簡単な会議参加と Skype 会議アプリを有効にする</span><span class="sxs-lookup"><span data-stu-id="c77cc-164">Enable simplified meeting join and Skype Meetings App</span></span>

1. <span data-ttu-id="c77cc-165">コンテンツ配信ネットワーク (CDN) へのアクセスを有効にした場合、ユーザーは CDN にオンラインで接続し、Skype Meetings App (Windows) と Skype for Business for Mac (Mac) を取得する機能を持ち、簡略化された会議参加エクスペリエンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="c77cc-165">When you enable access to the Content Delivery Network (CDN), users will have the ability to connect to CDN online and get Skype Meetings App (on Windows) and Skype for Business for Mac (on Mac), and will use the simplified meeting join experience.</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. <span data-ttu-id="c77cc-166">会議参加 Web ページまたは Skype Meetings App からのクライアント側のログ利用統計情報を Microsoft サーバーに送信できます (コマンドの既定値は false です)。</span><span class="sxs-lookup"><span data-stu-id="c77cc-166">Allow client side logging telemetry from the meeting join web page or the Skype Meetings App to be sent to Microsoft servers (the command defaults to false).</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    <span data-ttu-id="c77cc-167">Microsoft に送信される情報は、Skype for Business データ収集の [プラクティスに厳密に準拠しています](/skypeforbusiness/legal-and-regulatory/data-collection-practices)。</span><span class="sxs-lookup"><span data-stu-id="c77cc-167">Information sent to Microsoft is in strict compliance with [Skype for Business data collection practices](/skypeforbusiness/legal-and-regulatory/data-collection-practices).</span></span>

3. <span data-ttu-id="c77cc-168">CDN が利用できない場合は、ローカルでホストされている Skype for Business Web App エクスペリエンスにフォールバックする前にタイムアウトを設定します。</span><span class="sxs-lookup"><span data-stu-id="c77cc-168">Set the timeout before fall back to the locally hosted Skype for Business Web App experience if CDN isn't available.</span></span> <span data-ttu-id="c77cc-169">既定値は 6 秒です。</span><span class="sxs-lookup"><span data-stu-id="c77cc-169">The default value is 6 seconds.</span></span> <span data-ttu-id="c77cc-170">この値が 0 に設定されている場合、タイムアウトはありません。</span><span class="sxs-lookup"><span data-stu-id="c77cc-170">If this value is set to 0, there will be no timeout.</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> <span data-ttu-id="c77cc-171">Skype for Business Server 2015 累積的な更新プログラム 5 の MeetingUxUseCdn では、既定値は False に設定されます。</span><span class="sxs-lookup"><span data-stu-id="c77cc-171">With MeetingUxUseCdn in Skype for Business Server 2015 Cumulative Update 5, the default value is set to False.</span></span> <span data-ttu-id="c77cc-172">これにより、Skype for Business for Mac クライアントが、Skype for Business Admin が MeetingUxUseCdn を True に設定している場合でも、フェデレーションパートナー以外の会議にゲストとして参加できないという問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="c77cc-172">This causes an issue where Skype for Business for Mac client is unable to join non-federated partners' meetings as a guest, even if Skype for Business Admin has set MeetingUxUseCdn to True.</span></span> <span data-ttu-id="c77cc-173">これを機能するには、Skype for Business Server 2015 の累積的な更新プログラム 7、6.0.9319.534 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="c77cc-173">For this to work, Skype for Business Server 2015 must have the Cumulative Update 7, 6.0.9319.534, or later.</span></span> <span data-ttu-id="c77cc-174">「Enable [Skype Meetings App to replace Skype for Business Web App in Skype for Business Server 2015」を参照](https://support.microsoft.com/kb/4132312)してください。</span><span class="sxs-lookup"><span data-stu-id="c77cc-174">See [Enable Skype Meetings App to replace Skype for Business Web App in Skype for Business Server 2015](https://support.microsoft.com/kb/4132312).</span></span>


## <a name="see-also"></a><span data-ttu-id="c77cc-175">関連項目</span><span class="sxs-lookup"><span data-stu-id="c77cc-175">See also</span></span>
<span data-ttu-id="c77cc-176"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="c77cc-176"><a name="SMA_Enable"> </a></span></span>

[<span data-ttu-id="c77cc-177">会議クライアント用の計画 (Web アプリおよび会議アプリ)</span><span class="sxs-lookup"><span data-stu-id="c77cc-177">Plan for Meetings clients (Web App and Meetings App)</span></span>](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[<span data-ttu-id="c77cc-178">Skype for Business Server で会議参加ページを構成する</span><span class="sxs-lookup"><span data-stu-id="c77cc-178">Configure the meeting join page in Skype for Business Server</span></span>](../../manage/conferencing/meeting-join-page.md)

[<span data-ttu-id="c77cc-179">Microsoft のプライバシーに関する声明</span><span class="sxs-lookup"><span data-stu-id="c77cc-179">Microsoft Online Services Privacy Statement</span></span>](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx)

[<span data-ttu-id="c77cc-180">ライセンス条項とドキュメント</span><span class="sxs-lookup"><span data-stu-id="c77cc-180">Licensing Terms and Documentation</span></span>](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)