---
title: Lync Server 2013 のハードウェアロードバランサーの要件
description: Lync Server 2013 のハードウェアロードバランサーの要件。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware load balancer requirements
ms:assetid: 32891268-2059-43d0-adf4-af4ff1e9ce66
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ656815(v=OCS.15)
ms:contentKeyID: 49287208
ms.date: 05/11/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69cbf79c1fd7551dfd428c23ed22c924d0805c43
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552923"
---
# <a name="hardware-load-balancer-requirements-for-lync-server-2013"></a><span data-ttu-id="c2150-103">Lync Server 2013 のハードウェアロードバランサーの要件</span><span class="sxs-lookup"><span data-stu-id="c2150-103">Hardware load balancer requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2150-104">_**トピックの最終更新日:** 2015-05-11_</span><span class="sxs-lookup"><span data-stu-id="c2150-104">_**Topic Last Modified:** 2015-05-11_</span></span>

<span data-ttu-id="c2150-105">Lync server 2013 拡張統合エッジトポロジは、主に Lync Server を使用している他の組織とフェデレーションする新しい展開での DNS 負荷分散のために最適化されています。</span><span class="sxs-lookup"><span data-stu-id="c2150-105">The Lync Server 2013 scaled consolidated Edge topology is optimized for DNS load balancing for new deployments federating primarily with other organizations using Lync Server.</span></span> <span data-ttu-id="c2150-106">次のいずれかのシナリオで高可用性が必要な場合は、次の目的で、エッジ サーバー プールでハードウェア ロード バランサーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2150-106">If high availability is required for any of the following scenarios, a hardware load balancer must be used on Edge Server pools for the following:</span></span>

  - <span data-ttu-id="c2150-107">Office Communications Server 2007 R2 または Office Communications Server 2007 を使用する組織とのフェデレーション</span><span class="sxs-lookup"><span data-stu-id="c2150-107">Federation with organizations using Office Communications Server 2007 R2 or Office Communications Server 2007</span></span>

  - <span data-ttu-id="c2150-108">Exchange 2010 SP1 より前の exchange UM を使用するリモートユーザー用の exchange UM</span><span class="sxs-lookup"><span data-stu-id="c2150-108">Exchange UM for remote users using Exchange UM prior to Exchange 2010 with SP1</span></span>

  - <span data-ttu-id="c2150-109">パブリック IM ユーザーとの接続</span><span class="sxs-lookup"><span data-stu-id="c2150-109">Connectivity to public IM users</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c2150-p102">1 つのインターフェイスでハードウェア負荷分散を使用し、もう 1 つのインターフェイスで DNS 負荷分散を使用することはできません。両方のインターフェイスでハードウェア負荷分散を使用するか、両方で DNS 負荷分散を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2150-p102">Using DNS load balancing on one interface and hardware load balancing on the other is not supported. You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="c2150-p103">ロード バランザー機器を使用している場合は、内部ネットワークとの接続用に展開されているロード バランザーを構成して、アクセス エッジ サービスおよび音声ビデオ サービスを実行しているサーバーへのトラフィックのみを負荷分散する必要があります。内部の Web 会議エッジ サービスまたは内部 XMPP プロキシ サービスへのトラフィックを負荷分散することはできません。</span><span class="sxs-lookup"><span data-stu-id="c2150-p103">If you are using a hardware load balancer, the load balancer deployed for connections with the internal network must be configured to load balance only the traffic to servers running the Access Edge service and the A/V Edge service. It cannot load balance the traffic to the internal Web Conferencing Edge service or the internal XMPP Proxy service.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="c2150-114">直接サーバーリターン (DSR) NAT は、Lync Server 2013 ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c2150-114">The direct server return (DSR) NAT is not supported with Lync Server 2013.</span></span>



</div>

<span data-ttu-id="c2150-115">ご使用のハードウェアロードバランサーが Lync Server 2013 で必要な機能をサポートしているかどうかを判断するには、「Lync Server 2010 ロードバランサーパートナー」を参照してください [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452) 。</span><span class="sxs-lookup"><span data-stu-id="c2150-115">To determine whether your hardware load balancer supports the necessary features required by Lync Server 2013, see "Lync Server 2010 Load Balancer Partners" at [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452).</span></span>

<div>

## <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a><span data-ttu-id="c2150-116">音声ビデオ エッジ サービスを実行するエッジ サーバーに対するロード バランサー機器の要件</span><span class="sxs-lookup"><span data-stu-id="c2150-116">Hardware Load Balancer Requirements for Edge Servers Running the A/V Edge Service</span></span>

<span data-ttu-id="c2150-117">音声ビデオエッジサービスを実行するエッジサーバーに対するハードウェアロードバランサーの要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c2150-117">Following are the hardware load balancer requirements for Edge Servers running the A/V Edge service:</span></span>

  - <span data-ttu-id="c2150-p104">内部と外部の両方のポート 443 に対して TCP のネーグル処理がオフになっていること。ネーグル処理はいくつかの小さなパケットを 1 つの大きなパケットにまとめて転送効率を向上させるプロセスです。</span><span class="sxs-lookup"><span data-stu-id="c2150-p104">Turn off TCP nagling for both internal and external ports 443. Nagling is the process of combining several small packets into a single, larger packet for more efficient transmission.</span></span>

  - <span data-ttu-id="c2150-120">外部ポート範囲 50000 ～ 59999 の TCP のネーグル処理がオフになっていること。</span><span class="sxs-lookup"><span data-stu-id="c2150-120">Turn off TCP nagling for external port range 50,000 – 59,999.</span></span>

  - <span data-ttu-id="c2150-121">内部または外部のファイアウォールで NAT が使用されていないこと。</span><span class="sxs-lookup"><span data-stu-id="c2150-121">Do not use NAT on the internal or external firewall.</span></span>

  - <span data-ttu-id="c2150-122">エッジの内部インターフェイスがエッジ サーバーの外部インターフェイスとは別のネットワークに存在し、それらの間のルーティングが無効になっていること。</span><span class="sxs-lookup"><span data-stu-id="c2150-122">The edge internal interface must be on a different network than the Edge Server external interface and routing between them must be disabled.</span></span>

  - <span data-ttu-id="c2150-123">音声ビデオエッジサービスを実行しているエッジサーバーの外部インターフェイスでは、公開されたルーティング可能な IP アドレスを使用し、エッジの外部 IP アドレスで NAT またはポート変換を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="c2150-123">The external interface of the Edge Server running the A/V Edge Service must use publicly routable IP addresses and no NAT or port translation on any of the edge external IP addresses.</span></span>

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a><span data-ttu-id="c2150-124">ハードウェア ロード バランサーの要件</span><span class="sxs-lookup"><span data-stu-id="c2150-124">Hardware Load Balancer Requirements</span></span>

<span data-ttu-id="c2150-125">Web サービスの Lync Server 2013 では、Cookie ベースのアフィニティ要件が大幅に軽減されます。</span><span class="sxs-lookup"><span data-stu-id="c2150-125">Cookie-based affinity requirements are greatly reduced in Lync Server 2013 for Web services.</span></span> <span data-ttu-id="c2150-126">Lync server 2013 を展開していて、Lync Server 2010 フロントエンドサーバーまたはフロントエンドプールを保持していない場合は、cookie ベースの永続化は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="c2150-126">If you are deploying Lync Server 2013 and will not retain any Lync Server 2010 Front End Servers or Front End pools, you do not need cookie-based persistence.</span></span> <span data-ttu-id="c2150-127">ただし、Lync Server 2010 のフロントエンドサーバーまたはフロントエンドプールを一時的または完全に保持している場合でも、Lync Server 2010 に対して展開および構成されているときは、cookie ベースの永続性を使用します。</span><span class="sxs-lookup"><span data-stu-id="c2150-127">However, if you will temporarily or permanently retain any Lync Server 2010 Front End Servers or Front End pools, you still use cookie-based persistence as it is deployed and configured for Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c2150-128"><STRONG>展開では不要だが、Cookie ベースのアフィニティを使用する場合でも</STRONG>、悪影響はありません。</span><span class="sxs-lookup"><span data-stu-id="c2150-128"><STRONG>If you decide to use cookie-based affinity even though your deployment does not require it</STRONG>, there is no negative impact to doing so.</span></span>



</div>

<span data-ttu-id="c2150-129">Cookie ベースのアフィニティを**使用しない**展開の場合</span><span class="sxs-lookup"><span data-stu-id="c2150-129">For deployments that **will not use** cookie-based affinity:</span></span>

  - <span data-ttu-id="c2150-p106">リバース プロキシのポート 4443 に対する公開ルールで、[**ホスト ヘッダーを転送する**] が True に設定します。これにより、元の URL が確実に転送されます。</span><span class="sxs-lookup"><span data-stu-id="c2150-p106">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True. This will ensure that the original URL is forwarded.</span></span>

<span data-ttu-id="c2150-132">Cookie ベースのアフィニティを**使用する**展開の場合</span><span class="sxs-lookup"><span data-stu-id="c2150-132">For deployments that **will use** cookie-based affinity:</span></span>

  - <span data-ttu-id="c2150-p107">リバース プロキシのポート 4443 に対する公開ルールで、[**ホスト ヘッダーを転送する**] が True に設定します。これにより、元の URL が確実に転送されます。</span><span class="sxs-lookup"><span data-stu-id="c2150-p107">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True. This will ensure that the original URL is forwarded.</span></span>

  - <span data-ttu-id="c2150-135">ロード バランサー機器 Cookie が httpOnly とマークされていないこと</span><span class="sxs-lookup"><span data-stu-id="c2150-135">Hardware load balancer cookie MUST NOT be marked httpOnly</span></span>

  - <span data-ttu-id="c2150-136">ロード バランサー機器 Cookie に有効期限がないこと</span><span class="sxs-lookup"><span data-stu-id="c2150-136">Hardware load balancer cookie MUST NOT have an expiration time</span></span>

  - <span data-ttu-id="c2150-137">ロード バランサー機器 Cookie の名前が **MS-WSMAN** であること (これは Web サービスが受け取ることを想定している値であり、変更できません)</span><span class="sxs-lookup"><span data-stu-id="c2150-137">Hardware load balancer cookie MUST be named **MS-WSMAN** (This is the value that the Web services expect, and cannot be changed)</span></span>

  - <span data-ttu-id="c2150-p108">ロード バランサー機器着信 HTTP 要求に Cookie が含まれていなかったすべての HTTP 応答に Cookie が設定されていること。同じ TCP 接続での以前の HTTP 応答で Cookie がすでに取得されているかどうかは関係ありません。ロード バランサーによって、Cookie の挿入が TCP 接続ごとに 1 回のみ行われるように最適化されている場合は、その最適化を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="c2150-p108">Hardware load balancer cookie MUST be set in every HTTP response for which the incoming HTTP request did not have a cookie, regardless of whether a previous HTTP response on that same TCP connection had already obtained a cookie. If the load balancer optimizes cookie insert to only occur once per TCP connection, that optimization MUST NOT be used</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c2150-140">通常、ハードウェアロードバランサーの構成では、ソースアドレスのアフィニティと20個の TCP セッションの有効期間が使用されます。これは、Lync Server および Lync 2013 クライアントに対しては、クライアントの使用状況やアプリケーションの相互作用によってセッション状態が維持されるため、正常に動作します。</span><span class="sxs-lookup"><span data-stu-id="c2150-140">Typical hardware load balancer configurations use source-address affinity and a 20 min. TCP session lifetime, which is fine for Lync Server and Lync 2013 clients because session state is maintained through client usage and/or and application interaction.</span></span>



</div>

<span data-ttu-id="c2150-141">モバイル デバイスを展開する場合、ロード バランサー機器で、TCP セッション内の個々の要求を負荷分散できるようにする必要があります (実際には、ターゲット IP アドレスに基づいて個々の要求を負荷分散できる必要があります)。</span><span class="sxs-lookup"><span data-stu-id="c2150-141">If you are deploying mobile devices, your hardware load balancer must be able to load balance individual request within a TCP session (in effect, you must be able to load balance an individual request based on the target IP address).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="c2150-p109">F5 ロード バランサー機器には、OneConnect と呼ばれる機能があります。この機能を使用すると、TCP 接続内の各要求が個々に負荷分散されます。モバイル デバイスを展開する場合、ロード バランサー機器のベンダーが同じ機能をサポートしていることを確認してください。最新の Apple iOS モバイル アプリでは、トランスポート層セキュリティ (TLS) v1.2 が必要です。F5 は、その固有の設定を備えています。</span><span class="sxs-lookup"><span data-stu-id="c2150-p109">F5 hardware load balancers have a feature called OneConnect that ensures each request within a TCP connection is individually load balanced. If you are deploying mobile devices, ensure your hardware load balancer vendor supports the same functionality. The latest Apple iOS mobile apps require Transport Layer Security (TLS) version 1.2. F5 provides specific settings for this.</span></span><BR><span data-ttu-id="c2150-146">サードパーティ製のロードバランサー機器の詳細については、「」を参照してください。 <A href="https://go.microsoft.com/fwlink/p/?linkid=230700">https://go.microsoft.com/fwlink/p/?linkId=230700</A></span><span class="sxs-lookup"><span data-stu-id="c2150-146">For details on third party hardware load balancers, see <A href="https://go.microsoft.com/fwlink/p/?linkid=230700">https://go.microsoft.com/fwlink/p/?linkId=230700</A></span></span>



</div>

<span data-ttu-id="c2150-147">ディレクターおよびフロントエンド プールの Web サービスに対するロード バランサー機器の要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c2150-147">Following are the hardware load balancer requirements for Director and Front End pool Web Services:</span></span>

  - <span data-ttu-id="c2150-148">内部 Web サービスの Vip の場合は、 \_ ハードウェアロードバランサーでソースアドレス常設 (内部ポート80、443) を設定します。</span><span class="sxs-lookup"><span data-stu-id="c2150-148">For internal Web Services VIPs, set Source\_addr persistence (internal port 80, 443) on the hardware load balancer.</span></span> <span data-ttu-id="c2150-149">Lync Server 2013 の場合、ソースアドレスの常設とは、1つの \_ IP アドレスからの複数の接続が、セッション状態を維持するために常に1台のサーバーに送信されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="c2150-149">For Lync Server 2013, Source\_addr persistence means that multiple connections coming from a single IP address are always sent to one server to maintain session state.</span></span>

  - <span data-ttu-id="c2150-150">TCP アイドル タイムアウトが 1,800 秒に設定されていること</span><span class="sxs-lookup"><span data-stu-id="c2150-150">Use TCP idle timeout of 1800 seconds.</span></span>

  - <span data-ttu-id="c2150-p111">リバース プロキシと次ホップ プールのハードウェア ロード バランサー間のファイアウォールで、リバース プロキシからハードウェア ロード バランサーへのポート 4443 に対する https: トラフィックを許可するルールが作成されていること。ポート 80、443、および 4443 をリッスンするようにハードウェア ロード バランサーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2150-p111">On the firewall between the reverse proxy and the next hop pool’s hardware load balancer, create a rule to allow https: traffic on port 4443, from the reverse proxy to the hardware load balancer. The hardware load balancer must be configured to listen on ports 80, 443, and 4443.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c2150-153">ロードバランサー機器の構成の詳細については、「 <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port summary-拡張統合エッジ (ハードウェアロードバランサー) (Lync Server 2013)」</A>を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2150-153">For further reading on configuration of the hardware load balancer, please review <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="summary-of-hardware-load-balancer-affinity-requirements"></a><span data-ttu-id="c2150-154">ロード バランサー機器のアフィニティ要件の概要</span><span class="sxs-lookup"><span data-stu-id="c2150-154">Summary of Hardware Load Balancer Affinity Requirements</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c2150-155">クライアント/ユーザーの場所</span><span class="sxs-lookup"><span data-stu-id="c2150-155">Client/user location</span></span></th>
<th><span data-ttu-id="c2150-156">外部 Web サービスの FQDN のアフィニティ要件</span><span class="sxs-lookup"><span data-stu-id="c2150-156">External web services FQDN affinity requirements</span></span></th>
<th><span data-ttu-id="c2150-157">内部 Web サービスの FQDN のアフィニティ要件</span><span class="sxs-lookup"><span data-stu-id="c2150-157">Internal web services FQDN affinity requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c2150-158">Lync Web App (内部および外部ユーザー)</span><span class="sxs-lookup"><span data-stu-id="c2150-158">Lync Web App (internal and external users)</span></span></p>
<p><span data-ttu-id="c2150-159">モバイル デバイス (内部および外部ユーザー)</span><span class="sxs-lookup"><span data-stu-id="c2150-159">Mobile device (internal and external users)</span></span></p></td>
<td><p><span data-ttu-id="c2150-160">アフィニティなし</span><span class="sxs-lookup"><span data-stu-id="c2150-160">No affinity</span></span></p></td>
<td><p><span data-ttu-id="c2150-161">送信元アドレスのアフィニティ</span><span class="sxs-lookup"><span data-stu-id="c2150-161">Source address affinity</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2150-162">Lync Web App (外部ユーザーのみ)</span><span class="sxs-lookup"><span data-stu-id="c2150-162">Lync Web App (external users only)</span></span></p>
<p><span data-ttu-id="c2150-163">モバイル デバイス (内部および外部ユーザー)</span><span class="sxs-lookup"><span data-stu-id="c2150-163">Mobile device (internal and external users)</span></span></p></td>
<td><p><span data-ttu-id="c2150-164">アフィニティなし</span><span class="sxs-lookup"><span data-stu-id="c2150-164">No affinity</span></span></p></td>
<td><p><span data-ttu-id="c2150-165">送信元アドレスのアフィニティ</span><span class="sxs-lookup"><span data-stu-id="c2150-165">Source address affinity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2150-166">Lync Web App (内部ユーザーのみ)</span><span class="sxs-lookup"><span data-stu-id="c2150-166">Lync Web App (internal users only)</span></span></p>
<p><span data-ttu-id="c2150-167">モバイル デバイス (展開しない)</span><span class="sxs-lookup"><span data-stu-id="c2150-167">Mobile device (not deployed)</span></span></p></td>
<td><p><span data-ttu-id="c2150-168">アフィニティなし</span><span class="sxs-lookup"><span data-stu-id="c2150-168">No affinity</span></span></p></td>
<td><p><span data-ttu-id="c2150-169">送信元アドレスのアフィニティ</span><span class="sxs-lookup"><span data-stu-id="c2150-169">Source address affinity</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="port-monitoring-for-hardware-load-balancers"></a><span data-ttu-id="c2150-170">ロード バランサー機器のポート監視</span><span class="sxs-lookup"><span data-stu-id="c2150-170">Port Monitoring for Hardware Load Balancers</span></span>

<span data-ttu-id="c2150-171">特定のサービスがハードウェアまたは通信障害によって使用できないような状況を確認する目的で、ロード バランサー機器に対してポート監視を定義します。</span><span class="sxs-lookup"><span data-stu-id="c2150-171">You define port monitoring on the hardware load balancers to determine when specific services are no longer available due to hardware or communications failure.</span></span> <span data-ttu-id="c2150-172">たとえば、フロントエンドサーバーまたはフロントエンドプールに障害が発生したためにフロントエンドサーバーサービス (RTCSRV) が停止した場合、HLB の監視でも Web サービス上のトラフィックの受信を停止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2150-172">For example, if the Front End Server service (RTCSRV) stops because the Front End Server or Front End pool fails, the HLB monitoring should also stop receiving traffic on the Web Services.</span></span> <span data-ttu-id="c2150-173">以下を監視する目的で、HLB にポート監視を実装します。</span><span class="sxs-lookup"><span data-stu-id="c2150-173">You implement port monitoring on the HLB to monitor the following:</span></span>

### <a name="front-end-server-user-pool--hlb-internal-interface"></a><span data-ttu-id="c2150-174">フロントエンドサーバーユーザープール-HLB 内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c2150-174">Front End Server User Pool – HLB Internal Interface</span></span>

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
<th><span data-ttu-id="c2150-175">仮想 IP/ポート</span><span class="sxs-lookup"><span data-stu-id="c2150-175">Virtual IP/Port</span></span></th>
<th><span data-ttu-id="c2150-176">ノード ポート</span><span class="sxs-lookup"><span data-stu-id="c2150-176">Node Port</span></span></th>
<th><span data-ttu-id="c2150-177">ノード コンピューター/モニター</span><span class="sxs-lookup"><span data-stu-id="c2150-177">Node Machine/Monitor</span></span></th>
<th><span data-ttu-id="c2150-178">保存プロファイル</span><span class="sxs-lookup"><span data-stu-id="c2150-178">Persistence Profile</span></span></th>
<th><span data-ttu-id="c2150-179">Notes</span><span class="sxs-lookup"><span data-stu-id="c2150-179">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c2150-180">&lt;プール &gt; web-int_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="c2150-180">&lt;pool&gt;web-int_mco_443_vs</span></span></p>
<p><span data-ttu-id="c2150-181">443</span><span class="sxs-lookup"><span data-stu-id="c2150-181">443</span></span></p></td>
<td><p><span data-ttu-id="c2150-182">443</span><span class="sxs-lookup"><span data-stu-id="c2150-182">443</span></span></p></td>
<td><p><span data-ttu-id="c2150-183">フロントエンド</span><span class="sxs-lookup"><span data-stu-id="c2150-183">Front End</span></span></p>
<p><span data-ttu-id="c2150-184">5061</span><span class="sxs-lookup"><span data-stu-id="c2150-184">5061</span></span></p></td>
<td><p><span data-ttu-id="c2150-185">ソース</span><span class="sxs-lookup"><span data-stu-id="c2150-185">Source</span></span></p></td>
<td><p><span data-ttu-id="c2150-186">HTTPS</span><span class="sxs-lookup"><span data-stu-id="c2150-186">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2150-187">&lt;プール &gt; web-int_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="c2150-187">&lt;pool&gt;web-int_mco_80_vs</span></span></p>
<p><span data-ttu-id="c2150-188">80</span><span class="sxs-lookup"><span data-stu-id="c2150-188">80</span></span></p></td>
<td><p><span data-ttu-id="c2150-189">80</span><span class="sxs-lookup"><span data-stu-id="c2150-189">80</span></span></p></td>
<td><p><span data-ttu-id="c2150-190">フロントエンド</span><span class="sxs-lookup"><span data-stu-id="c2150-190">Front End</span></span></p>
<p><span data-ttu-id="c2150-191">5061</span><span class="sxs-lookup"><span data-stu-id="c2150-191">5061</span></span></p></td>
<td><p><span data-ttu-id="c2150-192">ソース</span><span class="sxs-lookup"><span data-stu-id="c2150-192">Source</span></span></p></td>
<td><p><span data-ttu-id="c2150-193">HTTP</span><span class="sxs-lookup"><span data-stu-id="c2150-193">HTTP</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="front-end-server-user-pool--hlb-external-interface"></a><span data-ttu-id="c2150-194">フロントエンドサーバーのユーザープール-HLB 外部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c2150-194">Front End Server User Pool – HLB External Interface</span></span>

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
<th><span data-ttu-id="c2150-195">仮想 IP/ポート</span><span class="sxs-lookup"><span data-stu-id="c2150-195">Virtual IP/Port</span></span></th>
<th><span data-ttu-id="c2150-196">ノード ポート</span><span class="sxs-lookup"><span data-stu-id="c2150-196">Node Port</span></span></th>
<th><span data-ttu-id="c2150-197">ノード コンピューター/モニター</span><span class="sxs-lookup"><span data-stu-id="c2150-197">Node Machine/Monitor</span></span></th>
<th><span data-ttu-id="c2150-198">保存プロファイル</span><span class="sxs-lookup"><span data-stu-id="c2150-198">Persistence Profile</span></span></th>
<th><span data-ttu-id="c2150-199">Notes</span><span class="sxs-lookup"><span data-stu-id="c2150-199">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c2150-200">&lt;プール &gt; web_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="c2150-200">&lt;pool&gt;web_mco_443_vs</span></span></p>
<p><span data-ttu-id="c2150-201">443</span><span class="sxs-lookup"><span data-stu-id="c2150-201">443</span></span></p></td>
<td><p><span data-ttu-id="c2150-202">4443</span><span class="sxs-lookup"><span data-stu-id="c2150-202">4443</span></span></p></td>
<td><p><span data-ttu-id="c2150-203">フロントエンド</span><span class="sxs-lookup"><span data-stu-id="c2150-203">Front End</span></span></p>
<p><span data-ttu-id="c2150-204">5061</span><span class="sxs-lookup"><span data-stu-id="c2150-204">5061</span></span></p></td>
<td><p><span data-ttu-id="c2150-205">なし</span><span class="sxs-lookup"><span data-stu-id="c2150-205">None</span></span></p></td>
<td><p><span data-ttu-id="c2150-206">HTTPS</span><span class="sxs-lookup"><span data-stu-id="c2150-206">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2150-207">&lt;プール &gt; web_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="c2150-207">&lt;pool&gt;web_mco_80_vs</span></span></p>
<p><span data-ttu-id="c2150-208">80</span><span class="sxs-lookup"><span data-stu-id="c2150-208">80</span></span></p></td>
<td><p><span data-ttu-id="c2150-209">8080</span><span class="sxs-lookup"><span data-stu-id="c2150-209">8080</span></span></p></td>
<td><p><span data-ttu-id="c2150-210">フロントエンド</span><span class="sxs-lookup"><span data-stu-id="c2150-210">Front End</span></span></p>
<p><span data-ttu-id="c2150-211">5061</span><span class="sxs-lookup"><span data-stu-id="c2150-211">5061</span></span></p></td>
<td><p><span data-ttu-id="c2150-212">なし</span><span class="sxs-lookup"><span data-stu-id="c2150-212">None</span></span></p></td>
<td><p><span data-ttu-id="c2150-213">HTTP</span><span class="sxs-lookup"><span data-stu-id="c2150-213">HTTP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

