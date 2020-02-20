---
title: 'Lync Server 2013: Lync Web App の展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Web App
ms:assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205190(v=OCS.15)
ms:contentKeyID: 48185189
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16a7a78c67b94084c59ebad63baa12c3a7aa3df2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147550"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-lync-web-app-in-lync-server-2013"></a><span data-ttu-id="4af8e-102">Lync Server 2013 での Lync Web App の展開</span><span class="sxs-lookup"><span data-stu-id="4af8e-102">Deploying Lync Web App in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4af8e-103">_**トピックの最終更新日:** 2013-07-18_</span><span class="sxs-lookup"><span data-stu-id="4af8e-103">_**Topic Last Modified:** 2013-07-18_</span></span>

<span data-ttu-id="4af8e-104">Lync Web App は、Lync Server 2013 と共にインストールされるインターネットインフォメーションサービス (IIS) web クライアントで、既定では有効になっています。</span><span class="sxs-lookup"><span data-stu-id="4af8e-104">Lync Web App is an Internet Information Services (IIS) web client that installs with Lync Server 2013 and is enabled by default.</span></span> <span data-ttu-id="4af8e-105">サーバーで Lync Web App を有効にしたり、web クライアントをユーザーに展開したりするための追加の手順は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="4af8e-105">No additional steps are necessary to either enable Lync Web App on the server or deploy the web client to users.</span></span> <span data-ttu-id="4af8e-106">ユーザーが会議 URL をクリックしても、Lync 2013 クライアントがインストールされていない場合は、最新バージョンの Lync Web App を使用して会議に参加するためのオプションがユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4af8e-106">Whenever a user clicks a meeting URL but does not have the Lync 2013 client installed, the user is presented with the option to join the meeting by using the latest version of Lync Web App.</span></span>

<span data-ttu-id="4af8e-107">Lync Web App の音声、ビデオ、および共有機能には、Microsoft ActiveX コントロールが必要です。</span><span class="sxs-lookup"><span data-stu-id="4af8e-107">The voice, video, and sharing features in Lync Web App require a Microsoft ActiveX control.</span></span> <span data-ttu-id="4af8e-108">ActiveX コントロールを事前にインストールするか、要求されたときにユーザーにインストールを許可することができます。これは、初めて Lync Web App を使用するとき、または ActiveX コントロールを必要とする機能に初めてアクセスしたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="4af8e-108">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Lync Web App or the first time they access a feature that requires the ActiveX control.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="4af8e-109">Lync Server 2013 エッジサーバー展開では、Lync Web App クライアントアクセスには、境界ネットワーク内の HTTPS リバースプロキシが必要です。</span><span class="sxs-lookup"><span data-stu-id="4af8e-109">In Lync Server 2013 Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Lync Web App client access.</span></span> <span data-ttu-id="4af8e-110">また、簡易 URL も公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4af8e-110">You must also publish simple URLs.</span></span> <span data-ttu-id="4af8e-111">詳細については、「lync <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">server 2013 用のリバースプロキシサーバーの設定</A>」および「 <A href="lync-server-2013-planning-for-simple-urls.md">lync server 2013 での簡単な url の計画</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4af8e-111">For details, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> and <A href="lync-server-2013-planning-for-simple-urls.md">Planning for simple URLs in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-web-app"></a><span data-ttu-id="4af8e-112">Lync Web App で多要素認証を有効にする</span><span class="sxs-lookup"><span data-stu-id="4af8e-112">Enabling Multi-Factor Authentication for Lync Web App</span></span>

<span data-ttu-id="4af8e-113">Lync Web App の Lync Server 2013 バージョンは、多要素認証をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="4af8e-113">The Lync Server 2013 version of Lync Web App supports multi-factor authentication.</span></span> <span data-ttu-id="4af8e-114">ユーザー名とパスワードに加えて、スマートカードや Pin などの追加の認証方法を要求して、Lync 会議にサインインするときに外部ネットワークから参加しているユーザーを認証することができます。</span><span class="sxs-lookup"><span data-stu-id="4af8e-114">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Lync meetings.</span></span> <span data-ttu-id="4af8e-115">Active Directory フェデレーションサービス (AD FS) フェデレーションサーバーを展開し、Lync Server 2013 でパッシブ認証を有効にすることによって、多要素認証を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="4af8e-115">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Lync Server 2013.</span></span> <span data-ttu-id="4af8e-116">AD FS を構成した後、Lync 会議に参加しようとする外部ユーザーには、ユーザー名とパスワードのチャレンジと、構成した追加の認証方法が含まれる AD FS 多要素認証 web ページが表示されます。.</span><span class="sxs-lookup"><span data-stu-id="4af8e-116">After AD FS is configured, external users who attempt to join Lync meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="4af8e-117">多要素認証の AD FS を構成する場合の重要な考慮事項を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4af8e-117">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="4af8e-118">複数要素 ADFS 認証は、会議の参加者と開催者が両方とも同じ組織内にあるか、または AD FS フェデレーション組織の両方にある場合に機能します。</span><span class="sxs-lookup"><span data-stu-id="4af8e-118">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization.</span></span> <span data-ttu-id="4af8e-119">Lync server web インフラストラクチャでは現在サポートされていないため、Lync フェデレーションユーザーは多要素 ADFS 認証を使用できません。</span><span class="sxs-lookup"><span data-stu-id="4af8e-119">Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span></P>
> <LI>
> <P><span data-ttu-id="4af8e-120">ハードウェアロードバランサーを使用する場合は、ロードバランサーで cookie の永続性を有効にして、Lync Web App クライアントからのすべての要求が同じフロントエンドサーバーによって処理されるようにします。</span><span class="sxs-lookup"><span data-stu-id="4af8e-120">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Lync Web App client are handled by the same Front End Server.</span></span></P>
> <LI>
> <P><span data-ttu-id="4af8e-121">Lync Server と AD FS サーバー間で証明書利用者の信頼を確立するときには、Lync 会議の最大長を長くするのに十分な長さのトークンライフサイクルを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4af8e-121">When you establish a relying party trust between Lync Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Lync meetings.</span></span> <span data-ttu-id="4af8e-122">通常、トークンの存続期間は 240 分で十分です。</span><span class="sxs-lookup"><span data-stu-id="4af8e-122">Typically, a token life of 240 minutes is sufficient.</span></span></P>
> <LI>
> <P><span data-ttu-id="4af8e-123">この構成は、Lync mobile クライアントには適用されません。</span><span class="sxs-lookup"><span data-stu-id="4af8e-123">This configuration does not apply to Lync mobile clients.</span></span></P></LI></UL>



</div>

<span data-ttu-id="4af8e-124">**多要素認証を構成するには**</span><span class="sxs-lookup"><span data-stu-id="4af8e-124">**To Configure Multi-Factor Authentication**</span></span>

1.  <span data-ttu-id="4af8e-125">AD FS フェデレーション サーバーの役割をインストールします。</span><span class="sxs-lookup"><span data-stu-id="4af8e-125">Install an AD FS federation server role.</span></span> <span data-ttu-id="4af8e-126">詳細については、「Active Directory フェデレーションサービス2.0 展開ガイド」を参照してください。<https://go.microsoft.com/fwlink/p/?linkid=267511></span><span class="sxs-lookup"><span data-stu-id="4af8e-126">For details, see the Active Directory Federation Services 2.0 Deployment Guide at <https://go.microsoft.com/fwlink/p/?linkid=267511></span></span>

2.  <span data-ttu-id="4af8e-127">AD FS の証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="4af8e-127">Create certificates for AD FS.</span></span> <span data-ttu-id="4af8e-128">詳細については、「計画と展開」の「AD FS を展開するには」の「フェデレーションサーバー証明書」セクション[https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376)を参照してください。シングルサインオンについては、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4af8e-128">For more information, see the "Federation server certificates" section of the Plan for and deploy AD FS for use with single sign-on topic at [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376).</span></span>

3.  <span data-ttu-id="4af8e-129">Windows PowerShell コマンドラインインターフェイスで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4af8e-129">From the Windows PowerShell command-line interface, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  <span data-ttu-id="4af8e-130">次のコマンドを実行し、パートナーシップを確立します。</span><span class="sxs-lookup"><span data-stu-id="4af8e-130">Establish a partnership by running the following command:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  <span data-ttu-id="4af8e-131">以下の証明書利用者のルールを設定します。</span><span class="sxs-lookup"><span data-stu-id="4af8e-131">Set the following relying party rules:</span></span>
    
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

## <a name="branchcache-configuration"></a><span data-ttu-id="4af8e-132">BranchCache 構成</span><span class="sxs-lookup"><span data-stu-id="4af8e-132">BranchCache Configuration</span></span>

<span data-ttu-id="4af8e-133">Windows 7 および Windows Server 2008 R2 の BranchCache 機能は、Lync Web App web コンポーネントと競合する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4af8e-133">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Lync Web App web components.</span></span> <span data-ttu-id="4af8e-134">Lync Web App ユーザーの問題が発生しないようにするには、BranchCache が有効になっていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4af8e-134">To prevent issues for Lync Web App users, make sure that BranchCache is not enabled.</span></span>

<span data-ttu-id="4af8e-135">BranchCache を無効にする方法の詳細については、「BranchCache 展開ガイド」を参照してください[https://go.microsoft.com/fwlink/p/?LinkId=268788](https://go.microsoft.com/fwlink/p/?linkid=268788) [https://go.microsoft.com/fwlink/p/?LinkId=268789](https://go.microsoft.com/fwlink/p/?linkid=268789)。このガイドは、MICROSOFT ダウンロードセンターおよび HTML 形式の Windows Server 2008 R2 Technical Library () にある word 形式で利用できます。</span><span class="sxs-lookup"><span data-stu-id="4af8e-135">For details about disabling BranchCache, see the BranchCache Deployment Guide, which is available in Word format at the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268788](https://go.microsoft.com/fwlink/p/?linkid=268788) and in HTML format in the Windows Server 2008 R2 Technical Library at [https://go.microsoft.com/fwlink/p/?LinkId=268789](https://go.microsoft.com/fwlink/p/?linkid=268789).</span></span>

</div>

<div>

## <a name="verifying-lync-web-app-deployment"></a><span data-ttu-id="4af8e-136">Lync Web App の展開を確認する</span><span class="sxs-lookup"><span data-stu-id="4af8e-136">Verifying Lync Web App Deployment</span></span>

<span data-ttu-id="4af8e-137">Test-CsUcwaConference コマンドレットを使用すると、2 人のテスト ユーザーが統合コミュニケーション Web API (UCWA) を使用して会議に参加できることを検証できます。</span><span class="sxs-lookup"><span data-stu-id="4af8e-137">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="4af8e-138">このコマンドレットの詳細については、「Lync Server Management Shell」のドキュメントの「 [test-csucwaconference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4af8e-138">For details about this cmdlet, see [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="troubleshooting-plug-in-installation-on-windows-server2008r2"></a><span data-ttu-id="4af8e-139">Windows Server 2008 R2 でのプラグインのインストールのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="4af8e-139">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>

<span data-ttu-id="4af8e-140">Windows Server 2008 R2 を実行しているコンピューターでプラグインのインストールが失敗した場合は、Internet Explorer のセキュリティ設定または DisableMSI レジストリキーの設定を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4af8e-140">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>

<span data-ttu-id="4af8e-141">**Internet Explorer のセキュリティ設定を変更するには**</span><span class="sxs-lookup"><span data-stu-id="4af8e-141">**To modify the security setting in Internet Explorer**</span></span>

1.  <span data-ttu-id="4af8e-142">Internet Explorer を開きます。</span><span class="sxs-lookup"><span data-stu-id="4af8e-142">Open Internet Explorer.</span></span>

2.  <span data-ttu-id="4af8e-143">[**ツール**]、[**インターネット オプション**]、[**詳細設定**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="4af8e-143">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>

3.  <span data-ttu-id="4af8e-144">[**セキュリティ**] セクションまで下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="4af8e-144">Scroll down to the **Security** section.</span></span>

4.  <span data-ttu-id="4af8e-145">[**暗号化されたページをディスクに保存しない**] チェック ボックスをオフにし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4af8e-145">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="4af8e-146">この設定を選択すると、Lync Web App から添付ファイルをダウンロードしようとした場合にもエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="4af8e-146">If selected, this setting will also cause an error when trying to download an attachment from Lync Web App.</span></span>

    
    </div>

5.  <span data-ttu-id="4af8e-147">会議にもう一度参加します。</span><span class="sxs-lookup"><span data-stu-id="4af8e-147">Rejoin the meeting.</span></span> <span data-ttu-id="4af8e-148">エラーが発生することなくプラグインがダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="4af8e-148">The plug-in should download without errors.</span></span>

<span data-ttu-id="4af8e-149">**DisableMSI レジストリ設定を変更するには**</span><span class="sxs-lookup"><span data-stu-id="4af8e-149">**To modify the DisableMSI Registry setting**</span></span>

1.  <span data-ttu-id="4af8e-150">[**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4af8e-150">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="4af8e-151">レジストリ エディターにアクセスするには、「**regedit**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="4af8e-151">To access the Registry Editor, type **regedit**.</span></span>

3.  <span data-ttu-id="4af8e-152">\_[HKEY\_LOCAL MACHINE\\Software\\Policies\\Microsoft\\Windows\\Installer に移動します。</span><span class="sxs-lookup"><span data-stu-id="4af8e-152">Navigate to HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\Installer.</span></span>

4.  <span data-ttu-id="4af8e-153">REG\_DWORD 型の DisableMSI レジストリキーを編集または追加し、0に設定します。</span><span class="sxs-lookup"><span data-stu-id="4af8e-153">Edit or add the DisableMSI registry key of type REG\_DWORD and set it to 0.</span></span>

5.  <span data-ttu-id="4af8e-154">会議にもう一度参加します。</span><span class="sxs-lookup"><span data-stu-id="4af8e-154">Rejoin the meeting.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4af8e-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="4af8e-155">See Also</span></span>


[<span data-ttu-id="4af8e-156">Lync Server 2013 での会議参加ページの構成</span><span class="sxs-lookup"><span data-stu-id="4af8e-156">Configuring the meeting join page in Lync Server 2013</span></span>](lync-server-2013-configuring-the-meeting-join-page.md)  
[<span data-ttu-id="4af8e-157">Lync Server 2013 の lync Web App がサポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="4af8e-157">Lync Web App supported platforms for Lync Server 2013</span></span>](lync-server-2013-lync-web-app-supported-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

