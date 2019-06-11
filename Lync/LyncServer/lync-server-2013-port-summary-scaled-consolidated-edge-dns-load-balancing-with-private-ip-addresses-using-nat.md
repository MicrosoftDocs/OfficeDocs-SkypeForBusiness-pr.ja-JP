---
title: 'Lync Server 2013: ポートの概要 - 拡張統合エッジ、NAT によるプライベート IP アドレスを使用した DNS 負荷分散'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: a296c2af-54d4-4b4f-9795-9191baf688cb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412756(v=OCS.15)
ms:contentKeyID: 48184955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d7e9a142e478674f4be369ace5551b2b628db83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824331"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="3227a-102">ポートの概要 - Lync Server 2013 における拡張統合エッジ、NAT によるプライベート IP アドレスを使用した DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="3227a-102">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3227a-103">_**最終更新日:** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="3227a-103">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="3227a-104">このシナリオアーキテクチャで説明されている Lync Server 2013 のエッジサーバー機能は、Lync Server 2010 で実装されたものとよく似ています。</span><span class="sxs-lookup"><span data-stu-id="3227a-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="3227a-105">最も顕著な追加機能は、拡張メッセージングとプレゼンスプロトコル (XMPP) の TCP エントリのポート**5269**です。</span><span class="sxs-lookup"><span data-stu-id="3227a-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="3227a-106">Lync Server 2013 では、必要に応じて、microsoft Edge サーバーまたはエッジプールに XMPP プロキシを展開し、フロントエンドサーバーまたはフロントエンドプールに XMPP ゲートウェイサーバーを配置します。</span><span class="sxs-lookup"><span data-stu-id="3227a-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="3227a-107">IPv4 に加えて、エッジサーバーは IPv6 をサポートするようになりました。</span><span class="sxs-lookup"><span data-stu-id="3227a-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="3227a-108">わかりやすくするために、シナリオでは IPv4 のみが使用されます。</span><span class="sxs-lookup"><span data-stu-id="3227a-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="3227a-109">**NAT を使用する統合エッジ用のエンタープライズ境界ネットワークとプライベート IP アドレス**</span><span class="sxs-lookup"><span data-stu-id="3227a-109">**Enterprise perimeter network for scaled consolidated edge with private IP addresses using NAT**</span></span>

<span data-ttu-id="3227a-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="3227a-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="3227a-111">ポートとプロトコルの詳細</span><span class="sxs-lookup"><span data-stu-id="3227a-111">Port and Protocol Details</span></span>

<span data-ttu-id="3227a-112">外部アクセスを提供する機能をサポートするために必要なポートのみを開くことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3227a-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="3227a-113">エッジサービスに対してリモートアクセスを使用するには、受信/送信エッジトラフィックの図に示すように、SIP トラフィックが双方向に流れるようにすることが必須です。</span><span class="sxs-lookup"><span data-stu-id="3227a-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="3227a-114">別の方法として、アクセスエッジサービスとの間の SIP メッセージングは、インスタントメッセージング (IM)、プレゼンス、web 会議、音声/ビデオ (A/V)、およびフェデレーションに関連しています。</span><span class="sxs-lookup"><span data-stu-id="3227a-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="3227a-115">拡張統合エッジの場合のファイアウォールの概要、NAT を使用したプライベート IP アドレスを使った DNS 負荷分散: ノード1とノード 2 (例)</span><span class="sxs-lookup"><span data-stu-id="3227a-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3227a-116">Role/Protocol/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="3227a-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="3227a-117">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="3227a-117">Source IP address</span></span></th>
<th><span data-ttu-id="3227a-118">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="3227a-118">Destination IP address</span></span></th>
<th><span data-ttu-id="3227a-119">メモ</span><span class="sxs-lookup"><span data-stu-id="3227a-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3227a-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="3227a-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="3227a-121">任意</span><span class="sxs-lookup"><span data-stu-id="3227a-121">Any</span></span></p></td>
<td><p><span data-ttu-id="3227a-122">XMPP プロキシサービス (アクセスエッジサービスで IP アドレスを共有)</span><span class="sxs-lookup"><span data-stu-id="3227a-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="3227a-123">XMPP プロキシサービスは、定義された XMPP フェデレーションの XMPP 連絡先からのトラフィックを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="3227a-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3227a-124">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="3227a-124">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="3227a-125">XMPP プロキシサービス (アクセスエッジサービスで IP アドレスを共有)</span><span class="sxs-lookup"><span data-stu-id="3227a-125">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="3227a-126">任意</span><span class="sxs-lookup"><span data-stu-id="3227a-126">Any</span></span></p></td>
<td><p><span data-ttu-id="3227a-127">XMPP プロキシサービスは、定義された XMPP フェデレーションの XMPP の連絡先にトラフィックを送信します。</span><span class="sxs-lookup"><span data-stu-id="3227a-127">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3227a-128">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="3227a-128">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="3227a-129">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="3227a-129">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="3227a-130">任意</span><span class="sxs-lookup"><span data-stu-id="3227a-130">Any</span></span></p></td>
<td><p><span data-ttu-id="3227a-131">証明書の失効/CRL の確認と取得</span><span class="sxs-lookup"><span data-stu-id="3227a-131">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3227a-132">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="3227a-132">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="3227a-133">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="3227a-133">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="3227a-134">任意</span><span class="sxs-lookup"><span data-stu-id="3227a-134">Any</span></span></p></td>
<td><p><span data-ttu-id="3227a-135">TCP 経由の DNS クエリ</span><span class="sxs-lookup"><span data-stu-id="3227a-135">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3227a-136">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="3227a-136">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="3227a-137">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="3227a-137">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="3227a-138">任意</span><span class="sxs-lookup"><span data-stu-id="3227a-138">Any</span></span></p></td>
<td><p><span data-ttu-id="3227a-139">UDP 経由の DNS クエリ</span><span class="sxs-lookup"><span data-stu-id="3227a-139">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3227a-140">アクセス/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="3227a-140">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="3227a-141">任意</span><span class="sxs-lookup"><span data-stu-id="3227a-141">Any</span></span></p></td>
<td><p><span data-ttu-id="3227a-142">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="3227a-142">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="3227a-143">外部ユーザーアクセスのクライアントツーサーバー SIP トラフィック</span><span class="sxs-lookup"><span data-stu-id="3227a-143">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3227a-144">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="3227a-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3227a-145">任意</span><span class="sxs-lookup"><span data-stu-id="3227a-145">Any</span></span></p></td>
<td><p><span data-ttu-id="3227a-146">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="3227a-146">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="3227a-147">SIP を使用するフェデレーションおよびパブリック IM 接続の場合</span><span class="sxs-lookup"><span data-stu-id="3227a-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3227a-148">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="3227a-148">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3227a-149">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="3227a-149">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="3227a-150">任意</span><span class="sxs-lookup"><span data-stu-id="3227a-150">Any</span></span></p></td>
<td><p><span data-ttu-id="3227a-151">SIP を使用するフェデレーションおよびパブリック IM 接続の場合</span><span class="sxs-lookup"><span data-stu-id="3227a-151">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3227a-152">Web 会議/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="3227a-152">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="3227a-153">任意</span><span class="sxs-lookup"><span data-stu-id="3227a-153">Any</span></span></p></td>
<td><p><span data-ttu-id="3227a-154">エッジサーバー Web 会議エッジサービス</span><span class="sxs-lookup"><span data-stu-id="3227a-154">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="3227a-155">Web 会議メディア</span><span class="sxs-lookup"><span data-stu-id="3227a-155">Web Conferencing media</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3227a-156">A/V/RTP/59,999</span><span class="sxs-lookup"><span data-stu-id="3227a-156">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="3227a-157">エッジサーバーの A/V Edge サービス</span><span class="sxs-lookup"><span data-stu-id="3227a-157">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3227a-158">任意</span><span class="sxs-lookup"><span data-stu-id="3227a-158">Any</span></span></p></td>
<td><p><span data-ttu-id="3227a-159">Office Communications Server 2007、Office Communications Server 2007 R2、Lync Server 2010、および Lync Server 2013 を実行しているパートナーとのフェデレーションに必要。</span><span class="sxs-lookup"><span data-stu-id="3227a-159">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3227a-160">A/V/RTP/59,999</span><span class="sxs-lookup"><span data-stu-id="3227a-160">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="3227a-161">エッジサーバーの A/V Edge サービス</span><span class="sxs-lookup"><span data-stu-id="3227a-161">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3227a-162">任意</span><span class="sxs-lookup"><span data-stu-id="3227a-162">Any</span></span></p></td>
<td><p><span data-ttu-id="3227a-163">Office Communications Server 2007 を実行しているパートナーとのフェデレーションの場合のみ必須です。</span><span class="sxs-lookup"><span data-stu-id="3227a-163">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3227a-164">A/V/RTP/59,999</span><span class="sxs-lookup"><span data-stu-id="3227a-164">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="3227a-165">任意</span><span class="sxs-lookup"><span data-stu-id="3227a-165">Any</span></span></p></td>
<td><p><span data-ttu-id="3227a-166">エッジサーバーの A/V Edge サービス</span><span class="sxs-lookup"><span data-stu-id="3227a-166">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3227a-167">Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必須</span><span class="sxs-lookup"><span data-stu-id="3227a-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3227a-168">A/V/RTP/59,999</span><span class="sxs-lookup"><span data-stu-id="3227a-168">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="3227a-169">任意</span><span class="sxs-lookup"><span data-stu-id="3227a-169">Any</span></span></p></td>
<td><p><span data-ttu-id="3227a-170">エッジサーバーの A/V Edge サービス</span><span class="sxs-lookup"><span data-stu-id="3227a-170">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3227a-171">Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必須</span><span class="sxs-lookup"><span data-stu-id="3227a-171">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3227a-172">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="3227a-172">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="3227a-173">エッジサーバーの A/V Edge サービス</span><span class="sxs-lookup"><span data-stu-id="3227a-173">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3227a-174">任意</span><span class="sxs-lookup"><span data-stu-id="3227a-174">Any</span></span></p></td>
<td><p><span data-ttu-id="3227a-175">3478送信は、Lync Server が通信するエッジサーバーのバージョンと、エッジサーバーからエッジサーバーへのメディアトラフィックも確認するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="3227a-175">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="3227a-176">Lync Server 2010、Windows Live Messenger、Office Communications Server 2007 R2 とのフェデレーション、および複数のエッジプールが会社内に展開されている場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="3227a-176">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3227a-177">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="3227a-177">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="3227a-178">任意</span><span class="sxs-lookup"><span data-stu-id="3227a-178">Any</span></span></p></td>
<td><p><span data-ttu-id="3227a-179">エッジサーバーの A/V Edge サービス</span><span class="sxs-lookup"><span data-stu-id="3227a-179">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3227a-180">UDP/3478 経由の候補のネゴシエーションをオフ/オンにする</span><span class="sxs-lookup"><span data-stu-id="3227a-180">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3227a-181">A/V/STUN、MSTURN/443</span><span class="sxs-lookup"><span data-stu-id="3227a-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="3227a-182">任意</span><span class="sxs-lookup"><span data-stu-id="3227a-182">Any</span></span></p></td>
<td><p><span data-ttu-id="3227a-183">エッジサーバーの A/V Edge サービス</span><span class="sxs-lookup"><span data-stu-id="3227a-183">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3227a-184">TCP/443 経由での候補のネゴシエーションをオフ/オンにする</span><span class="sxs-lookup"><span data-stu-id="3227a-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3227a-185">A/V/STUN、MSTURN/443</span><span class="sxs-lookup"><span data-stu-id="3227a-185">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="3227a-186">エッジサーバーの A/V Edge サービス</span><span class="sxs-lookup"><span data-stu-id="3227a-186">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3227a-187">任意</span><span class="sxs-lookup"><span data-stu-id="3227a-187">Any</span></span></p></td>
<td><p><span data-ttu-id="3227a-188">TCP/443 経由での候補のネゴシエーションをオフ/オンにする</span><span class="sxs-lookup"><span data-stu-id="3227a-188">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="3227a-189">拡大縮小された統合エッジのファイアウォールの概要: 内部インターフェイス–ノード1とノード 2 (例) のプライベート IP アドレスを使った DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="3227a-189">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3227a-190">Protocol/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="3227a-190">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="3227a-191">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="3227a-191">Source IP address</span></span></th>
<th><span data-ttu-id="3227a-192">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="3227a-192">Destination IP address</span></span></th>
<th><span data-ttu-id="3227a-193">コメント</span><span class="sxs-lookup"><span data-stu-id="3227a-193">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3227a-194">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="3227a-194">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="3227a-195">Any (フロントエンドサーバーアドレスとして定義可能、または XMPP ゲートウェイサービスを実行するフロントエンドプール IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="3227a-195">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="3227a-196">エッジサーバーの内部インターフェイス IP アドレス</span><span class="sxs-lookup"><span data-stu-id="3227a-196">Edge Server internal interface IP address</span></span></p></td>
<td><p><span data-ttu-id="3227a-197">フロントエンドサーバーまたはフロントエンドプールで実行されている XMPP ゲートウェイサービスからの送信 XMPP トラフィック</span><span class="sxs-lookup"><span data-stu-id="3227a-197">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3227a-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="3227a-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3227a-199">Any (ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバー、フロントエンドプールの IP アドレスとして定義できます)</span><span class="sxs-lookup"><span data-stu-id="3227a-199">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="3227a-200">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3227a-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3227a-201">送信 SIP トラフィック (ディレクター、ディレクタープール IP アドレス、フロントエンドサーバーまたはフロントエンドプールの IP アドレス) からエッジサーバーの内部インターフェイスへ</span><span class="sxs-lookup"><span data-stu-id="3227a-201">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3227a-202">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="3227a-202">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3227a-203">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3227a-203">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3227a-204">Any (ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバー、フロントエンドプールの IP アドレスとして定義できます)</span><span class="sxs-lookup"><span data-stu-id="3227a-204">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="3227a-205">エッジサーバーの内部インターフェイスから受信 SIP トラフィック (ディレクター、ディレクタープール IP アドレス、フロントエンドサーバー、またはフロントエンドプールの IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="3227a-205">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3227a-206">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="3227a-206">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="3227a-207">Any (フロントエンドサーバーの IP アドレス、またはフロントエンドプールの各フロントエンドサーバー IP アドレスとして定義できます)</span><span class="sxs-lookup"><span data-stu-id="3227a-207">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="3227a-208">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3227a-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3227a-209">フロントエンドサーバーからの Web 会議トラフィック、またはプール内の各フロントエンドサーバーから Edge Server の内部インターフェイスへの Web 会議トラフィック</span><span class="sxs-lookup"><span data-stu-id="3227a-209">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3227a-210">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="3227a-210">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="3227a-211">Any (フロントエンドサーバーの IP アドレス、またはこのエッジサーバーを使用している Survivable Branch Appliance または Survivable ブランチサーバー) として定義することができます。</span><span class="sxs-lookup"><span data-stu-id="3227a-211">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="3227a-212">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3227a-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3227a-213">このエッジサーバーを使用して、フロントエンドサーバーまたはフロントエンドプールの IP アドレスまたは Survivable Branch Appliance または Survivable ブランチサーバーからの、A/V ユーザー (A/V 認証サービス) の認証</span><span class="sxs-lookup"><span data-stu-id="3227a-213">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3227a-214">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="3227a-214">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="3227a-215">任意</span><span class="sxs-lookup"><span data-stu-id="3227a-215">Any</span></span></p></td>
<td><p><span data-ttu-id="3227a-216">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3227a-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3227a-217">内部と外部のユーザー、Survivable Branch Appliance または Survivable ブランチサーバー間の A/V メディア転送の優先パス</span><span class="sxs-lookup"><span data-stu-id="3227a-217">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3227a-218">STUN/MSTURN/443</span><span class="sxs-lookup"><span data-stu-id="3227a-218">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="3227a-219">任意</span><span class="sxs-lookup"><span data-stu-id="3227a-219">Any</span></span></p></td>
<td><p><span data-ttu-id="3227a-220">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3227a-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3227a-221">内部と外部のユーザーとの間でのメディア転送のフォールバックパス Survivable Branch Appliance または Survivable Branch Server (UDP 通信が確立できない場合は、TCP を使ってファイル転送とデスクトップ共有を行う)</span><span class="sxs-lookup"><span data-stu-id="3227a-221">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3227a-222">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="3227a-222">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="3227a-223">Any (任意) (フロントエンドサーバーの IP アドレス、または全体管理ストアを保持するプールとして定義できます)</span><span class="sxs-lookup"><span data-stu-id="3227a-223">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="3227a-224">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3227a-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3227a-225">中央管理ストアからエッジサーバーへの変更のレプリケーション</span><span class="sxs-lookup"><span data-stu-id="3227a-225">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3227a-226">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="3227a-226">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="3227a-227">任意</span><span class="sxs-lookup"><span data-stu-id="3227a-227">Any</span></span></p></td>
<td><p><span data-ttu-id="3227a-228">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3227a-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3227a-229">Lync Server 管理シェルと一元ログサービスコマンドレットを使用した一元管理サービスコントローラー、ClsController コマンドライン (ClsController) またはエージェント (Clscontroller .exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="3227a-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3227a-230">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="3227a-230">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="3227a-231">任意</span><span class="sxs-lookup"><span data-stu-id="3227a-231">Any</span></span></p></td>
<td><p><span data-ttu-id="3227a-232">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3227a-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3227a-233">Lync Server 管理シェルと一元ログサービスコマンドレットを使用した一元管理サービスコントローラー、ClsController コマンドライン (ClsController) またはエージェント (Clscontroller .exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="3227a-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3227a-234">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="3227a-234">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="3227a-235">任意</span><span class="sxs-lookup"><span data-stu-id="3227a-235">Any</span></span></p></td>
<td><p><span data-ttu-id="3227a-236">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3227a-236">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3227a-237">Lync Server 管理シェルと一元ログサービスコマンドレットを使用した一元管理サービスコントローラー、ClsController コマンドライン (ClsController) またはエージェント (Clscontroller .exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="3227a-237">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="3227a-238">フェデレーションのためのファイアウォールの概要</span><span class="sxs-lookup"><span data-stu-id="3227a-238">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3227a-239">Role/Protocol/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="3227a-239">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="3227a-240">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="3227a-240">Source IP address</span></span></th>
<th><span data-ttu-id="3227a-241">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="3227a-241">Destination IP address</span></span></th>
<th><span data-ttu-id="3227a-242">メモ</span><span class="sxs-lookup"><span data-stu-id="3227a-242">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3227a-243">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="3227a-243">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3227a-244">アクセスエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="3227a-244">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3227a-245">任意</span><span class="sxs-lookup"><span data-stu-id="3227a-245">Any</span></span></p></td>
<td><p><span data-ttu-id="3227a-246">SIP を使用するフェデレーションおよびパブリック IM 接続の場合</span><span class="sxs-lookup"><span data-stu-id="3227a-246">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="3227a-247">ファイアウォールの概要–パブリックインスタントメッセージング接続</span><span class="sxs-lookup"><span data-stu-id="3227a-247">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3227a-248">Role/Protocol/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="3227a-248">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="3227a-249">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="3227a-249">Source IP address</span></span></th>
<th><span data-ttu-id="3227a-250">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="3227a-250">Destination IP address</span></span></th>
<th><span data-ttu-id="3227a-251">メモ</span><span class="sxs-lookup"><span data-stu-id="3227a-251">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3227a-252">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="3227a-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3227a-253">パブリック IM 接続パートナー</span><span class="sxs-lookup"><span data-stu-id="3227a-253">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="3227a-254">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="3227a-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="3227a-255">SIP を使用するフェデレーションおよびパブリック IM 接続の場合</span><span class="sxs-lookup"><span data-stu-id="3227a-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3227a-256">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="3227a-256">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3227a-257">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="3227a-257">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="3227a-258">パブリック IM 接続パートナー</span><span class="sxs-lookup"><span data-stu-id="3227a-258">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="3227a-259">SIP を使用するフェデレーションおよびパブリック IM 接続の場合</span><span class="sxs-lookup"><span data-stu-id="3227a-259">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3227a-260">アクセス/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="3227a-260">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="3227a-261">クライアント</span><span class="sxs-lookup"><span data-stu-id="3227a-261">Clients</span></span></p></td>
<td><p><span data-ttu-id="3227a-262">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="3227a-262">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="3227a-263">外部ユーザーアクセスのクライアントツーサーバー SIP トラフィック</span><span class="sxs-lookup"><span data-stu-id="3227a-263">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3227a-264">A/V/RTP/59,999</span><span class="sxs-lookup"><span data-stu-id="3227a-264">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="3227a-265">エッジサーバーの A/V Edge サービス</span><span class="sxs-lookup"><span data-stu-id="3227a-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3227a-266">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="3227a-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="3227a-267">パブリック IM 接続が構成されている場合、Windows Live Messenger でのセッションに使用されます。</span><span class="sxs-lookup"><span data-stu-id="3227a-267">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3227a-268">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="3227a-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="3227a-269">エッジサーバーの A/V Edge サービス</span><span class="sxs-lookup"><span data-stu-id="3227a-269">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3227a-270">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="3227a-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="3227a-271">Windows Live Messenger とのパブリック IM 接続に必要</span><span class="sxs-lookup"><span data-stu-id="3227a-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3227a-272">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="3227a-272">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="3227a-273">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="3227a-273">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="3227a-274">エッジサーバーの A/V Edge サービス</span><span class="sxs-lookup"><span data-stu-id="3227a-274">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3227a-275">Windows Live Messenger とのパブリック IM 接続に必要</span><span class="sxs-lookup"><span data-stu-id="3227a-275">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="3227a-276">拡張メッセージングとプレゼンスプロトコルのファイアウォールの概要</span><span class="sxs-lookup"><span data-stu-id="3227a-276">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3227a-277">Protocol/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="3227a-277">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="3227a-278">ソース (IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="3227a-278">Source (IP address)</span></span></th>
<th><span data-ttu-id="3227a-279">宛先 (IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="3227a-279">Destination (IP address)</span></span></th>
<th><span data-ttu-id="3227a-280">コメント</span><span class="sxs-lookup"><span data-stu-id="3227a-280">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3227a-281">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="3227a-281">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="3227a-282">任意</span><span class="sxs-lookup"><span data-stu-id="3227a-282">Any</span></span></p></td>
<td><p><span data-ttu-id="3227a-283">エッジサーバーアクセスエッジサービスインターフェイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="3227a-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="3227a-284">XMPP 向けの標準的なサーバー間通信ポート。</span><span class="sxs-lookup"><span data-stu-id="3227a-284">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="3227a-285">フェデレーションされた XMPP パートナーからエッジサーバーの XMPP プロキシへの通信を許可します。</span><span class="sxs-lookup"><span data-stu-id="3227a-285">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3227a-286">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="3227a-286">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="3227a-287">エッジサーバーアクセスエッジサービスインターフェイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="3227a-287">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="3227a-288">任意</span><span class="sxs-lookup"><span data-stu-id="3227a-288">Any</span></span></p></td>
<td><p><span data-ttu-id="3227a-289">XMPP 向けの標準的なサーバー間通信ポート。</span><span class="sxs-lookup"><span data-stu-id="3227a-289">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="3227a-290">エッジサーバーの XMPP プロキシからフェデレーションされた XMPP パートナーへの通信を許可します。</span><span class="sxs-lookup"><span data-stu-id="3227a-290">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3227a-291">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="3227a-291">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="3227a-292">任意</span><span class="sxs-lookup"><span data-stu-id="3227a-292">Any</span></span></p></td>
<td><p><span data-ttu-id="3227a-293">各内部エッジサーバーインターフェイス IP</span><span class="sxs-lookup"><span data-stu-id="3227a-293">Each internal Edge Server interface IP</span></span></p></td>
<td><p><span data-ttu-id="3227a-294">フロントエンドサーバーまたはフロントエンドプールの XMPP ゲートウェイから Edge Server 内部 IP アドレスまたは各エッジプールメンバーの内部 IP アドレスへの内部の XMPP トラフィック</span><span class="sxs-lookup"><span data-stu-id="3227a-294">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

