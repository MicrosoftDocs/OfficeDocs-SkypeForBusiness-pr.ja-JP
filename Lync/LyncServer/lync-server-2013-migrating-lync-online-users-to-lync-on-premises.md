---
title: 'Lync Server 2013: lync Online ユーザーの Lync オンプレミスへの移行'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migrating Lync Online users to Lync on-premises
ms:assetid: 0e29605b-db2d-4cbf-b6a9-15db6b9fdabc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689115(v=OCS.15)
ms:contentKeyID: 62258120
ms.date: 11/13/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a2be7414dbdc48c9e245db33e57b8238cfb2ee9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520994"
---
# <a name="migrating-lync-online-users-to-lync-on-premises-in-lync-server-2013"></a><span data-ttu-id="6a644-102">Lync Online ユーザーを lync Server 2013 の Lync オンプレミスに移行する</span><span class="sxs-lookup"><span data-stu-id="6a644-102">Migrating Lync Online users to Lync on-premises in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a644-103">_**トピックの最終更新日:** 2015-11-13_</span><span class="sxs-lookup"><span data-stu-id="6a644-103">_**Topic Last Modified:** 2015-11-13_</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="6a644-104">これらの手順は、lync オンプレミスを展開する前に lync Online の Lync で最初に有効にされたユーザーアカウントを移行する場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="6a644-104">These steps are necessary only for migrating user accounts that were originally enabled for Lync in Lync Online, before you deployed Lync on-premises.</span></span> <span data-ttu-id="6a644-105">最初に Lync Online が有効になっていて、後で Lync Online に移動されたユーザーを移動するには、「 <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">ハイブリッド Lync Server 2013 展開でユーザーを管理</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a644-105">To move users who were originally enabled for Lync on-premises, then later moved to Lync Online, see <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administering users in a hybrid Lync Server 2013 deployment</A>.</span></span><BR><span data-ttu-id="6a644-106">さらに、移動するすべてのユーザーは、オンプレミスの Active Directory にアカウントを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a644-106">Additionally, all users being moved must have accounts in the on-premises Active Directory.</span></span>



</div>

<div>

## <a name="migrating-user-accounts-originally-enabled-in-lync-online-to-lync-on-premises"></a><span data-ttu-id="6a644-107">Lync Online で最初に有効にされるユーザーアカウントを、オンプレミスの Lync に移行する</span><span class="sxs-lookup"><span data-stu-id="6a644-107">Migrating User Accounts Originally Enabled in Lync Online to Lync On-Premises</span></span>

1.  <span data-ttu-id="6a644-108">最初に、組織がハイブリッド用に構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6a644-108">First, make sure that your organization is configured for hybrid.</span></span>
    
      - <span data-ttu-id="6a644-109">Azure Active Directory 同期ツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="6a644-109">Install the Azure Active Directory Sync Tool.</span></span> <span data-ttu-id="6a644-110">詳細については、「<https://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a644-110">For more information, see <https://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.</span></span>
    
      - <span data-ttu-id="6a644-111">ユーザーが Lync Online のシングルサインオンを使用できるようにするには、Active Directory フェデレーションサービスをインストール <https://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx> します。</span><span class="sxs-lookup"><span data-stu-id="6a644-111">To enable your users to use single sign-on for Lync Online, install Active Directory Federation Services <https://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>.</span></span>
    
      - <span data-ttu-id="6a644-112">オンプレミス展開で、Lync Server 管理シェルの次のコマンドレットを入力して、Lync Online のホスティングプロバイダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="6a644-112">On your on-premises deployment, in Lync Server Management Shell, type the following cmdlets to create the hosting provider for Lync Online:</span></span>
        
           ```PowerShell
           Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
           ```
        
           ```PowerShell
            New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
           ```

2.  <span data-ttu-id="6a644-113">オンプレミスのエッジサーバーに、次の表に示すように、Lync Online への接続を可能にする証明書チェーンがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6a644-113">Confirm that, on your on-premises Edge Servers, you have the certificate chain that enables connection to Lync Online, as shown in the following table.</span></span> <span data-ttu-id="6a644-114">このチェーンは、ここからダウンロードできます。 https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb</span><span class="sxs-lookup"><span data-stu-id="6a644-114">You can download this chain here: https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb</span></span>


    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="6a644-115">証明書</span><span class="sxs-lookup"><span data-stu-id="6a644-115">Certificate</span></span></th>
    <th><span data-ttu-id="6a644-116">証明書ストア</span><span class="sxs-lookup"><span data-stu-id="6a644-116">Certificate Store</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="6a644-117">Baltimore CyberTrust Root</span><span class="sxs-lookup"><span data-stu-id="6a644-117">Baltimore CyberTrust Root</span></span></p></td>
    <td><p><span data-ttu-id="6a644-118">信頼されたルート CA</span><span class="sxs-lookup"><span data-stu-id="6a644-118">Trusted Root CA</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="6a644-119">Microsoft インターネット権威 (新規 CA 証明書)</span><span class="sxs-lookup"><span data-stu-id="6a644-119">Microsoft Internet Authority (New CA certificate)</span></span></p></td>
    <td><p><span data-ttu-id="6a644-120">中間 CA</span><span class="sxs-lookup"><span data-stu-id="6a644-120">Intermediate CA</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="6a644-121">MSIT Machine Auth CA2 (新しい発行 CA2)</span><span class="sxs-lookup"><span data-stu-id="6a644-121">MSIT Machine Auth CA2 (New Issuing CA2)</span></span></p></td>
    <td><p><span data-ttu-id="6a644-122">中間 CA</span><span class="sxs-lookup"><span data-stu-id="6a644-122">Intermediate CA</span></span></p></td>
    </tr>
    </tbody>
    </table>

3.  <span data-ttu-id="6a644-123">オンプレミスの Active Directory で、該当する Lync オンプレミスのユーザーアカウントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="6a644-123">In your on-premises Active Directory, enable the affected user accounts for Lync on-premises.</span></span> <span data-ttu-id="6a644-124">この操作は、次のコマンドレットを入力することにより、個々のユーザーに対して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6a644-124">You can do this for an individual user by typing the following cmdlet:</span></span>
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    <span data-ttu-id="6a644-125">または、ファイルからユーザー名を読み取り、それを Enable-CsUser コマンドレットへの入力として提供するスクリプトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="6a644-125">Or you can create a script that reads user names from a file and provides them as input to the Enable-CsUser cmdlet:</span></span>
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  <span data-ttu-id="6a644-126">DirSync を実行して、Lync Online ユーザーと、更新された Lync オンプレミスユーザーを同期します。</span><span class="sxs-lookup"><span data-stu-id="6a644-126">Run DirSync to sync the Lync Online users with the updated Lync on-premises users.</span></span>

5.  <span data-ttu-id="6a644-127">一部の DNS レコードを更新して、すべての SIP トラフィックを社内の Lync に転送します。</span><span class="sxs-lookup"><span data-stu-id="6a644-127">Update some DNS records to direct all SIP traffic to Lync on-premises:</span></span>
    
      - <span data-ttu-id="6a644-128">**Lyncdiscover.contoso.com** A レコードを更新して、オンプレミスのリバースプロキシサーバーの FQDN を指すようにします。</span><span class="sxs-lookup"><span data-stu-id="6a644-128">Update the **lyncdiscover.contoso.com** A record to point to the FQDN of the on-premises reverse proxy server.</span></span>
    
      - <span data-ttu-id="6a644-129">\* Sip \* を更新し\*\* \_ ます。 \_\*\* Lync オンプレミスのアクセスエッジサービスのパブリック IP または VIP アドレスに解決する Tls.contoso.com SRV レコード。</span><span class="sxs-lookup"><span data-stu-id="6a644-129">Update the \***\_sip\*.\_tls.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
      - <span data-ttu-id="6a644-130">\* Sipfederationtls \* を更新し\*\* \_ ます。 \_\*\* Lync オンプレミスのアクセスエッジサービスのパブリック IP または VIP アドレスに解決する Tcp.contoso.com SRV レコード。</span><span class="sxs-lookup"><span data-stu-id="6a644-130">Update the \***\_sipfederationtls\*.\_tcp.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
      - <span data-ttu-id="6a644-131">組織で分割 DNS ("スプリットブレイン DNS" と呼ばれることもあります) を使用している場合は、内部 DNS ゾーンを使用して名前を解決するユーザーがフロントエンドプールに転送されることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6a644-131">If your organization uses split DNS (sometimes called “split-brain DNS”), make sure that users resolving names through the internal DNS zone are directed to the Front End Pool.</span></span>

6.  <span data-ttu-id="6a644-132">コマンドレットを入力して、 `Get-CsUser` 移動するユーザーに関するいくつかのプロパティを確認します。</span><span class="sxs-lookup"><span data-stu-id="6a644-132">Type the `Get-CsUser` cmdlet to check some properties about the users you’ll be moving.</span></span> <span data-ttu-id="6a644-133">HostingProviderProxyFQDN がに設定され、 `"sipfed.online.lync.com"` SIP アドレスが正しく設定されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a644-133">You want to make sure that the HostingProviderProxyFQDN is set to `"sipfed.online.lync.com"` and that the SIP addresses are set correctly.</span></span>

7.  <span data-ttu-id="6a644-134">Lync Online ユーザーをオンプレミスの Lync に移動します。</span><span class="sxs-lookup"><span data-stu-id="6a644-134">Move Lync Online users to Lync on-premises.</span></span>
    
    <span data-ttu-id="6a644-135">単一のユーザーを移動するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="6a644-135">To move a single user, type this:</span></span>
    
       ```PowerShell
       $cred = Get-Credential
       ```
    
       ```PowerShell
       Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
       ```
    
    <span data-ttu-id="6a644-136">-Filter パラメーターを指定して **Get-help ユーザー** コマンドレットを使用して、特定のプロパティを持つユーザーを選択すると、複数のユーザーを移動できます。</span><span class="sxs-lookup"><span data-stu-id="6a644-136">You can move multiple users by using the **Get-CsUSer** cmdlet with the –Filter parameter to select the users with a specific property.</span></span> <span data-ttu-id="6a644-137">たとえば、{ホスティングプロバイダー– eq "sipfed.online.lync.om"} にフィルターを適用することにより、すべての Lync Online ユーザーを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="6a644-137">For example, you could select all Lync Online users by filtering for {Hosting Provider –eq “sipfed.online.lync.om”}.</span></span> <span data-ttu-id="6a644-138">その後、次に示すように、返されたユーザーを移動して、 **csuser** コマンドレットにパイプ処理できます。</span><span class="sxs-lookup"><span data-stu-id="6a644-138">You can then pipe the returned users to the **Move-CsUSer** cmdlet, as shown below.</span></span>
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    <span data-ttu-id="6a644-139">**HostedMigrationOverrideUrl**パラメーターに指定する url の形式は、次の形式で、ホストされた移行サービスが実行されているプールへの url である必要があります。 *Https:// \<Pool FQDN\> /HostedMigration/hostedmigrationService.svc*。</span><span class="sxs-lookup"><span data-stu-id="6a644-139">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: *Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc*.</span></span>
    
    <span data-ttu-id="6a644-140">ホストされている移行サービスへの URL を確認するには、Microsoft 365 または Office 365 組織アカウントの Lync Online コントロールパネルの URL を表示します。</span><span class="sxs-lookup"><span data-stu-id="6a644-140">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Microsoft 365 or Office 365 organization account.</span></span>
    
    <div>
    
    ## <a name="to-determine-the-hosted-migration-service-url-for-your-organizaton"></a><span data-ttu-id="6a644-141">組織のためのホスト型移行サービスの URL を決定するには</span><span class="sxs-lookup"><span data-stu-id="6a644-141">To determine the Hosted Migration Service URL for your organizaton</span></span>
    
    1.  <span data-ttu-id="6a644-142">Microsoft 365 または Office 365 組織に管理者としてログインします。</span><span class="sxs-lookup"><span data-stu-id="6a644-142">Log in to your Microsoft 365 or Office 365 organization as an administrator.</span></span>
    
    2.  <span data-ttu-id="6a644-143">**Lync 管理センター**を開きます。</span><span class="sxs-lookup"><span data-stu-id="6a644-143">Open the **Lync admin center**.</span></span>
    
    3.  <span data-ttu-id="6a644-144">**Lync 管理センター**が表示されたら、アドレスバーの URL を選択して、 **lync.com**までコピーします。</span><span class="sxs-lookup"><span data-stu-id="6a644-144">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="6a644-145">URL の例は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6a644-145">An example URL looks similar to the following:</span></span>
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  <span data-ttu-id="6a644-146">URL 内の **webdir** を **管理者**に置き換えます。結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6a644-146">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
        
        `https://admin0a.online.lync.com`
    
    5.  <span data-ttu-id="6a644-147">次の文字列を URL: **/HostedMigration/hostedmigrationservice.svc**に追加します。</span><span class="sxs-lookup"><span data-stu-id="6a644-147">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
        
        <span data-ttu-id="6a644-148">生成される URL は **HostedMigrationOverrideUrl**の値で、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6a644-148">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    </div>
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="6a644-149">Rtcxds データベースのトランザクションログファイルの既定の最大サイズは 16 GB です。</span><span class="sxs-lookup"><span data-stu-id="6a644-149">The default maximum size for transaction log files of the rtcxds database is 16 GB.</span></span> <span data-ttu-id="6a644-150">多数のユーザーを同時に移動する場合は、特にミラーリングを有効にしている場合は、この値が十分ではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6a644-150">This might not be big enough if you’re moving a large number of users at once, especially if you have mirroring enabled.</span></span> <span data-ttu-id="6a644-151">これを回避するには、ファイルサイズを増やすか、またはログファイルを定期的にバックアップします。</span><span class="sxs-lookup"><span data-stu-id="6a644-151">To get around this you can increase the file size or back up the log files regularly.</span></span> <span data-ttu-id="6a644-152">詳細については、「」を参照してください <A class=uri href="https://support.microsoft.com/kb/2756725">https://support.microsoft.com/kb/2756725</A> 。</span><span class="sxs-lookup"><span data-stu-id="6a644-152">For more information, see <A class=uri href="https://support.microsoft.com/kb/2756725">https://support.microsoft.com/kb/2756725</A>.</span></span>

    
    </div>

8.  <span data-ttu-id="6a644-153">この手順は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="6a644-153">This is an optional step.</span></span> <span data-ttu-id="6a644-154">Exchange 2013 Online と統合する必要がある場合は、追加のホスティングプロバイダーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a644-154">If you need to integrate with Exchange 2013 Online, you need to use an additional hosting provider.</span></span> <span data-ttu-id="6a644-155">詳細については、「 [オンプレミスの Lync Server 2013 と Exchange Online との統合の構成](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a644-155">For details, see [Configuring on-premises Lync Server 2013 integration with Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).</span></span>

9.  <span data-ttu-id="6a644-156">ユーザーが移動されました。</span><span class="sxs-lookup"><span data-stu-id="6a644-156">The users are now moved.</span></span> <span data-ttu-id="6a644-157">ユーザーが次の表に示す属性の値を正しいかどうかを確認するには、次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="6a644-157">To check that a user has correct values for the attributes shown in the following table, type this cmdlet:</span></span>
    
        Get-CsUser | fl DisplayName,HostingProvider,SipAddress,Enabled
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="6a644-158">Active Directory 属性</span><span class="sxs-lookup"><span data-stu-id="6a644-158">Active Directory attribute</span></span></th>
    <th><span data-ttu-id="6a644-159">属性名</span><span class="sxs-lookup"><span data-stu-id="6a644-159">Attribute name</span></span></th>
    <th><span data-ttu-id="6a644-160">Lync Online ユーザーの正しい値</span><span class="sxs-lookup"><span data-stu-id="6a644-160">Correct value for Lync Online user</span></span></th>
    <th><span data-ttu-id="6a644-161">Lync オンプレミスユーザーの正しい値</span><span class="sxs-lookup"><span data-stu-id="6a644-161">Correct value for Lync on–premises users</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="6a644-162">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="6a644-162">msRTCSIP-DeploymentLocator</span></span></p></td>
    <td><p><span data-ttu-id="6a644-163">HostingProvider</span><span class="sxs-lookup"><span data-stu-id="6a644-163">HostingProvider</span></span></p></td>
    <td><p><span data-ttu-id="6a644-164">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6a644-164">sipfed.online.lync.com</span></span></p></td>
    <td><p><span data-ttu-id="6a644-165">SRV</span><span class="sxs-lookup"><span data-stu-id="6a644-165">SRV:</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="6a644-166">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="6a644-166">msRTCSIP-PrimaryUserAddress</span></span></p></td>
    <td><p><span data-ttu-id="6a644-167">SIPAddress</span><span class="sxs-lookup"><span data-stu-id="6a644-167">SIPAddress</span></span></p></td>
    <td><p><span data-ttu-id="6a644-168">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="6a644-168">sip:userName@contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="6a644-169">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="6a644-169">sip:userName@contoso.com</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="6a644-170">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="6a644-170">msRTCSIP-UserEnabled</span></span></p></td>
    <td><p><span data-ttu-id="6a644-171">Enabled</span><span class="sxs-lookup"><span data-stu-id="6a644-171">Enabled</span></span></p></td>
    <td><p><span data-ttu-id="6a644-172">True</span><span class="sxs-lookup"><span data-stu-id="6a644-172">True</span></span></p></td>
    <td><p><span data-ttu-id="6a644-173">True</span><span class="sxs-lookup"><span data-stu-id="6a644-173">True</span></span></p></td>
    </tr>
    </tbody>
    </table>


10. <span data-ttu-id="6a644-174">移動した各ユーザーは、Lync からログアウトしてログインし直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a644-174">Each user who has been moved will need to log out of Lync, then log back in.</span></span> <span data-ttu-id="6a644-175">ログインするときに、連絡先リストを確認し、必要に応じて連絡先を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a644-175">When they log in they should verify their contact lists, and add contacts if needed.</span></span>
    
    <span data-ttu-id="6a644-176">予約済みの会議は、Lync Online から Lync オンプレミスに移行されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6a644-176">Note that scheduled meetings are not migrated from Lync Online to Lync on-premises.</span></span> <span data-ttu-id="6a644-177">ユーザーは、移動後にこれらの会議を再度スケジュールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a644-177">Users will need to reschedule these meetings after being moved.</span></span>
    
    <span data-ttu-id="6a644-178">DNS レコードが更新され、すべてのユーザーがオンプレミスにリダイレクトされると、HostingProvider 属性によって Lync ユーザーは SRV レコードを使用するか、またはオンラインプロバイダー "sipfed.online.lync.com" に直接接続します。</span><span class="sxs-lookup"><span data-stu-id="6a644-178">After the DNS records are updated and all users are directed to On premise, the HostingProvider attribute directs the Lync user to either use SRV records or direct them to the Online provider “sipfed.online.lync.com.”</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

