---
title: Lync Server 2013 ユーザーモデルを使用した処理能力の計画
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
ms.openlocfilehash: 664091baee67d0ddf953d8a114370fdb875eef29
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135544"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-lync-server-2013-using-the-user-models"></a><span data-ttu-id="1c0f6-102">ユーザーモデルを使用した Lync Server 2013 の容量計画</span><span class="sxs-lookup"><span data-stu-id="1c0f6-102">Capacity planning for Lync Server 2013 using the user models</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c0f6-103">_**トピックの最終更新日:** 2014-01-14_</span><span class="sxs-lookup"><span data-stu-id="1c0f6-103">_**Topic Last Modified:** 2014-01-14_</span></span>

<span data-ttu-id="1c0f6-104">このセクションでは、 [Lync Server 2013 のユーザーモデル](lync-server-2013-user-models.md)で説明されている使用法に従って、サイトで必要なサーバーの数についてのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-104">This section provides guidance on how many servers you need at a site for the number of users at that site, according to the usage described in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<div>

## <a name="tested-hardware-platform"></a><span data-ttu-id="1c0f6-105">テスト済みのハードウェアプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="1c0f6-105">Tested Hardware Platform</span></span>

<span data-ttu-id="1c0f6-106">このセクションのパフォーマンスの結果と展開に関する推奨事項はすべて、次の表に示すハードウェアを実行しているサーバーのパフォーマンステストに基づいています。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-106">All the performance results and deployment recommendations in this section are based on performance testing on servers running the hardware described in the following table.</span></span> <span data-ttu-id="1c0f6-107">同様のハードウェアを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-107">We recommend that you use similar hardware.</span></span> <span data-ttu-id="1c0f6-108">より強力なハードウェアを使用すると、機能に問題が発生したり、パフォーマンスが低下したりする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-108">If you use less powerful hardware, you may experience functionality problems or poor performance.</span></span> <span data-ttu-id="1c0f6-109">これらの推奨ハードウェアは、以前のバージョンの Lync Server よりも高いことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-109">Note that these hardware recommendations are higher than those of previous versions of Lync Server.</span></span>

### <a name="hardware-used-in-performance-testing"></a><span data-ttu-id="1c0f6-110">パフォーマンステストで使用されるハードウェア</span><span class="sxs-lookup"><span data-stu-id="1c0f6-110">Hardware Used in Performance Testing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1c0f6-111">ハードウェア コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1c0f6-111">Hardware component</span></span></th>
<th><span data-ttu-id="1c0f6-112">推奨</span><span class="sxs-lookup"><span data-stu-id="1c0f6-112">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1c0f6-113">CPU</span><span class="sxs-lookup"><span data-stu-id="1c0f6-113">CPU</span></span></p></td>
<td><p><span data-ttu-id="1c0f6-114">64 ビット デュアル プロセッサ、6 コア、2.26 GHz 以上</span><span class="sxs-lookup"><span data-stu-id="1c0f6-114">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher</span></span></p>
<p><span data-ttu-id="1c0f6-115">Lync Server のサーバーの役割では、Intel Itanium プロセッサはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-115">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c0f6-116">メモリ</span><span class="sxs-lookup"><span data-stu-id="1c0f6-116">Memory</span></span></p></td>
<td><p><span data-ttu-id="1c0f6-117">32 ギガバイト (GB)</span><span class="sxs-lookup"><span data-stu-id="1c0f6-117">32 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c0f6-118">ディスク</span><span class="sxs-lookup"><span data-stu-id="1c0f6-118">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1c0f6-119">1万 RPM のハードディスクドライブのうち、少なくとも 72 GB の空きディスク領域があるものを8台以上。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-119">8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="1c0f6-120">ディスクのうち 2 台で RAID 1 を使用し、6 台で RAID 10 を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-120">Two of the disks should use RAID 1, and six should use RAID 10.</span></span></p>
<p><span data-ttu-id="1c0f6-121">-や</span><span class="sxs-lookup"><span data-stu-id="1c0f6-121">- OR -</span></span></p></li>
<li><p><span data-ttu-id="1c0f6-122">10,000 RPM の機械的ディスク ドライブ 8 台と同等のパフォーマンスを持つソリッド ステート ドライブ (SSD)</span><span class="sxs-lookup"><span data-stu-id="1c0f6-122">Solid state drives (SSDs) which provide performance similar to 8 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c0f6-123">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="1c0f6-123">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1c0f6-124">1 Gbps 以上のデュアルポート ネットワーク アダプター 1 つ (2 つを推奨。その場合は 1 つの MAC アドレスと 1 つの IP アドレスのチーミングが必要)</span><span class="sxs-lookup"><span data-stu-id="1c0f6-124">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="summary-of-results"></a><span data-ttu-id="1c0f6-125">結果の概要</span><span class="sxs-lookup"><span data-stu-id="1c0f6-125">Summary of Results</span></span>

<span data-ttu-id="1c0f6-126">次の表は、これらの推奨事項を要約したものです。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-126">The following table summarizes these recommendations.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1c0f6-127">サーバーの役割</span><span class="sxs-lookup"><span data-stu-id="1c0f6-127">Server role</span></span></th>
<th><span data-ttu-id="1c0f6-128">サポートされる最大ユーザー数</span><span class="sxs-lookup"><span data-stu-id="1c0f6-128">Maximum number of users supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1c0f6-129">12台のフロントエンドサーバーと1つのバックエンドサーバー、またはバックエンドサーバーのミラー化されたペアのフロントエンドプール。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-129">Front End pool with twelve Front End Servers and one Back End Server or a mirrored pair of Back End Servers.</span></span></p></td>
<td><p><span data-ttu-id="1c0f6-130">8万ユーザーが同時にログインし、50% 複数のプレゼンスポイント (MPOP) が表示されます。これには、非モバイルインスタンスが表示されます。さらに、合計152000エンドポイントのモビリティが有効になっているユーザーの40%。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-130">80,000 unique users simultaneously logged in, plus 50% multiple points of presence (MPOP) representing non-mobile instances, plus 40% of users enabled for Mobility for a total of 152,000 endpoints.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c0f6-131">音声ビデオ会議</span><span class="sxs-lookup"><span data-stu-id="1c0f6-131">A/V Conferencing</span></span></p></td>
<td><p><span data-ttu-id="1c0f6-132">フロントエンドプールによって提供される音声ビデオ会議サービスは、最大会議サイズ250ユーザーを想定し、一度に実行する大規模な会議を1つだけ持つプールの会議をサポートします。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-132">The A/V Conferencing service provided by a Front End pool supports the pool’s conferences assuming a maximum conference size of 250 users, and only one such large conference running at a time.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="1c0f6-133">さらに、大規模な会議をホストするために2台のフロントエンドサーバーを使用する独立したフロントエンドプールを展開することで、250と1000ユーザーの間の大規模な会議をサポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-133">Additionally, you can support large conferences of between 250 and 1000 users by deploying a separate Front End pool with two Front End Servers to host the large conferences.</span></span> <span data-ttu-id="1c0f6-134">詳細については、「 <A href="lync-server-2013-supporting-large-meetings.md">Lync Server 2013 を使用した大規模会議のサポート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-134">For details, see <A href="lync-server-2013-supporting-large-meetings.md">Supporting large meetings using Lync Server 2013</A>.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c0f6-135">1 台のエッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="1c0f6-135">One Edge Server</span></span></p></td>
<td><p><span data-ttu-id="1c0f6-136">12000同時リモートユーザー</span><span class="sxs-lookup"><span data-stu-id="1c0f6-136">12,000 concurrent remote users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c0f6-137">1 台のディレクター</span><span class="sxs-lookup"><span data-stu-id="1c0f6-137">One Director</span></span></p></td>
<td><p><span data-ttu-id="1c0f6-138">12000同時リモートユーザー</span><span class="sxs-lookup"><span data-stu-id="1c0f6-138">12,000 concurrent remote users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c0f6-139">監視およびアーカイブ</span><span class="sxs-lookup"><span data-stu-id="1c0f6-139">Monitoring and Archiving</span></span></p></td>
<td><p><span data-ttu-id="1c0f6-140">Lync Server 2013 では、監視およびアーカイブのフロントエンドサービスが、個別のサーバーの役割ではなく、各フロントエンドサーバーで実行されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-140">In Lync Server 2013, the Monitoring and Archiving front end services now run on each Front End Server, instead of on separate server roles.</span></span></p>
<p><span data-ttu-id="1c0f6-141">監視とアーカイブには、それぞれ独自のデータベースストアが必要です。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-141">Monitoring and Archiving each still require their own database stores.</span></span> <span data-ttu-id="1c0f6-142">Exchange 2013 も実行している場合は、専用の SQL データベースではなく、Exchange にアーカイブデータを保持できます。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-142">If you also run Exchange 2013, you can keep your Archiving data in Exchange, rather than in a dedicated SQL database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c0f6-143">1 台の仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="1c0f6-143">One Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="1c0f6-144">フロントエンドサーバーと併置された仲介サーバーは、プール内のすべてのフロントエンドサーバーで実行され、プール内のユーザーに十分な容量を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-144">Mediation Server collocated with Front End Server runs on every Front End Server in a pool, and should provide enough capacity for the users in the pool.</span></span> <span data-ttu-id="1c0f6-145">スタンドアロンの仲介サーバーの場合は、このトピックで後述する「仲介サーバー」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-145">For stand-alone Mediation Server, see the “Mediation Server” section later in this topic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c0f6-146">1 台の Standard Edition サーバー</span><span class="sxs-lookup"><span data-stu-id="1c0f6-146">One Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="1c0f6-147">Standard Edition サーバーを使用してユーザーをホストする場合は、「 <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">Lync Server 2013 での高可用性と障害復旧の計画</a>」の推奨事項を使用して、常に2台のサーバーを使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-147">We strongly recommend that if you use Standard Edition servers to host users, you always use two servers, paired using the recommendations in <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">Planning for high availability and disaster recovery in Lync Server 2013</a>.</span></span> <span data-ttu-id="1c0f6-148">ペア内の各サーバーは最大2500ユーザーをホストでき、1台のサーバーが障害を発生した場合、残りのサーバーはフェールオーバーシナリオで5000ユーザーをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-148">Each server in the pair can host up to 2,500 users, and if one server fails the remaining server can support 5,000 users in a failover scenario.</span></span></p>
<p><span data-ttu-id="1c0f6-149">展開に大量のオーディオまたはビデオトラフィックが含まれている場合、サーバーあたりのユーザー数が2500を超えると、サーバーのパフォーマンスが低下することがあります。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-149">If your deployment includes a significant amount of audio or video traffic, server performance may suffer with more than 2,500 users per server.</span></span> <span data-ttu-id="1c0f6-150">この場合は、より多くの Standard Edition サーバーを追加するか、Lync Server Enterprise Edition に移行することを検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-150">In this case, you should consider adding more Standard Edition servers or moving to Lync Server Enterprise Edition.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-server"></a><span data-ttu-id="1c0f6-151">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1c0f6-151">Front End Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1c0f6-152">拡張されたプールは、このサーバーの役割ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-152">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="1c0f6-153">フロントエンドプールには、プール内のすべてのサーバーでハイパースレッディングが有効になっており、サーバーハードウェアが[Lync server 2013 のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)の推奨事項を満たしていることを前提として、プールに所属する6660ユーザーごとに1台のフロントエンドサーバーが必要です。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-153">In a Front End pool, you should have one Front End Server for every 6,660 users homed in the pool, assuming that hyper-threading is enabled on all servers in the pool, and that the server hardware meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span> <span data-ttu-id="1c0f6-154">1つのフロントエンドプール内のユーザーの最大数は、ハイパースレッディングがプール内のすべてのサーバーで有効になっていることを前提としています (8万)。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-154">The maximum number of users in one Front End pool is 80,000, assuming that hyper-threading is enabled on all the servers in the pool.</span></span> <span data-ttu-id="1c0f6-155">サイトに 80,000 を超えるユーザーが存在する場合、複数のフロント エンド プールを展開できます。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-155">If you have more than 80,000 users at a site, you can deploy more than one Front End pool.</span></span>

<span data-ttu-id="1c0f6-156">フロント エンド プール内のユーザー数を考慮する際は、このフロント エンド プールに関連付けられているブランチ オフィスの存続可能ブランチ アプライアンスおよび存続可能ブランチ サーバーに所属するユーザーを含めます。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-156">When you account for the number of users in a Front End pool, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with this Front End pool.</span></span>

<span data-ttu-id="1c0f6-157">アクティブなサーバーが使用できなくなると、その接続はプール内にある他のサーバーに自動的に転送されます。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-157">When an active server is unavailable, its connections are transferred automatically to the other servers in the pool.</span></span> <span data-ttu-id="1c0f6-158">たとえば、3万ユーザーと5台のフロントエンドサーバーがある場合、1台のサーバーを使用できない場合は、6000ユーザーの接続を他の4台のサーバーに転送する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-158">For example, if you have 30,000 users and five Front End Servers, then if one server is unavailable, the connections of 6000 users need to be transferred to the other four servers.</span></span> <span data-ttu-id="1c0f6-159">残りの4台のサーバーはそれぞれ7500ユーザーを持ち、推奨されるよりも大きな数です。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-159">The remaining four servers will each have 7500 users, which is a larger number than recommended.</span></span>

<span data-ttu-id="1c0f6-160">その代わりに、3万ユーザーの6台のフロントエンドサーバーを使用していて、その後で使用できなくなった場合は、合計で5000ユーザーが残りの5台のサーバーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-160">If instead you had started with six Front End Servers for your 30,000 users and subsequently one became unavailable, a total of 5000 users will be moved to the remaining five servers.</span></span> <span data-ttu-id="1c0f6-161">これら5台のサーバーはそれぞれ6000ユーザーをホストしますが、これは推奨範囲になっています。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-161">These five servers will each host 6000 users, which is in the recommended range.</span></span>

<span data-ttu-id="1c0f6-162">1 フロント エンド プール内の最大ユーザー数は 80,000 です。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-162">The maximum number of users in a Front End pool is 80,000.</span></span> <span data-ttu-id="1c0f6-163">プール内のフロントエンドサーバーの最大数は12です。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-163">The maximum number of Front End Servers in a pool is 12.</span></span>

<span data-ttu-id="1c0f6-164">8万ユーザーが含まれるフロントエンドプールの場合、通常、 [Lync Server 2013 のユーザーモデル](lync-server-2013-user-models.md)に準拠する展開では、12台のフロントエンドサーバーでパフォーマンスを十分に確保できます。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-164">For a Front End pool with 80,000 users, twelve Front End Servers is sufficient for performance, in typical deployments that follow the [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span> <span data-ttu-id="1c0f6-165">障害復旧フェールオーバーをサポートするように設計されている展開では、2つのペアのフロントエンドプールのそれぞれで最大4万ユーザーをホストすることができます。各プールには、両方のプールのユーザーに対応する十分な数のフロントエンドサーバーがあり、1つのプールに障害が発生する必要があります。になります。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-165">Deployments designed to support disaster recovery failover assume that a maximum of 40,000 users can be hosted in each of two paired Front End pools, in which each pool has enough Front End Servers to accommodate the users in both pools should one pool need to be failed over to the other.</span></span>

<span data-ttu-id="1c0f6-166">特定のフロントエンドプールでサポートされているユーザーの数は、次の理由から、これらの値と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-166">The number of users supported with good performance by a particular Front End pool may differ from these numbers for the following reasons:</span></span>

  - <span data-ttu-id="1c0f6-167">フロントエンドサーバーのハードウェアは、 [Lync server 2013 のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)の推奨事項を満たしていません。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-167">The hardware for your Front End Servers does not meet the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

  - <span data-ttu-id="1c0f6-168">ユーザー モデルよりもかなり多い会議トラフィックの場合など、組織の使用法がユーザー モデルのそれと著しく異なります。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-168">Your organization’s usage differs significantly from the user models, such as significantly more conferencing traffic.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1c0f6-169">Lync Server 2013 では、プレゼンスデータベースは、バックエンドサーバーでホストされていた Lync Server 2010 とは異なり、フロントエンドサーバーでホストされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-169">In Lync Server 2013, the presence databases are now hosted on Front End Servers, unlike in Lync Server 2010 where they were hosted on the Back End Server.</span></span> <span data-ttu-id="1c0f6-170">これは、フロントエンドサーバーによってホストされているユーザーの数に関係なく、このセクションおよび<A href="lync-server-2013-server-hardware-platforms.md">Lync server 2013 のサーバーハードウェアプラットフォーム</A>で前述した推奨事項から、フロントエンドサーバーのディスクのパフォーマンスと容量を侵害してはならないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-170">This means that the disk performance and capacity of your Front End Servers should not be compromised from the recommendations listed earlier in this section and in <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>, regardless of the number of users hosted by your Front End Servers.</span></span>



</div>

<span data-ttu-id="1c0f6-171">次の表に、 [Lync Server 2013 のユーザーモデル](lync-server-2013-user-models.md)で定義されているように、ユーザーモデルを使用して IM とプレゼンスの平均帯域幅を示します。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-171">The following table shows the average bandwidth for IM and presence, given the user model, as defined in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1c0f6-172">ユーザー単位の平均帯域幅</span><span class="sxs-lookup"><span data-stu-id="1c0f6-172">Average bandwidth per user</span></span></th>
<th><span data-ttu-id="1c0f6-173">6660ユーザーのフロントエンドサーバーごとの帯域幅要件</span><span class="sxs-lookup"><span data-stu-id="1c0f6-173">Bandwidth requirements per Front End Server with 6,660 users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1c0f6-174">1.3 Kpbs</span><span class="sxs-lookup"><span data-stu-id="1c0f6-174">1.3 Kpbs</span></span></p></td>
<td><p><span data-ttu-id="1c0f6-175">13 Mbps</span><span class="sxs-lookup"><span data-stu-id="1c0f6-175">13 Mbps</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="1c0f6-176">フロントエンドサーバーで併置された音声ビデオ会議と仲介サーバーの機能のメディアパフォーマンスを向上させるには、フロントエンドサーバーのネットワークアダプターで受信側の拡大/縮小 (RSS) を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-176">To improve the media performance of the co-located A/V Conferencing and Mediation Server functionality on your Front End Servers, you should enable receive-side scaling (RSS) on the network adapters on your Front End Servers.</span></span> <span data-ttu-id="1c0f6-177">RSS は、着信パケットがサーバーの複数のプロセッサによって平行して処理されるのを可能にします。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-177">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="1c0f6-178">詳細については、「」の「Windows Server 2008 の受信側<A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A>スケーリングの拡張機能」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-178">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="1c0f6-179">RSS を有効にする方法の詳細については、ネットワークアダプターのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-179">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="conferencing-maximums"></a><span data-ttu-id="1c0f6-180">最大会議数</span><span class="sxs-lookup"><span data-stu-id="1c0f6-180">Conferencing Maximums</span></span>

<span data-ttu-id="1c0f6-181">ユーザーモデルでは、プール内のユーザーの5% が一度に会議に参加している可能性があるため、8万のユーザーのプールは、一度に1人の電話会議に約4000ユーザーを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-181">Given the user model that 5% of users in a pool may be in a conference at any one time, a pool of 80,000 users could have about 4,000 users in conferences at one time.</span></span> <span data-ttu-id="1c0f6-182">これらの電話会議は、メディアが混在していることが予想されます (一部の IM のみ、一部の IM、オーディオ/ビデオなど)、参加者の数です。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-182">These conferences are expected to be a mix of media (some IM-only, some IM with audio, some audio/video, for example) and number of participants.</span></span> <span data-ttu-id="1c0f6-183">許可されている実際の電話会議数に対するハードリミットはありません。実際の使用量によって実際のパフォーマンスが決まります。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-183">There is no hard limit for the actual number of conferences allowed, and actual usage determines the actual performance.</span></span> <span data-ttu-id="1c0f6-184">たとえば、組織にユーザーモデルで想定されているよりも多くの混在モードの会議がある場合は、このドキュメントの推奨事項より多くのフロントエンドサーバーまたは音声ビデオ会議サーバーを展開する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-184">For example, if your organization has many more mixed-mode conferences than are assumed in the user model, you might need to deploy more Front End Servers or A/V Conferencing Servers than the recommendations in this document.</span></span> <span data-ttu-id="1c0f6-185">ユーザーモデルの前提条件の詳細については、「 [Lync Server 2013 のユーザーモデル](lync-server-2013-user-models.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-185">For details about the assumptions in the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<span data-ttu-id="1c0f6-186">通常の Lync Server 2013 フロントエンドプールでホストされている、サポートされている会議の最大サイズは、ユーザーが250参加者であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-186">The maximum supported conference size hosted by a regular Lync Server 2013 Front End pool which also hosts users is 250 participants.</span></span> <span data-ttu-id="1c0f6-187">250ユーザーの会議が発生している間も、プールは引き続き他の会議をサポートしています。これには、プールユーザーの合計5% が同時会議に含まれます。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-187">While a 250-user conference is happening, the pool still supports other conferences as well, such that a total of 5% of pool users are in concurrent conferences.</span></span> <span data-ttu-id="1c0f6-188">たとえば、12台のフロントエンドサーバーと8万ユーザーのプールでは、250ユーザーの会議が発生している間、Lync Server は、小規模の電話会議に参加している他のユーザーの3750をサポートします。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-188">For example, in a pool of twelve Front End Servers and 80,000 users, while the 250-user conference is happening, Lync Server supports 3,750 other users participating in smaller conferences.</span></span>

<span data-ttu-id="1c0f6-189">Lync Server は、フロントエンドプールまたは Standard Edition サーバーに所属しているユーザー数に関係なく、250ユーザーの会議をホストしている同じプールまたはサーバー上の小さな会議に参加する、少なくとも125の他のユーザーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-189">Regardless of the number of users homed on the Front End pool or Standard Edition server, Lync Server supports a minimum of 125 other users participating in smaller conferences on the same pool or server which is hosting a 250-user conference.</span></span>

<span data-ttu-id="1c0f6-190">250ユーザーと1000ユーザーの間で会議を有効にするには、これらの会議をホストするためだけに別のフロントエンドプールをセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-190">To enable conferences with between 250 and 1000 users, you can set up a separate Front End pool just to host those conferences.</span></span> <span data-ttu-id="1c0f6-191">このフロントエンドプールでは、ユーザーはホストされません。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-191">This Front End pool will not host any users.</span></span> <span data-ttu-id="1c0f6-192">詳細については、「 [Lync Server 2013 を使用した大規模会議のサポート](lync-server-2013-supporting-large-meetings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-192">For details, see [Supporting large meetings using Lync Server 2013](lync-server-2013-supporting-large-meetings.md).</span></span>

<span data-ttu-id="1c0f6-193">ユーザーモデルで想定されているよりも多くの混合モード会議が組織にある場合は、このドキュメントの推奨事項 (上限は 12 FEs) より多くのフロントエンドサーバーを展開する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-193">If your organization has many more mixed-mode conferences than are assumed in the user model, you might need to deploy more Front End Servers than the recommendations in this document (up to a limit of 12 FEs).</span></span> <span data-ttu-id="1c0f6-194">ユーザーモデルの前提条件の詳細については、「 [Lync Server 2013 のユーザーモデル](lync-server-2013-user-models.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-194">For details about the assumptions in the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

</div>

<div>

## <a name="edge-server"></a><span data-ttu-id="1c0f6-195">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="1c0f6-195">Edge Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1c0f6-196">拡張されたプールは、このサーバーの役割ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-196">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="1c0f6-197">サイトに同時にアクセスする12000リモートユーザーごとに1つのエッジサーバーを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-197">You should deploy one Edge Server for every 12,000 remote users who will access a site concurrently.</span></span> <span data-ttu-id="1c0f6-198">高可用性を実現するために 2 つ以上のエッジ サーバーを用意することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-198">At a minimum we recommend two Edge Servers for high availability.</span></span> <span data-ttu-id="1c0f6-199">これらの推奨事項は、エッジサーバーのハードウェアが[Lync server 2013 のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)の推奨事項を満たしていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-199">These recommendations assume that the hardware for your Edge Servers meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="1c0f6-200">エッジ サーバーのユーザー数を考慮する際は、このサイトのフロント エンド プールに関連付けられているブランチ オフィスの存続可能ブランチ アプライアンスおよび存続可能ブランチ サーバーに所属するユーザーを含めます。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-200">When you account for the number of users for the Edge Servers, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with a Front End pool at this site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1c0f6-201">エッジ サーバーの音声ビデオ会議エッジ サービスのパフォーマンスを改善するには、エッジ サーバーのネットワーク アダプターの Receive-side Scaling (RSS) を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-201">To improve the performance of the A/V Conferencing Edge service on your Edge Servers, you should enable receive-side scaling (RSS) on the network adapters on your Edge Servers.</span></span> <span data-ttu-id="1c0f6-202">RSS は、着信パケットがサーバーの複数のプロセッサによって平行して処理されるのを可能にします。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-202">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="1c0f6-203">詳細については、「」の「Windows Server 2008 の受信側<A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A>スケーリングの拡張機能」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-203">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="1c0f6-204">RSS を有効にする方法の詳細については、ネットワークアダプターのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-204">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="director"></a><span data-ttu-id="1c0f6-205">ディレクター</span><span class="sxs-lookup"><span data-stu-id="1c0f6-205">Director</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1c0f6-206">拡張されたプールは、このサーバーの役割ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-206">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="1c0f6-207">ディレクターサーバーの役割を展開する場合は、サイトに同時にアクセスするすべての12000リモートユーザーに対して1つのディレクターを展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-207">If you deploy the Director server role we recommend that you deploy one Director for every 12,000 remote users who will access a site concurrently.</span></span> <span data-ttu-id="1c0f6-208">高可用性を実現するために 2 つ以上のディレクターを用意することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-208">At a minimum we recommend two Directors for high availability.</span></span> <span data-ttu-id="1c0f6-209">これらの推奨事項は、エッジサーバーのハードウェアが[Lync server 2013 のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)の推奨事項を満たしていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-209">These recommendations assume that the hardware for your Edge Servers meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="1c0f6-210">ディレクターのユーザー数を考慮する際は、このサイトのフロント エンド プールに関連付けられているブランチ オフィスの存続可能ブランチ アプライアンスおよび存続可能ブランチ サーバーに所属するユーザーを含めます。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-210">When you account for the number of users for the Directors, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with a Front End pool at this site.</span></span>

</div>

<div>

## <a name="mediation-server"></a><span data-ttu-id="1c0f6-211">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="1c0f6-211">Mediation Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1c0f6-212">拡張されたプールは、このサーバーの役割ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-212">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="1c0f6-213">仲介サーバーをフロントエンドサーバーと併置する場合、仲介サーバーはプール内のすべてのフロントエンドサーバー上で実行され、プール内のユーザーに十分な容量を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-213">If you collocate Mediation Server with Front End Server, Mediation Server runs on every Front End Server in the pool, and should provide enough capacity for the users in the pool.</span></span>

<span data-ttu-id="1c0f6-214">スタンドアロンの仲介サーバープールを展開する場合、展開する仲介サーバーの数は、仲介サーバーに使用されるハードウェア、使用する VoIP ユーザーの数、各仲介サーバープールのゲートウェイピアの数など、さまざまな要因によって異なります。制御、それらのゲートウェイを通過する時間内のトラフィック、および仲介サーバーをバイパスするメディアを使用した通話の割合。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-214">If you deploy a stand-alone Mediation Server pool, then how many Mediation Servers to deploy depends on many factors, including the hardware used for Mediation Server, the number of VoIP users you have, the number of gateway peers that each Mediation Server pool controls, the busy hour traffic through those gateways, and the percentage of calls with media that bypasses the Mediation Server.</span></span>

<span data-ttu-id="1c0f6-215">次の表は、仲介サーバーのハードウェアが[Lync server 2013 のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)の要件を満たしており、ハイパースレッディングが有効になっている場合に、仲介サーバーが処理できる同時呼び出し数に関するガイドラインを提供します。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-215">The following tables provide a guideline for how many concurrent calls a Mediation Server can handle, assuming that the hardware for the Mediation Servers meets the requirements in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) and that hyper-threading is enabled.</span></span> <span data-ttu-id="1c0f6-216">仲介サーバーのスケーラビリティの詳細については、「lync server [2013 の音声使用率とトラフィックの見積もり](lync-server-2013-estimating-voice-usage-and-traffic.md)」および「 [lync Server 2013 の仲介サーバーの展開ガイドライン](lync-server-2013-deployment-guidelines-for-mediation-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-216">For details about Mediation Server scalability, see [Estimating voice usage and traffic for Lync Server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) and [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span></span>

<span data-ttu-id="1c0f6-217">次の表はすべて、 [Lync Server 2013 のユーザーモデル](lync-server-2013-user-models.md)で要約された使用法を前提としています。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-217">All the following tables assume usage as summarized in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

### <a name="stand-alone-mediation-server-capacity-70-internal-users-30-external-users-with-non-bypass-call-capacity-media-transcoding-performed-by-mediation-server"></a><span data-ttu-id="1c0f6-218">スタンドアロン仲介サーバーの容量: 70% 内部ユーザー、30% の外部ユーザー (仲介サーバーによって実行されるメディアトランスコーディング)</span><span class="sxs-lookup"><span data-stu-id="1c0f6-218">Stand-alone Mediation Server Capacity: 70% Internal Users, 30% External users with non-bypass call capacity (media transcoding performed by Mediation Server)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1c0f6-219">サーバー ハードウェア</span><span class="sxs-lookup"><span data-stu-id="1c0f6-219">Server hardware</span></span></th>
<th><span data-ttu-id="1c0f6-220">最大通話数</span><span class="sxs-lookup"><span data-stu-id="1c0f6-220">Maximum number of calls</span></span></th>
<th><span data-ttu-id="1c0f6-221">T1 回線の最大数</span><span class="sxs-lookup"><span data-stu-id="1c0f6-221">Maximum number of T1 lines</span></span></th>
<th><span data-ttu-id="1c0f6-222">E1 回線の最大数</span><span class="sxs-lookup"><span data-stu-id="1c0f6-222">Maximum number of E1 lines</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1c0f6-223">デュアルプロセッサ、16コア、2.26 GHz ハイパースレッディング CPU (<strong>ハイパースレッディング無効</strong>)、32 GB メモリ、および1つのデュアルポートネットワークアダプターカード。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-223">Dual processor, hex core, 2.26 GHz hyper-threaded CPU <strong>with hyper-threading disabled</strong>, with 32 GB memory and one dual-port network adapter card.</span></span></p></td>
<td><p><span data-ttu-id="1c0f6-224">1100</span><span class="sxs-lookup"><span data-stu-id="1c0f6-224">1100</span></span></p></td>
<td><p><span data-ttu-id="1c0f6-225">46</span><span class="sxs-lookup"><span data-stu-id="1c0f6-225">46</span></span></p></td>
<td><p><span data-ttu-id="1c0f6-226">35</span><span class="sxs-lookup"><span data-stu-id="1c0f6-226">35</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c0f6-227">デュアルプロセッサ、16コア、2.26 GHz ハイパースレッディング CPU (32 GB メモリと1つのデュアルポートネットワークアダプターカードを使用)。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-227">Dual processor, hex core, 2.26 GHz hyper-threaded CPU, with 32 GB memory and one dual-port network adapter card.</span></span></p></td>
<td><p><span data-ttu-id="1c0f6-228">1500</span><span class="sxs-lookup"><span data-stu-id="1c0f6-228">1500</span></span></p></td>
<td><p><span data-ttu-id="1c0f6-229">63</span><span class="sxs-lookup"><span data-stu-id="1c0f6-229">63</span></span></p></td>
<td><p><span data-ttu-id="1c0f6-230">47</span><span class="sxs-lookup"><span data-stu-id="1c0f6-230">47</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="1c0f6-231">パフォーマンス テストにはメモリが 32 GB のサーバーを使用しましたが、スタンドアロンの仲介サーバーにはメモリが 16 GB のサーバーがサポートされており、その条件のサーバーでもこの表に示されるパフォーマンスを十分実現できます。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-231">Although servers with 32 GB of memory were used for performance testing, servers with 16 GB of memory are supported for stand-alone Mediation Server, and are sufficient to provide the performance shown in this table.</span></span>



</div>

### <a name="mediation-server-capacity-mediation-server-collocated-with-front-end-server-70-internal-users-30-external-users-non-bypass-call-capacity-media-processing-performed-by-mediation-server"></a><span data-ttu-id="1c0f6-232">仲介サーバーの処理能力 (フロントエンドサーバーと併置された仲介サーバー) 70% 内部ユーザー、30% の外部ユーザー、非バイパス通話の容量 (仲介サーバーによって実行されるメディア処理)</span><span class="sxs-lookup"><span data-stu-id="1c0f6-232">Mediation Server Capacity (Mediation Server Collocated with Front End Server) 70% Internal Users, 30% External Users, Non-Bypass Call Capacity (Media Processing Performed by Mediation Server)</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1c0f6-233">サーバー ハードウェア</span><span class="sxs-lookup"><span data-stu-id="1c0f6-233">Server hardware</span></span></th>
<th><span data-ttu-id="1c0f6-234">最大通話数</span><span class="sxs-lookup"><span data-stu-id="1c0f6-234">Maximum number of calls</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1c0f6-235">デュアルプロセッサ、16進コア、2.26 GHz ハイパースレッディング CPU (32 GB メモリと 2 GB ネットワークアダプターカード)。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-235">Dual processor, hex core, 2.26 GHz hyper-threaded CPU, with 32 GB memory and 2 1GB network adapter cards.</span></span></p></td>
<td><p><span data-ttu-id="1c0f6-236">150</span><span class="sxs-lookup"><span data-stu-id="1c0f6-236">150</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="1c0f6-237">この数は、フロントエンドサーバーが、音声呼び出しに必要なトランスコーディングだけでなく、それに所属する6600ユーザーの他の機能や機能を処理する必要があるため、スタンドアロンの仲介サーバーの数よりもはるかに小さくなります。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-237">This number is much smaller than the numbers for the stand-alone Mediation Server because the Front End Server has to handle other features and functions for the 6600 users homed on it, in addition to the transcoding needed for voice calls.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="1c0f6-238">仲介サーバーのパフォーマンスを向上させるには、仲介サーバーのネットワークアダプターで受信側の拡大/縮小 (RSS) を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-238">To improve the performance of the Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on your Mediation Servers.</span></span> <span data-ttu-id="1c0f6-239">RSS は、着信パケットがサーバーの複数のプロセッサによって平行して処理されるのを可能にします。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-239">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="1c0f6-240">詳細については、「」の「Windows Server 2008 の受信側<A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A>スケーリングの拡張機能」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-240">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="1c0f6-241">RSS を有効にする方法の詳細については、ネットワークアダプターのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-241">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="back-end-server"></a><span data-ttu-id="1c0f6-242">バック エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="1c0f6-242">Back End Server</span></span>

<span data-ttu-id="1c0f6-243">Lync Server 2013 では、プレゼンスデータベースはバックエンドサーバーではなくフロントエンドサーバーに配置されます。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-243">In Lync Server 2013, the presence databases are located on the Front End Servers instead of the Back End Server.</span></span> <span data-ttu-id="1c0f6-244">これにより、Lync Server 2013 のバックエンドサーバーごとに、フロントエンドサーバーのハードウェア要件と同等の要件が大幅に簡略化されました。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-244">This has resulted in a much simpler requirement for each Back End Server in Lync Server 2013, equivalent to the hardware requirement for the Front End Server.</span></span> <span data-ttu-id="1c0f6-245">これを Lync Server 2010 と比較します。これは、バックエンドサーバーが25台のディスクを使用した、より高いグレードのサーバーでなければならないということです。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-245">Contrast this to Lync Server 2010, where the Back End Server was required to be a much higher grade server with 25 disks.</span></span> <span data-ttu-id="1c0f6-246">ただし、バックエンドサーバーのワークロードについては、このセクションで前述したハードウェアの推奨事項や、 [Lync server 2013 のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)の要件を満たすことができない場合があります。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-246">However, the workload of Back End Servers is still such that you should not fail to meet the hardware recommendations listed earlier in this section and in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="1c0f6-247">バックエンドサーバーの高可用性を実現するには、サーバーミラーリングを展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-247">To provide high availability of your Back End Server, we recommend deploying server mirroring.</span></span> <span data-ttu-id="1c0f6-248">詳細については、「 [Lync server 2013 のバックエンドサーバーの高可用性](lync-server-2013-back-end-server-high-availability.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-248">For more information, see [Back End Server high availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span></span>

</div>

<div>

## <a name="monitoring-and-archiving"></a><span data-ttu-id="1c0f6-249">監視およびアーカイブ</span><span class="sxs-lookup"><span data-stu-id="1c0f6-249">Monitoring and Archiving</span></span>

<span data-ttu-id="1c0f6-250">Lync Server 2013 では、監視またはアーカイブを展開する場合、これらのサービスのフロントエンド機能は、個別のサーバーの役割ではなくフロントエンドサーバーで実行されます。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-250">In Lync Server 2013, if you deploy Monitoring or Archiving, the front end functionality of these services runs on the Front End Servers, instead of on separate server roles.</span></span> <span data-ttu-id="1c0f6-251">監視とアーカイブは、バックエンドストアから切り離された独自のデータベースストアを使用します。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-251">Monitoring and Archiving each still use their own database store, separate from the Back End store.</span></span> <span data-ttu-id="1c0f6-252">または、Exchange 2013 を展開している場合は、専用の SQL ストアではなく、インスタントメッセージのアーカイブデータを Exchange に格納できます。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-252">Alternatively, if you have Exchange 2013 deployed, you can store instant message Archiving data in Exchange instead of in a dedicated SQL store.</span></span>

<span data-ttu-id="1c0f6-253">次の表は、データを監視およびアーカイブするために、ユーザーごとに1日あたりに必要なデータベース記憶域のおおよその量を示しています。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-253">The following table indicates approximately how much database storage is required per user per day for Monitoring and Archiving data.</span></span>


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
<td><p><span data-ttu-id="1c0f6-254"><strong>CDR (監視)</strong></span><span class="sxs-lookup"><span data-stu-id="1c0f6-254"><strong>CDR (Monitoring)</strong></span></span></p></td>
<td><p><span data-ttu-id="1c0f6-255"><strong>QoE (監視)</strong></span><span class="sxs-lookup"><span data-stu-id="1c0f6-255"><strong>QoE (Monitoring)</strong></span></span></p></td>
<td><p><span data-ttu-id="1c0f6-256"><strong>アーカイブ</strong></span><span class="sxs-lookup"><span data-stu-id="1c0f6-256"><strong>Archiving</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c0f6-257">ユーザーごとに1日あたり必要なディスク領域</span><span class="sxs-lookup"><span data-stu-id="1c0f6-257">Disk space required per user per day</span></span></p></td>
<td><p><span data-ttu-id="1c0f6-258">49 KB</span><span class="sxs-lookup"><span data-stu-id="1c0f6-258">49 KB</span></span></p></td>
<td><p><span data-ttu-id="1c0f6-259">28 KB</span><span class="sxs-lookup"><span data-stu-id="1c0f6-259">28 KB</span></span></p></td>
<td><p><span data-ttu-id="1c0f6-260">57 KB</span><span class="sxs-lookup"><span data-stu-id="1c0f6-260">57 KB</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1c0f6-261">Microsoft では、データベースサーバーのパフォーマンステスト中に監視およびアーカイブするために、次の表に示すハードウェアを使用しています。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-261">Microsoft used the hardware in the following table for the database server for Monitoring and Archiving during its performance testing.</span></span> <span data-ttu-id="1c0f6-262">このテストでは、2つのフロントエンドプールのデータが収集され、それぞれに8万のユーザーが含まれていました。</span><span class="sxs-lookup"><span data-stu-id="1c0f6-262">The testing collected the data of two Front End pools, each of which contained 80,000 users.</span></span>

### <a name="hardware-used-in-monitoring-and-archiving-performance-testing"></a><span data-ttu-id="1c0f6-263">監視およびアーカイブのパフォーマンステストで使用されるハードウェア</span><span class="sxs-lookup"><span data-stu-id="1c0f6-263">Hardware Used in Monitoring and Archiving Performance Testing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1c0f6-264">ハードウェア コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1c0f6-264">Hardware component</span></span></th>
<th><span data-ttu-id="1c0f6-265">推奨</span><span class="sxs-lookup"><span data-stu-id="1c0f6-265">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1c0f6-266">CPU</span><span class="sxs-lookup"><span data-stu-id="1c0f6-266">CPU</span></span></p></td>
<td><p><span data-ttu-id="1c0f6-267">64 ビット デュアル プロセッサ、6 コア、2.26 GHz 以上</span><span class="sxs-lookup"><span data-stu-id="1c0f6-267">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c0f6-268">メモリ</span><span class="sxs-lookup"><span data-stu-id="1c0f6-268">Memory</span></span></p></td>
<td><p><span data-ttu-id="1c0f6-269">48ギガバイト (GB)</span><span class="sxs-lookup"><span data-stu-id="1c0f6-269">48 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c0f6-270">ディスク</span><span class="sxs-lookup"><span data-stu-id="1c0f6-270">Disk</span></span></p></td>
<td><p><span data-ttu-id="1c0f6-271">25 1万 RPM のハードディスクドライブ、各ディスク上の 300 GB、次の構成</span><span class="sxs-lookup"><span data-stu-id="1c0f6-271">25 10,000-RPM hard disk drives with 300 GB on each disk, with the following configuration</span></span></p>
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
<td><p><span data-ttu-id="1c0f6-272"><strong>Drive</strong></span><span class="sxs-lookup"><span data-stu-id="1c0f6-272"><strong>Drive</strong></span></span></p></td>
<td><p><span data-ttu-id="1c0f6-273"><strong>RAID 構成</strong></span><span class="sxs-lookup"><span data-stu-id="1c0f6-273"><strong>RAID Configuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1c0f6-274"><strong>ディスク数</strong></span><span class="sxs-lookup"><span data-stu-id="1c0f6-274"><strong>Number of disks</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c0f6-275">CDR、QoE、およびアーカイブデータベースのデータファイル、1台のドライブ</span><span class="sxs-lookup"><span data-stu-id="1c0f6-275">CDR, QoE, and Archiving database data files, on a single drive</span></span></p></td>
<td><p><span data-ttu-id="1c0f6-276">1 + 0</span><span class="sxs-lookup"><span data-stu-id="1c0f6-276">1+0</span></span></p></td>
<td><p><span data-ttu-id="1c0f6-277">16 </span><span class="sxs-lookup"><span data-stu-id="1c0f6-277">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c0f6-278">CDR データベースのログ ファイル</span><span class="sxs-lookup"><span data-stu-id="1c0f6-278">CDR database log file</span></span></p></td>
<td><p><span data-ttu-id="1c0f6-279">1-d</span><span class="sxs-lookup"><span data-stu-id="1c0f6-279">1</span></span></p></td>
<td><p><span data-ttu-id="1c0f6-280">pbm-2</span><span class="sxs-lookup"><span data-stu-id="1c0f6-280">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c0f6-281">QoE データベースのログ ファイル</span><span class="sxs-lookup"><span data-stu-id="1c0f6-281">QoE database log file</span></span></p></td>
<td><p><span data-ttu-id="1c0f6-282">1-d</span><span class="sxs-lookup"><span data-stu-id="1c0f6-282">1</span></span></p></td>
<td><p><span data-ttu-id="1c0f6-283">pbm-2</span><span class="sxs-lookup"><span data-stu-id="1c0f6-283">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c0f6-284">アーカイブデータベースのログファイル</span><span class="sxs-lookup"><span data-stu-id="1c0f6-284">Archiving database log file</span></span></p></td>
<td><p><span data-ttu-id="1c0f6-285">1-d</span><span class="sxs-lookup"><span data-stu-id="1c0f6-285">1</span></span></p></td>
<td><p><span data-ttu-id="1c0f6-286">pbm-2</span><span class="sxs-lookup"><span data-stu-id="1c0f6-286">2</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c0f6-287">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="1c0f6-287">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1c0f6-288">1 Gbps 以上のデュアルポート ネットワーク アダプター 1 つ (2 つを推奨。その場合は 1 つの MAC アドレスと 1 つの IP アドレスのチーミングが必要)</span><span class="sxs-lookup"><span data-stu-id="1c0f6-288">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1c0f6-289">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1c0f6-289">In This Section</span></span>

  - [<span data-ttu-id="1c0f6-290">Lync Server 2013 の音声の使用状況とトラフィックの予測</span><span class="sxs-lookup"><span data-stu-id="1c0f6-290">Estimating voice usage and traffic for Lync Server 2013</span></span>](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [<span data-ttu-id="1c0f6-291">Lync Server 2013 の仲介サーバーの展開ガイドライン</span><span class="sxs-lookup"><span data-stu-id="1c0f6-291">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

