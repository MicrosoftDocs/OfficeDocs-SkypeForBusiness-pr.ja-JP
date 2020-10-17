---
title: 'Lync Server 2013: フロントエンドサーバー、インスタントメッセージング、およびプレゼンスのトポロジとコンポーネント'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies and components for Front End Servers, instant messaging, and presence
ms:assetid: f08ce7a1-d14e-4a54-9771-a82c870658bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412996(v=OCS.15)
ms:contentKeyID: 48185763
ms.date: 10/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 103d03920df57023ae7dbb953beb0c426d0a43df
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503754"
---
# <a name="topologies-and-components-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="84ae3-102">Lync Server 2013 でのフロントエンドサーバー、インスタントメッセージング、およびプレゼンスのトポロジとコンポーネント</span><span class="sxs-lookup"><span data-stu-id="84ae3-102">Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84ae3-103">_**トピックの最終更新日:** 2014-10-24_</span><span class="sxs-lookup"><span data-stu-id="84ae3-103">_**Topic Last Modified:** 2014-10-24_</span></span>

<span data-ttu-id="84ae3-104">インスタントメッセージング (IM) とプレゼンスに必要なコンポーネントは、次のものだけです。</span><span class="sxs-lookup"><span data-stu-id="84ae3-104">The only components required for instant messaging (IM) and presence are:</span></span>

  - <span data-ttu-id="84ae3-105">組織のフロントエンドサーバーまたは Standard Edition サーバー。</span><span class="sxs-lookup"><span data-stu-id="84ae3-105">Your organization’s Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="84ae3-106">IM とプレゼンスの機能は、これらのサーバー上で常に有効になります。</span><span class="sxs-lookup"><span data-stu-id="84ae3-106">IM and presence capabilities are always enabled on these servers.</span></span>

  - <span data-ttu-id="84ae3-107">エンタープライズエディションのフロントエンドプールを使用している場合は、ロードバランサー。</span><span class="sxs-lookup"><span data-stu-id="84ae3-107">A load balancer, if you have an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="84ae3-108">詳細については、「 [Lync Server 2013 の負荷分散の要件](lync-server-2013-load-balancing-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84ae3-108">For more information, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

<div>

## <a name="planning-for-the-deployment-of-front-end-pools"></a><span data-ttu-id="84ae3-109">フロントエンドプールの展開の計画</span><span class="sxs-lookup"><span data-stu-id="84ae3-109">Planning for the Deployment of Front End Pools</span></span>

<span data-ttu-id="84ae3-110">Lync Server 2013 では、フロントエンドプールのアーキテクチャが変更され、これらの変更によってフロントエンドプールを計画および管理する方法が変わります。</span><span class="sxs-lookup"><span data-stu-id="84ae3-110">In Lync Server 2013, Front End pool architecture has changed, and these changes affect how you should plan and maintain your Front End pools.</span></span>

<span data-ttu-id="84ae3-111">すべての Enterprise Edition フロントエンドプールに、少なくとも3台のフロントエンドサーバーが含まれるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="84ae3-111">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers.</span></span> <span data-ttu-id="84ae3-112">Lync Server では、フロントエンドプールのアーキテクチャは分散システムモデルを使用しており、各ユーザーのデータはプール内の3つのフロントエンドサーバー上に保持されます。</span><span class="sxs-lookup"><span data-stu-id="84ae3-112">In Lync Server, the architecture of Front End pools uses a distributed systems model, with each user’s data kept on three Front End servers in the pool.</span></span> <span data-ttu-id="84ae3-113">この新しいアーキテクチャの詳細については、「 [Lync Server 2013 のトポロジの変更](lync-server-2013-topology-changes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84ae3-113">For more information about this new architecture, see [Topology changes in Lync Server 2013](lync-server-2013-topology-changes.md).</span></span>

<span data-ttu-id="84ae3-114">3つの Enterprise Edition フロントエンドサーバーを展開せず、障害復旧を必要とする場合は、Lync Server Standard Edition を使用して、バックアップ関係がペアになった2つのプールを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="84ae3-114">If you do not want to deploy three Enterprise Edition Front End Servers and want disaster recovery, we recommend you use Lync Server Standard Edition and create two pools with a paired backup relationship.</span></span> <span data-ttu-id="84ae3-115">これにより、2台のサーバーのみの障害復旧ソリューションが提供されます。</span><span class="sxs-lookup"><span data-stu-id="84ae3-115">This will provide a disaster recovery solution with only two servers.</span></span> <span data-ttu-id="84ae3-116">高可用性と障害復旧のトポロジおよび機能の詳細については、「 [Lync Server 2013 での高可用性と障害復旧の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84ae3-116">For more information, on high availability and disaster recovery topologies and features, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

</div>

<div>

## <a name="planning-for-the-management-of-front-end-pools"></a><span data-ttu-id="84ae3-117">フロントエンドプールの管理の計画</span><span class="sxs-lookup"><span data-stu-id="84ae3-117">Planning for the Management of Front End Pools</span></span>

<span data-ttu-id="84ae3-118">フロントエンドプールの場合は、このセクションのガイドラインに従ってください。</span><span class="sxs-lookup"><span data-stu-id="84ae3-118">For Front End pools, follow the guidelines in this section.</span></span>

<div>

## <a name="ensuring-that-pools-are-functional"></a><span data-ttu-id="84ae3-119">プールが機能していることを確認する</span><span class="sxs-lookup"><span data-stu-id="84ae3-119">Ensuring That Pools are Functional</span></span>

<span data-ttu-id="84ae3-120">フロントエンドプール用の新しい分散モデルでは、プールが機能するためには特定の数のプールのサーバーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="84ae3-120">With the new distributed model for Front End pools, certain numbers of a pool’s servers must be running for the pool to function.</span></span> <span data-ttu-id="84ae3-121">プールには2つの損失モードがあります。</span><span class="sxs-lookup"><span data-stu-id="84ae3-121">There are two loss modes for a pool</span></span>

  - <span data-ttu-id="84ae3-122">特定のルーティンググループに十分な数のレプリカサーバーがないことによって発生した、ルーティンググループレベルのクォーラム損失。</span><span class="sxs-lookup"><span data-stu-id="84ae3-122">Routing Group Level quorum loss, caused by not enough replica servers for a particular routing group.</span></span> <span data-ttu-id="84ae3-123">ルーティンググループとは、プールに所属する一連のユーザーの集合です。</span><span class="sxs-lookup"><span data-stu-id="84ae3-123">A routing group is an aggregation of a set of users homed in the pool.</span></span> <span data-ttu-id="84ae3-124">各ルーティンググループには、プールに3つのレプリカがあります。1つはプライマリ、2つはセカンダリです。</span><span class="sxs-lookup"><span data-stu-id="84ae3-124">Each routing group has three replicas in the pool: one primary and two secondaries.</span></span>

  - <span data-ttu-id="84ae3-125">プールレベルのクォーラム損失。プール内で十分な数のシードサーバーが実行されていない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="84ae3-125">Pool Level quorum loss, caused when not enough seed servers are running in the pool.</span></span>

<div>

## <a name="routing-group-level-quorum-loss"></a><span data-ttu-id="84ae3-126">ルーティンググループレベルのクォーラム損失</span><span class="sxs-lookup"><span data-stu-id="84ae3-126">Routing Group Level quorum loss</span></span>

<span data-ttu-id="84ae3-127">新しいフロントエンドプールを初めて起動するときは、次の表に示すように、サーバーの85% が稼働していることが重要です。</span><span class="sxs-lookup"><span data-stu-id="84ae3-127">The first time you start a new Front End pool, it is essential that 85% of the servers are up and running, as shown in the following table.</span></span> <span data-ttu-id="84ae3-128">実行されているサーバーの数が少ない場合、サービスが開始状態になり、プールが開始されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="84ae3-128">If fewer servers are running, the services might be stuck in the starting state and the pool might not start.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="84ae3-129">プール内のサーバーの合計数</span><span class="sxs-lookup"><span data-stu-id="84ae3-129">Total number of servers in the pool</span></span></th>
<th><span data-ttu-id="84ae3-130">プールを初めて起動するために実行する必要があるサーバーの数</span><span class="sxs-lookup"><span data-stu-id="84ae3-130">Number of servers that must be running for the pool to be started the first time</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84ae3-131">pbm-2</span><span class="sxs-lookup"><span data-stu-id="84ae3-131">2</span></span></p></td>
<td><p><span data-ttu-id="84ae3-132">1-d</span><span class="sxs-lookup"><span data-stu-id="84ae3-132">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ae3-133">1/3</span><span class="sxs-lookup"><span data-stu-id="84ae3-133">3</span></span></p></td>
<td><p><span data-ttu-id="84ae3-134">1/3</span><span class="sxs-lookup"><span data-stu-id="84ae3-134">3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ae3-135">4 </span><span class="sxs-lookup"><span data-stu-id="84ae3-135">4</span></span></p></td>
<td><p><span data-ttu-id="84ae3-136">1/3</span><span class="sxs-lookup"><span data-stu-id="84ae3-136">3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ae3-137">5 </span><span class="sxs-lookup"><span data-stu-id="84ae3-137">5</span></span></p></td>
<td><p><span data-ttu-id="84ae3-138">4 </span><span class="sxs-lookup"><span data-stu-id="84ae3-138">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ae3-139">6 </span><span class="sxs-lookup"><span data-stu-id="84ae3-139">6</span></span></p></td>
<td><p><span data-ttu-id="84ae3-140">5 </span><span class="sxs-lookup"><span data-stu-id="84ae3-140">5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ae3-141">7 </span><span class="sxs-lookup"><span data-stu-id="84ae3-141">7</span></span></p></td>
<td><p><span data-ttu-id="84ae3-142">5 </span><span class="sxs-lookup"><span data-stu-id="84ae3-142">5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ae3-143">8 </span><span class="sxs-lookup"><span data-stu-id="84ae3-143">8</span></span></p></td>
<td><p><span data-ttu-id="84ae3-144">6 </span><span class="sxs-lookup"><span data-stu-id="84ae3-144">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ae3-145">9 </span><span class="sxs-lookup"><span data-stu-id="84ae3-145">9</span></span></p></td>
<td><p><span data-ttu-id="84ae3-146">7 </span><span class="sxs-lookup"><span data-stu-id="84ae3-146">7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ae3-147">10  </span><span class="sxs-lookup"><span data-stu-id="84ae3-147">10</span></span></p></td>
<td><p><span data-ttu-id="84ae3-148">8 </span><span class="sxs-lookup"><span data-stu-id="84ae3-148">8</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ae3-149">#</span><span class="sxs-lookup"><span data-stu-id="84ae3-149">11</span></span></p></td>
<td><p><span data-ttu-id="84ae3-150">9 </span><span class="sxs-lookup"><span data-stu-id="84ae3-150">9</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ae3-151">12 </span><span class="sxs-lookup"><span data-stu-id="84ae3-151">12</span></span></p></td>
<td><p><span data-ttu-id="84ae3-152">10  </span><span class="sxs-lookup"><span data-stu-id="84ae3-152">10</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="84ae3-153">今後プールが起動されるたびに、サーバーの85% が開始されます (前の表に示すように)。</span><span class="sxs-lookup"><span data-stu-id="84ae3-153">Every subsequent time the pool is started, 85% of the servers should be started (as shown in the preceding table).</span></span> <span data-ttu-id="84ae3-154">この数のサーバーを開始できない (ただし、プールレベルのクォーラム損失が発生しないように、十分な数のサーバーを開始できる) 場合は、 **reset-cspoolregistrarstate – ResetType QuorumLossRecovery** コマンドレットを使用して、このルーティンググループレベルのクォーラム損失から回復できるようにプールを有効にし、進行状況を確認できます。</span><span class="sxs-lookup"><span data-stu-id="84ae3-154">If this number of servers cannot be started (but enough servers can be started so that you are not at pool-level quorum loss), you can use the **Reset-CsPoolRegistrarState –ResetType QuorumLossRecovery** cmdlet to enable the pool to recover from this routing group level quorum loss and make progress.</span></span> <span data-ttu-id="84ae3-155">このコマンドレットの使用方法の詳細については、「 [reset-cspoolregistrarstate](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84ae3-155">For more information about how to use this cmdlet, see [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="84ae3-156">Lync Server はプライマリ SQL データベースをミラーリング監視として使用しているため、プライマリデータベースをシャットダウンして、ミラーコピーに切り替え、十分な数のフロントエンドサーバーをシャットダウンして、前の表に従って十分でない場合は、プール全体がダウンします。</span><span class="sxs-lookup"><span data-stu-id="84ae3-156">Because Lync Server uses the Primary SQL database as Witness, if you shut down the primary database and switch to the Mirror copy, and shut down enough Front End Servers so that not enough are running according to the preceding table, the entire pool will go down.</span></span> <span data-ttu-id="84ae3-157">詳細については、「 <A href="https://go.microsoft.com/fwlink/?linkid=393672">データベースミラーリング監視</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84ae3-157">For more information, see <A href="https://go.microsoft.com/fwlink/?linkid=393672">Database Mirroring Witness</A>.</span></span>



</div>

</div>

<div>

## <a name="pool-level-quorum-loss"></a><span data-ttu-id="84ae3-158">プールレベルのクォーラム損失</span><span class="sxs-lookup"><span data-stu-id="84ae3-158">Pool-level quorum loss</span></span>

<span data-ttu-id="84ae3-159">フロントエンドプールが完全に機能するために、プールレベルのクォーラム損失になることはありません。</span><span class="sxs-lookup"><span data-stu-id="84ae3-159">For a Front End pool to function at all, it cannot be in pool-level quorum loss.</span></span> <span data-ttu-id="84ae3-160">次の表に示すように、実行しているサーバーの数が機能レベルの下にある場合は、プール内の残りのサーバーがすべての Lync Server サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="84ae3-160">If the number of servers running falls below the functional level as shown in the following table, the remaining servers in the pool will stop all Lync Server services.</span></span> <span data-ttu-id="84ae3-161">次の表の番号は、プール内のバックエンドサーバーが動作していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="84ae3-161">Note that the numbers in the following table assume that the Back End Servers in the pool are running.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="84ae3-162">プール内のフロントエンド サーバーの総数</span><span class="sxs-lookup"><span data-stu-id="84ae3-162">Total number of Front End Servers in the pool</span></span></th>
<th><span data-ttu-id="84ae3-163">プールが機能するために実行されている必要のあるサーバーの数</span><span class="sxs-lookup"><span data-stu-id="84ae3-163">Number of servers that must be running for pool to be functional</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84ae3-164">pbm-2</span><span class="sxs-lookup"><span data-stu-id="84ae3-164">2</span></span></p></td>
<td><p><span data-ttu-id="84ae3-165">1-d</span><span class="sxs-lookup"><span data-stu-id="84ae3-165">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ae3-166">3-4</span><span class="sxs-lookup"><span data-stu-id="84ae3-166">3-4</span></span></p></td>
<td><p><span data-ttu-id="84ae3-167">任意の2</span><span class="sxs-lookup"><span data-stu-id="84ae3-167">Any 2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ae3-168">5-6</span><span class="sxs-lookup"><span data-stu-id="84ae3-168">5-6</span></span></p></td>
<td><p><span data-ttu-id="84ae3-169">任意の3つ</span><span class="sxs-lookup"><span data-stu-id="84ae3-169">Any 3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ae3-170">7 </span><span class="sxs-lookup"><span data-stu-id="84ae3-170">7</span></span></p></td>
<td><p><span data-ttu-id="84ae3-171">任意4</span><span class="sxs-lookup"><span data-stu-id="84ae3-171">Any 4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ae3-172">8-9</span><span class="sxs-lookup"><span data-stu-id="84ae3-172">8-9</span></span></p></td>
<td><p><span data-ttu-id="84ae3-173">最初の7台のサーバーのうち4台</span><span class="sxs-lookup"><span data-stu-id="84ae3-173">Any 4 of the first 7 servers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ae3-174">10-12</span><span class="sxs-lookup"><span data-stu-id="84ae3-174">10-12</span></span></p></td>
<td><p><span data-ttu-id="84ae3-175">最初の9台のサーバーのうち5台</span><span class="sxs-lookup"><span data-stu-id="84ae3-175">Any 5 of the first 9 servers</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="84ae3-176">上記の表では、最初にプールが開始されたときに、最初に開始されたサーバーが "最初のサーバー" です。</span><span class="sxs-lookup"><span data-stu-id="84ae3-176">In the preceding table, the “first servers” are the servers which were brought up first, chronologically, when the pool was started for the first time.</span></span> <span data-ttu-id="84ae3-177">これらのサーバーを決定するには、 **-** **poolfqdn** オプションを指定して、コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="84ae3-177">To determine these servers, you can use the **Get-CsComputer** cmdlet with the **–PoolFqdn** option.</span></span> <span data-ttu-id="84ae3-178">このコマンドレットでは、トポロジに表示される順序でサーバーが表示され、一覧の一番上にあるサーバーが最初のサーバーになります。</span><span class="sxs-lookup"><span data-stu-id="84ae3-178">This cmdlet will show the servers in the order that they appear in the topology, and the ones at the top of the list are the first servers.</span></span>

</div>

<div>

## <a name="front-end-pools-with-two-front-end-servers"></a><span data-ttu-id="84ae3-179">フロントエンドサーバーが2台のフロントエンドプール</span><span class="sxs-lookup"><span data-stu-id="84ae3-179">Front End Pools with Two Front End Servers</span></span>

<span data-ttu-id="84ae3-180">2台のフロントエンドサーバーのみが含まれるフロントエンドプールを展開することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="84ae3-180">We do not recommend deploying a Front End pool that contains only two Front End Servers.</span></span> <span data-ttu-id="84ae3-181">このようなプールを展開する必要が生じた場合は、次のガイドラインに従ってください。</span><span class="sxs-lookup"><span data-stu-id="84ae3-181">If you do ever need to deploy such a pool, follow these guidelines:</span></span>

  - <span data-ttu-id="84ae3-182">2台のフロントエンドサーバーのうち1台がダウンした場合は、障害が発生したサーバーをできるだけ早く復旧するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="84ae3-182">If one of the two Front End Servers goes down, you should try to bring the failed server back up as soon as you can.</span></span> <span data-ttu-id="84ae3-183">同様に、2台のサーバーのいずれかをアップグレードする必要がある場合は、アップグレードが完了したらすぐにオンラインに戻します。</span><span class="sxs-lookup"><span data-stu-id="84ae3-183">Similarly, if you need to upgrade one of the two servers, bring it back online as soon as the upgrade is finished.</span></span>

  - <span data-ttu-id="84ae3-184">何らかの理由で両方のサーバーを同時に停止する必要がある場合は、プールのダウンタイムが終了したら、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="84ae3-184">If for some reason you need to bring both servers down at the same time, do the following when the downtime for the pool is finished:</span></span>
    
      - <span data-ttu-id="84ae3-185">ベストプラクティスは、両方のフロントエンドサーバーを同時に再起動することです。</span><span class="sxs-lookup"><span data-stu-id="84ae3-185">The best practice is to restart both Front End Servers at the same time.</span></span>
    
      - <span data-ttu-id="84ae3-186">2台のサーバーを同時に再起動できない場合は、停止した順序とは逆の順序でバックアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="84ae3-186">If the two servers cannot be restarted at the same time, you should bring them back up in the reverse order of the order they went down.</span></span>
    
      - <span data-ttu-id="84ae3-187">その順序で復元できない場合は、プールを復旧する前に、次のコマンドレットを使用してください。</span><span class="sxs-lookup"><span data-stu-id="84ae3-187">If you cannot bring them back up in that order, then use the following cmdlet before bringing the pool back up:.</span></span>
        
            Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>

</div>

<div>

## <a name="additional-steps-to-ensure-pools-are-functional"></a><span data-ttu-id="84ae3-188">プールが機能していることを確認するための追加の手順</span><span class="sxs-lookup"><span data-stu-id="84ae3-188">Additional Steps to Ensure Pools are Functional</span></span>

<span data-ttu-id="84ae3-189">フロントエンドプールが機能していることを確認するには、他にもいくつかの要因を監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84ae3-189">You should watch for a couple of other factors to ensure that your Front End pools remain functional.</span></span>

  - <span data-ttu-id="84ae3-190">ユーザーをプールに初めて移動するときは、少なくとも3台のフロントエンドサーバーが稼働していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="84ae3-190">When you move users to the pool for the first time, be sure at least three of the Front End Servers are running.</span></span>

  - <span data-ttu-id="84ae3-191">このプールと障害復旧のために別のプールとの間にペアリング関係を確立している場合は、その関係を確立した後で、その関係を確立した後、データをバックアッププールと同期するために、同時に3台のフロントエンドサーバーがこのプールに存在することを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84ae3-191">If you establish a pairing relationship between this pool and another pool for disaster recovery purposes, then after establishing that relationship you must be sure this pool has three Front End Servers running simultaneously at some time to properly synchronize data with the backup pool.</span></span> <span data-ttu-id="84ae3-192">プールのペアリングと障害復旧機能の詳細については、「 [Lync Server 2013 での高可用性と障害復旧の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84ae3-192">For more information on pool pairing and disaster recovery features, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

</div>

</div>

<div>

## <a name="improving-the-reliability-of-pool-upgrades"></a><span data-ttu-id="84ae3-193">プールのアップグレードの信頼性を向上させる</span><span class="sxs-lookup"><span data-stu-id="84ae3-193">Improving the Reliability of Pool Upgrades</span></span>

<span data-ttu-id="84ae3-194">フロントエンドプール内のサーバーをアップグレードまたは更新する必要がある場合は、「 [Lync Server 2013 でのフロントエンドサーバーのアップグレードまたは更新](lync-server-2013-upgrade-or-update-front-end-servers.md)」に示されているワークフローに従って、次のガイドラインを参照してください。</span><span class="sxs-lookup"><span data-stu-id="84ae3-194">When you need to upgrade or patch the servers in a Front End pool, follow the workflow shown in [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md), and the following guidelines:</span></span>

  - <span data-ttu-id="84ae3-195">アップグレードドメイン間を移行するために ( [アップグレード時または Lync Server 2013 でのフロントエンドサーバーの更新](lync-server-2013-upgrade-or-update-front-end-servers.md)時にワークフローに従って) 別のアップグレードドメインに移動する場合は、 **get-cspoolupgradereadinessstate 戻し** コマンドレットを使用して、レディ状態をチェックします。</span><span class="sxs-lookup"><span data-stu-id="84ae3-195">When you move from one upgrade domain to another for upgrades (following the workflow at [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)), you will use the **Get-CsPoolUpgradeReadinessState** cmdlet and check for Ready state.</span></span> <span data-ttu-id="84ae3-196">「Ready」に達した後、各アップグレードドメインの間に20分間の待ち時間を追加すると、アップグレードの信頼性が向上します。</span><span class="sxs-lookup"><span data-stu-id="84ae3-196">Adding a 20-minute wait between each upgrade domain after it reaches “Ready” will make the upgrades more reliable.</span></span> <span data-ttu-id="84ae3-197">この20分間の準備ができ **ない状態** になった場合は、20分のタイマーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="84ae3-197">If it becomes **Not Ready** during this 20 minutes, restart the 20-minute timer.</span></span> <span data-ttu-id="84ae3-198">また、20分間隔を開始する前と後に **get-cspoolfabricstate** コマンドレットを実行して、ルーティンググループのプライマリとセカンダリが変更されていないことを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="84ae3-198">Also, you can run the **Get-CsPoolFabricState** cmdlet before and after starting the 20-minute interval and make sure there are no changes to the primaries and secondaries of routing groups.</span></span>

  - <span data-ttu-id="84ae3-199">最後にパッチが適用されたアップグレードドメイン内のサーバーが停止または再起動しない場合は、次のアップグレードドメインに移動しないでください。</span><span class="sxs-lookup"><span data-stu-id="84ae3-199">Do not move on to the next upgrade domain if any of the servers in the last patched upgrade domain are stuck or not restarted.</span></span> <span data-ttu-id="84ae3-200">これは、アップグレード中のいずれかのサーバーが開始できない場合にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="84ae3-200">This also applies if any of the servers within an upgrade cannot start.</span></span> <span data-ttu-id="84ae3-201">**Get-cspoolfabricstate**を実行して、すべてのルーティンググループにプライマリおよび少なくとも1つのセカンダリがあることを確認します。これにより、すべてのユーザーがサービスを利用できるかどうかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="84ae3-201">Run **Get-CsPoolFabricState** to make sure all of the routing groups have a primary and at least one secondary; this will confirm whether all users have service.</span></span>

  - <span data-ttu-id="84ae3-202">一部のユーザーがサービスを所有していて、他のユーザーがいない場合は、-Verbose オプションを指定して **get-cspoolfabricstate** を実行し、レプリカがないルーティンググループを確認します。</span><span class="sxs-lookup"><span data-stu-id="84ae3-202">If some users have service and others do not, run **Get-CsPoolFabricState** with the –Verbose option to check for routing groups that have missing replicas.</span></span> <span data-ttu-id="84ae3-203">最初のトラブルシューティング手順として、プール全体を再起動しないでください。</span><span class="sxs-lookup"><span data-stu-id="84ae3-203">Do not restart the entire pool as the first troubleshooting step.</span></span> <span data-ttu-id="84ae3-204">このコマンドレットの詳細については、「 [get-cspoolfabricstate](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84ae3-204">For more information on this cmdlet, see [Get-CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState).</span></span>

  - <span data-ttu-id="84ae3-205">Windows fabric のインストール/アンインストールの際に、イベントビューアまたはパフォーマンスモニターウィンドウのすべてのインスタンスが閉じていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="84ae3-205">Make sure that all instances of the Event Viewer or Performance Monitor windows are closed for windows fabric installs/uninstalls.</span></span>

</div>

<div>

## <a name="changing-a-front-end-pools-configuration"></a><span data-ttu-id="84ae3-206">フロントエンドプールの構成の変更</span><span class="sxs-lookup"><span data-stu-id="84ae3-206">Changing a Front End Pool’s Configuration</span></span>

<span data-ttu-id="84ae3-207">フロントエンドサーバーをプールに追加、またはプールから削除した後、新しいトポロジを公開する場合は、次のガイドラインに従ってください。</span><span class="sxs-lookup"><span data-stu-id="84ae3-207">Whenever you add Front End Servers to a pool, or remove them from the pool, and then publish the new topology, follow these guidelines:</span></span>

  - <span data-ttu-id="84ae3-208">新しいトポロジが公開されたら、プール内の各フロントエンドサーバーを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84ae3-208">After the new topology has been published, you must restart each Front End Server in the pool.</span></span> <span data-ttu-id="84ae3-209">一度に1つずつ再起動します。</span><span class="sxs-lookup"><span data-stu-id="84ae3-209">Restart them one at a time.</span></span>

  - <span data-ttu-id="84ae3-210">構成の変更中にプール全体がダウンしていた場合は、新しいトポロジが公開された後、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="84ae3-210">If the entire pool has been down during the configuration change, then run the following cmdlet after the new topology is published:</span></span>
    
        Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset

<span data-ttu-id="84ae3-211">フロントエンドサーバーに障害が発生した場合、数日間またはそれ以上の交換が必要になる可能性がある場合は、サーバーをトポロジから削除します。</span><span class="sxs-lookup"><span data-stu-id="84ae3-211">If a Front End Server fails and is unlikely to be replaced for a few days or more, remove the server from the topology.</span></span> <span data-ttu-id="84ae3-212">再び使用できるようになったら、新しいフロントエンドサーバーをトポロジに追加します。</span><span class="sxs-lookup"><span data-stu-id="84ae3-212">Add the new Front End Server to the topology when it is available again.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

