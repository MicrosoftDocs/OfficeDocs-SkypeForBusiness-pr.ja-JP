---
title: 'Lync Server 2013: DNS 負荷分散'
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
ms.openlocfilehash: 79c2bb8e5bbcb9d00fe687d6f06ac6226a2edf6e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528924"
---
# <a name="dns-load-balancing-in-lync-server-2013"></a><span data-ttu-id="27559-102">Lync Server 2013 での DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="27559-102">DNS load balancing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27559-103">_**トピックの最終更新日:** 2014-01-15_</span><span class="sxs-lookup"><span data-stu-id="27559-103">_**Topic Last Modified:** 2014-01-15_</span></span>

<span data-ttu-id="27559-104">Lync Server は、DNS 負荷分散を有効にします。これにより、ネットワーク上の負荷分散の管理オーバーヘッドを大幅に削減できます。</span><span class="sxs-lookup"><span data-stu-id="27559-104">Lync Server enables DNS load balancing, a software solution that can greatly reduce the administration overhead for load balancing on your network.</span></span> <span data-ttu-id="27559-105">DNS 負荷分散は、SIP トラフィックやメディアトラフィックなど、Lync Server に固有のネットワークトラフィックのバランスをとります。</span><span class="sxs-lookup"><span data-stu-id="27559-105">DNS load balancing balances the network traffic that is unique to Lync Server, such as SIP traffic and media traffic.</span></span>

<span data-ttu-id="27559-106">DNS 負荷分散を展開すると、ハードウェアロードバランサーの管理オーバーヘッドが最小限に抑えられます。</span><span class="sxs-lookup"><span data-stu-id="27559-106">If you deploy DNS load balancing, your organization’s administration overhead for hardware load balancers will be minimized.</span></span> <span data-ttu-id="27559-107">さらに、SIP トラフィックの負荷分散装置の構成ミスに関する問題に対応するために、複雑なトラブルシューティングを行う必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="27559-107">Additionally, complex troubleshooting of problems related to misconfiguration of load balancers for SIP traffic will be eliminated.</span></span> <span data-ttu-id="27559-108">サーバーをオフラインにできるようにサーバー接続を禁止することもできます。</span><span class="sxs-lookup"><span data-stu-id="27559-108">You can also prevent server connections so that you can take servers offline.</span></span> <span data-ttu-id="27559-109">また、DNS 負荷分散を使用して、ハードウェア ロード バランサーの問題が基本的な通話のルーティングなどの SIP トラフィックの要素に影響しないようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="27559-109">DNS load balancing also ensures that hardware load balancer problems do not affect elements of SIP traffic such as basic call routing.</span></span>

<span data-ttu-id="27559-110">また、DNS 負荷分散を使用すると、すべての種類のトラフィックに対応するハードウェア ロード バランサーを使用していた場合よりもハードウェア ロード バランサーを低価格で購入できます。</span><span class="sxs-lookup"><span data-stu-id="27559-110">If you use DNS load balancing, you may also be able to purchase lower-cost hardware load balancers than if you used the hardware load balancers for all types of traffic.</span></span> <span data-ttu-id="27559-111">Lync Server との相互運用性認定テストに合格したロードバランサーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27559-111">You should use load balancers that have passed interoperability qualification testing with Lync Server.</span></span> <span data-ttu-id="27559-112">ロードバランサー相互運用性テストの詳細については、「」の「Lync Server 2010 ロードバランサーパートナー」を参照してください [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452) 。</span><span class="sxs-lookup"><span data-stu-id="27559-112">For details about load balancer interoperability testing, see "Lync Server 2010 Load Balancer Partners" at [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452).</span></span>

<span data-ttu-id="27559-113">DNS 負荷分散は、フロント エンド プール、エッジ サーバー プール、ディレクター プール、およびスタンドアロンの仲介サーバー プールでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="27559-113">DNS load balancing is supported for Front End pools, Edge Server pools, Director pools, and stand-alone Mediation Server pools.</span></span>

<div>

## <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="27559-114">フロント エンド プールとディレクター プールの DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="27559-114">DNS Load Balancing on Front End Pools and Director Pools</span></span>

<span data-ttu-id="27559-p104">フロント エンド プールとディレクター プールの SIP トラフィックに DNS 負荷分散を使用できます。 DNS 負荷分散を展開している場合でも、クライアントとサーバー間の HTTPS トラフィックに対してのみ、これらのプールに引き続きハードウェア ロード バランサーを使用する必要があります。 ハードウェア ロード バランサーは、ポート 443 とポート 80 経由のクライアントからの HTTPS トラフィックに対して使用します。</span><span class="sxs-lookup"><span data-stu-id="27559-p104">You can use DNS load balancing for the SIP traffic on Front End pools and Director pools. With DNS load balancing deployed, you still need to also use hardware load balancers for these pools, but only for client-to-server HTTPS traffic. The hardware load balancer is used for HTTPS traffic from clients over ports 443 and 80.</span></span>

<span data-ttu-id="27559-118">これらのプール用のハードウェア ロード バランサーは引き続き必要ですが、そのセットアップと管理は主に HTTP トラフィックに対するものであり、ハードウェア ロード バランサーの管理者にはなじみのあるものです。</span><span class="sxs-lookup"><span data-stu-id="27559-118">Although you still need hardware load balancers for these pools, their setup and administration will be primarily for HTTPS traffic, which the administrators of hardware load balancers are accustomed to.</span></span>

<div>

## <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a><span data-ttu-id="27559-119">DNS 負荷分散およびサポートされる以前のクライアントとサーバー</span><span class="sxs-lookup"><span data-stu-id="27559-119">DNS Load Balancing and Supporting Older Clients and Servers</span></span>

<span data-ttu-id="27559-120">DNS 負荷分散は、Lync Server 2013 または Lync Server 2010 を実行しているサーバー、および Lync 2013 および Lync 2010 クライアントに対してのみ、自動フェールオーバーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="27559-120">DNS load balancing supports automatic failover only for servers running Lync Server 2013 or Lync Server 2010, and for Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="27559-121">以前のバージョンのクライアントおよび Office Communications Server は、DNS 負荷分散を実行しているプールに接続できますが、DNS 負荷分散が参照する最初のサーバーに接続できない場合、プール内の別のサーバーにフェールオーバーすることはできません。</span><span class="sxs-lookup"><span data-stu-id="27559-121">Earlier versions of clients and Office Communications Server can still connect to pools running DNS load balancing, but if they cannot make a connection to the first server that DNS load balancing refers them to, they are unable to fail over to another server in the pool.</span></span>

<span data-ttu-id="27559-122">また、Exchange UM を使用している場合は、少なくとも Exchange 2010 SP1 を使用して Lync Server DNS 負荷分散のサポートを受ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="27559-122">Additionally, if you are using Exchange UM, you must use a minimum of Exchange 2010 SP1 to get support for Lync Server DNS load balancing.</span></span> <span data-ttu-id="27559-123">以前のバージョンの Exchange を使用している場合、次の Exchange UM シナリオでは、ユーザーはフェールオーバー機能を利用できません。</span><span class="sxs-lookup"><span data-stu-id="27559-123">If you use an earlier version of Exchange, your users will not have failover capabilities for these Exchange UM scenarios:</span></span>

  - <span data-ttu-id="27559-124">電話でエンタープライズ VoIP ボイス メールを再生する</span><span class="sxs-lookup"><span data-stu-id="27559-124">Playing their Enterprise Voice voice mail on their phone</span></span>

  - <span data-ttu-id="27559-125">Exchange UM 自動応答から通話を転送する</span><span class="sxs-lookup"><span data-stu-id="27559-125">Transferring calls from an Exchange UM Auto Attendant</span></span>

<span data-ttu-id="27559-126">他のすべての Exchange UM シナリオでは効果があります。</span><span class="sxs-lookup"><span data-stu-id="27559-126">All other Exchange UM scenarios will work properly.</span></span>

</div>

<div>

## <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="27559-127">フロント エンド プールとディレクター プールへの DNS 負荷分散の展開</span><span class="sxs-lookup"><span data-stu-id="27559-127">Deploying DNS Load Balancing on Front End Pools and Director Pools</span></span>

<span data-ttu-id="27559-128">フロント エンド プールとディレクター プールに DNS 負荷分散を展開するには、FQDN と DNS レコードでいくつか追加の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27559-128">Deploying DNS load balancing on Front End pools and Director pools requires you to perform a couple of extra steps with FQDNs and DNS records.</span></span>

  - <span data-ttu-id="27559-129">DNS 負荷分散を使用するプールに、次の 2 つの FQDN がある必要があります。まず、DNS 負荷分散で使用される通常のプールの FQDN (pool01.contoso.com など) で、プール内のサーバーの物理 IP に解決されます。次に、プールの Web サービスの別の FQDN (web01.contoso.com など) で、プールの仮想 IP アドレスに解決されます。</span><span class="sxs-lookup"><span data-stu-id="27559-129">A pool that uses DNS load balancing must have two FQDNs: the regular pool FQDN that is used by DNS load balancing (such as pool01.contoso.com), and resolves to the physical IPs of the servers in the pool, and another FQDN for the pool’s Web services (such as web01.contoso.com), which resolves to virtual IP address of the pool.</span></span>
    
    <span data-ttu-id="27559-130">トポロジビルダーで、プールの DNS 負荷分散を展開する場合は、プールの Web サービス用の追加の FQDN を作成するには、[ **内部 Web サービスプールの fqdn を上書き** する] チェックボックスをオンにして、[ **このプールの Web サービス url を指定** します] ページで FQDN を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27559-130">In Topology Builder, if you want to deploy DNS load balancing for a pool, to create this extra FQDN for the pool’s Web services you must select the **Override internal Web Services pool FQDN** check box and type the FQDN, in the **Specify the Web Services URLs for this Pool** page.</span></span>

  - <span data-ttu-id="27559-p107">DNS 負荷分散で使用される FQDN をサポートするには、プールの FQDN (pool01.contoso.com など) をプール内のすべてのサーバーの IP アドレス (192.168.1.1、192.168.1.2 など) に解決するように DNS をプロビジョニングする必要があります。現在展開されているサーバーの IP アドレスのみ含めるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="27559-p107">To support the FQDN used by DNS load balancing, you must provision DNS to resolve the pool FQDN (such as pool01.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on). You should include only the IP addresses of servers that are currently deployed.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="27559-133">フロントエンドプールまたはフロントエンドサーバーが複数ある場合は、外部 Web サービスの FQDN が一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="27559-133">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="27559-134">たとえば、フロントエンドサーバーの外部 Web サービスの FQDN を <STRONG>pool01.contoso.com</STRONG>として定義した場合、別のフロントエンドプールまたはフロントエンドサーバーに <STRONG>pool01.contoso.com</STRONG> を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="27559-134">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="27559-135">ディレクターを展開している場合は、ディレクターまたはディレクタープールに対して定義されている外部 Web サービスの FQDN が、他のすべてのディレクターまたはディレクタープールと、フロントエンドプールまたはフロントエンドサーバーとも一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="27559-135">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="27559-136">内部 web サービスを自己定義の FQDN で上書きする場合、各 FQDN は他のフロントエンドプール、ディレクター、またはディレクタープールとは一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="27559-136">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

</div>

</div>

<div>

## <a name="dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="27559-137">エッジ サーバー プールの DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="27559-137">DNS Load Balancing on Edge Server Pools</span></span>

<span data-ttu-id="27559-p109">エッジ サーバー プールに DNS 負荷分散を展開できます。 その場合、いくつかの考慮事項に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27559-p109">You can deploy DNS load balancing on Edge Server pools. If you do, you must be aware of some considerations.</span></span>

<span data-ttu-id="27559-140">エッジ サーバーで DNS 負荷分散を使用する場合、次のシナリオではフェールオーバー機能を利用できません。</span><span class="sxs-lookup"><span data-stu-id="27559-140">Using DNS load balancing on your Edge Servers causes a loss of failover ability in the following scenarios:</span></span>

  - <span data-ttu-id="27559-141">Lync Server 2010 より前にリリースされたバージョンの Office Communications Server を実行している組織とのフェデレーション。</span><span class="sxs-lookup"><span data-stu-id="27559-141">Federation with organizations that are running versions of Office Communications Server released prior to Lync Server 2010.</span></span>

  - <span data-ttu-id="27559-142">パブリックインスタントメッセージング (IM) サービス AOLand Yahoo のユーザーとのインスタントメッセージ交換 ( \! Google Talk などの XMPP ベースのプロバイダーおよびサーバーに加えて)。</span><span class="sxs-lookup"><span data-stu-id="27559-142">Instant message exchange with users of public instant messaging (IM) services AOLand Yahoo\!, in addition to XMPP-based providers and servers, such as Google Talk.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="27559-143">現時点では、Google Talk はサポートされている唯一の XMPP パートナーです。</span><span class="sxs-lookup"><span data-stu-id="27559-143">Google Talk is currently the only supported XMPP partner.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="27559-144">2012年9月1日時点で、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規購入時または契約の更新時に購入することができなくなりました。</span><span class="sxs-lookup"><span data-stu-id="27559-144">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="27559-145">アクティブなライセンスを持つお客様は、Yahoo! とのフェデレーションを続行できます。</span><span class="sxs-lookup"><span data-stu-id="27559-145">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="27559-146">メッセンジャーサービスが終了するまでの期間。</span><span class="sxs-lookup"><span data-stu-id="27559-146">Messenger until the service shut down date.</span></span> <span data-ttu-id="27559-147">AOL および Yahoo! の2014年6月の寿命の終了日</span><span class="sxs-lookup"><span data-stu-id="27559-147">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="27559-148">が発表されました。</span><span class="sxs-lookup"><span data-stu-id="27559-148">has been announced.</span></span> <span data-ttu-id="27559-149">詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27559-149">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P></LI></UL>

    
    </div>

<span data-ttu-id="27559-150">これらのシナリオは、プール内のすべてのエッジ サーバーが実行されている限り有効ですが、いずれかのエッジ サーバーが利用できなくなると、これらのシナリオでそのエッジ サーバーに送信されるすべての要求は、別のエッジ サーバーにルーティングされずに失敗します。</span><span class="sxs-lookup"><span data-stu-id="27559-150">These scenarios will work as long as all Edge Servers in the pool are up and running, but if one Edge Server is unavailable, any requests for these scenarios that are sent to it will fail, instead of routing to another Edge Server.</span></span>

<span data-ttu-id="27559-151">Exchange UM を使用している場合は、少なくとも Exchange 2013 を使用して、エッジで Lync Server DNS 負荷分散のサポートを受ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="27559-151">If you are using Exchange UM, you must use a minimum of Exchange 2013 to get support for Lync Server DNS load balancing on Edge.</span></span> <span data-ttu-id="27559-152">以前のバージョンの Exchange を使用している場合、リモートユーザーは、これらの Exchange UM シナリオではフェールオーバー機能を利用できません。</span><span class="sxs-lookup"><span data-stu-id="27559-152">If you use an earlier version of Exchange, your remote users will not have failover capabilities for these Exchange UM scenarios:</span></span>

  - <span data-ttu-id="27559-153">電話でエンタープライズ VoIP ボイス メールを再生する</span><span class="sxs-lookup"><span data-stu-id="27559-153">Playing their Enterprise Voice voice mail on their phone</span></span>

  - <span data-ttu-id="27559-154">Exchange UM 自動応答から通話を転送する</span><span class="sxs-lookup"><span data-stu-id="27559-154">Transferring calls from an Exchange UM Auto Attendant</span></span>

<span data-ttu-id="27559-155">他のすべての Exchange UM シナリオでは効果があります。</span><span class="sxs-lookup"><span data-stu-id="27559-155">All other Exchange UM scenarios will work properly.</span></span>

<span data-ttu-id="27559-p112">内部エッジ インターフェイスと外部エッジ インターフェイスでは、同じ種類のロード バランシングを使用する必要があります。1 つのエッジ インターフェイスで DNS ロード バランシングを使用し、もう 1 つのエッジ インターフェイスでロード バランサー機器を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="27559-p112">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>

<div>

## <a name="deploying-dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="27559-158">エッジ サーバー プールへの DNS 負荷分散の展開</span><span class="sxs-lookup"><span data-stu-id="27559-158">Deploying DNS Load Balancing on Edge Server Pools</span></span>

<span data-ttu-id="27559-159">エッジ サーバー プールの外部インターフェイスに DNS 負荷分散を展開するには、次の DNS エントリが必要です。</span><span class="sxs-lookup"><span data-stu-id="27559-159">To deploy DNS load balancing on the external interface of your Edge Server pool, you need the following DNS entries:</span></span>

  - <span data-ttu-id="27559-160">アクセスエッジサービスでは、プール内のサーバーごとに1つのエントリが必要です。</span><span class="sxs-lookup"><span data-stu-id="27559-160">For the Access Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="27559-161">各エントリでは、アクセスエッジサービスの FQDN (sip.contoso.com など) を、プール内のいずれかのエッジサーバー上のアクセスエッジサービスの IP アドレスに解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27559-161">Each entry must resolve the FQDN of the Access Edge service (for example, sip.contoso.com) to the IP address of the Access Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="27559-162">Web 会議エッジサービスでは、プール内のサーバーごとに1つのエントリが必要です。</span><span class="sxs-lookup"><span data-stu-id="27559-162">For the Web Conferencing Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="27559-163">各エントリでは、Web 会議エッジサービスの FQDN (webconf.contoso.com など) をプール内のいずれかのエッジサーバー上の Web 会議エッジサービスの IP アドレスに解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27559-163">Each entry must resolve the FQDN of the Web Conferencing Edge service (for example, webconf.contoso.com) to the IP address of the Web Conferencing Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="27559-164">音声ビデオエッジサービスでは、プール内のサーバーごとに1つのエントリが必要です。</span><span class="sxs-lookup"><span data-stu-id="27559-164">For the Audio/Video Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="27559-165">各エントリでは、オーディオ/ビデオエッジサービス (たとえば、av.contoso.com) の FQDN を、プール内のいずれかのエッジサーバーの音声ビデオエッジサービスの IP アドレスに解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27559-165">Each entry must resolve the FQDN of the Audio/Video Edge service (for example, av.contoso.com) to the IP address of the A/V Edge service on one of the Edge Servers in the pool.</span></span>

<span data-ttu-id="27559-166">エッジ サーバー プールの内部インターフェイスに DNS ロード バランシングを展開するには、エッジ サーバー プールの内部 FQDN をプール内の各サーバーの IP アドレスに解決する 1 つの DNS A レコードを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27559-166">To deploy DNS load balancing on the internal interface of your Edge Server pool, you must add one DNS A record, which resolves the internal FQDN of the Edge Server pool to the IP address of each server in the pool.</span></span>

</div>

</div>

<div>

## <a name="using-dns-load-balancing-on-mediation-server-pools"></a><span data-ttu-id="27559-167">仲介サーバー プールでの DNS 負荷分散の使用</span><span class="sxs-lookup"><span data-stu-id="27559-167">Using DNS Load Balancing on Mediation Server Pools</span></span>

<span data-ttu-id="27559-p116">スタンドアロンの仲介サーバー プールで、DNS 負荷分散を使用できます。すべての SIP トラフィックとメディア トラフィックは DNS 負荷分散によって調整されます。</span><span class="sxs-lookup"><span data-stu-id="27559-p116">You can use DNS load balancing on stand-alone Mediation Server pools. All SIP and media traffic is balanced by DNS load balancing.</span></span>

<span data-ttu-id="27559-170">仲介サーバー プールに DNS 負荷分散を展開するには、プールの FQDN (mediationpool1.contoso.com など) をプール内のすべてのサーバーの IP アドレス (192.168.1.1、192.168.1.2 など) に解決するように DNS をプロビジョニングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="27559-170">To deploy DNS load balancing on a Mediation Server pool, you must provision DNS to resolve the pool FQDN (for example, mediationpool1.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on).</span></span>

</div>

<div>

## <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a><span data-ttu-id="27559-171">DNS 負荷分散を使用してサーバーへのトラフィックをブロックする</span><span class="sxs-lookup"><span data-stu-id="27559-171">Blocking Traffic to a Server With DNS Load Balancing</span></span>

<span data-ttu-id="27559-172">DNS 負荷分散を使用していて、特定のコンピューターへのトラフィックをブロックする必要がある場合は、IP アドレスエントリをプールの FQDN から削除するだけで十分ではありません。</span><span class="sxs-lookup"><span data-stu-id="27559-172">If you use DNS load balancing and you need to block traffic to a specific computer, it is not sufficient to just remove the IP address entries from the Pool FQDN.</span></span> <span data-ttu-id="27559-173">コンピューターの DNS エントリも削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27559-173">You must remove the DNS entry for the computer as well.</span></span>

<span data-ttu-id="27559-174">サーバー間トラフィックの場合、Lync Server 2013 ではトポロジ対応の負荷分散が使用されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="27559-174">Note that for server-to-server traffic, Lync Server 2013 uses topology-aware load balancing.</span></span> <span data-ttu-id="27559-175">サーバーは、中央管理ストアで公開されているトポロジを読み取り、トポロジ内のサーバーの Fqdn を取得し、そのトラフィックをサーバー間で自動的に分配します。</span><span class="sxs-lookup"><span data-stu-id="27559-175">Servers read the published topology in the Central Management store to obtain the FQDNs of servers in the topology, and automatically distribute the traffic among the servers.</span></span> <span data-ttu-id="27559-176">サーバーからサーバーへのトラフィックの受信をブロックするには、サーバーをトポロジから削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27559-176">To block a server from receiving server-to-server traffic, you must remove the server from the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

