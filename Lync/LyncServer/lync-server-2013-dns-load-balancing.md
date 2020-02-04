---
title: 'Lync Server 2013: DNS の負荷分散'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS load balancing
ms:assetid: 7ed0ed20-33ad-4253-926d-21d392590ae7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398634(v=OCS.15)
ms:contentKeyID: 48184625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30d3b88ac66ad7dc6dd3216d941f4a99fc2feedd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-load-balancing-in-lync-server-2013"></a><span data-ttu-id="9dc31-102">Lync Server 2013 での DNS の負荷分散</span><span class="sxs-lookup"><span data-stu-id="9dc31-102">DNS load balancing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9dc31-103">_**最終更新日:** 2014-01-15_</span><span class="sxs-lookup"><span data-stu-id="9dc31-103">_**Topic Last Modified:** 2014-01-15_</span></span>

<span data-ttu-id="9dc31-104">Lync Server を使用すると、DNS の負荷分散が有効になり、ネットワークでの負荷分散の管理オーバーヘッドが大幅に削減されます。</span><span class="sxs-lookup"><span data-stu-id="9dc31-104">Lync Server enables DNS load balancing, a software solution that can greatly reduce the administration overhead for load balancing on your network.</span></span> <span data-ttu-id="9dc31-105">DNS ロードバランシングは、SIP トラフィックやメディアトラフィックなど、Lync Server に固有のネットワークトラフィックのバランスを行います。</span><span class="sxs-lookup"><span data-stu-id="9dc31-105">DNS load balancing balances the network traffic that is unique to Lync Server, such as SIP traffic and media traffic.</span></span>

<span data-ttu-id="9dc31-106">DNS の負荷分散を展開すると、組織のハードウェアロードバランサーの管理オーバーヘッドが最小化されます。</span><span class="sxs-lookup"><span data-stu-id="9dc31-106">If you deploy DNS load balancing, your organization’s administration overhead for hardware load balancers will be minimized.</span></span> <span data-ttu-id="9dc31-107">さらに、SIP トラフィックのロードバランサーの誤りに関連する問題の複雑なトラブルシューティングも行われなくなります。</span><span class="sxs-lookup"><span data-stu-id="9dc31-107">Additionally, complex troubleshooting of problems related to misconfiguration of load balancers for SIP traffic will be eliminated.</span></span> <span data-ttu-id="9dc31-108">サーバー接続を禁止して、サーバーをオフラインにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9dc31-108">You can also prevent server connections so that you can take servers offline.</span></span> <span data-ttu-id="9dc31-109">また、DNS の負荷分散により、ハードウェアロードバランサーの問題が、基本的な通話ルーティングなどの SIP トラフィックの要素に影響を与えることはありません。</span><span class="sxs-lookup"><span data-stu-id="9dc31-109">DNS load balancing also ensures that hardware load balancer problems do not affect elements of SIP traffic such as basic call routing.</span></span>

<span data-ttu-id="9dc31-110">DNS 負荷分散を使用している場合は、すべての種類のトラフィックにハードウェアロードバランサーを使用した場合よりも低コストのハードウェアロードバランサーを購入できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9dc31-110">If you use DNS load balancing, you may also be able to purchase lower-cost hardware load balancers than if you used the hardware load balancers for all types of traffic.</span></span> <span data-ttu-id="9dc31-111">ロードバランサーを使用して、Lync Server で相互運用性の認定テストに合格している必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dc31-111">You should use load balancers that have passed interoperability qualification testing with Lync Server.</span></span> <span data-ttu-id="9dc31-112">ロードバランサーの相互運用性テストの詳細については、の「Lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452)ロードバランサーパートナー」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dc31-112">For details about load balancer interoperability testing, see "Lync Server 2010 Load Balancer Partners" at [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452).</span></span>

<span data-ttu-id="9dc31-113">DNS の負荷分散は、フロントエンドプール、エッジサーバープール、ディレクタープール、スタンドアロンの仲介サーバープールでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9dc31-113">DNS load balancing is supported for Front End pools, Edge Server pools, Director pools, and stand-alone Mediation Server pools.</span></span>

<div>

## <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="9dc31-114">フロントエンドプールとディレクタープールの DNS ロードバランシング</span><span class="sxs-lookup"><span data-stu-id="9dc31-114">DNS Load Balancing on Front End Pools and Director Pools</span></span>

<span data-ttu-id="9dc31-115">フロントエンドプールおよびディレクタープールの SIP トラフィックには、DNS の負荷分散を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9dc31-115">You can use DNS load balancing for the SIP traffic on Front End pools and Director pools.</span></span> <span data-ttu-id="9dc31-116">DNS ロードバランシングが展開されている場合でも、これらのプールにはハードウェアロードバランサーを使用する必要があります。ただし、クライアントとサーバーの HTTPS トラフィックに対してのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="9dc31-116">With DNS load balancing deployed, you still need to also use hardware load balancers for these pools, but only for client-to-server HTTPS traffic.</span></span> <span data-ttu-id="9dc31-117">ハードウェアロードバランサーは、ポート443および80経由のクライアントからの HTTPS トラフィックに使用されます。</span><span class="sxs-lookup"><span data-stu-id="9dc31-117">The hardware load balancer is used for HTTPS traffic from clients over ports 443 and 80.</span></span>

<span data-ttu-id="9dc31-118">ただし、これらのプールについては、ハードウェアロードバランサーが必要ですが、これらのセットアップと管理は主に HTTPS トラフィック用であり、ハードウェアロードバランサーの管理者は使い慣れています。</span><span class="sxs-lookup"><span data-stu-id="9dc31-118">Although you still need hardware load balancers for these pools, their setup and administration will be primarily for HTTPS traffic, which the administrators of hardware load balancers are accustomed to.</span></span>

<div>

## <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a><span data-ttu-id="9dc31-119">DNS の負荷分散と、古いクライアントとサーバーのサポート</span><span class="sxs-lookup"><span data-stu-id="9dc31-119">DNS Load Balancing and Supporting Older Clients and Servers</span></span>

<span data-ttu-id="9dc31-120">DNS の負荷分散は、Lync Server 2013 または Lync Server 2010、および Lync 2013 および Lync 2010 クライアントを実行しているサーバーに対してのみ、自動フェールオーバーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="9dc31-120">DNS load balancing supports automatic failover only for servers running Lync Server 2013 or Lync Server 2010, and for Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="9dc31-121">以前のバージョンのクライアントと Office Communications Server でも、DNS 負荷分散を実行しているプールに接続できますが、DNS ロードバランシングで参照される最初のサーバーに接続できない場合は、プール内の別のサーバーにフェールオーバーすることはできません。.</span><span class="sxs-lookup"><span data-stu-id="9dc31-121">Earlier versions of clients and Office Communications Server can still connect to pools running DNS load balancing, but if they cannot make a connection to the first server that DNS load balancing refers them to, they are unable to fail over to another server in the pool.</span></span>

<span data-ttu-id="9dc31-122">さらに、Exchange UM を使用している場合は、少なくとも Exchange 2010 SP1 を使用して、Lync Server DNS の負荷分散のサポートを受ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dc31-122">Additionally, if you are using Exchange UM, you must use a minimum of Exchange 2010 SP1 to get support for Lync Server DNS load balancing.</span></span> <span data-ttu-id="9dc31-123">以前のバージョンの Exchange を使用している場合、ユーザーには次の Exchange UM シナリオのフェールオーバー機能はありません。</span><span class="sxs-lookup"><span data-stu-id="9dc31-123">If you use an earlier version of Exchange, your users will not have failover capabilities for these Exchange UM scenarios:</span></span>

  - <span data-ttu-id="9dc31-124">スマートフォンでのエンタープライズボイスボイスメールの再生</span><span class="sxs-lookup"><span data-stu-id="9dc31-124">Playing their Enterprise Voice voice mail on their phone</span></span>

  - <span data-ttu-id="9dc31-125">Exchange UM 自動応答からの着信の転送</span><span class="sxs-lookup"><span data-stu-id="9dc31-125">Transferring calls from an Exchange UM Auto Attendant</span></span>

<span data-ttu-id="9dc31-126">その他のすべての Exchange UM シナリオは適切に動作します。</span><span class="sxs-lookup"><span data-stu-id="9dc31-126">All other Exchange UM scenarios will work properly.</span></span>

</div>

<div>

## <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="9dc31-127">フロントエンドプールとディレクタープールで DNS の負荷分散を展開する</span><span class="sxs-lookup"><span data-stu-id="9dc31-127">Deploying DNS Load Balancing on Front End Pools and Director Pools</span></span>

<span data-ttu-id="9dc31-128">フロントエンドプールとディレクタープールで DNS の負荷分散を展開するには、Fqdn と DNS レコードでいくつかの追加の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dc31-128">Deploying DNS load balancing on Front End pools and Director pools requires you to perform a couple of extra steps with FQDNs and DNS records.</span></span>

  - <span data-ttu-id="9dc31-129">DNS 負荷分散を使用するプールには、DNS 負荷分散によって使用される標準プール FQDN (pool01.contoso.com など) と、プール内のサーバーの物理 Ip アドレス、さらにプールの Web サービス用の別の FQDN が含まれている必要があります。web01.contoso.com)。プールの仮想 IP アドレスに解決されます。</span><span class="sxs-lookup"><span data-stu-id="9dc31-129">A pool that uses DNS load balancing must have two FQDNs: the regular pool FQDN that is used by DNS load balancing (such as pool01.contoso.com), and resolves to the physical IPs of the servers in the pool, and another FQDN for the pool’s Web services (such as web01.contoso.com), which resolves to virtual IP address of the pool.</span></span>
    
    <span data-ttu-id="9dc31-130">トポロジビルダーでプールの負荷分散を展開する場合は、プールの Web サービスの追加 FQDN を作成するには、[**内部 Web サービスプールの fqdn を上書き**する] チェックボックスをオンにして、[**このプールの Web サービス url を指定**してください] ページで fqdn を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dc31-130">In Topology Builder, if you want to deploy DNS load balancing for a pool, to create this extra FQDN for the pool’s Web services you must select the **Override internal Web Services pool FQDN** check box and type the FQDN, in the **Specify the Web Services URLs for this Pool** page.</span></span>

  - <span data-ttu-id="9dc31-131">DNS の負荷分散で使用される FQDN をサポートするには、DNS をプロビジョニングしてプールの FQDN (pool01.contoso.com など) を、プール内のすべてのサーバーの IP アドレス (たとえば、192.168.1.1、192.168.1.2 など) に解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dc31-131">To support the FQDN used by DNS load balancing, you must provision DNS to resolve the pool FQDN (such as pool01.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on).</span></span> <span data-ttu-id="9dc31-132">現在展開されているサーバーの IP アドレスのみを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dc31-132">You should include only the IP addresses of servers that are currently deployed.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="9dc31-133">複数のフロントエンドプールまたはフロントエンドサーバーがある場合は、外部 Web サービスの FQDN が一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dc31-133">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="9dc31-134">たとえば、フロントエンドサーバーの外部 Web サービス FQDN を<STRONG>pool01.contoso.com</STRONG>として定義する場合、別のフロントエンドプールまたはフロントエンドサーバーに対して<STRONG>pool01.contoso.com</STRONG>を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="9dc31-134">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="9dc31-135">ディレクターも展開する場合、任意のディレクターまたはディレクタープール用に定義された外部 Web サービスの FQDN は、他のすべてのディレクターまたはディレクタープールと、フロントエンドプールまたはフロントエンドサーバーから一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dc31-135">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="9dc31-136">自己定義の FQDN を使用して内部 web サービスを上書きする場合、各 FQDN は、他のフロントエンドプール、ディレクター、またはディレクタープールから一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dc31-136">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

</div>

</div>

<div>

## <a name="dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="9dc31-137">エッジサーバープールでの DNS の負荷分散</span><span class="sxs-lookup"><span data-stu-id="9dc31-137">DNS Load Balancing on Edge Server Pools</span></span>

<span data-ttu-id="9dc31-138">エッジサーバープールで DNS の負荷分散を展開できます。</span><span class="sxs-lookup"><span data-stu-id="9dc31-138">You can deploy DNS load balancing on Edge Server pools.</span></span> <span data-ttu-id="9dc31-139">その場合は、いくつかの考慮事項に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dc31-139">If you do, you must be aware of some considerations.</span></span>

<span data-ttu-id="9dc31-140">エッジサーバーで DNS の負荷分散を使用すると、次のシナリオでフェールオーバー機能が失われます。</span><span class="sxs-lookup"><span data-stu-id="9dc31-140">Using DNS load balancing on your Edge Servers causes a loss of failover ability in the following scenarios:</span></span>

  - <span data-ttu-id="9dc31-141">Lync Server 2010 より前にリリースされたバージョンの Office Communications Server を実行している組織とのフェデレーション。</span><span class="sxs-lookup"><span data-stu-id="9dc31-141">Federation with organizations that are running versions of Office Communications Server released prior to Lync Server 2010.</span></span>

  - <span data-ttu-id="9dc31-142">パブリックインスタントメッセージング (IM) サービス AOLand Yahoo\!のユーザーとのインスタントメッセージ交換 (Google Talk などの xmpp ベースのプロバイダーとサーバー)。</span><span class="sxs-lookup"><span data-stu-id="9dc31-142">Instant message exchange with users of public instant messaging (IM) services AOLand Yahoo\!, in addition to XMPP-based providers and servers, such as Google Talk.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="9dc31-143">Google Talk は現在サポートされている XMPP パートナーのみです。</span><span class="sxs-lookup"><span data-stu-id="9dc31-143">Google Talk is currently the only supported XMPP partner.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="9dc31-144">2012年9月1日以降、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規または更新契約の購入に使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="9dc31-144">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="9dc31-145">アクティブなライセンスを持っているお客様は、Yahoo! とのフェデレーションを継続できます。</span><span class="sxs-lookup"><span data-stu-id="9dc31-145">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="9dc31-146">サービスが終了するまでの Messenger。</span><span class="sxs-lookup"><span data-stu-id="9dc31-146">Messenger until the service shut down date.</span></span> <span data-ttu-id="9dc31-147">AOL および Yahoo! の2014年6月の終了日</span><span class="sxs-lookup"><span data-stu-id="9dc31-147">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="9dc31-148">が発表されました。</span><span class="sxs-lookup"><span data-stu-id="9dc31-148">has been announced.</span></span> <span data-ttu-id="9dc31-149">詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dc31-149">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P></LI></UL>

    
    </div>

<span data-ttu-id="9dc31-150">これらのシナリオは、プール内のすべてのエッジサーバーが稼働していても動作しますが、1つのエッジサーバーが利用できない場合は、他のエッジサーバーにルーティングする代わりに、これらのシナリオに対する要求はすべて失敗します。</span><span class="sxs-lookup"><span data-stu-id="9dc31-150">These scenarios will work as long as all Edge Servers in the pool are up and running, but if one Edge Server is unavailable, any requests for these scenarios that are sent to it will fail, instead of routing to another Edge Server.</span></span>

<span data-ttu-id="9dc31-151">Exchange UM を使用している場合は、少なくとも Exchange 2013 を使用して、microsoft Lync Server DNS の負荷分散を Edge でサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dc31-151">If you are using Exchange UM, you must use a minimum of Exchange 2013 to get support for Lync Server DNS load balancing on Edge.</span></span> <span data-ttu-id="9dc31-152">以前のバージョンの Exchange を使用している場合、リモートユーザーには次の Exchange UM シナリオのフェールオーバー機能はありません。</span><span class="sxs-lookup"><span data-stu-id="9dc31-152">If you use an earlier version of Exchange, your remote users will not have failover capabilities for these Exchange UM scenarios:</span></span>

  - <span data-ttu-id="9dc31-153">スマートフォンでのエンタープライズボイスボイスメールの再生</span><span class="sxs-lookup"><span data-stu-id="9dc31-153">Playing their Enterprise Voice voice mail on their phone</span></span>

  - <span data-ttu-id="9dc31-154">Exchange UM 自動応答からの着信の転送</span><span class="sxs-lookup"><span data-stu-id="9dc31-154">Transferring calls from an Exchange UM Auto Attendant</span></span>

<span data-ttu-id="9dc31-155">その他のすべての Exchange UM シナリオは適切に動作します。</span><span class="sxs-lookup"><span data-stu-id="9dc31-155">All other Exchange UM scenarios will work properly.</span></span>

<span data-ttu-id="9dc31-156">内部エッジ インターフェイスと外部エッジ インターフェイスでは、同じ種類のロード バランシングを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dc31-156">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="9dc31-157">1 つのエッジ インターフェイスで DNS ロード バランシングを使用し、もう 1 つのエッジ インターフェイスでロード バランサー機器を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="9dc31-157">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>

<div>

## <a name="deploying-dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="9dc31-158">エッジサーバープールへの DNS 負荷分散の展開</span><span class="sxs-lookup"><span data-stu-id="9dc31-158">Deploying DNS Load Balancing on Edge Server Pools</span></span>

<span data-ttu-id="9dc31-159">エッジサーバープールの外部インターフェイスに DNS の負荷分散を展開するには、次の DNS エントリが必要です。</span><span class="sxs-lookup"><span data-stu-id="9dc31-159">To deploy DNS load balancing on the external interface of your Edge Server pool, you need the following DNS entries:</span></span>

  - <span data-ttu-id="9dc31-160">アクセスエッジサービスの場合、プール内の各サーバーに1つのエントリが必要です。</span><span class="sxs-lookup"><span data-stu-id="9dc31-160">For the Access Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="9dc31-161">各エントリは、アクセスエッジサービスの FQDN (sip.contoso.com など) を、プール内のいずれかのエッジサーバー上のアクセスエッジサービスの IP アドレスに解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dc31-161">Each entry must resolve the FQDN of the Access Edge service (for example, sip.contoso.com) to the IP address of the Access Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="9dc31-162">Web 会議エッジサービスの場合、プール内の各サーバーに1つのエントリが必要です。</span><span class="sxs-lookup"><span data-stu-id="9dc31-162">For the Web Conferencing Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="9dc31-163">各エントリは、Web 会議エッジサービスの FQDN (webconf.contoso.com など) を、プール内のいずれかのエッジサーバー上の Web 会議エッジサービスの IP アドレスに解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dc31-163">Each entry must resolve the FQDN of the Web Conferencing Edge service (for example, webconf.contoso.com) to the IP address of the Web Conferencing Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="9dc31-164">オーディオ/ビデオエッジサービスの場合、プール内の各サーバーに1つのエントリが必要です。</span><span class="sxs-lookup"><span data-stu-id="9dc31-164">For the Audio/Video Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="9dc31-165">各エントリは、オーディオ/ビデオエッジサービス (たとえば、av.contoso.com) の FQDN を、プール内のいずれかのエッジサーバー上の A/V Edge サービスの IP アドレスに解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dc31-165">Each entry must resolve the FQDN of the Audio/Video Edge service (for example, av.contoso.com) to the IP address of the A/V Edge service on one of the Edge Servers in the pool.</span></span>

<span data-ttu-id="9dc31-166">エッジサーバープールの内部インターフェイスで DNS の負荷分散を展開するには、1つの DNS A レコードを追加する必要があります。これにより、エッジサーバープールの内部 FQDN がプール内の各サーバーの IP アドレスに解決されます。</span><span class="sxs-lookup"><span data-stu-id="9dc31-166">To deploy DNS load balancing on the internal interface of your Edge Server pool, you must add one DNS A record, which resolves the internal FQDN of the Edge Server pool to the IP address of each server in the pool.</span></span>

</div>

</div>

<div>

## <a name="using-dns-load-balancing-on-mediation-server-pools"></a><span data-ttu-id="9dc31-167">仲介サーバープールでの DNS ロードバランシングの使用</span><span class="sxs-lookup"><span data-stu-id="9dc31-167">Using DNS Load Balancing on Mediation Server Pools</span></span>

<span data-ttu-id="9dc31-168">DNS の負荷分散は、スタンドアロンの仲介サーバープールで使うことができます。</span><span class="sxs-lookup"><span data-stu-id="9dc31-168">You can use DNS load balancing on stand-alone Mediation Server pools.</span></span> <span data-ttu-id="9dc31-169">SIP とメディアのトラフィックはすべて DNS の負荷分散によって均等化されます。</span><span class="sxs-lookup"><span data-stu-id="9dc31-169">All SIP and media traffic is balanced by DNS load balancing.</span></span>

<span data-ttu-id="9dc31-170">DNS 負荷分散を仲介サーバープールに展開するには、DNS をプロビジョニングしてプールの FQDN (たとえば、mediationpool1.contoso.com) を、プール内のすべてのサーバーの IP アドレス (たとえば、192.168.1.1、192.168.1.2 など) に解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dc31-170">To deploy DNS load balancing on a Mediation Server pool, you must provision DNS to resolve the pool FQDN (for example, mediationpool1.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on).</span></span>

</div>

<div>

## <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a><span data-ttu-id="9dc31-171">DNS 負荷分散を使用してサーバーへのトラフィックをブロックする</span><span class="sxs-lookup"><span data-stu-id="9dc31-171">Blocking Traffic to a Server With DNS Load Balancing</span></span>

<span data-ttu-id="9dc31-p117">DNS 負荷分散を使用していて、特定のコンピューターへのトラフィックを遮断する必要がある場合は、プールの FQDN から IP アドレス エントリを削除するだけでは十分ではありません。コンピューターの DNS エントリも削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dc31-p117">If you use DNS load balancing and you need to block traffic to a specific computer, it is not sufficient to just remove the IP address entries from the Pool FQDN. You must remove the DNS entry for the computer as well.</span></span>

<span data-ttu-id="9dc31-174">サーバー間のトラフィックについては、Lync Server 2013 はトポロジに対応した負荷分散を使用していることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9dc31-174">Note that for server-to-server traffic, Lync Server 2013 uses topology-aware load balancing.</span></span> <span data-ttu-id="9dc31-175">サーバーは、中央管理ストアで公開されているトポロジを読み取り、トポロジ内のサーバーの Fqdn を取得し、サーバー間でトラフィックを自動的に分散します。</span><span class="sxs-lookup"><span data-stu-id="9dc31-175">Servers read the published topology in the Central Management store to obtain the FQDNs of servers in the topology, and automatically distribute the traffic among the servers.</span></span> <span data-ttu-id="9dc31-176">サーバーがサーバー間トラフィックを受信することをブロックするには、トポロジからサーバーを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dc31-176">To block a server from receiving server-to-server traffic, you must remove the server from the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

