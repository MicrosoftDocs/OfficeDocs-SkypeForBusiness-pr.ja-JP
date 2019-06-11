---
title: 'Lync Server 2013: トポロジの選択'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Choosing a topology
ms:assetid: 23f2aeb6-fed9-4349-8fba-dcbf18ee4b04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425716(v=OCS.15)
ms:contentKeyID: 48183634
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3aa98d479ca2bfeaf6214bbd1e66bb3f41b09782
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840579"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="choosing-a-topology-in-lync-server-2013"></a><span data-ttu-id="82260-102">Lync Server 2013 でのトポロジの選択</span><span class="sxs-lookup"><span data-stu-id="82260-102">Choosing a topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span data-ttu-id="82260-103">_**最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="82260-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="82260-104">トポロジを選択する場合は、次のサポートされているトポロジオプションのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="82260-104">When you choose a topology, you can use one the following supported topology options:</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="82260-105">特に記載がない限り、Microsoft Lync Server 2010 を使用している場合は、次のガイダンスがほとんど変更されていないことがわかります。</span><span class="sxs-lookup"><span data-stu-id="82260-105">Unless otherwise noted, if you have experience with Microsoft Lync Server 2010, you will find the guidance here is largely unchanged.</span></span>



</div>

  - [<span data-ttu-id="82260-106">Lync Server 2013 におけるプライベート IP アドレスと NAT を用いた単一統合エッジ</span><span class="sxs-lookup"><span data-stu-id="82260-106">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [<span data-ttu-id="82260-107">Lync Server 2013 のパブリック IP アドレスを使用する単一統合エッジ</span><span class="sxs-lookup"><span data-stu-id="82260-107">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="82260-108">Lync Server 2013 における拡張統合エッジ、NAT によるプライベート IP アドレスを使用した DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="82260-108">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="82260-109">Lync Server 2013 での拡張統合エッジ、パブリック IP アドレスによる DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="82260-109">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="82260-110">Lync Server 2013 のハードウェア ロード バランサーによる拡張統合エッジ</span><span class="sxs-lookup"><span data-stu-id="82260-110">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]
> <span data-ttu-id="82260-111">内部エッジ インターフェイスと外部エッジ インターフェイスでは、同じ種類のロード バランシングを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82260-111">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="82260-112">1 つのエッジ インターフェイスで DNS ロード バランシングを使用し、もう 1 つのエッジ インターフェイスでロード バランサー機器を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="82260-112">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>



</div>

<span data-ttu-id="82260-113">次の表は、サポートされている Microsoft Lync Server 2013 トポロジで利用できる機能をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="82260-113">The following table summarizes the functionality available with the supported Microsoft Lync Server 2013 topologies.</span></span> <span data-ttu-id="82260-114">列見出しは、特定の Edge 構成オプションで使用できる機能を示します。</span><span class="sxs-lookup"><span data-stu-id="82260-114">The column headings indicate the functionality available for a given Edge configuration option.</span></span> <span data-ttu-id="82260-115">スケーリングされたエッジ (DNS load 均衡) オプションを使用すると、高可用性をサポートしていること、ルーティング可能ではないプライベート IP アドレス (NAT を含む)、またはエッジの外部インターフェイスに割り当てられているルーティング可能なパブリック IP アドレスを使用できることを確認できます。ハードウェアロードバランサーは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="82260-115">Using the Scaled Edge (DNS load balanced) option as an example, you can see that it supports high availability, can use non-routable private IP addresses (with NAT) or routable public IP addresses assigned to the Edge external interfaces, and reduces cost because a hardware load balancer is not required.</span></span>

<span data-ttu-id="82260-116">DNS の負荷分散でサポートされるエッジフェールオーバーのシナリオは、lync 間のポイントツーポイントセッション、Lync 会議セッション、Lync 間のセッション、および Office 365 です。</span><span class="sxs-lookup"><span data-stu-id="82260-116">Edge failover scenarios supported with DNS Load Balancing are Lync-to-Lync point-to-point sessions, Lync conferencing sessions, Lync-to-PSTN sessions and Office 365.</span></span> <span data-ttu-id="82260-117">DNS 負荷分散のメリットが得られないエッジフェールオーバーのシナリオは、リモートユーザーの Exchange ユニファイドメッセージング (UM 2010)、パブリックインスタントメッセージング (IM) 接続、Office 通信を実行しているサーバーとのフェデレーションなどに対応しています。Server.</span><span class="sxs-lookup"><span data-stu-id="82260-117">Edge failover scenarios that do not benefit from DNS Load Balancing are failover for remote user Exchange Unified Messaging (UM) (prior to Exchange 2010 SP1), public instant messaging (IM) connectivity, and federation with servers running Office Communications Server.</span></span>

### <a name="summary-of-edge-server-topology-options"></a><span data-ttu-id="82260-118">エッジサーバーのトポロジオプションの概要</span><span class="sxs-lookup"><span data-stu-id="82260-118">Summary of Edge Server Topology Options</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="82260-119">トポロジ</span><span class="sxs-lookup"><span data-stu-id="82260-119">Topology</span></span></th>
<th><span data-ttu-id="82260-120">高可用性</span><span class="sxs-lookup"><span data-stu-id="82260-120">High availability</span></span></th>
<th><span data-ttu-id="82260-121">追加 DNS A Edge プールの外部エッジサーバーに必要なレコード</span><span class="sxs-lookup"><span data-stu-id="82260-121">Additional DNS A records required for external Edge Server in the Edge pool</span></span></th>
<th><span data-ttu-id="82260-122">Lync to Lync セッションのエッジフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="82260-122">Edge Failover for Lync-to-Lync sessions</span></span></th>
<th><span data-ttu-id="82260-123">Lync 対 Lync EUM/PIC/OCS フェデレーションセッションのエッジフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="82260-123">Edge Failover for Lync-to-Lync EUM/PIC/OCS Federation sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="82260-124">NAT を使用する単一エッジ</span><span class="sxs-lookup"><span data-stu-id="82260-124">Single Edge using NAT</span></span></p></td>
<td><p><span data-ttu-id="82260-125">いいえ</span><span class="sxs-lookup"><span data-stu-id="82260-125">No</span></span></p></td>
<td><p><span data-ttu-id="82260-126">いいえ</span><span class="sxs-lookup"><span data-stu-id="82260-126">No</span></span></p></td>
<td><p><span data-ttu-id="82260-127">いいえ</span><span class="sxs-lookup"><span data-stu-id="82260-127">No</span></span></p></td>
<td><p><span data-ttu-id="82260-128">いいえ</span><span class="sxs-lookup"><span data-stu-id="82260-128">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82260-129">パブリック IP を使った単一エッジ</span><span class="sxs-lookup"><span data-stu-id="82260-129">Single Edge using Public IP</span></span></p></td>
<td><p><span data-ttu-id="82260-130">いいえ</span><span class="sxs-lookup"><span data-stu-id="82260-130">No</span></span></p></td>
<td><p><span data-ttu-id="82260-131">いいえ</span><span class="sxs-lookup"><span data-stu-id="82260-131">No</span></span></p></td>
<td><p><span data-ttu-id="82260-132">いいえ</span><span class="sxs-lookup"><span data-stu-id="82260-132">No</span></span></p></td>
<td><p><span data-ttu-id="82260-133">いいえ</span><span class="sxs-lookup"><span data-stu-id="82260-133">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82260-134">NAT を使用した拡張エッジ (DNS 負荷分散)</span><span class="sxs-lookup"><span data-stu-id="82260-134">Scaled Edge (DNS Load Balanced) using NAT</span></span></p></td>
<td><p><span data-ttu-id="82260-135">はい</span><span class="sxs-lookup"><span data-stu-id="82260-135">Yes</span></span></p></td>
<td><p><span data-ttu-id="82260-136">はい</span><span class="sxs-lookup"><span data-stu-id="82260-136">Yes</span></span></p></td>
<td><p><span data-ttu-id="82260-137">はい</span><span class="sxs-lookup"><span data-stu-id="82260-137">Yes</span></span></p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82260-138">パブリック IP を使った拡張エッジ (DNS 負荷分散)</span><span class="sxs-lookup"><span data-stu-id="82260-138">Scaled Edge (DNS Load Balanced) using Public IP</span></span></p></td>
<td><p><span data-ttu-id="82260-139">はい</span><span class="sxs-lookup"><span data-stu-id="82260-139">Yes</span></span></p></td>
<td><p><span data-ttu-id="82260-140">はい</span><span class="sxs-lookup"><span data-stu-id="82260-140">Yes</span></span></p></td>
<td><p><span data-ttu-id="82260-141">はい</span><span class="sxs-lookup"><span data-stu-id="82260-141">Yes</span></span></p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82260-142">スケーリングされたエッジハードウェアの負荷分散)</span><span class="sxs-lookup"><span data-stu-id="82260-142">Scaled Edge Hardware load balanced)</span></span></p></td>
<td><p><span data-ttu-id="82260-143">はい</span><span class="sxs-lookup"><span data-stu-id="82260-143">Yes</span></span></p></td>
<td><p><span data-ttu-id="82260-144">× (VIP ごとに 1 つの DNS A レコード)</span><span class="sxs-lookup"><span data-stu-id="82260-144">No (one DNS A record per VIP)</span></span></p></td>
<td><p><span data-ttu-id="82260-145">はい</span><span class="sxs-lookup"><span data-stu-id="82260-145">Yes</span></span></p></td>
<td><p><span data-ttu-id="82260-146">はい</span><span class="sxs-lookup"><span data-stu-id="82260-146">Yes</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="82260-147">**\*** パブリックインスタントメッセージング (IM) 接続のフェールオーバーと、Office Communications Server を実行しているサーバーとのフェデレーションは、DNS の負荷分散では利用できません。</span><span class="sxs-lookup"><span data-stu-id="82260-147">**\*** Failover for public instant messaging (IM) connectivity, and federation with servers running Office Communications Server is not available with DNS load balancing.</span></span> <span data-ttu-id="82260-148">DNS 負荷分散を使用した exchange UM (リモートユーザー) のフェールオーバーには、Exchange Server 2010 SP1 以上が必要です。</span><span class="sxs-lookup"><span data-stu-id="82260-148">Exchange UM (remote user) failover using DNS load balancing requires Exchange Server 2010 SP1 or newer.</span></span>



> [!NOTE]
> <span data-ttu-id="82260-149">単一のエッジとスケーリングされたエッジ (DNS 負荷分散) には、次のような用途があります。</span><span class="sxs-lookup"><span data-stu-id="82260-149">Single Edge and Scaled Edge (DNS load balanced) topologies can use:</span></span>
> <ul><li><p><span data-ttu-id="82260-150">ルーティング可能なパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="82260-150">Routable public IP addresses</span></span></p></li>
> <li><p><span data-ttu-id="82260-151">対称ネットワークアドレス変換 (NAT) が使用されている場合、ルーティング可能ではないプライベート IP アドレス</span><span class="sxs-lookup"><span data-stu-id="82260-151">Non-routable private IP address if symmetric network address translation (NAT) is used</span></span></p></li>
>
> <ul><li> <span data-ttu-id="82260-152">NAT でパブリック IP アドレスまたはプライベート IP アドレスを使用している場合でも、トポロジビルダーの構成の選択に基づいて、同じ数の IP アドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="82260-152">If you use public IP address or private IP address with NAT, you will still use the same number of IP addresses based on your configuration choice in Topology Builder.</span></span> <span data-ttu-id="82260-153">サービスごとに個別のポートを使用するようにエッジサーバーを構成することも、サービスごとに個別の IP アドレスを使用することもできますが、同じポート (既定では TCP 443) を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="82260-153">You can configure the Edge Server to use a single IP address with distinct ports per service, or use distinct IP addresses per service, but use the same port (by default, TCP 443).</span></span></li></ul>>
> <span data-ttu-id="82260-154">NAT でルーティング不能なプライベート IP アドレスを使用する場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="82260-154">If you decide to use non-routable private IP addresses with NAT:</span></span>
> <ul><li><p><span data-ttu-id="82260-155">ルーティング可能なプライベート IP アドレスは、すべての3つの外部インターフェイスで使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82260-155">You must use routable private IP addresses on all three external interfaces</span></span></p></li>
> <li><p><span data-ttu-id="82260-156">受信および送信トラフィック用に対称 NAT を構成する必要がある</span><span class="sxs-lookup"><span data-stu-id="82260-156">You must configure symmetric NAT for incoming and outgoing traffic</span></span></p></li></ul>>
> <span data-ttu-id="82260-157">スケーリングされたエッジ (ハードウェア負荷分散) トポロジでは、パブリック IP アドレスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82260-157">Scaled Edge (hardware load balanced) topology must use public IP addresses.</span></span>



<span data-ttu-id="82260-158">Lync Server 2013 は、ネットワークアドレス変換 (NAT) を実行するルーターまたはファイアウォールの背後にあるアクセス、Web 会議、および A/V Edge の外部インターフェイスの配置をサポートしています。統合されたエッジサーバートポロジの1つとスケーリングの両方に対応しています。</span><span class="sxs-lookup"><span data-stu-id="82260-158">Lync Server 2013 supports placing Access, Web Conferencing, and A/V Edge external interfaces behind a router or firewall that performs network address translation (NAT) for both single and scaled consolidated Edge Server topologies.</span></span>

<span data-ttu-id="82260-159">すべてのエッジに NAT を使用するには、DNS の負荷分散を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82260-159">Using NAT for all Edge external interfaces requires the use of DNS load balancing.</span></span> <span data-ttu-id="82260-160">ハードウェアロードバランサーの使用と比較した場合、DNS の負荷分散を使用すると、次の一覧に示すように、エッジプールでエッジサーバーあたりのパブリック IP アドレスの数を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="82260-160">When compared to using hardware load balancers, using DNS load balancing without NAT allows you to reduce the number of public IP address per Edge Server in an Edge pool as described in the following list:</span></span>

  - <span data-ttu-id="82260-161">Lync Server 2013 の統合エッジ (DNS 負荷分散) には、Edge プールのエッジサーバーごとに3つのパブリック IP アドレスが必要です。</span><span class="sxs-lookup"><span data-stu-id="82260-161">Lync Server 2013 Scaled Consolidated Edge (DNS load balanced) Requires three public IP addresses for each Edge Server in an Edge pool.</span></span>

  - <span data-ttu-id="82260-162">Lync Server 2013 の統合されたエッジ (ハードウェア負荷分散) には、ロードバランサーの仮想 IP アドレスに対して3つのパブリック IP アドレスが必要です (プールに追加されたエッジサーバーが増加しないため1回限りの場合)。プール内のエッジサーバー。</span><span class="sxs-lookup"><span data-stu-id="82260-162">Lync Server 2013 Scaled Consolidated Edge (hardware load balanced) Requires three public IP address for load balancer virtual IP addresses (one time requirement that does not increment as more Edge Servers are added to the pool) plus three public IP addresses per Edge Server in a pool.</span></span>

### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a><span data-ttu-id="82260-163">スケーリングされた統合エッジの IP アドレス要件 (役割ごとの IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="82260-163">IP Address Requirements for Scaled Consolidated Edge (IP Address per role)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="82260-164">1つのプールあたりのエッジサーバーの数</span><span class="sxs-lookup"><span data-stu-id="82260-164">Number of Edge Servers per pool</span></span></th>
<th><span data-ttu-id="82260-165">必要な IP アドレスの数 Lync Server 2013 (DNS 負荷分散)</span><span class="sxs-lookup"><span data-stu-id="82260-165">Number of required IP addresses Lync Server 2013 (DNS load balanced)</span></span></th>
<th><span data-ttu-id="82260-166">必要な IP アドレスの数 Lync Server 2013 (ハードウェアの負荷分散)</span><span class="sxs-lookup"><span data-stu-id="82260-166">Number of required IP addresses Lync Server 2013 (hardware load balanced)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="82260-167">2</span><span class="sxs-lookup"><span data-stu-id="82260-167">2</span></span></p></td>
<td><p><span data-ttu-id="82260-168">6</span><span class="sxs-lookup"><span data-stu-id="82260-168">6</span></span></p></td>
<td><p><span data-ttu-id="82260-169">3 (VIP ごとに 1 つ) + 6</span><span class="sxs-lookup"><span data-stu-id="82260-169">3 (1 per VIP) + 6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82260-170">3</span><span class="sxs-lookup"><span data-stu-id="82260-170">3</span></span></p></td>
<td><p><span data-ttu-id="82260-171">ファイブ</span><span class="sxs-lookup"><span data-stu-id="82260-171">9</span></span></p></td>
<td><p><span data-ttu-id="82260-172">3 (VIP ごとに 1 つ) + 9</span><span class="sxs-lookup"><span data-stu-id="82260-172">3 (1 per VIP) + 9</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82260-173">4</span><span class="sxs-lookup"><span data-stu-id="82260-173">4</span></span></p></td>
<td><p><span data-ttu-id="82260-174">以内</span><span class="sxs-lookup"><span data-stu-id="82260-174">12</span></span></p></td>
<td><p><span data-ttu-id="82260-175">3 (VIP ごとに 1 つ) + 12</span><span class="sxs-lookup"><span data-stu-id="82260-175">3 (1 per VIP) + 12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82260-176">5</span><span class="sxs-lookup"><span data-stu-id="82260-176">5</span></span></p></td>
<td><p><span data-ttu-id="82260-177">マート</span><span class="sxs-lookup"><span data-stu-id="82260-177">15</span></span></p></td>
<td><p><span data-ttu-id="82260-178">3 (VIP あたり 1) + 15</span><span class="sxs-lookup"><span data-stu-id="82260-178">3 (1 per VIP) + 15</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="ip-address-requirements-for-scaled-consolidated-edge-single-ip-address-for-all-roles"></a><span data-ttu-id="82260-179">スケーリングされた統合エッジの IP アドレス要件 (すべての役割の単一 IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="82260-179">IP Address Requirements for Scaled Consolidated Edge (Single IP address for all roles)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="82260-180">1つのプールあたりのエッジサーバーの数</span><span class="sxs-lookup"><span data-stu-id="82260-180">Number of Edge Servers per pool</span></span></th>
<th><span data-ttu-id="82260-181">必要な IP アドレスの数 Lync Server 2013 (DNS 負荷分散)</span><span class="sxs-lookup"><span data-stu-id="82260-181">Number of required IP addresses Lync Server 2013 (DNS load balanced)</span></span></th>
<th><span data-ttu-id="82260-182">必要な IP アドレスの数 Lync Server 2013 (ハードウェアの負荷分散)</span><span class="sxs-lookup"><span data-stu-id="82260-182">Number of required IP addresses Lync Server 2013 (hardware load balanced)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="82260-183">2</span><span class="sxs-lookup"><span data-stu-id="82260-183">2</span></span></p></td>
<td><p><span data-ttu-id="82260-184">2</span><span class="sxs-lookup"><span data-stu-id="82260-184">2</span></span></p></td>
<td><p><span data-ttu-id="82260-185">1 (VIP ごとに 1 つ) + 2</span><span class="sxs-lookup"><span data-stu-id="82260-185">1 (1 per VIP) + 2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82260-186">3</span><span class="sxs-lookup"><span data-stu-id="82260-186">3</span></span></p></td>
<td><p><span data-ttu-id="82260-187">3</span><span class="sxs-lookup"><span data-stu-id="82260-187">3</span></span></p></td>
<td><p><span data-ttu-id="82260-188">1 (VIP ごとに 1 つ) + 3</span><span class="sxs-lookup"><span data-stu-id="82260-188">1 (1 per VIP) + 3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82260-189">4</span><span class="sxs-lookup"><span data-stu-id="82260-189">4</span></span></p></td>
<td><p><span data-ttu-id="82260-190">4</span><span class="sxs-lookup"><span data-stu-id="82260-190">4</span></span></p></td>
<td><p><span data-ttu-id="82260-191">1 (VIP ごとに 1 つ) + 4</span><span class="sxs-lookup"><span data-stu-id="82260-191">1 (1 per VIP) + 4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82260-192">5</span><span class="sxs-lookup"><span data-stu-id="82260-192">5</span></span></p></td>
<td><p><span data-ttu-id="82260-193">5</span><span class="sxs-lookup"><span data-stu-id="82260-193">5</span></span></p></td>
<td><p><span data-ttu-id="82260-194">1 (VIP ごとに 1 つ) + 5</span><span class="sxs-lookup"><span data-stu-id="82260-194">1 (1 per VIP) + 5</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="82260-195">トポロジ選択の主要な決定ポイントは、高可用性と負荷分散です。</span><span class="sxs-lookup"><span data-stu-id="82260-195">The primary decision points for topology selection are high availability and load balancing.</span></span> <span data-ttu-id="82260-196">高可用性の要件は、負荷分散の決定に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="82260-196">The requirement for high availability can influence the load balancing decision.</span></span>

  - <span data-ttu-id="82260-197">**高可用性**  高可用性が必要な場合は、少なくとも2つのエッジサーバーをプールに展開します。</span><span class="sxs-lookup"><span data-stu-id="82260-197">**High availability**   If you need high availability, deploy at least two Edge Servers in a pool.</span></span> <span data-ttu-id="82260-198">1つのエッジプールは、最大12台のエッジサーバーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="82260-198">A single Edge pool will support up to twelve Edge Servers.</span></span> <span data-ttu-id="82260-199">さらに多くの容量が必要な場合は、複数のエッジプールを展開できます。</span><span class="sxs-lookup"><span data-stu-id="82260-199">If more capacity is required, you can deploy multiple Edge pools.</span></span> <span data-ttu-id="82260-200">一般的な規則として、特定のユーザーベースの 10% には外部アクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="82260-200">As a general rule, 10% of a given user base will need external access.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="82260-201">トポロジビルダーを使用すると、1つのエッジプールで最大20台のエッジサーバーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="82260-201">Topology Builder will allow you to configure up to twenty Edge Servers in a single Edge pool.</span></span> <span data-ttu-id="82260-202">プール内のエッジサーバーのうち、テストおよびサポートされている最大数は12個とトポロジービルダーで、1つのエッジプールで12台以上のエッジサーバーに対して暗示的なサポートを行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="82260-202">The tested and supported maximum number of Edge Servers in a pool is twelve and Topology Builder allowing for a number larger than twelve should not be construed as implied support for more than twelve Edge Servers in a single Edge pool.</span></span>

    
    </div>

  - <span data-ttu-id="82260-203">**ハードウェア負荷分散**  エッジ外部インターフェイスに対してパブリックルーティング可能な IP アドレスを使用している場合、ハードウェア負荷分散がサポートさ2013れます。</span><span class="sxs-lookup"><span data-stu-id="82260-203">**Hardware load balancing**   Hardware load balancing is supported for load balancing Lync Server 2013 Edge Servers when using publicly routable IP addresses for the Edge external interfaces.</span></span> <span data-ttu-id="82260-204">たとえば、次のいずれかのアプリケーションでフェールオーバーが必要な場合に、この方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="82260-204">For example, you would use this approach in situations where failover is required for any of the following applications:</span></span>
    
      - <span data-ttu-id="82260-205">パブリック IM 接続</span><span class="sxs-lookup"><span data-stu-id="82260-205">Public IM connectivity</span></span>
    
      - <span data-ttu-id="82260-206">Microsoft Office Communications Server 2007 または Microsoft Office Communications Server 2007 R2 を実行している企業とのフェデレーション</span><span class="sxs-lookup"><span data-stu-id="82260-206">Federation with companies running Microsoft Office Communications Server 2007 or Microsoft Office Communications Server 2007 R2</span></span>
    
      - <span data-ttu-id="82260-207">Exchange 2007 ユニファイドメッセージング (UM) または Exchange 2010 UM への外部アクセス</span><span class="sxs-lookup"><span data-stu-id="82260-207">External access to Exchange 2007 Unified Messaging (UM) or Exchange 2010 UM</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="82260-208">Exchange 2010 SP1 以降の DNS の負荷分散は、Exchange UM でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="82260-208">DNS load balancing for Exchange 2010 SP1 and newer is supported for Exchange UM.</span></span>

        
        </div>
    
    <span data-ttu-id="82260-209">これら3つのアプリケーションは引き続き動作しますが、DNS の負荷分散に対応しておらず、プールの最初のエッジサーバーにのみ接続されます。</span><span class="sxs-lookup"><span data-stu-id="82260-209">These three applications will continue to operate, but they are not DNS load balancing aware and will only connect to the first Edge Server in the pool.</span></span> <span data-ttu-id="82260-210">そのサーバーが利用できない場合、接続は失敗します。</span><span class="sxs-lookup"><span data-stu-id="82260-210">If that server is unavailable, the connection will fail.</span></span> <span data-ttu-id="82260-211">たとえば、フェデレーションされたトラフィックの負荷を処理するために複数のエッジサーバーがプールに展開されている場合、他のユーザーがアイドル状態になっている間、実際にトラフィックを受信するのは1つのアクセスプロキシだけです。</span><span class="sxs-lookup"><span data-stu-id="82260-211">For example, if multiple Edge Servers are deployed in a pool to handle the federated traffic load, only one access proxy actually receives traffic while the others are idle.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="82260-212">Lync Server 2010 および Microsoft Office 365 を使用して会社とフェデレーションする場合は、DNS の負荷分散を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="82260-212">Using DNS load balancing is recommended if you are federating with companies using Lync Server 2010 and Microsoft Office 365.</span></span> <span data-ttu-id="82260-213">フェデレーションパートナーの大半が Office Communications Server 2007 または Office Communications Server 2007 R2 を使用している場合、パフォーマンスへの影響が大きくなることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="82260-213">Be aware that there are significant performance impacts if most of your federated partners are using Office Communications Server 2007 or Office Communications Server 2007 R2.</span></span>



<span data-ttu-id="82260-214"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="82260-214"></span></span></div>

