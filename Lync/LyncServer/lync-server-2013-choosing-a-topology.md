---
title: 'Lync Server 2013: トポロジの選択'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Choosing a topology
ms:assetid: 23f2aeb6-fed9-4349-8fba-dcbf18ee4b04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425716(v=OCS.15)
ms:contentKeyID: 48183634
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3a77a37cb9f9c4f92f344988082086834ab3489
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046530"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="choosing-a-topology-in-lync-server-2013"></a><span data-ttu-id="b0a87-102">Lync Server 2013 でのトポロジの選択</span><span class="sxs-lookup"><span data-stu-id="b0a87-102">Choosing a topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span data-ttu-id="b0a87-103">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="b0a87-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="b0a87-104">トポロジの選択では、次に示すサポートされるトポロジ オプションのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b0a87-104">When you choose a topology, you can use one the following supported topology options:</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="b0a87-105">特に明記されていない限り、Microsoft Lync Server 2010 を使用している場合は、ここに示すガイダンスがほぼ変更されていないことがわかります。</span><span class="sxs-lookup"><span data-stu-id="b0a87-105">Unless otherwise noted, if you have experience with Microsoft Lync Server 2010, you will find the guidance here is largely unchanged.</span></span>



</div>

  - [<span data-ttu-id="b0a87-106">Lync Server 2013 でのプライベート IP アドレスと NAT を使用する単一統合エッジ</span><span class="sxs-lookup"><span data-stu-id="b0a87-106">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [<span data-ttu-id="b0a87-107">Lync Server 2013 でのパブリック IP アドレスを使用する単一統合エッジ</span><span class="sxs-lookup"><span data-stu-id="b0a87-107">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="b0a87-108">Lync Server 2013 での拡張統合エッジ、NAT を使用したプライベート IP アドレスを使用した DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="b0a87-108">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="b0a87-109">Lync Server 2013 の拡張統合エッジ、パブリック IP アドレスによる DNS 負荷分散</span><span class="sxs-lookup"><span data-stu-id="b0a87-109">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="b0a87-110">Lync Server 2013 での拡張統合エッジとロードバランサー機器</span><span class="sxs-lookup"><span data-stu-id="b0a87-110">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]
> <span data-ttu-id="b0a87-p101">内部エッジ インターフェイスと外部エッジ インターフェイスでは、同じ種類のロード バランシングを使用する必要があります。1 つのエッジ インターフェイスで DNS ロード バランシングを使用し、もう 1 つのエッジ インターフェイスでロード バランサー機器を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="b0a87-p101">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>



</div>

<span data-ttu-id="b0a87-113">次の表に、サポートされている Microsoft Lync Server 2013 トポロジで使用可能な機能を示します。</span><span class="sxs-lookup"><span data-stu-id="b0a87-113">The following table summarizes the functionality available with the supported Microsoft Lync Server 2013 topologies.</span></span> <span data-ttu-id="b0a87-114">列見出しは、該当するエッジ構成オプションで使用できる機能を示しています。</span><span class="sxs-lookup"><span data-stu-id="b0a87-114">The column headings indicate the functionality available for a given Edge configuration option.</span></span> <span data-ttu-id="b0a87-115">たとえば、拡張エッジ (DNS 負荷分散) オプションでは、高可用性がサポートされること、エッジの外部インターフェイスに割り当てられたルーティング不可のプライベート IP アドレス (NAT を使用) またはルーティング可能なパブリック IP アドレスを使用できること、およびロード バランサー機器が必要ないのでコストが削減されることがわかります。</span><span class="sxs-lookup"><span data-stu-id="b0a87-115">Using the Scaled Edge (DNS load balanced) option as an example, you can see that it supports high availability, can use non-routable private IP addresses (with NAT) or routable public IP addresses assigned to the Edge external interfaces, and reduces cost because a hardware load balancer is not required.</span></span>

<span data-ttu-id="b0a87-116">DNS 負荷分散でサポートされているエッジフェールオーバーシナリオには、Lync から Lync へのポイントツーポイントセッション、Lync 会議セッション、Lync から PSTN へのセッション、および Office 365 があります。</span><span class="sxs-lookup"><span data-stu-id="b0a87-116">Edge failover scenarios supported with DNS Load Balancing are Lync-to-Lync point-to-point sessions, Lync conferencing sessions, Lync-to-PSTN sessions and Office 365.</span></span> <span data-ttu-id="b0a87-117">DNS 負荷分散のメリットを得られないエッジフェールオーバーのシナリオは、リモートユーザー Exchange ユニファイドメッセージング (UM) (Exchange 2010 SP1 以前)、パブリックインスタントメッセージング (IM) 接続、および Office Communications を実行しているサーバーとのフェデレーションのためのフェールオーバーです。Server.</span><span class="sxs-lookup"><span data-stu-id="b0a87-117">Edge failover scenarios that do not benefit from DNS Load Balancing are failover for remote user Exchange Unified Messaging (UM) (prior to Exchange 2010 SP1), public instant messaging (IM) connectivity, and federation with servers running Office Communications Server.</span></span>

### <a name="summary-of-edge-server-topology-options"></a><span data-ttu-id="b0a87-118">エッジ サーバー トポロジ オプションの概要</span><span class="sxs-lookup"><span data-stu-id="b0a87-118">Summary of Edge Server Topology Options</span></span>

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
<th><span data-ttu-id="b0a87-119">トポロジ</span><span class="sxs-lookup"><span data-stu-id="b0a87-119">Topology</span></span></th>
<th><span data-ttu-id="b0a87-120">高可用性</span><span class="sxs-lookup"><span data-stu-id="b0a87-120">High availability</span></span></th>
<th><span data-ttu-id="b0a87-121">エッジ プールにある外部エッジ サーバーの追加 DNS A レコードの必要性</span><span class="sxs-lookup"><span data-stu-id="b0a87-121">Additional DNS A records required for external Edge Server in the Edge pool</span></span></th>
<th><span data-ttu-id="b0a87-122">Lync 対 Lync セッションのエッジフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="b0a87-122">Edge Failover for Lync-to-Lync sessions</span></span></th>
<th><span data-ttu-id="b0a87-123">Lync 対 Lync EUM/PIC/OCS フェデレーションセッションのエッジフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="b0a87-123">Edge Failover for Lync-to-Lync EUM/PIC/OCS Federation sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b0a87-124">NAT を使用する単一エッジ</span><span class="sxs-lookup"><span data-stu-id="b0a87-124">Single Edge using NAT</span></span></p></td>
<td><p><span data-ttu-id="b0a87-125">いいえ</span><span class="sxs-lookup"><span data-stu-id="b0a87-125">No</span></span></p></td>
<td><p><span data-ttu-id="b0a87-126">いいえ</span><span class="sxs-lookup"><span data-stu-id="b0a87-126">No</span></span></p></td>
<td><p><span data-ttu-id="b0a87-127">いいえ</span><span class="sxs-lookup"><span data-stu-id="b0a87-127">No</span></span></p></td>
<td><p><span data-ttu-id="b0a87-128">いいえ</span><span class="sxs-lookup"><span data-stu-id="b0a87-128">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0a87-129">パブリック IP を使用する単一エッジ</span><span class="sxs-lookup"><span data-stu-id="b0a87-129">Single Edge using Public IP</span></span></p></td>
<td><p><span data-ttu-id="b0a87-130">いいえ</span><span class="sxs-lookup"><span data-stu-id="b0a87-130">No</span></span></p></td>
<td><p><span data-ttu-id="b0a87-131">いいえ</span><span class="sxs-lookup"><span data-stu-id="b0a87-131">No</span></span></p></td>
<td><p><span data-ttu-id="b0a87-132">いいえ</span><span class="sxs-lookup"><span data-stu-id="b0a87-132">No</span></span></p></td>
<td><p><span data-ttu-id="b0a87-133">いいえ</span><span class="sxs-lookup"><span data-stu-id="b0a87-133">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0a87-134">NAT を使用する拡張エッジ (DNS 負荷分散)</span><span class="sxs-lookup"><span data-stu-id="b0a87-134">Scaled Edge (DNS Load Balanced) using NAT</span></span></p></td>
<td><p><span data-ttu-id="b0a87-135">はい</span><span class="sxs-lookup"><span data-stu-id="b0a87-135">Yes</span></span></p></td>
<td><p><span data-ttu-id="b0a87-136">はい</span><span class="sxs-lookup"><span data-stu-id="b0a87-136">Yes</span></span></p></td>
<td><p><span data-ttu-id="b0a87-137">はい</span><span class="sxs-lookup"><span data-stu-id="b0a87-137">Yes</span></span></p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0a87-138">パブリック IP を使用する拡張エッジ (DNS 負荷分散)</span><span class="sxs-lookup"><span data-stu-id="b0a87-138">Scaled Edge (DNS Load Balanced) using Public IP</span></span></p></td>
<td><p><span data-ttu-id="b0a87-139">はい</span><span class="sxs-lookup"><span data-stu-id="b0a87-139">Yes</span></span></p></td>
<td><p><span data-ttu-id="b0a87-140">はい</span><span class="sxs-lookup"><span data-stu-id="b0a87-140">Yes</span></span></p></td>
<td><p><span data-ttu-id="b0a87-141">はい</span><span class="sxs-lookup"><span data-stu-id="b0a87-141">Yes</span></span></p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0a87-142">拡張エッジ (ハードウェア負荷分散)</span><span class="sxs-lookup"><span data-stu-id="b0a87-142">Scaled Edge Hardware load balanced)</span></span></p></td>
<td><p><span data-ttu-id="b0a87-143">はい</span><span class="sxs-lookup"><span data-stu-id="b0a87-143">Yes</span></span></p></td>
<td><p><span data-ttu-id="b0a87-144">いいえ (VIP ごとに 1 つの DNS A レコード)</span><span class="sxs-lookup"><span data-stu-id="b0a87-144">No (one DNS A record per VIP)</span></span></p></td>
<td><p><span data-ttu-id="b0a87-145">はい</span><span class="sxs-lookup"><span data-stu-id="b0a87-145">Yes</span></span></p></td>
<td><p><span data-ttu-id="b0a87-146">はい</span><span class="sxs-lookup"><span data-stu-id="b0a87-146">Yes</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b0a87-147">**\*** パブリックインスタントメッセージング (IM) 接続のフェールオーバー、および Office Communications Server を実行しているサーバーとのフェデレーションは、DNS 負荷分散では使用できません。</span><span class="sxs-lookup"><span data-stu-id="b0a87-147">**\*** Failover for public instant messaging (IM) connectivity, and federation with servers running Office Communications Server is not available with DNS load balancing.</span></span> <span data-ttu-id="b0a87-148">DNS 負荷分散を使用した exchange UM (リモートユーザー) のフェールオーバーには、Exchange Server 2010 SP1 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="b0a87-148">Exchange UM (remote user) failover using DNS load balancing requires Exchange Server 2010 SP1 or newer.</span></span>



> [!NOTE]
> <span data-ttu-id="b0a87-149">単一エッジおよび拡張エッジ (DNS 負荷分散) トポロジでは、次のアドレスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b0a87-149">Single Edge and Scaled Edge (DNS load balanced) topologies can use:</span></span>
> <ul><li><p><span data-ttu-id="b0a87-150">ルーティング可能なパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b0a87-150">Routable public IP addresses</span></span></p></li>
> <li><p><span data-ttu-id="b0a87-151">対称ネットワークアドレス変換 (NAT) を使用している場合は、ルーティング可能でないプライベート IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b0a87-151">Non-routable private IP address if symmetric network address translation (NAT) is used</span></span></p></li>
>
> <ul><li> <span data-ttu-id="b0a87-152">NAT でパブリック IP アドレスまたはプライベート IP アドレスを使用する場合でも、トポロジビルダーの構成選択に基づいて、同じ数の IP アドレスを使用することになります。</span><span class="sxs-lookup"><span data-stu-id="b0a87-152">If you use public IP address or private IP address with NAT, you will still use the same number of IP addresses based on your configuration choice in Topology Builder.</span></span> <span data-ttu-id="b0a87-153">サービスごとに個別のポートを持つ単一の IP アドレスを使用するようにエッジサーバーを構成することも、サービスごとに個別の IP アドレスを使用することもできますが、同じポート (既定では TCP 443) を使用します。</span><span class="sxs-lookup"><span data-stu-id="b0a87-153">You can configure the Edge Server to use a single IP address with distinct ports per service, or use distinct IP addresses per service, but use the same port (by default, TCP 443).</span></span></li></ul>>
> <span data-ttu-id="b0a87-154">NAT でルーティング不能なプライベート IP アドレスを使用する場合は、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="b0a87-154">If you decide to use non-routable private IP addresses with NAT:</span></span>
> <ul><li><p><span data-ttu-id="b0a87-155">3つすべての外部インターフェイスで、ルーティング可能なプライベート IP アドレスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0a87-155">You must use routable private IP addresses on all three external interfaces</span></span></p></li>
> <li><p><span data-ttu-id="b0a87-156">受信トラフィックと送信トラフィック用に対称 NAT を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0a87-156">You must configure symmetric NAT for incoming and outgoing traffic</span></span></p></li></ul>>
> <span data-ttu-id="b0a87-157">拡張エッジ (ハードウェア負荷分散) トポロジでは、パブリック IP アドレスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0a87-157">Scaled Edge (hardware load balanced) topology must use public IP addresses.</span></span>



<span data-ttu-id="b0a87-158">Lync Server 2013 では、単一および拡張統合エッジサーバートポロジの両方でネットワークアドレス変換 (NAT) を実行する、ルーターまたはファイアウォールの背後にあるアクセス、Web 会議、および音声ビデオエッジ外部インターフェイスの配置をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b0a87-158">Lync Server 2013 supports placing Access, Web Conferencing, and A/V Edge external interfaces behind a router or firewall that performs network address translation (NAT) for both single and scaled consolidated Edge Server topologies.</span></span>

<span data-ttu-id="b0a87-p106">すべてのエッジ外部インターフェイスで NAT を使用する場合は、DNS 負荷分散を使用する必要があります。ロード バランサー機器を使用する場合に比べて、NAT を使わずに DNS 負荷分散を使用すると、次の一覧に示すとおり、エッジ プール内のエッジ サーバーごとのパブリック IP アドレス数を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="b0a87-p106">Using NAT for all Edge external interfaces requires the use of DNS load balancing. When compared to using hardware load balancers, using DNS load balancing without NAT allows you to reduce the number of public IP address per Edge Server in an Edge pool as described in the following list:</span></span>

  - <span data-ttu-id="b0a87-161">Lync Server 2013 の拡張統合エッジ (DNS 負荷分散) には、エッジプールの各エッジサーバーに3つのパブリック IP アドレスが必要です。</span><span class="sxs-lookup"><span data-stu-id="b0a87-161">Lync Server 2013 Scaled Consolidated Edge (DNS load balanced) Requires three public IP addresses for each Edge Server in an Edge pool.</span></span>

  - <span data-ttu-id="b0a87-162">Lync Server 2013 の拡張統合エッジ (ハードウェア負荷分散) には、ロードバランサーの仮想 IP アドレスに3つのパブリック IP アドレスが必要です (プールに追加されたエッジサーバーの数が増えても1回の要件)、さらに3つのパブリック IP アドレスプール内のエッジサーバー。</span><span class="sxs-lookup"><span data-stu-id="b0a87-162">Lync Server 2013 Scaled Consolidated Edge (hardware load balanced) Requires three public IP address for load balancer virtual IP addresses (one time requirement that does not increment as more Edge Servers are added to the pool) plus three public IP addresses per Edge Server in a pool.</span></span>

### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a><span data-ttu-id="b0a87-163">拡張統合エッジに必要な IP アドレス (役割ごとの IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="b0a87-163">IP Address Requirements for Scaled Consolidated Edge (IP Address per role)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b0a87-164">プールごとのエッジ サーバー数</span><span class="sxs-lookup"><span data-stu-id="b0a87-164">Number of Edge Servers per pool</span></span></th>
<th><span data-ttu-id="b0a87-165">必要な IP アドレスの数 Lync Server 2013 (DNS 負荷分散)</span><span class="sxs-lookup"><span data-stu-id="b0a87-165">Number of required IP addresses Lync Server 2013 (DNS load balanced)</span></span></th>
<th><span data-ttu-id="b0a87-166">必要な IP アドレス数 Lync Server 2013 (ハードウェア負荷分散)</span><span class="sxs-lookup"><span data-stu-id="b0a87-166">Number of required IP addresses Lync Server 2013 (hardware load balanced)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b0a87-167">2 </span><span class="sxs-lookup"><span data-stu-id="b0a87-167">2</span></span></p></td>
<td><p><span data-ttu-id="b0a87-168">6 </span><span class="sxs-lookup"><span data-stu-id="b0a87-168">6</span></span></p></td>
<td><p><span data-ttu-id="b0a87-169">3 (VIP ごとに 1 つ) + 6</span><span class="sxs-lookup"><span data-stu-id="b0a87-169">3 (1 per VIP) + 6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0a87-170">3 </span><span class="sxs-lookup"><span data-stu-id="b0a87-170">3</span></span></p></td>
<td><p><span data-ttu-id="b0a87-171">9 </span><span class="sxs-lookup"><span data-stu-id="b0a87-171">9</span></span></p></td>
<td><p><span data-ttu-id="b0a87-172">3 (VIP ごとに 1 つ) + 9</span><span class="sxs-lookup"><span data-stu-id="b0a87-172">3 (1 per VIP) + 9</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0a87-173">4 </span><span class="sxs-lookup"><span data-stu-id="b0a87-173">4</span></span></p></td>
<td><p><span data-ttu-id="b0a87-174">12</span><span class="sxs-lookup"><span data-stu-id="b0a87-174">12</span></span></p></td>
<td><p><span data-ttu-id="b0a87-175">3 (VIP ごとに 1 つ) + 12</span><span class="sxs-lookup"><span data-stu-id="b0a87-175">3 (1 per VIP) + 12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0a87-176">5 </span><span class="sxs-lookup"><span data-stu-id="b0a87-176">5</span></span></p></td>
<td><p><span data-ttu-id="b0a87-177">15 </span><span class="sxs-lookup"><span data-stu-id="b0a87-177">15</span></span></p></td>
<td><p><span data-ttu-id="b0a87-178">3 (VIP ごとに 1 つ) + 15</span><span class="sxs-lookup"><span data-stu-id="b0a87-178">3 (1 per VIP) + 15</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="ip-address-requirements-for-scaled-consolidated-edge-single-ip-address-for-all-roles"></a><span data-ttu-id="b0a87-179">拡張統合エッジに必要な IP アドレス (すべての役割に対して 1 つの IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="b0a87-179">IP Address Requirements for Scaled Consolidated Edge (Single IP address for all roles)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b0a87-180">プールごとのエッジ サーバー数</span><span class="sxs-lookup"><span data-stu-id="b0a87-180">Number of Edge Servers per pool</span></span></th>
<th><span data-ttu-id="b0a87-181">必要な IP アドレスの数 Lync Server 2013 (DNS 負荷分散)</span><span class="sxs-lookup"><span data-stu-id="b0a87-181">Number of required IP addresses Lync Server 2013 (DNS load balanced)</span></span></th>
<th><span data-ttu-id="b0a87-182">必要な IP アドレス数 Lync Server 2013 (ハードウェア負荷分散)</span><span class="sxs-lookup"><span data-stu-id="b0a87-182">Number of required IP addresses Lync Server 2013 (hardware load balanced)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b0a87-183">2 </span><span class="sxs-lookup"><span data-stu-id="b0a87-183">2</span></span></p></td>
<td><p><span data-ttu-id="b0a87-184">2 </span><span class="sxs-lookup"><span data-stu-id="b0a87-184">2</span></span></p></td>
<td><p><span data-ttu-id="b0a87-185">1 (VIP ごとに 1 つ) + 2</span><span class="sxs-lookup"><span data-stu-id="b0a87-185">1 (1 per VIP) + 2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0a87-186">3 </span><span class="sxs-lookup"><span data-stu-id="b0a87-186">3</span></span></p></td>
<td><p><span data-ttu-id="b0a87-187">3 </span><span class="sxs-lookup"><span data-stu-id="b0a87-187">3</span></span></p></td>
<td><p><span data-ttu-id="b0a87-188">1 ( VIP ごとに 1 つ) + 3</span><span class="sxs-lookup"><span data-stu-id="b0a87-188">1 (1 per VIP) + 3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0a87-189">4 </span><span class="sxs-lookup"><span data-stu-id="b0a87-189">4</span></span></p></td>
<td><p><span data-ttu-id="b0a87-190">4 </span><span class="sxs-lookup"><span data-stu-id="b0a87-190">4</span></span></p></td>
<td><p><span data-ttu-id="b0a87-191">1 (VIP ごとに 1 つ) + 4</span><span class="sxs-lookup"><span data-stu-id="b0a87-191">1 (1 per VIP) + 4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0a87-192">5 </span><span class="sxs-lookup"><span data-stu-id="b0a87-192">5</span></span></p></td>
<td><p><span data-ttu-id="b0a87-193">5</span><span class="sxs-lookup"><span data-stu-id="b0a87-193">5</span></span></p></td>
<td><p><span data-ttu-id="b0a87-194">1 (VIP ごとに 1 つ) + 5</span><span class="sxs-lookup"><span data-stu-id="b0a87-194">1 (1 per VIP) + 5</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b0a87-p107">トポロジ選択を決定する上で最も優先されるポイントは、高可用性と負荷分散です。 高可用性の要件は、負荷分散の決定に影響を及ぼすことがあります。</span><span class="sxs-lookup"><span data-stu-id="b0a87-p107">The primary decision points for topology selection are high availability and load balancing. The requirement for high availability can influence the load balancing decision.</span></span>

  - <span data-ttu-id="b0a87-197">**高可用性**  高可用性が必要な場合は、少なくとも2台のエッジサーバーをプールに展開します。</span><span class="sxs-lookup"><span data-stu-id="b0a87-197">**High availability**   If you need high availability, deploy at least two Edge Servers in a pool.</span></span> <span data-ttu-id="b0a87-198">1つのエッジプールは最大12台のエッジサーバーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="b0a87-198">A single Edge pool will support up to twelve Edge Servers.</span></span> <span data-ttu-id="b0a87-199">処理能力を増やす場合は、複数のエッジ プールを展開できます。</span><span class="sxs-lookup"><span data-stu-id="b0a87-199">If more capacity is required, you can deploy multiple Edge pools.</span></span> <span data-ttu-id="b0a87-200">一般には、ユーザー ベースの 10％ は、外部アクセスを必要とします。</span><span class="sxs-lookup"><span data-stu-id="b0a87-200">As a general rule, 10% of a given user base will need external access.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="b0a87-201">トポロジビルダーを使用すると、1つのエッジプールで最大20台のエッジサーバーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="b0a87-201">Topology Builder will allow you to configure up to twenty Edge Servers in a single Edge pool.</span></span> <span data-ttu-id="b0a87-202">プール内のエッジサーバーのテスト済みおよびサポートされる最大数は12で、12より大きい数のトポロジビルダーは、1つのエッジプールに12台以上のエッジサーバーがあることを示す暗黙的なサポートとして解釈されないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0a87-202">The tested and supported maximum number of Edge Servers in a pool is twelve and Topology Builder allowing for a number larger than twelve should not be construed as implied support for more than twelve Edge Servers in a single Edge pool.</span></span>

    
    </div>

  - <span data-ttu-id="b0a87-203">**ハードウェア負荷分散**  エッジの外部インターフェイスに対してパブリックルーティング可能な IP アドレスを使用している場合、Lync Server 2013 エッジサーバーの負荷分散は、ハードウェア負荷分散をサポートします。</span><span class="sxs-lookup"><span data-stu-id="b0a87-203">**Hardware load balancing**   Hardware load balancing is supported for load balancing Lync Server 2013 Edge Servers when using publicly routable IP addresses for the Edge external interfaces.</span></span> <span data-ttu-id="b0a87-204">たとえば、次のいずれかのアプリケーションでフェールオーバーが必要な状況でこのアプローチを使用します。</span><span class="sxs-lookup"><span data-stu-id="b0a87-204">For example, you would use this approach in situations where failover is required for any of the following applications:</span></span>
    
      - <span data-ttu-id="b0a87-205">パブリック IM 接続</span><span class="sxs-lookup"><span data-stu-id="b0a87-205">Public IM connectivity</span></span>
    
      - <span data-ttu-id="b0a87-206">Microsoft Office Communications Server 2007 または Microsoft Office Communications Server 2007 R2 を実行している企業とのフェデレーション</span><span class="sxs-lookup"><span data-stu-id="b0a87-206">Federation with companies running Microsoft Office Communications Server 2007 or Microsoft Office Communications Server 2007 R2</span></span>
    
      - <span data-ttu-id="b0a87-207">Exchange 2007 Unified Messaging (UM) または Exchange 2010 UM への外部アクセス</span><span class="sxs-lookup"><span data-stu-id="b0a87-207">External access to Exchange 2007 Unified Messaging (UM) or Exchange 2010 UM</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="b0a87-208">Exchange UM では、Exchange 2010 SP1 以降の DNS 負荷分散がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b0a87-208">DNS load balancing for Exchange 2010 SP1 and newer is supported for Exchange UM.</span></span>

        
        </div>
    
    <span data-ttu-id="b0a87-p111">これら 3 つのアプリケーションは引き続き動作しますが、DNS 負荷分散に対応していないため、プール内の最初のエッジ サーバーだけに接続されます。 そのサーバーを使用できなくなると、接続は切断されます。 たとえば、フェデレーションされたトラフィックの負荷を処理するために、プールに複数のエッジ サーバーが展開されていても、実際には、1 台のアクセス プロキシだけがトラフィックを受信し、残りのサーバーはアイドル状態です。</span><span class="sxs-lookup"><span data-stu-id="b0a87-p111">These three applications will continue to operate, but they are not DNS load balancing aware and will only connect to the first Edge Server in the pool. If that server is unavailable, the connection will fail. For example, if multiple Edge Servers are deployed in a pool to handle the federated traffic load, only one access proxy actually receives traffic while the others are idle.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="b0a87-212">Lync Server 2010 および Microsoft Office 365 を使用して企業とフェデレーションを行う場合は、DNS 負荷分散を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b0a87-212">Using DNS load balancing is recommended if you are federating with companies using Lync Server 2010 and Microsoft Office 365.</span></span> <span data-ttu-id="b0a87-213">フェデレーションパートナーの大部分が Office Communications Server 2007 または Office Communications Server 2007 R2 を使用している場合は、パフォーマンスに著しい影響を与えることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b0a87-213">Be aware that there are significant performance impacts if most of your federated partners are using Office Communications Server 2007 or Office Communications Server 2007 R2.</span></span>



<span data-ttu-id="b0a87-214"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="b0a87-214"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

