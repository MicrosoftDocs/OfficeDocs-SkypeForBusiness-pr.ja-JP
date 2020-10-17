---
title: ポートの概要-拡張統合エッジ (ロードバランサー機器を使用)
description: ポートの概要-拡張統合エッジ (ロードバランサー機器を使用)。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 91213b1e-f875-464b-83e8-fe3a351595a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398739(v=OCS.15)
ms:contentKeyID: 48184841
ms.date: 04/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a03acb3644d83669bcf0065ebb20c526ef5fa32
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564593"
---
# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="b035e-103">ポートの概要-Lync Server 2013 の拡張統合エッジ (ロードバランサー機器を含む)</span><span class="sxs-lookup"><span data-stu-id="b035e-103">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b035e-104">_**トピックの最終更新日:** 2015-04-27_</span><span class="sxs-lookup"><span data-stu-id="b035e-104">_**Topic Last Modified:** 2015-04-27_</span></span>

<span data-ttu-id="b035e-105">このシナリオアーキテクチャで説明されている Lync server 2013 のエッジサーバー機能は、Lync Server 2010 で実装されていたものとよく似ています。</span><span class="sxs-lookup"><span data-stu-id="b035e-105">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="b035e-106">最も目を引くのは、XMPP (Extensible Messaging and Presence Protocol) 用の ポート **5269/TCP** エントリが追加されたことです。</span><span class="sxs-lookup"><span data-stu-id="b035e-106">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="b035e-107">Lync Server 2013 は、フロントエンドサーバーまたはフロントエンドプールに、エッジサーバーまたはエッジプールおよび XMPP ゲートウェイサーバー上に XMPP プロキシを任意で展開します。</span><span class="sxs-lookup"><span data-stu-id="b035e-107">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="b035e-108">IPv4 に加えて、エッジサーバーは IPv6 をサポートするようになりました。</span><span class="sxs-lookup"><span data-stu-id="b035e-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="b035e-109">わかりやすいように、シナリオでは IPv4 のみを使用します。</span><span class="sxs-lookup"><span data-stu-id="b035e-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="b035e-110">**ハードウェア負荷分散を使用する拡張統合エッジ**</span><span class="sxs-lookup"><span data-stu-id="b035e-110">**Scaled Consolidated Edge using Hardware Load Balancing**</span></span>

<span data-ttu-id="b035e-111">![エッジサーバー境界ネットワークのポートとプロトコル](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "エッジサーバー境界ネットワークのポートとプロトコル")</span><span class="sxs-lookup"><span data-stu-id="b035e-111">![Edge Server Perimeter Network ports and protocols](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Edge Server Perimeter Network ports and protocols")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="b035e-112">ポートとプロトコルの詳細</span><span class="sxs-lookup"><span data-stu-id="b035e-112">Port and Protocol Details</span></span>

<span data-ttu-id="b035e-113">外部アクセスを提供する機能のサポートに必要なポートのみを開くことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b035e-113">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="b035e-p103">エッジ サービスのリモート アクセスが機能するためには、受信/送信のエッジ トラフィックの図が示すように、SIP トラフィックの双方向通過が許可されていることが必須です。つまり、インスタント メッセージング (IM)、プレゼンス、Web 会議、音声ビデオ (A/V)、およびフェデレーションでは、アクセス エッジ サービスとの間で SIP メッセージングが実行されます。</span><span class="sxs-lookup"><span data-stu-id="b035e-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="b035e-116">拡張統合エッジのファイアウォールの概要 (ハードウェア負荷分散): 外部インターフェイス–ノード1およびノード 2 (例)</span><span class="sxs-lookup"><span data-stu-id="b035e-116">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b035e-117">役割/プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="b035e-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b035e-118">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b035e-118">Source IP address</span></span></th>
<th><span data-ttu-id="b035e-119">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b035e-119">Destination IP address</span></span></th>
<th><span data-ttu-id="b035e-120">Notes</span><span class="sxs-lookup"><span data-stu-id="b035e-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b035e-121">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="b035e-121">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="b035e-122">エッジサーバーアクセスエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b035e-122">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b035e-123">任意</span><span class="sxs-lookup"><span data-stu-id="b035e-123">Any</span></span></p></td>
<td><p><span data-ttu-id="b035e-124">証明書の失効/CRL のチェックおよび取得</span><span class="sxs-lookup"><span data-stu-id="b035e-124">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b035e-125">アクセス/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="b035e-125">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="b035e-126">エッジサーバーアクセスエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b035e-126">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b035e-127">任意</span><span class="sxs-lookup"><span data-stu-id="b035e-127">Any</span></span></p></td>
<td><p><span data-ttu-id="b035e-128">TCP による DNS クエリ</span><span class="sxs-lookup"><span data-stu-id="b035e-128">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b035e-129">アクセス/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="b035e-129">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="b035e-130">エッジサーバーアクセスエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b035e-130">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b035e-131">任意</span><span class="sxs-lookup"><span data-stu-id="b035e-131">Any</span></span></p></td>
<td><p><span data-ttu-id="b035e-132">UDP による DNS クエリ</span><span class="sxs-lookup"><span data-stu-id="b035e-132">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b035e-133">音声/V/RTP/TCP/50,000-59999</span><span class="sxs-lookup"><span data-stu-id="b035e-133">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b035e-134">エッジサーバーの音声ビデオエッジサービスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b035e-134">Edge Server A/V Edge service IP address</span></span></p></td>
<td><p><span data-ttu-id="b035e-135">任意</span><span class="sxs-lookup"><span data-stu-id="b035e-135">Any</span></span></p></td>
<td><p><span data-ttu-id="b035e-136">Office Communications Server 2007、Office Communications Server 2007 R2、Lync Server 2010、Lync Server 2013 を実行しているパートナーとのフェデレーションに必要です。</span><span class="sxs-lookup"><span data-stu-id="b035e-136">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b035e-137">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="b035e-137">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b035e-138">エッジサーバーの音声ビデオエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b035e-138">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b035e-139">任意</span><span class="sxs-lookup"><span data-stu-id="b035e-139">Any</span></span></p></td>
<td><p><span data-ttu-id="b035e-140">Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必要。</span><span class="sxs-lookup"><span data-stu-id="b035e-140">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b035e-141">音声/V/RTP/TCP/50,000-59999</span><span class="sxs-lookup"><span data-stu-id="b035e-141">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b035e-142">任意</span><span class="sxs-lookup"><span data-stu-id="b035e-142">Any</span></span></p></td>
<td><p><span data-ttu-id="b035e-143">エッジサーバーの音声ビデオエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b035e-143">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b035e-144">Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必要</span><span class="sxs-lookup"><span data-stu-id="b035e-144">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b035e-145">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="b035e-145">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b035e-146">任意</span><span class="sxs-lookup"><span data-stu-id="b035e-146">Any</span></span></p></td>
<td><p><span data-ttu-id="b035e-147">エッジサーバーの音声ビデオエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b035e-147">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b035e-148">Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必要</span><span class="sxs-lookup"><span data-stu-id="b035e-148">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b035e-149">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b035e-149">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b035e-150">エッジサーバーの音声ビデオエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b035e-150">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b035e-151">任意</span><span class="sxs-lookup"><span data-stu-id="b035e-151">Any</span></span></p></td>
<td><p><span data-ttu-id="b035e-152">3478の送信は、Lync Server の通信相手であるエッジサーバーのバージョンと、エッジサーバー間のメディアトラフィックに使用されます。</span><span class="sxs-lookup"><span data-stu-id="b035e-152">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="b035e-153">Lync Server 2010、Windows Live Messenger、および Office Communications Server 2007 R2 とのフェデレーションに必要です。また、複数のエッジプールが会社内に展開されている場合も必須です。</span><span class="sxs-lookup"><span data-stu-id="b035e-153">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b035e-154">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b035e-154">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b035e-155">任意</span><span class="sxs-lookup"><span data-stu-id="b035e-155">Any</span></span></p></td>
<td><p><span data-ttu-id="b035e-156">エッジサーバーの音声ビデオエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b035e-156">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b035e-157">STUN/UDP による候補の TURN ネゴシエーション/3478</span><span class="sxs-lookup"><span data-stu-id="b035e-157">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b035e-158">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b035e-158">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b035e-159">任意</span><span class="sxs-lookup"><span data-stu-id="b035e-159">Any</span></span></p></td>
<td><p><span data-ttu-id="b035e-160">エッジサーバーの音声ビデオエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b035e-160">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b035e-161">STUN/TCP による候補の TURN ネゴシエーション/443</span><span class="sxs-lookup"><span data-stu-id="b035e-161">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b035e-162">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b035e-162">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b035e-163">エッジサーバーの音声ビデオエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b035e-163">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b035e-164">任意</span><span class="sxs-lookup"><span data-stu-id="b035e-164">Any</span></span></p></td>
<td><p><span data-ttu-id="b035e-165">STUN/TCP による候補の TURN ネゴシエーション/443</span><span class="sxs-lookup"><span data-stu-id="b035e-165">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a><span data-ttu-id="b035e-166">拡張統合エッジのファイアウォールの概要ハードウェア負荷分散: ノード1およびノード2の内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b035e-166">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Node 1 and Node 2</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b035e-167">役割/プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="b035e-167">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b035e-168">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b035e-168">Source IP address</span></span></th>
<th><span data-ttu-id="b035e-169">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b035e-169">Destination IP address</span></span></th>
<th><span data-ttu-id="b035e-170">Notes</span><span class="sxs-lookup"><span data-stu-id="b035e-170">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b035e-171">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="b035e-171">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="b035e-172">任意 (フロントエンドサーバーのアドレス、または XMPP ゲートウェイサービスを実行しているフロントエンドプールの仮想 IP アドレスとして定義可能)</span><span class="sxs-lookup"><span data-stu-id="b035e-172">Any (can be defined as Front End Server address, or Front End pool virtual IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="b035e-173">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b035e-173">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b035e-174">フロントエンドサーバーまたはフロントエンドプールで実行されている XMPP ゲートウェイサービスからの送信 XMPP トラフィック</span><span class="sxs-lookup"><span data-stu-id="b035e-174">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b035e-175">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="b035e-175">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="b035e-176">任意 (中央管理ストアを保持するフロントエンドサーバーサーバーの IP またはプールとして定義可能)</span><span class="sxs-lookup"><span data-stu-id="b035e-176">Any (can be defined as the Front End Server server IP or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="b035e-177">エッジ サーバー内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b035e-177">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="b035e-178">中央管理ストアからエッジ サーバーへの変更のレプリケーション</span><span class="sxs-lookup"><span data-stu-id="b035e-178">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b035e-179">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="b035e-179">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="b035e-180">任意 (ディレクター IP、フロントエンドサーバー IP またはプールの仮想 IP として定義可能)</span><span class="sxs-lookup"><span data-stu-id="b035e-180">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="b035e-181">エッジ サーバー内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b035e-181">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="b035e-182">内部展開から内部エッジ サーバー インターフェイスへの Web 会議トラフィック</span><span class="sxs-lookup"><span data-stu-id="b035e-182">Web conferencing traffic from Internal deployment to Internal Edge Server interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b035e-183">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b035e-183">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b035e-184">任意 (ディレクター IP、フロントエンドサーバー IP またはプールの仮想 IP として定義可能)</span><span class="sxs-lookup"><span data-stu-id="b035e-184">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="b035e-185">エッジ サーバー内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b035e-185">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="b035e-186">内部ユーザーと外部ユーザーとの間の音声ビデオメディア転送の優先パス、存続可能 Branch Appliance または存続可能 Branch Server</span><span class="sxs-lookup"><span data-stu-id="b035e-186">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b035e-187">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b035e-187">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b035e-188">任意 (ディレクター IP、フロントエンドサーバー IP またはプールの仮想 IP として定義可能)</span><span class="sxs-lookup"><span data-stu-id="b035e-188">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="b035e-189">エッジ サーバー内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b035e-189">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="b035e-190">内部ユーザーと外部ユーザーとの間の音声ビデオメディア転送のフォールバックパス UDP 通信を確立できない場合は、存続可能 Branch Appliance または存続可能 Branch Server、TCP はファイル転送およびデスクトップ共有に使用されます。</span><span class="sxs-lookup"><span data-stu-id="b035e-190">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b035e-191">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="b035e-191">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="b035e-192">任意</span><span class="sxs-lookup"><span data-stu-id="b035e-192">Any</span></span></p></td>
<td><p><span data-ttu-id="b035e-193">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b035e-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b035e-194">Lync Server 管理シェルと集中ログサービスコマンドレットを使用した集中ログサービスコントローラー、ClsController コマンドライン (ClsController.exe) またはエージェント (ClsAgent.exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="b035e-194">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b035e-195">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="b035e-195">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="b035e-196">任意</span><span class="sxs-lookup"><span data-stu-id="b035e-196">Any</span></span></p></td>
<td><p><span data-ttu-id="b035e-197">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b035e-197">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b035e-198">Lync Server 管理シェルと集中ログサービスコマンドレットを使用した集中ログサービスコントローラー、ClsController コマンドライン (ClsController.exe) またはエージェント (ClsAgent.exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="b035e-198">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b035e-199">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="b035e-199">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="b035e-200">任意</span><span class="sxs-lookup"><span data-stu-id="b035e-200">Any</span></span></p></td>
<td><p><span data-ttu-id="b035e-201">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b035e-201">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b035e-202">Lync Server 管理シェルと集中ログサービスコマンドレットを使用した集中ログサービスコントローラー、ClsController コマンドライン (ClsController.exe) またはエージェント (ClsAgent.exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="b035e-202">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b035e-203">ハードウェアロードバランサーを展開する場合は、Lync Server の可用性と負荷分散を実現するための特定の要件があります。</span><span class="sxs-lookup"><span data-stu-id="b035e-203">Hardware load balancers have specific requirements when deployed to provide availability and load balancing for Lync Server.</span></span> <span data-ttu-id="b035e-204">要件は、次の図と表で定義されています。</span><span class="sxs-lookup"><span data-stu-id="b035e-204">The requirements are defined in the following figure and tables.</span></span> <span data-ttu-id="b035e-205">サードパーティベンダーは、ここで定義されている要件に関して異なる用語を使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="b035e-205">Third party vendors may use different terminology for the requirements defined here.</span></span> <span data-ttu-id="b035e-206">Lync Server の要件を、ロードバランサー機器ベンダーが提供する機能および構成オプションにマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b035e-206">It will be necessary to map the requirements of Lync Server to the features and configuration options provided by your hardware load balancer vendor.</span></span>

<span data-ttu-id="b035e-207">ロードバランサー機器を構成する場合は、次の要件を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="b035e-207">When configuring hardware load balancers, consider the following requirements:</span></span>

  - <span data-ttu-id="b035e-208">ソースネットワークアドレス変換 (SNAT) は、アクセスエッジサービスと Web 会議エッジサービスのハードウェアロードバランサー (HLB) で構成できます。</span><span class="sxs-lookup"><span data-stu-id="b035e-208">Source Network Address Translation (SNAT) can be configured on the hardware load balancer (HLB) for Access Edge service and Web Conferencing Edge service</span></span>

  - <span data-ttu-id="b035e-209">音声ビデオエッジサービスで SNAT を構成することはできません。音声ビデオエッジサービスは、UDP over NAT (STUN) を使用した実際のサーバーアドレスではなく、(仮想 IP) を使用して応答する必要があります。これは、リレー NAT (TURN) と federation TURN (FTURN) を使用して正しく動作します。</span><span class="sxs-lookup"><span data-stu-id="b035e-209">SNAT cannot be configured on the A/V Edge service– the A/V Edge service must respond with the real server address, not the HLB virtual IP (VIP), for simple traversal of UDP over NAT (STUN)/traversal using relay NAT (TURN)/federation TURN (FTURN) to work properly</span></span>
    
      - <span data-ttu-id="b035e-210">クライアントが HLB に要求を送信する場合、応答は HLB VIP から返される必要があります。</span><span class="sxs-lookup"><span data-stu-id="b035e-210">If the client sends a request to the HLB, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="b035e-211">クライアントがエッジに要求を送信する場合、応答はエッジ IP から返される必要があります。</span><span class="sxs-lookup"><span data-stu-id="b035e-211">If the client sends a request to the Edge, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="b035e-212">パブリック IP アドレスは、各サーバーインターフェイスおよび HLB の Vip で使用され、パブリック ip アドレスの要件は、各 real サーバーインターフェイスにパブリック IP アドレスがあり、各 HLB VIP に対して1つずつ使用される N + 1 です。</span><span class="sxs-lookup"><span data-stu-id="b035e-212">Public IP addresses are used on each server interface and on the VIPs of the HLB, and your public IP address requirements are N+1, where there is a public IP address for each real server interface and one for each HLB VIP.</span></span> <span data-ttu-id="b035e-213">プールに2台のエッジサーバーがある場合、この値は9個のパブリック IP アドレスになります。ここでは、HLB Vip に3を使用し、各エッジサーバーインターフェイス (サーバーの合計 6) に対して1つを使用します。</span><span class="sxs-lookup"><span data-stu-id="b035e-213">Where you have 2 Edge servers in the pool, this results in 9 public IP addresses, where 3 are used for the HLB VIPs, and one for each Edge server interface (a total of six for the servers)</span></span>

  - <span data-ttu-id="b035e-214">アクセスエッジサービスと Web 会議エッジサービス (および HLB で NAT を使用して) は、クライアントが VIP に接続するため、VIP はクライアントの送信元 IP アドレスを自身の IP アドレスに変更します。</span><span class="sxs-lookup"><span data-stu-id="b035e-214">For the Access Edge service and Web Conferencing Edge service, (and using NAT on the HLB) the client contacts the VIP, the VIP changes the source IP address from the client to its own IP address.</span></span> <span data-ttu-id="b035e-215">サーバーインターフェイスは、VIP への復帰アドレスに対応します。 VIP は、サーバーインターフェイスの IP アドレスから送信元のアドレスを変更して、クライアントにパケットを送信します。</span><span class="sxs-lookup"><span data-stu-id="b035e-215">The server interface addresses the return address to the VIP, the VIP changes the source address from the server interface IP address and sends the packet to the client</span></span>

  - <span data-ttu-id="b035e-216">音声ビデオエッジサービスでは、VIP がソース IP アドレスを変更しないで、実際のサーバーアドレスが直接クライアントに返されるので、AV トラフィック用に HLB で NAT を構成することはできません</span><span class="sxs-lookup"><span data-stu-id="b035e-216">For the A/V Edge service, the VIP must NOT change the source IP address, and the real server address is returned to the client directly – you cannot configure NAT on the HLB for AV traffic</span></span>
    
      - <span data-ttu-id="b035e-217">クライアントが HLB VIP に要求を送信する場合、応答は HLB VIP から返される必要があります。</span><span class="sxs-lookup"><span data-stu-id="b035e-217">If the client sends a request to the HLB VIP, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="b035e-218">クライアントがエッジ IP に要求を送信する場合、応答はエッジ IP から返される必要があります。</span><span class="sxs-lookup"><span data-stu-id="b035e-218">If the client sends a request to the Edge IP, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="b035e-219">AV の場合、外部ファイアウォールはすべてのパケットに対して実際のサーバーのパブリック IP アドレスを保持します。</span><span class="sxs-lookup"><span data-stu-id="b035e-219">For AV, the external firewall will retain the real server public IP address for all packets</span></span>

  - <span data-ttu-id="b035e-220">確立されると、HLB ではなく、クライアントから音声ビデオエッジサービスの通信が実際のサーバーに対して行われます。</span><span class="sxs-lookup"><span data-stu-id="b035e-220">Once established, client to A/V Edge service communication is to the real server, not the HLB</span></span>

  - <span data-ttu-id="b035e-221">内部エッジから内部サーバーとクライアントをルーティングする必要があり、サーバーまたはクライアントをホストするすべての内部ネットワークに対して固定ルートが設定されている。</span><span class="sxs-lookup"><span data-stu-id="b035e-221">Internal edge to internal servers and clients must be routed, and persistent routes are set for all internal networks that host servers or clients</span></span>

  - <span data-ttu-id="b035e-222">HLB アクセスエッジサービス VIP は、各エッジサーバーインターフェイスの既定のゲートウェイとして機能します。</span><span class="sxs-lookup"><span data-stu-id="b035e-222">The HLB Access Edge service VIP will act as the default gateway for each Edge server interface</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="b035e-223">NAT の計画および機能の詳細については、「 <A href="lync-server-2013-hardware-load-balancer-requirements.md">Lync Server 2013 のハードウェアロードバランサーの要件</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b035e-223">For further information on NAT planning and functionality, please refer to <A href="lync-server-2013-hardware-load-balancer-requirements.md">Hardware load balancer requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="b035e-224">![エッジサーバーのポートとプロトコルの詳細](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "エッジサーバーのポートとプロトコルの詳細")</span><span class="sxs-lookup"><span data-stu-id="b035e-224">![Edge Server ports and protocols details](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Edge Server ports and protocols details")</span></span>

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a><span data-ttu-id="b035e-225">拡張統合エッジに必要な外部ポートの設定: ハードウェア負荷分散: 外部インターフェイスの仮想 Ip</span><span class="sxs-lookup"><span data-stu-id="b035e-225">External Port Settings Required for Scaled Consolidated Edge, Hardware Load Balanced: External Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b035e-226">役割/プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="b035e-226">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b035e-227">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b035e-227">Source IP address</span></span></th>
<th><span data-ttu-id="b035e-228">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b035e-228">Destination IP address</span></span></th>
<th><span data-ttu-id="b035e-229">Notes</span><span class="sxs-lookup"><span data-stu-id="b035e-229">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b035e-230">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="b035e-230">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="b035e-231">任意</span><span class="sxs-lookup"><span data-stu-id="b035e-231">Any</span></span></p></td>
<td><p><span data-ttu-id="b035e-232">XMPP プロキシサービス (アクセスエッジサービスを使用して IP アドレスを共有)</span><span class="sxs-lookup"><span data-stu-id="b035e-232">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="b035e-233">XMPP プロキシ サービスは、定義された XMPP フェデレーションの XMPP コンタクトからトラフィックを受け付けます</span><span class="sxs-lookup"><span data-stu-id="b035e-233">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b035e-234">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="b035e-234">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="b035e-235">XMPP プロキシサービス (アクセスエッジサービスを使用して IP アドレスを共有)</span><span class="sxs-lookup"><span data-stu-id="b035e-235">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="b035e-236">任意</span><span class="sxs-lookup"><span data-stu-id="b035e-236">Any</span></span></p></td>
<td><p><span data-ttu-id="b035e-237">XMPP プロキシサービスは、定義された XMPP フェデレーションの XMPP 連絡先にトラフィックを送信します。</span><span class="sxs-lookup"><span data-stu-id="b035e-237">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b035e-238">アクセス/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b035e-238">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b035e-239">任意</span><span class="sxs-lookup"><span data-stu-id="b035e-239">Any</span></span></p></td>
<td><p><span data-ttu-id="b035e-240">アクセスエッジサービスのパブリック VIP アドレス</span><span class="sxs-lookup"><span data-stu-id="b035e-240">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="b035e-241">外部ユーザー アクセス用のクライアントからサーバーへの SIP トラフィック</span><span class="sxs-lookup"><span data-stu-id="b035e-241">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b035e-242">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b035e-242">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b035e-243">任意</span><span class="sxs-lookup"><span data-stu-id="b035e-243">Any</span></span></p></td>
<td><p><span data-ttu-id="b035e-244">アクセスエッジサービスのパブリック VIP アドレス</span><span class="sxs-lookup"><span data-stu-id="b035e-244">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="b035e-245">Sip を使用した SIP 信号、フェデレーション、パブリック IM 接続</span><span class="sxs-lookup"><span data-stu-id="b035e-245">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b035e-246">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b035e-246">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b035e-247">アクセスエッジサービスのパブリック VIP アドレス</span><span class="sxs-lookup"><span data-stu-id="b035e-247">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="b035e-248">フェデレーションパートナー</span><span class="sxs-lookup"><span data-stu-id="b035e-248">Federated partner</span></span></p></td>
<td><p><span data-ttu-id="b035e-249">Sip を使用した SIP 信号、フェデレーション、パブリック IM 接続</span><span class="sxs-lookup"><span data-stu-id="b035e-249">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b035e-250">Web 会議/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b035e-250">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b035e-251">任意</span><span class="sxs-lookup"><span data-stu-id="b035e-251">Any</span></span></p></td>
<td><p><span data-ttu-id="b035e-252">エッジサーバー Web 会議エッジサービスのパブリック VIP アドレス</span><span class="sxs-lookup"><span data-stu-id="b035e-252">Edge Server Web Conferencing Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="b035e-253">Web 会議メディア</span><span class="sxs-lookup"><span data-stu-id="b035e-253">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b035e-254">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b035e-254">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b035e-255">任意</span><span class="sxs-lookup"><span data-stu-id="b035e-255">Any</span></span></p></td>
<td><p><span data-ttu-id="b035e-256">エッジサーバーの音声ビデオエッジサービスのパブリック VIP アドレス</span><span class="sxs-lookup"><span data-stu-id="b035e-256">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="b035e-257">STUN/UDP による候補の TURN ネゴシエーション/3478</span><span class="sxs-lookup"><span data-stu-id="b035e-257">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b035e-258">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b035e-258">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b035e-259">任意</span><span class="sxs-lookup"><span data-stu-id="b035e-259">Any</span></span></p></td>
<td><p><span data-ttu-id="b035e-260">エッジサーバーの音声ビデオエッジサービスのパブリック VIP アドレス</span><span class="sxs-lookup"><span data-stu-id="b035e-260">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="b035e-261">STUN/TCP による候補の TURN ネゴシエーション/443</span><span class="sxs-lookup"><span data-stu-id="b035e-261">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a><span data-ttu-id="b035e-262">拡張統合エッジのファイアウォールの概要ハードウェア負荷分散: 内部インターフェイスの仮想 Ip</span><span class="sxs-lookup"><span data-stu-id="b035e-262">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b035e-263">役割/プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="b035e-263">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b035e-264">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b035e-264">Source IP address</span></span></th>
<th><span data-ttu-id="b035e-265">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b035e-265">Destination IP address</span></span></th>
<th><span data-ttu-id="b035e-266">Notes</span><span class="sxs-lookup"><span data-stu-id="b035e-266">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b035e-267">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b035e-267">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b035e-268">任意 (ディレクター、ディレクタープールの仮想 IP アドレス、フロントエンドサーバー、またはフロントエンドプールの仮想 IP アドレスとして定義可能)</span><span class="sxs-lookup"><span data-stu-id="b035e-268">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="b035e-269">エッジサーバーの内部 VIP インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b035e-269">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="b035e-270">送信 SIP トラフィック (ディレクター、ディレクタープールの仮想 IP アドレス、フロントエンドサーバーまたはフロントエンドプールの仮想 IP アドレス) から内部エッジ VIP へ</span><span class="sxs-lookup"><span data-stu-id="b035e-270">Outbound SIP traffic (from Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)to Internal Edge VIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b035e-271">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b035e-271">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b035e-272">エッジサーバーの内部 VIP インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b035e-272">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="b035e-273">任意 (ディレクター、ディレクタープールの仮想 IP アドレス、フロントエンドサーバー、またはフロントエンドプールの仮想 IP アドレスとして定義可能)</span><span class="sxs-lookup"><span data-stu-id="b035e-273">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="b035e-274">エッジサーバーの内部インターフェイスからの受信 SIP トラフィック (ディレクター、ディレクタープールの仮想 IP アドレス、フロントエンドサーバー、またはフロントエンドプールの仮想 IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="b035e-274">Inbound SIP traffic (to Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b035e-275">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="b035e-275">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="b035e-276">Any (このエッジサーバーを使用するフロントエンドサーバーの IP アドレスまたはフロントエンドプールの IP アドレス、または存続可能 Branch Appliance または存続可能ブランチサーバーとして定義できます)</span><span class="sxs-lookup"><span data-stu-id="b035e-276">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="b035e-277">エッジサーバーの内部 VIP インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b035e-277">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="b035e-278">このエッジサーバーを使用するフロントエンドサーバーまたはフロントエンドプールの IP アドレスまたは任意の存続可能 Branch Appliance または存続可能ブランチサーバーからの音声ビデオユーザーの認証 (音声ビデオ認証サービス)</span><span class="sxs-lookup"><span data-stu-id="b035e-278">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b035e-279">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b035e-279">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b035e-280">任意</span><span class="sxs-lookup"><span data-stu-id="b035e-280">Any</span></span></p></td>
<td><p><span data-ttu-id="b035e-281">エッジサーバーの内部 VIP インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b035e-281">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="b035e-282">内部ユーザーと外部ユーザーとの間の音声ビデオ メディア転送の優先パス</span><span class="sxs-lookup"><span data-stu-id="b035e-282">Preferred path for A/V media transfer between internal and external users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b035e-283">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b035e-283">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b035e-284">任意</span><span class="sxs-lookup"><span data-stu-id="b035e-284">Any</span></span></p></td>
<td><p><span data-ttu-id="b035e-285">エッジサーバーの内部 VIP インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b035e-285">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="b035e-286">UDP 通信を確立できない場合の内部ユーザーと外部ユーザーとの間の音声ビデオ メディア転送のフォールバック パス、TCP はファイル転送およびデスクトップ共有に使用</span><span class="sxs-lookup"><span data-stu-id="b035e-286">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b035e-287">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b035e-287">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b035e-288">エッジサーバーの内部 VIP インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b035e-288">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="b035e-289">任意</span><span class="sxs-lookup"><span data-stu-id="b035e-289">Any</span></span></p></td>
<td><p><span data-ttu-id="b035e-290">UDP 通信を確立できない場合の内部ユーザーと外部ユーザーとの間の音声ビデオ メディア転送のフォールバック パス、TCP はファイル転送およびデスクトップ共有に使用</span><span class="sxs-lookup"><span data-stu-id="b035e-290">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

