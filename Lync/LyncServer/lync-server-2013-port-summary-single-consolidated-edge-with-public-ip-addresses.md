---
title: ポートの概要 - パブリック IP アドレスを使用する単一の統合エッジ
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
ms.openlocfilehash: 7ad4d6dc9b7eda2e476068d5fae4a40d066a0d71
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="4f51f-102">ポートの概要 - Lync Server 2013 でパブリック IP アドレスを使用する単一の統合エッジ</span><span class="sxs-lookup"><span data-stu-id="4f51f-102">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f51f-103">_**最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="4f51f-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="4f51f-104">このシナリオアーキテクチャで説明されている Lync Server 2013 のエッジサーバー機能は、Lync Server 2010 で実装されたものとよく似ています。</span><span class="sxs-lookup"><span data-stu-id="4f51f-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="4f51f-105">最も顕著な追加機能は、拡張メッセージングとプレゼンスプロトコル (XMPP) の TCP エントリのポート**5269**です。</span><span class="sxs-lookup"><span data-stu-id="4f51f-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="4f51f-106">Lync Server 2013 では、必要に応じて、microsoft Edge サーバーまたはエッジプールに XMPP プロキシを展開し、フロントエンドサーバーまたはフロントエンドプールに XMPP ゲートウェイサーバーを配置します。</span><span class="sxs-lookup"><span data-stu-id="4f51f-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span> <span data-ttu-id="4f51f-107">リバースプロキシおよびフェデレーションの計画情報については、「 [lync server 2013 のリバースプロキシのシナリオ](lync-server-2013-scenarios-for-reverse-proxy.md)」および「 [lync server 2013 セクションでの SIP、xmpp フェデレーション、パブリックインスタントメッセージングの計画](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f51f-107">Planning information for the reverse proxy and federation are found in [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) and [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) sections, respectively.</span></span>

<span data-ttu-id="4f51f-108">IPv4 に加えて、エッジサーバーは IPv6 をサポートするようになりました。</span><span class="sxs-lookup"><span data-stu-id="4f51f-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="4f51f-109">わかりやすくするために、シナリオでは IPv4 のみが使用されます。</span><span class="sxs-lookup"><span data-stu-id="4f51f-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="4f51f-110">**パブリック IP アドレスを使った単一の統合エッジのエンタープライズ境界ネットワーク**</span><span class="sxs-lookup"><span data-stu-id="4f51f-110">**Enterprise perimeter network for single consolidated edge with public IP addressing**</span></span>

<span data-ttu-id="4f51f-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="4f51f-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="4f51f-112">ポートとプロトコルの詳細</span><span class="sxs-lookup"><span data-stu-id="4f51f-112">Port and Protocol Details</span></span>

<span data-ttu-id="4f51f-113">外部アクセスを提供する機能をサポートするために必要なポートのみを開くことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4f51f-113">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="4f51f-114">エッジサービスに対してリモートアクセスを使用するには、受信/送信エッジトラフィックの図に示すように、SIP トラフィックが双方向に流れるようにすることが必須です。</span><span class="sxs-lookup"><span data-stu-id="4f51f-114">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bidirectionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="4f51f-115">別の方法として、アクセスエッジサービスとの間の SIP メッセージングは、インスタントメッセージング (IM)、プレゼンス、web 会議、音声/ビデオ (A/V)、およびフェデレーションに関連しています。</span><span class="sxs-lookup"><span data-stu-id="4f51f-115">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-external-interface"></a><span data-ttu-id="4f51f-116">パブリック IP アドレスを持つ単一の統合エッジのファイアウォールの概要: 外部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4f51f-116">Firewall Summary for Single Consolidated Edge with Public IP Addresses: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f51f-117">Role/Protocol/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="4f51f-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="4f51f-118">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4f51f-118">Source IP address</span></span></th>
<th><span data-ttu-id="4f51f-119">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4f51f-119">Destination IP address</span></span></th>
<th><span data-ttu-id="4f51f-120">メモ</span><span class="sxs-lookup"><span data-stu-id="4f51f-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f51f-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="4f51f-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="4f51f-122">任意</span><span class="sxs-lookup"><span data-stu-id="4f51f-122">Any</span></span></p></td>
<td><p><span data-ttu-id="4f51f-123">XMPP プロキシサービス (アクセスエッジサービスで IP アドレスを共有)</span><span class="sxs-lookup"><span data-stu-id="4f51f-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="4f51f-124">XMPP プロキシサービスは、定義された XMPP フェデレーションの XMPP 連絡先からのトラフィックを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="4f51f-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f51f-125">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="4f51f-125">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="4f51f-126">エッジサーバーアクセスエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4f51f-126">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="4f51f-127">任意</span><span class="sxs-lookup"><span data-stu-id="4f51f-127">Any</span></span></p></td>
<td><p><span data-ttu-id="4f51f-128">証明書の失効/CRL の確認と取得</span><span class="sxs-lookup"><span data-stu-id="4f51f-128">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f51f-129">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="4f51f-129">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="4f51f-130">エッジサーバーアクセスエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4f51f-130">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="4f51f-131">任意</span><span class="sxs-lookup"><span data-stu-id="4f51f-131">Any</span></span></p></td>
<td><p><span data-ttu-id="4f51f-132">TCP 経由の DNS クエリ</span><span class="sxs-lookup"><span data-stu-id="4f51f-132">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f51f-133">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="4f51f-133">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="4f51f-134">エッジサーバーアクセスエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4f51f-134">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="4f51f-135">任意</span><span class="sxs-lookup"><span data-stu-id="4f51f-135">Any</span></span></p></td>
<td><p><span data-ttu-id="4f51f-136">UDP 経由の DNS クエリ</span><span class="sxs-lookup"><span data-stu-id="4f51f-136">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f51f-137">アクセス/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="4f51f-137">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="4f51f-138">任意</span><span class="sxs-lookup"><span data-stu-id="4f51f-138">Any</span></span></p></td>
<td><p><span data-ttu-id="4f51f-139">エッジサーバーアクセスエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4f51f-139">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="4f51f-140">外部ユーザーアクセスのクライアントツーサーバー SIP トラフィック</span><span class="sxs-lookup"><span data-stu-id="4f51f-140">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f51f-141">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="4f51f-141">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="4f51f-142">任意</span><span class="sxs-lookup"><span data-stu-id="4f51f-142">Any</span></span></p></td>
<td><p><span data-ttu-id="4f51f-143">エッジサーバーアクセスエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4f51f-143">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="4f51f-144">SIP を使用するフェデレーションおよびパブリック IM 接続の場合</span><span class="sxs-lookup"><span data-stu-id="4f51f-144">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f51f-145">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="4f51f-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="4f51f-146">エッジサーバーアクセスエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4f51f-146">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="4f51f-147">任意</span><span class="sxs-lookup"><span data-stu-id="4f51f-147">Any</span></span></p></td>
<td><p><span data-ttu-id="4f51f-148">SIP を使用するフェデレーションおよびパブリック IM 接続の場合</span><span class="sxs-lookup"><span data-stu-id="4f51f-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f51f-149">Web 会議/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="4f51f-149">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="4f51f-150">任意</span><span class="sxs-lookup"><span data-stu-id="4f51f-150">Any</span></span></p></td>
<td><p><span data-ttu-id="4f51f-151">エッジサーバー Web 会議エッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4f51f-151">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="4f51f-152">Web 会議メディア</span><span class="sxs-lookup"><span data-stu-id="4f51f-152">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f51f-153">A/V/RTP/59,999</span><span class="sxs-lookup"><span data-stu-id="4f51f-153">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="4f51f-154">エッジサーバーアクセスエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4f51f-154">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="4f51f-155">任意</span><span class="sxs-lookup"><span data-stu-id="4f51f-155">Any</span></span></p></td>
<td><p><span data-ttu-id="4f51f-156">Office Communications Server 2007、Office Communications Server 2007 R2、Lync Server 2010、および Lync Server 2013 を実行しているパートナーとのフェデレーションに必要。</span><span class="sxs-lookup"><span data-stu-id="4f51f-156">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f51f-157">A/V/RTP/59,999</span><span class="sxs-lookup"><span data-stu-id="4f51f-157">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="4f51f-158">エッジサーバーの A/V エッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4f51f-158">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="4f51f-159">任意</span><span class="sxs-lookup"><span data-stu-id="4f51f-159">Any</span></span></p></td>
<td><p><span data-ttu-id="4f51f-160">Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必須</span><span class="sxs-lookup"><span data-stu-id="4f51f-160">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f51f-161">A/V/RTP/59,999</span><span class="sxs-lookup"><span data-stu-id="4f51f-161">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="4f51f-162">任意</span><span class="sxs-lookup"><span data-stu-id="4f51f-162">Any</span></span></p></td>
<td><p><span data-ttu-id="4f51f-163">エッジサーバーの A/V エッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4f51f-163">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="4f51f-164">Office Communications Server 2007 を実行しているパートナーとのフェデレーションの場合のみ必須です。</span><span class="sxs-lookup"><span data-stu-id="4f51f-164">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f51f-165">A/V/RTP/59,999</span><span class="sxs-lookup"><span data-stu-id="4f51f-165">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="4f51f-166">任意</span><span class="sxs-lookup"><span data-stu-id="4f51f-166">Any</span></span></p></td>
<td><p><span data-ttu-id="4f51f-167">エッジサーバーの A/V エッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4f51f-167">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="4f51f-168">Office Communications Server 2007 を実行しているパートナーとのフェデレーションの場合のみ必須です。</span><span class="sxs-lookup"><span data-stu-id="4f51f-168">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f51f-169">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="4f51f-169">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="4f51f-170">エッジサーバーの A/V エッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4f51f-170">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="4f51f-171">任意</span><span class="sxs-lookup"><span data-stu-id="4f51f-171">Any</span></span></p></td>
<td><p><span data-ttu-id="4f51f-172">3478送信は、Lync Server が通信するエッジサーバーのバージョンと、エッジサーバーからエッジサーバーへのメディアトラフィックも確認するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="4f51f-172">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="4f51f-173">Lync Server 2010、Windows Live Messenger、Office Communications Server 2007 R2 とのフェデレーション、および複数のエッジプールが会社内に展開されている場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="4f51f-173">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f51f-174">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="4f51f-174">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="4f51f-175">任意</span><span class="sxs-lookup"><span data-stu-id="4f51f-175">Any</span></span></p></td>
<td><p><span data-ttu-id="4f51f-176">エッジサーバーの A/V エッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4f51f-176">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="4f51f-177">UDP/3478 経由の候補のネゴシエーションをオフ/オンにする</span><span class="sxs-lookup"><span data-stu-id="4f51f-177">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f51f-178">A/V/STUN、MSTURN/443</span><span class="sxs-lookup"><span data-stu-id="4f51f-178">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="4f51f-179">任意</span><span class="sxs-lookup"><span data-stu-id="4f51f-179">Any</span></span></p></td>
<td><p><span data-ttu-id="4f51f-180">エッジサーバーの A/V エッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4f51f-180">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="4f51f-181">TCP/443 経由での候補のネゴシエーションをオフ/オンにする</span><span class="sxs-lookup"><span data-stu-id="4f51f-181">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f51f-182">A/V/STUN、MSTURN/443</span><span class="sxs-lookup"><span data-stu-id="4f51f-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="4f51f-183">エッジサーバーの A/V エッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4f51f-183">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="4f51f-184">任意</span><span class="sxs-lookup"><span data-stu-id="4f51f-184">Any</span></span></p></td>
<td><p><span data-ttu-id="4f51f-185">TCP/443 経由での候補のネゴシエーションをオフ/オンにする</span><span class="sxs-lookup"><span data-stu-id="4f51f-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-internal-interface"></a><span data-ttu-id="4f51f-186">パブリック IP アドレスを持つ単一の統合エッジのファイアウォールの概要: 内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4f51f-186">Firewall Summary for Single Consolidated Edge with Public IP Addresses: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f51f-187">Protocol/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="4f51f-187">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="4f51f-188">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4f51f-188">Source IP address</span></span></th>
<th><span data-ttu-id="4f51f-189">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4f51f-189">Destination IP address</span></span></th>
<th><span data-ttu-id="4f51f-190">コメント</span><span class="sxs-lookup"><span data-stu-id="4f51f-190">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f51f-191">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="4f51f-191">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="4f51f-192">Any (標準エディションサーバー IP、Standard Edition server IP アドレス、または XMPP ゲートウェイサービスを実行しているプール IP アドレスとして定義できます)</span><span class="sxs-lookup"><span data-stu-id="4f51f-192">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="4f51f-193">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4f51f-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4f51f-194">フロントエンドサーバーまたはフロントエンドプールで実行されている XMPP ゲートウェイサービスからの送信 XMPP トラフィック</span><span class="sxs-lookup"><span data-stu-id="4f51f-194">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f51f-195">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="4f51f-195">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="4f51f-196">Any (ディレクター、ディレクタープールの IP アドレス、フロントエンドサーバー、フロントエンドプールの IP アドレスとして定義できます)</span><span class="sxs-lookup"><span data-stu-id="4f51f-196">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="4f51f-197">エッジサーバー IP、または内部インターフェイスを保持するプール</span><span class="sxs-lookup"><span data-stu-id="4f51f-197">Edge Server IP, or pool that holds the internal interface</span></span></p></td>
<td><p><span data-ttu-id="4f51f-198">送信 SIP トラフィック (ディレクター、ディレクタープール IP アドレス、フロントエンドサーバーまたはフロントエンドプールの IP アドレス) からエッジサーバーの内部インターフェイスへ</span><span class="sxs-lookup"><span data-stu-id="4f51f-198">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f51f-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="4f51f-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="4f51f-200">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4f51f-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4f51f-201">Any (ディレクター、ディレクタープール IP アドレス、フロントエンドサーバー、フロントエンドプールのアドレスとして定義できます)</span><span class="sxs-lookup"><span data-stu-id="4f51f-201">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool address)</span></span></p></td>
<td><p><span data-ttu-id="4f51f-202">エッジサーバーの内部インターフェイスから受信 SIP トラフィック (ディレクター、ディレクタープール IP アドレス、フロントエンドサーバー、またはフロントエンドプールの IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="4f51f-202">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f51f-203">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="4f51f-203">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="4f51f-204">Any (フロントエンドサーバーの IP アドレス、またはフロントエンドプールの各フロントエンドサーバー IP アドレスとして定義できます)</span><span class="sxs-lookup"><span data-stu-id="4f51f-204">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="4f51f-205">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4f51f-205">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4f51f-206">フロントエンドサーバーからの Web 会議トラフィック、またはプール内の各フロントエンドサーバーから Edge Server の内部インターフェイスへの Web 会議トラフィック</span><span class="sxs-lookup"><span data-stu-id="4f51f-206">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f51f-207">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="4f51f-207">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="4f51f-208">Any (フロントエンドサーバーの IP アドレス、またはこのエッジサーバーを使用している Survivable Branch Appliance または Survivable ブランチサーバー) として定義することができます。</span><span class="sxs-lookup"><span data-stu-id="4f51f-208">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="4f51f-209">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4f51f-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4f51f-210">このエッジサーバーを使用して、フロントエンドサーバーまたはフロントエンドプールの IP アドレスまたは Survivable Branch Appliance または Survivable ブランチサーバーからの、A/V ユーザー (A/V 認証サービス) の認証</span><span class="sxs-lookup"><span data-stu-id="4f51f-210">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f51f-211">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="4f51f-211">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="4f51f-212">任意</span><span class="sxs-lookup"><span data-stu-id="4f51f-212">Any</span></span></p></td>
<td><p><span data-ttu-id="4f51f-213">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4f51f-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4f51f-214">内部と外部のユーザー、Survivable Branch Appliance または Survivable ブランチサーバー間の A/V メディア転送の優先パス</span><span class="sxs-lookup"><span data-stu-id="4f51f-214">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f51f-215">STUN/MSTURN/443</span><span class="sxs-lookup"><span data-stu-id="4f51f-215">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="4f51f-216">任意</span><span class="sxs-lookup"><span data-stu-id="4f51f-216">Any</span></span></p></td>
<td><p><span data-ttu-id="4f51f-217">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4f51f-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4f51f-218">内部と外部のユーザーとの間でのメディア転送のフォールバックパス Survivable Branch Appliance または Survivable Branch Server (UDP 通信が確立できない場合は、TCP を使ってファイル転送とデスクトップ共有を行う)</span><span class="sxs-lookup"><span data-stu-id="4f51f-218">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f51f-219">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="4f51f-219">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="4f51f-220">Any (任意) (フロントエンドサーバーの IP アドレス、または全体管理ストアを保持するプールとして定義できます)</span><span class="sxs-lookup"><span data-stu-id="4f51f-220">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="4f51f-221">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4f51f-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4f51f-222">中央管理ストアからエッジサーバーへの変更のレプリケーション</span><span class="sxs-lookup"><span data-stu-id="4f51f-222">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f51f-223">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="4f51f-223">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="4f51f-224">任意</span><span class="sxs-lookup"><span data-stu-id="4f51f-224">Any</span></span></p></td>
<td><p><span data-ttu-id="4f51f-225">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4f51f-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4f51f-226">Lync Server 管理シェルと一元ログサービスコマンドレットを使用した一元管理サービスコントローラー、ClsController コマンドライン (ClsController) またはエージェント (Clscontroller .exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="4f51f-226">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f51f-227">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="4f51f-227">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="4f51f-228">任意</span><span class="sxs-lookup"><span data-stu-id="4f51f-228">Any</span></span></p></td>
<td><p><span data-ttu-id="4f51f-229">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4f51f-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4f51f-230">Lync Server 管理シェルと一元ログサービスコマンドレットを使用した一元管理サービスコントローラー、ClsController コマンドライン (ClsController) またはエージェント (Clscontroller .exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="4f51f-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f51f-231">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="4f51f-231">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="4f51f-232">任意</span><span class="sxs-lookup"><span data-stu-id="4f51f-232">Any</span></span></p></td>
<td><p><span data-ttu-id="4f51f-233">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4f51f-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4f51f-234">Lync Server 管理シェルと一元ログサービスコマンドレットを使用した一元管理サービスコントローラー、ClsController コマンドライン (ClsController) またはエージェント (Clscontroller .exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="4f51f-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="4f51f-235">フェデレーションのためのファイアウォールの概要</span><span class="sxs-lookup"><span data-stu-id="4f51f-235">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f51f-236">Role/Protocol/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="4f51f-236">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="4f51f-237">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4f51f-237">Source IP address</span></span></th>
<th><span data-ttu-id="4f51f-238">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4f51f-238">Destination IP address</span></span></th>
<th><span data-ttu-id="4f51f-239">メモ</span><span class="sxs-lookup"><span data-stu-id="4f51f-239">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f51f-240">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="4f51f-240">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="4f51f-241">アクセスエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4f51f-241">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="4f51f-242">任意</span><span class="sxs-lookup"><span data-stu-id="4f51f-242">Any</span></span></p></td>
<td><p><span data-ttu-id="4f51f-243">SIP を使用するフェデレーションおよびパブリック IM 接続の場合</span><span class="sxs-lookup"><span data-stu-id="4f51f-243">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="4f51f-244">ファイアウォールの概要–パブリックインスタントメッセージング接続</span><span class="sxs-lookup"><span data-stu-id="4f51f-244">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f51f-245">Role/Protocol/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="4f51f-245">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="4f51f-246">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4f51f-246">Source IP address</span></span></th>
<th><span data-ttu-id="4f51f-247">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4f51f-247">Destination IP address</span></span></th>
<th><span data-ttu-id="4f51f-248">メモ</span><span class="sxs-lookup"><span data-stu-id="4f51f-248">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f51f-249">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="4f51f-249">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="4f51f-250">パブリック IM 接続パートナー</span><span class="sxs-lookup"><span data-stu-id="4f51f-250">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="4f51f-251">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="4f51f-251">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="4f51f-252">SIP を使用するフェデレーションおよびパブリック IM 接続の場合</span><span class="sxs-lookup"><span data-stu-id="4f51f-252">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f51f-253">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="4f51f-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="4f51f-254">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="4f51f-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="4f51f-255">パブリック IM 接続パートナー</span><span class="sxs-lookup"><span data-stu-id="4f51f-255">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="4f51f-256">SIP を使用するフェデレーションおよびパブリック IM 接続の場合</span><span class="sxs-lookup"><span data-stu-id="4f51f-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f51f-257">アクセス/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="4f51f-257">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="4f51f-258">クライアント</span><span class="sxs-lookup"><span data-stu-id="4f51f-258">Clients</span></span></p></td>
<td><p><span data-ttu-id="4f51f-259">エッジサーバーアクセスエッジサービス</span><span class="sxs-lookup"><span data-stu-id="4f51f-259">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="4f51f-260">外部ユーザーアクセスのクライアントツーサーバー SIP トラフィック</span><span class="sxs-lookup"><span data-stu-id="4f51f-260">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f51f-261">A/V/RTP/59,999</span><span class="sxs-lookup"><span data-stu-id="4f51f-261">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="4f51f-262">エッジサーバーの A/V Edge サービス</span><span class="sxs-lookup"><span data-stu-id="4f51f-262">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="4f51f-263">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="4f51f-263">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="4f51f-264">パブリック IM 接続が構成されている場合、Windows Live Messenger でのセッションに使用されます。</span><span class="sxs-lookup"><span data-stu-id="4f51f-264">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f51f-265">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="4f51f-265">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="4f51f-266">エッジサーバーの A/V Edge サービス</span><span class="sxs-lookup"><span data-stu-id="4f51f-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="4f51f-267">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="4f51f-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="4f51f-268">Windows Live Messenger とのパブリック IM 接続に必要</span><span class="sxs-lookup"><span data-stu-id="4f51f-268">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f51f-269">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="4f51f-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="4f51f-270">Live Messenger クライアント</span><span class="sxs-lookup"><span data-stu-id="4f51f-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="4f51f-271">エッジサーバーの A/V Edge サービス</span><span class="sxs-lookup"><span data-stu-id="4f51f-271">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="4f51f-272">Windows Live Messenger とのパブリック IM 接続に必要</span><span class="sxs-lookup"><span data-stu-id="4f51f-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="4f51f-273">拡張メッセージングとプレゼンスプロトコルのファイアウォールの概要</span><span class="sxs-lookup"><span data-stu-id="4f51f-273">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f51f-274">Protocol/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="4f51f-274">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="4f51f-275">ソース (IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="4f51f-275">Source (IP address)</span></span></th>
<th><span data-ttu-id="4f51f-276">宛先 (IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="4f51f-276">Destination (IP address)</span></span></th>
<th><span data-ttu-id="4f51f-277">コメント</span><span class="sxs-lookup"><span data-stu-id="4f51f-277">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f51f-278">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="4f51f-278">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="4f51f-279">任意</span><span class="sxs-lookup"><span data-stu-id="4f51f-279">Any</span></span></p></td>
<td><p><span data-ttu-id="4f51f-280">エッジサーバーアクセスエッジサービスインターフェイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4f51f-280">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="4f51f-281">XMPP 向けの標準的なサーバー間通信ポート。</span><span class="sxs-lookup"><span data-stu-id="4f51f-281">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="4f51f-282">フェデレーションされた XMPP パートナーからエッジサーバーの XMPP プロキシへの通信を許可します。</span><span class="sxs-lookup"><span data-stu-id="4f51f-282">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f51f-283">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="4f51f-283">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="4f51f-284">エッジサーバーアクセスエッジサービスインターフェイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4f51f-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="4f51f-285">任意</span><span class="sxs-lookup"><span data-stu-id="4f51f-285">Any</span></span></p></td>
<td><p><span data-ttu-id="4f51f-286">XMPP 向けの標準的なサーバー間通信ポート。</span><span class="sxs-lookup"><span data-stu-id="4f51f-286">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="4f51f-287">エッジサーバーの XMPP プロキシからフェデレーションされた XMPP パートナーへの通信を許可します。</span><span class="sxs-lookup"><span data-stu-id="4f51f-287">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f51f-288">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="4f51f-288">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="4f51f-289">任意</span><span class="sxs-lookup"><span data-stu-id="4f51f-289">Any</span></span></p></td>
<td><p><span data-ttu-id="4f51f-290">各内部エッジサーバーインターフェイス IP</span><span class="sxs-lookup"><span data-stu-id="4f51f-290">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="4f51f-291">フロントエンドサーバーまたはフロントエンドプールの XMPP ゲートウェイから Edge Server 内部 IP アドレスまたは各エッジプールメンバーの内部 IP アドレスへの内部の XMPP トラフィック</span><span class="sxs-lookup"><span data-stu-id="4f51f-291">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

