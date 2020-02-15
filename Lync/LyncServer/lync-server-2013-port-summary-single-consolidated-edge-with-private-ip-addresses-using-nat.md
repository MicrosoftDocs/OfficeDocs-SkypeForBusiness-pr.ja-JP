---
title: ポートの概要-NAT を使用したプライベート IP アドレスを持つ単一統合エッジ
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
ms.openlocfilehash: 025e472da32afc9d865557c29836c66c0c1f5b18
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006875"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="ad795-102">ポートの概要-Lync Server 2013 で NAT を使用するプライベート IP アドレスを持つ単一統合エッジ</span><span class="sxs-lookup"><span data-stu-id="ad795-102">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad795-103">_**トピックの最終更新日:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="ad795-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="ad795-104">このシナリオアーキテクチャで説明されている Lync server 2013 のエッジサーバー機能は、Lync Server 2010 で実装されていたものとよく似ています。</span><span class="sxs-lookup"><span data-stu-id="ad795-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="ad795-105">最も目を引くのは、XMPP (Extensible Messaging and Presence Protocol) 用の ポート **5269/TCP** エントリが追加されたことです。</span><span class="sxs-lookup"><span data-stu-id="ad795-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="ad795-106">Lync Server 2013 は、フロントエンドサーバーまたはフロントエンドプールに、エッジサーバーまたはエッジプールおよび XMPP ゲートウェイサーバー上に XMPP プロキシを任意で展開します。</span><span class="sxs-lookup"><span data-stu-id="ad795-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="ad795-107">IPv4 に加えて、エッジサーバーは IPv6 をサポートするようになりました。</span><span class="sxs-lookup"><span data-stu-id="ad795-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="ad795-108">わかりやすいように、シナリオでは IPv4 のみを使用します。</span><span class="sxs-lookup"><span data-stu-id="ad795-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="ad795-109">**NAT を使用したプライベート IP アドレスを使用する単一の統合エッジサーバーのネットワーク境界**</span><span class="sxs-lookup"><span data-stu-id="ad795-109">**Network Perimeter for a Single Consolidated Edge Server with Private IP Addressing Using NAT**</span></span>

<span data-ttu-id="ad795-110">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="ad795-110">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="ad795-111">ポートとプロトコルの詳細</span><span class="sxs-lookup"><span data-stu-id="ad795-111">Port and Protocol Details</span></span>

<span data-ttu-id="ad795-112">外部アクセスが可能な機能のサポートに必要なポートのみを開くことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ad795-112">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="ad795-113">エッジ サービスのリモート アクセスが機能するためには、受信/送信のエッジ トラフィックの図が示すように、SIP トラフィックの双方向通過が許可されていることが必須です。</span><span class="sxs-lookup"><span data-stu-id="ad795-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="ad795-114">もう1つの方法として、アクセスエッジサービスとの間の SIP メッセージングは、インスタントメッセージング (IM)、プレゼンス、web 会議、音声ビデオ (A/V)、およびフェデレーションに関係しています。</span><span class="sxs-lookup"><span data-stu-id="ad795-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V), and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-external-interface"></a><span data-ttu-id="ad795-115">NAT を使用したプライベート IP アドレスを持つ単一統合エッジのファイアウォールの概要: 外部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ad795-115">Firewall Summary for Single Consolidated Edge with Private IP Addresses using NAT: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad795-116">役割/プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="ad795-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ad795-117">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="ad795-117">Source IP address</span></span></th>
<th><span data-ttu-id="ad795-118">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="ad795-118">Destination IP address</span></span></th>
<th><span data-ttu-id="ad795-119">メモ</span><span class="sxs-lookup"><span data-stu-id="ad795-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad795-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="ad795-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="ad795-121">任意</span><span class="sxs-lookup"><span data-stu-id="ad795-121">Any</span></span></p></td>
<td><p><span data-ttu-id="ad795-122">XMPP プロキシサービス (アクセスエッジサービスを使用して IP アドレスを共有)</span><span class="sxs-lookup"><span data-stu-id="ad795-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="ad795-123">XMPP プロキシ サービスは、定義された XMPP フェデレーションの XMPP コンタクトからトラフィックを受け付けます</span><span class="sxs-lookup"><span data-stu-id="ad795-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad795-124">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="ad795-124">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="ad795-125">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="ad795-125">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="ad795-126">任意</span><span class="sxs-lookup"><span data-stu-id="ad795-126">Any</span></span></p></td>
<td><p><span data-ttu-id="ad795-127">証明書の失効/CRL のチェックおよび取得</span><span class="sxs-lookup"><span data-stu-id="ad795-127">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad795-128">アクセス/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="ad795-128">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="ad795-129">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="ad795-129">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="ad795-130">任意</span><span class="sxs-lookup"><span data-stu-id="ad795-130">Any</span></span></p></td>
<td><p><span data-ttu-id="ad795-131">TCP による DNS クエリ</span><span class="sxs-lookup"><span data-stu-id="ad795-131">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad795-132">アクセス/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="ad795-132">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="ad795-133">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="ad795-133">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="ad795-134">任意</span><span class="sxs-lookup"><span data-stu-id="ad795-134">Any</span></span></p></td>
<td><p><span data-ttu-id="ad795-135">UDP による DNS クエリ</span><span class="sxs-lookup"><span data-stu-id="ad795-135">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad795-136">アクセス/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ad795-136">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ad795-137">任意</span><span class="sxs-lookup"><span data-stu-id="ad795-137">Any</span></span></p></td>
<td><p><span data-ttu-id="ad795-138">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="ad795-138">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="ad795-139">外部ユーザー アクセス用のクライアントからサーバーへの SIP トラフィック</span><span class="sxs-lookup"><span data-stu-id="ad795-139">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad795-140">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ad795-140">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ad795-141">任意</span><span class="sxs-lookup"><span data-stu-id="ad795-141">Any</span></span></p></td>
<td><p><span data-ttu-id="ad795-142">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="ad795-142">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="ad795-143">SIP を使用したフェデレーションおよびパブリック IM 接続用</span><span class="sxs-lookup"><span data-stu-id="ad795-143">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad795-144">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ad795-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ad795-145">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="ad795-145">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="ad795-146">任意</span><span class="sxs-lookup"><span data-stu-id="ad795-146">Any</span></span></p></td>
<td><p><span data-ttu-id="ad795-147">SIP を使用したフェデレーションおよびパブリック IM 接続用</span><span class="sxs-lookup"><span data-stu-id="ad795-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad795-148">Web 会議/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ad795-148">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ad795-149">任意</span><span class="sxs-lookup"><span data-stu-id="ad795-149">Any</span></span></p></td>
<td><p><span data-ttu-id="ad795-150">エッジサーバー Web 会議エッジサービス</span><span class="sxs-lookup"><span data-stu-id="ad795-150">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="ad795-151">Web 会議メディア</span><span class="sxs-lookup"><span data-stu-id="ad795-151">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad795-152">音声/V/RTP/TCP/50,000-59999</span><span class="sxs-lookup"><span data-stu-id="ad795-152">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="ad795-153">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="ad795-153">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ad795-154">任意</span><span class="sxs-lookup"><span data-stu-id="ad795-154">Any</span></span></p></td>
<td><p><span data-ttu-id="ad795-155">Office Communications Server 2007、Office Communications Server 2007 R2、Lync Server 2010、Lync Server 2013 を実行しているパートナーとのフェデレーションに必要です。</span><span class="sxs-lookup"><span data-stu-id="ad795-155">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad795-156">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="ad795-156">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="ad795-157">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="ad795-157">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ad795-158">任意</span><span class="sxs-lookup"><span data-stu-id="ad795-158">Any</span></span></p></td>
<td><p><span data-ttu-id="ad795-159">Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必要。</span><span class="sxs-lookup"><span data-stu-id="ad795-159">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad795-160">音声/V/RTP/TCP/50,000-59999</span><span class="sxs-lookup"><span data-stu-id="ad795-160">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="ad795-161">任意</span><span class="sxs-lookup"><span data-stu-id="ad795-161">Any</span></span></p></td>
<td><p><span data-ttu-id="ad795-162">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="ad795-162">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ad795-163">Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必要</span><span class="sxs-lookup"><span data-stu-id="ad795-163">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad795-164">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="ad795-164">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="ad795-165">任意</span><span class="sxs-lookup"><span data-stu-id="ad795-165">Any</span></span></p></td>
<td><p><span data-ttu-id="ad795-166">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="ad795-166">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ad795-167">Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必要</span><span class="sxs-lookup"><span data-stu-id="ad795-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad795-168">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ad795-168">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ad795-169">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="ad795-169">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ad795-170">任意</span><span class="sxs-lookup"><span data-stu-id="ad795-170">Any</span></span></p></td>
<td><p><span data-ttu-id="ad795-171">3478の送信は、Lync Server の通信相手であるエッジサーバーのバージョンと、エッジサーバー間のメディアトラフィックに使用されます。</span><span class="sxs-lookup"><span data-stu-id="ad795-171">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="ad795-172">Lync Server 2010、Windows Live Messenger、および Office Communications Server 2007 R2 とのフェデレーションに必要です。また、複数のエッジプールが会社内に展開されている場合も必須です。</span><span class="sxs-lookup"><span data-stu-id="ad795-172">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad795-173">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ad795-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ad795-174">任意</span><span class="sxs-lookup"><span data-stu-id="ad795-174">Any</span></span></p></td>
<td><p><span data-ttu-id="ad795-175">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="ad795-175">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ad795-176">STUN/UDP による候補の TURN ネゴシエーション/3478</span><span class="sxs-lookup"><span data-stu-id="ad795-176">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad795-177">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ad795-177">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ad795-178">任意</span><span class="sxs-lookup"><span data-stu-id="ad795-178">Any</span></span></p></td>
<td><p><span data-ttu-id="ad795-179">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="ad795-179">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ad795-180">STUN/TCP による候補の TURN ネゴシエーション/443</span><span class="sxs-lookup"><span data-stu-id="ad795-180">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad795-181">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ad795-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ad795-182">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="ad795-182">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ad795-183">任意</span><span class="sxs-lookup"><span data-stu-id="ad795-183">Any</span></span></p></td>
<td><p><span data-ttu-id="ad795-184">STUN/TCP による候補の TURN ネゴシエーション/443</span><span class="sxs-lookup"><span data-stu-id="ad795-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-internal-interface"></a><span data-ttu-id="ad795-185">NAT を使用したプライベート IP アドレスを持つ単一統合エッジのファイアウォールの概要: 内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ad795-185">Firewall Summary for Single Consolidated Edge with Private IP Addresses Using NAT: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad795-186">プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="ad795-186">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ad795-187">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="ad795-187">Source IP address</span></span></th>
<th><span data-ttu-id="ad795-188">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="ad795-188">Destination IP address</span></span></th>
<th><span data-ttu-id="ad795-189">コメント</span><span class="sxs-lookup"><span data-stu-id="ad795-189">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad795-190">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="ad795-190">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="ad795-191">Any (Standard Edition サーバー IP、Standard Edition サーバー IP アドレス、または XMPP ゲートウェイサービスを実行しているプール IP アドレスとして定義できます)</span><span class="sxs-lookup"><span data-stu-id="ad795-191">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="ad795-192">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ad795-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ad795-193">フロントエンドサーバーまたはフロントエンドプールで実行されている XMPP ゲートウェイサービスからの送信 XMPP トラフィック</span><span class="sxs-lookup"><span data-stu-id="ad795-193">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad795-194">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ad795-194">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ad795-195">任意 (ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバー、またはフロントエンドプールの IP アドレスとして定義可能)</span><span class="sxs-lookup"><span data-stu-id="ad795-195">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="ad795-196">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ad795-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ad795-197">(ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバーまたはフロントエンドプールの IP アドレスからの) エッジサーバーの内部インターフェイスへの送信 SIP トラフィック</span><span class="sxs-lookup"><span data-stu-id="ad795-197">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad795-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ad795-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ad795-199">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ad795-199">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ad795-200">任意 (ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバー、またはフロントエンドプールの IP アドレスとして定義可能)</span><span class="sxs-lookup"><span data-stu-id="ad795-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="ad795-201">エッジサーバーの内部インターフェイスからの受信 SIP トラフィック (ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバー、またはフロントエンドプールの ip アドレス)</span><span class="sxs-lookup"><span data-stu-id="ad795-201">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad795-202">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="ad795-202">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="ad795-203">任意 (フロントエンドサーバーの IP アドレスとして、またはフロントエンドプール内の各フロントエンドサーバーの IP アドレスとして定義可能)</span><span class="sxs-lookup"><span data-stu-id="ad795-203">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="ad795-204">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ad795-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ad795-205">フロントエンドサーバーまたはプール内の各フロントエンドサーバーからエッジサーバーの内部インターフェイスへの Web 会議トラフィック</span><span class="sxs-lookup"><span data-stu-id="ad795-205">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad795-206">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="ad795-206">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="ad795-207">Any (このエッジサーバーを使用するフロントエンドサーバーの IP アドレスまたはフロントエンドプールの IP アドレス、または存続可能 Branch Appliance または存続可能ブランチサーバーとして定義できます)</span><span class="sxs-lookup"><span data-stu-id="ad795-207">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="ad795-208">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ad795-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ad795-209">このエッジサーバーを使用するフロントエンドサーバーまたはフロントエンドプールの IP アドレスまたは任意の存続可能 Branch Appliance または存続可能ブランチサーバーからの音声ビデオユーザーの認証 (音声ビデオ認証サービス)</span><span class="sxs-lookup"><span data-stu-id="ad795-209">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad795-210">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ad795-210">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ad795-211">任意</span><span class="sxs-lookup"><span data-stu-id="ad795-211">Any</span></span></p></td>
<td><p><span data-ttu-id="ad795-212">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ad795-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ad795-213">内部ユーザーと外部ユーザーとの間の音声ビデオメディア転送の優先パス、存続可能 Branch Appliance または存続可能 Branch Server</span><span class="sxs-lookup"><span data-stu-id="ad795-213">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad795-214">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ad795-214">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ad795-215">任意</span><span class="sxs-lookup"><span data-stu-id="ad795-215">Any</span></span></p></td>
<td><p><span data-ttu-id="ad795-216">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ad795-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ad795-217">内部ユーザーと外部ユーザーとの間の音声ビデオメディア転送のフォールバックパス UDP 通信を確立できない場合は、存続可能 Branch Appliance または存続可能 Branch Server、TCP はファイル転送およびデスクトップ共有に使用されます。</span><span class="sxs-lookup"><span data-stu-id="ad795-217">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad795-218">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="ad795-218">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="ad795-219">任意 (フロントエンドサーバーの IP アドレス、または中央管理ストアを保持するプールとして定義可能)</span><span class="sxs-lookup"><span data-stu-id="ad795-219">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="ad795-220">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ad795-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ad795-221">中央管理ストアからエッジ サーバーへの変更のレプリケーション</span><span class="sxs-lookup"><span data-stu-id="ad795-221">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad795-222">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="ad795-222">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="ad795-223">任意</span><span class="sxs-lookup"><span data-stu-id="ad795-223">Any</span></span></p></td>
<td><p><span data-ttu-id="ad795-224">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ad795-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ad795-225">Lync Server 管理シェルと集中ログサービスコマンドレットを使用した集中ログサービスコントローラー、ClsController コマンドライン (ClsController) またはエージェント (Clscontroller. .exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="ad795-225">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad795-226">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="ad795-226">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="ad795-227">任意</span><span class="sxs-lookup"><span data-stu-id="ad795-227">Any</span></span></p></td>
<td><p><span data-ttu-id="ad795-228">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ad795-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ad795-229">Lync Server 管理シェルと集中ログサービスコマンドレットを使用した集中ログサービスコントローラー、ClsController コマンドライン (ClsController) またはエージェント (Clscontroller. .exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="ad795-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad795-230">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="ad795-230">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="ad795-231">任意</span><span class="sxs-lookup"><span data-stu-id="ad795-231">Any</span></span></p></td>
<td><p><span data-ttu-id="ad795-232">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ad795-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ad795-233">Lync Server 管理シェルと集中ログサービスコマンドレットを使用した集中ログサービスコントローラー、ClsController コマンドライン (ClsController) またはエージェント (Clscontroller. .exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="ad795-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="ad795-234">フェデレーションのファイアウォールの概要</span><span class="sxs-lookup"><span data-stu-id="ad795-234">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad795-235">役割/プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="ad795-235">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ad795-236">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="ad795-236">Source IP address</span></span></th>
<th><span data-ttu-id="ad795-237">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="ad795-237">Destination IP address</span></span></th>
<th><span data-ttu-id="ad795-238">メモ</span><span class="sxs-lookup"><span data-stu-id="ad795-238">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad795-239">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ad795-239">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ad795-240">アクセス エッジ サービス パブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="ad795-240">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ad795-241">任意</span><span class="sxs-lookup"><span data-stu-id="ad795-241">Any</span></span></p></td>
<td><p><span data-ttu-id="ad795-242">SIP を使用したフェデレーションおよびパブリック IM 接続用</span><span class="sxs-lookup"><span data-stu-id="ad795-242">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="ad795-243">ファイアウォールの概要 ‐ パブリック インスタント メッセージング接続</span><span class="sxs-lookup"><span data-stu-id="ad795-243">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad795-244">役割/プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="ad795-244">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ad795-245">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="ad795-245">Source IP address</span></span></th>
<th><span data-ttu-id="ad795-246">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="ad795-246">Destination IP address</span></span></th>
<th><span data-ttu-id="ad795-247">メモ</span><span class="sxs-lookup"><span data-stu-id="ad795-247">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad795-248">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ad795-248">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ad795-249">パブリック IM 接続パートナー</span><span class="sxs-lookup"><span data-stu-id="ad795-249">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="ad795-250">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="ad795-250">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="ad795-251">SIP を使用したフェデレーションおよびパブリック IM 接続用</span><span class="sxs-lookup"><span data-stu-id="ad795-251">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad795-252">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ad795-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ad795-253">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="ad795-253">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="ad795-254">パブリック IM 接続パートナー</span><span class="sxs-lookup"><span data-stu-id="ad795-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="ad795-255">SIP を使用したフェデレーションおよびパブリック IM 接続用</span><span class="sxs-lookup"><span data-stu-id="ad795-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad795-256">アクセス/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ad795-256">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ad795-257">クライアント</span><span class="sxs-lookup"><span data-stu-id="ad795-257">Clients</span></span></p></td>
<td><p><span data-ttu-id="ad795-258">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="ad795-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="ad795-259">外部ユーザー アクセス用のクライアントからサーバーへの SIP トラフィック</span><span class="sxs-lookup"><span data-stu-id="ad795-259">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad795-260">音声/V/RTP/TCP/50,000-59999</span><span class="sxs-lookup"><span data-stu-id="ad795-260">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="ad795-261">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="ad795-261">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ad795-262">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="ad795-262">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="ad795-263">パブリック IM 接続が構成されている場合に、Windows Live Messenger との音声ビデオ セッションに使用されます。</span><span class="sxs-lookup"><span data-stu-id="ad795-263">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad795-264">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ad795-264">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ad795-265">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="ad795-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ad795-266">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="ad795-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="ad795-267">Windows Live Messenger とのパブリック IM 接続では必須</span><span class="sxs-lookup"><span data-stu-id="ad795-267">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad795-268">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ad795-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ad795-269">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="ad795-269">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="ad795-270">エッジサーバーの音声ビデオエッジサービス</span><span class="sxs-lookup"><span data-stu-id="ad795-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ad795-271">Windows Live Messenger とのパブリック IM 接続では必須</span><span class="sxs-lookup"><span data-stu-id="ad795-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="ad795-272">XMPP のファイアウォールの概要</span><span class="sxs-lookup"><span data-stu-id="ad795-272">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad795-273">プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="ad795-273">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ad795-274">送信元 (IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="ad795-274">Source (IP address)</span></span></th>
<th><span data-ttu-id="ad795-275">宛先 (IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="ad795-275">Destination (IP address)</span></span></th>
<th><span data-ttu-id="ad795-276">コメント</span><span class="sxs-lookup"><span data-stu-id="ad795-276">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad795-277">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="ad795-277">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="ad795-278">任意</span><span class="sxs-lookup"><span data-stu-id="ad795-278">Any</span></span></p></td>
<td><p><span data-ttu-id="ad795-279">エッジサーバーアクセスエッジサービスインターフェイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="ad795-279">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="ad795-280">XMPP 用の標準的なサーバー間通信。</span><span class="sxs-lookup"><span data-stu-id="ad795-280">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="ad795-281">フェデレーションされた XMPP パートナーからのエッジサーバー XMPP プロキシへの通信を許可します。</span><span class="sxs-lookup"><span data-stu-id="ad795-281">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad795-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="ad795-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="ad795-283">エッジサーバーアクセスエッジサービスインターフェイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="ad795-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="ad795-284">任意</span><span class="sxs-lookup"><span data-stu-id="ad795-284">Any</span></span></p></td>
<td><p><span data-ttu-id="ad795-285">XMPP 用の標準的なサーバー間通信。</span><span class="sxs-lookup"><span data-stu-id="ad795-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="ad795-286">エッジサーバー XMPP プロキシからフェデレーションされた XMPP パートナーへの通信を許可します。</span><span class="sxs-lookup"><span data-stu-id="ad795-286">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad795-287">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="ad795-287">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="ad795-288">任意</span><span class="sxs-lookup"><span data-stu-id="ad795-288">Any</span></span></p></td>
<td><p><span data-ttu-id="ad795-289">各内部エッジサーバーインターフェイス IP</span><span class="sxs-lookup"><span data-stu-id="ad795-289">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="ad795-290">フロントエンドサーバーまたはフロントエンドプールの XMPP ゲートウェイから、エッジサーバーの内部 IP アドレスまたは各エッジプールメンバーの内部 IP アドレスへの内部 XMPP トラフィック</span><span class="sxs-lookup"><span data-stu-id="ad795-290">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

