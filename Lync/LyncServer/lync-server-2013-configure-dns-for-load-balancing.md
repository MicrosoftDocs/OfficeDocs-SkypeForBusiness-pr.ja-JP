---
title: 'Lync Server 2013: 負荷分散のための DNS の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS for load balancing
ms:assetid: 1b2e8414-8676-4872-8ecf-ea07196f74de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398251(v=OCS.15)
ms:contentKeyID: 48183540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 831968516ef155d6ad018f33bfa27226f58292dc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537144"
---
# <a name="configure-dns-for-load-balancing-in-lync-server-2013"></a><span data-ttu-id="8ec93-102">Lync Server 2013 での負荷分散の DNS の構成</span><span class="sxs-lookup"><span data-stu-id="8ec93-102">Configure DNS for load balancing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ec93-103">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="8ec93-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="8ec93-104">この手順を正常に完了するには、最低限でも Domain Admins グループまたは DnsAdmins グループのメンバーとしてサーバーまたはドメインにログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ec93-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="8ec93-105">ドメインネームシステム (DNS) 負荷分散は、SIP トラフィックやメディアトラフィックなど、Lync Server 2013 に固有のネットワークトラフィックのバランスをとります。</span><span class="sxs-lookup"><span data-stu-id="8ec93-105">Domain Name System (DNS) Load Balancing balances the network traffic that is unique to Lync Server 2013, such as SIP traffic and media traffic.</span></span> <span data-ttu-id="8ec93-106">DNS 負荷分散は、フロントエンドプール、エッジプール、ディレクタープール、およびスタンドアロンの仲介プールに対してサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8ec93-106">DNS load balancing is supported for Front End pools, Edge pools, Director pools, and stand-alone Mediation pools.</span></span> <span data-ttu-id="8ec93-107">DNS 負荷分散を使用するように構成されたプールには、次の2つの完全修飾ドメイン名 (Fqdn) が定義されている必要があります。 DNS 負荷分散 (たとえば、pool1.contoso.com) によって使用され、プール内のサーバーの物理 Ip に解決される通常のプールの FQDN、およびプールの Web サービス (たとえば、web1.contoso.net) の別の FQDN がプールの仮想 IP アドレスに解決されます。</span><span class="sxs-lookup"><span data-stu-id="8ec93-107">A pool that is configured to use DNS load balancing must have two fully qualified domain names (FQDNs) defined: the regular pool FQDN that is used by DNS load balancing (for example, pool1.contoso.com) and that resolves to the physical IPs of the servers in the pool, and another FQDN for the pool’s Web Services (for example, web1.contoso.net), which resolves to the virtual IP address of the pool.</span></span> <span data-ttu-id="8ec93-108">DNS 負荷分散の詳細については、「計画」のドキュメントの「 [dns load balancing In Lync Server 2013](lync-server-2013-dns-load-balancing.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ec93-108">For details about DNS Load Balancing, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) in the Planning documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8ec93-109">クライアントからサーバーへの HTTPS トラフィックには、まだハードウェア負荷分散が必要です。</span><span class="sxs-lookup"><span data-stu-id="8ec93-109">Hardware load balancing is still required for client to server HTTPS traffic.</span></span>



</div>

<span data-ttu-id="8ec93-110">DNS 負荷分散を使用する前に、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ec93-110">Before you can use DNS load balancing, you must do the following:</span></span>

1.  <span data-ttu-id="8ec93-111">内部 Web サービスプールの FQDN を上書きします。</span><span class="sxs-lookup"><span data-stu-id="8ec93-111">Override the internal Web Services pool FQDN.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="8ec93-112">内部 web サービスを自己定義の FQDN で上書きする場合、各 FQDN は他のフロントエンドプール、ディレクター、またはディレクタープールとは一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ec93-112">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

2.  <span data-ttu-id="8ec93-113">プールの FQDN をプール内のすべてのサーバーの IP アドレスに解決するための DNS A ホスト レコードの作成</span><span class="sxs-lookup"><span data-stu-id="8ec93-113">Create DNS A host records to resolve the pool FQDN to the IP addresses of all the servers in the pool.</span></span>

3.  <span data-ttu-id="8ec93-114">IP アドレスのランダム化を有効にする (Windows Server の DNS の場合は、ラウンド ロビンを有効にする)</span><span class="sxs-lookup"><span data-stu-id="8ec93-114">Enable IP Address randomization or, for Windows Server DNS, enable round robin.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8ec93-115">ラウンド ロビンは既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="8ec93-115">Round robin should be enabled by default.</span></span>

    
    </div>

<div>

## <a name="to-override-internal-web-services-fqdn"></a><span data-ttu-id="8ec93-116">内部 Web サービスの FQDN をオーバーライドするには</span><span class="sxs-lookup"><span data-stu-id="8ec93-116">To override internal Web services FQDN</span></span>

1.  <span data-ttu-id="8ec93-117">トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ec93-117">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="8ec93-118">コンソール ツリーから、Enterprise Edition のフロントエンド プールのノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="8ec93-118">From the console tree, expand the Enterprise Edition Front End pools node.</span></span>

3.  <span data-ttu-id="8ec93-119">プールを右クリックして [**プロパティの編集**] をクリックし、[**Web サービス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ec93-119">Right-click the pool, click **Edit Properties**, and then click **Web Services**.</span></span>

4.  <span data-ttu-id="8ec93-120">[**内部 Web サービス**] で、[**FQDN のオーバーライド**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="8ec93-120">Below **Internal web services**, select the **Override FQDN** check box.</span></span>

5.  <span data-ttu-id="8ec93-121">プール内のサーバーの物理 IP アドレスへ解決するプールの FQDN を入力します。</span><span class="sxs-lookup"><span data-stu-id="8ec93-121">Type the pool FQDN that resolves to the physical IP addresses of the servers in the pool.</span></span>

6.  <span data-ttu-id="8ec93-122">[**外部 Web サービス**] で、プールの仮想 IP アドレスへ解決する外部プールの FQDN を入力し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ec93-122">Below **External web services**, type the external pool FQDN that resolves to the virtual IP addresses of the pool, and then click **OK**.</span></span>

7.  <span data-ttu-id="8ec93-123">コンソールツリーで [ **Lync Server 2013**] をクリックし、[ **操作** ] ウィンドウで [ **トポロジの公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ec93-123">From the console tree, click **Lync Server 2013**, and then in the **Actions** pane, click **Publish Topology**.</span></span>

</div>

<div>

## <a name="to-create-dns-host-a-records-for-all-internal-pool-servers"></a><span data-ttu-id="8ec93-124">すべての内部プール サーバーの DNS ホスト (A) レコードを作成するには</span><span class="sxs-lookup"><span data-stu-id="8ec93-124">To create DNS Host (A) Records for all internal pool servers</span></span>

1.  <span data-ttu-id="8ec93-125">[**スタート**] をクリックし、[**すべてのプログラム**]、[**管理ツール**] をクリックし、[**DNS**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ec93-125">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="8ec93-126">[**DNS マネージャー**] で、レコードを管理する DNS サーバーをクリックして展開します。</span><span class="sxs-lookup"><span data-stu-id="8ec93-126">In **DNS Manager**, click the DNS Server that manages your records to expand it.</span></span>

3.  <span data-ttu-id="8ec93-127">[**前方参照ゾーン**] をクリックして展開します。</span><span class="sxs-lookup"><span data-stu-id="8ec93-127">Click **Forward Lookup Zones** to expand it.</span></span>

4.  <span data-ttu-id="8ec93-128">レコードの追加が必要な DNS ドメインを右クリックし、[**新しいホスト (A または AAAA)**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ec93-128">Right-click the DNS domain that you need to add records to, and then click **New Host (A or AAAA)**.</span></span>

5.  <span data-ttu-id="8ec93-129">[ **名前** ] ボックスに、ホストレコードの名前を入力します (ドメイン名は自動的に追加されます)。</span><span class="sxs-lookup"><span data-stu-id="8ec93-129">In the **Name** box, type the name of the host record (the domain name will be automatically appended).</span></span>

6.  <span data-ttu-id="8ec93-130">[IP アドレス] ボックスで、個々のフロントエンド サーバーの IP アドレスを入力し、適用可能な場合は [**関連付けられたポインター (PTR) レコードを作成する**] または [**同じ所有者名の DNS レコードの更新を認証されたユーザーに許可する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ec93-130">In the IP Address box, type the IP address of the individual Front End Server and then select **Create associated pointer (PTR) record** or **Allow any authenticated user to update DNS records with the same owner name**, if applicable.</span></span>

7.  <span data-ttu-id="8ec93-131">引き続き、DNS 負荷分散に参加するすべてのメンバー フロントエンド サーバーのレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="8ec93-131">Continue creating records for all member Front End Servers that will participate in DNS Load Balancing.</span></span>
    
    <span data-ttu-id="8ec93-132">たとえば、pool1.contoso.com という名前のプールと 3 台のフロントエンド サーバーがある場合は、次の DNS エントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="8ec93-132">For example, if you had a pool named pool1.contoso.com and three Front End Servers, you would create the following DNS entries:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="8ec93-133">FQDN</span><span class="sxs-lookup"><span data-stu-id="8ec93-133">FQDN</span></span></th>
    <th><span data-ttu-id="8ec93-134">型</span><span class="sxs-lookup"><span data-stu-id="8ec93-134">Type</span></span></th>
    <th><span data-ttu-id="8ec93-135">データ</span><span class="sxs-lookup"><span data-stu-id="8ec93-135">Data</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="8ec93-136">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ec93-136">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="8ec93-137">ホスト (A)</span><span class="sxs-lookup"><span data-stu-id="8ec93-137">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="8ec93-138">192.168.1.1</span><span class="sxs-lookup"><span data-stu-id="8ec93-138">192.168.1.1</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="8ec93-139">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ec93-139">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="8ec93-140">ホスト (A)</span><span class="sxs-lookup"><span data-stu-id="8ec93-140">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="8ec93-141">192.168.1.2</span><span class="sxs-lookup"><span data-stu-id="8ec93-141">192.168.1.2</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="8ec93-142">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ec93-142">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="8ec93-143">ホスト (A)</span><span class="sxs-lookup"><span data-stu-id="8ec93-143">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="8ec93-144">192.168.1.3</span><span class="sxs-lookup"><span data-stu-id="8ec93-144">192.168.1.3</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="8ec93-145">DNS ホスト (A) レコードの作成の詳細については、「 [CONFIGURE Dns host records For Lync Server 2013](lync-server-2013-configure-dns-host-records.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ec93-145">For details about creating DNS Host (A) records, see [Configure DNS Host records for Lync Server 2013](lync-server-2013-configure-dns-host-records.md).</span></span>

</div>

<div>

## <a name="to-enable-round-robin-for-windows-server"></a><span data-ttu-id="8ec93-146">Windows Server のラウンド ロビンを有効にするには</span><span class="sxs-lookup"><span data-stu-id="8ec93-146">To enable round robin for Windows Server</span></span>

1.  <span data-ttu-id="8ec93-147">[**スタート**] をクリックし、[**すべてのプログラム**]、[**管理ツール**] をクリックし、[**DNS**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ec93-147">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="8ec93-148">[**DNS**] を展開し、構成する DNS サーバーを右クリックして、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ec93-148">Expand **DNS**, right-click the DNS server you want to configure, and then click **Properties**.</span></span>

3.  <span data-ttu-id="8ec93-149">[**詳細設定**] タブをクリックし、[**ラウンド ロビンを有効にする**] と [**ネットマスクの順序を有効にする**] を選択して、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ec93-149">Click the **Advanced** tab, select **Enable round robin** and **Enable netmask ordering**, and then click **OK**.</span></span>
    
    <span data-ttu-id="8ec93-150">![DNS ラウンドロビンダイアログボックス](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "DNS ラウンドロビンダイアログボックス")</span><span class="sxs-lookup"><span data-stu-id="8ec93-150">![DNS Round Robin dialog box](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "DNS Round Robin dialog box")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8ec93-151">この機能は既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="8ec93-151">This feature should be enabled by default.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8ec93-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="8ec93-152">See Also</span></span>


[<span data-ttu-id="8ec93-153">Lync Server 2013 での DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="8ec93-153">DNS load balancing in Lync Server 2013</span></span>](lync-server-2013-dns-load-balancing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

