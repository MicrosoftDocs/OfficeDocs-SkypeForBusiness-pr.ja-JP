---
title: ポートの概要 - 拡張統合エッジ (ロード バランサー機器を使用)
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
ms.openlocfilehash: 6260a4ad7f2717e0b4eb2446fc5b17671c3e45a5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725037"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="4ebd8-102">ポートの概要 - Lync Server 2013 の拡張統合エッジ (ロード バランサー機器を使用)</span><span class="sxs-lookup"><span data-stu-id="4ebd8-102">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ebd8-103">_**最終更新日:** 2015-04-27_</span><span class="sxs-lookup"><span data-stu-id="4ebd8-103">_**Topic Last Modified:** 2015-04-27_</span></span>

<span data-ttu-id="4ebd8-104">このシナリオアーキテクチャで説明されている Lync Server 2013 のエッジサーバー機能は、Lync Server 2010 で実装されたものとよく似ています。</span><span class="sxs-lookup"><span data-stu-id="4ebd8-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="4ebd8-105">最も顕著な追加機能は、拡張メッセージングとプレゼンスプロトコル (XMPP) の TCP エントリのポート**5269**です。</span><span class="sxs-lookup"><span data-stu-id="4ebd8-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="4ebd8-106">Lync Server 2013 では、必要に応じて、microsoft Edge サーバーまたはエッジプールに XMPP プロキシを展開し、フロントエンドサーバーまたはフロントエンドプールに XMPP ゲートウェイサーバーを配置します。</span><span class="sxs-lookup"><span data-stu-id="4ebd8-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="4ebd8-107">IPv4 に加えて、エッジサーバーは IPv6 をサポートするようになりました。</span><span class="sxs-lookup"><span data-stu-id="4ebd8-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="4ebd8-108">わかりやすくするために、シナリオでは IPv4 のみが使用されます。</span><span class="sxs-lookup"><span data-stu-id="4ebd8-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="4ebd8-109">**ハードウェア負荷分散を使用した拡大縮小エッジ**</span><span class="sxs-lookup"><span data-stu-id="4ebd8-109">**Scaled Consolidated Edge using Hardware Load Balancing**</span></span>

<span data-ttu-id="4ebd8-110">![エッジ サーバー境界ネットワークのポートおよびプロトコル](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "エッジ サーバー境界ネットワークのポートおよびプロトコル")</span><span class="sxs-lookup"><span data-stu-id="4ebd8-110">![Edge Server Perimeter Network ports and protocols](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Edge Server Perimeter Network ports and protocols")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="4ebd8-111">ポートとプロトコルの詳細</span><span class="sxs-lookup"><span data-stu-id="4ebd8-111">Port and Protocol Details</span></span>

<span data-ttu-id="4ebd8-112">外部アクセスを提供する機能をサポートするために必要なポートのみを開くことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4ebd8-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="4ebd8-113">エッジサービスに対してリモートアクセスを使用するには、受信/送信エッジトラフィックの図に示すように、SIP トラフィックが双方向に流れるようにすることが必須です。</span><span class="sxs-lookup"><span data-stu-id="4ebd8-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="4ebd8-114">別の方法として、アクセスエッジサービスとの間の SIP メッセージングは、インスタントメッセージング (IM)、プレゼンス、web 会議、音声/ビデオ (A/V)、およびフェデレーションに関連しています。</span><span class="sxs-lookup"><span data-stu-id="4ebd8-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="4ebd8-115">スケーリングされた統合エッジのファイアウォールの概要: ハードウェア負荷分散: ノード1とノード 2 (例)</span><span class="sxs-lookup"><span data-stu-id="4ebd8-115">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4ebd8-116">Role/Protocol/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="4ebd8-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="4ebd8-117">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-117">Source IP address</span></span></th>
<th><span data-ttu-id="4ebd8-118">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-118">Destination IP address</span></span></th>
<th><span data-ttu-id="4ebd8-119">メモ</span><span class="sxs-lookup"><span data-stu-id="4ebd8-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4ebd8-120">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="4ebd8-120">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-121">エッジサーバーアクセスエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-121">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-122">任意</span><span class="sxs-lookup"><span data-stu-id="4ebd8-122">Any</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-123">証明書の失効/CRL の確認と取得</span><span class="sxs-lookup"><span data-stu-id="4ebd8-123">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ebd8-124">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="4ebd8-124">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-125">エッジサーバーアクセスエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-125">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-126">任意</span><span class="sxs-lookup"><span data-stu-id="4ebd8-126">Any</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-127">TCP 経由の DNS クエリ</span><span class="sxs-lookup"><span data-stu-id="4ebd8-127">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ebd8-128">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="4ebd8-128">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-129">エッジサーバーアクセスエッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-129">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-130">任意</span><span class="sxs-lookup"><span data-stu-id="4ebd8-130">Any</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-131">UDP 経由の DNS クエリ</span><span class="sxs-lookup"><span data-stu-id="4ebd8-131">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ebd8-132">A/V/RTP/59,999</span><span class="sxs-lookup"><span data-stu-id="4ebd8-132">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-133">エッジサーバー A/V Edge サービス IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-133">Edge Server A/V Edge service IP address</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-134">任意</span><span class="sxs-lookup"><span data-stu-id="4ebd8-134">Any</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-135">Office Communications Server 2007、Office Communications Server 2007 R2、Lync Server 2010、および Lync Server 2013 を実行しているパートナーとのフェデレーションに必要。</span><span class="sxs-lookup"><span data-stu-id="4ebd8-135">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ebd8-136">A/V/RTP/59,999</span><span class="sxs-lookup"><span data-stu-id="4ebd8-136">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-137">エッジサーバーの A/V エッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-137">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-138">任意</span><span class="sxs-lookup"><span data-stu-id="4ebd8-138">Any</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-139">Office Communications Server 2007 を実行しているパートナーとのフェデレーションの場合のみ必須です。</span><span class="sxs-lookup"><span data-stu-id="4ebd8-139">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ebd8-140">A/V/RTP/59,999</span><span class="sxs-lookup"><span data-stu-id="4ebd8-140">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-141">任意</span><span class="sxs-lookup"><span data-stu-id="4ebd8-141">Any</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-142">エッジサーバーの A/V エッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-142">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-143">Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必須</span><span class="sxs-lookup"><span data-stu-id="4ebd8-143">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ebd8-144">A/V/RTP/59,999</span><span class="sxs-lookup"><span data-stu-id="4ebd8-144">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-145">任意</span><span class="sxs-lookup"><span data-stu-id="4ebd8-145">Any</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-146">エッジサーバーの A/V エッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-146">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-147">Office Communications Server 2007 を実行しているパートナーとのフェデレーションにのみ必須</span><span class="sxs-lookup"><span data-stu-id="4ebd8-147">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ebd8-148">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="4ebd8-148">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-149">エッジサーバーの A/V エッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-149">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-150">任意</span><span class="sxs-lookup"><span data-stu-id="4ebd8-150">Any</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-151">3478送信は、Lync Server が通信するエッジサーバーのバージョンと、エッジサーバーからエッジサーバーへのメディアトラフィックも確認するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="4ebd8-151">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="4ebd8-152">Lync Server 2010、Windows Live Messenger、Office Communications Server 2007 R2 とのフェデレーション、および複数のエッジプールが会社内に展開されている場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="4ebd8-152">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ebd8-153">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="4ebd8-153">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-154">任意</span><span class="sxs-lookup"><span data-stu-id="4ebd8-154">Any</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-155">エッジサーバーの A/V エッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-155">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-156">UDP/3478 経由の候補のネゴシエーションをオフ/オンにする</span><span class="sxs-lookup"><span data-stu-id="4ebd8-156">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ebd8-157">A/V/STUN、MSTURN/443</span><span class="sxs-lookup"><span data-stu-id="4ebd8-157">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-158">任意</span><span class="sxs-lookup"><span data-stu-id="4ebd8-158">Any</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-159">エッジサーバーの A/V エッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-159">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-160">TCP/443 経由での候補のネゴシエーションをオフ/オンにする</span><span class="sxs-lookup"><span data-stu-id="4ebd8-160">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ebd8-161">A/V/STUN、MSTURN/443</span><span class="sxs-lookup"><span data-stu-id="4ebd8-161">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-162">エッジサーバーの A/V エッジサービスのパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-162">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-163">任意</span><span class="sxs-lookup"><span data-stu-id="4ebd8-163">Any</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-164">TCP/443 経由での候補のネゴシエーションをオフ/オンにする</span><span class="sxs-lookup"><span data-stu-id="4ebd8-164">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a><span data-ttu-id="4ebd8-165">スケーリングされた統合エッジのファイアウォールの概要、ハードウェア負荷分散: 内部インターフェイスノード1とノード2</span><span class="sxs-lookup"><span data-stu-id="4ebd8-165">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Node 1 and Node 2</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4ebd8-166">Role/Protocol/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="4ebd8-166">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="4ebd8-167">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-167">Source IP address</span></span></th>
<th><span data-ttu-id="4ebd8-168">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-168">Destination IP address</span></span></th>
<th><span data-ttu-id="4ebd8-169">メモ</span><span class="sxs-lookup"><span data-stu-id="4ebd8-169">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4ebd8-170">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="4ebd8-170">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-171">Any (フロントエンドサーバーアドレスとして定義可能、または XMPP ゲートウェイサービスを実行するフロントエンドプール仮想 IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="4ebd8-171">Any (can be defined as Front End Server address, or Front End pool virtual IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-172">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-172">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-173">フロントエンドサーバーまたはフロントエンドプールで実行されている XMPP ゲートウェイサービスからの送信 XMPP トラフィック</span><span class="sxs-lookup"><span data-stu-id="4ebd8-173">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ebd8-174">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="4ebd8-174">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-175">Any (任意) (中央管理ストアを保持するフロントエンドサーバーサーバーの IP またはプールとして定義できます)</span><span class="sxs-lookup"><span data-stu-id="4ebd8-175">Any (can be defined as the Front End Server server IP or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-176">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-176">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-177">中央管理ストアからエッジサーバーへの変更のレプリケーション</span><span class="sxs-lookup"><span data-stu-id="4ebd8-177">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ebd8-178">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="4ebd8-178">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-179">Any (ディレクター IP、フロントエンドサーバー IP またはプール仮想 IP として定義可能)</span><span class="sxs-lookup"><span data-stu-id="4ebd8-179">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-180">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-180">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-181">内部展開から内部のエッジサーバーインターフェイスへの Web 会議トラフィック</span><span class="sxs-lookup"><span data-stu-id="4ebd8-181">Web conferencing traffic from Internal deployment to Internal Edge Server interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ebd8-182">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="4ebd8-182">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-183">Any (ディレクター IP、フロントエンドサーバー IP またはプール仮想 IP として定義可能)</span><span class="sxs-lookup"><span data-stu-id="4ebd8-183">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-184">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-184">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-185">内部と外部のユーザー、Survivable Branch Appliance または Survivable ブランチサーバー間の A/V メディア転送の優先パス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-185">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ebd8-186">STUN/MSTURN/443</span><span class="sxs-lookup"><span data-stu-id="4ebd8-186">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-187">Any (ディレクター IP、フロントエンドサーバー IP またはプール仮想 IP として定義可能)</span><span class="sxs-lookup"><span data-stu-id="4ebd8-187">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-188">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-188">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-189">内部と外部のユーザーとの間でのメディア転送のフォールバックパス Survivable Branch Appliance または Survivable Branch Server (UDP 通信が確立できない場合は、TCP を使ってファイル転送とデスクトップ共有を行う)</span><span class="sxs-lookup"><span data-stu-id="4ebd8-189">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ebd8-190">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="4ebd8-190">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-191">任意</span><span class="sxs-lookup"><span data-stu-id="4ebd8-191">Any</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-192">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-193">Lync Server 管理シェルと一元ログサービスコマンドレットを使用した一元管理サービスコントローラー、ClsController コマンドライン (ClsController) またはエージェント (Clscontroller .exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="4ebd8-193">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ebd8-194">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="4ebd8-194">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-195">任意</span><span class="sxs-lookup"><span data-stu-id="4ebd8-195">Any</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-196">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-197">Lync Server 管理シェルと一元ログサービスコマンドレットを使用した一元管理サービスコントローラー、ClsController コマンドライン (ClsController) またはエージェント (Clscontroller .exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="4ebd8-197">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ebd8-198">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="4ebd8-198">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-199">任意</span><span class="sxs-lookup"><span data-stu-id="4ebd8-199">Any</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-200">エッジサーバーの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-201">Lync Server 管理シェルと一元ログサービスコマンドレットを使用した一元管理サービスコントローラー、ClsController コマンドライン (ClsController) またはエージェント (Clscontroller .exe) コマンドとログ収集</span><span class="sxs-lookup"><span data-stu-id="4ebd8-201">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4ebd8-202">ハードウェアロードバランサーを展開するときに、Lync Server の可用性と負荷分散を提供するための特定の要件があります。</span><span class="sxs-lookup"><span data-stu-id="4ebd8-202">Hardware load balancers have specific requirements when deployed to provide availability and load balancing for Lync Server.</span></span> <span data-ttu-id="4ebd8-203">要件は、次の図と表で定義されています。</span><span class="sxs-lookup"><span data-stu-id="4ebd8-203">The requirements are defined in the following figure and tables.</span></span> <span data-ttu-id="4ebd8-204">サードパーティベンダーは、ここで定義されている要件について別の用語を使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="4ebd8-204">Third party vendors may use different terminology for the requirements defined here.</span></span> <span data-ttu-id="4ebd8-205">Lync Server の要件を、ハードウェアロードバランサーのベンダーから提供されている機能と構成オプションにマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ebd8-205">It will be necessary to map the requirements of Lync Server to the features and configuration options provided by your hardware load balancer vendor.</span></span>

<span data-ttu-id="4ebd8-206">ハードウェアロードバランサーを構成する場合は、次の要件を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="4ebd8-206">When configuring hardware load balancers, consider the following requirements:</span></span>

  - <span data-ttu-id="4ebd8-207">ソースネットワークアドレス変換 (SNAT) を、Access Edge サービスおよび Web 会議エッジサービスのハードウェアロードバランサー (HLB) で構成することができます。</span><span class="sxs-lookup"><span data-stu-id="4ebd8-207">Source Network Address Translation (SNAT) can be configured on the hardware load balancer (HLB) for Access Edge service and Web Conferencing Edge service</span></span>

  - <span data-ttu-id="4ebd8-208">SNAT を A/V Edge サービスで構成することはできません。 A/V Edge サービスは、UDP 経由の単純なトラバーサル (STUN)、または relay NAT (TURN) を使用したトラバーサル (FTURN) で正常に動作するように、実際のサーバーアドレスに応答する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ebd8-208">SNAT cannot be configured on the A/V Edge service– the A/V Edge service must respond with the real server address, not the HLB virtual IP (VIP), for simple traversal of UDP over NAT (STUN)/traversal using relay NAT (TURN)/federation TURN (FTURN) to work properly</span></span>
    
      - <span data-ttu-id="4ebd8-209">クライアントが HLB に要求を送信した場合、応答は HLB VIP から返される必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ebd8-209">If the client sends a request to the HLB, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="4ebd8-210">クライアントが要求をエッジに送信した場合、応答はエッジ IP から返される必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ebd8-210">If the client sends a request to the Edge, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="4ebd8-211">パブリック IP アドレスは、各サーバーインターフェイスと HLB の Vip で使用され、パブリック ip アドレスの要件は、それぞれの実際のサーバーインターフェイスのパブリック IP アドレスと、各 HLB VIP 用に1つずつ使用されます。</span><span class="sxs-lookup"><span data-stu-id="4ebd8-211">Public IP addresses are used on each server interface and on the VIPs of the HLB, and your public IP address requirements are N+1, where there is a public IP address for each real server interface and one for each HLB VIP.</span></span> <span data-ttu-id="4ebd8-212">プール内に2台のエッジサーバーがある場合、この結果、3つのパブリック IP アドレスが作成されます。ここでは、3は HLB Vip として、3は各エッジサーバーインターフェイスに対して使います (サーバーの場合は合計 6)。</span><span class="sxs-lookup"><span data-stu-id="4ebd8-212">Where you have 2 Edge servers in the pool, this results in 9 public IP addresses, where 3 are used for the HLB VIPs, and one for each Edge server interface (a total of six for the servers)</span></span>

  - <span data-ttu-id="4ebd8-213">クライアントは、アクセスエッジサービスおよび Web 会議エッジサービス (および HLB で NAT を使う) について、VIP に接続して、クライアントのソース IP アドレスをクライアントの IP アドレスに変更します。</span><span class="sxs-lookup"><span data-stu-id="4ebd8-213">For the Access Edge service and Web Conferencing Edge service, (and using NAT on the HLB) the client contacts the VIP, the VIP changes the source IP address from the client to its own IP address.</span></span> <span data-ttu-id="4ebd8-214">サーバーインターフェイスは、VIP に対して差出人住所を解決し、VIP によってサーバーインターフェイスの IP アドレスからソースアドレスが変更され、パケットがクライアントに送信されます。</span><span class="sxs-lookup"><span data-stu-id="4ebd8-214">The server interface addresses the return address to the VIP, the VIP changes the source address from the server interface IP address and sends the packet to the client</span></span>

  - <span data-ttu-id="4ebd8-215">A/V Edge サービスの場合、VIP はソースの IP アドレスを変更してはなりません。実際のサーバーのアドレスはクライアントに直接返され、AV トラフィック用に HLB で NAT を構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="4ebd8-215">For the A/V Edge service, the VIP must NOT change the source IP address, and the real server address is returned to the client directly – you cannot configure NAT on the HLB for AV traffic</span></span>
    
      - <span data-ttu-id="4ebd8-216">クライアントが HLB VIP に要求を送信した場合、応答は HLB VIP から返される必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ebd8-216">If the client sends a request to the HLB VIP, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="4ebd8-217">クライアントが要求をエッジ IP に送信した場合、応答はエッジ IP から返される必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ebd8-217">If the client sends a request to the Edge IP, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="4ebd8-218">AV の場合、外部ファイアウォールは、すべてのパケットに対して実際のサーバーのパブリック IP アドレスを保持します。</span><span class="sxs-lookup"><span data-stu-id="4ebd8-218">For AV, the external firewall will retain the real server public IP address for all packets</span></span>

  - <span data-ttu-id="4ebd8-219">確立されたクライアントから A/V Edge サービス通信は、HLB ではなく、実際のサーバーに対して行われます。</span><span class="sxs-lookup"><span data-stu-id="4ebd8-219">Once established, client to A/V Edge service communication is to the real server, not the HLB</span></span>

  - <span data-ttu-id="4ebd8-220">内部サーバーとクライアント間の内部境界はルーティングされる必要があり、サーバーまたはクライアントをホストするすべての内部ネットワークに対して固定ルートが設定されます。</span><span class="sxs-lookup"><span data-stu-id="4ebd8-220">Internal edge to internal servers and clients must be routed, and persistent routes are set for all internal networks that host servers or clients</span></span>

  - <span data-ttu-id="4ebd8-221">HLB Access Edge service VIP は、各エッジサーバーインターフェイスの既定のゲートウェイとして機能します。</span><span class="sxs-lookup"><span data-stu-id="4ebd8-221">The HLB Access Edge service VIP will act as the default gateway for each Edge server interface</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="4ebd8-222">NAT の計画と機能の詳細については、「 <A href="lync-server-2013-hardware-load-balancer-requirements.md">Lync Server 2013 のハードウェアロードバランサーの要件</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ebd8-222">For further information on NAT planning and functionality, please refer to <A href="lync-server-2013-hardware-load-balancer-requirements.md">Hardware load balancer requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="4ebd8-223">![エッジ サーバーのポートおよびプロトコルの詳細](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "エッジ サーバーのポートおよびプロトコルの詳細")</span><span class="sxs-lookup"><span data-stu-id="4ebd8-223">![Edge Server ports and protocols details](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Edge Server ports and protocols details")</span></span>

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a><span data-ttu-id="4ebd8-224">スケーリングされた統合エッジに必要な外部ポート設定、ハードウェア負荷分散: 外部インターフェイス仮想 Ip</span><span class="sxs-lookup"><span data-stu-id="4ebd8-224">External Port Settings Required for Scaled Consolidated Edge, Hardware Load Balanced: External Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4ebd8-225">Role/Protocol/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="4ebd8-225">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="4ebd8-226">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-226">Source IP address</span></span></th>
<th><span data-ttu-id="4ebd8-227">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-227">Destination IP address</span></span></th>
<th><span data-ttu-id="4ebd8-228">メモ</span><span class="sxs-lookup"><span data-stu-id="4ebd8-228">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4ebd8-229">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="4ebd8-229">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-230">任意</span><span class="sxs-lookup"><span data-stu-id="4ebd8-230">Any</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-231">XMPP プロキシサービス (アクセスエッジサービスで IP アドレスを共有)</span><span class="sxs-lookup"><span data-stu-id="4ebd8-231">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-232">XMPP プロキシサービスは、定義された XMPP フェデレーションの XMPP 連絡先からのトラフィックを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="4ebd8-232">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ebd8-233">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="4ebd8-233">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-234">XMPP プロキシサービス (アクセスエッジサービスで IP アドレスを共有)</span><span class="sxs-lookup"><span data-stu-id="4ebd8-234">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-235">任意</span><span class="sxs-lookup"><span data-stu-id="4ebd8-235">Any</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-236">XMPP プロキシサービスは、定義された XMPP フェデレーションの XMPP の連絡先にトラフィックを送信します。</span><span class="sxs-lookup"><span data-stu-id="4ebd8-236">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ebd8-237">アクセス/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="4ebd8-237">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-238">任意</span><span class="sxs-lookup"><span data-stu-id="4ebd8-238">Any</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-239">アクセスエッジサービスのパブリック VIP アドレス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-239">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-240">外部ユーザーアクセスのクライアントツーサーバー SIP トラフィック</span><span class="sxs-lookup"><span data-stu-id="4ebd8-240">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ebd8-241">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="4ebd8-241">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-242">任意</span><span class="sxs-lookup"><span data-stu-id="4ebd8-242">Any</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-243">アクセスエッジサービスのパブリック VIP アドレス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-243">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-244">Sip を使用した SIP シグナリング、フェデレーションおよびパブリック IM 接続</span><span class="sxs-lookup"><span data-stu-id="4ebd8-244">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ebd8-245">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="4ebd8-245">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-246">アクセスエッジサービスのパブリック VIP アドレス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-246">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-247">フェデレーションパートナー</span><span class="sxs-lookup"><span data-stu-id="4ebd8-247">Federated partner</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-248">Sip を使用した SIP シグナリング、フェデレーションおよびパブリック IM 接続</span><span class="sxs-lookup"><span data-stu-id="4ebd8-248">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ebd8-249">Web 会議/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="4ebd8-249">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-250">任意</span><span class="sxs-lookup"><span data-stu-id="4ebd8-250">Any</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-251">エッジサーバー Web 会議エッジサービスのパブリック VIP アドレス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-251">Edge Server Web Conferencing Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-252">Web 会議メディア</span><span class="sxs-lookup"><span data-stu-id="4ebd8-252">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ebd8-253">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="4ebd8-253">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-254">任意</span><span class="sxs-lookup"><span data-stu-id="4ebd8-254">Any</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-255">エッジサーバーの A/V エッジサービスのパブリック VIP アドレス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-255">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-256">UDP/3478 経由の候補のネゴシエーションをオフ/オンにする</span><span class="sxs-lookup"><span data-stu-id="4ebd8-256">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ebd8-257">A/V/STUN、MSTURN/443</span><span class="sxs-lookup"><span data-stu-id="4ebd8-257">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-258">任意</span><span class="sxs-lookup"><span data-stu-id="4ebd8-258">Any</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-259">エッジサーバーの A/V エッジサービスのパブリック VIP アドレス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-259">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-260">TCP/443 経由での候補のネゴシエーションをオフ/オンにする</span><span class="sxs-lookup"><span data-stu-id="4ebd8-260">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a><span data-ttu-id="4ebd8-261">スケーリングされた統合エッジのファイアウォールの概要: ハードウェア負荷分散: 内部インターフェイス仮想 Ip</span><span class="sxs-lookup"><span data-stu-id="4ebd8-261">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4ebd8-262">Role/Protocol/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="4ebd8-262">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="4ebd8-263">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-263">Source IP address</span></span></th>
<th><span data-ttu-id="4ebd8-264">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-264">Destination IP address</span></span></th>
<th><span data-ttu-id="4ebd8-265">メモ</span><span class="sxs-lookup"><span data-stu-id="4ebd8-265">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4ebd8-266">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="4ebd8-266">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-267">Any (ディレクター、ディレクタープールの仮想 IP アドレス、フロントエンドサーバー、またはフロントエンドプールの仮想 IP アドレスとして定義できます)</span><span class="sxs-lookup"><span data-stu-id="4ebd8-267">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-268">エッジサーバーの内部 VIP インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-268">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-269">送信 SIP トラフィック (ディレクター、ディレクタープールの仮想 IP アドレス、フロントエンドサーバーまたはフロントエンドプールの仮想 IP アドレス) から内部エッジ VIP へ</span><span class="sxs-lookup"><span data-stu-id="4ebd8-269">Outbound SIP traffic (from Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)to Internal Edge VIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ebd8-270">アクセス/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="4ebd8-270">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-271">エッジサーバーの内部 VIP インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-271">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-272">Any (ディレクター、ディレクタープールの仮想 IP アドレス、フロントエンドサーバー、またはフロントエンドプールの仮想 IP アドレスとして定義できます)</span><span class="sxs-lookup"><span data-stu-id="4ebd8-272">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-273">エッジサーバーの内部インターフェイスから受信 SIP トラフィック (ディレクター、ディレクタープールの仮想 IP アドレス、フロントエンドサーバー、またはフロントエンドプールの仮想 IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="4ebd8-273">Inbound SIP traffic (to Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ebd8-274">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="4ebd8-274">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-275">Any (フロントエンドサーバーの IP アドレス、またはこのエッジサーバーを使用している Survivable Branch Appliance または Survivable ブランチサーバー) として定義することができます。</span><span class="sxs-lookup"><span data-stu-id="4ebd8-275">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-276">エッジサーバーの内部 VIP インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-276">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-277">このエッジサーバーを使用して、フロントエンドサーバーまたはフロントエンドプールの IP アドレスまたは Survivable Branch Appliance または Survivable ブランチサーバーからの、A/V ユーザー (A/V 認証サービス) の認証</span><span class="sxs-lookup"><span data-stu-id="4ebd8-277">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ebd8-278">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="4ebd8-278">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-279">任意</span><span class="sxs-lookup"><span data-stu-id="4ebd8-279">Any</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-280">エッジサーバーの内部 VIP インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-280">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-281">内部と外部のユーザー間の A/V メディア転送の優先パス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-281">Preferred path for A/V media transfer between internal and external users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ebd8-282">STUN/MSTURN/443</span><span class="sxs-lookup"><span data-stu-id="4ebd8-282">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-283">任意</span><span class="sxs-lookup"><span data-stu-id="4ebd8-283">Any</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-284">エッジサーバーの内部 VIP インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-284">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-285">内部と外部のユーザーとの間でのメディア転送のフォールバックパス UDP 通信を確立できない場合、TCP がファイル転送とデスクトップ共有に使用されます。</span><span class="sxs-lookup"><span data-stu-id="4ebd8-285">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ebd8-286">STUN/MSTURN/443</span><span class="sxs-lookup"><span data-stu-id="4ebd8-286">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-287">エッジサーバーの内部 VIP インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4ebd8-287">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-288">任意</span><span class="sxs-lookup"><span data-stu-id="4ebd8-288">Any</span></span></p></td>
<td><p><span data-ttu-id="4ebd8-289">内部と外部のユーザーとの間でのメディア転送のフォールバックパス UDP 通信を確立できない場合、TCP がファイル転送とデスクトップ共有に使用されます。</span><span class="sxs-lookup"><span data-stu-id="4ebd8-289">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

