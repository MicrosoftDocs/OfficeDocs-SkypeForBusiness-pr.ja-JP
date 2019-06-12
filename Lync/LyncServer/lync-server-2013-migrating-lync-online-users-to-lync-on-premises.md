---
title: 'Lync Server 2013: lync Online ユーザーをオンプレミスの Lync に移行する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migrating Lync Online users to Lync on-premises
ms:assetid: 0e29605b-db2d-4cbf-b6a9-15db6b9fdabc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689115(v=OCS.15)
ms:contentKeyID: 62258120
ms.date: 11/13/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d33888069b00eaf8a4d743f1e6ed3937d7a442bc
ms.sourcegitcommit: 5895afd0d5752a6ea1ace68d613f86c68eae8bdb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2019
ms.locfileid: "34857492"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-lync-online-users-to-lync-on-premises-in-lync-server-2013"></a><span data-ttu-id="a90ab-102">Lync Online ユーザーをオンプレミスの lync Server に移行する2013</span><span class="sxs-lookup"><span data-stu-id="a90ab-102">Migrating Lync Online users to Lync on-premises in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a90ab-103">_**最終更新日:** 2015-11-13_</span><span class="sxs-lookup"><span data-stu-id="a90ab-103">_**Topic Last Modified:** 2015-11-13_</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="a90ab-104">以下の手順は、lync をオンプレミスで展開する前に、lync Online の Lync で最初に有効になっていたユーザーアカウントを移行する場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="a90ab-104">These steps are necessary only for migrating user accounts that were originally enabled for Lync in Lync Online, before you deployed Lync on-premises.</span></span> <span data-ttu-id="a90ab-105">初めて Lync をオンプレミスで有効にしたユーザーを移動し、後で Lync Online に移行するには、「<A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">ハイブリッド Lync Server 2013 展開でユーザーを管理</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a90ab-105">To move users who were originally enabled for Lync on-premises, then later moved to Lync Online, see <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administering users in a hybrid Lync Server 2013 deployment</A>.</span></span><BR><span data-ttu-id="a90ab-106">さらに、移動対象のすべてのユーザーは、オンプレミス Active Directory にアカウントを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a90ab-106">Additionally, all users being moved must have accounts in the on-premises Active Directory.</span></span>



</div>

<div>

## <a name="migrating-user-accounts-originally-enabled-in-lync-online-to-lync-on-premises"></a><span data-ttu-id="a90ab-107">初めて Lync Online で有効化されるユーザーアカウントをオンプレミスの Lync に移行する</span><span class="sxs-lookup"><span data-stu-id="a90ab-107">Migrating User Accounts Originally Enabled in Lync Online to Lync On-Premises</span></span>

1.  <span data-ttu-id="a90ab-108">最初に、組織がハイブリッド用に構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a90ab-108">First, make sure that your organization is configured for hybrid.</span></span>
    
      - <span data-ttu-id="a90ab-109">Azure Active Directory 同期ツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a90ab-109">Install the Azure Active Directory Sync Tool.</span></span> <span data-ttu-id="a90ab-110">詳細については<http://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a90ab-110">For more information, see <http://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.</span></span>
    
      - <span data-ttu-id="a90ab-111">Lync Online でユーザーがシングルサインオンを使用できるようにするには、Active Directory <http://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>フェデレーションサービスをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a90ab-111">To enable your users to use single sign-on for Lync Online, install Active Directory Federation Services <http://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>.</span></span>
    
      - <span data-ttu-id="a90ab-112">オンプレミスの展開の Lync Server 管理シェルで、次のコマンドレットを入力して、Lync Online のホスティングプロバイダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="a90ab-112">On your on-premises deployment, in Lync Server Management Shell, type the following cmdlets to create the hosting provider for Lync Online:</span></span>
        
           ```
           Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
           ```
        
           ```
            New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
           ```

2.  <span data-ttu-id="a90ab-113">オンプレミスエッジサーバーで、次の表に示すように、Lync Online への接続を有効にする証明書チェーンがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a90ab-113">Confirm that, on your on-premises Edge Servers, you have the certificate chain that enables connection to Lync Online, as shown in the following table.</span></span> <span data-ttu-id="a90ab-114">このチェーンは次のページからダウンロードできます。https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb</span><span class="sxs-lookup"><span data-stu-id="a90ab-114">You can download this chain here: https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb</span></span>


    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="a90ab-115">証明書</span><span class="sxs-lookup"><span data-stu-id="a90ab-115">Certificate</span></span></th>
    <th><span data-ttu-id="a90ab-116">証明書ストア</span><span class="sxs-lookup"><span data-stu-id="a90ab-116">Certificate Store</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="a90ab-117">Baltimore CyberTrust Root</span><span class="sxs-lookup"><span data-stu-id="a90ab-117">Baltimore CyberTrust Root</span></span></p></td>
    <td><p><span data-ttu-id="a90ab-118">信頼されたルート CA</span><span class="sxs-lookup"><span data-stu-id="a90ab-118">Trusted Root CA</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="a90ab-119">Microsoft Internet Authority (新しい CA 証明書)</span><span class="sxs-lookup"><span data-stu-id="a90ab-119">Microsoft Internet Authority (New CA certificate)</span></span></p></td>
    <td><p><span data-ttu-id="a90ab-120">中間 CA</span><span class="sxs-lookup"><span data-stu-id="a90ab-120">Intermediate CA</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="a90ab-121">MSIT Machine Auth CA2 (新規発行 CA2)</span><span class="sxs-lookup"><span data-stu-id="a90ab-121">MSIT Machine Auth CA2 (New Issuing CA2)</span></span></p></td>
    <td><p><span data-ttu-id="a90ab-122">中間 CA</span><span class="sxs-lookup"><span data-stu-id="a90ab-122">Intermediate CA</span></span></p></td>
    </tr>
    </tbody>
    </table>

3.  <span data-ttu-id="a90ab-123">オンプレミスの Active Directory で、オンプレミスの Lync の影響を受けるユーザーアカウントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="a90ab-123">In your on-premises Active Directory, enable the affected user accounts for Lync on-premises.</span></span> <span data-ttu-id="a90ab-124">ユーザーごとにこの操作を行うには、次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="a90ab-124">You can do this for an individual user by typing the following cmdlet:</span></span>
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    <span data-ttu-id="a90ab-125">または、ファイルからユーザー名を読み込んで Enable-CsUser コマンドレットへの入力として与えるスクリプトを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="a90ab-125">Or you can create a script that reads user names from a file and provides them as input to the Enable-CsUser cmdlet:</span></span>
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  <span data-ttu-id="a90ab-126">DirSync を実行して、Lync Online ユーザーと、更新された Lync オンプレミスユーザーを同期します。</span><span class="sxs-lookup"><span data-stu-id="a90ab-126">Run DirSync to sync the Lync Online users with the updated Lync on-premises users.</span></span>

5.  <span data-ttu-id="a90ab-127">すべての SIP トラフィックがオンプレミスの Lync に転送されるように、いくつかの DNS レコードを更新します。</span><span class="sxs-lookup"><span data-stu-id="a90ab-127">Update some DNS records to direct all SIP traffic to Lync on-premises:</span></span>
    
      - <span data-ttu-id="a90ab-128">オンプレミスのリバース プロキシ サーバーの FQDN を指すように **lyncdiscover.contoso.com** A レコードを更新します。</span><span class="sxs-lookup"><span data-stu-id="a90ab-128">Update the **lyncdiscover.contoso.com** A record to point to the FQDN of the on-premises reverse proxy server.</span></span>
    
      - <span data-ttu-id="a90ab-129">\***\_Sip \* を更新し\_ます。** オンプレミスの Lync のアクセスエッジサービスのパブリック IP または VIP アドレスに解決する Tls.contoso.com SRV レコード。</span><span class="sxs-lookup"><span data-stu-id="a90ab-129">Update the \***\_sip\*.\_tls.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
      - <span data-ttu-id="a90ab-130">\* Sipfederationtls \* を更新して**\_ください。\_** オンプレミスの Lync のアクセスエッジサービスのパブリック IP または VIP アドレスに解決する Tcp.contoso.com SRV レコード。</span><span class="sxs-lookup"><span data-stu-id="a90ab-130">Update the \***\_sipfederationtls\*.\_tcp.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
      - <span data-ttu-id="a90ab-131">組織でスプリット DNS ("スプリットブレイン DNS" と呼ばれることもあります) を使用している場合は、社内 DNS ゾーンを介して名前が解決されるユーザーがフロント エンド プールに転送されることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a90ab-131">If your organization uses split DNS (sometimes called “split-brain DNS”), make sure that users resolving names through the internal DNS zone are directed to the Front End Pool.</span></span>

6.  <span data-ttu-id="a90ab-132">移動する`Get-CsUser`ユーザーに関する一部のプロパティを確認するコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="a90ab-132">Type the `Get-CsUser` cmdlet to check some properties about the users you’ll be moving.</span></span> <span data-ttu-id="a90ab-133">HostingProviderProxyFQDN がに`"sipfed.online.lync.com"`設定されていて、SIP アドレスが正しく設定されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a90ab-133">You want to make sure that the HostingProviderProxyFQDN is set to `"sipfed.online.lync.com"` and that the SIP addresses are set correctly.</span></span>

7.  <span data-ttu-id="a90ab-134">Lync Online ユーザーをオンプレミスの Lync に移動します。</span><span class="sxs-lookup"><span data-stu-id="a90ab-134">Move Lync Online users to Lync on-premises.</span></span>
    
    <span data-ttu-id="a90ab-135">単独のユーザーを移動するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="a90ab-135">To move a single user, type this:</span></span>
    
       ```
       $cred = Get-Credential
       ```
    
       ```
       Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
       ```
    
    <span data-ttu-id="a90ab-136">複数のユーザーを移動するには\*\*\*\* 、-Filter パラメーターを指定して、特定のプロパティを持つユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="a90ab-136">You can move multiple users by using the **Get-CsUSer** cmdlet with the –Filter parameter to select the users with a specific property.</span></span> <span data-ttu-id="a90ab-137">たとえば、{ホスティングプロバイダー– eq "sipfed.online.lync.om"} をフィルター処理することによって、すべての Lync Online ユーザーを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="a90ab-137">For example, you could select all Lync Online users by filtering for {Hosting Provider –eq “sipfed.online.lync.om”}.</span></span> <span data-ttu-id="a90ab-138">次に示すように、返されたユーザーを**移動-CsUSer**コマンドレットにパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="a90ab-138">You can then pipe the returned users to the **Move-CsUSer** cmdlet, as shown below.</span></span>
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    <span data-ttu-id="a90ab-139">**HostedMigrationOverrideUrl**パラメーターに指定する url の形式は、次の形式で、ホステッド移行サービスが実行されているプールへの url である必要があります。 *Https://\<pool FQDN\>/HostedMigration/hostedmigrationService*。</span><span class="sxs-lookup"><span data-stu-id="a90ab-139">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: *Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc*.</span></span>
    
    <span data-ttu-id="a90ab-140">ホスティング型移行サービスへの URL は、ご使用の Office 365 テナント アカウント用の Lync Online コントロール パネルの URL を表示することで確認できます。</span><span class="sxs-lookup"><span data-stu-id="a90ab-140">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>
    
    <div>
    
    ## <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a><span data-ttu-id="a90ab-141">Office 365 テナントのホスティング型移行サービスの URL を確認するには</span><span class="sxs-lookup"><span data-stu-id="a90ab-141">To determine the Hosted Migration Service URL for your Office 365 tenant</span></span>
    
    1.  <span data-ttu-id="a90ab-142">管理者として Office 365 テナントにログインします。</span><span class="sxs-lookup"><span data-stu-id="a90ab-142">Login to your Office 365 tenant as an administrator.</span></span>
    
    2.  <span data-ttu-id="a90ab-143">**Lync 管理センター**を開きます。</span><span class="sxs-lookup"><span data-stu-id="a90ab-143">Open the **Lync admin center**.</span></span>
    
    3.  <span data-ttu-id="a90ab-144">**Lync 管理センター**が表示されたら、アドレスバーの URL を選択して**lync.com**にコピーします。</span><span class="sxs-lookup"><span data-stu-id="a90ab-144">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="a90ab-145">URL は、次のような書式です。</span><span class="sxs-lookup"><span data-stu-id="a90ab-145">An example URL looks similar to the following:</span></span>
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  <span data-ttu-id="a90ab-146">URL の **webdir** を **admin** に置き換えると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="a90ab-146">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
        
        `https://admin0a.online.lync.com`
    
    5.  <span data-ttu-id="a90ab-147">URL に以下の文字列を付加します。**/HostedMigration/hostedmigrationservice.svc**</span><span class="sxs-lookup"><span data-stu-id="a90ab-147">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
        
        <span data-ttu-id="a90ab-148">以上の手順によって、**HostedMigrationOverrideUrl** の値を持った URL は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="a90ab-148">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    </div>
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="a90ab-149">rtcxds データベースのトランザクション ログ ファイルの既定の最大サイズは 16 GB です。</span><span class="sxs-lookup"><span data-stu-id="a90ab-149">The default maximum size for transaction log files of the rtcxds database is 16 GB.</span></span> <span data-ttu-id="a90ab-150">一度に多くのユーザーを移行する場合 (特にミラーリングを有効にしている場合) は、このサイズでは不十分な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a90ab-150">This might not be big enough if you’re moving a large number of users at once, especially if you have mirroring enabled.</span></span> <span data-ttu-id="a90ab-151">これに対処するには、ファイル サイズを大きくするか、ログ ファイルを定期的にバックアップします。</span><span class="sxs-lookup"><span data-stu-id="a90ab-151">To get around this you can increase the file size or back up the log files regularly.</span></span> <span data-ttu-id="a90ab-152">詳細については<A class=uri href="http://support.microsoft.com/kb/2756725">http://support.microsoft.com/kb/2756725</A>、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a90ab-152">For more information, see <A class=uri href="http://support.microsoft.com/kb/2756725">http://support.microsoft.com/kb/2756725</A>.</span></span>

    
    </div>

8.  <span data-ttu-id="a90ab-153">この手順は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="a90ab-153">This is an optional step.</span></span> <span data-ttu-id="a90ab-154">Exchange 2013 Online と統合する必要がある場合は、追加のホスティング プロバイダーが必要になります。</span><span class="sxs-lookup"><span data-stu-id="a90ab-154">If you need to integrate with Exchange 2013 Online, you need to use an additional hosting provider.</span></span> <span data-ttu-id="a90ab-155">詳細については、「[オンプレミスの Lync Server 2013 と Exchange Online との統合を構成する](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a90ab-155">For details, see [Configuring on-premises Lync Server 2013 integration with Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).</span></span>

9.  <span data-ttu-id="a90ab-p110">ユーザーが移動されます。次の表に示すユーザーの属性の値が適切であることを確認するために、次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="a90ab-p110">The users are now moved. To check that a user has correct values for the attributes shown in the following table, type this cmdlet:</span></span>
    
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
    <th><span data-ttu-id="a90ab-158">Active Directory 属性</span><span class="sxs-lookup"><span data-stu-id="a90ab-158">Active Directory attribute</span></span></th>
    <th><span data-ttu-id="a90ab-159">属性名</span><span class="sxs-lookup"><span data-stu-id="a90ab-159">Attribute name</span></span></th>
    <th><span data-ttu-id="a90ab-160">Lync Online ユーザーの正しい値</span><span class="sxs-lookup"><span data-stu-id="a90ab-160">Correct value for Lync Online user</span></span></th>
    <th><span data-ttu-id="a90ab-161">Lync on プレミスユーザーの正しい値</span><span class="sxs-lookup"><span data-stu-id="a90ab-161">Correct value for Lync on–premises users</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="a90ab-162">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="a90ab-162">msRTCSIP-DeploymentLocator</span></span></p></td>
    <td><p><span data-ttu-id="a90ab-163">HostingProvider</span><span class="sxs-lookup"><span data-stu-id="a90ab-163">HostingProvider</span></span></p></td>
    <td><p><span data-ttu-id="a90ab-164">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a90ab-164">sipfed.online.lync.com</span></span></p></td>
    <td><p><span data-ttu-id="a90ab-165">SRV</span><span class="sxs-lookup"><span data-stu-id="a90ab-165">SRV:</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="a90ab-166">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="a90ab-166">msRTCSIP-PrimaryUserAddress</span></span></p></td>
    <td><p><span data-ttu-id="a90ab-167">SIPAddress</span><span class="sxs-lookup"><span data-stu-id="a90ab-167">SIPAddress</span></span></p></td>
    <td><p><span data-ttu-id="a90ab-168">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="a90ab-168">sip:userName@contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="a90ab-169">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="a90ab-169">sip:userName@contoso.com</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="a90ab-170">Msrtcsip-userenabled true-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="a90ab-170">msRTCSIP-UserEnabled</span></span></p></td>
    <td><p><span data-ttu-id="a90ab-171">Enabled</span><span class="sxs-lookup"><span data-stu-id="a90ab-171">Enabled</span></span></p></td>
    <td><p><span data-ttu-id="a90ab-172">True</span><span class="sxs-lookup"><span data-stu-id="a90ab-172">True</span></span></p></td>
    <td><p><span data-ttu-id="a90ab-173">True</span><span class="sxs-lookup"><span data-stu-id="a90ab-173">True</span></span></p></td>
    </tr>
    </tbody>
    </table>


10. <span data-ttu-id="a90ab-174">移動された各ユーザーは、Lync からログアウトしてから、もう一度ログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a90ab-174">Each user who has been moved will need to log out of Lync, then log back in.</span></span> <span data-ttu-id="a90ab-175">ユーザーは、ログイン時に連絡先リストを確認し、必要に応じて連絡先を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a90ab-175">When they log in they should verify their contact lists, and add contacts if needed.</span></span>
    
    <span data-ttu-id="a90ab-176">スケジュールされた会議は、Lync Online からオンプレミスの Lync に移行されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a90ab-176">Note that scheduled meetings are not migrated from Lync Online to Lync on-premises.</span></span> <span data-ttu-id="a90ab-177">ユーザーは、移動後にこれらの会議をスケジュールし直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="a90ab-177">Users will need to reschedule these meetings after being moved.</span></span>
    
    <span data-ttu-id="a90ab-178">DNS レコードが更新され、すべてのユーザーがオンプレミスに転送されると、HostingProvider 属性によって、Lync ユーザーは SRV レコードを使用するように指示されるか、オンラインのプロバイダー "sipfed.online.lync.com" に転送されます。</span><span class="sxs-lookup"><span data-stu-id="a90ab-178">After the DNS records are updated and all users are directed to On premise, the HostingProvider attribute directs the Lync user to either use SRV records or direct them to the Online provider “sipfed.online.lync.com.”</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

