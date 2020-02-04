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
ms.openlocfilehash: 49fcea107a4613ca78661a21d492612f82d9775f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757651"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-windows-store-app-in-lync-server-2013"></a><span data-ttu-id="90fcc-102">Lync Server 2013 での Lync Windows ストアアプリの展開</span><span class="sxs-lookup"><span data-stu-id="90fcc-102">Deploying Lync Windows Store app in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90fcc-103">_**最終更新日:** 2013-12-03_</span><span class="sxs-lookup"><span data-stu-id="90fcc-103">_**Topic Last Modified:** 2013-12-03_</span></span>

<span data-ttu-id="90fcc-104">Lync Windows ストアアプリをユーザーが利用できるようにする前に、展開が[Lync Server 2013 の Lync Windows ストアアプリの要件](lync-server-2013-lync-windows-store-app-requirements.md)を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="90fcc-104">Before making Lync Windows Store app available to users, make sure that your deployment meets the [Lync Windows Store app requirements for Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md).</span></span> <span data-ttu-id="90fcc-105">Lync Windows ストアアプリをサポートするように Lync Server 2013 を構成する方法の詳細については、「NextHop のブログ記事、「Lync Server の[http://go.microsoft.com/fwlink/?LinkId=271966](http://go.microsoft.com/fwlink/?linkid=271966)自動検出と Lync Windows ストアアプリ (英語)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90fcc-105">For details about configuring Lync Server 2013 to support Lync Windows Store app, see the NextHop Blog article, "Lync Server Autodiscover and the Lync Windows Store App," at [http://go.microsoft.com/fwlink/?LinkId=271966](http://go.microsoft.com/fwlink/?linkid=271966).</span></span> <span data-ttu-id="90fcc-106">サーバー環境が正しく構成された後、ユーザーは "Lync" を検索して Windows ストアから Lync アプリをダウンロードするように指示できます。</span><span class="sxs-lookup"><span data-stu-id="90fcc-106">After your server environment is configured correctly, you can direct users to download the Lync app from the Windows Store by searching for "Lync."</span></span>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-windows-store-app"></a><span data-ttu-id="90fcc-107">Lync Windows ストアアプリの多要素認証を有効にする</span><span class="sxs-lookup"><span data-stu-id="90fcc-107">Enabling Multi-Factor Authentication for Lync Windows Store app</span></span>

<span data-ttu-id="90fcc-108">Lync Server 2013 の累積更新プログラム: 2013 年6月は、Lync Windows ストアアプリクライアントの多要素認証のサポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="90fcc-108">Cumulative Updates for Lync Server 2013: June 2013 adds support for multi-factor authentication for Lync Windows Store app clients.</span></span> <span data-ttu-id="90fcc-109">ユーザー名とパスワードに加えて、他の認証方法 (スマートカードや Pin など) を使用して、Lync 会議にサインインするときに外部ユーザーを認証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90fcc-109">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate external users when they sign in to Lync meetings.</span></span> <span data-ttu-id="90fcc-110">多要素認証を有効にするには、Active Directory フェデレーションサービス (AD FS) フェデレーションサーバーを展開して、Lync Server 2013 でパッシブ認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="90fcc-110">To enable multi-factor authentication, you deploy Active Directory Federation Service (AD FS) federation server and enable passive authentication in Lync Server 2013.</span></span> <span data-ttu-id="90fcc-111">AD FS が構成されると、Lync 会議に参加しようとしている外部ユーザーには、ユーザー名とパスワードのチャレンジと、構成したその他の認証方法が含まれた、AD FS 多要素認証の web ページが表示されます。.</span><span class="sxs-lookup"><span data-stu-id="90fcc-111">After AD FS is configured, external users who attempt to join Lync meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="90fcc-112">Lync Windows ストアアプリの多要素認証用に AD FS を構成する場合は、次の点を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90fcc-112">The following are important considerations if you plan to configure AD FS for multi-factor authentication for Lync Windows Store app:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="90fcc-113">Lync server 2013 の累積更新プログラムを含む lync Server 2013: 少なくとも、2013年6月が必要です。</span><span class="sxs-lookup"><span data-stu-id="90fcc-113">Lync Server 2013 with Cumulative Updates for Lync Server 2013: June 2013 is required at a minimum.</span></span> <span data-ttu-id="90fcc-114">Lync 2013 デスクトップクライアントでは、lync Server 2013 の累積更新プログラムは必要ありません2013。そのため、Lync 2013 クライアントは認証できるため、パッシブ認証が機能すると表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="90fcc-114">Lync 2013 desktop clients do not require Cumulative Updates for Lync Server 2013: June 2013, so it might appear that passive authentication is working because Lync 2013 clients are able to authenticate.</span></span> <span data-ttu-id="90fcc-115">ただし、Lync Windows ストアアプリクライアントの認証プロセスは完了しません。通知やエラーメッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="90fcc-115">However, the authentication process for Lync Windows Store app clients will fail to complete and no notification or error message will display.</span></span></P>
> <LI>
> <P><span data-ttu-id="90fcc-116">サーバーは、受動的認証が提供されている認証の種類のみになるように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90fcc-116">The server must be configured so that passive authentication is the only authentication type offered.</span></span></P>
> <LI>
> <P><span data-ttu-id="90fcc-117">ハードウェアロードバランサーを使用している場合、Lync Windows ストアアプリクライアントからのすべての要求が同じフロントエンドサーバーによって処理されるように、ロードバランサーで cookie の永続性を有効にします。</span><span class="sxs-lookup"><span data-stu-id="90fcc-117">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Lync Windows Store app client are handled by the same Front End Server.</span></span></P>
> <LI>
> <P><span data-ttu-id="90fcc-118">Lync Server と AD FS サーバー間で証明書利用者の信頼を確立する場合は、Lync 会議の最大の長さに収まる長さのトークンの有効期間を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="90fcc-118">When you establish a relying party trust between Lync Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Lync meetings.</span></span> <span data-ttu-id="90fcc-119">通常、トークンの存続期間は 240 分で十分です。</span><span class="sxs-lookup"><span data-stu-id="90fcc-119">Typically, a token life of 240 minutes is sufficient.</span></span></P></LI></UL>



</div>

<span data-ttu-id="90fcc-120">**多要素認証を構成するには**</span><span class="sxs-lookup"><span data-stu-id="90fcc-120">**To Configure Multi-Factor Authentication**</span></span>

1.  <span data-ttu-id="90fcc-121">AD FS フェデレーション サーバーの役割をインストールします。</span><span class="sxs-lookup"><span data-stu-id="90fcc-121">Install an AD FS federation server role.</span></span> <span data-ttu-id="90fcc-122">詳細については、「Active Directory フェデレーションサービス2.0 展開<http://go.microsoft.com/fwlink/p/?linkid=267511>ガイド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90fcc-122">For details, see the Active Directory Federation Services 2.0 Deployment Guide at <http://go.microsoft.com/fwlink/p/?linkid=267511>.</span></span>

2.  <span data-ttu-id="90fcc-123">AD FS の証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="90fcc-123">Create certificates for AD FS.</span></span> <span data-ttu-id="90fcc-124">詳細については、「AD FS を計画して展開する」の「フェデレーションサーバーの証明書」セクションを参照して[http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376)ください。シングルサインオンのトピックで使用します。</span><span class="sxs-lookup"><span data-stu-id="90fcc-124">For more information, see the "Federation server certificates" section of the Plan for and deploy AD FS for use with single sign-on topic at [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376).</span></span>

3.  <span data-ttu-id="90fcc-125">Windows PowerShell コマンドラインインターフェイスで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="90fcc-125">From the Windows PowerShell command-line interface, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  <span data-ttu-id="90fcc-126">次のコマンドを実行し、パートナーシップを確立します。</span><span class="sxs-lookup"><span data-stu-id="90fcc-126">Establish a partnership by running the following command:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```
5.  <span data-ttu-id="90fcc-127">以下の証明書利用者のルールを設定します。</span><span class="sxs-lookup"><span data-stu-id="90fcc-127">Set the following relying party rules:</span></span>
    
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

## <a name="known-issues-that-can-prevent-sign-in"></a><span data-ttu-id="90fcc-128">サインインを禁止できる既知の問題</span><span class="sxs-lookup"><span data-stu-id="90fcc-128">Known Issues that Can Prevent Sign-in</span></span>

<div>

## <a name="the-time-and-date-are-not-set-accurately-on-the-device-running-lync-windows-store-app"></a><span data-ttu-id="90fcc-129">Lync Windows ストアアプリが実行されているデバイスで時刻と日付が正しく設定されていない</span><span class="sxs-lookup"><span data-stu-id="90fcc-129">The time and date are not set accurately on the device running Lync Windows Store app</span></span>

<span data-ttu-id="90fcc-130">デバイスの時刻設定がサーバーの時刻設定と同期されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="90fcc-130">The time setting on the device must be synchronized with the time setting on the server.</span></span> <span data-ttu-id="90fcc-131">これは、Microsoft Surface などのデバイスや、ドメインに参加していない Windows RT を実行しているその他のデバイスで特に重要です。</span><span class="sxs-lookup"><span data-stu-id="90fcc-131">This is particularly important for devices such as Microsoft Surface, and other devices running Windows RT that are not joined to a domain.</span></span> <span data-ttu-id="90fcc-132">これらのデバイスの時刻を時刻サーバーから自動的に設定するには、デバイスの昇格されたコマンドプロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="90fcc-132">To set the time on these devices automatically from a time server, run the following command from an elevated command prompt on the device:</span></span>
```console
w32tm /resync
```
</div>

<div>

## <a name="lync-windows-store-app-cannot-access-the-lync-server-or-services"></a><span data-ttu-id="90fcc-133">Lync Windows ストアアプリが Lync サーバーまたはサービスにアクセスできない</span><span class="sxs-lookup"><span data-stu-id="90fcc-133">Lync Windows Store app cannot access the Lync server or services</span></span>

<span data-ttu-id="90fcc-134">Lync Windows ストアアプリでは、Windows 8 に物理デバイスとして登録されないネットワークアダプター (4G LTE USB モデムなど) を介して Lync サーバーまたはサービスにアクセスできない場合があります。</span><span class="sxs-lookup"><span data-stu-id="90fcc-134">Lync Windows Store app may not be able to access the Lync server or services through network adapters, such as 4G LTE USB modems, that do not register with Windows 8 as physical devices.</span></span> <span data-ttu-id="90fcc-135">デスクトップアプリやブラウザーが他のサーバーや web サイトにアクセスできる場合でも、Lync Windows ストアアプリでこの問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="90fcc-135">Lync Windows Store app may have this issue even when the desktop apps and browsers are able to access other servers and web sites.</span></span>

</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-with-lync-server-2010-and-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="90fcc-136">Lync Windows ストアアプリで Lync Server 2010 および Office Communications Server 2007 R2 Edge Server でサインインできない</span><span class="sxs-lookup"><span data-stu-id="90fcc-136">Lync Windows Store app cannot sign in with Lync Server 2010 and Office Communications Server 2007 R2 Edge Server</span></span>

<span data-ttu-id="90fcc-137">使用しているトポロジが Lync Server 2010 で構成されている Office Communications Server 2007 R2 Edge サーバーの場合は、Lync Server 2010: 2013 年7月の累積更新プログラムで利用可能なトポロジビルダーの更新バージョンを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90fcc-137">If your topology consists of Lync Server 2010 with Office Communications Server 2007 R2 Edge Server, you will need to run the updated version of Topology Builder available in the cumulative update for Lync Server 2010: July 2013.</span></span> <span data-ttu-id="90fcc-138">以前のバージョンのトポロジビルダーでは、Office Communications Server 2007 エッジサーバーへの必要なマッピングは作成されないため、Lync Windows ストアアプリクライアントではサインインできません。</span><span class="sxs-lookup"><span data-stu-id="90fcc-138">Earlier versions of Topology Builder do not create the required mapping to Office Communications Server 2007 Edge Server, so Lync Windows Store app clients are unable to sign in.</span></span> <span data-ttu-id="90fcc-139">次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90fcc-139">The following steps are required:</span></span>

1.  <span data-ttu-id="90fcc-140">Lync server 2010 の累積的な更新プログラムをインストールする: Lync Server 2010 プールおよび Lync Server 2010 ディレクターの2013年7月。</span><span class="sxs-lookup"><span data-stu-id="90fcc-140">Install the cumulative update for Lync Server 2010: July 2013 on Lync Server 2010 pools and Lync Server 2010 Directors.</span></span>

2.  <span data-ttu-id="90fcc-141">次の操作を行って、外部 SIP エントリポイントがエッジサーバーアドレスであることを示すために Lync 自動検出構成を更新します。</span><span class="sxs-lookup"><span data-stu-id="90fcc-141">Update the Lync AutoDiscover configuration to indicate that the external SIP entry point is the Edge server address by doing the following:</span></span>
    
    1.  <span data-ttu-id="90fcc-142">Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="90fcc-142">Open Lync Server Management Shell.</span></span>
    
    2.  <span data-ttu-id="90fcc-143">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="90fcc-143">Run the following command:</span></span>
        ```powershell
        Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443
        ```
</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-due-to-a-certificate-name-validation-failure"></a><span data-ttu-id="90fcc-144">証明書名の検証に失敗したため、Lync Windows ストアアプリでサインインできない</span><span class="sxs-lookup"><span data-stu-id="90fcc-144">Lync Windows Store App cannot sign in due to a certificate name validation failure</span></span>

<span data-ttu-id="90fcc-145">サインインの問題は、最新バージョンの Lync Windows ストアアプリを実行していない Office 365 ユーザーに対して発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="90fcc-145">A sign-in issue can occur for Office 365 users who are not running the latest version of Lync Windows Store app.</span></span> <span data-ttu-id="90fcc-146">この問題は通常、複数のドメインを使用している場合に発生します (たとえば、SIP URI は**userA@domainZ.com**が、エッジサーバーは**sip.domainX.com**)。</span><span class="sxs-lookup"><span data-stu-id="90fcc-146">This issue generally occurs when using multiple domains (for example, when the SIP URI is **userA@domainZ.com** but the Edge Server is **sip.domainX.com**).</span></span> <span data-ttu-id="90fcc-147">この問題を解決するには、ユーザーが最新バージョンの Lync Windows ストアアプリをインストールする必要があります。これには、Windows 8.1 が必要です。</span><span class="sxs-lookup"><span data-stu-id="90fcc-147">To fix the issue, users should install the latest version of Lync Windows Store app, which also requires Windows 8.1.</span></span>

</div>

</div>

<div>

## <a name="use-lync-windows-store-app-logs-to-troubleshoot-issues"></a><span data-ttu-id="90fcc-148">Lync Windows ストアアプリログを使って問題のトラブルシューティングを行う</span><span class="sxs-lookup"><span data-stu-id="90fcc-148">Use Lync Windows Store app logs to troubleshoot issues</span></span>

<span data-ttu-id="90fcc-149">デバイスで生成されたログを使用して、問題のトラブルシューティングを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="90fcc-149">You can use the logs generated on the device to troubleshoot issues.</span></span> <span data-ttu-id="90fcc-150">ログは、次のフォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="90fcc-150">The logs are stored in the following folder:</span></span>

<span data-ttu-id="90fcc-151">% LocalAppData%\\\\LyncMX\_8wekyb3d8bbwe\\localappdata\\Tracing</span><span class="sxs-lookup"><span data-stu-id="90fcc-151">%LocalAppData%\\Packages\\Microsoft.LyncMX\_8wekyb3d8bbwe\\LocalState\\Tracing</span></span>

<span data-ttu-id="90fcc-152">ユーザーからログを取得する前に、ログが有効になっていることを確認してから、メモリに保存されているすべての情報がハードドライブ上のファイルにも保存されるように、ログを保存するようにユーザーに依頼します。</span><span class="sxs-lookup"><span data-stu-id="90fcc-152">Before you get the logs from a user, make sure that logging is turned on, and then ask the user to save the logs so that all the information stored in memory is also saved to files on the hard drive.</span></span>

<span data-ttu-id="90fcc-153">**ログをオンにするには**</span><span class="sxs-lookup"><span data-stu-id="90fcc-153">**To turn on logging**</span></span>

1.  <span data-ttu-id="90fcc-154">デバイスで Lync Windows ストアアプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="90fcc-154">Open Lync Windows Store app on the device.</span></span>

2.  <span data-ttu-id="90fcc-155">画面の右側からスワイプします。</span><span class="sxs-lookup"><span data-stu-id="90fcc-155">Swipe from the right side of the screen.</span></span> <span data-ttu-id="90fcc-156">マウスを使用している場合は、画面の右上隅をポイントし、マウスポインターを画面の下に移動します。</span><span class="sxs-lookup"><span data-stu-id="90fcc-156">If you’re using a mouse, point to the upper-right corner of the screen and then move the mouse pointer down the screen.</span></span>

3.  <span data-ttu-id="90fcc-157">[**設定**]、[**オプション**] の順に選択し、[**診断ログ**] を **[オン**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="90fcc-157">Select **Settings**, select **Options**, and then set **Diagnostic Logs** to **On**.</span></span>

4.  <span data-ttu-id="90fcc-158">**診断ログ**が以前にオフになっていた場合は、Lync を再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90fcc-158">If **Diagnostic Logs** was off previously, you must restart Lync.</span></span> <span data-ttu-id="90fcc-159">Lync を再起動するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="90fcc-159">To restart Lync, do one of the following:</span></span>
    
      - <span data-ttu-id="90fcc-160">デバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="90fcc-160">Restart the device.</span></span>
    
      - <span data-ttu-id="90fcc-161">Lync タスクを終了して、アプリをもう一度起動します。</span><span class="sxs-lookup"><span data-stu-id="90fcc-161">End the Lync task and launch the app again.</span></span> <span data-ttu-id="90fcc-162">タスクを終了するには、Windows タスクマネージャーを開き、[ **Lync**] を選択して、[**タスクの終了**] をタップします。</span><span class="sxs-lookup"><span data-stu-id="90fcc-162">To end the task, open the Windows Task Manager, select **Lync**, and then tap **End task**.</span></span> <span data-ttu-id="90fcc-163">Lync が一覧に表示されていない場合は、[**詳細**] をタップして、[**バックグラウンドプロセス**] で lync を探します。</span><span class="sxs-lookup"><span data-stu-id="90fcc-163">If Lync is not listed, tap **More details** and look for Lync under **Background processes**.</span></span>

<span data-ttu-id="90fcc-164">**ログを保存するには**</span><span class="sxs-lookup"><span data-stu-id="90fcc-164">**To save the logs**</span></span>

1.  <span data-ttu-id="90fcc-165">デバイスで Lync Windows ストアアプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="90fcc-165">Open Lync Windows Store app on the device.</span></span>

2.  <span data-ttu-id="90fcc-166">サインインしてみてください。</span><span class="sxs-lookup"><span data-stu-id="90fcc-166">Try signing in.</span></span>

3.  <span data-ttu-id="90fcc-167">画面の右側からスワイプします。</span><span class="sxs-lookup"><span data-stu-id="90fcc-167">Swipe from the right side of the screen.</span></span> <span data-ttu-id="90fcc-168">マウスを使用している場合は、画面の右上隅をポイントし、マウスポインターを画面の下に移動します。</span><span class="sxs-lookup"><span data-stu-id="90fcc-168">If you’re using a mouse, point to the upper-right corner of the screen and then move the mouse pointer down the screen.</span></span>

4.  <span data-ttu-id="90fcc-169">[**設定**] を選択し、[**バージョン情報**] を選択して、[**ログの保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="90fcc-169">Select **Settings**, select **About**, and then select **Save logs**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

