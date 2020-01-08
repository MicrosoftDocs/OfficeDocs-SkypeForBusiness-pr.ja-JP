---
title: 'Lync Server 2013: Lync Web App の展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Lync Web App
ms:assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205190(v=OCS.15)
ms:contentKeyID: 48185189
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c355be1c1709cede9c032d59790d6beefb337ff6
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971136"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-web-app-in-lync-server-2013"></a><span data-ttu-id="d99ff-102">Lync Server 2013 での Lync Web App の展開</span><span class="sxs-lookup"><span data-stu-id="d99ff-102">Deploying Lync Web App in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d99ff-103">_**最終更新日:** 2013-07-18_</span><span class="sxs-lookup"><span data-stu-id="d99ff-103">_**Topic Last Modified:** 2013-07-18_</span></span>

<span data-ttu-id="d99ff-104">Lync Web App は、Lync Server 2013 と共にインストールされるインターネットインフォメーションサービス (IIS) web クライアントであり、既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="d99ff-104">Lync Web App is an Internet Information Services (IIS) web client that installs with Lync Server 2013 and is enabled by default.</span></span> <span data-ttu-id="d99ff-105">サーバーで Lync Web App を有効にするか、web クライアントをユーザーに展開するために、追加の手順は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="d99ff-105">No additional steps are necessary to either enable Lync Web App on the server or deploy the web client to users.</span></span> <span data-ttu-id="d99ff-106">ユーザーが会議 URL をクリックしたときに、Lync 2013 クライアントがインストールされていない場合は、最新バージョンの Lync Web App を使って会議に参加するためのオプションがユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d99ff-106">Whenever a user clicks a meeting URL but does not have the Lync 2013 client installed, the user is presented with the option to join the meeting by using the latest version of Lync Web App.</span></span>

<span data-ttu-id="d99ff-107">Lync Web App の音声、ビデオ、共有機能には、Microsoft ActiveX コントロールが必要です。</span><span class="sxs-lookup"><span data-stu-id="d99ff-107">The voice, video, and sharing features in Lync Web App require a Microsoft ActiveX control.</span></span> <span data-ttu-id="d99ff-108">事前に ActiveX コントロールをインストールするか、メッセージが表示されたときにユーザーがアプリをインストールできるようにすることができます。これは、Lync Web App を初めて使用したとき、または ActiveX コントロールを必要とする機能に初めてアクセスしたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="d99ff-108">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Lync Web App or the first time they access a feature that requires the ActiveX control.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="d99ff-109">Lync Server 2013 Edge Server 展開では、Lync Web App クライアントへのアクセスには、境界ネットワーク内の HTTPS 逆プロキシが必要です。</span><span class="sxs-lookup"><span data-stu-id="d99ff-109">In Lync Server 2013 Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Lync Web App client access.</span></span> <span data-ttu-id="d99ff-110">簡易 URL を発行する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="d99ff-110">You must also publish simple URLs.</span></span> <span data-ttu-id="d99ff-111">詳細については、「 <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Lync server 2013 用のリバースプロキシサーバーをセットアップする</A>」および「 <A href="lync-server-2013-planning-for-simple-urls.md">lync server 2013 で簡単な url を計画</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d99ff-111">For details, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> and <A href="lync-server-2013-planning-for-simple-urls.md">Planning for simple URLs in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-web-app"></a><span data-ttu-id="d99ff-112">Lync Web App の多要素認証を有効にする</span><span class="sxs-lookup"><span data-stu-id="d99ff-112">Enabling Multi-Factor Authentication for Lync Web App</span></span>

<span data-ttu-id="d99ff-113">Lync Server 2013 バージョンの Lync Web App では、多要素認証がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d99ff-113">The Lync Server 2013 version of Lync Web App supports multi-factor authentication.</span></span> <span data-ttu-id="d99ff-114">ユーザー名とパスワードに加えて、他の認証方法 (スマートカード、Pin など) を使用して、Lync 会議にサインインするときに外部ネットワークから参加するユーザーを認証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d99ff-114">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Lync meetings.</span></span> <span data-ttu-id="d99ff-115">多要素認証を有効にするには、Active Directory フェデレーションサービス (AD FS) フェデレーションサーバーを展開し、Lync Server 2013 でパッシブ認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="d99ff-115">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Lync Server 2013.</span></span> <span data-ttu-id="d99ff-116">AD FS が構成されると、Lync 会議に参加しようとしている外部ユーザーには、ユーザー名とパスワードのチャレンジと、構成したその他の認証方法が含まれた、AD FS 多要素認証の web ページが表示されます。.</span><span class="sxs-lookup"><span data-stu-id="d99ff-116">After AD FS is configured, external users who attempt to join Lync meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="d99ff-117">多要素認証の AD FS を構成する場合の重要な考慮事項を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d99ff-117">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="d99ff-p105">ADFS の多要素認証は、会議の参加者と開催者がともに同じ組織内に存在しているか、AD FS フェデレーション組織からのものである場合に機能します。ADFS の多要素認証は、Lync サーバーの Web インフラストラクチャでは現在サポートされていないため、Lync のフェデレーション ユーザーに対しては機能しません。</span><span class="sxs-lookup"><span data-stu-id="d99ff-p105">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization. Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span></P>
> <LI>
> <P><span data-ttu-id="d99ff-120">ハードウェアロードバランサーを使っている場合は、すべての要求が同じフロントエンドサーバーによって処理されるように、ロードバランサーでの cookie の永続化を有効にします。</span><span class="sxs-lookup"><span data-stu-id="d99ff-120">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Lync Web App client are handled by the same Front End Server.</span></span></P>
> <LI>
> <P><span data-ttu-id="d99ff-121">Lync Server と AD FS サーバー間で証明書利用者の信頼を確立する場合は、Lync 会議の最大の長さに収まる長さのトークンの有効期間を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d99ff-121">When you establish a relying party trust between Lync Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Lync meetings.</span></span> <span data-ttu-id="d99ff-122">通常、トークンの存続期間は 240 分で十分です。</span><span class="sxs-lookup"><span data-stu-id="d99ff-122">Typically, a token life of 240 minutes is sufficient.</span></span></P>
> <LI>
> <P><span data-ttu-id="d99ff-123">この構成は、Lync モバイル クライアントには適用されません。</span><span class="sxs-lookup"><span data-stu-id="d99ff-123">This configuration does not apply to Lync mobile clients.</span></span></P></LI></UL>



</div>

<span data-ttu-id="d99ff-124">**多要素認証を構成するには**</span><span class="sxs-lookup"><span data-stu-id="d99ff-124">**To Configure Multi-Factor Authentication**</span></span>

1.  <span data-ttu-id="d99ff-125">AD FS フェデレーション サーバーの役割をインストールします。</span><span class="sxs-lookup"><span data-stu-id="d99ff-125">Install an AD FS federation server role.</span></span> <span data-ttu-id="d99ff-126">詳細については、「Active Directory フェデレーションサービス2.0 展開ガイド」を参照してください。<http://go.microsoft.com/fwlink/p/?linkid=267511></span><span class="sxs-lookup"><span data-stu-id="d99ff-126">For details, see the Active Directory Federation Services 2.0 Deployment Guide at <http://go.microsoft.com/fwlink/p/?linkid=267511></span></span>

2.  <span data-ttu-id="d99ff-127">AD FS の証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="d99ff-127">Create certificates for AD FS.</span></span> <span data-ttu-id="d99ff-128">詳細については、「AD FS を計画して展開する」の「フェデレーションサーバーの証明書」セクションを参照して[http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376)ください。シングルサインオンのトピックで使用します。</span><span class="sxs-lookup"><span data-stu-id="d99ff-128">For more information, see the "Federation server certificates" section of the Plan for and deploy AD FS for use with single sign-on topic at [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376).</span></span>

3.  <span data-ttu-id="d99ff-129">Windows PowerShell コマンドラインインターフェイスで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d99ff-129">From the Windows PowerShell command-line interface, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  <span data-ttu-id="d99ff-130">次のコマンドを実行し、パートナーシップを確立します。</span><span class="sxs-lookup"><span data-stu-id="d99ff-130">Establish a partnership by running the following command:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  <span data-ttu-id="d99ff-131">以下の証明書利用者のルールを設定します。</span><span class="sxs-lookup"><span data-stu-id="d99ff-131">Set the following relying party rules:</span></span>
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```powershell
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="branchcache-configuration"></a><span data-ttu-id="d99ff-132">BranchCache の構成</span><span class="sxs-lookup"><span data-stu-id="d99ff-132">BranchCache Configuration</span></span>

<span data-ttu-id="d99ff-133">Windows 7 および Windows Server 2008 R2 の BranchCache 機能は、Lync Web App web コンポーネントを干渉する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d99ff-133">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Lync Web App web components.</span></span> <span data-ttu-id="d99ff-134">Lync Web App ユーザーの問題を回避するには、BranchCache が有効になっていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d99ff-134">To prevent issues for Lync Web App users, make sure that BranchCache is not enabled.</span></span>

<span data-ttu-id="d99ff-135">BranchCache の無効化の詳細については、Microsoft ダウンロードセンターの Word 形式[http://go.microsoft.com/fwlink/p/?LinkId=268788](http://go.microsoft.com/fwlink/p/?linkid=268788)と、Windows Server 2008 R2 テクニカルライブラリの HTML 形式で利用できる Branchcache 展開ガイドを参照して[http://go.microsoft.com/fwlink/p/?LinkId=268789](http://go.microsoft.com/fwlink/p/?linkid=268789)ください。</span><span class="sxs-lookup"><span data-stu-id="d99ff-135">For details about disabling BranchCache, see the BranchCache Deployment Guide, which is available in Word format at the Microsoft Download Center at [http://go.microsoft.com/fwlink/p/?LinkId=268788](http://go.microsoft.com/fwlink/p/?linkid=268788) and in HTML format in the Windows Server 2008 R2 Technical Library at [http://go.microsoft.com/fwlink/p/?LinkId=268789](http://go.microsoft.com/fwlink/p/?linkid=268789).</span></span>

</div>

<div>

## <a name="verifying-lync-web-app-deployment"></a><span data-ttu-id="d99ff-136">Lync Web App の展開を確認する</span><span class="sxs-lookup"><span data-stu-id="d99ff-136">Verifying Lync Web App Deployment</span></span>

<span data-ttu-id="d99ff-137">Test-CsUcwaConference コマンドレットを使用すると、2 人のテスト ユーザーが統合コミュニケーション Web API (UCWA) を使用して電話会議に参加できることを検証できます。</span><span class="sxs-lookup"><span data-stu-id="d99ff-137">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="d99ff-138">このコマンドレットの詳細については、「Lync Server Management Shell ドキュメントの[CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d99ff-138">For details about this cmdlet, see [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="troubleshooting-plug-in-installation-on-windows-server2008r2"></a><span data-ttu-id="d99ff-139">Windows Server 2008 R2 でのプラグインのインストールのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d99ff-139">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>

<span data-ttu-id="d99ff-140">Windows Server 2008 R2 を実行しているコンピューターでプラグインのインストールが失敗した場合は、Internet Explorer のセキュリティ設定または DisableMSI のレジストリキー設定を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d99ff-140">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>

<span data-ttu-id="d99ff-141">**Internet Explorer でセキュリティ設定を変更するには**</span><span class="sxs-lookup"><span data-stu-id="d99ff-141">**To modify the security setting in Internet Explorer**</span></span>

1.  <span data-ttu-id="d99ff-142">Internet Explorer を開きます。</span><span class="sxs-lookup"><span data-stu-id="d99ff-142">Open Internet Explorer.</span></span>

2.  <span data-ttu-id="d99ff-143">[**ツール**]、[**インターネット オプション**]、[**詳細設定**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d99ff-143">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>

3.  <span data-ttu-id="d99ff-144">[**セキュリティ**] セクションまで下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="d99ff-144">Scroll down to the **Security** section.</span></span>

4.  <span data-ttu-id="d99ff-145">[**暗号化されたページをディスクに保存しない**] チェック ボックスをオフにして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d99ff-145">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="d99ff-146">この設定を選択すると、Lync Web App から添付ファイルをダウンロードしようとしたときにもエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="d99ff-146">If selected, this setting will also cause an error when trying to download an attachment from Lync Web App.</span></span>

    
    </div>

5.  <span data-ttu-id="d99ff-147">会議にもう一度参加します。</span><span class="sxs-lookup"><span data-stu-id="d99ff-147">Rejoin the meeting.</span></span> <span data-ttu-id="d99ff-148">エラーが発生することなくプラグインがダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="d99ff-148">The plug-in should download without errors.</span></span>

<span data-ttu-id="d99ff-149">**DisableMSI のレジストリ設定を変更するには**</span><span class="sxs-lookup"><span data-stu-id="d99ff-149">**To modify the DisableMSI Registry setting**</span></span>

1.  <span data-ttu-id="d99ff-150">[**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d99ff-150">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="d99ff-151">レジストリ エディターにアクセスするには、「**regedit**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="d99ff-151">To access the Registry Editor, type **regedit**.</span></span>

3.  <span data-ttu-id="d99ff-152">\_"HKEY\_LOCAL MACHINE\\Software\\Policies\\Microsoft\\Windows\\Installer" に移動します。</span><span class="sxs-lookup"><span data-stu-id="d99ff-152">Navigate to HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\Installer.</span></span>

4.  <span data-ttu-id="d99ff-153">REG\_DWORD 型の DisableMSI レジストリキーを編集または追加し、0に設定します。</span><span class="sxs-lookup"><span data-stu-id="d99ff-153">Edit or add the DisableMSI registry key of type REG\_DWORD and set it to 0.</span></span>

5.  <span data-ttu-id="d99ff-154">会議にもう一度参加します。</span><span class="sxs-lookup"><span data-stu-id="d99ff-154">Rejoin the meeting.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d99ff-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="d99ff-155">See Also</span></span>


[<span data-ttu-id="d99ff-156">Lync Server 2013 での会議参加ページの構成</span><span class="sxs-lookup"><span data-stu-id="d99ff-156">Configuring the meeting join page in Lync Server 2013</span></span>](lync-server-2013-configuring-the-meeting-join-page.md)  
[<span data-ttu-id="d99ff-157">Lync Web App が Lync Server 2013 用にサポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="d99ff-157">Lync Web App supported platforms for Lync Server 2013</span></span>](lync-server-2013-lync-web-app-supported-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

