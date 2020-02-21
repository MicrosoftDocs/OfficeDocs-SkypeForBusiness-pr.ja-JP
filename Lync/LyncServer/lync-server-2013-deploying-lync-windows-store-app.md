---
title: 'Lync Server 2013: Lync Windows ストアアプリの展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Windows Store app
ms:assetid: 9e00aaf4-15f9-4356-9ed7-5a58a2bfa043
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ822971(v=OCS.15)
ms:contentKeyID: 50117635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de478ddf104f36fc208f2773c26c772b2cc0addd
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195340"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-lync-windows-store-app-in-lync-server-2013"></a><span data-ttu-id="2d419-102">Lync Server 2013 での Lync Windows ストアアプリの展開</span><span class="sxs-lookup"><span data-stu-id="2d419-102">Deploying Lync Windows Store app in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d419-103">_**トピックの最終更新日:** 2013-12-03_</span><span class="sxs-lookup"><span data-stu-id="2d419-103">_**Topic Last Modified:** 2013-12-03_</span></span>

<span data-ttu-id="2d419-104">Lync Windows ストアアプリをユーザーが使用できるようにする前に、展開が[Lync Server 2013 の Lync Windows ストアのアプリ要件](lync-server-2013-lync-windows-store-app-requirements.md)を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="2d419-104">Before making Lync Windows Store app available to users, make sure that your deployment meets the [Lync Windows Store app requirements for Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md).</span></span> <span data-ttu-id="2d419-105">Lync Windows ストアアプリをサポートするように Lync Server 2013 を構成する方法の詳細については、「NextHop ブログの記事、「Lync Server の[https://go.microsoft.com/fwlink/?LinkId=271966](https://go.microsoft.com/fwlink/?linkid=271966)自動検出と Lync Windows ストアアプリ」 () を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d419-105">For details about configuring Lync Server 2013 to support Lync Windows Store app, see the NextHop Blog article, "Lync Server Autodiscover and the Lync Windows Store App," at [https://go.microsoft.com/fwlink/?LinkId=271966](https://go.microsoft.com/fwlink/?linkid=271966).</span></span> <span data-ttu-id="2d419-106">サーバー環境が正しく構成された後、ユーザーは「Lync」を検索して Windows ストアから Lync アプリをダウンロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="2d419-106">After your server environment is configured correctly, you can direct users to download the Lync app from the Windows Store by searching for "Lync."</span></span>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-windows-store-app"></a><span data-ttu-id="2d419-107">Lync Windows ストアアプリで多要素認証を有効にする</span><span class="sxs-lookup"><span data-stu-id="2d419-107">Enabling Multi-Factor Authentication for Lync Windows Store app</span></span>

<span data-ttu-id="2d419-108">Lync Server 2013 の累積的な更新プログラム: 2013 年6月、Lync Windows ストアアプリクライアントに対して多要素認証のサポートが追加されます。</span><span class="sxs-lookup"><span data-stu-id="2d419-108">Cumulative Updates for Lync Server 2013: June 2013 adds support for multi-factor authentication for Lync Windows Store app clients.</span></span> <span data-ttu-id="2d419-109">ユーザー名とパスワードに加えて、スマートカードや Pin などの追加の認証方法を要求して、Lync 会議にサインインする際に外部ユーザーを認証することができます。</span><span class="sxs-lookup"><span data-stu-id="2d419-109">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate external users when they sign in to Lync meetings.</span></span> <span data-ttu-id="2d419-110">多要素認証を有効にするには、Active Directory フェデレーションサービス (AD FS) フェデレーションサーバーを展開し、Lync Server 2013 でパッシブ認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="2d419-110">To enable multi-factor authentication, you deploy Active Directory Federation Service (AD FS) federation server and enable passive authentication in Lync Server 2013.</span></span> <span data-ttu-id="2d419-111">AD FS を構成した後、Lync 会議に参加しようとする外部ユーザーには、ユーザー名とパスワードのチャレンジと、構成した追加の認証方法が含まれる AD FS 多要素認証 web ページが表示されます。.</span><span class="sxs-lookup"><span data-stu-id="2d419-111">After AD FS is configured, external users who attempt to join Lync meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="2d419-112">Lync Windows ストアアプリで多要素認証を使用するように AD FS を構成する場合の重要な考慮事項は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2d419-112">The following are important considerations if you plan to configure AD FS for multi-factor authentication for Lync Windows Store app:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="2d419-113">Lync server 2013 の累積的な更新プログラム (Lync Server 2013): 少なくとも2013年6月1日</span><span class="sxs-lookup"><span data-stu-id="2d419-113">Lync Server 2013 with Cumulative Updates for Lync Server 2013: June 2013 is required at a minimum.</span></span> <span data-ttu-id="2d419-114">Lync 2013 デスクトップクライアントは、lync Server 2013 の累積的な更新プログラム (2013 年6月) を必要としないため、Lync 2013 クライアントは認証を行うことができるため、パッシブ認証が機能しているように見える場合があります。</span><span class="sxs-lookup"><span data-stu-id="2d419-114">Lync 2013 desktop clients do not require Cumulative Updates for Lync Server 2013: June 2013, so it might appear that passive authentication is working because Lync 2013 clients are able to authenticate.</span></span> <span data-ttu-id="2d419-115">ただし、Lync Windows ストアアプリクライアントの認証プロセスは完了せず、通知やエラーメッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="2d419-115">However, the authentication process for Lync Windows Store app clients will fail to complete and no notification or error message will display.</span></span></P>
> <LI>
> <P><span data-ttu-id="2d419-116">パッシブ認証が提供される唯一の認証の種類になるようにサーバーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d419-116">The server must be configured so that passive authentication is the only authentication type offered.</span></span></P>
> <LI>
> <P><span data-ttu-id="2d419-117">ハードウェアロードバランサーを使用する場合は、ロードバランサーで cookie の永続性を有効にして、Lync Windows ストアアプリクライアントからのすべての要求が同じフロントエンドサーバーによって処理されるようにします。</span><span class="sxs-lookup"><span data-stu-id="2d419-117">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Lync Windows Store app client are handled by the same Front End Server.</span></span></P>
> <LI>
> <P><span data-ttu-id="2d419-118">Lync Server と AD FS サーバー間で証明書利用者の信頼を確立するときには、Lync 会議の最大長を長くするのに十分な長さのトークンライフサイクルを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2d419-118">When you establish a relying party trust between Lync Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Lync meetings.</span></span> <span data-ttu-id="2d419-119">通常、トークンの存続期間は 240 分で十分です。</span><span class="sxs-lookup"><span data-stu-id="2d419-119">Typically, a token life of 240 minutes is sufficient.</span></span></P></LI></UL>



</div>

<span data-ttu-id="2d419-120">**多要素認証を構成するには**</span><span class="sxs-lookup"><span data-stu-id="2d419-120">**To Configure Multi-Factor Authentication**</span></span>

1.  <span data-ttu-id="2d419-121">AD FS フェデレーション サーバーの役割をインストールします。</span><span class="sxs-lookup"><span data-stu-id="2d419-121">Install an AD FS federation server role.</span></span> <span data-ttu-id="2d419-122">詳細については、「Active Directory フェデレーションサービス2.0 展開<https://go.microsoft.com/fwlink/p/?linkid=267511>ガイド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d419-122">For details, see the Active Directory Federation Services 2.0 Deployment Guide at <https://go.microsoft.com/fwlink/p/?linkid=267511>.</span></span>

2.  <span data-ttu-id="2d419-123">AD FS の証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="2d419-123">Create certificates for AD FS.</span></span> <span data-ttu-id="2d419-124">詳細については、「計画と展開」の「AD FS を展開するには」の「フェデレーションサーバー証明書」セクション[https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376)を参照してください。シングルサインオンについては、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d419-124">For more information, see the "Federation server certificates" section of the Plan for and deploy AD FS for use with single sign-on topic at [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376).</span></span>

3.  <span data-ttu-id="2d419-125">Windows PowerShell コマンドラインインターフェイスで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2d419-125">From the Windows PowerShell command-line interface, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  <span data-ttu-id="2d419-126">次のコマンドを実行し、パートナーシップを確立します。</span><span class="sxs-lookup"><span data-stu-id="2d419-126">Establish a partnership by running the following command:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```
5.  <span data-ttu-id="2d419-127">以下の証明書利用者のルールを設定します。</span><span class="sxs-lookup"><span data-stu-id="2d419-127">Set the following relying party rules:</span></span>
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```powershell
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="known-issues-that-can-prevent-sign-in"></a><span data-ttu-id="2d419-128">サインインを妨げる可能性がある既知の問題</span><span class="sxs-lookup"><span data-stu-id="2d419-128">Known Issues that Can Prevent Sign-in</span></span>

<div>

## <a name="the-time-and-date-are-not-set-accurately-on-the-device-running-lync-windows-store-app"></a><span data-ttu-id="2d419-129">Lync Windows ストアアプリを実行しているデバイスに日付と時刻が正しく設定されていません</span><span class="sxs-lookup"><span data-stu-id="2d419-129">The time and date are not set accurately on the device running Lync Windows Store app</span></span>

<span data-ttu-id="2d419-130">デバイスの時刻設定は、サーバーの時刻設定と同期されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d419-130">The time setting on the device must be synchronized with the time setting on the server.</span></span> <span data-ttu-id="2d419-131">これは、Microsoft Surface などのデバイス、およびドメインに参加していない Windows RT を実行しているデバイスにとって特に重要です。</span><span class="sxs-lookup"><span data-stu-id="2d419-131">This is particularly important for devices such as Microsoft Surface, and other devices running Windows RT that are not joined to a domain.</span></span> <span data-ttu-id="2d419-132">これらのデバイスの時刻をタイムサーバーから自動的に設定するには、デバイス上の管理者特権でのコマンドプロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2d419-132">To set the time on these devices automatically from a time server, run the following command from an elevated command prompt on the device:</span></span>
```console
w32tm /resync
```
</div>

<div>

## <a name="lync-windows-store-app-cannot-access-the-lync-server-or-services"></a><span data-ttu-id="2d419-133">Lync Windows ストアアプリが Lync server またはサービスにアクセスできません</span><span class="sxs-lookup"><span data-stu-id="2d419-133">Lync Windows Store app cannot access the Lync server or services</span></span>

<span data-ttu-id="2d419-134">Lync Windows ストアアプリは、物理デバイスとして Windows 8 に登録されていない 4G LTE USB モデムなどのネットワークアダプターを介して Lync server またはサービスにアクセスできない場合があります。</span><span class="sxs-lookup"><span data-stu-id="2d419-134">Lync Windows Store app may not be able to access the Lync server or services through network adapters, such as 4G LTE USB modems, that do not register with Windows 8 as physical devices.</span></span> <span data-ttu-id="2d419-135">Lync Windows ストアアプリは、デスクトップアプリとブラウザーが他のサーバーや web サイトにアクセスできる場合でも、この問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="2d419-135">Lync Windows Store app may have this issue even when the desktop apps and browsers are able to access other servers and web sites.</span></span>

</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-with-lync-server-2010-and-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="2d419-136">Lync Windows ストアアプリで Lync Server 2010 および Office Communications Server 2007 R2 エッジサーバーを使用してサインインできない</span><span class="sxs-lookup"><span data-stu-id="2d419-136">Lync Windows Store app cannot sign in with Lync Server 2010 and Office Communications Server 2007 R2 Edge Server</span></span>

<span data-ttu-id="2d419-137">Office Communications Server 2007 R2 エッジサーバーを使用する Lync Server 2010 でトポロジが構成されている場合は、Lync Server 2010 の累積的な更新プログラム (7 月 2013 7 日) で使用できる、更新されたバージョンのトポロジビルダーを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d419-137">If your topology consists of Lync Server 2010 with Office Communications Server 2007 R2 Edge Server, you will need to run the updated version of Topology Builder available in the cumulative update for Lync Server 2010: July 2013.</span></span> <span data-ttu-id="2d419-138">以前のバージョンのトポロジビルダーでは、Office Communications Server 2007 エッジサーバーへの必要なマッピングが作成されないため、Lync Windows ストアアプリクライアントはサインインできません。</span><span class="sxs-lookup"><span data-stu-id="2d419-138">Earlier versions of Topology Builder do not create the required mapping to Office Communications Server 2007 Edge Server, so Lync Windows Store app clients are unable to sign in.</span></span> <span data-ttu-id="2d419-139">次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d419-139">The following steps are required:</span></span>

1.  <span data-ttu-id="2d419-140">Lync server 2010 プールおよび Lync Server の2010ディレクターの累積的な更新プログラム (2010 2013 年7月) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="2d419-140">Install the cumulative update for Lync Server 2010: July 2013 on Lync Server 2010 pools and Lync Server 2010 Directors.</span></span>

2.  <span data-ttu-id="2d419-141">次の手順を実行して、外部 SIP エントリポイントがエッジサーバーアドレスであることを示すように、Lync 自動検出構成を更新します。</span><span class="sxs-lookup"><span data-stu-id="2d419-141">Update the Lync AutoDiscover configuration to indicate that the external SIP entry point is the Edge server address by doing the following:</span></span>
    
    1.  <span data-ttu-id="2d419-142">Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="2d419-142">Open Lync Server Management Shell.</span></span>
    
    2.  <span data-ttu-id="2d419-143">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2d419-143">Run the following command:</span></span>
        ```powershell
        Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443
        ```
</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-due-to-a-certificate-name-validation-failure"></a><span data-ttu-id="2d419-144">証明書名の検証に失敗したため、Lync Windows ストアアプリがサインインできない</span><span class="sxs-lookup"><span data-stu-id="2d419-144">Lync Windows Store App cannot sign in due to a certificate name validation failure</span></span>

<span data-ttu-id="2d419-145">最新バージョンの Lync Windows ストアアプリを実行していない Office 365 ユーザーに対してサインインの問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="2d419-145">A sign-in issue can occur for Office 365 users who are not running the latest version of Lync Windows Store app.</span></span> <span data-ttu-id="2d419-146">通常、この問題は複数のドメインを使用する場合に発生します (たとえば、SIP URI が**userA@domainZ.com** 、エッジサーバーが**sip.domainX.com**)。</span><span class="sxs-lookup"><span data-stu-id="2d419-146">This issue generally occurs when using multiple domains (for example, when the SIP URI is **userA@domainZ.com** but the Edge Server is **sip.domainX.com**).</span></span> <span data-ttu-id="2d419-147">この問題を解決するには、ユーザーは Lync Windows ストアアプリの最新バージョンをインストールする必要があります。これには、Windows 8.1 も必要です。</span><span class="sxs-lookup"><span data-stu-id="2d419-147">To fix the issue, users should install the latest version of Lync Windows Store app, which also requires Windows 8.1.</span></span>

</div>

</div>

<div>

## <a name="use-lync-windows-store-app-logs-to-troubleshoot-issues"></a><span data-ttu-id="2d419-148">Lync Windows ストアのアプリログを使用して問題のトラブルシューティングを行う</span><span class="sxs-lookup"><span data-stu-id="2d419-148">Use Lync Windows Store app logs to troubleshoot issues</span></span>

<span data-ttu-id="2d419-149">デバイスで生成されたログを使用して、問題のトラブルシューティングを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2d419-149">You can use the logs generated on the device to troubleshoot issues.</span></span> <span data-ttu-id="2d419-150">ログは次のフォルダーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="2d419-150">The logs are stored in the following folder:</span></span>

<span data-ttu-id="2d419-151">% LocalAppData%\\\\LyncMX\_8wekyb3d8bbwe\\localappdata\\Tracing</span><span class="sxs-lookup"><span data-stu-id="2d419-151">%LocalAppData%\\Packages\\Microsoft.LyncMX\_8wekyb3d8bbwe\\LocalState\\Tracing</span></span>

<span data-ttu-id="2d419-152">ユーザーからログを取得する前に、ログ記録が有効になっていることを確認し、メモリに格納されているすべての情報がハードドライブ上のファイルにも保存されるように、ログを保存するようにユーザーに依頼します。</span><span class="sxs-lookup"><span data-stu-id="2d419-152">Before you get the logs from a user, make sure that logging is turned on, and then ask the user to save the logs so that all the information stored in memory is also saved to files on the hard drive.</span></span>

<span data-ttu-id="2d419-153">**ログ記録を有効にするには**</span><span class="sxs-lookup"><span data-stu-id="2d419-153">**To turn on logging**</span></span>

1.  <span data-ttu-id="2d419-154">デバイスで Lync Windows ストアアプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="2d419-154">Open Lync Windows Store app on the device.</span></span>

2.  <span data-ttu-id="2d419-155">画面の右端からスワイプします。</span><span class="sxs-lookup"><span data-stu-id="2d419-155">Swipe from the right side of the screen.</span></span> <span data-ttu-id="2d419-156">マウスを使用している場合は、画面の右上隅をポイントし、画面の下にマウスポインターを移動します。</span><span class="sxs-lookup"><span data-stu-id="2d419-156">If you’re using a mouse, point to the upper-right corner of the screen and then move the mouse pointer down the screen.</span></span>

3.  <span data-ttu-id="2d419-157">[**設定**] を選択し、[**オプション**] を選択して、**診断ログ**を **[オン**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="2d419-157">Select **Settings**, select **Options**, and then set **Diagnostic Logs** to **On**.</span></span>

4.  <span data-ttu-id="2d419-158">以前に**診断ログ**がオフになっていた場合は、Lync を再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d419-158">If **Diagnostic Logs** was off previously, you must restart Lync.</span></span> <span data-ttu-id="2d419-159">Lync を再起動するには、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2d419-159">To restart Lync, do one of the following:</span></span>
    
      - <span data-ttu-id="2d419-160">デバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="2d419-160">Restart the device.</span></span>
    
      - <span data-ttu-id="2d419-161">Lync タスクを終了し、アプリをもう一度起動します。</span><span class="sxs-lookup"><span data-stu-id="2d419-161">End the Lync task and launch the app again.</span></span> <span data-ttu-id="2d419-162">タスクを終了するには、Windows タスクマネージャーを開き、[ **Lync**] を選択してから、[**タスクの終了**] をタップします。</span><span class="sxs-lookup"><span data-stu-id="2d419-162">To end the task, open the Windows Task Manager, select **Lync**, and then tap **End task**.</span></span> <span data-ttu-id="2d419-163">Lync が表示されていない場合は、詳細**情報**をタップして、[**バックグラウンド処理**] の下で lync を探します。</span><span class="sxs-lookup"><span data-stu-id="2d419-163">If Lync is not listed, tap **More details** and look for Lync under **Background processes**.</span></span>

<span data-ttu-id="2d419-164">**ログを保存するには**</span><span class="sxs-lookup"><span data-stu-id="2d419-164">**To save the logs**</span></span>

1.  <span data-ttu-id="2d419-165">デバイスで Lync Windows ストアアプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="2d419-165">Open Lync Windows Store app on the device.</span></span>

2.  <span data-ttu-id="2d419-166">サインインしてください。</span><span class="sxs-lookup"><span data-stu-id="2d419-166">Try signing in.</span></span>

3.  <span data-ttu-id="2d419-167">画面の右端からスワイプします。</span><span class="sxs-lookup"><span data-stu-id="2d419-167">Swipe from the right side of the screen.</span></span> <span data-ttu-id="2d419-168">マウスを使用している場合は、画面の右上隅をポイントし、画面の下にマウスポインターを移動します。</span><span class="sxs-lookup"><span data-stu-id="2d419-168">If you’re using a mouse, point to the upper-right corner of the screen and then move the mouse pointer down the screen.</span></span>

4.  <span data-ttu-id="2d419-169">[**設定**] を選択し、[**バージョン情報**] を選択し、[**ログの保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2d419-169">Select **Settings**, select **About**, and then select **Save logs**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

