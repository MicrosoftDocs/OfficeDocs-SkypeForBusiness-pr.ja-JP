---
title: Lync Server 2013 ユーザーモデルを使用した処理能力の計画
description: Lync Server 2013 ユーザーモデルを使用した処理能力の計画。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning using the user models
ms:assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615015(v=OCS.15)
ms:contentKeyID: 49733733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b710f7ec88dd75c872d704f2169fa2f161fc186
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544413"
---
# <a name="capacity-planning-for-lync-server-2013-using-the-user-models"></a><span data-ttu-id="09b1f-103">ユーザーモデルを使用した Lync Server 2013 の容量計画</span><span class="sxs-lookup"><span data-stu-id="09b1f-103">Capacity planning for Lync Server 2013 using the user models</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09b1f-104">_**トピックの最終更新日:** 2014-01-14_</span><span class="sxs-lookup"><span data-stu-id="09b1f-104">_**Topic Last Modified:** 2014-01-14_</span></span>

<span data-ttu-id="09b1f-105">このセクションでは、 [Lync Server 2013 のユーザーモデル](lync-server-2013-user-models.md)で説明されている使用法に従って、サイトで必要なサーバーの数についてのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="09b1f-105">This section provides guidance on how many servers you need at a site for the number of users at that site, according to the usage described in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<div>

## <a name="tested-hardware-platform"></a><span data-ttu-id="09b1f-106">テスト済みのハードウェアプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="09b1f-106">Tested Hardware Platform</span></span>

<span data-ttu-id="09b1f-107">このセクションのパフォーマンスの結果と展開に関する推奨事項はすべて、次の表に示すハードウェアを実行しているサーバーのパフォーマンステストに基づいています。</span><span class="sxs-lookup"><span data-stu-id="09b1f-107">All the performance results and deployment recommendations in this section are based on performance testing on servers running the hardware described in the following table.</span></span> <span data-ttu-id="09b1f-108">同様のハードウェアを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="09b1f-108">We recommend that you use similar hardware.</span></span> <span data-ttu-id="09b1f-109">より強力なハードウェアを使用すると、機能に問題が発生したり、パフォーマンスが低下したりする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="09b1f-109">If you use less powerful hardware, you may experience functionality problems or poor performance.</span></span> <span data-ttu-id="09b1f-110">これらの推奨ハードウェアは、以前のバージョンの Lync Server よりも高いことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="09b1f-110">Note that these hardware recommendations are higher than those of previous versions of Lync Server.</span></span>

### <a name="hardware-used-in-performance-testing"></a><span data-ttu-id="09b1f-111">パフォーマンステストで使用されるハードウェア</span><span class="sxs-lookup"><span data-stu-id="09b1f-111">Hardware Used in Performance Testing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="09b1f-112">ハードウェア コンポーネント</span><span class="sxs-lookup"><span data-stu-id="09b1f-112">Hardware component</span></span></th>
<th><span data-ttu-id="09b1f-113">推奨</span><span class="sxs-lookup"><span data-stu-id="09b1f-113">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="09b1f-114">CPU</span><span class="sxs-lookup"><span data-stu-id="09b1f-114">CPU</span></span></p></td>
<td><p><span data-ttu-id="09b1f-115">64 ビット デュアル プロセッサ、6 コア、2.26 GHz 以上</span><span class="sxs-lookup"><span data-stu-id="09b1f-115">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher</span></span></p>
<p><span data-ttu-id="09b1f-116">Lync Server のサーバーの役割では、Intel Itanium プロセッサはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="09b1f-116">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09b1f-117">メモリ</span><span class="sxs-lookup"><span data-stu-id="09b1f-117">Memory</span></span></p></td>
<td><p><span data-ttu-id="09b1f-118">32 ギガバイト (GB)</span><span class="sxs-lookup"><span data-stu-id="09b1f-118">32 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09b1f-119">ディスク</span><span class="sxs-lookup"><span data-stu-id="09b1f-119">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="09b1f-120">1万 RPM のハードディスクドライブのうち、少なくとも 72 GB の空きディスク領域があるものを8台以上。</span><span class="sxs-lookup"><span data-stu-id="09b1f-120">8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="09b1f-121">ディスクのうち 2 台で RAID 1 を使用し、6 台で RAID 10 を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09b1f-121">Two of the disks should use RAID 1, and six should use RAID 10.</span></span></p>
<p><span data-ttu-id="09b1f-122">- や</span><span class="sxs-lookup"><span data-stu-id="09b1f-122">- OR -</span></span></p></li>
<li><p><span data-ttu-id="09b1f-123">10,000 RPM の機械的ディスク ドライブ 8 台と同等のパフォーマンスを持つソリッド ステート ドライブ (SSD)</span><span class="sxs-lookup"><span data-stu-id="09b1f-123">Solid state drives (SSDs) which provide performance similar to 8 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09b1f-124">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="09b1f-124">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="09b1f-125">1 Gbps 以上のデュアルポート ネットワーク アダプター 1 つ (2 つを推奨。その場合は 1 つの MAC アドレスと 1 つの IP アドレスのチーミングが必要)</span><span class="sxs-lookup"><span data-stu-id="09b1f-125">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="summary-of-results"></a><span data-ttu-id="09b1f-126">結果の概要</span><span class="sxs-lookup"><span data-stu-id="09b1f-126">Summary of Results</span></span>

<span data-ttu-id="09b1f-127">次の表は、これらの推奨事項を要約したものです。</span><span class="sxs-lookup"><span data-stu-id="09b1f-127">The following table summarizes these recommendations.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="09b1f-128">サーバーの役割</span><span class="sxs-lookup"><span data-stu-id="09b1f-128">Server role</span></span></th>
<th><span data-ttu-id="09b1f-129">サポートされる最大ユーザー数</span><span class="sxs-lookup"><span data-stu-id="09b1f-129">Maximum number of users supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="09b1f-130">12台のフロントエンドサーバーと1つのバックエンドサーバー、またはバックエンドサーバーのミラー化されたペアのフロントエンドプール。</span><span class="sxs-lookup"><span data-stu-id="09b1f-130">Front End pool with twelve Front End Servers and one Back End Server or a mirrored pair of Back End Servers.</span></span></p></td>
<td><p><span data-ttu-id="09b1f-131">8万ユーザーが同時にログインし、50% 複数のプレゼンスポイント (MPOP) が表示されます。これには、非モバイルインスタンスが表示されます。さらに、合計152000エンドポイントのモビリティが有効になっているユーザーの40%。</span><span class="sxs-lookup"><span data-stu-id="09b1f-131">80,000 unique users simultaneously logged in, plus 50% multiple points of presence (MPOP) representing non-mobile instances, plus 40% of users enabled for Mobility for a total of 152,000 endpoints.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09b1f-132">音声ビデオ会議</span><span class="sxs-lookup"><span data-stu-id="09b1f-132">A/V Conferencing</span></span></p></td>
<td><p><span data-ttu-id="09b1f-133">フロントエンドプールによって提供される音声ビデオ会議サービスは、最大会議サイズ250ユーザーを想定し、一度に実行する大規模な会議を1つだけ持つプールの会議をサポートします。</span><span class="sxs-lookup"><span data-stu-id="09b1f-133">The A/V Conferencing service provided by a Front End pool supports the pool’s conferences assuming a maximum conference size of 250 users, and only one such large conference running at a time.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="09b1f-134">さらに、大規模な会議をホストするために2台のフロントエンドサーバーを使用する独立したフロントエンドプールを展開することで、250と1000ユーザーの間の大規模な会議をサポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="09b1f-134">Additionally, you can support large conferences of between 250 and 1000 users by deploying a separate Front End pool with two Front End Servers to host the large conferences.</span></span> <span data-ttu-id="09b1f-135">詳細については、「 <A href="lync-server-2013-supporting-large-meetings.md">Lync Server 2013 を使用した大規模会議のサポート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09b1f-135">For details, see <A href="lync-server-2013-supporting-large-meetings.md">Supporting large meetings using Lync Server 2013</A>.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09b1f-136">1 台のエッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="09b1f-136">One Edge Server</span></span></p></td>
<td><p><span data-ttu-id="09b1f-137">12000同時リモートユーザー</span><span class="sxs-lookup"><span data-stu-id="09b1f-137">12,000 concurrent remote users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09b1f-138">1 台のディレクター</span><span class="sxs-lookup"><span data-stu-id="09b1f-138">One Director</span></span></p></td>
<td><p><span data-ttu-id="09b1f-139">12000同時リモートユーザー</span><span class="sxs-lookup"><span data-stu-id="09b1f-139">12,000 concurrent remote users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09b1f-140">監視およびアーカイブ</span><span class="sxs-lookup"><span data-stu-id="09b1f-140">Monitoring and Archiving</span></span></p></td>
<td><p><span data-ttu-id="09b1f-141">Lync Server 2013 では、監視およびアーカイブのフロントエンドサービスが、個別のサーバーの役割ではなく、各フロントエンドサーバーで実行されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="09b1f-141">In Lync Server 2013, the Monitoring and Archiving front end services now run on each Front End Server, instead of on separate server roles.</span></span></p>
<p><span data-ttu-id="09b1f-142">監視とアーカイブには、それぞれ独自のデータベースストアが必要です。</span><span class="sxs-lookup"><span data-stu-id="09b1f-142">Monitoring and Archiving each still require their own database stores.</span></span> <span data-ttu-id="09b1f-143">Exchange 2013 も実行している場合は、専用の SQL データベースではなく、Exchange にアーカイブデータを保持できます。</span><span class="sxs-lookup"><span data-stu-id="09b1f-143">If you also run Exchange 2013, you can keep your Archiving data in Exchange, rather than in a dedicated SQL database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09b1f-144">1 台の仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="09b1f-144">One Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="09b1f-145">フロントエンドサーバーと併置された仲介サーバーは、プール内のすべてのフロントエンドサーバーで実行され、プール内のユーザーに十分な容量を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09b1f-145">Mediation Server collocated with Front End Server runs on every Front End Server in a pool, and should provide enough capacity for the users in the pool.</span></span> <span data-ttu-id="09b1f-146">スタンドアロンの仲介サーバーの場合は、このトピックで後述する「仲介サーバー」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="09b1f-146">For stand-alone Mediation Server, see the “Mediation Server” section later in this topic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09b1f-147">1 台の Standard Edition サーバー</span><span class="sxs-lookup"><span data-stu-id="09b1f-147">One Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="09b1f-148">Standard Edition サーバーを使用してユーザーをホストする場合は、「 <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">Lync Server 2013 での高可用性と障害復旧の計画</a>」の推奨事項を使用して、常に2台のサーバーを使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="09b1f-148">We strongly recommend that if you use Standard Edition servers to host users, you always use two servers, paired using the recommendations in <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">Planning for high availability and disaster recovery in Lync Server 2013</a>.</span></span> <span data-ttu-id="09b1f-149">ペア内の各サーバーは最大2500ユーザーをホストでき、1台のサーバーが障害を発生した場合、残りのサーバーはフェールオーバーシナリオで5000ユーザーをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="09b1f-149">Each server in the pair can host up to 2,500 users, and if one server fails the remaining server can support 5,000 users in a failover scenario.</span></span></p>
<p><span data-ttu-id="09b1f-150">展開に大量のオーディオまたはビデオトラフィックが含まれている場合、サーバーあたりのユーザー数が2500を超えると、サーバーのパフォーマンスが低下することがあります。</span><span class="sxs-lookup"><span data-stu-id="09b1f-150">If your deployment includes a significant amount of audio or video traffic, server performance may suffer with more than 2,500 users per server.</span></span> <span data-ttu-id="09b1f-151">この場合は、より多くの Standard Edition サーバーを追加するか、Lync Server Enterprise Edition に移行することを検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09b1f-151">In this case, you should consider adding more Standard Edition servers or moving to Lync Server Enterprise Edition.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-server"></a><span data-ttu-id="09b1f-152">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="09b1f-152">Front End Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="09b1f-153">拡張されたプールは、このサーバーの役割ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="09b1f-153">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="09b1f-154">フロントエンドプールには、プール内のすべてのサーバーでハイパースレッディングが有効になっており、サーバーハードウェアが [Lync server 2013 のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)の推奨事項を満たしていることを前提として、プールに所属する6660ユーザーごとに1台のフロントエンドサーバーが必要です。</span><span class="sxs-lookup"><span data-stu-id="09b1f-154">In a Front End pool, you should have one Front End Server for every 6,660 users homed in the pool, assuming that hyper-threading is enabled on all servers in the pool, and that the server hardware meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span> <span data-ttu-id="09b1f-155">1つのフロントエンドプール内のユーザーの最大数は、ハイパースレッディングがプール内のすべてのサーバーで有効になっていることを前提としています (8万)。</span><span class="sxs-lookup"><span data-stu-id="09b1f-155">The maximum number of users in one Front End pool is 80,000, assuming that hyper-threading is enabled on all the servers in the pool.</span></span> <span data-ttu-id="09b1f-156">サイトに 80,000 を超えるユーザーが存在する場合、複数のフロント エンド プールを展開できます。</span><span class="sxs-lookup"><span data-stu-id="09b1f-156">If you have more than 80,000 users at a site, you can deploy more than one Front End pool.</span></span>

<span data-ttu-id="09b1f-157">フロント エンド プール内のユーザー数を考慮する際は、このフロント エンド プールに関連付けられているブランチ オフィスの存続可能ブランチ アプライアンスおよび存続可能ブランチ サーバーに所属するユーザーを含めます。</span><span class="sxs-lookup"><span data-stu-id="09b1f-157">When you account for the number of users in a Front End pool, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with this Front End pool.</span></span>

<span data-ttu-id="09b1f-158">アクティブなサーバーが使用できなくなると、その接続はプール内にある他のサーバーに自動的に転送されます。</span><span class="sxs-lookup"><span data-stu-id="09b1f-158">When an active server is unavailable, its connections are transferred automatically to the other servers in the pool.</span></span> <span data-ttu-id="09b1f-159">たとえば、3万ユーザーと5台のフロントエンドサーバーがある場合、1台のサーバーを使用できない場合は、6000ユーザーの接続を他の4台のサーバーに転送する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09b1f-159">For example, if you have 30,000 users and five Front End Servers, then if one server is unavailable, the connections of 6000 users need to be transferred to the other four servers.</span></span> <span data-ttu-id="09b1f-160">残りの4台のサーバーはそれぞれ7500ユーザーを持ち、推奨されるよりも大きな数です。</span><span class="sxs-lookup"><span data-stu-id="09b1f-160">The remaining four servers will each have 7500 users, which is a larger number than recommended.</span></span>

<span data-ttu-id="09b1f-161">その代わりに、3万ユーザーの6台のフロントエンドサーバーを使用していて、その後で使用できなくなった場合は、合計で5000ユーザーが残りの5台のサーバーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="09b1f-161">If instead you had started with six Front End Servers for your 30,000 users and subsequently one became unavailable, a total of 5000 users will be moved to the remaining five servers.</span></span> <span data-ttu-id="09b1f-162">これら5台のサーバーはそれぞれ6000ユーザーをホストしますが、これは推奨範囲になっています。</span><span class="sxs-lookup"><span data-stu-id="09b1f-162">These five servers will each host 6000 users, which is in the recommended range.</span></span>

<span data-ttu-id="09b1f-163">1 フロント エンド プール内の最大ユーザー数は 80,000 です。</span><span class="sxs-lookup"><span data-stu-id="09b1f-163">The maximum number of users in a Front End pool is 80,000.</span></span> <span data-ttu-id="09b1f-164">プール内のフロントエンドサーバーの最大数は12です。</span><span class="sxs-lookup"><span data-stu-id="09b1f-164">The maximum number of Front End Servers in a pool is 12.</span></span>

<span data-ttu-id="09b1f-165">8万ユーザーが含まれるフロントエンドプールの場合、通常、 [Lync Server 2013 のユーザーモデル](lync-server-2013-user-models.md)に準拠する展開では、12台のフロントエンドサーバーでパフォーマンスを十分に確保できます。</span><span class="sxs-lookup"><span data-stu-id="09b1f-165">For a Front End pool with 80,000 users, twelve Front End Servers is sufficient for performance, in typical deployments that follow the [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span> <span data-ttu-id="09b1f-166">障害復旧フェールオーバーをサポートするように設計されている展開では、2つのペアのフロントエンドプールのそれぞれで最大4万ユーザーをホストすることができます。これには、両方のプールのユーザーに対応する十分な数のフロントエンドサーバーが存在することが前提となります。</span><span class="sxs-lookup"><span data-stu-id="09b1f-166">Deployments designed to support disaster recovery failover assume that a maximum of 40,000 users can be hosted in each of two paired Front End pools, in which each pool has enough Front End Servers to accommodate the users in both pools should one pool need to be failed over to the other.</span></span>

<span data-ttu-id="09b1f-167">特定のフロントエンドプールでサポートされているユーザーの数は、次の理由から、これらの値と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="09b1f-167">The number of users supported with good performance by a particular Front End pool may differ from these numbers for the following reasons:</span></span>

  - <span data-ttu-id="09b1f-168">フロントエンドサーバーのハードウェアは、 [Lync server 2013 のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)の推奨事項を満たしていません。</span><span class="sxs-lookup"><span data-stu-id="09b1f-168">The hardware for your Front End Servers does not meet the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

  - <span data-ttu-id="09b1f-169">ユーザー モデルよりもかなり多い会議トラフィックの場合など、組織の使用法がユーザー モデルのそれと著しく異なります。</span><span class="sxs-lookup"><span data-stu-id="09b1f-169">Your organization’s usage differs significantly from the user models, such as significantly more conferencing traffic.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="09b1f-170">Lync Server 2013 では、プレゼンスデータベースは、バックエンドサーバーでホストされていた Lync Server 2010 とは異なり、フロントエンドサーバーでホストされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="09b1f-170">In Lync Server 2013, the presence databases are now hosted on Front End Servers, unlike in Lync Server 2010 where they were hosted on the Back End Server.</span></span> <span data-ttu-id="09b1f-171">これは、フロントエンドサーバーによってホストされているユーザーの数に関係なく、このセクションおよび <A href="lync-server-2013-server-hardware-platforms.md">Lync server 2013 のサーバーハードウェアプラットフォーム</A>で前述した推奨事項から、フロントエンドサーバーのディスクのパフォーマンスと容量を侵害してはならないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="09b1f-171">This means that the disk performance and capacity of your Front End Servers should not be compromised from the recommendations listed earlier in this section and in <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>, regardless of the number of users hosted by your Front End Servers.</span></span>



</div>

<span data-ttu-id="09b1f-172">次の表に、 [Lync Server 2013 のユーザーモデル](lync-server-2013-user-models.md)で定義されているように、ユーザーモデルを使用して IM とプレゼンスの平均帯域幅を示します。</span><span class="sxs-lookup"><span data-stu-id="09b1f-172">The following table shows the average bandwidth for IM and presence, given the user model, as defined in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="09b1f-173">ユーザー単位の平均帯域幅</span><span class="sxs-lookup"><span data-stu-id="09b1f-173">Average bandwidth per user</span></span></th>
<th><span data-ttu-id="09b1f-174">6660ユーザーのフロントエンドサーバーごとの帯域幅要件</span><span class="sxs-lookup"><span data-stu-id="09b1f-174">Bandwidth requirements per Front End Server with 6,660 users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="09b1f-175">1.3 Kpbs</span><span class="sxs-lookup"><span data-stu-id="09b1f-175">1.3 Kpbs</span></span></p></td>
<td><p><span data-ttu-id="09b1f-176">13 Mbps</span><span class="sxs-lookup"><span data-stu-id="09b1f-176">13 Mbps</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="09b1f-177">フロントエンドサーバーで併置された音声ビデオ会議と仲介サーバーの機能のメディアパフォーマンスを向上させるには、フロントエンドサーバーのネットワークアダプターで受信側の拡大/縮小 (RSS) を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="09b1f-177">To improve the media performance of the co-located A/V Conferencing and Mediation Server functionality on your Front End Servers, you should enable receive-side scaling (RSS) on the network adapters on your Front End Servers.</span></span> <span data-ttu-id="09b1f-178">RSS は、着信パケットがサーバーの複数のプロセッサによって平行して処理されるのを可能にします。</span><span class="sxs-lookup"><span data-stu-id="09b1f-178">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="09b1f-179">詳細については、「」の「Windows Server 2008 の受信側スケーリングの拡張機能」を参照してください <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A> 。</span><span class="sxs-lookup"><span data-stu-id="09b1f-179">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="09b1f-180">RSS を有効にする方法の詳細については、ネットワークアダプターのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="09b1f-180">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="conferencing-maximums"></a><span data-ttu-id="09b1f-181">最大会議数</span><span class="sxs-lookup"><span data-stu-id="09b1f-181">Conferencing Maximums</span></span>

<span data-ttu-id="09b1f-182">ユーザーモデルでは、プール内のユーザーの5% が一度に会議に参加している可能性があるため、8万のユーザーのプールは、一度に1人の電話会議に約4000ユーザーを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="09b1f-182">Given the user model that 5% of users in a pool may be in a conference at any one time, a pool of 80,000 users could have about 4,000 users in conferences at one time.</span></span> <span data-ttu-id="09b1f-183">これらの電話会議は、メディアが混在していることが予想されます (一部の IM のみ、一部の IM、オーディオ/ビデオなど)、参加者の数です。</span><span class="sxs-lookup"><span data-stu-id="09b1f-183">These conferences are expected to be a mix of media (some IM-only, some IM with audio, some audio/video, for example) and number of participants.</span></span> <span data-ttu-id="09b1f-184">許可されている実際の電話会議数に対するハードリミットはありません。実際の使用量によって実際のパフォーマンスが決まります。</span><span class="sxs-lookup"><span data-stu-id="09b1f-184">There is no hard limit for the actual number of conferences allowed, and actual usage determines the actual performance.</span></span> <span data-ttu-id="09b1f-185">たとえば、組織にユーザーモデルで想定されているよりも多くの混在モードの会議がある場合は、このドキュメントの推奨事項より多くのフロントエンドサーバーまたは音声ビデオ会議サーバーを展開する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="09b1f-185">For example, if your organization has many more mixed-mode conferences than are assumed in the user model, you might need to deploy more Front End Servers or A/V Conferencing Servers than the recommendations in this document.</span></span> <span data-ttu-id="09b1f-186">ユーザーモデルの前提条件の詳細については、「 [Lync Server 2013 のユーザーモデル](lync-server-2013-user-models.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09b1f-186">For details about the assumptions in the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<span data-ttu-id="09b1f-187">通常の Lync Server 2013 フロントエンドプールでホストされている、サポートされている会議の最大サイズは、ユーザーが250参加者であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="09b1f-187">The maximum supported conference size hosted by a regular Lync Server 2013 Front End pool which also hosts users is 250 participants.</span></span> <span data-ttu-id="09b1f-188">250ユーザーの会議が発生している間も、プールは引き続き他の会議をサポートしています。これには、プールユーザーの合計5% が同時会議に含まれます。</span><span class="sxs-lookup"><span data-stu-id="09b1f-188">While a 250-user conference is happening, the pool still supports other conferences as well, such that a total of 5% of pool users are in concurrent conferences.</span></span> <span data-ttu-id="09b1f-189">たとえば、12台のフロントエンドサーバーと8万ユーザーのプールでは、250ユーザーの会議が発生している間、Lync Server は、小規模の電話会議に参加している他のユーザーの3750をサポートします。</span><span class="sxs-lookup"><span data-stu-id="09b1f-189">For example, in a pool of twelve Front End Servers and 80,000 users, while the 250-user conference is happening, Lync Server supports 3,750 other users participating in smaller conferences.</span></span>

<span data-ttu-id="09b1f-190">Lync Server は、フロントエンドプールまたは Standard Edition サーバーに所属しているユーザー数に関係なく、250ユーザーの会議をホストしている同じプールまたはサーバー上の小さな会議に参加する、少なくとも125の他のユーザーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="09b1f-190">Regardless of the number of users homed on the Front End pool or Standard Edition server, Lync Server supports a minimum of 125 other users participating in smaller conferences on the same pool or server which is hosting a 250-user conference.</span></span>

<span data-ttu-id="09b1f-191">250ユーザーと1000ユーザーの間で会議を有効にするには、これらの会議をホストするためだけに別のフロントエンドプールをセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="09b1f-191">To enable conferences with between 250 and 1000 users, you can set up a separate Front End pool just to host those conferences.</span></span> <span data-ttu-id="09b1f-192">このフロントエンドプールでは、ユーザーはホストされません。</span><span class="sxs-lookup"><span data-stu-id="09b1f-192">This Front End pool will not host any users.</span></span> <span data-ttu-id="09b1f-193">詳細については、「 [Lync Server 2013 を使用した大規模会議のサポート](lync-server-2013-supporting-large-meetings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09b1f-193">For details, see [Supporting large meetings using Lync Server 2013](lync-server-2013-supporting-large-meetings.md).</span></span>

<span data-ttu-id="09b1f-194">ユーザーモデルで想定されているよりも多くの混合モード会議が組織にある場合は、このドキュメントの推奨事項 (上限は 12 FEs) より多くのフロントエンドサーバーを展開する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="09b1f-194">If your organization has many more mixed-mode conferences than are assumed in the user model, you might need to deploy more Front End Servers than the recommendations in this document (up to a limit of 12 FEs).</span></span> <span data-ttu-id="09b1f-195">ユーザーモデルの前提条件の詳細については、「 [Lync Server 2013 のユーザーモデル](lync-server-2013-user-models.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09b1f-195">For details about the assumptions in the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

</div>

<div>

## <a name="edge-server"></a><span data-ttu-id="09b1f-196">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="09b1f-196">Edge Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="09b1f-197">拡張されたプールは、このサーバーの役割ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="09b1f-197">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="09b1f-198">サイトに同時にアクセスする12000リモートユーザーごとに1つのエッジサーバーを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09b1f-198">You should deploy one Edge Server for every 12,000 remote users who will access a site concurrently.</span></span> <span data-ttu-id="09b1f-199">高可用性を実現するために 2 つ以上のエッジ サーバーを用意することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="09b1f-199">At a minimum we recommend two Edge Servers for high availability.</span></span> <span data-ttu-id="09b1f-200">これらの推奨事項は、エッジサーバーのハードウェアが [Lync server 2013 のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)の推奨事項を満たしていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="09b1f-200">These recommendations assume that the hardware for your Edge Servers meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="09b1f-201">エッジ サーバーのユーザー数を考慮する際は、このサイトのフロント エンド プールに関連付けられているブランチ オフィスの存続可能ブランチ アプライアンスおよび存続可能ブランチ サーバーに所属するユーザーを含めます。</span><span class="sxs-lookup"><span data-stu-id="09b1f-201">When you account for the number of users for the Edge Servers, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with a Front End pool at this site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="09b1f-202">エッジ サーバーの音声ビデオ会議エッジ サービスのパフォーマンスを改善するには、エッジ サーバーのネットワーク アダプターの Receive-side Scaling (RSS) を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="09b1f-202">To improve the performance of the A/V Conferencing Edge service on your Edge Servers, you should enable receive-side scaling (RSS) on the network adapters on your Edge Servers.</span></span> <span data-ttu-id="09b1f-203">RSS は、着信パケットがサーバーの複数のプロセッサによって平行して処理されるのを可能にします。</span><span class="sxs-lookup"><span data-stu-id="09b1f-203">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="09b1f-204">詳細については、「」の「Windows Server 2008 の受信側スケーリングの拡張機能」を参照してください <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A> 。</span><span class="sxs-lookup"><span data-stu-id="09b1f-204">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="09b1f-205">RSS を有効にする方法の詳細については、ネットワークアダプターのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="09b1f-205">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="director"></a><span data-ttu-id="09b1f-206">ディレクター</span><span class="sxs-lookup"><span data-stu-id="09b1f-206">Director</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="09b1f-207">拡張されたプールは、このサーバーの役割ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="09b1f-207">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="09b1f-208">ディレクターサーバーの役割を展開する場合は、サイトに同時にアクセスするすべての12000リモートユーザーに対して1つのディレクターを展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="09b1f-208">If you deploy the Director server role we recommend that you deploy one Director for every 12,000 remote users who will access a site concurrently.</span></span> <span data-ttu-id="09b1f-209">高可用性を実現するために 2 つ以上のディレクターを用意することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="09b1f-209">At a minimum we recommend two Directors for high availability.</span></span> <span data-ttu-id="09b1f-210">これらの推奨事項は、エッジサーバーのハードウェアが [Lync server 2013 のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)の推奨事項を満たしていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="09b1f-210">These recommendations assume that the hardware for your Edge Servers meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="09b1f-211">ディレクターのユーザー数を考慮する際は、このサイトのフロント エンド プールに関連付けられているブランチ オフィスの存続可能ブランチ アプライアンスおよび存続可能ブランチ サーバーに所属するユーザーを含めます。</span><span class="sxs-lookup"><span data-stu-id="09b1f-211">When you account for the number of users for the Directors, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with a Front End pool at this site.</span></span>

</div>

<div>

## <a name="mediation-server"></a><span data-ttu-id="09b1f-212">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="09b1f-212">Mediation Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="09b1f-213">拡張されたプールは、このサーバーの役割ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="09b1f-213">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="09b1f-214">仲介サーバーをフロントエンドサーバーと併置する場合、仲介サーバーはプール内のすべてのフロントエンドサーバー上で実行され、プール内のユーザーに十分な容量を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09b1f-214">If you collocate Mediation Server with Front End Server, Mediation Server runs on every Front End Server in the pool, and should provide enough capacity for the users in the pool.</span></span>

<span data-ttu-id="09b1f-215">スタンドアロンの仲介サーバープールを展開する場合、展開する仲介サーバーの数は、仲介サーバーに使用されるハードウェア、所有する VoIP ユーザーの数、各仲介サーバープールが制御するゲートウェイピアの数、それらのゲートウェイを通過するゲートウェイピアの数、仲介サーバーをバイパスするメディアでの通話の割合など、さまざまな要因によって異なります。</span><span class="sxs-lookup"><span data-stu-id="09b1f-215">If you deploy a stand-alone Mediation Server pool, then how many Mediation Servers to deploy depends on many factors, including the hardware used for Mediation Server, the number of VoIP users you have, the number of gateway peers that each Mediation Server pool controls, the busy hour traffic through those gateways, and the percentage of calls with media that bypasses the Mediation Server.</span></span>

<span data-ttu-id="09b1f-216">次の表は、仲介サーバーのハードウェアが [Lync server 2013 のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md) の要件を満たしており、ハイパースレッディングが有効になっている場合に、仲介サーバーが処理できる同時呼び出し数に関するガイドラインを提供します。</span><span class="sxs-lookup"><span data-stu-id="09b1f-216">The following tables provide a guideline for how many concurrent calls a Mediation Server can handle, assuming that the hardware for the Mediation Servers meets the requirements in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) and that hyper-threading is enabled.</span></span> <span data-ttu-id="09b1f-217">仲介サーバーのスケーラビリティの詳細については、「lync server [2013 の音声使用率とトラフィックの見積もり](lync-server-2013-estimating-voice-usage-and-traffic.md) 」および「 [lync Server 2013 の仲介サーバーの展開ガイドライン](lync-server-2013-deployment-guidelines-for-mediation-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09b1f-217">For details about Mediation Server scalability, see [Estimating voice usage and traffic for Lync Server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) and [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span></span>

<span data-ttu-id="09b1f-218">次の表はすべて、 [Lync Server 2013 のユーザーモデル](lync-server-2013-user-models.md)で要約された使用法を前提としています。</span><span class="sxs-lookup"><span data-stu-id="09b1f-218">All the following tables assume usage as summarized in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

### <a name="stand-alone-mediation-server-capacity-70-internal-users-30-external-users-with-non-bypass-call-capacity-media-transcoding-performed-by-mediation-server"></a><span data-ttu-id="09b1f-219">スタンドアロン仲介サーバーの容量: 70% 内部ユーザー、30% の外部ユーザー (仲介サーバーによって実行されるメディアトランスコーディング)</span><span class="sxs-lookup"><span data-stu-id="09b1f-219">Stand-alone Mediation Server Capacity: 70% Internal Users, 30% External users with non-bypass call capacity (media transcoding performed by Mediation Server)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="09b1f-220">サーバー ハードウェア</span><span class="sxs-lookup"><span data-stu-id="09b1f-220">Server hardware</span></span></th>
<th><span data-ttu-id="09b1f-221">最大通話数</span><span class="sxs-lookup"><span data-stu-id="09b1f-221">Maximum number of calls</span></span></th>
<th><span data-ttu-id="09b1f-222">T1 回線の最大数</span><span class="sxs-lookup"><span data-stu-id="09b1f-222">Maximum number of T1 lines</span></span></th>
<th><span data-ttu-id="09b1f-223">E1 回線の最大数</span><span class="sxs-lookup"><span data-stu-id="09b1f-223">Maximum number of E1 lines</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="09b1f-224">デュアルプロセッサ、16コア、2.26 GHz ハイパースレッディング CPU ( <strong>ハイパースレッディング無効</strong>)、32 GB メモリ、および1つのデュアルポートネットワークアダプターカード。</span><span class="sxs-lookup"><span data-stu-id="09b1f-224">Dual processor, hex core, 2.26 GHz hyper-threaded CPU <strong>with hyper-threading disabled</strong>, with 32 GB memory and one dual-port network adapter card.</span></span></p></td>
<td><p><span data-ttu-id="09b1f-225">1100</span><span class="sxs-lookup"><span data-stu-id="09b1f-225">1100</span></span></p></td>
<td><p><span data-ttu-id="09b1f-226">46</span><span class="sxs-lookup"><span data-stu-id="09b1f-226">46</span></span></p></td>
<td><p><span data-ttu-id="09b1f-227">35</span><span class="sxs-lookup"><span data-stu-id="09b1f-227">35</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09b1f-228">デュアルプロセッサ、16コア、2.26 GHz ハイパースレッディング CPU (32 GB メモリと1つのデュアルポートネットワークアダプターカードを使用)。</span><span class="sxs-lookup"><span data-stu-id="09b1f-228">Dual processor, hex core, 2.26 GHz hyper-threaded CPU, with 32 GB memory and one dual-port network adapter card.</span></span></p></td>
<td><p><span data-ttu-id="09b1f-229">1500</span><span class="sxs-lookup"><span data-stu-id="09b1f-229">1500</span></span></p></td>
<td><p><span data-ttu-id="09b1f-230">63</span><span class="sxs-lookup"><span data-stu-id="09b1f-230">63</span></span></p></td>
<td><p><span data-ttu-id="09b1f-231">47</span><span class="sxs-lookup"><span data-stu-id="09b1f-231">47</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="09b1f-232">パフォーマンス テストにはメモリが 32 GB のサーバーを使用しましたが、スタンドアロンの仲介サーバーにはメモリが 16 GB のサーバーがサポートされており、その条件のサーバーでもこの表に示されるパフォーマンスを十分実現できます。</span><span class="sxs-lookup"><span data-stu-id="09b1f-232">Although servers with 32 GB of memory were used for performance testing, servers with 16 GB of memory are supported for stand-alone Mediation Server, and are sufficient to provide the performance shown in this table.</span></span>



</div>

### <a name="mediation-server-capacity-mediation-server-collocated-with-front-end-server-70-internal-users-30-external-users-non-bypass-call-capacity-media-processing-performed-by-mediation-server"></a><span data-ttu-id="09b1f-233">仲介サーバーの処理能力 (フロントエンドサーバーと併置された仲介サーバー) 70% 内部ユーザー、30% の外部ユーザー、非バイパス通話の容量 (仲介サーバーによって実行されるメディア処理)</span><span class="sxs-lookup"><span data-stu-id="09b1f-233">Mediation Server Capacity (Mediation Server Collocated with Front End Server) 70% Internal Users, 30% External Users, Non-Bypass Call Capacity (Media Processing Performed by Mediation Server)</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="09b1f-234">サーバー ハードウェア</span><span class="sxs-lookup"><span data-stu-id="09b1f-234">Server hardware</span></span></th>
<th><span data-ttu-id="09b1f-235">最大通話数</span><span class="sxs-lookup"><span data-stu-id="09b1f-235">Maximum number of calls</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="09b1f-236">デュアルプロセッサ、16進コア、2.26 GHz ハイパースレッディング CPU (32 GB メモリと 2 GB ネットワークアダプターカード)。</span><span class="sxs-lookup"><span data-stu-id="09b1f-236">Dual processor, hex core, 2.26 GHz hyper-threaded CPU, with 32 GB memory and 2 1GB network adapter cards.</span></span></p></td>
<td><p><span data-ttu-id="09b1f-237">150</span><span class="sxs-lookup"><span data-stu-id="09b1f-237">150</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="09b1f-238">この数は、フロントエンドサーバーが、音声呼び出しに必要なトランスコーディングだけでなく、それに所属する6600ユーザーの他の機能や機能を処理する必要があるため、スタンドアロンの仲介サーバーの数よりもはるかに小さくなります。</span><span class="sxs-lookup"><span data-stu-id="09b1f-238">This number is much smaller than the numbers for the stand-alone Mediation Server because the Front End Server has to handle other features and functions for the 6600 users homed on it, in addition to the transcoding needed for voice calls.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="09b1f-239">仲介サーバーのパフォーマンスを向上させるには、仲介サーバーのネットワークアダプターで受信側の拡大/縮小 (RSS) を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="09b1f-239">To improve the performance of the Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on your Mediation Servers.</span></span> <span data-ttu-id="09b1f-240">RSS は、着信パケットがサーバーの複数のプロセッサによって平行して処理されるのを可能にします。</span><span class="sxs-lookup"><span data-stu-id="09b1f-240">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="09b1f-241">詳細については、「」の「Windows Server 2008 の受信側スケーリングの拡張機能」を参照してください <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A> 。</span><span class="sxs-lookup"><span data-stu-id="09b1f-241">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="09b1f-242">RSS を有効にする方法の詳細については、ネットワークアダプターのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="09b1f-242">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="back-end-server"></a><span data-ttu-id="09b1f-243">バック エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="09b1f-243">Back End Server</span></span>

<span data-ttu-id="09b1f-244">Lync Server 2013 では、プレゼンスデータベースはバックエンドサーバーではなくフロントエンドサーバーに配置されます。</span><span class="sxs-lookup"><span data-stu-id="09b1f-244">In Lync Server 2013, the presence databases are located on the Front End Servers instead of the Back End Server.</span></span> <span data-ttu-id="09b1f-245">これにより、Lync Server 2013 のバックエンドサーバーごとに、フロントエンドサーバーのハードウェア要件と同等の要件が大幅に簡略化されました。</span><span class="sxs-lookup"><span data-stu-id="09b1f-245">This has resulted in a much simpler requirement for each Back End Server in Lync Server 2013, equivalent to the hardware requirement for the Front End Server.</span></span> <span data-ttu-id="09b1f-246">これを Lync Server 2010 と比較します。これは、バックエンドサーバーが25台のディスクを使用した、より高いグレードのサーバーでなければならないということです。</span><span class="sxs-lookup"><span data-stu-id="09b1f-246">Contrast this to Lync Server 2010, where the Back End Server was required to be a much higher grade server with 25 disks.</span></span> <span data-ttu-id="09b1f-247">ただし、バックエンドサーバーのワークロードについては、このセクションで前述したハードウェアの推奨事項や、 [Lync server 2013 のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)の要件を満たすことができない場合があります。</span><span class="sxs-lookup"><span data-stu-id="09b1f-247">However, the workload of Back End Servers is still such that you should not fail to meet the hardware recommendations listed earlier in this section and in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="09b1f-248">バックエンドサーバーの高可用性を実現するには、サーバーミラーリングを展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="09b1f-248">To provide high availability of your Back End Server, we recommend deploying server mirroring.</span></span> <span data-ttu-id="09b1f-249">詳細については、「 [Lync server 2013 のバックエンドサーバーの高可用性](lync-server-2013-back-end-server-high-availability.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09b1f-249">For more information, see [Back End Server high availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span></span>

</div>

<div>

## <a name="monitoring-and-archiving"></a><span data-ttu-id="09b1f-250">監視およびアーカイブ</span><span class="sxs-lookup"><span data-stu-id="09b1f-250">Monitoring and Archiving</span></span>

<span data-ttu-id="09b1f-251">Lync Server 2013 では、監視またはアーカイブを展開する場合、これらのサービスのフロントエンド機能は、個別のサーバーの役割ではなくフロントエンドサーバーで実行されます。</span><span class="sxs-lookup"><span data-stu-id="09b1f-251">In Lync Server 2013, if you deploy Monitoring or Archiving, the front end functionality of these services runs on the Front End Servers, instead of on separate server roles.</span></span> <span data-ttu-id="09b1f-252">監視とアーカイブは、バックエンドストアから切り離された独自のデータベースストアを使用します。</span><span class="sxs-lookup"><span data-stu-id="09b1f-252">Monitoring and Archiving each still use their own database store, separate from the Back End store.</span></span> <span data-ttu-id="09b1f-253">または、Exchange 2013 を展開している場合は、専用の SQL ストアではなく、インスタントメッセージのアーカイブデータを Exchange に格納できます。</span><span class="sxs-lookup"><span data-stu-id="09b1f-253">Alternatively, if you have Exchange 2013 deployed, you can store instant message Archiving data in Exchange instead of in a dedicated SQL store.</span></span>

<span data-ttu-id="09b1f-254">次の表は、データを監視およびアーカイブするために、ユーザーごとに1日あたりに必要なデータベース記憶域のおおよその量を示しています。</span><span class="sxs-lookup"><span data-stu-id="09b1f-254">The following table indicates approximately how much database storage is required per user per day for Monitoring and Archiving data.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="09b1f-255"><strong>CDR (監視)</strong></span><span class="sxs-lookup"><span data-stu-id="09b1f-255"><strong>CDR (Monitoring)</strong></span></span></p></td>
<td><p><span data-ttu-id="09b1f-256"><strong>QoE (監視)</strong></span><span class="sxs-lookup"><span data-stu-id="09b1f-256"><strong>QoE (Monitoring)</strong></span></span></p></td>
<td><p><span data-ttu-id="09b1f-257"><strong>アーカイブ</strong></span><span class="sxs-lookup"><span data-stu-id="09b1f-257"><strong>Archiving</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09b1f-258">ユーザーごとに1日あたり必要なディスク領域</span><span class="sxs-lookup"><span data-stu-id="09b1f-258">Disk space required per user per day</span></span></p></td>
<td><p><span data-ttu-id="09b1f-259">49 KB</span><span class="sxs-lookup"><span data-stu-id="09b1f-259">49 KB</span></span></p></td>
<td><p><span data-ttu-id="09b1f-260">28 KB</span><span class="sxs-lookup"><span data-stu-id="09b1f-260">28 KB</span></span></p></td>
<td><p><span data-ttu-id="09b1f-261">57 KB</span><span class="sxs-lookup"><span data-stu-id="09b1f-261">57 KB</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="09b1f-262">Microsoft では、データベースサーバーのパフォーマンステスト中に監視およびアーカイブするために、次の表に示すハードウェアを使用しています。</span><span class="sxs-lookup"><span data-stu-id="09b1f-262">Microsoft used the hardware in the following table for the database server for Monitoring and Archiving during its performance testing.</span></span> <span data-ttu-id="09b1f-263">このテストでは、2つのフロントエンドプールのデータが収集され、それぞれに8万のユーザーが含まれていました。</span><span class="sxs-lookup"><span data-stu-id="09b1f-263">The testing collected the data of two Front End pools, each of which contained 80,000 users.</span></span>

### <a name="hardware-used-in-monitoring-and-archiving-performance-testing"></a><span data-ttu-id="09b1f-264">監視およびアーカイブのパフォーマンステストで使用されるハードウェア</span><span class="sxs-lookup"><span data-stu-id="09b1f-264">Hardware Used in Monitoring and Archiving Performance Testing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="09b1f-265">ハードウェア コンポーネント</span><span class="sxs-lookup"><span data-stu-id="09b1f-265">Hardware component</span></span></th>
<th><span data-ttu-id="09b1f-266">推奨</span><span class="sxs-lookup"><span data-stu-id="09b1f-266">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="09b1f-267">CPU</span><span class="sxs-lookup"><span data-stu-id="09b1f-267">CPU</span></span></p></td>
<td><p><span data-ttu-id="09b1f-268">64 ビット デュアル プロセッサ、6 コア、2.26 GHz 以上</span><span class="sxs-lookup"><span data-stu-id="09b1f-268">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09b1f-269">メモリ</span><span class="sxs-lookup"><span data-stu-id="09b1f-269">Memory</span></span></p></td>
<td><p><span data-ttu-id="09b1f-270">48ギガバイト (GB)</span><span class="sxs-lookup"><span data-stu-id="09b1f-270">48 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09b1f-271">ディスク</span><span class="sxs-lookup"><span data-stu-id="09b1f-271">Disk</span></span></p></td>
<td><p><span data-ttu-id="09b1f-272">25 1万 RPM のハードディスクドライブ、各ディスク上の 300 GB、次の構成</span><span class="sxs-lookup"><span data-stu-id="09b1f-272">25 10,000-RPM hard disk drives with 300 GB on each disk, with the following configuration</span></span></p>
<h3 id="section-3"> </h3>
<div>
<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="09b1f-273"><strong>Drive</strong></span><span class="sxs-lookup"><span data-stu-id="09b1f-273"><strong>Drive</strong></span></span></p></td>
<td><p><span data-ttu-id="09b1f-274"><strong>RAID 構成</strong></span><span class="sxs-lookup"><span data-stu-id="09b1f-274"><strong>RAID Configuration</strong></span></span></p></td>
<td><p><span data-ttu-id="09b1f-275"><strong>ディスク数</strong></span><span class="sxs-lookup"><span data-stu-id="09b1f-275"><strong>Number of disks</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09b1f-276">CDR、QoE、およびアーカイブデータベースのデータファイル、1台のドライブ</span><span class="sxs-lookup"><span data-stu-id="09b1f-276">CDR, QoE, and Archiving database data files, on a single drive</span></span></p></td>
<td><p><span data-ttu-id="09b1f-277">1 + 0</span><span class="sxs-lookup"><span data-stu-id="09b1f-277">1+0</span></span></p></td>
<td><p><span data-ttu-id="09b1f-278">16 </span><span class="sxs-lookup"><span data-stu-id="09b1f-278">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09b1f-279">CDR データベースのログ ファイル</span><span class="sxs-lookup"><span data-stu-id="09b1f-279">CDR database log file</span></span></p></td>
<td><p><span data-ttu-id="09b1f-280">1-d</span><span class="sxs-lookup"><span data-stu-id="09b1f-280">1</span></span></p></td>
<td><p><span data-ttu-id="09b1f-281">pbm-2</span><span class="sxs-lookup"><span data-stu-id="09b1f-281">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09b1f-282">QoE データベースのログ ファイル</span><span class="sxs-lookup"><span data-stu-id="09b1f-282">QoE database log file</span></span></p></td>
<td><p><span data-ttu-id="09b1f-283">1-d</span><span class="sxs-lookup"><span data-stu-id="09b1f-283">1</span></span></p></td>
<td><p><span data-ttu-id="09b1f-284">pbm-2</span><span class="sxs-lookup"><span data-stu-id="09b1f-284">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09b1f-285">アーカイブデータベースのログファイル</span><span class="sxs-lookup"><span data-stu-id="09b1f-285">Archiving database log file</span></span></p></td>
<td><p><span data-ttu-id="09b1f-286">1-d</span><span class="sxs-lookup"><span data-stu-id="09b1f-286">1</span></span></p></td>
<td><p><span data-ttu-id="09b1f-287">pbm-2</span><span class="sxs-lookup"><span data-stu-id="09b1f-287">2</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09b1f-288">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="09b1f-288">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="09b1f-289">1 Gbps 以上のデュアルポート ネットワーク アダプター 1 つ (2 つを推奨。その場合は 1 つの MAC アドレスと 1 つの IP アドレスのチーミングが必要)</span><span class="sxs-lookup"><span data-stu-id="09b1f-289">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="09b1f-290">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="09b1f-290">In This Section</span></span>

  - [<span data-ttu-id="09b1f-291">Lync Server 2013 の音声の使用状況とトラフィックの予測</span><span class="sxs-lookup"><span data-stu-id="09b1f-291">Estimating voice usage and traffic for Lync Server 2013</span></span>](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [<span data-ttu-id="09b1f-292">Lync Server 2013 の仲介サーバーの展開ガイドライン</span><span class="sxs-lookup"><span data-stu-id="09b1f-292">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

