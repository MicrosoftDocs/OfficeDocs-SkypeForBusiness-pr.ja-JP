---
title: 'Lync Server 2013: ポートの概要-拡張統合エッジ、パブリック IP アドレスによる DNS 負荷分散'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses
ms:assetid: f7cbd0f1-841d-4116-8d17-e9d991daa4a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205394(v=OCS.15)
ms:contentKeyID: 48185865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5318f418c2bbd0876999aedcb33b559c5572b20a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534124"
---
# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="c72e9-102">ポートの概要-Lync Server 2013 での拡張統合エッジ、パブリック IP アドレスを使用した DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="c72e9-102">Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c72e9-103">_**トピックの最終更新日:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="c72e9-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="c72e9-104">このシナリオアーキテクチャで説明されている Lync server 2013 のエッジサーバー機能は、Lync Server 2010 で実装されていたものとよく似ています。</span><span class="sxs-lookup"><span data-stu-id="c72e9-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="c72e9-105">最も目を引くのは、XMPP (Extensible Messaging and Presence Protocol) 用の ポート **5269/TCP** エントリが追加されたことです。</span><span class="sxs-lookup"><span data-stu-id="c72e9-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="c72e9-106">Lync Server 2013 は、フロントエンドサーバーまたはフロントエンドプールに、エッジサーバーまたはエッジプールおよび XMPP ゲートウェイサーバー上に XMPP プロキシを任意で展開します。</span><span class="sxs-lookup"><span data-stu-id="c72e9-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="c72e9-107">IPv4 に加えて、エッジサーバーは IPv6 をサポートするようになりました。</span><span class="sxs-lookup"><span data-stu-id="c72e9-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="c72e9-108">わかりやすいように、シナリオでは IPv4 のみを使用します。</span><span class="sxs-lookup"><span data-stu-id="c72e9-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="c72e9-109">**拡張統合エッジ、パブリック IP アドレスによる DNS 負荷分散のためのエンタープライズ境界ネットワーク**</span><span class="sxs-lookup"><span data-stu-id="c72e9-109">**Enterprise perimeter network for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses**</span></span>

<span data-ttu-id="c72e9-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="c72e9-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="c72e9-111">ポートとプロトコルの詳細</span><span class="sxs-lookup"><span data-stu-id="c72e9-111">Port and Protocol Details</span></span>

<span data-ttu-id="c72e9-112">外部アクセスを提供する機能のサポートに必要なポートのみを開くことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c72e9-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="c72e9-p103">エッジ サービスのリモート アクセスが機能するためには、受信/送信のエッジ トラフィックの図が示すように、SIP トラフィックの双方向通過が許可されていることが必須です。つまり、インスタント メッセージング (IM)、プレゼンス、Web 会議、音声ビデオ (A/V)、およびフェデレーションでは、アクセス エッジ サービスとの間で SIP メッセージングが実行されます。</span><span class="sxs-lookup"><span data-stu-id="c72e9-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="c72e9-115">拡張統合エッジ、パブリック IP アドレスを使用した DNS 負荷分散のためのファイアウォールの概要: 外部インターフェイス–ノード1およびノード 2 (例)</span><span class="sxs-lookup"><span data-stu-id="c72e9-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c72e9-116">役割/プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="c72e9-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c72e9-117">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="c72e9-117">Source IP address</span></span></th>
<th><span data-ttu-id="c72e9-118">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="c72e9-118">Destination IP address</span></span></th>
<th><span data-ttu-id="c72e9-119">Notes</span><span class="sxs-lookup"><span data-stu-id="c72e9-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c72e9-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="c72e9-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="c72e9-121">任意</span><span class="sxs-lookup"><span data-stu-id="c72e9-121">Any</span></span></p></td>
<td><p><span data-ttu-id="c72e9-122">XMPP プロキシサービス (アクセスエッジサービスを使用して IP アドレスを共有)</span><span class="sxs-lookup"><span data-stu-id="c72e9-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="c72e9-123">XMPP プロキシ サービスは、定義された XMPP フェデレーションの XMPP コンタクトからトラフィックを受け付けます</span><span class="sxs-lookup"><span data-stu-id="c72e9-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c72e9-124">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="c72e9-124">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="c72e9-125">エッジサーバーアクセスエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="c72e9-125">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c72e9-126">任意</span><span class="sxs-lookup"><span data-stu-id="c72e9-126">Any</span></span></p></td>
<td><p><span data-ttu-id="c72e9-127">証明書の失効/CRL のチェックおよび取得</span><span class="sxs-lookup"><span data-stu-id="c72e9-127">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c72e9-128">アクセス/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="c72e9-128">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="c72e9-129">エッジサーバーアクセスエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="c72e9-129">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c72e9-130">任意</span><span class="sxs-lookup"><span data-stu-id="c72e9-130">Any</span></span></p></td>
<td><p><span data-ttu-id="c72e9-131">TCP による DNS クエリ</span><span class="sxs-lookup"><span data-stu-id="c72e9-131">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c72e9-132">アクセス/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="c72e9-132">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="c72e9-133">エッジサーバーアクセスエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="c72e9-133">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c72e9-134">任意</span><span class="sxs-lookup"><span data-stu-id="c72e9-134">Any</span></span></p></td>
<td><p><span data-ttu-id="c72e9-135">UDP による DNS クエリ</span><span class="sxs-lookup"><span data-stu-id="c72e9-135">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c72e9-136">アクセス/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="c72e9-136">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c72e9-137">任意</span><span class="sxs-lookup"><span data-stu-id="c72e9-137">Any</span></span></p></td>
<td><p><span data-ttu-id="c72e9-138">エッジサーバーアクセスエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="c72e9-138">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c72e9-139">外部ユーザー アクセス用のクライアントからサーバーへの SIP トラフィック</span><span class="sxs-lookup"><span data-stu-id="c72e9-139">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c72e9-140">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="c72e9-140">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c72e9-141">任意</span><span class="sxs-lookup"><span data-stu-id="c72e9-141">Any</span></span></p></td>
<td><p><span data-ttu-id="c72e9-142">エッジサーバーアクセスエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="c72e9-142">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c72e9-143">SIP を使用したフェデレーションおよびパブリック IM 接続用</span><span class="sxs-lookup"><span data-stu-id="c72e9-143">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c72e9-144">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="c72e9-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c72e9-145">エッジサーバーアクセスエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="c72e9-145">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c72e9-146">任意</span><span class="sxs-lookup"><span data-stu-id="c72e9-146">Any</span></span></p></td>
<td><p><span data-ttu-id="c72e9-147">SIP を使用したフェデレーションおよびパブリック IM 接続用</span><span class="sxs-lookup"><span data-stu-id="c72e9-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c72e9-148">Web 会議/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="c72e9-148">Web Conferencing/PSOM(TLS)TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c72e9-149">任意</span><span class="sxs-lookup"><span data-stu-id="c72e9-149">Any</span></span></p></td>
<td><p><span data-ttu-id="c72e9-150">エッジサーバー Web 会議エッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="c72e9-150">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c72e9-151">Web 会議メディア</span><span class="sxs-lookup"><span data-stu-id="c72e9-151">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c72e9-152">音声/V/RTP/TCP/50,000-59999</span><span class="sxs-lookup"><span data-stu-id="c72e9-152">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="c72e9-153">エッジサーバーの音声ビデオエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="c72e9-153">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c72e9-154">任意</span><span class="sxs-lookup"><span data-stu-id="c72e9-154">Any</span></span></p></td>
<td><p><span data-ttu-id="c72e9-155">Office Communications Server 2007、Office Communications Server 2007 R2、Lync Server 2010、Lync Server 2013 を実行しているパートナーとのフェデレーションに必要です。</span><span class="sxs-lookup"><span data-stu-id="c72e9-155">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c72e9-156">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="c72e9-156">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="c72e9-157">エッジサーバーの音声ビデオエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="c72e9-157">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c72e9-158">任意</span><span class="sxs-lookup"><span data-stu-id="c72e9-158">Any</span></span></p></td>
<td><p><span data-ttu-id="c72e9-159">Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必要。</span><span class="sxs-lookup"><span data-stu-id="c72e9-159">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c72e9-160">音声/V/RTP/TCP/50,000-59999</span><span class="sxs-lookup"><span data-stu-id="c72e9-160">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="c72e9-161">任意</span><span class="sxs-lookup"><span data-stu-id="c72e9-161">Any</span></span></p></td>
<td><p><span data-ttu-id="c72e9-162">エッジサーバーの音声ビデオエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="c72e9-162">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c72e9-163">Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必要</span><span class="sxs-lookup"><span data-stu-id="c72e9-163">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c72e9-164">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="c72e9-164">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="c72e9-165">任意</span><span class="sxs-lookup"><span data-stu-id="c72e9-165">Any</span></span></p></td>
<td><p><span data-ttu-id="c72e9-166">エッジサーバーの音声ビデオエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="c72e9-166">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c72e9-167">Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必要</span><span class="sxs-lookup"><span data-stu-id="c72e9-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c72e9-168">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="c72e9-168">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="c72e9-169">エッジサーバーの音声ビデオエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="c72e9-169">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c72e9-170">任意</span><span class="sxs-lookup"><span data-stu-id="c72e9-170">Any</span></span></p></td>
<td><p><span data-ttu-id="c72e9-171">3478の送信は、Lync Server の通信相手であるエッジサーバーのバージョンと、エッジサーバー間のメディアトラフィックに使用されます。</span><span class="sxs-lookup"><span data-stu-id="c72e9-171">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="c72e9-172">Lync Server 2010、Windows Live Messenger、および Office Communications Server 2007 R2 とのフェデレーションに必要です。また、複数のエッジプールが会社内に展開されている場合も必須です。</span><span class="sxs-lookup"><span data-stu-id="c72e9-172">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c72e9-173">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="c72e9-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="c72e9-174">任意</span><span class="sxs-lookup"><span data-stu-id="c72e9-174">Any</span></span></p></td>
<td><p><span data-ttu-id="c72e9-175">エッジサーバーの音声ビデオエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="c72e9-175">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c72e9-176">STUN/UDP による候補の TURN ネゴシエーション/3478</span><span class="sxs-lookup"><span data-stu-id="c72e9-176">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c72e9-177">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="c72e9-177">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c72e9-178">任意</span><span class="sxs-lookup"><span data-stu-id="c72e9-178">Any</span></span></p></td>
<td><p><span data-ttu-id="c72e9-179">エッジサーバーの音声ビデオエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="c72e9-179">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c72e9-180">STUN/TCP による候補の TURN ネゴシエーション/443</span><span class="sxs-lookup"><span data-stu-id="c72e9-180">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c72e9-181">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="c72e9-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c72e9-182">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="c72e9-182">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="c72e9-183">任意</span><span class="sxs-lookup"><span data-stu-id="c72e9-183">Any</span></span></p></td>
<td><p><span data-ttu-id="c72e9-184">STUN/TCP による候補の TURN ネゴシエーション/443</span><span class="sxs-lookup"><span data-stu-id="c72e9-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="c72e9-185">拡張統合エッジ、パブリック IP アドレスを使用した DNS 負荷分散のためのファイアウォールの概要: 内部インターフェイス – ノード 1 およびノード 2 (例)</span><span class="sxs-lookup"><span data-stu-id="c72e9-185">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c72e9-186">プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="c72e9-186">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c72e9-187">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="c72e9-187">Source IP address</span></span></th>
<th><span data-ttu-id="c72e9-188">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="c72e9-188">Destination IP address</span></span></th>
<th><span data-ttu-id="c72e9-189">Comments</span><span class="sxs-lookup"><span data-stu-id="c72e9-189">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c72e9-190">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="c72e9-190">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="c72e9-191">任意 (フロントエンドサーバーのアドレス、または XMPP ゲートウェイサービスを実行しているフロントエンドプールの IP アドレスとして定義可能)</span><span class="sxs-lookup"><span data-stu-id="c72e9-191">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="c72e9-192">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c72e9-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c72e9-193">フロントエンドサーバーまたはフロントエンドプールで実行されている XMPP ゲートウェイサービスからの送信 XMPP トラフィック</span><span class="sxs-lookup"><span data-stu-id="c72e9-193">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c72e9-194">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="c72e9-194">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c72e9-195">任意 (ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバー、またはフロントエンドプールの IP アドレスとして定義可能)</span><span class="sxs-lookup"><span data-stu-id="c72e9-195">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="c72e9-196">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c72e9-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c72e9-197">(ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバーまたはフロントエンドプールの IP アドレスからの) エッジサーバーの内部インターフェイスへの送信 SIP トラフィック</span><span class="sxs-lookup"><span data-stu-id="c72e9-197">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c72e9-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="c72e9-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c72e9-199">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c72e9-199">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c72e9-200">任意 (ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバー、またはフロントエンドプールの IP アドレスとして定義可能)</span><span class="sxs-lookup"><span data-stu-id="c72e9-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="c72e9-201">エッジサーバーの内部インターフェイスからの受信 SIP トラフィック (ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバー、またはフロントエンドプールの ip アドレス)</span><span class="sxs-lookup"><span data-stu-id="c72e9-201">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c72e9-202">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="c72e9-202">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="c72e9-203">任意 (フロントエンドサーバーの IP アドレスとして、またはフロントエンドプール内の各フロントエンドサーバーの IP アドレスとして定義可能)</span><span class="sxs-lookup"><span data-stu-id="c72e9-203">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="c72e9-204">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c72e9-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c72e9-205">フロントエンドサーバーまたはプール内の各フロントエンドサーバーからエッジサーバーの内部インターフェイスへの Web 会議トラフィック</span><span class="sxs-lookup"><span data-stu-id="c72e9-205">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c72e9-206">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="c72e9-206">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="c72e9-207">Any (このエッジサーバーを使用するフロントエンドサーバーの IP アドレスまたはフロントエンドプールの IP アドレス、または存続可能 Branch Appliance または存続可能ブランチサーバーとして定義できます)</span><span class="sxs-lookup"><span data-stu-id="c72e9-207">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="c72e9-208">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c72e9-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c72e9-209">このエッジサーバーを使用するフロントエンドサーバーまたはフロントエンドプールの IP アドレスまたは任意の存続可能 Branch Appliance または存続可能ブランチサーバーからの音声ビデオユーザーの認証 (音声ビデオ認証サービス)</span><span class="sxs-lookup"><span data-stu-id="c72e9-209">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c72e9-210">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="c72e9-210">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="c72e9-211">任意</span><span class="sxs-lookup"><span data-stu-id="c72e9-211">Any</span></span></p></td>
<td><p><span data-ttu-id="c72e9-212">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c72e9-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c72e9-213">内部ユーザーと外部ユーザーとの間の音声ビデオメディア転送の優先パス、存続可能 Branch Appliance または存続可能 Branch Server</span><span class="sxs-lookup"><span data-stu-id="c72e9-213">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c72e9-214">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="c72e9-214">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c72e9-215">任意</span><span class="sxs-lookup"><span data-stu-id="c72e9-215">Any</span></span></p></td>
<td><p><span data-ttu-id="c72e9-216">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c72e9-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c72e9-217">内部ユーザーと外部ユーザーとの間の音声ビデオメディア転送のフォールバックパス UDP 通信を確立できない場合は、存続可能 Branch Appliance または存続可能 Branch Server、TCP はファイル転送およびデスクトップ共有に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c72e9-217">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c72e9-218">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="c72e9-218">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="c72e9-219">任意 (フロントエンドサーバーの IP アドレス、または中央管理ストアを保持するプールとして定義可能)</span><span class="sxs-lookup"><span data-stu-id="c72e9-219">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="c72e9-220">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c72e9-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c72e9-221">中央管理ストアからエッジ サーバーへの変更のレプリケーション</span><span class="sxs-lookup"><span data-stu-id="c72e9-221">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c72e9-222">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="c72e9-222">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="c72e9-223">任意</span><span class="sxs-lookup"><span data-stu-id="c72e9-223">Any</span></span></p></td>
<td><p><span data-ttu-id="c72e9-224">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c72e9-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c72e9-225">Lync Server 管理シェルと集中ログサービスコマンドレットを使用した集中ログサービスコントローラー、ClsController コマンドライン (ClsController.exe) またはエージェント (ClsAgent.exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="c72e9-225">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c72e9-226">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="c72e9-226">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="c72e9-227">任意</span><span class="sxs-lookup"><span data-stu-id="c72e9-227">Any</span></span></p></td>
<td><p><span data-ttu-id="c72e9-228">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c72e9-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c72e9-229">Lync Server 管理シェルと集中ログサービスコマンドレットを使用した集中ログサービスコントローラー、ClsController コマンドライン (ClsController.exe) またはエージェント (ClsAgent.exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="c72e9-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c72e9-230">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="c72e9-230">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="c72e9-231">任意</span><span class="sxs-lookup"><span data-stu-id="c72e9-231">Any</span></span></p></td>
<td><p><span data-ttu-id="c72e9-232">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c72e9-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c72e9-233">Lync Server 管理シェルと集中ログサービスコマンドレットを使用した集中ログサービスコントローラー、ClsController コマンドライン (ClsController.exe) またはエージェント (ClsAgent.exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="c72e9-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="c72e9-234">フェデレーションのファイアウォールの概要</span><span class="sxs-lookup"><span data-stu-id="c72e9-234">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c72e9-235">役割/プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="c72e9-235">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c72e9-236">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="c72e9-236">Source IP address</span></span></th>
<th><span data-ttu-id="c72e9-237">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="c72e9-237">Destination IP address</span></span></th>
<th><span data-ttu-id="c72e9-238">Notes</span><span class="sxs-lookup"><span data-stu-id="c72e9-238">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c72e9-239">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="c72e9-239">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c72e9-240">アクセス エッジ サービス パブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="c72e9-240">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c72e9-241">任意</span><span class="sxs-lookup"><span data-stu-id="c72e9-241">Any</span></span></p></td>
<td><p><span data-ttu-id="c72e9-242">SIP を使用したフェデレーションおよびパブリック IM 接続用</span><span class="sxs-lookup"><span data-stu-id="c72e9-242">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="c72e9-243">ファイアウォールの概要 ‐ パブリック インスタント メッセージング接続</span><span class="sxs-lookup"><span data-stu-id="c72e9-243">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c72e9-244">役割/プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="c72e9-244">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c72e9-245">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="c72e9-245">Source IP address</span></span></th>
<th><span data-ttu-id="c72e9-246">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="c72e9-246">Destination IP address</span></span></th>
<th><span data-ttu-id="c72e9-247">Notes</span><span class="sxs-lookup"><span data-stu-id="c72e9-247">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c72e9-248">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="c72e9-248">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c72e9-249">パブリック IM 接続パートナー</span><span class="sxs-lookup"><span data-stu-id="c72e9-249">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="c72e9-250">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="c72e9-250">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="c72e9-251">SIP を使用したフェデレーションおよびパブリック IM 接続用</span><span class="sxs-lookup"><span data-stu-id="c72e9-251">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c72e9-252">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="c72e9-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c72e9-253">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="c72e9-253">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="c72e9-254">パブリック IM 接続パートナー</span><span class="sxs-lookup"><span data-stu-id="c72e9-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="c72e9-255">SIP を使用したフェデレーションおよびパブリック IM 接続用</span><span class="sxs-lookup"><span data-stu-id="c72e9-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c72e9-256">アクセス/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="c72e9-256">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c72e9-257">クライアント</span><span class="sxs-lookup"><span data-stu-id="c72e9-257">Clients</span></span></p></td>
<td><p><span data-ttu-id="c72e9-258">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="c72e9-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="c72e9-259">外部ユーザー アクセス用のクライアントからサーバーへの SIP トラフィック</span><span class="sxs-lookup"><span data-stu-id="c72e9-259">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c72e9-260">音声/V/RTP/TCP/50,000-59999</span><span class="sxs-lookup"><span data-stu-id="c72e9-260">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="c72e9-261">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="c72e9-261">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="c72e9-262">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="c72e9-262">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="c72e9-263">パブリック IM 接続が構成されている場合に、Windows Live Messenger との音声ビデオ セッションに使用されます。</span><span class="sxs-lookup"><span data-stu-id="c72e9-263">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c72e9-264">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="c72e9-264">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="c72e9-265">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="c72e9-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="c72e9-266">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="c72e9-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="c72e9-267">Windows Live Messenger とのパブリック IM 接続では必須</span><span class="sxs-lookup"><span data-stu-id="c72e9-267">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c72e9-268">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="c72e9-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="c72e9-269">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="c72e9-269">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="c72e9-270">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="c72e9-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="c72e9-271">Windows Live Messenger とのパブリック IM 接続では必須</span><span class="sxs-lookup"><span data-stu-id="c72e9-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="c72e9-272">XMPP のファイアウォールの概要</span><span class="sxs-lookup"><span data-stu-id="c72e9-272">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c72e9-273">プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="c72e9-273">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c72e9-274">送信元 (IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="c72e9-274">Source (IP address)</span></span></th>
<th><span data-ttu-id="c72e9-275">宛先 (IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="c72e9-275">Destination (IP address)</span></span></th>
<th><span data-ttu-id="c72e9-276">Comments</span><span class="sxs-lookup"><span data-stu-id="c72e9-276">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c72e9-277">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="c72e9-277">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="c72e9-278">任意</span><span class="sxs-lookup"><span data-stu-id="c72e9-278">Any</span></span></p></td>
<td><p><span data-ttu-id="c72e9-279">エッジサーバーアクセスエッジサービスインターフェイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="c72e9-279">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="c72e9-280">XMPP 用の標準的なサーバー間通信。</span><span class="sxs-lookup"><span data-stu-id="c72e9-280">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="c72e9-281">フェデレーションされた XMPP パートナーからのエッジサーバー XMPP プロキシへの通信を許可します。</span><span class="sxs-lookup"><span data-stu-id="c72e9-281">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c72e9-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="c72e9-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="c72e9-283">エッジサーバーアクセスエッジサービスインターフェイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="c72e9-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="c72e9-284">任意</span><span class="sxs-lookup"><span data-stu-id="c72e9-284">Any</span></span></p></td>
<td><p><span data-ttu-id="c72e9-285">XMPP 用の標準的なサーバー間通信。</span><span class="sxs-lookup"><span data-stu-id="c72e9-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="c72e9-286">エッジサーバー XMPP プロキシからフェデレーションされた XMPP パートナーへの通信を許可します。</span><span class="sxs-lookup"><span data-stu-id="c72e9-286">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c72e9-287">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="c72e9-287">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="c72e9-288">任意</span><span class="sxs-lookup"><span data-stu-id="c72e9-288">Any</span></span></p></td>
<td><p><span data-ttu-id="c72e9-289">各内部エッジサーバーインターフェイス IP</span><span class="sxs-lookup"><span data-stu-id="c72e9-289">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="c72e9-290">フロントエンドサーバーまたはフロントエンドプールの XMPP ゲートウェイから、エッジサーバーの内部 IP アドレスまたは各エッジプールメンバーの内部 IP アドレスへの内部 XMPP トラフィック</span><span class="sxs-lookup"><span data-stu-id="c72e9-290">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

