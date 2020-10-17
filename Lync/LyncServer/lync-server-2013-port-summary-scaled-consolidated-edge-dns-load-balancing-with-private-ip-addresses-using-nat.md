---
title: 'Lync Server 2013: ポートの概要-拡張統合エッジ、NAT を使用したプライベート IP アドレスを使用した DNS 負荷分散'
description: 'Lync Server 2013: ポートの概要-拡張統合エッジ、NAT を使用したプライベート IP アドレスを使用した DNS 負荷分散'
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
ms.openlocfilehash: e0402b6682e86e5edf263fca78dfbe0f8fa070b4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563943"
---
# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="3f094-103">ポートの概要-Lync Server 2013 での NAT を使用したプライベート IP アドレスを使用した拡張統合エッジ、DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="3f094-103">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f094-104">_**トピックの最終更新日:** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="3f094-104">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="3f094-105">このシナリオアーキテクチャで説明されている Lync server 2013 のエッジサーバー機能は、Lync Server 2010 で実装されていたものとよく似ています。</span><span class="sxs-lookup"><span data-stu-id="3f094-105">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="3f094-106">最も目を引くのは、XMPP (Extensible Messaging and Presence Protocol) 用の ポート **5269/TCP** エントリが追加されたことです。</span><span class="sxs-lookup"><span data-stu-id="3f094-106">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="3f094-107">Lync Server 2013 は、フロントエンドサーバーまたはフロントエンドプールに、エッジサーバーまたはエッジプールおよび XMPP ゲートウェイサーバー上に XMPP プロキシを任意で展開します。</span><span class="sxs-lookup"><span data-stu-id="3f094-107">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="3f094-108">IPv4 に加えて、エッジサーバーは IPv6 をサポートするようになりました。</span><span class="sxs-lookup"><span data-stu-id="3f094-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="3f094-109">わかりやすいように、シナリオでは IPv4 のみを使用します。</span><span class="sxs-lookup"><span data-stu-id="3f094-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="3f094-110">**NAT を使用して拡張統合エッジとプライベート IP アドレスを使用するためのエンタープライズ境界ネットワーク**</span><span class="sxs-lookup"><span data-stu-id="3f094-110">**Enterprise perimeter network for scaled consolidated edge with private IP addresses using NAT**</span></span>

<span data-ttu-id="3f094-111">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="3f094-111">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="3f094-112">ポートとプロトコルの詳細</span><span class="sxs-lookup"><span data-stu-id="3f094-112">Port and Protocol Details</span></span>

<span data-ttu-id="3f094-113">外部アクセスを提供する機能のサポートに必要なポートのみを開くことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3f094-113">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="3f094-p103">エッジ サービスのリモート アクセスが機能するためには、受信/送信のエッジ トラフィックの図が示すように、SIP トラフィックの双方向通過が許可されていることが必須です。つまり、インスタント メッセージング (IM)、プレゼンス、Web 会議、音声ビデオ (A/V)、およびフェデレーションでは、アクセス エッジ サービスとの間で SIP メッセージングが実行されます。</span><span class="sxs-lookup"><span data-stu-id="3f094-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="3f094-116">拡張統合エッジ、NAT を使用したプライベート IP アドレスを使用した DNS 負荷分散のためのファイアウォールの概要: 外部インターフェイス–ノード1およびノード 2 (例)</span><span class="sxs-lookup"><span data-stu-id="3f094-116">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3f094-117">役割/プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="3f094-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="3f094-118">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="3f094-118">Source IP address</span></span></th>
<th><span data-ttu-id="3f094-119">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="3f094-119">Destination IP address</span></span></th>
<th><span data-ttu-id="3f094-120">Notes</span><span class="sxs-lookup"><span data-stu-id="3f094-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3f094-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="3f094-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="3f094-122">任意</span><span class="sxs-lookup"><span data-stu-id="3f094-122">Any</span></span></p></td>
<td><p><span data-ttu-id="3f094-123">XMPP プロキシサービス (アクセスエッジサービスを使用して IP アドレスを共有)</span><span class="sxs-lookup"><span data-stu-id="3f094-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="3f094-124">XMPP プロキシ サービスは、定義された XMPP フェデレーションの XMPP コンタクトからトラフィックを受け付けます</span><span class="sxs-lookup"><span data-stu-id="3f094-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f094-125">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="3f094-125">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="3f094-126">XMPP プロキシサービス (アクセスエッジサービスを使用して IP アドレスを共有)</span><span class="sxs-lookup"><span data-stu-id="3f094-126">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="3f094-127">任意</span><span class="sxs-lookup"><span data-stu-id="3f094-127">Any</span></span></p></td>
<td><p><span data-ttu-id="3f094-128">XMPP プロキシサービスは、定義された XMPP フェデレーションの XMPP 連絡先にトラフィックを送信します。</span><span class="sxs-lookup"><span data-stu-id="3f094-128">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f094-129">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="3f094-129">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="3f094-130">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="3f094-130">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="3f094-131">任意</span><span class="sxs-lookup"><span data-stu-id="3f094-131">Any</span></span></p></td>
<td><p><span data-ttu-id="3f094-132">証明書の失効/CRL のチェックおよび取得</span><span class="sxs-lookup"><span data-stu-id="3f094-132">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f094-133">アクセス/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="3f094-133">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="3f094-134">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="3f094-134">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="3f094-135">任意</span><span class="sxs-lookup"><span data-stu-id="3f094-135">Any</span></span></p></td>
<td><p><span data-ttu-id="3f094-136">TCP による DNS クエリ</span><span class="sxs-lookup"><span data-stu-id="3f094-136">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f094-137">アクセス/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="3f094-137">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="3f094-138">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="3f094-138">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="3f094-139">任意</span><span class="sxs-lookup"><span data-stu-id="3f094-139">Any</span></span></p></td>
<td><p><span data-ttu-id="3f094-140">UDP による DNS クエリ</span><span class="sxs-lookup"><span data-stu-id="3f094-140">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f094-141">アクセス/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="3f094-141">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="3f094-142">任意</span><span class="sxs-lookup"><span data-stu-id="3f094-142">Any</span></span></p></td>
<td><p><span data-ttu-id="3f094-143">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="3f094-143">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="3f094-144">外部ユーザー アクセス用のクライアントからサーバーへの SIP トラフィック</span><span class="sxs-lookup"><span data-stu-id="3f094-144">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f094-145">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="3f094-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3f094-146">任意</span><span class="sxs-lookup"><span data-stu-id="3f094-146">Any</span></span></p></td>
<td><p><span data-ttu-id="3f094-147">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="3f094-147">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="3f094-148">SIP を使用したフェデレーションおよびパブリック IM 接続用</span><span class="sxs-lookup"><span data-stu-id="3f094-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f094-149">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="3f094-149">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3f094-150">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="3f094-150">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="3f094-151">任意</span><span class="sxs-lookup"><span data-stu-id="3f094-151">Any</span></span></p></td>
<td><p><span data-ttu-id="3f094-152">SIP を使用したフェデレーションおよびパブリック IM 接続用</span><span class="sxs-lookup"><span data-stu-id="3f094-152">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f094-153">Web 会議/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="3f094-153">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="3f094-154">任意</span><span class="sxs-lookup"><span data-stu-id="3f094-154">Any</span></span></p></td>
<td><p><span data-ttu-id="3f094-155">エッジサーバー Web 会議エッジサービス</span><span class="sxs-lookup"><span data-stu-id="3f094-155">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="3f094-156">Web 会議メディア</span><span class="sxs-lookup"><span data-stu-id="3f094-156">Web Conferencing media</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f094-157">音声/V/RTP/TCP/50,000-59999</span><span class="sxs-lookup"><span data-stu-id="3f094-157">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="3f094-158">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="3f094-158">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3f094-159">任意</span><span class="sxs-lookup"><span data-stu-id="3f094-159">Any</span></span></p></td>
<td><p><span data-ttu-id="3f094-160">Office Communications Server 2007、Office Communications Server 2007 R2、Lync Server 2010、Lync Server 2013 を実行しているパートナーとのフェデレーションに必要です。</span><span class="sxs-lookup"><span data-stu-id="3f094-160">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f094-161">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="3f094-161">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="3f094-162">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="3f094-162">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3f094-163">任意</span><span class="sxs-lookup"><span data-stu-id="3f094-163">Any</span></span></p></td>
<td><p><span data-ttu-id="3f094-164">Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必要。</span><span class="sxs-lookup"><span data-stu-id="3f094-164">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f094-165">音声/V/RTP/TCP/50,000-59999</span><span class="sxs-lookup"><span data-stu-id="3f094-165">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="3f094-166">任意</span><span class="sxs-lookup"><span data-stu-id="3f094-166">Any</span></span></p></td>
<td><p><span data-ttu-id="3f094-167">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="3f094-167">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3f094-168">Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必要</span><span class="sxs-lookup"><span data-stu-id="3f094-168">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f094-169">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="3f094-169">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="3f094-170">任意</span><span class="sxs-lookup"><span data-stu-id="3f094-170">Any</span></span></p></td>
<td><p><span data-ttu-id="3f094-171">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="3f094-171">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3f094-172">Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必要</span><span class="sxs-lookup"><span data-stu-id="3f094-172">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f094-173">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="3f094-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="3f094-174">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="3f094-174">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3f094-175">任意</span><span class="sxs-lookup"><span data-stu-id="3f094-175">Any</span></span></p></td>
<td><p><span data-ttu-id="3f094-176">3478の送信は、Lync Server の通信相手であるエッジサーバーのバージョンと、エッジサーバー間のメディアトラフィックに使用されます。</span><span class="sxs-lookup"><span data-stu-id="3f094-176">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="3f094-177">Lync Server 2010、Windows Live Messenger、および Office Communications Server 2007 R2 とのフェデレーションに必要です。また、複数のエッジプールが会社内に展開されている場合も必須です。</span><span class="sxs-lookup"><span data-stu-id="3f094-177">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f094-178">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="3f094-178">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="3f094-179">任意</span><span class="sxs-lookup"><span data-stu-id="3f094-179">Any</span></span></p></td>
<td><p><span data-ttu-id="3f094-180">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="3f094-180">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3f094-181">STUN/UDP による候補の TURN ネゴシエーション/3478</span><span class="sxs-lookup"><span data-stu-id="3f094-181">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f094-182">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="3f094-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="3f094-183">任意</span><span class="sxs-lookup"><span data-stu-id="3f094-183">Any</span></span></p></td>
<td><p><span data-ttu-id="3f094-184">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="3f094-184">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3f094-185">STUN/TCP による候補の TURN ネゴシエーション/443</span><span class="sxs-lookup"><span data-stu-id="3f094-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f094-186">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="3f094-186">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="3f094-187">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="3f094-187">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3f094-188">任意</span><span class="sxs-lookup"><span data-stu-id="3f094-188">Any</span></span></p></td>
<td><p><span data-ttu-id="3f094-189">STUN/TCP による候補の TURN ネゴシエーション/443</span><span class="sxs-lookup"><span data-stu-id="3f094-189">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="3f094-190">拡張統合エッジ、NAT を使用したプライベート IP アドレスを使用した DNS 負荷分散のためのファイアウォールの概要: 内部インターフェイス–ノード1およびノード 2 (例)</span><span class="sxs-lookup"><span data-stu-id="3f094-190">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3f094-191">プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="3f094-191">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="3f094-192">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="3f094-192">Source IP address</span></span></th>
<th><span data-ttu-id="3f094-193">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="3f094-193">Destination IP address</span></span></th>
<th><span data-ttu-id="3f094-194">Comments</span><span class="sxs-lookup"><span data-stu-id="3f094-194">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3f094-195">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="3f094-195">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="3f094-196">任意 (フロントエンドサーバーのアドレス、または XMPP ゲートウェイサービスを実行しているフロントエンドプールの IP アドレスとして定義可能)</span><span class="sxs-lookup"><span data-stu-id="3f094-196">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="3f094-197">エッジサーバーの内部インターフェイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="3f094-197">Edge Server internal interface IP address</span></span></p></td>
<td><p><span data-ttu-id="3f094-198">フロントエンドサーバーまたはフロントエンドプールで実行されている XMPP ゲートウェイサービスからの送信 XMPP トラフィック</span><span class="sxs-lookup"><span data-stu-id="3f094-198">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f094-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="3f094-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3f094-200">任意 (ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバー、またはフロントエンドプールの IP アドレスとして定義可能)</span><span class="sxs-lookup"><span data-stu-id="3f094-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="3f094-201">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3f094-201">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3f094-202">(ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバーまたはフロントエンドプールの IP アドレスからの) エッジサーバーの内部インターフェイスへの送信 SIP トラフィック</span><span class="sxs-lookup"><span data-stu-id="3f094-202">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f094-203">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="3f094-203">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3f094-204">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3f094-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3f094-205">任意 (ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバー、またはフロントエンドプールの IP アドレスとして定義可能)</span><span class="sxs-lookup"><span data-stu-id="3f094-205">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="3f094-206">エッジサーバーの内部インターフェイスからの受信 SIP トラフィック (ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバー、またはフロントエンドプールの ip アドレス)</span><span class="sxs-lookup"><span data-stu-id="3f094-206">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f094-207">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="3f094-207">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="3f094-208">任意 (フロントエンドサーバーの IP アドレスとして、またはフロントエンドプール内の各フロントエンドサーバーの IP アドレスとして定義可能)</span><span class="sxs-lookup"><span data-stu-id="3f094-208">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="3f094-209">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3f094-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3f094-210">フロントエンドサーバーまたはプール内の各フロントエンドサーバーからエッジサーバーの内部インターフェイスへの Web 会議トラフィック</span><span class="sxs-lookup"><span data-stu-id="3f094-210">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f094-211">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="3f094-211">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="3f094-212">Any (このエッジサーバーを使用するフロントエンドサーバーの IP アドレスまたはフロントエンドプールの IP アドレス、または存続可能 Branch Appliance または存続可能ブランチサーバーとして定義できます)</span><span class="sxs-lookup"><span data-stu-id="3f094-212">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="3f094-213">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3f094-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3f094-214">このエッジサーバーを使用するフロントエンドサーバーまたはフロントエンドプールの IP アドレスまたは任意の存続可能 Branch Appliance または存続可能ブランチサーバーからの音声ビデオユーザーの認証 (音声ビデオ認証サービス)</span><span class="sxs-lookup"><span data-stu-id="3f094-214">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f094-215">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="3f094-215">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="3f094-216">任意</span><span class="sxs-lookup"><span data-stu-id="3f094-216">Any</span></span></p></td>
<td><p><span data-ttu-id="3f094-217">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3f094-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3f094-218">内部ユーザーと外部ユーザーとの間の音声ビデオメディア転送の優先パス、存続可能 Branch Appliance または存続可能 Branch Server</span><span class="sxs-lookup"><span data-stu-id="3f094-218">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f094-219">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="3f094-219">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="3f094-220">任意</span><span class="sxs-lookup"><span data-stu-id="3f094-220">Any</span></span></p></td>
<td><p><span data-ttu-id="3f094-221">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3f094-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3f094-222">内部ユーザーと外部ユーザーとの間の音声ビデオメディア転送のフォールバックパス UDP 通信を確立できない場合は、存続可能 Branch Appliance または存続可能 Branch Server、TCP はファイル転送およびデスクトップ共有に使用されます。</span><span class="sxs-lookup"><span data-stu-id="3f094-222">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f094-223">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="3f094-223">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="3f094-224">任意 (フロントエンドサーバーの IP アドレス、または中央管理ストアを保持するプールとして定義可能)</span><span class="sxs-lookup"><span data-stu-id="3f094-224">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="3f094-225">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3f094-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3f094-226">中央管理ストアからエッジ サーバーへの変更のレプリケーション</span><span class="sxs-lookup"><span data-stu-id="3f094-226">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f094-227">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="3f094-227">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="3f094-228">任意</span><span class="sxs-lookup"><span data-stu-id="3f094-228">Any</span></span></p></td>
<td><p><span data-ttu-id="3f094-229">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3f094-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3f094-230">Lync Server 管理シェルと集中ログサービスコマンドレットを使用した集中ログサービスコントローラー、ClsController コマンドライン (ClsController.exe) またはエージェント (ClsAgent.exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="3f094-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f094-231">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="3f094-231">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="3f094-232">任意</span><span class="sxs-lookup"><span data-stu-id="3f094-232">Any</span></span></p></td>
<td><p><span data-ttu-id="3f094-233">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3f094-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3f094-234">Lync Server 管理シェルと集中ログサービスコマンドレットを使用した集中ログサービスコントローラー、ClsController コマンドライン (ClsController.exe) またはエージェント (ClsAgent.exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="3f094-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f094-235">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="3f094-235">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="3f094-236">任意</span><span class="sxs-lookup"><span data-stu-id="3f094-236">Any</span></span></p></td>
<td><p><span data-ttu-id="3f094-237">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3f094-237">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3f094-238">Lync Server 管理シェルと集中ログサービスコマンドレットを使用した集中ログサービスコントローラー、ClsController コマンドライン (ClsController.exe) またはエージェント (ClsAgent.exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="3f094-238">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="3f094-239">フェデレーションのファイアウォールの概要</span><span class="sxs-lookup"><span data-stu-id="3f094-239">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3f094-240">役割/プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="3f094-240">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="3f094-241">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="3f094-241">Source IP address</span></span></th>
<th><span data-ttu-id="3f094-242">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="3f094-242">Destination IP address</span></span></th>
<th><span data-ttu-id="3f094-243">Notes</span><span class="sxs-lookup"><span data-stu-id="3f094-243">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3f094-244">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="3f094-244">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3f094-245">アクセス エッジ サービス パブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="3f094-245">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3f094-246">任意</span><span class="sxs-lookup"><span data-stu-id="3f094-246">Any</span></span></p></td>
<td><p><span data-ttu-id="3f094-247">SIP を使用したフェデレーションおよびパブリック IM 接続用</span><span class="sxs-lookup"><span data-stu-id="3f094-247">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="3f094-248">ファイアウォールの概要 ‐ パブリック インスタント メッセージング接続</span><span class="sxs-lookup"><span data-stu-id="3f094-248">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3f094-249">役割/プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="3f094-249">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="3f094-250">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="3f094-250">Source IP address</span></span></th>
<th><span data-ttu-id="3f094-251">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="3f094-251">Destination IP address</span></span></th>
<th><span data-ttu-id="3f094-252">Notes</span><span class="sxs-lookup"><span data-stu-id="3f094-252">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3f094-253">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="3f094-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3f094-254">パブリック IM 接続パートナー</span><span class="sxs-lookup"><span data-stu-id="3f094-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="3f094-255">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="3f094-255">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="3f094-256">SIP を使用したフェデレーションおよびパブリック IM 接続用</span><span class="sxs-lookup"><span data-stu-id="3f094-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f094-257">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="3f094-257">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3f094-258">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="3f094-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="3f094-259">パブリック IM 接続パートナー</span><span class="sxs-lookup"><span data-stu-id="3f094-259">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="3f094-260">SIP を使用したフェデレーションおよびパブリック IM 接続用</span><span class="sxs-lookup"><span data-stu-id="3f094-260">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f094-261">アクセス/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="3f094-261">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="3f094-262">クライアント</span><span class="sxs-lookup"><span data-stu-id="3f094-262">Clients</span></span></p></td>
<td><p><span data-ttu-id="3f094-263">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="3f094-263">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="3f094-264">外部ユーザー アクセス用のクライアントからサーバーへの SIP トラフィック</span><span class="sxs-lookup"><span data-stu-id="3f094-264">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f094-265">音声/V/RTP/TCP/50,000-59999</span><span class="sxs-lookup"><span data-stu-id="3f094-265">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="3f094-266">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="3f094-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3f094-267">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="3f094-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="3f094-268">パブリック IM 接続が構成されている場合に、Windows Live Messenger との音声ビデオ セッションに使用されます。</span><span class="sxs-lookup"><span data-stu-id="3f094-268">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f094-269">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="3f094-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="3f094-270">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="3f094-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3f094-271">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="3f094-271">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="3f094-272">Windows Live Messenger とのパブリック IM 接続では必須</span><span class="sxs-lookup"><span data-stu-id="3f094-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f094-273">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="3f094-273">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="3f094-274">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="3f094-274">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="3f094-275">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="3f094-275">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3f094-276">Windows Live Messenger とのパブリック IM 接続では必須</span><span class="sxs-lookup"><span data-stu-id="3f094-276">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="3f094-277">XMPP のファイアウォールの概要</span><span class="sxs-lookup"><span data-stu-id="3f094-277">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3f094-278">プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="3f094-278">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="3f094-279">送信元 (IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="3f094-279">Source (IP address)</span></span></th>
<th><span data-ttu-id="3f094-280">宛先 (IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="3f094-280">Destination (IP address)</span></span></th>
<th><span data-ttu-id="3f094-281">Comments</span><span class="sxs-lookup"><span data-stu-id="3f094-281">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3f094-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="3f094-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="3f094-283">任意</span><span class="sxs-lookup"><span data-stu-id="3f094-283">Any</span></span></p></td>
<td><p><span data-ttu-id="3f094-284">エッジサーバーアクセスエッジサービスインターフェイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="3f094-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="3f094-285">XMPP 用の標準的なサーバー間通信。</span><span class="sxs-lookup"><span data-stu-id="3f094-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="3f094-286">フェデレーションされた XMPP パートナーからのエッジサーバー XMPP プロキシへの通信を許可します。</span><span class="sxs-lookup"><span data-stu-id="3f094-286">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f094-287">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="3f094-287">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="3f094-288">エッジサーバーアクセスエッジサービスインターフェイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="3f094-288">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="3f094-289">任意</span><span class="sxs-lookup"><span data-stu-id="3f094-289">Any</span></span></p></td>
<td><p><span data-ttu-id="3f094-290">XMPP 用の標準的なサーバー間通信。</span><span class="sxs-lookup"><span data-stu-id="3f094-290">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="3f094-291">エッジサーバー XMPP プロキシからフェデレーションされた XMPP パートナーへの通信を許可します。</span><span class="sxs-lookup"><span data-stu-id="3f094-291">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f094-292">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="3f094-292">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="3f094-293">任意</span><span class="sxs-lookup"><span data-stu-id="3f094-293">Any</span></span></p></td>
<td><p><span data-ttu-id="3f094-294">各内部エッジサーバーインターフェイス IP</span><span class="sxs-lookup"><span data-stu-id="3f094-294">Each internal Edge Server interface IP</span></span></p></td>
<td><p><span data-ttu-id="3f094-295">フロントエンドサーバーまたはフロントエンドプールの XMPP ゲートウェイから、エッジサーバーの内部 IP アドレスまたは各エッジプールメンバーの内部 IP アドレスへの内部 XMPP トラフィック</span><span class="sxs-lookup"><span data-stu-id="3f094-295">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

