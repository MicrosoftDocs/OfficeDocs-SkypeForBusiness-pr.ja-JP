---
title: 'Lync Server 2013: ポートの概要 - 拡張統合エッジ、NAT によるプライベート IP アドレスを使用した DNS 負荷分散'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: a296c2af-54d4-4b4f-9795-9191baf688cb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412756(v=OCS.15)
ms:contentKeyID: 48184955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20071cba55551a42ea6406723bb1f9ed55853afa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725047"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="a106c-102">ポートの概要 - Lync Server 2013 における拡張統合エッジ、NAT によるプライベート IP アドレスを使用した DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="a106c-102">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a106c-103">_**最終更新日:** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="a106c-103">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="a106c-104">このシナリオアーキテクチャで説明されている Lync Server 2013 のエッジサーバー機能は、Lync Server 2010 で実装されたものとよく似ています。</span><span class="sxs-lookup"><span data-stu-id="a106c-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="a106c-105">最も顕著な追加機能は、拡張メッセージングとプレゼンスプロトコル (XMPP) の TCP エントリのポート**5269**です。</span><span class="sxs-lookup"><span data-stu-id="a106c-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="a106c-106">Lync Server 2013 では、必要に応じて、microsoft Edge サーバーまたはエッジプールに XMPP プロキシを展開し、フロントエンドサーバーまたはフロントエンドプールに XMPP ゲートウェイサーバーを配置します。</span><span class="sxs-lookup"><span data-stu-id="a106c-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="a106c-107">IPv4 に加えて、エッジサーバーは IPv6 をサポートするようになりました。</span><span class="sxs-lookup"><span data-stu-id="a106c-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="a106c-108">わかりやすくするために、シナリオでは IPv4 のみが使用されます。</span><span class="sxs-lookup"><span data-stu-id="a106c-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="a106c-109">**NAT を使用する統合エッジ用のエンタープライズ境界ネットワークとプライベート IP アドレス**</span><span class="sxs-lookup"><span data-stu-id="a106c-109">**Enterprise perimeter network for scaled consolidated edge with private IP addresses using NAT**</span></span>

<span data-ttu-id="a106c-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="a106c-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="a106c-111">ポートとプロトコルの詳細</span><span class="sxs-lookup"><span data-stu-id="a106c-111">Port and Protocol Details</span></span>

<span data-ttu-id="a106c-112">外部アクセスを提供する機能をサポートするために必要なポートのみを開くことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a106c-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="a106c-113">エッジサービスに対してリモートアクセスを使用するには、受信/送信エッジトラフィックの図に示すように、SIP トラフィックが双方向に流れるようにすることが必須です。</span><span class="sxs-lookup"><span data-stu-id="a106c-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="a106c-114">別の方法として、アクセスエッジサービスとの間の SIP メッセージングは、インスタントメッセージング (IM)、プレゼンス、web 会議、音声/ビデオ (A/V)、およびフェデレーションに関連しています。</span><span class="sxs-lookup"><span data-stu-id="a106c-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="a106c-115">拡張統合エッジの場合のファイアウォールの概要、NAT を使用したプライベート IP アドレスを使った DNS 負荷分散: ノード1とノード 2 (例)</span><span class="sxs-lookup"><span data-stu-id="a106c-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a106c-116">Role/Protocol/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="a106c-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a106c-117">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="a106c-117">Source IP address</span></span></th>
<th><span data-ttu-id="a106c-118">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="a106c-118">Destination IP address</span></span></th>
<th><span data-ttu-id="a106c-119">メモ</span><span class="sxs-lookup"><span data-stu-id="a106c-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a106c-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="a106c-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="a106c-121">任意</span><span class="sxs-lookup"><span data-stu-id="a106c-121">Any</span></span></p></td>
<td><p><span data-ttu-id="a106c-122">XMPP プロキシサービス (アクセスエッジサービスで IP アドレスを共有)</span><span class="sxs-lookup"><span data-stu-id="a106c-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="a106c-123">XMPP プロキシサービスは、定義された XMPP フェデレーションの XMPP 連絡先からのトラフィックを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="a106c-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a106c-124">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="a106c-124">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="a106c-125">XMPP プロキシサービス (アクセスエッジサービスで IP アドレスを共有)</span><span class="sxs-lookup"><span data-stu-id="a106c-125">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="a106c-126">任意</span><span class="sxs-lookup"><span data-stu-id="a106c-126">Any</span></span></p></td>
<td><p><span data-ttu-id="a106c-127">XMPP プロキシサービスは、定義された XMPP フェデレーションの XMPP の連絡先にトラフィックを送信します。</span><span class="sxs-lookup"><span data-stu-id="a106c-127">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a106c-128">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="a106c-128">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="a106c-129">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="a106c-129">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="a106c-130">任意</span><span class="sxs-lookup"><span data-stu-id="a106c-130">Any</span></span></p></td>
<td><p><span data-ttu-id="a106c-131">証明書の失効/CRL の確認と取得</span><span class="sxs-lookup"><span data-stu-id="a106c-131">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a106c-132">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="a106c-132">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="a106c-133">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="a106c-133">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="a106c-134">任意</span><span class="sxs-lookup"><span data-stu-id="a106c-134">Any</span></span></p></td>
<td><p><span data-ttu-id="a106c-135">TCP 経由の DNS クエリ</span><span class="sxs-lookup"><span data-stu-id="a106c-135">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a106c-136">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="a106c-136">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="a106c-137">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="a106c-137">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="a106c-138">任意</span><span class="sxs-lookup"><span data-stu-id="a106c-138">Any</span></span></p></td>
<td><p><span data-ttu-id="a106c-139">UDP 経由の DNS クエリ</span><span class="sxs-lookup"><span data-stu-id="a106c-139">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a106c-140">アクセス/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a106c-140">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a106c-141">任意</span><span class="sxs-lookup"><span data-stu-id="a106c-141">Any</span></span></p></td>
<td><p><span data-ttu-id="a106c-142">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="a106c-142">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="a106c-143">外部ユーザーアクセスのクライアントツーサーバー SIP トラフィック</span><span class="sxs-lookup"><span data-stu-id="a106c-143">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a106c-144">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a106c-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a106c-145">任意</span><span class="sxs-lookup"><span data-stu-id="a106c-145">Any</span></span></p></td>
<td><p><span data-ttu-id="a106c-146">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="a106c-146">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="a106c-147">SIP を使用するフェデレーションおよびパブリック IM 接続の場合</span><span class="sxs-lookup"><span data-stu-id="a106c-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a106c-148">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a106c-148">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a106c-149">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="a106c-149">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="a106c-150">任意</span><span class="sxs-lookup"><span data-stu-id="a106c-150">Any</span></span></p></td>
<td><p><span data-ttu-id="a106c-151">SIP を使用するフェデレーションおよびパブリック IM 接続の場合</span><span class="sxs-lookup"><span data-stu-id="a106c-151">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a106c-152">Web 会議/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a106c-152">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a106c-153">任意</span><span class="sxs-lookup"><span data-stu-id="a106c-153">Any</span></span></p></td>
<td><p><span data-ttu-id="a106c-154">エッジサーバー Web 会議エッジサービス</span><span class="sxs-lookup"><span data-stu-id="a106c-154">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="a106c-155">Web 会議メディア</span><span class="sxs-lookup"><span data-stu-id="a106c-155">Web Conferencing media</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a106c-156">A/V/RTP/59,999</span><span class="sxs-lookup"><span data-stu-id="a106c-156">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="a106c-157">エッジサーバーの A/V Edge サービス</span><span class="sxs-lookup"><span data-stu-id="a106c-157">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a106c-158">任意</span><span class="sxs-lookup"><span data-stu-id="a106c-158">Any</span></span></p></td>
<td><p><span data-ttu-id="a106c-159">Office Communications Server 2007、Office Communications Server 2007 R2、Lync Server 2010、および Lync Server 2013 を実行しているパートナーとのフェデレーションに必要。</span><span class="sxs-lookup"><span data-stu-id="a106c-159">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a106c-160">A/V/RTP/59,999</span><span class="sxs-lookup"><span data-stu-id="a106c-160">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="a106c-161">エッジサーバーの A/V Edge サービス</span><span class="sxs-lookup"><span data-stu-id="a106c-161">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a106c-162">任意</span><span class="sxs-lookup"><span data-stu-id="a106c-162">Any</span></span></p></td>
<td><p><span data-ttu-id="a106c-163">Office Communications Server 2007 を実行しているパートナーとのフェデレーションの場合のみ必須です。</span><span class="sxs-lookup"><span data-stu-id="a106c-163">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a106c-164">A/V/RTP/59,999</span><span class="sxs-lookup"><span data-stu-id="a106c-164">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="a106c-165">任意</span><span class="sxs-lookup"><span data-stu-id="a106c-165">Any</span></span></p></td>
<td><p><span data-ttu-id="a106c-166">エッジサーバーの A/V Edge サービス</span><span class="sxs-lookup"><span data-stu-id="a106c-166">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a106c-167">Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必須</span><span class="sxs-lookup"><span data-stu-id="a106c-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a106c-168">A/V/RTP/59,999</span><span class="sxs-lookup"><span data-stu-id="a106c-168">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="a106c-169">任意</span><span class="sxs-lookup"><span data-stu-id="a106c-169">Any</span></span></p></td>
<td><p><span data-ttu-id="a106c-170">エッジサーバーの A/V Edge サービス</span><span class="sxs-lookup"><span data-stu-id="a106c-170">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a106c-171">Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必須</span><span class="sxs-lookup"><span data-stu-id="a106c-171">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a106c-172">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a106c-172">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a106c-173">エッジサーバーの A/V Edge サービス</span><span class="sxs-lookup"><span data-stu-id="a106c-173">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a106c-174">任意</span><span class="sxs-lookup"><span data-stu-id="a106c-174">Any</span></span></p></td>
<td><p><span data-ttu-id="a106c-175">3478送信は、Lync Server が通信するエッジサーバーのバージョンと、エッジサーバーからエッジサーバーへのメディアトラフィックも確認するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="a106c-175">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="a106c-176">Lync Server 2010、Windows Live Messenger、Office Communications Server 2007 R2 とのフェデレーション、および複数のエッジプールが会社内に展開されている場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="a106c-176">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a106c-177">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a106c-177">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a106c-178">任意</span><span class="sxs-lookup"><span data-stu-id="a106c-178">Any</span></span></p></td>
<td><p><span data-ttu-id="a106c-179">エッジサーバーの A/V Edge サービス</span><span class="sxs-lookup"><span data-stu-id="a106c-179">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a106c-180">UDP/3478 経由の候補のネゴシエーションをオフ/オンにする</span><span class="sxs-lookup"><span data-stu-id="a106c-180">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a106c-181">A/V/STUN、MSTURN/443</span><span class="sxs-lookup"><span data-stu-id="a106c-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a106c-182">任意</span><span class="sxs-lookup"><span data-stu-id="a106c-182">Any</span></span></p></td>
<td><p><span data-ttu-id="a106c-183">エッジサーバーの A/V Edge サービス</span><span class="sxs-lookup"><span data-stu-id="a106c-183">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a106c-184">TCP/443 経由での候補のネゴシエーションをオフ/オンにする</span><span class="sxs-lookup"><span data-stu-id="a106c-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a106c-185">A/V/STUN、MSTURN/443</span><span class="sxs-lookup"><span data-stu-id="a106c-185">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a106c-186">エッジサーバーの A/V Edge サービス</span><span class="sxs-lookup"><span data-stu-id="a106c-186">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a106c-187">任意</span><span class="sxs-lookup"><span data-stu-id="a106c-187">Any</span></span></p></td>
<td><p><span data-ttu-id="a106c-188">TCP/443 経由での候補のネゴシエーションをオフ/オンにする</span><span class="sxs-lookup"><span data-stu-id="a106c-188">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="a106c-189">拡大縮小された統合エッジのファイアウォールの概要: 内部インターフェイス–ノード1とノード 2 (例) のプライベート IP アドレスを使った DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="a106c-189">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a106c-190">Protocol/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="a106c-190">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a106c-191">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="a106c-191">Source IP address</span></span></th>
<th><span data-ttu-id="a106c-192">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="a106c-192">Destination IP address</span></span></th>
<th><span data-ttu-id="a106c-193">コメント</span><span class="sxs-lookup"><span data-stu-id="a106c-193">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a106c-194">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="a106c-194">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="a106c-195">Any (フロントエンドサーバーアドレスとして定義可能、または XMPP ゲートウェイサービスを実行するフロントエンドプール IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="a106c-195">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="a106c-196">エッジサーバーの内部インターフェイス IP アドレス</span><span class="sxs-lookup"><span data-stu-id="a106c-196">Edge Server internal interface IP address</span></span></p></td>
<td><p><span data-ttu-id="a106c-197">フロントエンドサーバーまたはフロントエンドプールで実行されている XMPP ゲートウェイサービスからの送信 XMPP トラフィック</span><span class="sxs-lookup"><span data-stu-id="a106c-197">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a106c-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a106c-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a106c-199">Any (ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバー、フロントエンドプールの IP アドレスとして定義できます)</span><span class="sxs-lookup"><span data-stu-id="a106c-199">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="a106c-200">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a106c-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a106c-201">送信 SIP トラフィック (ディレクター、ディレクタープール IP アドレス、フロントエンドサーバーまたはフロントエンドプールの IP アドレス) からエッジサーバーの内部インターフェイスへ</span><span class="sxs-lookup"><span data-stu-id="a106c-201">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a106c-202">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a106c-202">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a106c-203">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a106c-203">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a106c-204">Any (ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバー、フロントエンドプールの IP アドレスとして定義できます)</span><span class="sxs-lookup"><span data-stu-id="a106c-204">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="a106c-205">エッジサーバーの内部インターフェイスから受信 SIP トラフィック (ディレクター、ディレクタープール IP アドレス、フロントエンドサーバー、またはフロントエンドプールの IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="a106c-205">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a106c-206">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="a106c-206">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="a106c-207">Any (フロントエンドサーバーの IP アドレス、またはフロントエンドプールの各フロントエンドサーバー IP アドレスとして定義できます)</span><span class="sxs-lookup"><span data-stu-id="a106c-207">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="a106c-208">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a106c-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a106c-209">フロントエンドサーバーからの Web 会議トラフィック、またはプール内の各フロントエンドサーバーから Edge Server の内部インターフェイスへの Web 会議トラフィック</span><span class="sxs-lookup"><span data-stu-id="a106c-209">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a106c-210">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="a106c-210">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="a106c-211">Any (フロントエンドサーバーの IP アドレス、またはこのエッジサーバーを使用している Survivable Branch Appliance または Survivable ブランチサーバー) として定義することができます。</span><span class="sxs-lookup"><span data-stu-id="a106c-211">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="a106c-212">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a106c-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a106c-213">このエッジサーバーを使用して、フロントエンドサーバーまたはフロントエンドプールの IP アドレスまたは Survivable Branch Appliance または Survivable ブランチサーバーからの、A/V ユーザー (A/V 認証サービス) の認証</span><span class="sxs-lookup"><span data-stu-id="a106c-213">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a106c-214">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a106c-214">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a106c-215">任意</span><span class="sxs-lookup"><span data-stu-id="a106c-215">Any</span></span></p></td>
<td><p><span data-ttu-id="a106c-216">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a106c-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a106c-217">内部と外部のユーザー、Survivable Branch Appliance または Survivable ブランチサーバー間の A/V メディア転送の優先パス</span><span class="sxs-lookup"><span data-stu-id="a106c-217">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a106c-218">STUN/MSTURN/443</span><span class="sxs-lookup"><span data-stu-id="a106c-218">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a106c-219">任意</span><span class="sxs-lookup"><span data-stu-id="a106c-219">Any</span></span></p></td>
<td><p><span data-ttu-id="a106c-220">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a106c-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a106c-221">内部と外部のユーザーとの間でのメディア転送のフォールバックパス Survivable Branch Appliance または Survivable Branch Server (UDP 通信が確立できない場合は、TCP を使ってファイル転送とデスクトップ共有を行う)</span><span class="sxs-lookup"><span data-stu-id="a106c-221">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a106c-222">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="a106c-222">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="a106c-223">Any (任意) (フロントエンドサーバーの IP アドレス、または全体管理ストアを保持するプールとして定義できます)</span><span class="sxs-lookup"><span data-stu-id="a106c-223">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="a106c-224">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a106c-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a106c-225">中央管理ストアからエッジサーバーへの変更のレプリケーション</span><span class="sxs-lookup"><span data-stu-id="a106c-225">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a106c-226">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="a106c-226">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="a106c-227">任意</span><span class="sxs-lookup"><span data-stu-id="a106c-227">Any</span></span></p></td>
<td><p><span data-ttu-id="a106c-228">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a106c-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a106c-229">Lync Server 管理シェルと一元ログサービスコマンドレットを使用した一元管理サービスコントローラー、ClsController コマンドライン (ClsController) またはエージェント (Clscontroller .exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="a106c-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a106c-230">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="a106c-230">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="a106c-231">任意</span><span class="sxs-lookup"><span data-stu-id="a106c-231">Any</span></span></p></td>
<td><p><span data-ttu-id="a106c-232">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a106c-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a106c-233">Lync Server 管理シェルと一元ログサービスコマンドレットを使用した一元管理サービスコントローラー、ClsController コマンドライン (ClsController) またはエージェント (Clscontroller .exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="a106c-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a106c-234">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="a106c-234">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="a106c-235">任意</span><span class="sxs-lookup"><span data-stu-id="a106c-235">Any</span></span></p></td>
<td><p><span data-ttu-id="a106c-236">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a106c-236">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a106c-237">Lync Server 管理シェルと一元ログサービスコマンドレットを使用した一元管理サービスコントローラー、ClsController コマンドライン (ClsController) またはエージェント (Clscontroller .exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="a106c-237">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="a106c-238">フェデレーションのためのファイアウォールの概要</span><span class="sxs-lookup"><span data-stu-id="a106c-238">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a106c-239">Role/Protocol/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="a106c-239">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a106c-240">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="a106c-240">Source IP address</span></span></th>
<th><span data-ttu-id="a106c-241">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="a106c-241">Destination IP address</span></span></th>
<th><span data-ttu-id="a106c-242">メモ</span><span class="sxs-lookup"><span data-stu-id="a106c-242">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a106c-243">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a106c-243">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a106c-244">アクセスエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="a106c-244">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a106c-245">任意</span><span class="sxs-lookup"><span data-stu-id="a106c-245">Any</span></span></p></td>
<td><p><span data-ttu-id="a106c-246">SIP を使用するフェデレーションおよびパブリック IM 接続の場合</span><span class="sxs-lookup"><span data-stu-id="a106c-246">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="a106c-247">ファイアウォールの概要–パブリックインスタントメッセージング接続</span><span class="sxs-lookup"><span data-stu-id="a106c-247">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a106c-248">Role/Protocol/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="a106c-248">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a106c-249">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="a106c-249">Source IP address</span></span></th>
<th><span data-ttu-id="a106c-250">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="a106c-250">Destination IP address</span></span></th>
<th><span data-ttu-id="a106c-251">メモ</span><span class="sxs-lookup"><span data-stu-id="a106c-251">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a106c-252">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a106c-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a106c-253">パブリック IM 接続パートナー</span><span class="sxs-lookup"><span data-stu-id="a106c-253">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="a106c-254">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="a106c-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="a106c-255">SIP を使用するフェデレーションおよびパブリック IM 接続の場合</span><span class="sxs-lookup"><span data-stu-id="a106c-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a106c-256">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a106c-256">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a106c-257">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="a106c-257">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="a106c-258">パブリック IM 接続パートナー</span><span class="sxs-lookup"><span data-stu-id="a106c-258">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="a106c-259">SIP を使用するフェデレーションおよびパブリック IM 接続の場合</span><span class="sxs-lookup"><span data-stu-id="a106c-259">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a106c-260">アクセス/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a106c-260">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a106c-261">クライアント</span><span class="sxs-lookup"><span data-stu-id="a106c-261">Clients</span></span></p></td>
<td><p><span data-ttu-id="a106c-262">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="a106c-262">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="a106c-263">外部ユーザーアクセスのクライアントツーサーバー SIP トラフィック</span><span class="sxs-lookup"><span data-stu-id="a106c-263">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a106c-264">A/V/RTP/59,999</span><span class="sxs-lookup"><span data-stu-id="a106c-264">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="a106c-265">エッジサーバーの A/V Edge サービス</span><span class="sxs-lookup"><span data-stu-id="a106c-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a106c-266">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="a106c-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="a106c-267">パブリック IM 接続が構成されている場合、Windows Live Messenger でのセッションに使用されます。</span><span class="sxs-lookup"><span data-stu-id="a106c-267">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a106c-268">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a106c-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a106c-269">エッジサーバーの A/V Edge サービス</span><span class="sxs-lookup"><span data-stu-id="a106c-269">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a106c-270">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="a106c-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="a106c-271">Windows Live Messenger とのパブリック IM 接続に必要</span><span class="sxs-lookup"><span data-stu-id="a106c-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a106c-272">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a106c-272">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a106c-273">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="a106c-273">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="a106c-274">エッジサーバーの A/V Edge サービス</span><span class="sxs-lookup"><span data-stu-id="a106c-274">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a106c-275">Windows Live Messenger とのパブリック IM 接続に必要</span><span class="sxs-lookup"><span data-stu-id="a106c-275">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="a106c-276">拡張メッセージングとプレゼンスプロトコルのファイアウォールの概要</span><span class="sxs-lookup"><span data-stu-id="a106c-276">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a106c-277">Protocol/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="a106c-277">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a106c-278">ソース (IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="a106c-278">Source (IP address)</span></span></th>
<th><span data-ttu-id="a106c-279">宛先 (IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="a106c-279">Destination (IP address)</span></span></th>
<th><span data-ttu-id="a106c-280">コメント</span><span class="sxs-lookup"><span data-stu-id="a106c-280">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a106c-281">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="a106c-281">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="a106c-282">任意</span><span class="sxs-lookup"><span data-stu-id="a106c-282">Any</span></span></p></td>
<td><p><span data-ttu-id="a106c-283">エッジサーバーアクセスエッジサービスインターフェイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="a106c-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="a106c-284">XMPP 向けの標準的なサーバー間通信ポート。</span><span class="sxs-lookup"><span data-stu-id="a106c-284">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="a106c-285">フェデレーションされた XMPP パートナーからエッジサーバーの XMPP プロキシへの通信を許可します。</span><span class="sxs-lookup"><span data-stu-id="a106c-285">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a106c-286">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="a106c-286">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="a106c-287">エッジサーバーアクセスエッジサービスインターフェイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="a106c-287">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="a106c-288">任意</span><span class="sxs-lookup"><span data-stu-id="a106c-288">Any</span></span></p></td>
<td><p><span data-ttu-id="a106c-289">XMPP 向けの標準的なサーバー間通信ポート。</span><span class="sxs-lookup"><span data-stu-id="a106c-289">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="a106c-290">エッジサーバーの XMPP プロキシからフェデレーションされた XMPP パートナーへの通信を許可します。</span><span class="sxs-lookup"><span data-stu-id="a106c-290">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a106c-291">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="a106c-291">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="a106c-292">任意</span><span class="sxs-lookup"><span data-stu-id="a106c-292">Any</span></span></p></td>
<td><p><span data-ttu-id="a106c-293">各内部エッジサーバーインターフェイス IP</span><span class="sxs-lookup"><span data-stu-id="a106c-293">Each internal Edge Server interface IP</span></span></p></td>
<td><p><span data-ttu-id="a106c-294">フロントエンドサーバーまたはフロントエンドプールの XMPP ゲートウェイから Edge Server 内部 IP アドレスまたは各エッジプールメンバーの内部 IP アドレスへの内部の XMPP トラフィック</span><span class="sxs-lookup"><span data-stu-id="a106c-294">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

