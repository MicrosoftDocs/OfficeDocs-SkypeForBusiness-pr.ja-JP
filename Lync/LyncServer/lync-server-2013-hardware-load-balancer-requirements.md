---
title: Lync Server 2013 のハードウェア ロード バランサーの要件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hardware load balancer requirements
ms:assetid: 32891268-2059-43d0-adf4-af4ff1e9ce66
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ656815(v=OCS.15)
ms:contentKeyID: 49287208
ms.date: 05/11/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d5b10a91f469bf4688de06e836e0bdeffae1112
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833091"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-load-balancer-requirements-for-lync-server-2013"></a><span data-ttu-id="ebb2d-102">Lync Server 2013 のハードウェア ロード バランサーの要件</span><span class="sxs-lookup"><span data-stu-id="ebb2d-102">Hardware load balancer requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ebb2d-103">_**最終更新日:** 2015-05-11_</span><span class="sxs-lookup"><span data-stu-id="ebb2d-103">_**Topic Last Modified:** 2015-05-11_</span></span>

<span data-ttu-id="ebb2d-104">Lync Server 2013 スケーリングされた統合エッジトポロジは、新しい展開の場合、Lync Server を使用する他の組織との主な展開のために、DNS の負荷分散のために最適化されています。</span><span class="sxs-lookup"><span data-stu-id="ebb2d-104">The Lync Server 2013 scaled consolidated Edge topology is optimized for DNS load balancing for new deployments federating primarily with other organizations using Lync Server.</span></span> <span data-ttu-id="ebb2d-105">次のシナリオのいずれかに対して高可用性が必要な場合は、次のように、エッジサーバープールでハードウェアロードバランサーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebb2d-105">If high availability is required for any of the following scenarios, a hardware load balancer must be used on Edge Server pools for the following:</span></span>

  - <span data-ttu-id="ebb2d-106">Office Communications Server 2007 R2 または Office Communications Server 2007 を使用している組織とのフェデレーション</span><span class="sxs-lookup"><span data-stu-id="ebb2d-106">Federation with organizations using Office Communications Server 2007 R2 or Office Communications Server 2007</span></span>

  - <span data-ttu-id="ebb2d-107">Exchange 2010 SP1 より前の exchange UM を使用しているリモートユーザーの exchange UM</span><span class="sxs-lookup"><span data-stu-id="ebb2d-107">Exchange UM for remote users using Exchange UM prior to Exchange 2010 with SP1</span></span>

  - <span data-ttu-id="ebb2d-108">パブリック IM ユーザーとの接続</span><span class="sxs-lookup"><span data-stu-id="ebb2d-108">Connectivity to public IM users</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ebb2d-p102">1 つのインターフェイスでハードウェア負荷分散を使用し、もう 1 つのインターフェイスで DNS 負荷分散を使用することはできません。両方のインターフェイスでハードウェア負荷分散を使用するか、両方で DNS 負荷分散を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebb2d-p102">Using DNS load balancing on one interface and hardware load balancing on the other is not supported. You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="ebb2d-p103">ロード バランサー機器を使用している場合は、内部ネットワークとの接続用に展開されているロード バランサーを構成して、アクセス エッジ サービスおよび音声ビデオ サービスを実行しているサーバーへのトラフィックのみを負荷分散する必要があります。内部の Web 会議エッジ サービスまたは内部 XMPP プロキシ サービスへのトラフィックを負荷分散することはできません。</span><span class="sxs-lookup"><span data-stu-id="ebb2d-p103">If you are using a hardware load balancer, the load balancer deployed for connections with the internal network must be configured to load balance only the traffic to servers running the Access Edge service and the A/V Edge service. It cannot load balance the traffic to the internal Web Conferencing Edge service or the internal XMPP Proxy service.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="ebb2d-113">Direct server return (DSR) NAT は、Lync Server 2013 ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ebb2d-113">The direct server return (DSR) NAT is not supported with Lync Server 2013.</span></span>



</div>

<span data-ttu-id="ebb2d-114">使用[http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452)しているハードウェアロードバランサーが lync server 2013 に必要な機能をサポートしているかどうかを判断するには、の「lync Server 2010 ロードバランサーパートナー」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebb2d-114">To determine whether your hardware load balancer supports the necessary features required by Lync Server 2013, see "Lync Server 2010 Load Balancer Partners" at [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452).</span></span>

<div>

## <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a><span data-ttu-id="ebb2d-115">音声ビデオ エッジ サービスを実行するエッジ サーバーに対するロード バランサー機器の要件</span><span class="sxs-lookup"><span data-stu-id="ebb2d-115">Hardware Load Balancer Requirements for Edge Servers Running the A/V Edge Service</span></span>

<span data-ttu-id="ebb2d-116">A/V Edge サービスを実行しているエッジサーバーのハードウェアロードバランサーの要件を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ebb2d-116">Following are the hardware load balancer requirements for Edge Servers running the A/V Edge service:</span></span>

  - <span data-ttu-id="ebb2d-p104">内部と外部の両方のポート 443 に対して TCP のネーグル処理がオフになっていること。ネーグル処理はいくつかの小さなパケットを 1 つの大きなパケットにまとめて転送効率を向上させるプロセスです。</span><span class="sxs-lookup"><span data-stu-id="ebb2d-p104">Turn off TCP nagling for both internal and external ports 443. Nagling is the process of combining several small packets into a single, larger packet for more efficient transmission.</span></span>

  - <span data-ttu-id="ebb2d-119">外部ポート範囲 50000 ～ 59999 の TCP のネーグル処理がオフになっていること。</span><span class="sxs-lookup"><span data-stu-id="ebb2d-119">Turn off TCP nagling for external port range 50,000 – 59,999.</span></span>

  - <span data-ttu-id="ebb2d-120">内部または外部のファイアウォールで NAT が使用されていないこと。</span><span class="sxs-lookup"><span data-stu-id="ebb2d-120">Do not use NAT on the internal or external firewall.</span></span>

  - <span data-ttu-id="ebb2d-121">Edge の内部インターフェイスは、エッジサーバーの外部インターフェイスとは異なるネットワーク上にあり、その間のルーティングを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebb2d-121">The edge internal interface must be on a different network than the Edge Server external interface and routing between them must be disabled.</span></span>

  - <span data-ttu-id="ebb2d-122">A/V Edge サービスを実行しているエッジサーバーの外部インターフェイスでは、公開ルーティング可能な IP アドレスを使用し、エッジ外部 IP アドレスには NAT やポートの変換を行わないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebb2d-122">The external interface of the Edge Server running the A/V Edge Service must use publicly routable IP addresses and no NAT or port translation on any of the edge external IP addresses.</span></span>

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a><span data-ttu-id="ebb2d-123">ロード バランサー機器の要件</span><span class="sxs-lookup"><span data-stu-id="ebb2d-123">Hardware Load Balancer Requirements</span></span>

<span data-ttu-id="ebb2d-124">Cookie ベースのアフィニティ要件は、Web サービスの Lync Server 2013 で大幅に削減されます。</span><span class="sxs-lookup"><span data-stu-id="ebb2d-124">Cookie-based affinity requirements are greatly reduced in Lync Server 2013 for Web services.</span></span> <span data-ttu-id="ebb2d-125">Lync server 2013 を展開していて、Lync Server 2010 フロントエンドサーバーまたはフロントエンドプールを保持していない場合は、cookie ベースの常設は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="ebb2d-125">If you are deploying Lync Server 2013 and will not retain any Lync Server 2010 Front End Servers or Front End pools, you do not need cookie-based persistence.</span></span> <span data-ttu-id="ebb2d-126">ただし、Lync Server 2010 のフロントエンドサーバーまたはフロントエンドプールを一時的または完全に保持する場合でも、Lync Server 2010 用に展開して構成すると、cookie ベースの常設が使用されます。</span><span class="sxs-lookup"><span data-stu-id="ebb2d-126">However, if you will temporarily or permanently retain any Lync Server 2010 Front End Servers or Front End pools, you still use cookie-based persistence as it is deployed and configured for Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ebb2d-127"><STRONG>展開では不要だが、Cookie ベースのアフィニティを使用する場合でも</STRONG>、悪影響はありません。</span><span class="sxs-lookup"><span data-stu-id="ebb2d-127"><STRONG>If you decide to use cookie-based affinity even though your deployment does not require it</STRONG>, there is no negative impact to doing so.</span></span>



</div>

<span data-ttu-id="ebb2d-128">Cookie ベースのアフィニティを**使用しない**展開の場合</span><span class="sxs-lookup"><span data-stu-id="ebb2d-128">For deployments that **will not use** cookie-based affinity:</span></span>

  - <span data-ttu-id="ebb2d-129">リバース プロキシのポート 4443 に対する公開ルールで、[**ホスト ヘッダーを転送する**] を True に設定します。</span><span class="sxs-lookup"><span data-stu-id="ebb2d-129">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True.</span></span> <span data-ttu-id="ebb2d-130">これにより、元の URL が確実に転送されます。</span><span class="sxs-lookup"><span data-stu-id="ebb2d-130">This will ensure that the original URL is forwarded.</span></span>

<span data-ttu-id="ebb2d-131">Cookie ベースのアフィニティを**使用する**展開の場合</span><span class="sxs-lookup"><span data-stu-id="ebb2d-131">For deployments that **will use** cookie-based affinity:</span></span>

  - <span data-ttu-id="ebb2d-p107">リバース プロキシのポート 4443 に対する公開ルールで、[**ホスト ヘッダーを転送する**] を True に設定します。これにより、元の URL が確実に転送されます。</span><span class="sxs-lookup"><span data-stu-id="ebb2d-p107">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True. This will ensure that the original URL is forwarded.</span></span>

  - <span data-ttu-id="ebb2d-134">ロード バランサー機器 Cookie が httpOnly とマークされていないこと</span><span class="sxs-lookup"><span data-stu-id="ebb2d-134">Hardware load balancer cookie MUST NOT be marked httpOnly</span></span>

  - <span data-ttu-id="ebb2d-135">ロード バランサー機器 Cookie に有効期限がないこと</span><span class="sxs-lookup"><span data-stu-id="ebb2d-135">Hardware load balancer cookie MUST NOT have an expiration time</span></span>

  - <span data-ttu-id="ebb2d-136">ロード バランサー機器 Cookie の名前が **MS-WSMAN** であること (これは Web サービスが受け取ることを想定している値であり、変更できません)</span><span class="sxs-lookup"><span data-stu-id="ebb2d-136">Hardware load balancer cookie MUST be named **MS-WSMAN** (This is the value that the Web services expect, and cannot be changed)</span></span>

  - <span data-ttu-id="ebb2d-p108">ロード バランサー機器着信 HTTP 要求に Cookie が含まれていなかったすべての HTTP 応答に Cookie が設定されていること。同じ TCP 接続での以前の HTTP 応答で Cookie が既に取得されているかどうかは関係ありません。ロード バランサーによって、Cookie の挿入が TCP 接続ごとに 1 回のみ行われるように最適化されている場合は、その最適化を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="ebb2d-p108">Hardware load balancer cookie MUST be set in every HTTP response for which the incoming HTTP request did not have a cookie, regardless of whether a previous HTTP response on that same TCP connection had already obtained a cookie. If the load balancer optimizes cookie insert to only occur once per TCP connection, that optimization MUST NOT be used</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ebb2d-139">一般的なハードウェアロードバランサー構成では、ソースアドレスのアフィニティと20分の TCP セッションの有効期限が使用されます。これは、クライアントの使用状況やアプリケーションの操作によってセッションの状態が維持されるため、Lync Server と Lync 2013 クライアントにとって適切です。</span><span class="sxs-lookup"><span data-stu-id="ebb2d-139">Typical hardware load balancer configurations use source-address affinity and a 20 min. TCP session lifetime, which is fine for Lync Server and Lync 2013 clients because session state is maintained through client usage and/or and application interaction.</span></span>



</div>

<span data-ttu-id="ebb2d-140">モバイル デバイスを展開する場合、ロード バランサー機器で、TCP セッション内の個々の要求を負荷分散できるようにする必要があります (実際には、ターゲット IP アドレスに基づいて個々の要求を負荷分散できる必要があります)。</span><span class="sxs-lookup"><span data-stu-id="ebb2d-140">If you are deploying mobile devices, your hardware load balancer must be able to load balance individual request within a TCP session (in effect, you must be able to load balance an individual request based on the target IP address).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="ebb2d-p109">F5 ロード バランサー機器には、OneConnect と呼ばれる機能があります。この機能を使用すると、TCP 接続内の各要求が個々に負荷分散されます。モバイル デバイスを展開する場合、ロード バランサー機器のベンダーが同じ機能をサポートしていることを確認してください。最新の Apple iOS モバイル アプリでは、トランスポート層セキュリティ (TLS) v1.2 が必要です。F5 は、その固有の設定を備えています。</span><span class="sxs-lookup"><span data-stu-id="ebb2d-p109">F5 hardware load balancers have a feature called OneConnect that ensures each request within a TCP connection is individually load balanced. If you are deploying mobile devices, ensure your hardware load balancer vendor supports the same functionality. The latest Apple iOS mobile apps require Transport Layer Security (TLS) version 1.2. F5 provides specific settings for this.</span></span><BR><span data-ttu-id="ebb2d-145">サードパーティのハードウェアロードバランサーの詳細については、<A href="http://go.microsoft.com/fwlink/p/?linkid=230700">http://go.microsoft.com/fwlink/p/?linkId=230700</A></span><span class="sxs-lookup"><span data-stu-id="ebb2d-145">For details on third party hardware load balancers, see <A href="http://go.microsoft.com/fwlink/p/?linkid=230700">http://go.microsoft.com/fwlink/p/?linkId=230700</A></span></span>



</div>

<span data-ttu-id="ebb2d-146">ディレクターおよびフロントエンド プールの Web サービスに対するロード バランサー機器の要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ebb2d-146">Following are the hardware load balancer requirements for Director and Front End pool Web Services:</span></span>

  - <span data-ttu-id="ebb2d-147">内部の Web サービス Vip では、\_ハードウェアのロードバランサーでソースアドレスの常設 (内部ポート80、443) を設定します。</span><span class="sxs-lookup"><span data-stu-id="ebb2d-147">For internal Web Services VIPs, set Source\_addr persistence (internal port 80, 443) on the hardware load balancer.</span></span> <span data-ttu-id="ebb2d-148">Lync Server 2013 の場合、\_ソースアドレス常設は、1つの IP アドレスからの複数の接続が常に1つのサーバーに送信され、セッションの状態を維持することを意味します。</span><span class="sxs-lookup"><span data-stu-id="ebb2d-148">For Lync Server 2013, Source\_addr persistence means that multiple connections coming from a single IP address are always sent to one server to maintain session state.</span></span>

  - <span data-ttu-id="ebb2d-149">TCP アイドル タイムアウトが 1800 秒に設定されていること</span><span class="sxs-lookup"><span data-stu-id="ebb2d-149">Use TCP idle timeout of 1800 seconds.</span></span>

  - <span data-ttu-id="ebb2d-p111">リバース プロキシと次ホップ プールのロード バランサー機器間のファイアウォールで、リバース プロキシからロード バランサー機器へのポート 4443 に対する https: トラフィックを許可するルールが作成されていること。ポート 80、443、および 4443 をリッスンするようにロード バランサー機器を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebb2d-p111">On the firewall between the reverse proxy and the next hop pool’s hardware load balancer, create a rule to allow https: traffic on port 4443, from the reverse proxy to the hardware load balancer. The hardware load balancer must be configured to listen on ports 80, 443, and 4443.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ebb2d-152">ハードウェアロードバランサーの構成の詳細については、「<A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">ポートの概要-Lync Server 2013 でハードウェアロードバランサーを使用して拡大縮小されたエッジを</A>確認する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebb2d-152">For further reading on configuration of the hardware load balancer, please review <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="summary-of-hardware-load-balancer-affinity-requirements"></a><span data-ttu-id="ebb2d-153">ロード バランサー機器のアフィニティ要件の概要</span><span class="sxs-lookup"><span data-stu-id="ebb2d-153">Summary of Hardware Load Balancer Affinity Requirements</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ebb2d-154">クライアント/ユーザーの場所</span><span class="sxs-lookup"><span data-stu-id="ebb2d-154">Client/user location</span></span></th>
<th><span data-ttu-id="ebb2d-155">外部 Web サービスの FQDN のアフィニティ要件</span><span class="sxs-lookup"><span data-stu-id="ebb2d-155">External web services FQDN affinity requirements</span></span></th>
<th><span data-ttu-id="ebb2d-156">内部 Web サービスの FQDN のアフィニティ要件</span><span class="sxs-lookup"><span data-stu-id="ebb2d-156">Internal web services FQDN affinity requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ebb2d-157">Lync Web App (内部と外部のユーザー)</span><span class="sxs-lookup"><span data-stu-id="ebb2d-157">Lync Web App (internal and external users)</span></span></p>
<p><span data-ttu-id="ebb2d-158">モバイル デバイス (内部および外部ユーザー)</span><span class="sxs-lookup"><span data-stu-id="ebb2d-158">Mobile device (internal and external users)</span></span></p></td>
<td><p><span data-ttu-id="ebb2d-159">アフィニティなし</span><span class="sxs-lookup"><span data-stu-id="ebb2d-159">No affinity</span></span></p></td>
<td><p><span data-ttu-id="ebb2d-160">送信元アドレスのアフィニティ</span><span class="sxs-lookup"><span data-stu-id="ebb2d-160">Source address affinity</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ebb2d-161">Lync Web App (外部ユーザーのみ)</span><span class="sxs-lookup"><span data-stu-id="ebb2d-161">Lync Web App (external users only)</span></span></p>
<p><span data-ttu-id="ebb2d-162">モバイル デバイス (内部および外部ユーザー)</span><span class="sxs-lookup"><span data-stu-id="ebb2d-162">Mobile device (internal and external users)</span></span></p></td>
<td><p><span data-ttu-id="ebb2d-163">アフィニティなし</span><span class="sxs-lookup"><span data-stu-id="ebb2d-163">No affinity</span></span></p></td>
<td><p><span data-ttu-id="ebb2d-164">送信元アドレスのアフィニティ</span><span class="sxs-lookup"><span data-stu-id="ebb2d-164">Source address affinity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ebb2d-165">Lync Web App (内部ユーザーのみ)</span><span class="sxs-lookup"><span data-stu-id="ebb2d-165">Lync Web App (internal users only)</span></span></p>
<p><span data-ttu-id="ebb2d-166">モバイル デバイス (展開しない)</span><span class="sxs-lookup"><span data-stu-id="ebb2d-166">Mobile device (not deployed)</span></span></p></td>
<td><p><span data-ttu-id="ebb2d-167">アフィニティなし</span><span class="sxs-lookup"><span data-stu-id="ebb2d-167">No affinity</span></span></p></td>
<td><p><span data-ttu-id="ebb2d-168">送信元アドレスのアフィニティ</span><span class="sxs-lookup"><span data-stu-id="ebb2d-168">Source address affinity</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="port-monitoring-for-hardware-load-balancers"></a><span data-ttu-id="ebb2d-169">ロード バランサー機器のポート監視</span><span class="sxs-lookup"><span data-stu-id="ebb2d-169">Port Monitoring for Hardware Load Balancers</span></span>

<span data-ttu-id="ebb2d-170">特定のサービスがハードウェアまたは通信障害によって使用できないような状況を確認する目的で、ロード バランサー機器に対してポート監視を定義します。</span><span class="sxs-lookup"><span data-stu-id="ebb2d-170">You define port monitoring on the hardware load balancers to determine when specific services are no longer available due to hardware or communications failure.</span></span> <span data-ttu-id="ebb2d-171">たとえば、フロントエンドサーバーまたはフロントエンドプールに障害が発生したために、フロントエンドサーバーサービス (RTCSRV) が停止した場合、HLB の監視でも Web サービスのトラフィックの受信を停止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebb2d-171">For example, if the Front End Server service (RTCSRV) stops because the Front End Server or Front End pool fails, the HLB monitoring should also stop receiving traffic on the Web Services.</span></span> <span data-ttu-id="ebb2d-172">以下を監視する目的で、HLB にポート監視を実装します。</span><span class="sxs-lookup"><span data-stu-id="ebb2d-172">You implement port monitoring on the HLB to monitor the following:</span></span>

### <a name="front-end-server-user-pool--hlb-internal-interface"></a><span data-ttu-id="ebb2d-173">フロントエンドサーバーのユーザープール– HLB 内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ebb2d-173">Front End Server User Pool – HLB Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ebb2d-174">仮想 IP/ポート</span><span class="sxs-lookup"><span data-stu-id="ebb2d-174">Virtual IP/Port</span></span></th>
<th><span data-ttu-id="ebb2d-175">ノード ポート</span><span class="sxs-lookup"><span data-stu-id="ebb2d-175">Node Port</span></span></th>
<th><span data-ttu-id="ebb2d-176">ノード コンピューター/モニター</span><span class="sxs-lookup"><span data-stu-id="ebb2d-176">Node Machine/Monitor</span></span></th>
<th><span data-ttu-id="ebb2d-177">保存プロファイル</span><span class="sxs-lookup"><span data-stu-id="ebb2d-177">Persistence Profile</span></span></th>
<th><span data-ttu-id="ebb2d-178">メモ</span><span class="sxs-lookup"><span data-stu-id="ebb2d-178">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ebb2d-179">&lt;pool&gt;web-int_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="ebb2d-179">&lt;pool&gt;web-int_mco_443_vs</span></span></p>
<p><span data-ttu-id="ebb2d-180">443</span><span class="sxs-lookup"><span data-stu-id="ebb2d-180">443</span></span></p></td>
<td><p><span data-ttu-id="ebb2d-181">443</span><span class="sxs-lookup"><span data-stu-id="ebb2d-181">443</span></span></p></td>
<td><p><span data-ttu-id="ebb2d-182">フロントエンド</span><span class="sxs-lookup"><span data-stu-id="ebb2d-182">Front End</span></span></p>
<p><span data-ttu-id="ebb2d-183">5061</span><span class="sxs-lookup"><span data-stu-id="ebb2d-183">5061</span></span></p></td>
<td><p><span data-ttu-id="ebb2d-184">ソース</span><span class="sxs-lookup"><span data-stu-id="ebb2d-184">Source</span></span></p></td>
<td><p><span data-ttu-id="ebb2d-185">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ebb2d-185">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ebb2d-186">&lt;pool&gt;web-int_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="ebb2d-186">&lt;pool&gt;web-int_mco_80_vs</span></span></p>
<p><span data-ttu-id="ebb2d-187">80</span><span class="sxs-lookup"><span data-stu-id="ebb2d-187">80</span></span></p></td>
<td><p><span data-ttu-id="ebb2d-188">80</span><span class="sxs-lookup"><span data-stu-id="ebb2d-188">80</span></span></p></td>
<td><p><span data-ttu-id="ebb2d-189">フロントエンド</span><span class="sxs-lookup"><span data-stu-id="ebb2d-189">Front End</span></span></p>
<p><span data-ttu-id="ebb2d-190">5061</span><span class="sxs-lookup"><span data-stu-id="ebb2d-190">5061</span></span></p></td>
<td><p><span data-ttu-id="ebb2d-191">ソース</span><span class="sxs-lookup"><span data-stu-id="ebb2d-191">Source</span></span></p></td>
<td><p><span data-ttu-id="ebb2d-192">HTTP</span><span class="sxs-lookup"><span data-stu-id="ebb2d-192">HTTP</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="front-end-server-user-pool--hlb-external-interface"></a><span data-ttu-id="ebb2d-193">フロントエンドサーバーのユーザープール– HLB 外部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ebb2d-193">Front End Server User Pool – HLB External Interface</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ebb2d-194">仮想 IP/ポート</span><span class="sxs-lookup"><span data-stu-id="ebb2d-194">Virtual IP/Port</span></span></th>
<th><span data-ttu-id="ebb2d-195">ノード ポート</span><span class="sxs-lookup"><span data-stu-id="ebb2d-195">Node Port</span></span></th>
<th><span data-ttu-id="ebb2d-196">ノード コンピューター/モニター</span><span class="sxs-lookup"><span data-stu-id="ebb2d-196">Node Machine/Monitor</span></span></th>
<th><span data-ttu-id="ebb2d-197">保存プロファイル</span><span class="sxs-lookup"><span data-stu-id="ebb2d-197">Persistence Profile</span></span></th>
<th><span data-ttu-id="ebb2d-198">メモ</span><span class="sxs-lookup"><span data-stu-id="ebb2d-198">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ebb2d-199">&lt;プール&gt;web_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="ebb2d-199">&lt;pool&gt;web_mco_443_vs</span></span></p>
<p><span data-ttu-id="ebb2d-200">443</span><span class="sxs-lookup"><span data-stu-id="ebb2d-200">443</span></span></p></td>
<td><p><span data-ttu-id="ebb2d-201">4443</span><span class="sxs-lookup"><span data-stu-id="ebb2d-201">4443</span></span></p></td>
<td><p><span data-ttu-id="ebb2d-202">フロントエンド</span><span class="sxs-lookup"><span data-stu-id="ebb2d-202">Front End</span></span></p>
<p><span data-ttu-id="ebb2d-203">5061</span><span class="sxs-lookup"><span data-stu-id="ebb2d-203">5061</span></span></p></td>
<td><p><span data-ttu-id="ebb2d-204">なし</span><span class="sxs-lookup"><span data-stu-id="ebb2d-204">None</span></span></p></td>
<td><p><span data-ttu-id="ebb2d-205">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ebb2d-205">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ebb2d-206">&lt;プール&gt;web_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="ebb2d-206">&lt;pool&gt;web_mco_80_vs</span></span></p>
<p><span data-ttu-id="ebb2d-207">80</span><span class="sxs-lookup"><span data-stu-id="ebb2d-207">80</span></span></p></td>
<td><p><span data-ttu-id="ebb2d-208">8080</span><span class="sxs-lookup"><span data-stu-id="ebb2d-208">8080</span></span></p></td>
<td><p><span data-ttu-id="ebb2d-209">フロントエンド</span><span class="sxs-lookup"><span data-stu-id="ebb2d-209">Front End</span></span></p>
<p><span data-ttu-id="ebb2d-210">5061</span><span class="sxs-lookup"><span data-stu-id="ebb2d-210">5061</span></span></p></td>
<td><p><span data-ttu-id="ebb2d-211">なし</span><span class="sxs-lookup"><span data-stu-id="ebb2d-211">None</span></span></p></td>
<td><p><span data-ttu-id="ebb2d-212">HTTP</span><span class="sxs-lookup"><span data-stu-id="ebb2d-212">HTTP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

