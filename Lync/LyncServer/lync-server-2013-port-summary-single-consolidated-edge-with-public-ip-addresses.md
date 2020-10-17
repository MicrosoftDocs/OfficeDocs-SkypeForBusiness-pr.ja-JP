---
title: ポートの概要-パブリック IP アドレスを使用する単一統合エッジ
description: ポートの概要-パブリック IP アドレスを使用する単一統合エッジ。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single consolidated edge with public IP addresses
ms:assetid: 28407acc-8b92-4f78-875c-fd6b4323b602
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204756(v=OCS.15)
ms:contentKeyID: 48183685
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82ab2d89404fb174994d8e5b798f64bb68768326
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566403"
---
# <a name="port-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="76e65-103">ポートの概要-Lync Server 2013 でのパブリック IP アドレスを使用する単一統合エッジ</span><span class="sxs-lookup"><span data-stu-id="76e65-103">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76e65-104">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="76e65-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="76e65-105">このシナリオアーキテクチャで説明されている Lync server 2013 のエッジサーバー機能は、Lync Server 2010 で実装されていたものとよく似ています。</span><span class="sxs-lookup"><span data-stu-id="76e65-105">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="76e65-106">最も目を引くのは、XMPP (Extensible Messaging and Presence Protocol) 用の ポート **5269/TCP** エントリが追加されたことです。</span><span class="sxs-lookup"><span data-stu-id="76e65-106">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="76e65-107">Lync Server 2013 は、フロントエンドサーバーまたはフロントエンドプールに、エッジサーバーまたはエッジプールおよび XMPP ゲートウェイサーバー上に XMPP プロキシを任意で展開します。</span><span class="sxs-lookup"><span data-stu-id="76e65-107">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span> <span data-ttu-id="76e65-108">リバースプロキシとフェデレーションの計画情報については、「 [Lync server 2013 のリバースプロキシのシナリオ](lync-server-2013-scenarios-for-reverse-proxy.md) 」および「 [lync server 2013 セクションでの SIP、xmpp フェデレーション、パブリックインスタントメッセージングの計画](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76e65-108">Planning information for the reverse proxy and federation are found in [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) and [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) sections, respectively.</span></span>

<span data-ttu-id="76e65-109">IPv4 に加えて、エッジサーバーは IPv6 をサポートするようになりました。</span><span class="sxs-lookup"><span data-stu-id="76e65-109">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="76e65-110">わかりやすいように、シナリオでは IPv4 のみを使用します。</span><span class="sxs-lookup"><span data-stu-id="76e65-110">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="76e65-111">**パブリック IP アドレスを使用する単一統合エッジのエンタープライズ境界ネットワーク**</span><span class="sxs-lookup"><span data-stu-id="76e65-111">**Enterprise perimeter network for single consolidated edge with public IP addressing**</span></span>

<span data-ttu-id="76e65-112">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="76e65-112">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="76e65-113">ポートとプロトコルの詳細</span><span class="sxs-lookup"><span data-stu-id="76e65-113">Port and Protocol Details</span></span>

<span data-ttu-id="76e65-114">外部アクセスを提供する機能のサポートに必要なポートのみを開くことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="76e65-114">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="76e65-p103">エッジ サービスのリモート アクセスが機能するためには、受信/送信のエッジ トラフィックの図が示すように、SIP トラフィックの双方向通過が許可されていることが必須です。つまり、インスタント メッセージング (IM)、プレゼンス、Web 会議、音声ビデオ (A/V)、およびフェデレーションでは、アクセス エッジ サービスとの間で SIP メッセージングが実行されます。</span><span class="sxs-lookup"><span data-stu-id="76e65-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bidirectionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-external-interface"></a><span data-ttu-id="76e65-117">パブリック IP アドレスを使用する単一の統合エッジのファイアウォールの概要: 外部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="76e65-117">Firewall Summary for Single Consolidated Edge with Public IP Addresses: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="76e65-118">役割/プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="76e65-118">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="76e65-119">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="76e65-119">Source IP address</span></span></th>
<th><span data-ttu-id="76e65-120">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="76e65-120">Destination IP address</span></span></th>
<th><span data-ttu-id="76e65-121">Notes</span><span class="sxs-lookup"><span data-stu-id="76e65-121">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76e65-122">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="76e65-122">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="76e65-123">任意</span><span class="sxs-lookup"><span data-stu-id="76e65-123">Any</span></span></p></td>
<td><p><span data-ttu-id="76e65-124">XMPP プロキシサービス (アクセスエッジサービスを使用して IP アドレスを共有)</span><span class="sxs-lookup"><span data-stu-id="76e65-124">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="76e65-125">XMPP プロキシ サービスは、定義された XMPP フェデレーションの XMPP コンタクトからトラフィックを受け付けます</span><span class="sxs-lookup"><span data-stu-id="76e65-125">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76e65-126">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="76e65-126">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="76e65-127">エッジサーバーアクセスエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="76e65-127">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="76e65-128">任意</span><span class="sxs-lookup"><span data-stu-id="76e65-128">Any</span></span></p></td>
<td><p><span data-ttu-id="76e65-129">証明書の失効/CRL のチェックおよび取得</span><span class="sxs-lookup"><span data-stu-id="76e65-129">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76e65-130">アクセス/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="76e65-130">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="76e65-131">エッジサーバーアクセスエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="76e65-131">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="76e65-132">任意</span><span class="sxs-lookup"><span data-stu-id="76e65-132">Any</span></span></p></td>
<td><p><span data-ttu-id="76e65-133">TCP による DNS クエリ</span><span class="sxs-lookup"><span data-stu-id="76e65-133">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76e65-134">アクセス/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="76e65-134">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="76e65-135">エッジサーバーアクセスエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="76e65-135">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="76e65-136">任意</span><span class="sxs-lookup"><span data-stu-id="76e65-136">Any</span></span></p></td>
<td><p><span data-ttu-id="76e65-137">UDP による DNS クエリ</span><span class="sxs-lookup"><span data-stu-id="76e65-137">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76e65-138">アクセス/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="76e65-138">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="76e65-139">任意</span><span class="sxs-lookup"><span data-stu-id="76e65-139">Any</span></span></p></td>
<td><p><span data-ttu-id="76e65-140">エッジサーバーアクセスエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="76e65-140">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="76e65-141">外部ユーザー アクセス用のクライアントからサーバーへの SIP トラフィック</span><span class="sxs-lookup"><span data-stu-id="76e65-141">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76e65-142">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="76e65-142">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="76e65-143">任意</span><span class="sxs-lookup"><span data-stu-id="76e65-143">Any</span></span></p></td>
<td><p><span data-ttu-id="76e65-144">エッジサーバーアクセスエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="76e65-144">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="76e65-145">SIP を使用したフェデレーションおよびパブリック IM 接続用</span><span class="sxs-lookup"><span data-stu-id="76e65-145">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76e65-146">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="76e65-146">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="76e65-147">エッジサーバーアクセスエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="76e65-147">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="76e65-148">任意</span><span class="sxs-lookup"><span data-stu-id="76e65-148">Any</span></span></p></td>
<td><p><span data-ttu-id="76e65-149">SIP を使用したフェデレーションおよびパブリック IM 接続用</span><span class="sxs-lookup"><span data-stu-id="76e65-149">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76e65-150">Web 会議/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="76e65-150">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="76e65-151">任意</span><span class="sxs-lookup"><span data-stu-id="76e65-151">Any</span></span></p></td>
<td><p><span data-ttu-id="76e65-152">エッジサーバー Web 会議エッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="76e65-152">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="76e65-153">Web 会議メディア</span><span class="sxs-lookup"><span data-stu-id="76e65-153">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76e65-154">音声/V/RTP/TCP/50,000-59999</span><span class="sxs-lookup"><span data-stu-id="76e65-154">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="76e65-155">エッジサーバーアクセスエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="76e65-155">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="76e65-156">任意</span><span class="sxs-lookup"><span data-stu-id="76e65-156">Any</span></span></p></td>
<td><p><span data-ttu-id="76e65-157">Office Communications Server 2007、Office Communications Server 2007 R2、Lync Server 2010、Lync Server 2013 を実行しているパートナーとのフェデレーションに必要です。</span><span class="sxs-lookup"><span data-stu-id="76e65-157">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76e65-158">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="76e65-158">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="76e65-159">エッジサーバーの音声ビデオエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="76e65-159">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="76e65-160">任意</span><span class="sxs-lookup"><span data-stu-id="76e65-160">Any</span></span></p></td>
<td><p><span data-ttu-id="76e65-161">Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必要</span><span class="sxs-lookup"><span data-stu-id="76e65-161">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76e65-162">音声/V/RTP/TCP/50,000-59999</span><span class="sxs-lookup"><span data-stu-id="76e65-162">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="76e65-163">任意</span><span class="sxs-lookup"><span data-stu-id="76e65-163">Any</span></span></p></td>
<td><p><span data-ttu-id="76e65-164">エッジサーバーの音声ビデオエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="76e65-164">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="76e65-165">Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必要。</span><span class="sxs-lookup"><span data-stu-id="76e65-165">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76e65-166">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="76e65-166">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="76e65-167">任意</span><span class="sxs-lookup"><span data-stu-id="76e65-167">Any</span></span></p></td>
<td><p><span data-ttu-id="76e65-168">エッジサーバーの音声ビデオエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="76e65-168">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="76e65-169">Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必要。</span><span class="sxs-lookup"><span data-stu-id="76e65-169">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76e65-170">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="76e65-170">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="76e65-171">エッジサーバーの音声ビデオエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="76e65-171">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="76e65-172">任意</span><span class="sxs-lookup"><span data-stu-id="76e65-172">Any</span></span></p></td>
<td><p><span data-ttu-id="76e65-173">3478の送信は、Lync Server の通信相手であるエッジサーバーのバージョンと、エッジサーバー間のメディアトラフィックに使用されます。</span><span class="sxs-lookup"><span data-stu-id="76e65-173">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="76e65-174">Lync Server 2010、Windows Live Messenger、および Office Communications Server 2007 R2 とのフェデレーションに必要です。また、複数のエッジプールが会社内に展開されている場合も必須です。</span><span class="sxs-lookup"><span data-stu-id="76e65-174">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76e65-175">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="76e65-175">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="76e65-176">任意</span><span class="sxs-lookup"><span data-stu-id="76e65-176">Any</span></span></p></td>
<td><p><span data-ttu-id="76e65-177">エッジサーバーの音声ビデオエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="76e65-177">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="76e65-178">STUN/UDP による候補の TURN ネゴシエーション/3478</span><span class="sxs-lookup"><span data-stu-id="76e65-178">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76e65-179">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="76e65-179">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="76e65-180">任意</span><span class="sxs-lookup"><span data-stu-id="76e65-180">Any</span></span></p></td>
<td><p><span data-ttu-id="76e65-181">エッジサーバーの音声ビデオエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="76e65-181">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="76e65-182">STUN/TCP による候補の TURN ネゴシエーション/443</span><span class="sxs-lookup"><span data-stu-id="76e65-182">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76e65-183">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="76e65-183">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="76e65-184">エッジサーバーの音声ビデオエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="76e65-184">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="76e65-185">任意</span><span class="sxs-lookup"><span data-stu-id="76e65-185">Any</span></span></p></td>
<td><p><span data-ttu-id="76e65-186">STUN/TCP による候補の TURN ネゴシエーション/443</span><span class="sxs-lookup"><span data-stu-id="76e65-186">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-internal-interface"></a><span data-ttu-id="76e65-187">パブリック IP アドレスを使用する単一の統合エッジのファイアウォールの概要: 内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="76e65-187">Firewall Summary for Single Consolidated Edge with Public IP Addresses: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="76e65-188">プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="76e65-188">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="76e65-189">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="76e65-189">Source IP address</span></span></th>
<th><span data-ttu-id="76e65-190">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="76e65-190">Destination IP address</span></span></th>
<th><span data-ttu-id="76e65-191">Comments</span><span class="sxs-lookup"><span data-stu-id="76e65-191">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76e65-192">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="76e65-192">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="76e65-193">Any (Standard Edition サーバー IP、Standard Edition サーバー IP アドレス、または XMPP ゲートウェイサービスを実行しているプール IP アドレスとして定義できます)</span><span class="sxs-lookup"><span data-stu-id="76e65-193">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="76e65-194">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="76e65-194">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="76e65-195">フロントエンドサーバーまたはフロントエンドプールで実行されている XMPP ゲートウェイサービスからの送信 XMPP トラフィック</span><span class="sxs-lookup"><span data-stu-id="76e65-195">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76e65-196">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="76e65-196">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="76e65-197">任意 (ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバー、またはフロントエンドプールの IP アドレスとして定義可能)</span><span class="sxs-lookup"><span data-stu-id="76e65-197">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="76e65-198">エッジサーバー IP、または内部インターフェイスを保持するプール</span><span class="sxs-lookup"><span data-stu-id="76e65-198">Edge Server IP, or pool that holds the internal interface</span></span></p></td>
<td><p><span data-ttu-id="76e65-199">(ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバーまたはフロントエンドプールの IP アドレスからの) エッジサーバーの内部インターフェイスへの送信 SIP トラフィック</span><span class="sxs-lookup"><span data-stu-id="76e65-199">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76e65-200">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="76e65-200">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="76e65-201">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="76e65-201">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="76e65-202">任意 (ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバー、またはフロントエンドプールのアドレスとして定義可能)</span><span class="sxs-lookup"><span data-stu-id="76e65-202">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool address)</span></span></p></td>
<td><p><span data-ttu-id="76e65-203">エッジサーバーの内部インターフェイスからの受信 SIP トラフィック (ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバー、またはフロントエンドプールの ip アドレス)</span><span class="sxs-lookup"><span data-stu-id="76e65-203">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76e65-204">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="76e65-204">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="76e65-205">任意 (フロントエンドサーバーの IP アドレスとして、またはフロントエンドプール内の各フロントエンドサーバーの IP アドレスとして定義可能)</span><span class="sxs-lookup"><span data-stu-id="76e65-205">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="76e65-206">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="76e65-206">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="76e65-207">フロントエンドサーバーまたはプール内の各フロントエンドサーバーからエッジサーバーの内部インターフェイスへの Web 会議トラフィック</span><span class="sxs-lookup"><span data-stu-id="76e65-207">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76e65-208">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="76e65-208">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="76e65-209">Any (このエッジサーバーを使用するフロントエンドサーバーの IP アドレスまたはフロントエンドプールの IP アドレス、または存続可能 Branch Appliance または存続可能ブランチサーバーとして定義できます)</span><span class="sxs-lookup"><span data-stu-id="76e65-209">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="76e65-210">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="76e65-210">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="76e65-211">このエッジサーバーを使用するフロントエンドサーバーまたはフロントエンドプールの IP アドレスまたは任意の存続可能 Branch Appliance または存続可能ブランチサーバーからの音声ビデオユーザーの認証 (音声ビデオ認証サービス)</span><span class="sxs-lookup"><span data-stu-id="76e65-211">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76e65-212">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="76e65-212">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="76e65-213">任意</span><span class="sxs-lookup"><span data-stu-id="76e65-213">Any</span></span></p></td>
<td><p><span data-ttu-id="76e65-214">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="76e65-214">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="76e65-215">内部ユーザーと外部ユーザーとの間の音声ビデオメディア転送の優先パス、存続可能 Branch Appliance または存続可能 Branch Server</span><span class="sxs-lookup"><span data-stu-id="76e65-215">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76e65-216">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="76e65-216">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="76e65-217">任意</span><span class="sxs-lookup"><span data-stu-id="76e65-217">Any</span></span></p></td>
<td><p><span data-ttu-id="76e65-218">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="76e65-218">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="76e65-219">内部ユーザーと外部ユーザーとの間の音声ビデオメディア転送のフォールバックパス UDP 通信を確立できない場合は、存続可能 Branch Appliance または存続可能 Branch Server、TCP はファイル転送およびデスクトップ共有に使用されます。</span><span class="sxs-lookup"><span data-stu-id="76e65-219">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76e65-220">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="76e65-220">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="76e65-221">任意 (フロントエンドサーバーの IP アドレス、または中央管理ストアを保持するプールとして定義可能)</span><span class="sxs-lookup"><span data-stu-id="76e65-221">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="76e65-222">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="76e65-222">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="76e65-223">中央管理ストアからエッジ サーバーへの変更のレプリケーション</span><span class="sxs-lookup"><span data-stu-id="76e65-223">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76e65-224">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="76e65-224">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="76e65-225">任意</span><span class="sxs-lookup"><span data-stu-id="76e65-225">Any</span></span></p></td>
<td><p><span data-ttu-id="76e65-226">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="76e65-226">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="76e65-227">Lync Server 管理シェルと集中ログサービスコマンドレットを使用した集中ログサービスコントローラー、ClsController コマンドライン (ClsController.exe) またはエージェント (ClsAgent.exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="76e65-227">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76e65-228">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="76e65-228">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="76e65-229">任意</span><span class="sxs-lookup"><span data-stu-id="76e65-229">Any</span></span></p></td>
<td><p><span data-ttu-id="76e65-230">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="76e65-230">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="76e65-231">Lync Server 管理シェルと集中ログサービスコマンドレットを使用した集中ログサービスコントローラー、ClsController コマンドライン (ClsController.exe) またはエージェント (ClsAgent.exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="76e65-231">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76e65-232">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="76e65-232">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="76e65-233">任意</span><span class="sxs-lookup"><span data-stu-id="76e65-233">Any</span></span></p></td>
<td><p><span data-ttu-id="76e65-234">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="76e65-234">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="76e65-235">Lync Server 管理シェルと集中ログサービスコマンドレットを使用した集中ログサービスコントローラー、ClsController コマンドライン (ClsController.exe) またはエージェント (ClsAgent.exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="76e65-235">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="76e65-236">フェデレーションのファイアウォールの概要</span><span class="sxs-lookup"><span data-stu-id="76e65-236">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="76e65-237">役割/プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="76e65-237">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="76e65-238">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="76e65-238">Source IP address</span></span></th>
<th><span data-ttu-id="76e65-239">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="76e65-239">Destination IP address</span></span></th>
<th><span data-ttu-id="76e65-240">Notes</span><span class="sxs-lookup"><span data-stu-id="76e65-240">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76e65-241">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="76e65-241">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="76e65-242">アクセス エッジ サービス パブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="76e65-242">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="76e65-243">任意</span><span class="sxs-lookup"><span data-stu-id="76e65-243">Any</span></span></p></td>
<td><p><span data-ttu-id="76e65-244">SIP を使用したフェデレーションおよびパブリック IM 接続用</span><span class="sxs-lookup"><span data-stu-id="76e65-244">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="76e65-245">ファイアウォールの概要 ‐ パブリック インスタント メッセージング接続</span><span class="sxs-lookup"><span data-stu-id="76e65-245">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="76e65-246">役割/プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="76e65-246">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="76e65-247">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="76e65-247">Source IP address</span></span></th>
<th><span data-ttu-id="76e65-248">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="76e65-248">Destination IP address</span></span></th>
<th><span data-ttu-id="76e65-249">Notes</span><span class="sxs-lookup"><span data-stu-id="76e65-249">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76e65-250">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="76e65-250">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="76e65-251">パブリック IM 接続パートナー</span><span class="sxs-lookup"><span data-stu-id="76e65-251">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="76e65-252">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="76e65-252">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="76e65-253">SIP を使用したフェデレーションおよびパブリック IM 接続用</span><span class="sxs-lookup"><span data-stu-id="76e65-253">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76e65-254">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="76e65-254">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="76e65-255">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="76e65-255">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="76e65-256">パブリック IM 接続パートナー</span><span class="sxs-lookup"><span data-stu-id="76e65-256">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="76e65-257">SIP を使用したフェデレーションおよびパブリック IM 接続用</span><span class="sxs-lookup"><span data-stu-id="76e65-257">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76e65-258">アクセス/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="76e65-258">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="76e65-259">クライアント</span><span class="sxs-lookup"><span data-stu-id="76e65-259">Clients</span></span></p></td>
<td><p><span data-ttu-id="76e65-260">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="76e65-260">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="76e65-261">外部ユーザー アクセス用のクライアントからサーバーへの SIP トラフィック</span><span class="sxs-lookup"><span data-stu-id="76e65-261">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76e65-262">音声/V/RTP/TCP/50,000-59999</span><span class="sxs-lookup"><span data-stu-id="76e65-262">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="76e65-263">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="76e65-263">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="76e65-264">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="76e65-264">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="76e65-265">パブリック IM 接続が構成されている場合に、Windows Live Messenger との音声ビデオ セッションに使用されます。</span><span class="sxs-lookup"><span data-stu-id="76e65-265">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76e65-266">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="76e65-266">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="76e65-267">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="76e65-267">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="76e65-268">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="76e65-268">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="76e65-269">Windows Live Messenger とのパブリック IM 接続では必須</span><span class="sxs-lookup"><span data-stu-id="76e65-269">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76e65-270">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="76e65-270">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="76e65-271">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="76e65-271">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="76e65-272">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="76e65-272">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="76e65-273">Windows Live Messenger とのパブリック IM 接続では必須</span><span class="sxs-lookup"><span data-stu-id="76e65-273">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="76e65-274">XMPP のファイアウォールの概要</span><span class="sxs-lookup"><span data-stu-id="76e65-274">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="76e65-275">プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="76e65-275">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="76e65-276">送信元 (IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="76e65-276">Source (IP address)</span></span></th>
<th><span data-ttu-id="76e65-277">宛先 (IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="76e65-277">Destination (IP address)</span></span></th>
<th><span data-ttu-id="76e65-278">Comments</span><span class="sxs-lookup"><span data-stu-id="76e65-278">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76e65-279">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="76e65-279">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="76e65-280">任意</span><span class="sxs-lookup"><span data-stu-id="76e65-280">Any</span></span></p></td>
<td><p><span data-ttu-id="76e65-281">エッジサーバーアクセスエッジサービスインターフェイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="76e65-281">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="76e65-282">XMPP 用の標準的なサーバー間通信。</span><span class="sxs-lookup"><span data-stu-id="76e65-282">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="76e65-283">フェデレーションされた XMPP パートナーからのエッジサーバー XMPP プロキシへの通信を許可します。</span><span class="sxs-lookup"><span data-stu-id="76e65-283">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76e65-284">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="76e65-284">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="76e65-285">エッジサーバーアクセスエッジサービスインターフェイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="76e65-285">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="76e65-286">任意</span><span class="sxs-lookup"><span data-stu-id="76e65-286">Any</span></span></p></td>
<td><p><span data-ttu-id="76e65-287">XMPP 用の標準的なサーバー間通信。</span><span class="sxs-lookup"><span data-stu-id="76e65-287">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="76e65-288">エッジサーバー XMPP プロキシからフェデレーションされた XMPP パートナーへの通信を許可します。</span><span class="sxs-lookup"><span data-stu-id="76e65-288">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76e65-289">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="76e65-289">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="76e65-290">任意</span><span class="sxs-lookup"><span data-stu-id="76e65-290">Any</span></span></p></td>
<td><p><span data-ttu-id="76e65-291">各内部エッジサーバーインターフェイス IP</span><span class="sxs-lookup"><span data-stu-id="76e65-291">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="76e65-292">フロントエンドサーバーまたはフロントエンドプールの XMPP ゲートウェイから、エッジサーバーの内部 IP アドレスまたは各エッジプールメンバーの内部 IP アドレスへの内部 XMPP トラフィック</span><span class="sxs-lookup"><span data-stu-id="76e65-292">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

