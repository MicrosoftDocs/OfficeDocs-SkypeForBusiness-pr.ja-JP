---
title: 'Lync Server 2013: ポートの概要-拡張統合エッジ、NAT を使用したプライベート IP アドレスを使用した DNS 負荷分散'
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
ms.openlocfilehash: ff1cb9d559d3d6824882a87aaa4d45ad7254c276
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534144"
---
# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="b94c9-102">ポートの概要-Lync Server 2013 での NAT を使用したプライベート IP アドレスを使用した拡張統合エッジ、DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="b94c9-102">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b94c9-103">_**トピックの最終更新日:** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="b94c9-103">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="b94c9-104">このシナリオアーキテクチャで説明されている Lync server 2013 のエッジサーバー機能は、Lync Server 2010 で実装されていたものとよく似ています。</span><span class="sxs-lookup"><span data-stu-id="b94c9-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="b94c9-105">最も目を引くのは、XMPP (Extensible Messaging and Presence Protocol) 用の ポート **5269/TCP** エントリが追加されたことです。</span><span class="sxs-lookup"><span data-stu-id="b94c9-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="b94c9-106">Lync Server 2013 は、フロントエンドサーバーまたはフロントエンドプールに、エッジサーバーまたはエッジプールおよび XMPP ゲートウェイサーバー上に XMPP プロキシを任意で展開します。</span><span class="sxs-lookup"><span data-stu-id="b94c9-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="b94c9-107">IPv4 に加えて、エッジサーバーは IPv6 をサポートするようになりました。</span><span class="sxs-lookup"><span data-stu-id="b94c9-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="b94c9-108">わかりやすいように、シナリオでは IPv4 のみを使用します。</span><span class="sxs-lookup"><span data-stu-id="b94c9-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="b94c9-109">**NAT を使用して拡張統合エッジとプライベート IP アドレスを使用するためのエンタープライズ境界ネットワーク**</span><span class="sxs-lookup"><span data-stu-id="b94c9-109">**Enterprise perimeter network for scaled consolidated edge with private IP addresses using NAT**</span></span>

<span data-ttu-id="b94c9-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="b94c9-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="b94c9-111">ポートとプロトコルの詳細</span><span class="sxs-lookup"><span data-stu-id="b94c9-111">Port and Protocol Details</span></span>

<span data-ttu-id="b94c9-112">外部アクセスを提供する機能のサポートに必要なポートのみを開くことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b94c9-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="b94c9-p103">エッジ サービスのリモート アクセスが機能するためには、受信/送信のエッジ トラフィックの図が示すように、SIP トラフィックの双方向通過が許可されていることが必須です。つまり、インスタント メッセージング (IM)、プレゼンス、Web 会議、音声ビデオ (A/V)、およびフェデレーションでは、アクセス エッジ サービスとの間で SIP メッセージングが実行されます。</span><span class="sxs-lookup"><span data-stu-id="b94c9-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="b94c9-115">拡張統合エッジ、NAT を使用したプライベート IP アドレスを使用した DNS 負荷分散のためのファイアウォールの概要: 外部インターフェイス–ノード1およびノード 2 (例)</span><span class="sxs-lookup"><span data-stu-id="b94c9-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b94c9-116">役割/プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="b94c9-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b94c9-117">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b94c9-117">Source IP address</span></span></th>
<th><span data-ttu-id="b94c9-118">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b94c9-118">Destination IP address</span></span></th>
<th><span data-ttu-id="b94c9-119">Notes</span><span class="sxs-lookup"><span data-stu-id="b94c9-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b94c9-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="b94c9-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="b94c9-121">任意</span><span class="sxs-lookup"><span data-stu-id="b94c9-121">Any</span></span></p></td>
<td><p><span data-ttu-id="b94c9-122">XMPP プロキシサービス (アクセスエッジサービスを使用して IP アドレスを共有)</span><span class="sxs-lookup"><span data-stu-id="b94c9-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="b94c9-123">XMPP プロキシ サービスは、定義された XMPP フェデレーションの XMPP コンタクトからトラフィックを受け付けます</span><span class="sxs-lookup"><span data-stu-id="b94c9-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b94c9-124">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="b94c9-124">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="b94c9-125">XMPP プロキシサービス (アクセスエッジサービスを使用して IP アドレスを共有)</span><span class="sxs-lookup"><span data-stu-id="b94c9-125">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="b94c9-126">任意</span><span class="sxs-lookup"><span data-stu-id="b94c9-126">Any</span></span></p></td>
<td><p><span data-ttu-id="b94c9-127">XMPP プロキシサービスは、定義された XMPP フェデレーションの XMPP 連絡先にトラフィックを送信します。</span><span class="sxs-lookup"><span data-stu-id="b94c9-127">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b94c9-128">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="b94c9-128">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="b94c9-129">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="b94c9-129">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b94c9-130">任意</span><span class="sxs-lookup"><span data-stu-id="b94c9-130">Any</span></span></p></td>
<td><p><span data-ttu-id="b94c9-131">証明書の失効/CRL のチェックおよび取得</span><span class="sxs-lookup"><span data-stu-id="b94c9-131">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b94c9-132">アクセス/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="b94c9-132">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="b94c9-133">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="b94c9-133">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b94c9-134">任意</span><span class="sxs-lookup"><span data-stu-id="b94c9-134">Any</span></span></p></td>
<td><p><span data-ttu-id="b94c9-135">TCP による DNS クエリ</span><span class="sxs-lookup"><span data-stu-id="b94c9-135">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b94c9-136">アクセス/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="b94c9-136">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="b94c9-137">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="b94c9-137">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b94c9-138">任意</span><span class="sxs-lookup"><span data-stu-id="b94c9-138">Any</span></span></p></td>
<td><p><span data-ttu-id="b94c9-139">UDP による DNS クエリ</span><span class="sxs-lookup"><span data-stu-id="b94c9-139">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b94c9-140">アクセス/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b94c9-140">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b94c9-141">任意</span><span class="sxs-lookup"><span data-stu-id="b94c9-141">Any</span></span></p></td>
<td><p><span data-ttu-id="b94c9-142">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="b94c9-142">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b94c9-143">外部ユーザー アクセス用のクライアントからサーバーへの SIP トラフィック</span><span class="sxs-lookup"><span data-stu-id="b94c9-143">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b94c9-144">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b94c9-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b94c9-145">任意</span><span class="sxs-lookup"><span data-stu-id="b94c9-145">Any</span></span></p></td>
<td><p><span data-ttu-id="b94c9-146">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="b94c9-146">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b94c9-147">SIP を使用したフェデレーションおよびパブリック IM 接続用</span><span class="sxs-lookup"><span data-stu-id="b94c9-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b94c9-148">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b94c9-148">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b94c9-149">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="b94c9-149">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b94c9-150">任意</span><span class="sxs-lookup"><span data-stu-id="b94c9-150">Any</span></span></p></td>
<td><p><span data-ttu-id="b94c9-151">SIP を使用したフェデレーションおよびパブリック IM 接続用</span><span class="sxs-lookup"><span data-stu-id="b94c9-151">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b94c9-152">Web 会議/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b94c9-152">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b94c9-153">任意</span><span class="sxs-lookup"><span data-stu-id="b94c9-153">Any</span></span></p></td>
<td><p><span data-ttu-id="b94c9-154">エッジサーバー Web 会議エッジサービス</span><span class="sxs-lookup"><span data-stu-id="b94c9-154">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="b94c9-155">Web 会議メディア</span><span class="sxs-lookup"><span data-stu-id="b94c9-155">Web Conferencing media</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b94c9-156">音声/V/RTP/TCP/50,000-59999</span><span class="sxs-lookup"><span data-stu-id="b94c9-156">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b94c9-157">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="b94c9-157">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b94c9-158">任意</span><span class="sxs-lookup"><span data-stu-id="b94c9-158">Any</span></span></p></td>
<td><p><span data-ttu-id="b94c9-159">Office Communications Server 2007、Office Communications Server 2007 R2、Lync Server 2010、Lync Server 2013 を実行しているパートナーとのフェデレーションに必要です。</span><span class="sxs-lookup"><span data-stu-id="b94c9-159">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b94c9-160">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="b94c9-160">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b94c9-161">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="b94c9-161">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b94c9-162">任意</span><span class="sxs-lookup"><span data-stu-id="b94c9-162">Any</span></span></p></td>
<td><p><span data-ttu-id="b94c9-163">Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必要。</span><span class="sxs-lookup"><span data-stu-id="b94c9-163">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b94c9-164">音声/V/RTP/TCP/50,000-59999</span><span class="sxs-lookup"><span data-stu-id="b94c9-164">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b94c9-165">任意</span><span class="sxs-lookup"><span data-stu-id="b94c9-165">Any</span></span></p></td>
<td><p><span data-ttu-id="b94c9-166">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="b94c9-166">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b94c9-167">Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必要</span><span class="sxs-lookup"><span data-stu-id="b94c9-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b94c9-168">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="b94c9-168">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b94c9-169">任意</span><span class="sxs-lookup"><span data-stu-id="b94c9-169">Any</span></span></p></td>
<td><p><span data-ttu-id="b94c9-170">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="b94c9-170">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b94c9-171">Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必要</span><span class="sxs-lookup"><span data-stu-id="b94c9-171">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b94c9-172">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b94c9-172">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b94c9-173">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="b94c9-173">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b94c9-174">任意</span><span class="sxs-lookup"><span data-stu-id="b94c9-174">Any</span></span></p></td>
<td><p><span data-ttu-id="b94c9-175">3478の送信は、Lync Server の通信相手であるエッジサーバーのバージョンと、エッジサーバー間のメディアトラフィックに使用されます。</span><span class="sxs-lookup"><span data-stu-id="b94c9-175">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="b94c9-176">Lync Server 2010、Windows Live Messenger、および Office Communications Server 2007 R2 とのフェデレーションに必要です。また、複数のエッジプールが会社内に展開されている場合も必須です。</span><span class="sxs-lookup"><span data-stu-id="b94c9-176">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b94c9-177">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b94c9-177">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b94c9-178">任意</span><span class="sxs-lookup"><span data-stu-id="b94c9-178">Any</span></span></p></td>
<td><p><span data-ttu-id="b94c9-179">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="b94c9-179">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b94c9-180">STUN/UDP による候補の TURN ネゴシエーション/3478</span><span class="sxs-lookup"><span data-stu-id="b94c9-180">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b94c9-181">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b94c9-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b94c9-182">任意</span><span class="sxs-lookup"><span data-stu-id="b94c9-182">Any</span></span></p></td>
<td><p><span data-ttu-id="b94c9-183">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="b94c9-183">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b94c9-184">STUN/TCP による候補の TURN ネゴシエーション/443</span><span class="sxs-lookup"><span data-stu-id="b94c9-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b94c9-185">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b94c9-185">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b94c9-186">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="b94c9-186">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b94c9-187">任意</span><span class="sxs-lookup"><span data-stu-id="b94c9-187">Any</span></span></p></td>
<td><p><span data-ttu-id="b94c9-188">STUN/TCP による候補の TURN ネゴシエーション/443</span><span class="sxs-lookup"><span data-stu-id="b94c9-188">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="b94c9-189">拡張統合エッジ、NAT を使用したプライベート IP アドレスを使用した DNS 負荷分散のためのファイアウォールの概要: 内部インターフェイス–ノード1およびノード 2 (例)</span><span class="sxs-lookup"><span data-stu-id="b94c9-189">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b94c9-190">プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="b94c9-190">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b94c9-191">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b94c9-191">Source IP address</span></span></th>
<th><span data-ttu-id="b94c9-192">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b94c9-192">Destination IP address</span></span></th>
<th><span data-ttu-id="b94c9-193">Comments</span><span class="sxs-lookup"><span data-stu-id="b94c9-193">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b94c9-194">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="b94c9-194">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="b94c9-195">任意 (フロントエンドサーバーのアドレス、または XMPP ゲートウェイサービスを実行しているフロントエンドプールの IP アドレスとして定義可能)</span><span class="sxs-lookup"><span data-stu-id="b94c9-195">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="b94c9-196">エッジサーバーの内部インターフェイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b94c9-196">Edge Server internal interface IP address</span></span></p></td>
<td><p><span data-ttu-id="b94c9-197">フロントエンドサーバーまたはフロントエンドプールで実行されている XMPP ゲートウェイサービスからの送信 XMPP トラフィック</span><span class="sxs-lookup"><span data-stu-id="b94c9-197">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b94c9-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b94c9-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b94c9-199">任意 (ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバー、またはフロントエンドプールの IP アドレスとして定義可能)</span><span class="sxs-lookup"><span data-stu-id="b94c9-199">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="b94c9-200">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b94c9-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b94c9-201">(ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバーまたはフロントエンドプールの IP アドレスからの) エッジサーバーの内部インターフェイスへの送信 SIP トラフィック</span><span class="sxs-lookup"><span data-stu-id="b94c9-201">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b94c9-202">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b94c9-202">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b94c9-203">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b94c9-203">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b94c9-204">任意 (ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバー、またはフロントエンドプールの IP アドレスとして定義可能)</span><span class="sxs-lookup"><span data-stu-id="b94c9-204">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="b94c9-205">エッジサーバーの内部インターフェイスからの受信 SIP トラフィック (ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバー、またはフロントエンドプールの ip アドレス)</span><span class="sxs-lookup"><span data-stu-id="b94c9-205">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b94c9-206">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="b94c9-206">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="b94c9-207">任意 (フロントエンドサーバーの IP アドレスとして、またはフロントエンドプール内の各フロントエンドサーバーの IP アドレスとして定義可能)</span><span class="sxs-lookup"><span data-stu-id="b94c9-207">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="b94c9-208">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b94c9-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b94c9-209">フロントエンドサーバーまたはプール内の各フロントエンドサーバーからエッジサーバーの内部インターフェイスへの Web 会議トラフィック</span><span class="sxs-lookup"><span data-stu-id="b94c9-209">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b94c9-210">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="b94c9-210">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="b94c9-211">Any (このエッジサーバーを使用するフロントエンドサーバーの IP アドレスまたはフロントエンドプールの IP アドレス、または存続可能 Branch Appliance または存続可能ブランチサーバーとして定義できます)</span><span class="sxs-lookup"><span data-stu-id="b94c9-211">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="b94c9-212">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b94c9-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b94c9-213">このエッジサーバーを使用するフロントエンドサーバーまたはフロントエンドプールの IP アドレスまたは任意の存続可能 Branch Appliance または存続可能ブランチサーバーからの音声ビデオユーザーの認証 (音声ビデオ認証サービス)</span><span class="sxs-lookup"><span data-stu-id="b94c9-213">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b94c9-214">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b94c9-214">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b94c9-215">任意</span><span class="sxs-lookup"><span data-stu-id="b94c9-215">Any</span></span></p></td>
<td><p><span data-ttu-id="b94c9-216">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b94c9-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b94c9-217">内部ユーザーと外部ユーザーとの間の音声ビデオメディア転送の優先パス、存続可能 Branch Appliance または存続可能 Branch Server</span><span class="sxs-lookup"><span data-stu-id="b94c9-217">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b94c9-218">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b94c9-218">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b94c9-219">任意</span><span class="sxs-lookup"><span data-stu-id="b94c9-219">Any</span></span></p></td>
<td><p><span data-ttu-id="b94c9-220">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b94c9-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b94c9-221">内部ユーザーと外部ユーザーとの間の音声ビデオメディア転送のフォールバックパス UDP 通信を確立できない場合は、存続可能 Branch Appliance または存続可能 Branch Server、TCP はファイル転送およびデスクトップ共有に使用されます。</span><span class="sxs-lookup"><span data-stu-id="b94c9-221">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b94c9-222">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="b94c9-222">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="b94c9-223">任意 (フロントエンドサーバーの IP アドレス、または中央管理ストアを保持するプールとして定義可能)</span><span class="sxs-lookup"><span data-stu-id="b94c9-223">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="b94c9-224">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b94c9-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b94c9-225">中央管理ストアからエッジ サーバーへの変更のレプリケーション</span><span class="sxs-lookup"><span data-stu-id="b94c9-225">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b94c9-226">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="b94c9-226">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="b94c9-227">任意</span><span class="sxs-lookup"><span data-stu-id="b94c9-227">Any</span></span></p></td>
<td><p><span data-ttu-id="b94c9-228">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b94c9-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b94c9-229">Lync Server 管理シェルと集中ログサービスコマンドレットを使用した集中ログサービスコントローラー、ClsController コマンドライン (ClsController.exe) またはエージェント (ClsAgent.exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="b94c9-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b94c9-230">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="b94c9-230">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="b94c9-231">任意</span><span class="sxs-lookup"><span data-stu-id="b94c9-231">Any</span></span></p></td>
<td><p><span data-ttu-id="b94c9-232">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b94c9-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b94c9-233">Lync Server 管理シェルと集中ログサービスコマンドレットを使用した集中ログサービスコントローラー、ClsController コマンドライン (ClsController.exe) またはエージェント (ClsAgent.exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="b94c9-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b94c9-234">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="b94c9-234">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="b94c9-235">任意</span><span class="sxs-lookup"><span data-stu-id="b94c9-235">Any</span></span></p></td>
<td><p><span data-ttu-id="b94c9-236">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b94c9-236">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b94c9-237">Lync Server 管理シェルと集中ログサービスコマンドレットを使用した集中ログサービスコントローラー、ClsController コマンドライン (ClsController.exe) またはエージェント (ClsAgent.exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="b94c9-237">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="b94c9-238">フェデレーションのファイアウォールの概要</span><span class="sxs-lookup"><span data-stu-id="b94c9-238">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b94c9-239">役割/プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="b94c9-239">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b94c9-240">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b94c9-240">Source IP address</span></span></th>
<th><span data-ttu-id="b94c9-241">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b94c9-241">Destination IP address</span></span></th>
<th><span data-ttu-id="b94c9-242">Notes</span><span class="sxs-lookup"><span data-stu-id="b94c9-242">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b94c9-243">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b94c9-243">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b94c9-244">アクセス エッジ サービス パブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b94c9-244">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b94c9-245">任意</span><span class="sxs-lookup"><span data-stu-id="b94c9-245">Any</span></span></p></td>
<td><p><span data-ttu-id="b94c9-246">SIP を使用したフェデレーションおよびパブリック IM 接続用</span><span class="sxs-lookup"><span data-stu-id="b94c9-246">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="b94c9-247">ファイアウォールの概要 ‐ パブリック インスタント メッセージング接続</span><span class="sxs-lookup"><span data-stu-id="b94c9-247">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b94c9-248">役割/プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="b94c9-248">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b94c9-249">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b94c9-249">Source IP address</span></span></th>
<th><span data-ttu-id="b94c9-250">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b94c9-250">Destination IP address</span></span></th>
<th><span data-ttu-id="b94c9-251">Notes</span><span class="sxs-lookup"><span data-stu-id="b94c9-251">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b94c9-252">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b94c9-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b94c9-253">パブリック IM 接続パートナー</span><span class="sxs-lookup"><span data-stu-id="b94c9-253">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="b94c9-254">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="b94c9-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b94c9-255">SIP を使用したフェデレーションおよびパブリック IM 接続用</span><span class="sxs-lookup"><span data-stu-id="b94c9-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b94c9-256">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b94c9-256">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b94c9-257">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="b94c9-257">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b94c9-258">パブリック IM 接続パートナー</span><span class="sxs-lookup"><span data-stu-id="b94c9-258">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="b94c9-259">SIP を使用したフェデレーションおよびパブリック IM 接続用</span><span class="sxs-lookup"><span data-stu-id="b94c9-259">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b94c9-260">アクセス/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b94c9-260">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b94c9-261">クライアント</span><span class="sxs-lookup"><span data-stu-id="b94c9-261">Clients</span></span></p></td>
<td><p><span data-ttu-id="b94c9-262">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="b94c9-262">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b94c9-263">外部ユーザー アクセス用のクライアントからサーバーへの SIP トラフィック</span><span class="sxs-lookup"><span data-stu-id="b94c9-263">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b94c9-264">音声/V/RTP/TCP/50,000-59999</span><span class="sxs-lookup"><span data-stu-id="b94c9-264">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b94c9-265">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="b94c9-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b94c9-266">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="b94c9-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="b94c9-267">パブリック IM 接続が構成されている場合に、Windows Live Messenger との音声ビデオ セッションに使用されます。</span><span class="sxs-lookup"><span data-stu-id="b94c9-267">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b94c9-268">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b94c9-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b94c9-269">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="b94c9-269">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b94c9-270">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="b94c9-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="b94c9-271">Windows Live Messenger とのパブリック IM 接続では必須</span><span class="sxs-lookup"><span data-stu-id="b94c9-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b94c9-272">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b94c9-272">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b94c9-273">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="b94c9-273">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="b94c9-274">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="b94c9-274">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b94c9-275">Windows Live Messenger とのパブリック IM 接続では必須</span><span class="sxs-lookup"><span data-stu-id="b94c9-275">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="b94c9-276">XMPP のファイアウォールの概要</span><span class="sxs-lookup"><span data-stu-id="b94c9-276">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b94c9-277">プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="b94c9-277">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b94c9-278">送信元 (IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="b94c9-278">Source (IP address)</span></span></th>
<th><span data-ttu-id="b94c9-279">宛先 (IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="b94c9-279">Destination (IP address)</span></span></th>
<th><span data-ttu-id="b94c9-280">Comments</span><span class="sxs-lookup"><span data-stu-id="b94c9-280">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b94c9-281">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="b94c9-281">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="b94c9-282">任意</span><span class="sxs-lookup"><span data-stu-id="b94c9-282">Any</span></span></p></td>
<td><p><span data-ttu-id="b94c9-283">エッジサーバーアクセスエッジサービスインターフェイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b94c9-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="b94c9-284">XMPP 用の標準的なサーバー間通信。</span><span class="sxs-lookup"><span data-stu-id="b94c9-284">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="b94c9-285">フェデレーションされた XMPP パートナーからのエッジサーバー XMPP プロキシへの通信を許可します。</span><span class="sxs-lookup"><span data-stu-id="b94c9-285">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b94c9-286">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="b94c9-286">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="b94c9-287">エッジサーバーアクセスエッジサービスインターフェイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b94c9-287">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="b94c9-288">任意</span><span class="sxs-lookup"><span data-stu-id="b94c9-288">Any</span></span></p></td>
<td><p><span data-ttu-id="b94c9-289">XMPP 用の標準的なサーバー間通信。</span><span class="sxs-lookup"><span data-stu-id="b94c9-289">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="b94c9-290">エッジサーバー XMPP プロキシからフェデレーションされた XMPP パートナーへの通信を許可します。</span><span class="sxs-lookup"><span data-stu-id="b94c9-290">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b94c9-291">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="b94c9-291">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="b94c9-292">任意</span><span class="sxs-lookup"><span data-stu-id="b94c9-292">Any</span></span></p></td>
<td><p><span data-ttu-id="b94c9-293">各内部エッジサーバーインターフェイス IP</span><span class="sxs-lookup"><span data-stu-id="b94c9-293">Each internal Edge Server interface IP</span></span></p></td>
<td><p><span data-ttu-id="b94c9-294">フロントエンドサーバーまたはフロントエンドプールの XMPP ゲートウェイから、エッジサーバーの内部 IP アドレスまたは各エッジプールメンバーの内部 IP アドレスへの内部 XMPP トラフィック</span><span class="sxs-lookup"><span data-stu-id="b94c9-294">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

