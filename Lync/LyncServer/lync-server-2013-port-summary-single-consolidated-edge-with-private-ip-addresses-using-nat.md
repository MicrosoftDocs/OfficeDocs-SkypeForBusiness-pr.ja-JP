---
title: ポートの概要-NAT を使用したプライベート IP アドレスを持つ単一統合エッジ
description: ポートの概要-NAT を使用したプライベート IP アドレスを持つ単一統合エッジ。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: 3c1a389f-5f42-4719-a05b-e0b84aa3eb9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425891(v=OCS.15)
ms:contentKeyID: 48183877
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3fc182b9fbbd24d589feb7f73e3c0086fa23152
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564563"
---
# <a name="port-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="f2894-103">ポートの概要-Lync Server 2013 で NAT を使用するプライベート IP アドレスを持つ単一統合エッジ</span><span class="sxs-lookup"><span data-stu-id="f2894-103">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2894-104">_**トピックの最終更新日:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="f2894-104">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="f2894-105">このシナリオアーキテクチャで説明されている Lync server 2013 のエッジサーバー機能は、Lync Server 2010 で実装されていたものとよく似ています。</span><span class="sxs-lookup"><span data-stu-id="f2894-105">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="f2894-106">最も目を引くのは、XMPP (Extensible Messaging and Presence Protocol) 用の ポート **5269/TCP** エントリが追加されたことです。</span><span class="sxs-lookup"><span data-stu-id="f2894-106">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="f2894-107">Lync Server 2013 は、フロントエンドサーバーまたはフロントエンドプールに、エッジサーバーまたはエッジプールおよび XMPP ゲートウェイサーバー上に XMPP プロキシを任意で展開します。</span><span class="sxs-lookup"><span data-stu-id="f2894-107">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="f2894-108">IPv4 に加えて、エッジサーバーは IPv6 をサポートするようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2894-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="f2894-109">わかりやすいように、シナリオでは IPv4 のみを使用します。</span><span class="sxs-lookup"><span data-stu-id="f2894-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="f2894-110">**NAT を使用したプライベート IP アドレスを使用する単一の統合エッジサーバーのネットワーク境界**</span><span class="sxs-lookup"><span data-stu-id="f2894-110">**Network Perimeter for a Single Consolidated Edge Server with Private IP Addressing Using NAT**</span></span>

<span data-ttu-id="f2894-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="f2894-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="f2894-112">ポートとプロトコルの詳細</span><span class="sxs-lookup"><span data-stu-id="f2894-112">Port and Protocol Details</span></span>

<span data-ttu-id="f2894-113">外部アクセスが可能な機能のサポートに必要なポートのみを開くことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f2894-113">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="f2894-114">エッジ サービスのリモート アクセスが機能するためには、受信/送信のエッジ トラフィックの図が示すように、SIP トラフィックの双方向通過が許可されていることが必須です。</span><span class="sxs-lookup"><span data-stu-id="f2894-114">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="f2894-115">もう1つの方法として、アクセスエッジサービスとの間の SIP メッセージングは、インスタントメッセージング (IM)、プレゼンス、web 会議、音声ビデオ (A/V)、およびフェデレーションに関係しています。</span><span class="sxs-lookup"><span data-stu-id="f2894-115">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V), and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-external-interface"></a><span data-ttu-id="f2894-116">NAT を使用したプライベート IP アドレスを持つ単一統合エッジのファイアウォールの概要: 外部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f2894-116">Firewall Summary for Single Consolidated Edge with Private IP Addresses using NAT: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2894-117">役割/プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="f2894-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="f2894-118">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="f2894-118">Source IP address</span></span></th>
<th><span data-ttu-id="f2894-119">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="f2894-119">Destination IP address</span></span></th>
<th><span data-ttu-id="f2894-120">Notes</span><span class="sxs-lookup"><span data-stu-id="f2894-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2894-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="f2894-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="f2894-122">任意</span><span class="sxs-lookup"><span data-stu-id="f2894-122">Any</span></span></p></td>
<td><p><span data-ttu-id="f2894-123">XMPP プロキシサービス (アクセスエッジサービスを使用して IP アドレスを共有)</span><span class="sxs-lookup"><span data-stu-id="f2894-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="f2894-124">XMPP プロキシ サービスは、定義された XMPP フェデレーションの XMPP コンタクトからトラフィックを受け付けます</span><span class="sxs-lookup"><span data-stu-id="f2894-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2894-125">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="f2894-125">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="f2894-126">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="f2894-126">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="f2894-127">任意</span><span class="sxs-lookup"><span data-stu-id="f2894-127">Any</span></span></p></td>
<td><p><span data-ttu-id="f2894-128">証明書の失効/CRL のチェックおよび取得</span><span class="sxs-lookup"><span data-stu-id="f2894-128">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2894-129">アクセス/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="f2894-129">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="f2894-130">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="f2894-130">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="f2894-131">任意</span><span class="sxs-lookup"><span data-stu-id="f2894-131">Any</span></span></p></td>
<td><p><span data-ttu-id="f2894-132">TCP による DNS クエリ</span><span class="sxs-lookup"><span data-stu-id="f2894-132">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2894-133">アクセス/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="f2894-133">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="f2894-134">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="f2894-134">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="f2894-135">任意</span><span class="sxs-lookup"><span data-stu-id="f2894-135">Any</span></span></p></td>
<td><p><span data-ttu-id="f2894-136">UDP による DNS クエリ</span><span class="sxs-lookup"><span data-stu-id="f2894-136">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2894-137">アクセス/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="f2894-137">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="f2894-138">任意</span><span class="sxs-lookup"><span data-stu-id="f2894-138">Any</span></span></p></td>
<td><p><span data-ttu-id="f2894-139">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="f2894-139">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="f2894-140">外部ユーザー アクセス用のクライアントからサーバーへの SIP トラフィック</span><span class="sxs-lookup"><span data-stu-id="f2894-140">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2894-141">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="f2894-141">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="f2894-142">任意</span><span class="sxs-lookup"><span data-stu-id="f2894-142">Any</span></span></p></td>
<td><p><span data-ttu-id="f2894-143">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="f2894-143">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="f2894-144">SIP を使用したフェデレーションおよびパブリック IM 接続用</span><span class="sxs-lookup"><span data-stu-id="f2894-144">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2894-145">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="f2894-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="f2894-146">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="f2894-146">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="f2894-147">任意</span><span class="sxs-lookup"><span data-stu-id="f2894-147">Any</span></span></p></td>
<td><p><span data-ttu-id="f2894-148">SIP を使用したフェデレーションおよびパブリック IM 接続用</span><span class="sxs-lookup"><span data-stu-id="f2894-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2894-149">Web 会議/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="f2894-149">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="f2894-150">任意</span><span class="sxs-lookup"><span data-stu-id="f2894-150">Any</span></span></p></td>
<td><p><span data-ttu-id="f2894-151">エッジサーバー Web 会議エッジサービス</span><span class="sxs-lookup"><span data-stu-id="f2894-151">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="f2894-152">Web 会議メディア</span><span class="sxs-lookup"><span data-stu-id="f2894-152">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2894-153">音声/V/RTP/TCP/50,000-59999</span><span class="sxs-lookup"><span data-stu-id="f2894-153">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="f2894-154">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="f2894-154">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="f2894-155">任意</span><span class="sxs-lookup"><span data-stu-id="f2894-155">Any</span></span></p></td>
<td><p><span data-ttu-id="f2894-156">Office Communications Server 2007、Office Communications Server 2007 R2、Lync Server 2010、Lync Server 2013 を実行しているパートナーとのフェデレーションに必要です。</span><span class="sxs-lookup"><span data-stu-id="f2894-156">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2894-157">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="f2894-157">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="f2894-158">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="f2894-158">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="f2894-159">任意</span><span class="sxs-lookup"><span data-stu-id="f2894-159">Any</span></span></p></td>
<td><p><span data-ttu-id="f2894-160">Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必要。</span><span class="sxs-lookup"><span data-stu-id="f2894-160">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2894-161">音声/V/RTP/TCP/50,000-59999</span><span class="sxs-lookup"><span data-stu-id="f2894-161">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="f2894-162">任意</span><span class="sxs-lookup"><span data-stu-id="f2894-162">Any</span></span></p></td>
<td><p><span data-ttu-id="f2894-163">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="f2894-163">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="f2894-164">Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必要</span><span class="sxs-lookup"><span data-stu-id="f2894-164">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2894-165">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="f2894-165">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="f2894-166">任意</span><span class="sxs-lookup"><span data-stu-id="f2894-166">Any</span></span></p></td>
<td><p><span data-ttu-id="f2894-167">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="f2894-167">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="f2894-168">Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必要</span><span class="sxs-lookup"><span data-stu-id="f2894-168">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2894-169">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="f2894-169">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="f2894-170">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="f2894-170">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="f2894-171">任意</span><span class="sxs-lookup"><span data-stu-id="f2894-171">Any</span></span></p></td>
<td><p><span data-ttu-id="f2894-172">3478の送信は、Lync Server の通信相手であるエッジサーバーのバージョンと、エッジサーバー間のメディアトラフィックに使用されます。</span><span class="sxs-lookup"><span data-stu-id="f2894-172">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="f2894-173">Lync Server 2010、Windows Live Messenger、および Office Communications Server 2007 R2 とのフェデレーションに必要です。また、複数のエッジプールが会社内に展開されている場合も必須です。</span><span class="sxs-lookup"><span data-stu-id="f2894-173">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2894-174">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="f2894-174">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="f2894-175">任意</span><span class="sxs-lookup"><span data-stu-id="f2894-175">Any</span></span></p></td>
<td><p><span data-ttu-id="f2894-176">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="f2894-176">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="f2894-177">STUN/UDP による候補の TURN ネゴシエーション/3478</span><span class="sxs-lookup"><span data-stu-id="f2894-177">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2894-178">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="f2894-178">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="f2894-179">任意</span><span class="sxs-lookup"><span data-stu-id="f2894-179">Any</span></span></p></td>
<td><p><span data-ttu-id="f2894-180">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="f2894-180">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="f2894-181">STUN/TCP による候補の TURN ネゴシエーション/443</span><span class="sxs-lookup"><span data-stu-id="f2894-181">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2894-182">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="f2894-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="f2894-183">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="f2894-183">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="f2894-184">任意</span><span class="sxs-lookup"><span data-stu-id="f2894-184">Any</span></span></p></td>
<td><p><span data-ttu-id="f2894-185">STUN/TCP による候補の TURN ネゴシエーション/443</span><span class="sxs-lookup"><span data-stu-id="f2894-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-internal-interface"></a><span data-ttu-id="f2894-186">NAT を使用したプライベート IP アドレスを持つ単一統合エッジのファイアウォールの概要: 内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f2894-186">Firewall Summary for Single Consolidated Edge with Private IP Addresses Using NAT: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2894-187">プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="f2894-187">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="f2894-188">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="f2894-188">Source IP address</span></span></th>
<th><span data-ttu-id="f2894-189">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="f2894-189">Destination IP address</span></span></th>
<th><span data-ttu-id="f2894-190">Comments</span><span class="sxs-lookup"><span data-stu-id="f2894-190">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2894-191">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="f2894-191">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="f2894-192">Any (Standard Edition サーバー IP、Standard Edition サーバー IP アドレス、または XMPP ゲートウェイサービスを実行しているプール IP アドレスとして定義できます)</span><span class="sxs-lookup"><span data-stu-id="f2894-192">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="f2894-193">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f2894-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="f2894-194">フロントエンドサーバーまたはフロントエンドプールで実行されている XMPP ゲートウェイサービスからの送信 XMPP トラフィック</span><span class="sxs-lookup"><span data-stu-id="f2894-194">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2894-195">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="f2894-195">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="f2894-196">任意 (ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバー、またはフロントエンドプールの IP アドレスとして定義可能)</span><span class="sxs-lookup"><span data-stu-id="f2894-196">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="f2894-197">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f2894-197">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="f2894-198">(ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバーまたはフロントエンドプールの IP アドレスからの) エッジサーバーの内部インターフェイスへの送信 SIP トラフィック</span><span class="sxs-lookup"><span data-stu-id="f2894-198">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2894-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="f2894-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="f2894-200">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f2894-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="f2894-201">任意 (ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバー、またはフロントエンドプールの IP アドレスとして定義可能)</span><span class="sxs-lookup"><span data-stu-id="f2894-201">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="f2894-202">エッジサーバーの内部インターフェイスからの受信 SIP トラフィック (ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバー、またはフロントエンドプールの ip アドレス)</span><span class="sxs-lookup"><span data-stu-id="f2894-202">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2894-203">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="f2894-203">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="f2894-204">任意 (フロントエンドサーバーの IP アドレスとして、またはフロントエンドプール内の各フロントエンドサーバーの IP アドレスとして定義可能)</span><span class="sxs-lookup"><span data-stu-id="f2894-204">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="f2894-205">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f2894-205">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="f2894-206">フロントエンドサーバーまたはプール内の各フロントエンドサーバーからエッジサーバーの内部インターフェイスへの Web 会議トラフィック</span><span class="sxs-lookup"><span data-stu-id="f2894-206">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2894-207">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="f2894-207">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="f2894-208">Any (このエッジサーバーを使用するフロントエンドサーバーの IP アドレスまたはフロントエンドプールの IP アドレス、または存続可能 Branch Appliance または存続可能ブランチサーバーとして定義できます)</span><span class="sxs-lookup"><span data-stu-id="f2894-208">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="f2894-209">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f2894-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="f2894-210">このエッジサーバーを使用するフロントエンドサーバーまたはフロントエンドプールの IP アドレスまたは任意の存続可能 Branch Appliance または存続可能ブランチサーバーからの音声ビデオユーザーの認証 (音声ビデオ認証サービス)</span><span class="sxs-lookup"><span data-stu-id="f2894-210">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2894-211">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="f2894-211">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="f2894-212">任意</span><span class="sxs-lookup"><span data-stu-id="f2894-212">Any</span></span></p></td>
<td><p><span data-ttu-id="f2894-213">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f2894-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="f2894-214">内部ユーザーと外部ユーザーとの間の音声ビデオメディア転送の優先パス、存続可能 Branch Appliance または存続可能 Branch Server</span><span class="sxs-lookup"><span data-stu-id="f2894-214">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2894-215">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="f2894-215">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="f2894-216">任意</span><span class="sxs-lookup"><span data-stu-id="f2894-216">Any</span></span></p></td>
<td><p><span data-ttu-id="f2894-217">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f2894-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="f2894-218">内部ユーザーと外部ユーザーとの間の音声ビデオメディア転送のフォールバックパス UDP 通信を確立できない場合は、存続可能 Branch Appliance または存続可能 Branch Server、TCP はファイル転送およびデスクトップ共有に使用されます。</span><span class="sxs-lookup"><span data-stu-id="f2894-218">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2894-219">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="f2894-219">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="f2894-220">任意 (フロントエンドサーバーの IP アドレス、または中央管理ストアを保持するプールとして定義可能)</span><span class="sxs-lookup"><span data-stu-id="f2894-220">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="f2894-221">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f2894-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="f2894-222">中央管理ストアからエッジ サーバーへの変更のレプリケーション</span><span class="sxs-lookup"><span data-stu-id="f2894-222">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2894-223">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="f2894-223">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="f2894-224">任意</span><span class="sxs-lookup"><span data-stu-id="f2894-224">Any</span></span></p></td>
<td><p><span data-ttu-id="f2894-225">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f2894-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="f2894-226">Lync Server 管理シェルと集中ログサービスコマンドレットを使用した集中ログサービスコントローラー、ClsController コマンドライン (ClsController.exe) またはエージェント (ClsAgent.exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="f2894-226">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2894-227">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="f2894-227">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="f2894-228">任意</span><span class="sxs-lookup"><span data-stu-id="f2894-228">Any</span></span></p></td>
<td><p><span data-ttu-id="f2894-229">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f2894-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="f2894-230">Lync Server 管理シェルと集中ログサービスコマンドレットを使用した集中ログサービスコントローラー、ClsController コマンドライン (ClsController.exe) またはエージェント (ClsAgent.exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="f2894-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2894-231">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="f2894-231">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="f2894-232">任意</span><span class="sxs-lookup"><span data-stu-id="f2894-232">Any</span></span></p></td>
<td><p><span data-ttu-id="f2894-233">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f2894-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="f2894-234">Lync Server 管理シェルと集中ログサービスコマンドレットを使用した集中ログサービスコントローラー、ClsController コマンドライン (ClsController.exe) またはエージェント (ClsAgent.exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="f2894-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="f2894-235">フェデレーションのファイアウォールの概要</span><span class="sxs-lookup"><span data-stu-id="f2894-235">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2894-236">役割/プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="f2894-236">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="f2894-237">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="f2894-237">Source IP address</span></span></th>
<th><span data-ttu-id="f2894-238">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="f2894-238">Destination IP address</span></span></th>
<th><span data-ttu-id="f2894-239">Notes</span><span class="sxs-lookup"><span data-stu-id="f2894-239">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2894-240">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="f2894-240">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="f2894-241">アクセス エッジ サービス パブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="f2894-241">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="f2894-242">任意</span><span class="sxs-lookup"><span data-stu-id="f2894-242">Any</span></span></p></td>
<td><p><span data-ttu-id="f2894-243">SIP を使用したフェデレーションおよびパブリック IM 接続用</span><span class="sxs-lookup"><span data-stu-id="f2894-243">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="f2894-244">ファイアウォールの概要 ‐ パブリック インスタント メッセージング接続</span><span class="sxs-lookup"><span data-stu-id="f2894-244">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2894-245">役割/プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="f2894-245">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="f2894-246">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="f2894-246">Source IP address</span></span></th>
<th><span data-ttu-id="f2894-247">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="f2894-247">Destination IP address</span></span></th>
<th><span data-ttu-id="f2894-248">Notes</span><span class="sxs-lookup"><span data-stu-id="f2894-248">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2894-249">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="f2894-249">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="f2894-250">パブリック IM 接続パートナー</span><span class="sxs-lookup"><span data-stu-id="f2894-250">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="f2894-251">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="f2894-251">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="f2894-252">SIP を使用したフェデレーションおよびパブリック IM 接続用</span><span class="sxs-lookup"><span data-stu-id="f2894-252">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2894-253">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="f2894-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="f2894-254">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="f2894-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="f2894-255">パブリック IM 接続パートナー</span><span class="sxs-lookup"><span data-stu-id="f2894-255">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="f2894-256">SIP を使用したフェデレーションおよびパブリック IM 接続用</span><span class="sxs-lookup"><span data-stu-id="f2894-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2894-257">アクセス/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="f2894-257">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="f2894-258">クライアント</span><span class="sxs-lookup"><span data-stu-id="f2894-258">Clients</span></span></p></td>
<td><p><span data-ttu-id="f2894-259">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="f2894-259">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="f2894-260">外部ユーザー アクセス用のクライアントからサーバーへの SIP トラフィック</span><span class="sxs-lookup"><span data-stu-id="f2894-260">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2894-261">音声/V/RTP/TCP/50,000-59999</span><span class="sxs-lookup"><span data-stu-id="f2894-261">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="f2894-262">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="f2894-262">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="f2894-263">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="f2894-263">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="f2894-264">パブリック IM 接続が構成されている場合に、Windows Live Messenger との音声ビデオ セッションに使用されます。</span><span class="sxs-lookup"><span data-stu-id="f2894-264">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2894-265">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="f2894-265">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="f2894-266">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="f2894-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="f2894-267">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="f2894-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="f2894-268">Windows Live Messenger とのパブリック IM 接続では必須</span><span class="sxs-lookup"><span data-stu-id="f2894-268">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2894-269">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="f2894-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="f2894-270">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="f2894-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="f2894-271">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="f2894-271">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="f2894-272">Windows Live Messenger とのパブリック IM 接続では必須</span><span class="sxs-lookup"><span data-stu-id="f2894-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="f2894-273">XMPP のファイアウォールの概要</span><span class="sxs-lookup"><span data-stu-id="f2894-273">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2894-274">プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="f2894-274">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="f2894-275">送信元 (IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="f2894-275">Source (IP address)</span></span></th>
<th><span data-ttu-id="f2894-276">宛先 (IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="f2894-276">Destination (IP address)</span></span></th>
<th><span data-ttu-id="f2894-277">Comments</span><span class="sxs-lookup"><span data-stu-id="f2894-277">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2894-278">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="f2894-278">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="f2894-279">任意</span><span class="sxs-lookup"><span data-stu-id="f2894-279">Any</span></span></p></td>
<td><p><span data-ttu-id="f2894-280">エッジサーバーアクセスエッジサービスインターフェイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="f2894-280">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="f2894-281">XMPP 用の標準的なサーバー間通信。</span><span class="sxs-lookup"><span data-stu-id="f2894-281">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="f2894-282">フェデレーションされた XMPP パートナーからのエッジサーバー XMPP プロキシへの通信を許可します。</span><span class="sxs-lookup"><span data-stu-id="f2894-282">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2894-283">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="f2894-283">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="f2894-284">エッジサーバーアクセスエッジサービスインターフェイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="f2894-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="f2894-285">任意</span><span class="sxs-lookup"><span data-stu-id="f2894-285">Any</span></span></p></td>
<td><p><span data-ttu-id="f2894-286">XMPP 用の標準的なサーバー間通信。</span><span class="sxs-lookup"><span data-stu-id="f2894-286">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="f2894-287">エッジサーバー XMPP プロキシからフェデレーションされた XMPP パートナーへの通信を許可します。</span><span class="sxs-lookup"><span data-stu-id="f2894-287">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2894-288">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="f2894-288">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="f2894-289">任意</span><span class="sxs-lookup"><span data-stu-id="f2894-289">Any</span></span></p></td>
<td><p><span data-ttu-id="f2894-290">各内部エッジサーバーインターフェイス IP</span><span class="sxs-lookup"><span data-stu-id="f2894-290">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="f2894-291">フロントエンドサーバーまたはフロントエンドプールの XMPP ゲートウェイから、エッジサーバーの内部 IP アドレスまたは各エッジプールメンバーの内部 IP アドレスへの内部 XMPP トラフィック</span><span class="sxs-lookup"><span data-stu-id="f2894-291">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

