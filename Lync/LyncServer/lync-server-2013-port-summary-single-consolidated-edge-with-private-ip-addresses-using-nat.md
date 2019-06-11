---
title: ポートの概要 - NAT を使用したプライベート IP アドレスを含む単一統合エッジ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: 3c1a389f-5f42-4719-a05b-e0b84aa3eb9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425891(v=OCS.15)
ms:contentKeyID: 48183877
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b7c908d52577375f9caaab974f059ffda17fb35
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824359"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="df84e-102">ポートの概要 - Lync Server 2013 の NAT を使用したプライベート IP アドレスを含む単一統合エッジ</span><span class="sxs-lookup"><span data-stu-id="df84e-102">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df84e-103">_**最終更新日:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="df84e-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="df84e-104">このシナリオアーキテクチャで説明されている Lync Server 2013 のエッジサーバー機能は、Lync Server 2010 で実装されたものとよく似ています。</span><span class="sxs-lookup"><span data-stu-id="df84e-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="df84e-105">最も顕著な追加機能は、拡張メッセージングとプレゼンスプロトコル (XMPP) の TCP エントリのポート**5269**です。</span><span class="sxs-lookup"><span data-stu-id="df84e-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="df84e-106">Lync Server 2013 では、必要に応じて、microsoft Edge サーバーまたはエッジプールに XMPP プロキシを展開し、フロントエンドサーバーまたはフロントエンドプールに XMPP ゲートウェイサーバーを配置します。</span><span class="sxs-lookup"><span data-stu-id="df84e-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="df84e-107">IPv4 に加えて、エッジサーバーは IPv6 をサポートするようになりました。</span><span class="sxs-lookup"><span data-stu-id="df84e-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="df84e-108">わかりやすくするために、シナリオでは IPv4 のみが使用されます。</span><span class="sxs-lookup"><span data-stu-id="df84e-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="df84e-109">**NAT を使用するプライベート IP アドレスが指定された単一の統合エッジサーバーのネットワーク境界線**</span><span class="sxs-lookup"><span data-stu-id="df84e-109">**Network Perimeter for a Single Consolidated Edge Server with Private IP Addressing Using NAT**</span></span>

<span data-ttu-id="df84e-110">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="df84e-110">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="df84e-111">ポートとプロトコルの詳細</span><span class="sxs-lookup"><span data-stu-id="df84e-111">Port and Protocol Details</span></span>

<span data-ttu-id="df84e-112">外部アクセスを提供する機能をサポートするために必要なポートのみを開くことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="df84e-112">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="df84e-113">エッジサービスに対してリモートアクセスを使用するには、受信/送信エッジトラフィックの図に示すように、SIP トラフィックが双方向に流れるようにすることが必須です。</span><span class="sxs-lookup"><span data-stu-id="df84e-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="df84e-114">別の方法として、アクセスエッジサービスとの間の SIP メッセージングは、インスタントメッセージング (IM)、プレゼンス、web 会議、音声/ビデオ (A/V)、およびフェデレーションに関連しています。</span><span class="sxs-lookup"><span data-stu-id="df84e-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V), and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-external-interface"></a><span data-ttu-id="df84e-115">NAT を使用してプライベート IP アドレスを持つ単一の統合エッジのファイアウォールの概要: 外部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="df84e-115">Firewall Summary for Single Consolidated Edge with Private IP Addresses using NAT: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="df84e-116">Role/Protocol/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="df84e-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="df84e-117">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="df84e-117">Source IP address</span></span></th>
<th><span data-ttu-id="df84e-118">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="df84e-118">Destination IP address</span></span></th>
<th><span data-ttu-id="df84e-119">メモ</span><span class="sxs-lookup"><span data-stu-id="df84e-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="df84e-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="df84e-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="df84e-121">任意</span><span class="sxs-lookup"><span data-stu-id="df84e-121">Any</span></span></p></td>
<td><p><span data-ttu-id="df84e-122">XMPP プロキシサービス (アクセスエッジサービスで IP アドレスを共有)</span><span class="sxs-lookup"><span data-stu-id="df84e-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="df84e-123">XMPP プロキシサービスは、定義された XMPP フェデレーションの XMPP 連絡先からのトラフィックを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="df84e-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df84e-124">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="df84e-124">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="df84e-125">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="df84e-125">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="df84e-126">任意</span><span class="sxs-lookup"><span data-stu-id="df84e-126">Any</span></span></p></td>
<td><p><span data-ttu-id="df84e-127">証明書の失効/CRL の確認と取得</span><span class="sxs-lookup"><span data-stu-id="df84e-127">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df84e-128">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="df84e-128">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="df84e-129">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="df84e-129">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="df84e-130">任意</span><span class="sxs-lookup"><span data-stu-id="df84e-130">Any</span></span></p></td>
<td><p><span data-ttu-id="df84e-131">TCP 経由の DNS クエリ</span><span class="sxs-lookup"><span data-stu-id="df84e-131">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df84e-132">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="df84e-132">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="df84e-133">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="df84e-133">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="df84e-134">任意</span><span class="sxs-lookup"><span data-stu-id="df84e-134">Any</span></span></p></td>
<td><p><span data-ttu-id="df84e-135">UDP 経由の DNS クエリ</span><span class="sxs-lookup"><span data-stu-id="df84e-135">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df84e-136">アクセス/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="df84e-136">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="df84e-137">任意</span><span class="sxs-lookup"><span data-stu-id="df84e-137">Any</span></span></p></td>
<td><p><span data-ttu-id="df84e-138">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="df84e-138">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="df84e-139">外部ユーザーアクセスのクライアントツーサーバー SIP トラフィック</span><span class="sxs-lookup"><span data-stu-id="df84e-139">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df84e-140">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="df84e-140">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="df84e-141">任意</span><span class="sxs-lookup"><span data-stu-id="df84e-141">Any</span></span></p></td>
<td><p><span data-ttu-id="df84e-142">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="df84e-142">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="df84e-143">SIP を使用するフェデレーションおよびパブリック IM 接続の場合</span><span class="sxs-lookup"><span data-stu-id="df84e-143">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df84e-144">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="df84e-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="df84e-145">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="df84e-145">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="df84e-146">任意</span><span class="sxs-lookup"><span data-stu-id="df84e-146">Any</span></span></p></td>
<td><p><span data-ttu-id="df84e-147">SIP を使用するフェデレーションおよびパブリック IM 接続の場合</span><span class="sxs-lookup"><span data-stu-id="df84e-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df84e-148">Web 会議/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="df84e-148">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="df84e-149">任意</span><span class="sxs-lookup"><span data-stu-id="df84e-149">Any</span></span></p></td>
<td><p><span data-ttu-id="df84e-150">エッジサーバー Web 会議エッジサービス</span><span class="sxs-lookup"><span data-stu-id="df84e-150">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="df84e-151">Web 会議メディア</span><span class="sxs-lookup"><span data-stu-id="df84e-151">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df84e-152">A/V/RTP/59,999</span><span class="sxs-lookup"><span data-stu-id="df84e-152">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="df84e-153">エッジサーバーの A/V Edge サービス</span><span class="sxs-lookup"><span data-stu-id="df84e-153">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="df84e-154">任意</span><span class="sxs-lookup"><span data-stu-id="df84e-154">Any</span></span></p></td>
<td><p><span data-ttu-id="df84e-155">Office Communications Server 2007、Office Communications Server 2007 R2、Lync Server 2010、および Lync Server 2013 を実行しているパートナーとのフェデレーションに必要。</span><span class="sxs-lookup"><span data-stu-id="df84e-155">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df84e-156">A/V/RTP/59,999</span><span class="sxs-lookup"><span data-stu-id="df84e-156">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="df84e-157">エッジサーバーの A/V Edge サービス</span><span class="sxs-lookup"><span data-stu-id="df84e-157">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="df84e-158">任意</span><span class="sxs-lookup"><span data-stu-id="df84e-158">Any</span></span></p></td>
<td><p><span data-ttu-id="df84e-159">Office Communications Server 2007 を実行しているパートナーとのフェデレーションの場合のみ必須です。</span><span class="sxs-lookup"><span data-stu-id="df84e-159">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df84e-160">A/V/RTP/59,999</span><span class="sxs-lookup"><span data-stu-id="df84e-160">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="df84e-161">任意</span><span class="sxs-lookup"><span data-stu-id="df84e-161">Any</span></span></p></td>
<td><p><span data-ttu-id="df84e-162">エッジサーバーの A/V Edge サービス</span><span class="sxs-lookup"><span data-stu-id="df84e-162">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="df84e-163">Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必須</span><span class="sxs-lookup"><span data-stu-id="df84e-163">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df84e-164">A/V/RTP/59,999</span><span class="sxs-lookup"><span data-stu-id="df84e-164">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="df84e-165">任意</span><span class="sxs-lookup"><span data-stu-id="df84e-165">Any</span></span></p></td>
<td><p><span data-ttu-id="df84e-166">エッジサーバーの A/V Edge サービス</span><span class="sxs-lookup"><span data-stu-id="df84e-166">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="df84e-167">Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必須</span><span class="sxs-lookup"><span data-stu-id="df84e-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df84e-168">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="df84e-168">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="df84e-169">エッジサーバーの A/V Edge サービス</span><span class="sxs-lookup"><span data-stu-id="df84e-169">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="df84e-170">任意</span><span class="sxs-lookup"><span data-stu-id="df84e-170">Any</span></span></p></td>
<td><p><span data-ttu-id="df84e-171">3478送信は、Lync Server が通信するエッジサーバーのバージョンと、エッジサーバーからエッジサーバーへのメディアトラフィックも確認するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="df84e-171">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="df84e-172">Lync Server 2010、Windows Live Messenger、Office Communications Server 2007 R2 とのフェデレーション、および複数のエッジプールが会社内に展開されている場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="df84e-172">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df84e-173">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="df84e-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="df84e-174">任意</span><span class="sxs-lookup"><span data-stu-id="df84e-174">Any</span></span></p></td>
<td><p><span data-ttu-id="df84e-175">エッジサーバーの A/V Edge サービス</span><span class="sxs-lookup"><span data-stu-id="df84e-175">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="df84e-176">UDP/3478 経由の候補のネゴシエーションをオフ/オンにする</span><span class="sxs-lookup"><span data-stu-id="df84e-176">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df84e-177">A/V/STUN、MSTURN/443</span><span class="sxs-lookup"><span data-stu-id="df84e-177">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="df84e-178">任意</span><span class="sxs-lookup"><span data-stu-id="df84e-178">Any</span></span></p></td>
<td><p><span data-ttu-id="df84e-179">エッジサーバーの A/V Edge サービス</span><span class="sxs-lookup"><span data-stu-id="df84e-179">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="df84e-180">TCP/443 経由での候補のネゴシエーションをオフ/オンにする</span><span class="sxs-lookup"><span data-stu-id="df84e-180">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df84e-181">A/V/STUN、MSTURN/443</span><span class="sxs-lookup"><span data-stu-id="df84e-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="df84e-182">エッジサーバーの A/V Edge サービス</span><span class="sxs-lookup"><span data-stu-id="df84e-182">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="df84e-183">任意</span><span class="sxs-lookup"><span data-stu-id="df84e-183">Any</span></span></p></td>
<td><p><span data-ttu-id="df84e-184">TCP/443 経由での候補のネゴシエーションをオフ/オンにする</span><span class="sxs-lookup"><span data-stu-id="df84e-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-internal-interface"></a><span data-ttu-id="df84e-185">NAT を使用してプライベート IP アドレスを持つ単一の統合エッジのファイアウォールの概要: 内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="df84e-185">Firewall Summary for Single Consolidated Edge with Private IP Addresses Using NAT: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="df84e-186">Protocol/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="df84e-186">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="df84e-187">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="df84e-187">Source IP address</span></span></th>
<th><span data-ttu-id="df84e-188">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="df84e-188">Destination IP address</span></span></th>
<th><span data-ttu-id="df84e-189">コメント</span><span class="sxs-lookup"><span data-stu-id="df84e-189">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="df84e-190">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="df84e-190">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="df84e-191">Any (標準エディションサーバー IP、Standard Edition server IP アドレス、または XMPP ゲートウェイサービスを実行しているプール IP アドレスとして定義できます)</span><span class="sxs-lookup"><span data-stu-id="df84e-191">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="df84e-192">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="df84e-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="df84e-193">フロントエンドサーバーまたはフロントエンドプールで実行されている XMPP ゲートウェイサービスからの送信 XMPP トラフィック</span><span class="sxs-lookup"><span data-stu-id="df84e-193">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df84e-194">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="df84e-194">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="df84e-195">Any (ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバー、フロントエンドプールの IP アドレスとして定義できます)</span><span class="sxs-lookup"><span data-stu-id="df84e-195">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="df84e-196">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="df84e-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="df84e-197">送信 SIP トラフィック (ディレクター、ディレクタープール IP アドレス、フロントエンドサーバーまたはフロントエンドプールの IP アドレス) からエッジサーバーの内部インターフェイスへ</span><span class="sxs-lookup"><span data-stu-id="df84e-197">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df84e-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="df84e-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="df84e-199">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="df84e-199">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="df84e-200">Any (ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバー、フロントエンドプールの IP アドレスとして定義できます)</span><span class="sxs-lookup"><span data-stu-id="df84e-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="df84e-201">エッジサーバーの内部インターフェイスから受信 SIP トラフィック (ディレクター、ディレクタープール IP アドレス、フロントエンドサーバー、またはフロントエンドプールの IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="df84e-201">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df84e-202">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="df84e-202">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="df84e-203">Any (フロントエンドサーバーの IP アドレス、またはフロントエンドプールの各フロントエンドサーバー IP アドレスとして定義できます)</span><span class="sxs-lookup"><span data-stu-id="df84e-203">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="df84e-204">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="df84e-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="df84e-205">フロントエンドサーバーからの Web 会議トラフィック、またはプール内の各フロントエンドサーバーから Edge Server の内部インターフェイスへの Web 会議トラフィック</span><span class="sxs-lookup"><span data-stu-id="df84e-205">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df84e-206">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="df84e-206">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="df84e-207">Any (フロントエンドサーバーの IP アドレス、またはこのエッジサーバーを使用している Survivable Branch Appliance または Survivable ブランチサーバー) として定義することができます。</span><span class="sxs-lookup"><span data-stu-id="df84e-207">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="df84e-208">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="df84e-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="df84e-209">このエッジサーバーを使用して、フロントエンドサーバーまたはフロントエンドプールの IP アドレスまたは Survivable Branch Appliance または Survivable ブランチサーバーからの、A/V ユーザー (A/V 認証サービス) の認証</span><span class="sxs-lookup"><span data-stu-id="df84e-209">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df84e-210">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="df84e-210">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="df84e-211">任意</span><span class="sxs-lookup"><span data-stu-id="df84e-211">Any</span></span></p></td>
<td><p><span data-ttu-id="df84e-212">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="df84e-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="df84e-213">内部と外部のユーザー、Survivable Branch Appliance または Survivable ブランチサーバー間の A/V メディア転送の優先パス</span><span class="sxs-lookup"><span data-stu-id="df84e-213">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df84e-214">STUN/MSTURN/443</span><span class="sxs-lookup"><span data-stu-id="df84e-214">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="df84e-215">任意</span><span class="sxs-lookup"><span data-stu-id="df84e-215">Any</span></span></p></td>
<td><p><span data-ttu-id="df84e-216">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="df84e-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="df84e-217">内部と外部のユーザーとの間でのメディア転送のフォールバックパス Survivable Branch Appliance または Survivable Branch Server (UDP 通信が確立できない場合は、TCP を使ってファイル転送とデスクトップ共有を行う)</span><span class="sxs-lookup"><span data-stu-id="df84e-217">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df84e-218">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="df84e-218">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="df84e-219">Any (任意) (フロントエンドサーバーの IP アドレス、または全体管理ストアを保持するプールとして定義できます)</span><span class="sxs-lookup"><span data-stu-id="df84e-219">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="df84e-220">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="df84e-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="df84e-221">中央管理ストアからエッジサーバーへの変更のレプリケーション</span><span class="sxs-lookup"><span data-stu-id="df84e-221">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df84e-222">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="df84e-222">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="df84e-223">任意</span><span class="sxs-lookup"><span data-stu-id="df84e-223">Any</span></span></p></td>
<td><p><span data-ttu-id="df84e-224">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="df84e-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="df84e-225">Lync Server 管理シェルと一元ログサービスコマンドレットを使用した一元管理サービスコントローラー、ClsController コマンドライン (ClsController) またはエージェント (Clscontroller .exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="df84e-225">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df84e-226">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="df84e-226">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="df84e-227">任意</span><span class="sxs-lookup"><span data-stu-id="df84e-227">Any</span></span></p></td>
<td><p><span data-ttu-id="df84e-228">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="df84e-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="df84e-229">Lync Server 管理シェルと一元ログサービスコマンドレットを使用した一元管理サービスコントローラー、ClsController コマンドライン (ClsController) またはエージェント (Clscontroller .exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="df84e-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df84e-230">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="df84e-230">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="df84e-231">任意</span><span class="sxs-lookup"><span data-stu-id="df84e-231">Any</span></span></p></td>
<td><p><span data-ttu-id="df84e-232">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="df84e-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="df84e-233">Lync Server 管理シェルと一元ログサービスコマンドレットを使用した一元管理サービスコントローラー、ClsController コマンドライン (ClsController) またはエージェント (Clscontroller .exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="df84e-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="df84e-234">フェデレーションのためのファイアウォールの概要</span><span class="sxs-lookup"><span data-stu-id="df84e-234">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="df84e-235">Role/Protocol/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="df84e-235">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="df84e-236">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="df84e-236">Source IP address</span></span></th>
<th><span data-ttu-id="df84e-237">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="df84e-237">Destination IP address</span></span></th>
<th><span data-ttu-id="df84e-238">メモ</span><span class="sxs-lookup"><span data-stu-id="df84e-238">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="df84e-239">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="df84e-239">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="df84e-240">アクセスエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="df84e-240">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="df84e-241">任意</span><span class="sxs-lookup"><span data-stu-id="df84e-241">Any</span></span></p></td>
<td><p><span data-ttu-id="df84e-242">SIP を使用するフェデレーションおよびパブリック IM 接続の場合</span><span class="sxs-lookup"><span data-stu-id="df84e-242">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="df84e-243">ファイアウォールの概要–パブリックインスタントメッセージング接続</span><span class="sxs-lookup"><span data-stu-id="df84e-243">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="df84e-244">Role/Protocol/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="df84e-244">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="df84e-245">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="df84e-245">Source IP address</span></span></th>
<th><span data-ttu-id="df84e-246">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="df84e-246">Destination IP address</span></span></th>
<th><span data-ttu-id="df84e-247">メモ</span><span class="sxs-lookup"><span data-stu-id="df84e-247">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="df84e-248">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="df84e-248">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="df84e-249">パブリック IM 接続パートナー</span><span class="sxs-lookup"><span data-stu-id="df84e-249">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="df84e-250">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="df84e-250">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="df84e-251">SIP を使用するフェデレーションおよびパブリック IM 接続の場合</span><span class="sxs-lookup"><span data-stu-id="df84e-251">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df84e-252">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="df84e-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="df84e-253">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="df84e-253">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="df84e-254">パブリック IM 接続パートナー</span><span class="sxs-lookup"><span data-stu-id="df84e-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="df84e-255">SIP を使用するフェデレーションおよびパブリック IM 接続の場合</span><span class="sxs-lookup"><span data-stu-id="df84e-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df84e-256">アクセス/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="df84e-256">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="df84e-257">クライアント</span><span class="sxs-lookup"><span data-stu-id="df84e-257">Clients</span></span></p></td>
<td><p><span data-ttu-id="df84e-258">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="df84e-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="df84e-259">外部ユーザーアクセスのクライアントツーサーバー SIP トラフィック</span><span class="sxs-lookup"><span data-stu-id="df84e-259">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df84e-260">A/V/RTP/59,999</span><span class="sxs-lookup"><span data-stu-id="df84e-260">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="df84e-261">エッジサーバーの A/V Edge サービス</span><span class="sxs-lookup"><span data-stu-id="df84e-261">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="df84e-262">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="df84e-262">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="df84e-263">パブリック IM 接続が構成されている場合、Windows Live Messenger でのセッションに使用されます。</span><span class="sxs-lookup"><span data-stu-id="df84e-263">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df84e-264">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="df84e-264">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="df84e-265">エッジサーバーの A/V Edge サービス</span><span class="sxs-lookup"><span data-stu-id="df84e-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="df84e-266">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="df84e-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="df84e-267">Windows Live Messenger とのパブリック IM 接続に必要</span><span class="sxs-lookup"><span data-stu-id="df84e-267">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df84e-268">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="df84e-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="df84e-269">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="df84e-269">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="df84e-270">エッジサーバーの A/V Edge サービス</span><span class="sxs-lookup"><span data-stu-id="df84e-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="df84e-271">Windows Live Messenger とのパブリック IM 接続に必要</span><span class="sxs-lookup"><span data-stu-id="df84e-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="df84e-272">拡張メッセージングとプレゼンスプロトコルのファイアウォールの概要</span><span class="sxs-lookup"><span data-stu-id="df84e-272">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="df84e-273">Protocol/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="df84e-273">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="df84e-274">ソース (IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="df84e-274">Source (IP address)</span></span></th>
<th><span data-ttu-id="df84e-275">宛先 (IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="df84e-275">Destination (IP address)</span></span></th>
<th><span data-ttu-id="df84e-276">コメント</span><span class="sxs-lookup"><span data-stu-id="df84e-276">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="df84e-277">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="df84e-277">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="df84e-278">任意</span><span class="sxs-lookup"><span data-stu-id="df84e-278">Any</span></span></p></td>
<td><p><span data-ttu-id="df84e-279">エッジサーバーアクセスエッジサービスインターフェイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="df84e-279">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="df84e-280">XMPP 向けの標準的なサーバー間通信ポート。</span><span class="sxs-lookup"><span data-stu-id="df84e-280">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="df84e-281">フェデレーションされた XMPP パートナーからエッジサーバーの XMPP プロキシへの通信を許可します。</span><span class="sxs-lookup"><span data-stu-id="df84e-281">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df84e-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="df84e-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="df84e-283">エッジサーバーアクセスエッジサービスインターフェイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="df84e-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="df84e-284">任意</span><span class="sxs-lookup"><span data-stu-id="df84e-284">Any</span></span></p></td>
<td><p><span data-ttu-id="df84e-285">XMPP 向けの標準的なサーバー間通信ポート。</span><span class="sxs-lookup"><span data-stu-id="df84e-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="df84e-286">エッジサーバーの XMPP プロキシからフェデレーションされた XMPP パートナーへの通信を許可します。</span><span class="sxs-lookup"><span data-stu-id="df84e-286">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df84e-287">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="df84e-287">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="df84e-288">任意</span><span class="sxs-lookup"><span data-stu-id="df84e-288">Any</span></span></p></td>
<td><p><span data-ttu-id="df84e-289">各内部エッジサーバーインターフェイス IP</span><span class="sxs-lookup"><span data-stu-id="df84e-289">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="df84e-290">フロントエンドサーバーまたはフロントエンドプールの XMPP ゲートウェイから Edge Server 内部 IP アドレスまたは各エッジプールメンバーの内部 IP アドレスへの内部の XMPP トラフィック</span><span class="sxs-lookup"><span data-stu-id="df84e-290">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

