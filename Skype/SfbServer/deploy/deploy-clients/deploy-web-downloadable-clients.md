---
title: Skype for Business Server で Web ダウンロード可能なクライアントを展開する
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: '概要: skype for business で使用する Skype for Business Web App と Skype 会議アプリを展開します。'
ms.openlocfilehash: 7f6bebbc9950a7eb5da202c3b818b1288c811f17
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029048"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a><span data-ttu-id="f8b79-103">Skype for Business Server で Web ダウンロード可能なクライアントを展開する</span><span class="sxs-lookup"><span data-stu-id="f8b79-103">Deploy Web downloadable clients in Skype for Business Server</span></span>

<span data-ttu-id="f8b79-104">**概要:** Skype for business Server で使用する Skype for Business 2015 Web App と Skype 会議アプリを展開します。</span><span class="sxs-lookup"><span data-stu-id="f8b79-104">**Summary:** Deploy the Skype for Business 2015 Web App and Skype Meetings App used with Skype for Business Server.</span></span>

<span data-ttu-id="f8b79-105">Skype for Business Web App は、Skype for business Server を実行しているサーバーにインストールされるインターネットインフォメーションサービス (IIS) web クライアントであり、既定では、Skype for business クライアントをまだ持っていない会議のユーザーに対してはオンデマンドで展開されます。</span><span class="sxs-lookup"><span data-stu-id="f8b79-105">Skype for Business Web App is an Internet Information Services (IIS) web client that is installed on the server running Skype for Business Server and by default it is deployed on demand to meeting users who do not already have the Skype for Business client.</span></span> <span data-ttu-id="f8b79-106">これらの会議ユーザーは、多くの場合、ネットワークの外部から接続されていません。</span><span class="sxs-lookup"><span data-stu-id="f8b79-106">These meeting users are more often than not connecting from outside your network.</span></span> <span data-ttu-id="f8b79-107">ユーザーが会議 URL をクリックしても、Skype for Business クライアントがインストールされていない場合は、Skype for Business Web App、Skype 会議アプリ、または Skype for Business for Mac の最新バージョンを使用して、会議に参加するためのオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8b79-107">Whenever a user clicks a meeting URL but does not have the Skype for Business client installed, the user is presented with the option to join the meeting by using the latest version of Skype for Business Web App, Skype Meetings App, or Skype for Business for Mac.</span></span>

<span data-ttu-id="f8b79-108">Skype for Business Web App の音声、ビデオ、および共有機能には、ユーザーのブラウザーでプラグインとして使用される Microsoft ActiveX コントロールが必要です。</span><span class="sxs-lookup"><span data-stu-id="f8b79-108">The voice, video, and sharing features in Skype for Business Web App require a Microsoft ActiveX control that is used as a plugin by the user's browser.</span></span> <span data-ttu-id="f8b79-109">ActiveX コントロールを事前にインストールするか、要求されたときにユーザーにインストールを許可することができます。これは、ユーザーが初めて Skype for Business Web App を使用したとき、または ActiveX コントロールを必要とする機能に初めてアクセスしたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="f8b79-109">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Skype for Business Web App or the first time they access a feature that requires the ActiveX control.</span></span>

> [!NOTE]
> <span data-ttu-id="f8b79-110">Skype for Business Server エッジサーバーの展開では、Skype for Business Web App クライアントアクセスには、境界ネットワーク内の HTTPS リバースプロキシが必要です。</span><span class="sxs-lookup"><span data-stu-id="f8b79-110">In Skype for Business Server Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Skype for Business Web App client access.</span></span> <span data-ttu-id="f8b79-111">また、簡易 URL も公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8b79-111">You must also publish simple URLs.</span></span> <span data-ttu-id="f8b79-112">詳細については、「 [Skype For Business Server の簡易 url の](../../plan-your-deployment/network-requirements/simple-urls.md)[リバースプロキシサーバーの設定](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx)と DNS 要件」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8b79-112">For details, see [Setting Up Reverse Proxy Servers](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) and [DNS requirements for simple URLs in Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).</span></span>

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a><span data-ttu-id="f8b79-113">Skype for Business Web App で多要素認証を有効にする</span><span class="sxs-lookup"><span data-stu-id="f8b79-113">Enable Multi-Factor Authentication for Skype for Business Web App</span></span>
<span data-ttu-id="f8b79-114"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="f8b79-114"><a name="MFA"> </a></span></span>

<span data-ttu-id="f8b79-115">Skype for Business Web App、Skype 会議アプリ、および Skype for business for Mac では、多要素認証がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f8b79-115">Skype for Business Web App,  Skype Meetings App, and Skype for Business for Mac support multi-factor authentication.</span></span> <span data-ttu-id="f8b79-116">ユーザー名とパスワードに加えて、スマートカードや Pin などの追加の認証方法を要求して、外部ネットワークから参加しているユーザーが Skype for Business の会議にサインインしたときに認証を受けることができます。</span><span class="sxs-lookup"><span data-stu-id="f8b79-116">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Skype for Business meetings.</span></span> <span data-ttu-id="f8b79-117">Active Directory フェデレーションサービス (AD FS) フェデレーションサーバーを展開し、Skype for Business Server でパッシブ認証を有効にすることによって、多要素認証を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f8b79-117">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Skype for Business Server.</span></span> <span data-ttu-id="f8b79-118">AD FS を構成した後、Skype for Business 会議に参加しようとする外部ユーザーには、ユーザー名とパスワードのチャレンジと追加の認証方法を含む AD FS 多要素認証 web ページが表示されます。構成されている。</span><span class="sxs-lookup"><span data-stu-id="f8b79-118">After AD FS is configured, external users who attempt to join Skype for Business meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f8b79-119">多要素認証の AD FS を構成する場合の重要な考慮事項を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f8b79-119">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span>

- <span data-ttu-id="f8b79-120">複数要素 ADFS 認証は、会議の参加者と開催者が両方とも同じ組織内にあるか、または AD FS フェデレーション組織の両方にある場合に機能します。</span><span class="sxs-lookup"><span data-stu-id="f8b79-120">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization.</span></span> <span data-ttu-id="f8b79-121">Lync server web インフラストラクチャでは現在サポートされていないため、Lync フェデレーションユーザーは多要素 ADFS 認証を使用できません。</span><span class="sxs-lookup"><span data-stu-id="f8b79-121">Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span>

- <span data-ttu-id="f8b79-122">ハードウェアロードバランサーを使用する場合は、ロードバランサーの cookie 永続を有効にして、Skype for Business Web App または会議アプリクライアントからのすべての要求が同じフロントエンドサーバーによって処理されるようにします。</span><span class="sxs-lookup"><span data-stu-id="f8b79-122">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Skype for Business Web App or Meetings App clients are handled by the same Front End Server.</span></span>

- <span data-ttu-id="f8b79-123">Skype for Business Server と AD FS サーバー間で証明書利用者の信頼を確立するときには、Skype for Business 会議の最大長を長くするのに十分な長さのトークンライフサイクルを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f8b79-123">When you establish a relying party trust between Skype for Business Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Skype for Business meetings.</span></span> <span data-ttu-id="f8b79-124">通常、トークンの存続期間は 240 分で十分です。</span><span class="sxs-lookup"><span data-stu-id="f8b79-124">Typically, a token life of 240 minutes is sufficient.</span></span>

- <span data-ttu-id="f8b79-125">この構成は、Lync mobile クライアントには適用されません。</span><span class="sxs-lookup"><span data-stu-id="f8b79-125">This configuration does not apply to Lync mobile clients.</span></span>

### <a name="configure-multi-factor-authentication"></a><span data-ttu-id="f8b79-126">多要素認証を構成する</span><span class="sxs-lookup"><span data-stu-id="f8b79-126">Configure Multi-Factor Authentication</span></span>

1. <span data-ttu-id="f8b79-127">AD FS フェデレーション サーバーの役割をインストールします。</span><span class="sxs-lookup"><span data-stu-id="f8b79-127">Install an AD FS federation server role.</span></span> <span data-ttu-id="f8b79-128">詳細については、「 [Active Directory フェデレーションサービス2.0 展開ガイド](https://go.microsoft.com/fwlink/p/?linkid=267511)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8b79-128">For details, see the [Active Directory Federation Services 2.0 Deployment Guide](https://go.microsoft.com/fwlink/p/?linkid=267511)</span></span>

2. <span data-ttu-id="f8b79-129">AD FS の証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="f8b79-129">Create certificates for AD FS.</span></span> <span data-ttu-id="f8b79-130">詳細については、「計画と展開」の「AD FS を展開する」の「[フェデレーションサーバー証明書」](https://go.microsoft.com/fwlink/p/?LinkId=285376)セクションを参照してください。シングルサインオンのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8b79-130">For more information, see ["Federation server certificates"](https://go.microsoft.com/fwlink/p/?LinkId=285376) section of the Plan for and deploy AD FS for use with single sign-on topic.</span></span>

3. <span data-ttu-id="f8b79-131">Windows PowerShell コマンドラインインターフェイスで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f8b79-131">From the Windows PowerShell command-line interface, run the following command:</span></span>

    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. <span data-ttu-id="f8b79-132">次のコマンドを実行し、パートナーシップを確立します。</span><span class="sxs-lookup"><span data-stu-id="f8b79-132">Establish a partnership by running the following command:</span></span>

    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. <span data-ttu-id="f8b79-133">以下の証明書利用者のルールを設定します。</span><span class="sxs-lookup"><span data-stu-id="f8b79-133">Set the following relying party rules:</span></span>

    ```powershell
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a><span data-ttu-id="f8b79-134">BranchCache を無効にする</span><span class="sxs-lookup"><span data-stu-id="f8b79-134">Disable BranchCache</span></span>
<span data-ttu-id="f8b79-135"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="f8b79-135"><a name="MFA"> </a></span></span>

<span data-ttu-id="f8b79-136">Windows 7 および Windows Server 2008 R2 の BranchCache 機能は、Skype for Business Web App web コンポーネントに干渉する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f8b79-136">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Skype for Business Web App web components.</span></span> <span data-ttu-id="f8b79-137">Skype for Business Web App ユーザーの問題が発生しないようにするには、BranchCache が有効になっていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f8b79-137">To prevent issues for Skype for Business Web App users, make sure that BranchCache is not enabled.</span></span>

<span data-ttu-id="f8b79-138">BranchCache を無効にする方法の詳細については、「 [Branchcache 展開ガイド](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8b79-138">For details about disabling BranchCache, see the [BranchCache Deployment Guide](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).</span></span>

## <a name="verifying-skype-for-business-web-app-deployment"></a><span data-ttu-id="f8b79-139">Skype for Business Web App の展開を確認する</span><span class="sxs-lookup"><span data-stu-id="f8b79-139">Verifying Skype for Business Web App Deployment</span></span>
<span data-ttu-id="f8b79-140"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="f8b79-140"><a name="MFA"> </a></span></span>

<span data-ttu-id="f8b79-141">Test-CsUcwaConference コマンドレットを使用すると、2 人のテスト ユーザーが統合コミュニケーション Web API (UCWA) を使用して会議に参加できることを検証できます。</span><span class="sxs-lookup"><span data-stu-id="f8b79-141">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="f8b79-142">このコマンドレットの詳細については、「Skype for Business Server Management Shell」のドキュメントの「 [test-csucwaconference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8b79-142">For details about this cmdlet, see [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) in the Skype for Business Server Management Shell documentation.</span></span>

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a><span data-ttu-id="f8b79-143">Windows Server 2008 R2 でのプラグインのインストールのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="f8b79-143">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>
<span data-ttu-id="f8b79-144"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="f8b79-144"><a name="MFA"> </a></span></span>

<span data-ttu-id="f8b79-145">Windows Server 2008 R2 を実行しているコンピューターでプラグインのインストールが失敗した場合は、Internet Explorer のセキュリティ設定または DisableMSI レジストリキーの設定を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8b79-145">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>

### <a name="modify-the-security-setting-in-internet-explorer"></a><span data-ttu-id="f8b79-146">Internet Explorer のセキュリティ設定を変更する</span><span class="sxs-lookup"><span data-stu-id="f8b79-146">Modify the security setting in Internet Explorer</span></span>

1. <span data-ttu-id="f8b79-147">Internet Explorer を開きます。</span><span class="sxs-lookup"><span data-stu-id="f8b79-147">Open Internet Explorer.</span></span>

2. <span data-ttu-id="f8b79-148">[**ツール**]、[**インターネット オプション**]、[**詳細設定**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8b79-148">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>

3. <span data-ttu-id="f8b79-149">[**セキュリティ**] セクションまで下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="f8b79-149">Scroll down to the **Security** section.</span></span>

4. <span data-ttu-id="f8b79-150">[**暗号化されたページをディスクに保存しない**] チェック ボックスをオフにし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8b79-150">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f8b79-151">この設定を選択すると、Skype for Business Web App から添付ファイルをダウンロードしようとした場合にもエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="f8b79-151">If selected, this setting will also cause an error when trying to download an attachment from Skype for Business Web App.</span></span>

5. <span data-ttu-id="f8b79-152">会議にもう一度参加します。</span><span class="sxs-lookup"><span data-stu-id="f8b79-152">Rejoin the meeting.</span></span> <span data-ttu-id="f8b79-153">エラーが発生することなくプラグインがダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="f8b79-153">The plug-in should download without errors.</span></span>

### <a name="modify-the-disablemsi-registry-setting"></a><span data-ttu-id="f8b79-154">DisableMSI レジストリ設定を変更する</span><span class="sxs-lookup"><span data-stu-id="f8b79-154">Modify the DisableMSI Registry setting</span></span>

1. <span data-ttu-id="f8b79-155">[**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8b79-155">Click **Start**, and then click **Run**.</span></span>

2. <span data-ttu-id="f8b79-156">レジストリ エディターにアクセスするには、「**regedit**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="f8b79-156">To access the Registry Editor, type **regedit**.</span></span>

3. <span data-ttu-id="f8b79-157">HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer に移動します。</span><span class="sxs-lookup"><span data-stu-id="f8b79-157">Navigate to HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span></span>

4. <span data-ttu-id="f8b79-158">種類 REG_DWORD の DisableMSI レジストリ キーを編集または追加し、0 に設定します。</span><span class="sxs-lookup"><span data-stu-id="f8b79-158">Edit or add the DisableMSI registry key of type REG_DWORD and set it to 0.</span></span>

5. <span data-ttu-id="f8b79-159">会議にもう一度参加します。</span><span class="sxs-lookup"><span data-stu-id="f8b79-159">Rejoin the meeting.</span></span>

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a><span data-ttu-id="f8b79-160">Skype 会議アプリを有効にして Skype for Business Web App を置き換える (オプション、Skype for Business Server 2015 のみ)</span><span class="sxs-lookup"><span data-stu-id="f8b79-160">Enable Skype Meetings App to replace Skype for Business Web App (Optional, Skype for Business Server 2015 only)</span></span>
<span data-ttu-id="f8b79-161"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="f8b79-161"><a name="SMA_Enable"> </a></span></span>

<span data-ttu-id="f8b79-162">この手順はオプションであり、Skype for Business Server 2015 CU5 以降に適用されます。</span><span class="sxs-lookup"><span data-stu-id="f8b79-162">This procedure is optional, and applies to Skype for Business Server 2015 CU5 and later.</span></span> <span data-ttu-id="f8b79-163">これを使用しない場合、外部ユーザーは Skype for Business Web App を使用してミーティングに参加し続けます。</span><span class="sxs-lookup"><span data-stu-id="f8b79-163">If you do not use it, external users will continue to join meetings using Skype for Business Web App.</span></span>

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a><span data-ttu-id="f8b79-164">簡易会議参加と Skype 会議アプリを有効にする</span><span class="sxs-lookup"><span data-stu-id="f8b79-164">Enable simplified meeting join and Skype Meetings App</span></span>

1. <span data-ttu-id="f8b79-165">コンテンツ配信ネットワーク (CDN) へのアクセスを有効にすると、ユーザーは CDN online に接続して、Skype for business (Windows) および Skype for Business for Mac (on Mac) を取得し、簡単な会議参加の操作性を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f8b79-165">When you enable access to the Content Delivery Network (CDN), users will have the ability to connect to CDN online and get Skype Meetings App (on Windows) and Skype for Business for Mac (on Mac), and will use the simplified meeting join experience.</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. <span data-ttu-id="f8b79-166">会議参加 web ページまたは Skype 会議アプリのクライアント側のログテレメトリを Microsoft サーバーに送信できるようにします (既定では、このコマンドは false になります)。</span><span class="sxs-lookup"><span data-stu-id="f8b79-166">Allow client side logging telemetry from the meeting join web page or the Skype Meetings App to be sent to Microsoft servers (the command defaults to false).</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    <span data-ttu-id="f8b79-167">Microsoft に送信される情報は、 [Skype For business のデータ収集方法](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices)に厳密に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="f8b79-167">Information sent to Microsoft is in strict compliance with [Skype for Business data collection practices](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices).</span></span>

3. <span data-ttu-id="f8b79-168">CDN を使用できない場合は、ローカルにホストされている Skype for Business Web App 環境に戻す前にタイムアウトを設定します。</span><span class="sxs-lookup"><span data-stu-id="f8b79-168">Set the timeout before fall back to the locally hosted Skype for Business Web App experience if CDN isn't available.</span></span> <span data-ttu-id="f8b79-169">既定値は6秒です。</span><span class="sxs-lookup"><span data-stu-id="f8b79-169">The default value is 6 seconds.</span></span> <span data-ttu-id="f8b79-170">この値が0に設定されている場合は、タイムアウトはありません。</span><span class="sxs-lookup"><span data-stu-id="f8b79-170">If this value is set to 0, there will be no timeout.</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> <span data-ttu-id="f8b79-171">MeetingUxUseCdn With Skype for Business Server 2015 累積更新プログラム5では、既定値は False に設定されています。</span><span class="sxs-lookup"><span data-stu-id="f8b79-171">With MeetingUxUseCdn in Skype for Business Server 2015 Cumulative Update 5, the default value is set to False.</span></span> <span data-ttu-id="f8b79-172">このため、Skype for business 管理者が MeetingUxUseCdn を True に設定している場合でも、Skype for Business クライアントが、フェデレーションパートナーの会議にゲストとして参加できないという問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="f8b79-172">This causes an issue where Skype for Business for Mac client is unable to join non-federated partners' meetings as a guest, even if Skype for Business Admin has set MeetingUxUseCdn to True.</span></span> <span data-ttu-id="f8b79-173">この作業を行うには、Skype for Business Server 2015 に累積更新プログラム7、6.0.9319.534 がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8b79-173">For this to work, Skype for Business Server 2015 must have the Cumulative Update 7, 6.0.9319.534, or later.</span></span> <span data-ttu-id="f8b79-174">Skype for business [Server 2015 で skype for Business Web App を置き換えるには、「Skype 会議アプリを有効にする」を](https://support.microsoft.com/kb/4132312)参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8b79-174">See [Enable Skype Meetings App to replace Skype for Business Web App in Skype for Business Server 2015](https://support.microsoft.com/kb/4132312).</span></span>


## <a name="see-also"></a><span data-ttu-id="f8b79-175">関連項目</span><span class="sxs-lookup"><span data-stu-id="f8b79-175">See also</span></span>
<span data-ttu-id="f8b79-176"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="f8b79-176"><a name="SMA_Enable"> </a></span></span>

[<span data-ttu-id="f8b79-177">会議クライアントを計画する (Web アプリと会議アプリ)</span><span class="sxs-lookup"><span data-stu-id="f8b79-177">Plan for Meetings clients (Web App and Meetings App)</span></span>](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[<span data-ttu-id="f8b79-178">Skype for Business Server での会議参加ページの構成</span><span class="sxs-lookup"><span data-stu-id="f8b79-178">Configure the meeting join page in Skype for Business Server</span></span>](../../manage/conferencing/meeting-join-page.md)

[<span data-ttu-id="f8b79-179">Microsoft のプライバシーに関する声明</span><span class="sxs-lookup"><span data-stu-id="f8b79-179">Microsoft Online Services Privacy Statement</span></span>](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx)

[<span data-ttu-id="f8b79-180">ライセンス条項とドキュメント</span><span class="sxs-lookup"><span data-stu-id="f8b79-180">Licensing Terms and Documentation</span></span>](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)
