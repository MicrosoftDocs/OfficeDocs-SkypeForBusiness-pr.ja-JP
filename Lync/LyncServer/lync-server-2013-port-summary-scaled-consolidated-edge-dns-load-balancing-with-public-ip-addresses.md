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
ms.openlocfilehash: df1a650feb27a4f104ae4077d0bf7d541cc5d7d9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152635"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="bf8b5-102">ポートの概要-Lync Server 2013 での拡張統合エッジ、パブリック IP アドレスを使用した DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="bf8b5-102">Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf8b5-103">_**トピックの最終更新日:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="bf8b5-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="bf8b5-104">このシナリオアーキテクチャで説明されている Lync server 2013 のエッジサーバー機能は、Lync Server 2010 で実装されていたものとよく似ています。</span><span class="sxs-lookup"><span data-stu-id="bf8b5-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="bf8b5-105">最も目を引くのは、XMPP (Extensible Messaging and Presence Protocol) 用の ポート **5269/TCP** エントリが追加されたことです。</span><span class="sxs-lookup"><span data-stu-id="bf8b5-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="bf8b5-106">Lync Server 2013 は、フロントエンドサーバーまたはフロントエンドプールに、エッジサーバーまたはエッジプールおよび XMPP ゲートウェイサーバー上に XMPP プロキシを任意で展開します。</span><span class="sxs-lookup"><span data-stu-id="bf8b5-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="bf8b5-107">IPv4 に加えて、エッジサーバーは IPv6 をサポートするようになりました。</span><span class="sxs-lookup"><span data-stu-id="bf8b5-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="bf8b5-108">わかりやすいように、シナリオでは IPv4 のみを使用します。</span><span class="sxs-lookup"><span data-stu-id="bf8b5-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="bf8b5-109">**拡張統合エッジ、パブリック IP アドレスによる DNS 負荷分散のためのエンタープライズ境界ネットワーク**</span><span class="sxs-lookup"><span data-stu-id="bf8b5-109">**Enterprise perimeter network for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses**</span></span>

<span data-ttu-id="bf8b5-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="bf8b5-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="bf8b5-111">ポートとプロトコルの詳細</span><span class="sxs-lookup"><span data-stu-id="bf8b5-111">Port and Protocol Details</span></span>

<span data-ttu-id="bf8b5-112">外部アクセスを提供する機能のサポートに必要なポートのみを開くことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bf8b5-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="bf8b5-p103">エッジ サービスのリモート アクセスが機能するためには、受信/送信のエッジ トラフィックの図が示すように、SIP トラフィックの双方向通過が許可されていることが必須です。つまり、インスタント メッセージング (IM)、プレゼンス、Web 会議、音声ビデオ (A/V)、およびフェデレーションでは、アクセス エッジ サービスとの間で SIP メッセージングが実行されます。</span><span class="sxs-lookup"><span data-stu-id="bf8b5-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="bf8b5-115">拡張統合エッジ、パブリック IP アドレスを使用した DNS 負荷分散のためのファイアウォールの概要: 外部インターフェイス–ノード1およびノード 2 (例)</span><span class="sxs-lookup"><span data-stu-id="bf8b5-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bf8b5-116">役割/プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="bf8b5-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="bf8b5-117">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-117">Source IP address</span></span></th>
<th><span data-ttu-id="bf8b5-118">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-118">Destination IP address</span></span></th>
<th><span data-ttu-id="bf8b5-119">メモ</span><span class="sxs-lookup"><span data-stu-id="bf8b5-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bf8b5-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="bf8b5-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-121">任意</span><span class="sxs-lookup"><span data-stu-id="bf8b5-121">Any</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-122">XMPP プロキシサービス (アクセスエッジサービスを使用して IP アドレスを共有)</span><span class="sxs-lookup"><span data-stu-id="bf8b5-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-123">XMPP プロキシ サービスは、定義された XMPP フェデレーションの XMPP コンタクトからトラフィックを受け付けます</span><span class="sxs-lookup"><span data-stu-id="bf8b5-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf8b5-124">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="bf8b5-124">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-125">エッジサーバーアクセスエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-125">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-126">任意</span><span class="sxs-lookup"><span data-stu-id="bf8b5-126">Any</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-127">証明書の失効/CRL のチェックおよび取得</span><span class="sxs-lookup"><span data-stu-id="bf8b5-127">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf8b5-128">アクセス/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="bf8b5-128">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-129">エッジサーバーアクセスエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-129">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-130">任意</span><span class="sxs-lookup"><span data-stu-id="bf8b5-130">Any</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-131">TCP による DNS クエリ</span><span class="sxs-lookup"><span data-stu-id="bf8b5-131">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf8b5-132">アクセス/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="bf8b5-132">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-133">エッジサーバーアクセスエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-133">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-134">任意</span><span class="sxs-lookup"><span data-stu-id="bf8b5-134">Any</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-135">UDP による DNS クエリ</span><span class="sxs-lookup"><span data-stu-id="bf8b5-135">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf8b5-136">アクセス/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="bf8b5-136">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-137">任意</span><span class="sxs-lookup"><span data-stu-id="bf8b5-137">Any</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-138">エッジサーバーアクセスエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-138">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-139">外部ユーザー アクセス用のクライアントからサーバーへの SIP トラフィック</span><span class="sxs-lookup"><span data-stu-id="bf8b5-139">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf8b5-140">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="bf8b5-140">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-141">任意</span><span class="sxs-lookup"><span data-stu-id="bf8b5-141">Any</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-142">エッジサーバーアクセスエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-142">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-143">SIP を使用したフェデレーションおよびパブリック IM 接続用</span><span class="sxs-lookup"><span data-stu-id="bf8b5-143">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf8b5-144">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="bf8b5-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-145">エッジサーバーアクセスエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-145">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-146">任意</span><span class="sxs-lookup"><span data-stu-id="bf8b5-146">Any</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-147">SIP を使用したフェデレーションおよびパブリック IM 接続用</span><span class="sxs-lookup"><span data-stu-id="bf8b5-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf8b5-148">Web 会議/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="bf8b5-148">Web Conferencing/PSOM(TLS)TCP/443</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-149">任意</span><span class="sxs-lookup"><span data-stu-id="bf8b5-149">Any</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-150">エッジサーバー Web 会議エッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-150">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-151">Web 会議メディア</span><span class="sxs-lookup"><span data-stu-id="bf8b5-151">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf8b5-152">音声/V/RTP/TCP/50,000-59999</span><span class="sxs-lookup"><span data-stu-id="bf8b5-152">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-153">エッジサーバーの音声ビデオエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-153">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-154">任意</span><span class="sxs-lookup"><span data-stu-id="bf8b5-154">Any</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-155">Office Communications Server 2007、Office Communications Server 2007 R2、Lync Server 2010、Lync Server 2013 を実行しているパートナーとのフェデレーションに必要です。</span><span class="sxs-lookup"><span data-stu-id="bf8b5-155">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf8b5-156">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="bf8b5-156">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-157">エッジサーバーの音声ビデオエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-157">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-158">任意</span><span class="sxs-lookup"><span data-stu-id="bf8b5-158">Any</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-159">Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必要。</span><span class="sxs-lookup"><span data-stu-id="bf8b5-159">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf8b5-160">音声/V/RTP/TCP/50,000-59999</span><span class="sxs-lookup"><span data-stu-id="bf8b5-160">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-161">任意</span><span class="sxs-lookup"><span data-stu-id="bf8b5-161">Any</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-162">エッジサーバーの音声ビデオエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-162">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-163">Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必要</span><span class="sxs-lookup"><span data-stu-id="bf8b5-163">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf8b5-164">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="bf8b5-164">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-165">任意</span><span class="sxs-lookup"><span data-stu-id="bf8b5-165">Any</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-166">エッジサーバーの音声ビデオエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-166">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-167">Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必要</span><span class="sxs-lookup"><span data-stu-id="bf8b5-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf8b5-168">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="bf8b5-168">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-169">エッジサーバーの音声ビデオエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-169">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-170">任意</span><span class="sxs-lookup"><span data-stu-id="bf8b5-170">Any</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-171">3478の送信は、Lync Server の通信相手であるエッジサーバーのバージョンと、エッジサーバー間のメディアトラフィックに使用されます。</span><span class="sxs-lookup"><span data-stu-id="bf8b5-171">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="bf8b5-172">Lync Server 2010、Windows Live Messenger、および Office Communications Server 2007 R2 とのフェデレーションに必要です。また、複数のエッジプールが会社内に展開されている場合も必須です。</span><span class="sxs-lookup"><span data-stu-id="bf8b5-172">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf8b5-173">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="bf8b5-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-174">任意</span><span class="sxs-lookup"><span data-stu-id="bf8b5-174">Any</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-175">エッジサーバーの音声ビデオエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-175">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-176">STUN/UDP による候補の TURN ネゴシエーション/3478</span><span class="sxs-lookup"><span data-stu-id="bf8b5-176">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf8b5-177">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="bf8b5-177">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-178">任意</span><span class="sxs-lookup"><span data-stu-id="bf8b5-178">Any</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-179">エッジサーバーの音声ビデオエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-179">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-180">STUN/TCP による候補の TURN ネゴシエーション/443</span><span class="sxs-lookup"><span data-stu-id="bf8b5-180">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf8b5-181">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="bf8b5-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-182">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-182">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-183">任意</span><span class="sxs-lookup"><span data-stu-id="bf8b5-183">Any</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-184">STUN/TCP による候補の TURN ネゴシエーション/443</span><span class="sxs-lookup"><span data-stu-id="bf8b5-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="bf8b5-185">拡張統合エッジ、パブリック IP アドレスを使用した DNS 負荷分散のためのファイアウォールの概要: 内部インターフェイス – ノード 1 およびノード 2 (例)</span><span class="sxs-lookup"><span data-stu-id="bf8b5-185">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bf8b5-186">プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="bf8b5-186">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="bf8b5-187">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-187">Source IP address</span></span></th>
<th><span data-ttu-id="bf8b5-188">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-188">Destination IP address</span></span></th>
<th><span data-ttu-id="bf8b5-189">コメント</span><span class="sxs-lookup"><span data-stu-id="bf8b5-189">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bf8b5-190">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="bf8b5-190">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-191">任意 (フロントエンドサーバーのアドレス、または XMPP ゲートウェイサービスを実行しているフロントエンドプールの IP アドレスとして定義可能)</span><span class="sxs-lookup"><span data-stu-id="bf8b5-191">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-192">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-193">フロントエンドサーバーまたはフロントエンドプールで実行されている XMPP ゲートウェイサービスからの送信 XMPP トラフィック</span><span class="sxs-lookup"><span data-stu-id="bf8b5-193">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf8b5-194">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="bf8b5-194">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-195">任意 (ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバー、またはフロントエンドプールの IP アドレスとして定義可能)</span><span class="sxs-lookup"><span data-stu-id="bf8b5-195">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-196">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-197">(ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバーまたはフロントエンドプールの IP アドレスからの) エッジサーバーの内部インターフェイスへの送信 SIP トラフィック</span><span class="sxs-lookup"><span data-stu-id="bf8b5-197">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf8b5-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="bf8b5-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-199">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-199">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-200">任意 (ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバー、またはフロントエンドプールの IP アドレスとして定義可能)</span><span class="sxs-lookup"><span data-stu-id="bf8b5-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-201">エッジサーバーの内部インターフェイスからの受信 SIP トラフィック (ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバー、またはフロントエンドプールの ip アドレス)</span><span class="sxs-lookup"><span data-stu-id="bf8b5-201">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf8b5-202">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="bf8b5-202">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-203">任意 (フロントエンドサーバーの IP アドレスとして、またはフロントエンドプール内の各フロントエンドサーバーの IP アドレスとして定義可能)</span><span class="sxs-lookup"><span data-stu-id="bf8b5-203">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-204">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-205">フロントエンドサーバーまたはプール内の各フロントエンドサーバーからエッジサーバーの内部インターフェイスへの Web 会議トラフィック</span><span class="sxs-lookup"><span data-stu-id="bf8b5-205">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf8b5-206">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="bf8b5-206">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-207">Any (このエッジサーバーを使用するフロントエンドサーバーの IP アドレスまたはフロントエンドプールの IP アドレス、または存続可能 Branch Appliance または存続可能ブランチサーバーとして定義できます)</span><span class="sxs-lookup"><span data-stu-id="bf8b5-207">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-208">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-209">このエッジサーバーを使用するフロントエンドサーバーまたはフロントエンドプールの IP アドレスまたは任意の存続可能 Branch Appliance または存続可能ブランチサーバーからの音声ビデオユーザーの認証 (音声ビデオ認証サービス)</span><span class="sxs-lookup"><span data-stu-id="bf8b5-209">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf8b5-210">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="bf8b5-210">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-211">任意</span><span class="sxs-lookup"><span data-stu-id="bf8b5-211">Any</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-212">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-213">内部ユーザーと外部ユーザーとの間の音声ビデオメディア転送の優先パス、存続可能 Branch Appliance または存続可能 Branch Server</span><span class="sxs-lookup"><span data-stu-id="bf8b5-213">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf8b5-214">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="bf8b5-214">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-215">任意</span><span class="sxs-lookup"><span data-stu-id="bf8b5-215">Any</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-216">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-217">内部ユーザーと外部ユーザーとの間の音声ビデオメディア転送のフォールバックパス UDP 通信を確立できない場合は、存続可能 Branch Appliance または存続可能 Branch Server、TCP はファイル転送およびデスクトップ共有に使用されます。</span><span class="sxs-lookup"><span data-stu-id="bf8b5-217">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf8b5-218">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="bf8b5-218">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-219">任意 (フロントエンドサーバーの IP アドレス、または中央管理ストアを保持するプールとして定義可能)</span><span class="sxs-lookup"><span data-stu-id="bf8b5-219">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-220">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-221">中央管理ストアからエッジ サーバーへの変更のレプリケーション</span><span class="sxs-lookup"><span data-stu-id="bf8b5-221">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf8b5-222">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="bf8b5-222">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-223">任意</span><span class="sxs-lookup"><span data-stu-id="bf8b5-223">Any</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-224">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-225">Lync Server 管理シェルと集中ログサービスコマンドレットを使用した集中ログサービスコントローラー、ClsController コマンドライン (ClsController) またはエージェント (Clscontroller. .exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="bf8b5-225">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf8b5-226">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="bf8b5-226">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-227">任意</span><span class="sxs-lookup"><span data-stu-id="bf8b5-227">Any</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-228">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-229">Lync Server 管理シェルと集中ログサービスコマンドレットを使用した集中ログサービスコントローラー、ClsController コマンドライン (ClsController) またはエージェント (Clscontroller. .exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="bf8b5-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf8b5-230">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="bf8b5-230">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-231">任意</span><span class="sxs-lookup"><span data-stu-id="bf8b5-231">Any</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-232">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-233">Lync Server 管理シェルと集中ログサービスコマンドレットを使用した集中ログサービスコントローラー、ClsController コマンドライン (ClsController) またはエージェント (Clscontroller. .exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="bf8b5-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="bf8b5-234">フェデレーションのファイアウォールの概要</span><span class="sxs-lookup"><span data-stu-id="bf8b5-234">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bf8b5-235">役割/プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="bf8b5-235">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="bf8b5-236">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-236">Source IP address</span></span></th>
<th><span data-ttu-id="bf8b5-237">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-237">Destination IP address</span></span></th>
<th><span data-ttu-id="bf8b5-238">メモ</span><span class="sxs-lookup"><span data-stu-id="bf8b5-238">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bf8b5-239">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="bf8b5-239">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-240">アクセス エッジ サービス パブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-240">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-241">任意</span><span class="sxs-lookup"><span data-stu-id="bf8b5-241">Any</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-242">SIP を使用したフェデレーションおよびパブリック IM 接続用</span><span class="sxs-lookup"><span data-stu-id="bf8b5-242">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="bf8b5-243">ファイアウォールの概要 ‐ パブリック インスタント メッセージング接続</span><span class="sxs-lookup"><span data-stu-id="bf8b5-243">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bf8b5-244">役割/プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="bf8b5-244">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="bf8b5-245">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-245">Source IP address</span></span></th>
<th><span data-ttu-id="bf8b5-246">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-246">Destination IP address</span></span></th>
<th><span data-ttu-id="bf8b5-247">メモ</span><span class="sxs-lookup"><span data-stu-id="bf8b5-247">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bf8b5-248">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="bf8b5-248">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-249">パブリック IM 接続パートナー</span><span class="sxs-lookup"><span data-stu-id="bf8b5-249">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-250">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-250">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-251">SIP を使用したフェデレーションおよびパブリック IM 接続用</span><span class="sxs-lookup"><span data-stu-id="bf8b5-251">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf8b5-252">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="bf8b5-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-253">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-253">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-254">パブリック IM 接続パートナー</span><span class="sxs-lookup"><span data-stu-id="bf8b5-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-255">SIP を使用したフェデレーションおよびパブリック IM 接続用</span><span class="sxs-lookup"><span data-stu-id="bf8b5-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf8b5-256">アクセス/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="bf8b5-256">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-257">クライアント</span><span class="sxs-lookup"><span data-stu-id="bf8b5-257">Clients</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-258">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-259">外部ユーザー アクセス用のクライアントからサーバーへの SIP トラフィック</span><span class="sxs-lookup"><span data-stu-id="bf8b5-259">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf8b5-260">音声/V/RTP/TCP/50,000-59999</span><span class="sxs-lookup"><span data-stu-id="bf8b5-260">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-261">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-261">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-262">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="bf8b5-262">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-263">パブリック IM 接続が構成されている場合に、Windows Live Messenger との音声ビデオ セッションに使用されます。</span><span class="sxs-lookup"><span data-stu-id="bf8b5-263">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf8b5-264">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="bf8b5-264">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-265">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-266">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="bf8b5-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-267">Windows Live Messenger とのパブリック IM 接続では必須</span><span class="sxs-lookup"><span data-stu-id="bf8b5-267">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf8b5-268">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="bf8b5-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-269">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="bf8b5-269">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-270">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-271">Windows Live Messenger とのパブリック IM 接続では必須</span><span class="sxs-lookup"><span data-stu-id="bf8b5-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="bf8b5-272">XMPP のファイアウォールの概要</span><span class="sxs-lookup"><span data-stu-id="bf8b5-272">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bf8b5-273">プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="bf8b5-273">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="bf8b5-274">送信元 (IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="bf8b5-274">Source (IP address)</span></span></th>
<th><span data-ttu-id="bf8b5-275">宛先 (IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="bf8b5-275">Destination (IP address)</span></span></th>
<th><span data-ttu-id="bf8b5-276">コメント</span><span class="sxs-lookup"><span data-stu-id="bf8b5-276">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bf8b5-277">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="bf8b5-277">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-278">任意</span><span class="sxs-lookup"><span data-stu-id="bf8b5-278">Any</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-279">エッジサーバーアクセスエッジサービスインターフェイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-279">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-280">XMPP 用の標準的なサーバー間通信。</span><span class="sxs-lookup"><span data-stu-id="bf8b5-280">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="bf8b5-281">フェデレーションされた XMPP パートナーからのエッジサーバー XMPP プロキシへの通信を許可します。</span><span class="sxs-lookup"><span data-stu-id="bf8b5-281">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf8b5-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="bf8b5-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-283">エッジサーバーアクセスエッジサービスインターフェイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="bf8b5-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-284">任意</span><span class="sxs-lookup"><span data-stu-id="bf8b5-284">Any</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-285">XMPP 用の標準的なサーバー間通信。</span><span class="sxs-lookup"><span data-stu-id="bf8b5-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="bf8b5-286">エッジサーバー XMPP プロキシからフェデレーションされた XMPP パートナーへの通信を許可します。</span><span class="sxs-lookup"><span data-stu-id="bf8b5-286">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf8b5-287">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="bf8b5-287">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-288">任意</span><span class="sxs-lookup"><span data-stu-id="bf8b5-288">Any</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-289">各内部エッジサーバーインターフェイス IP</span><span class="sxs-lookup"><span data-stu-id="bf8b5-289">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="bf8b5-290">フロントエンドサーバーまたはフロントエンドプールの XMPP ゲートウェイから、エッジサーバーの内部 IP アドレスまたは各エッジプールメンバーの内部 IP アドレスへの内部 XMPP トラフィック</span><span class="sxs-lookup"><span data-stu-id="bf8b5-290">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

