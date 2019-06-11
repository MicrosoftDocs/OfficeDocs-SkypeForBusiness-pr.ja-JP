---
title: 'Lync Server 2013: フロントエンド サーバー、インスタント メッセージングおよびプレゼンスのトポロジおよびコンポーネント'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Topologies and components for Front End Servers, instant messaging, and presence
ms:assetid: f08ce7a1-d14e-4a54-9771-a82c870658bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412996(v=OCS.15)
ms:contentKeyID: 48185763
ms.date: 10/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bc44790fc9584676cdd10305085b23bd5e99299
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848408"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="7e46b-102">Lync Server 2013 フロントエンド サーバー、インスタント メッセージングおよびプレゼンスのトポロジおよびコンポーネント</span><span class="sxs-lookup"><span data-stu-id="7e46b-102">Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e46b-103">_**最終更新日:** 2014-10-24_</span><span class="sxs-lookup"><span data-stu-id="7e46b-103">_**Topic Last Modified:** 2014-10-24_</span></span>

<span data-ttu-id="7e46b-104">インスタント メッセージング (IM) とプレゼンスに必要なコンポーネントは、次に示すものだけです。</span><span class="sxs-lookup"><span data-stu-id="7e46b-104">The only components required for instant messaging (IM) and presence are:</span></span>

  - <span data-ttu-id="7e46b-105">組織のフロントエンドサーバーまたは Standard Edition サーバー。</span><span class="sxs-lookup"><span data-stu-id="7e46b-105">Your organization’s Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="7e46b-106">これらのサーバーで、IM およびプレゼンス機能は常にオンになっています。</span><span class="sxs-lookup"><span data-stu-id="7e46b-106">IM and presence capabilities are always enabled on these servers.</span></span>

  - <span data-ttu-id="7e46b-107">ロード バランサー (Enterprise Edition フロントエンド プールがある場合)</span><span class="sxs-lookup"><span data-stu-id="7e46b-107">A load balancer, if you have an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="7e46b-108">詳細については、「 [Lync Server 2013 の負荷分散の要件](lync-server-2013-load-balancing-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e46b-108">For more information, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

<div>

## <a name="planning-for-the-deployment-of-front-end-pools"></a><span data-ttu-id="7e46b-109">フロントエンドプールの展開を計画する</span><span class="sxs-lookup"><span data-stu-id="7e46b-109">Planning for the Deployment of Front End Pools</span></span>

<span data-ttu-id="7e46b-110">Lync Server 2013 では、フロントエンドプールのアーキテクチャが変更され、これらの変更が、フロントエンドプールの計画と維持の方法に影響します。</span><span class="sxs-lookup"><span data-stu-id="7e46b-110">In Lync Server 2013, Front End pool architecture has changed, and these changes affect how you should plan and maintain your Front End pools.</span></span>

<span data-ttu-id="7e46b-111">すべての Enterprise Edition フロントエンドプールには、少なくとも3台のフロントエンドサーバーが含まれていることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7e46b-111">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers.</span></span> <span data-ttu-id="7e46b-112">Lync Server では、フロントエンドプールのアーキテクチャで分散システムモデルが使用され、各ユーザーのデータはプール内の3つのフロントエンドサーバー上に保持されます。</span><span class="sxs-lookup"><span data-stu-id="7e46b-112">In Lync Server, the architecture of Front End pools uses a distributed systems model, with each user’s data kept on three Front End servers in the pool.</span></span> <span data-ttu-id="7e46b-113">この新しいアーキテクチャの詳細については、「 [Lync Server 2013 でのトポロジの変更](lync-server-2013-topology-changes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e46b-113">For more information about this new architecture, see [Topology changes in Lync Server 2013](lync-server-2013-topology-changes.md).</span></span>

<span data-ttu-id="7e46b-114">3つの Enterprise Edition フロントエンドサーバーを展開したくない場合、および障害回復が必要な場合は、Lync Server Standard Edition を使用して、ペアのバックアップリレーションシップを持つ2つのプールを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7e46b-114">If you do not want to deploy three Enterprise Edition Front End Servers and want disaster recovery, we recommend you use Lync Server Standard Edition and create two pools with a paired backup relationship.</span></span> <span data-ttu-id="7e46b-115">これにより、2台のサーバーのみを含む障害回復ソリューションが提供されます。</span><span class="sxs-lookup"><span data-stu-id="7e46b-115">This will provide a disaster recovery solution with only two servers.</span></span> <span data-ttu-id="7e46b-116">高可用性と障害回復のトポロジと機能の詳細については、「 [Lync Server 2013 での高可用性と障害回復の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e46b-116">For more information, on high availability and disaster recovery topologies and features, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

</div>

<div>

## <a name="planning-for-the-management-of-front-end-pools"></a><span data-ttu-id="7e46b-117">フロントエンドプールの管理の計画</span><span class="sxs-lookup"><span data-stu-id="7e46b-117">Planning for the Management of Front End Pools</span></span>

<span data-ttu-id="7e46b-118">フロントエンドプールの場合は、このセクションのガイドラインに従ってください。</span><span class="sxs-lookup"><span data-stu-id="7e46b-118">For Front End pools, follow the guidelines in this section.</span></span>

<div>

## <a name="ensuring-that-pools-are-functional"></a><span data-ttu-id="7e46b-119">プールが機能していることを確認する</span><span class="sxs-lookup"><span data-stu-id="7e46b-119">Ensuring That Pools are Functional</span></span>

<span data-ttu-id="7e46b-120">フロントエンドプール用の新しい分散モデルを使用すると、プールを機能させるには、プールのサーバーの特定の数を実行しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e46b-120">With the new distributed model for Front End pools, certain numbers of a pool’s servers must be running for the pool to function.</span></span> <span data-ttu-id="7e46b-121">プールには2つの損失モードがあります。</span><span class="sxs-lookup"><span data-stu-id="7e46b-121">There are two loss modes for a pool</span></span>

  - <span data-ttu-id="7e46b-122">特定のルーティンググループの十分なレプリカサーバーがないために、ルーティンググループレベルのクォーラム損失が発生しました。</span><span class="sxs-lookup"><span data-stu-id="7e46b-122">Routing Group Level quorum loss, caused by not enough replica servers for a particular routing group.</span></span> <span data-ttu-id="7e46b-123">ルーティンググループは、プールに所属している一連のユーザーの集合体です。</span><span class="sxs-lookup"><span data-stu-id="7e46b-123">A routing group is an aggregation of a set of users homed in the pool.</span></span> <span data-ttu-id="7e46b-124">各ルーティンググループには、1つのプライマリと2つのセカンダリという3つの複製がプールにあります。</span><span class="sxs-lookup"><span data-stu-id="7e46b-124">Each routing group has three replicas in the pool: one primary and two secondaries.</span></span>

  - <span data-ttu-id="7e46b-125">プール レベル クォーラム損失。プールで十分な数のシード サーバーが実行されていない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="7e46b-125">Pool Level quorum loss, caused when not enough seed servers are running in the pool.</span></span>

<div>

## <a name="routing-group-level-quorum-loss"></a><span data-ttu-id="7e46b-126">ルーティング グループ レベル クォーラム損失</span><span class="sxs-lookup"><span data-stu-id="7e46b-126">Routing Group Level quorum loss</span></span>

<span data-ttu-id="7e46b-p107">新しいフロント エンド プールを初めて起動するときには、次の表に示すように、サーバーの 85% が実行されていることが必要です。実行されているサーバーの数がそれより少ないと、サービスが起動状態で行き詰まり、プールが起動されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="7e46b-p107">The first time you start a new Front End pool, it is essential that 85% of the servers are up and running, as shown in the following table. If fewer servers are running, the services might be stuck in the starting state and the pool might not start.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7e46b-129">プール内のサーバーの合計数</span><span class="sxs-lookup"><span data-stu-id="7e46b-129">Total number of servers in the pool</span></span></th>
<th><span data-ttu-id="7e46b-130">プールを初めて起動させるために実行する必要があるサーバー数</span><span class="sxs-lookup"><span data-stu-id="7e46b-130">Number of servers that must be running for the pool to be started the first time</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e46b-131">2</span><span class="sxs-lookup"><span data-stu-id="7e46b-131">2</span></span></p></td>
<td><p><span data-ttu-id="7e46b-132">1</span><span class="sxs-lookup"><span data-stu-id="7e46b-132">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e46b-133">3</span><span class="sxs-lookup"><span data-stu-id="7e46b-133">3</span></span></p></td>
<td><p><span data-ttu-id="7e46b-134">3</span><span class="sxs-lookup"><span data-stu-id="7e46b-134">3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e46b-135">4</span><span class="sxs-lookup"><span data-stu-id="7e46b-135">4</span></span></p></td>
<td><p><span data-ttu-id="7e46b-136">3</span><span class="sxs-lookup"><span data-stu-id="7e46b-136">3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e46b-137">5</span><span class="sxs-lookup"><span data-stu-id="7e46b-137">5</span></span></p></td>
<td><p><span data-ttu-id="7e46b-138">4</span><span class="sxs-lookup"><span data-stu-id="7e46b-138">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e46b-139">6</span><span class="sxs-lookup"><span data-stu-id="7e46b-139">6</span></span></p></td>
<td><p><span data-ttu-id="7e46b-140">5</span><span class="sxs-lookup"><span data-stu-id="7e46b-140">5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e46b-141">7</span><span class="sxs-lookup"><span data-stu-id="7e46b-141">7</span></span></p></td>
<td><p><span data-ttu-id="7e46b-142">5</span><span class="sxs-lookup"><span data-stu-id="7e46b-142">5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e46b-143">個</span><span class="sxs-lookup"><span data-stu-id="7e46b-143">8</span></span></p></td>
<td><p><span data-ttu-id="7e46b-144">6</span><span class="sxs-lookup"><span data-stu-id="7e46b-144">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e46b-145">ファイブ</span><span class="sxs-lookup"><span data-stu-id="7e46b-145">9</span></span></p></td>
<td><p><span data-ttu-id="7e46b-146">7</span><span class="sxs-lookup"><span data-stu-id="7e46b-146">7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e46b-147">常用</span><span class="sxs-lookup"><span data-stu-id="7e46b-147">10</span></span></p></td>
<td><p><span data-ttu-id="7e46b-148">個</span><span class="sxs-lookup"><span data-stu-id="7e46b-148">8</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e46b-149">折り</span><span class="sxs-lookup"><span data-stu-id="7e46b-149">11</span></span></p></td>
<td><p><span data-ttu-id="7e46b-150">ファイブ</span><span class="sxs-lookup"><span data-stu-id="7e46b-150">9</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e46b-151">以内</span><span class="sxs-lookup"><span data-stu-id="7e46b-151">12</span></span></p></td>
<td><p><span data-ttu-id="7e46b-152">常用</span><span class="sxs-lookup"><span data-stu-id="7e46b-152">10</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7e46b-153">その後もプールが起動されるたびに、サーバーの 85% が起動されている必要があります (前出の表を参照)。</span><span class="sxs-lookup"><span data-stu-id="7e46b-153">Every subsequent time the pool is started, 85% of the servers should be started (as shown in the preceding table).</span></span> <span data-ttu-id="7e46b-154">この数のサーバーを起動できない (ただし、プール レベル クォーラム損失にはならない数のサーバーが起動されている) 場合は、**Reset-CsPoolRegistrarState –ResetType QuorumLossRecovery** コマンドレットを使用して、プールをルーティング グループ レベル クォーラム損失から復旧させ、処理を続行させることができます。</span><span class="sxs-lookup"><span data-stu-id="7e46b-154">If this number of servers cannot be started (but enough servers can be started so that you are not at pool-level quorum loss), you can use the **Reset-CsPoolRegistrarState –ResetType QuorumLossRecovery** cmdlet to enable the pool to recover from this routing group level quorum loss and make progress.</span></span> <span data-ttu-id="7e46b-155">このコマンドレットの使い方の詳細については、「 [CsPoolRegistrarState をリセット](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e46b-155">For more information about how to use this cmdlet, see [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7e46b-156">Lync Server ではプライマリ SQL データベースが監視として使用されるため、プライマリデータベースをシャットダウンし、ミラーコピーに切り替えて、前の表に従っても十分に動作しない場合には、プール全体がダウンします。</span><span class="sxs-lookup"><span data-stu-id="7e46b-156">Because Lync Server uses the Primary SQL database as Witness, if you shut down the primary database and switch to the Mirror copy, and shut down enough Front End Servers so that not enough are running according to the preceding table, the entire pool will go down.</span></span> <span data-ttu-id="7e46b-157">詳細については、「<A href="http://go.microsoft.com/fwlink/?linkid=393672">データベースミラーリング監視</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e46b-157">For more information, see <A href="http://go.microsoft.com/fwlink/?linkid=393672">Database Mirroring Witness</A>.</span></span>



</div>

</div>

<div>

## <a name="pool-level-quorum-loss"></a><span data-ttu-id="7e46b-158">プール レベル クォーラム損失</span><span class="sxs-lookup"><span data-stu-id="7e46b-158">Pool-level quorum loss</span></span>

<span data-ttu-id="7e46b-159">フロントエンドプールをまったく機能させるには、プールレベルのクォーラム損失にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7e46b-159">For a Front End pool to function at all, it cannot be in pool-level quorum loss.</span></span> <span data-ttu-id="7e46b-160">次の表に示すように、実行しているサーバーの数が機能レベルを下回っている場合は、プール内の残りのサーバーによって、すべての Lync Server サービスが停止されます。</span><span class="sxs-lookup"><span data-stu-id="7e46b-160">If the number of servers running falls below the functional level as shown in the following table, the remaining servers in the pool will stop all Lync Server services.</span></span> <span data-ttu-id="7e46b-161">次の表の数値は、プール内のバックエンドサーバーが実行されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="7e46b-161">Note that the numbers in the following table assume that the Back End Servers in the pool are running.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7e46b-162">プール内のフロントエンドサーバーの合計数</span><span class="sxs-lookup"><span data-stu-id="7e46b-162">Total number of Front End Servers in the pool</span></span></th>
<th><span data-ttu-id="7e46b-163">プールを機能させるために実行する必要があるサーバーの数</span><span class="sxs-lookup"><span data-stu-id="7e46b-163">Number of servers that must be running for pool to be functional</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e46b-164">2</span><span class="sxs-lookup"><span data-stu-id="7e46b-164">2</span></span></p></td>
<td><p><span data-ttu-id="7e46b-165">1</span><span class="sxs-lookup"><span data-stu-id="7e46b-165">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e46b-166">3 ～ 4</span><span class="sxs-lookup"><span data-stu-id="7e46b-166">3-4</span></span></p></td>
<td><p><span data-ttu-id="7e46b-167">任意の 2 台</span><span class="sxs-lookup"><span data-stu-id="7e46b-167">Any 2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e46b-168">5 ～ 6</span><span class="sxs-lookup"><span data-stu-id="7e46b-168">5-6</span></span></p></td>
<td><p><span data-ttu-id="7e46b-169">任意の 3 台</span><span class="sxs-lookup"><span data-stu-id="7e46b-169">Any 3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e46b-170">7</span><span class="sxs-lookup"><span data-stu-id="7e46b-170">7</span></span></p></td>
<td><p><span data-ttu-id="7e46b-171">任意の 4 台</span><span class="sxs-lookup"><span data-stu-id="7e46b-171">Any 4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e46b-172">8 ～ 9</span><span class="sxs-lookup"><span data-stu-id="7e46b-172">8-9</span></span></p></td>
<td><p><span data-ttu-id="7e46b-173">最初の 7 台のうちの任意の 4 台</span><span class="sxs-lookup"><span data-stu-id="7e46b-173">Any 4 of the first 7 servers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e46b-174">10 ～ 12</span><span class="sxs-lookup"><span data-stu-id="7e46b-174">10-12</span></span></p></td>
<td><p><span data-ttu-id="7e46b-175">最初の 9 台のうちの任意の 5 台</span><span class="sxs-lookup"><span data-stu-id="7e46b-175">Any 5 of the first 9 servers</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7e46b-176">この表でいう最初のサーバーとは、プールが初めて起動されたとき先に立ち上げられたものから順に数えたサーバーです。</span><span class="sxs-lookup"><span data-stu-id="7e46b-176">In the preceding table, the “first servers” are the servers which were brought up first, chronologically, when the pool was started for the first time.</span></span> <span data-ttu-id="7e46b-177">これらのサーバーを確認するには、 **– Poolfqdn**オプションを使用して、**コンピューターの購入**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="7e46b-177">To determine these servers, you can use the **Get-CsComputer** cmdlet with the **–PoolFqdn** option.</span></span> <span data-ttu-id="7e46b-178">このコマンドレットはサーバーをトポロジ内に出現した順に表示するので、そのリストの先頭にある方が最初のサーバーです。</span><span class="sxs-lookup"><span data-stu-id="7e46b-178">This cmdlet will show the servers in the order that they appear in the topology, and the ones at the top of the list are the first servers.</span></span>

</div>

<div>

## <a name="front-end-pools-with-two-front-end-servers"></a><span data-ttu-id="7e46b-179">フロントエンドサーバーが2台あるフロントエンドプール</span><span class="sxs-lookup"><span data-stu-id="7e46b-179">Front End Pools with Two Front End Servers</span></span>

<span data-ttu-id="7e46b-180">2台のフロントエンドサーバーのみを含むフロントエンドプールの展開はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="7e46b-180">We do not recommend deploying a Front End pool that contains only two Front End Servers.</span></span> <span data-ttu-id="7e46b-181">このようなプールを展開する必要がある場合は、次のガイドラインに従ってください。</span><span class="sxs-lookup"><span data-stu-id="7e46b-181">If you do ever need to deploy such a pool, follow these guidelines:</span></span>

  - <span data-ttu-id="7e46b-182">2台のフロントエンドサーバーのいずれかがダウンしている場合は、可能な限り早く、障害が発生したサーバーをバックアップしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e46b-182">If one of the two Front End Servers goes down, you should try to bring the failed server back up as soon as you can.</span></span> <span data-ttu-id="7e46b-183">同様に、2 台のサーバーのうち 1 台をアップグレードする必要がある場合は、アップグレードが終わり次第、オンラインにします。</span><span class="sxs-lookup"><span data-stu-id="7e46b-183">Similarly, if you need to upgrade one of the two servers, bring it back online as soon as the upgrade is finished.</span></span>

  - <span data-ttu-id="7e46b-184">何らかの理由で両方のサーバーを同時に停止する必要がある場合は、プールのダウンタイムが終わったら次のことをします。</span><span class="sxs-lookup"><span data-stu-id="7e46b-184">If for some reason you need to bring both servers down at the same time, do the following when the downtime for the pool is finished:</span></span>
    
      - <span data-ttu-id="7e46b-185">ベストプラクティスとして、フロントエンドサーバーの両方を同時に再起動することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7e46b-185">The best practice is to restart both Front End Servers at the same time.</span></span>
    
      - <span data-ttu-id="7e46b-186">2 台のサーバーを同時に再起動できない場合は、停止した順序とは逆の順序で復旧する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e46b-186">If the two servers cannot be restarted at the same time, you should bring them back up in the reverse order of the order they went down.</span></span>
    
      - <span data-ttu-id="7e46b-187">この順序で元の状態に戻すことができない場合は、プールを復元する前に、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="7e46b-187">If you cannot bring them back up in that order, then use the following cmdlet before bringing the pool back up:.</span></span>
        
            Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>

</div>

<div>

## <a name="additional-steps-to-ensure-pools-are-functional"></a><span data-ttu-id="7e46b-188">プールを機能させるための追加の手順</span><span class="sxs-lookup"><span data-stu-id="7e46b-188">Additional Steps to Ensure Pools are Functional</span></span>

<span data-ttu-id="7e46b-189">フロント エンド プールを確実に機能させておくために、他にもいくつかの要因を監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e46b-189">You should watch for a couple of other factors to ensure that your Front End pools remain functional.</span></span>

  - <span data-ttu-id="7e46b-190">ユーザーをプールに初めて移動する場合は、少なくとも3台のフロントエンドサーバーが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7e46b-190">When you move users to the pool for the first time, be sure at least three of the Front End Servers are running.</span></span>

  - <span data-ttu-id="7e46b-191">このプールと障害回復目的のために別のプールとの間にペアリング関係を確立した場合は、リレーションシップを設定した後に、リレーションシップを確立した後に、このプールに3つのフロントエンドサーバーが同時に実行されていることを確認する必要があります。バックアッププールのあるデータ。</span><span class="sxs-lookup"><span data-stu-id="7e46b-191">If you establish a pairing relationship between this pool and another pool for disaster recovery purposes, then after establishing that relationship you must be sure this pool has three Front End Servers running simultaneously at some time to properly synchronize data with the backup pool.</span></span> <span data-ttu-id="7e46b-192">プールのペアリングと障害回復機能の詳細については、「 [Lync Server 2013 での高可用性と障害回復の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e46b-192">For more information on pool pairing and disaster recovery features, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

</div>

</div>

<div>

## <a name="improving-the-reliability-of-pool-upgrades"></a><span data-ttu-id="7e46b-193">プールのアップグレードの信頼性を向上させる</span><span class="sxs-lookup"><span data-stu-id="7e46b-193">Improving the Reliability of Pool Upgrades</span></span>

<span data-ttu-id="7e46b-194">フロントエンドプールのサーバーをアップグレードまたは更新する必要がある場合は、「 [Lync Server 2013 のフロントエンドサーバーのアップグレードまたは更新](lync-server-2013-upgrade-or-update-front-end-servers.md)に関するワークフロー」と次のガイドラインに従ってください。</span><span class="sxs-lookup"><span data-stu-id="7e46b-194">When you need to upgrade or patch the servers in a Front End pool, follow the workflow shown in [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md), and the following guidelines:</span></span>

  - <span data-ttu-id="7e46b-195">アップグレードのために1つのアップグレードドメインから別のドメインに移動する場合 ([アップグレードまたは Lync Server 2013 のフロントエンドサーバーの更新](lync-server-2013-upgrade-or-update-front-end-servers.md)でワークフローに従います)、 **CsPoolUpgradeReadinessState**コマンドレットを使用して、[準備完了] 状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="7e46b-195">When you move from one upgrade domain to another for upgrades (following the workflow at [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)), you will use the **Get-CsPoolUpgradeReadinessState** cmdlet and check for Ready state.</span></span> <span data-ttu-id="7e46b-196">"準備完了" になった後の各ドメイン間で20分間の待機を追加すると、アップグレードの信頼性が向上します。</span><span class="sxs-lookup"><span data-stu-id="7e46b-196">Adding a 20-minute wait between each upgrade domain after it reaches “Ready” will make the upgrades more reliable.</span></span> <span data-ttu-id="7e46b-197">この20分間に準備ができ**ない**場合は、20分のタイマーを再起動してください。</span><span class="sxs-lookup"><span data-stu-id="7e46b-197">If it becomes **Not Ready** during this 20 minutes, restart the 20-minute timer.</span></span> <span data-ttu-id="7e46b-198">また、 **CsPoolFabricState**コマンドレットを実行してから20分間隔を開始してから、ルーティンググループのプライマリとセカンダリを変更しないようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7e46b-198">Also, you can run the **Get-CsPoolFabricState** cmdlet before and after starting the 20-minute interval and make sure there are no changes to the primaries and secondaries of routing groups.</span></span>

  - <span data-ttu-id="7e46b-199">最後に修正されたアップグレードドメイン内のいずれかのサーバーが停止しているか、再開されていない場合は、次のアップグレードドメインに移動しないでください。</span><span class="sxs-lookup"><span data-stu-id="7e46b-199">Do not move on to the next upgrade domain if any of the servers in the last patched upgrade domain are stuck or not restarted.</span></span> <span data-ttu-id="7e46b-200">これは、アップグレード内のいずれかのサーバーが起動できない場合にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="7e46b-200">This also applies if any of the servers within an upgrade cannot start.</span></span> <span data-ttu-id="7e46b-201">**CsPoolFabricState**を実行して、すべてのルーティンググループにプライマリと少なくとも1つのセカンダリが含まれていることを確認します。これにより、すべてのユーザーがサービスを利用できるかどうかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="7e46b-201">Run **Get-CsPoolFabricState** to make sure all of the routing groups have a primary and at least one secondary; this will confirm whether all users have service.</span></span>

  - <span data-ttu-id="7e46b-202">一部のユーザーがサービスを利用していない場合は、– Verbose オプションを指定して**CsPoolFabricState**を実行し、レプリカが存在しないルーティンググループを確認します。</span><span class="sxs-lookup"><span data-stu-id="7e46b-202">If some users have service and others do not, run **Get-CsPoolFabricState** with the –Verbose option to check for routing groups that have missing replicas.</span></span> <span data-ttu-id="7e46b-203">最初のトラブルシューティング手順として、プール全体を再起動しないでください。</span><span class="sxs-lookup"><span data-stu-id="7e46b-203">Do not restart the entire pool as the first troubleshooting step.</span></span> <span data-ttu-id="7e46b-204">このコマンドレットの詳細については、「 [Get-CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e46b-204">For more information on this cmdlet, see [Get-CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState).</span></span>

  - <span data-ttu-id="7e46b-205">Windows fabric のインストール/アンインストールのため、イベントビューアーまたはパフォーマンスモニターのウィンドウのすべてのインスタンスが閉じていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7e46b-205">Make sure that all instances of the Event Viewer or Performance Monitor windows are closed for windows fabric installs/uninstalls.</span></span>

</div>

<div>

## <a name="changing-a-front-end-pools-configuration"></a><span data-ttu-id="7e46b-206">フロントエンドプールの構成を変更する</span><span class="sxs-lookup"><span data-stu-id="7e46b-206">Changing a Front End Pool’s Configuration</span></span>

<span data-ttu-id="7e46b-207">フロントエンドサーバーをプールに追加するか、またはプールから削除して、新しいトポロジを公開する場合は、次のガイドラインに従ってください。</span><span class="sxs-lookup"><span data-stu-id="7e46b-207">Whenever you add Front End Servers to a pool, or remove them from the pool, and then publish the new topology, follow these guidelines:</span></span>

  - <span data-ttu-id="7e46b-208">新しいトポロジが公開されたら、プール内の各フロントエンドサーバーを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e46b-208">After the new topology has been published, you must restart each Front End Server in the pool.</span></span> <span data-ttu-id="7e46b-209">1 台ずつ再起動してください。</span><span class="sxs-lookup"><span data-stu-id="7e46b-209">Restart them one at a time.</span></span>

  - <span data-ttu-id="7e46b-210">構成の変更中にプール全体が停止している場合は、新しいトポロジが公開された後に次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="7e46b-210">If the entire pool has been down during the configuration change, then run the following cmdlet after the new topology is published:</span></span>
    
        Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset

<span data-ttu-id="7e46b-211">フロントエンドサーバーに障害が発生し、数日以上に置き換えられない場合は、トポロジからサーバーを削除します。</span><span class="sxs-lookup"><span data-stu-id="7e46b-211">If a Front End Server fails and is unlikely to be replaced for a few days or more, remove the server from the topology.</span></span> <span data-ttu-id="7e46b-212">再利用可能な場合は、新しいフロントエンドサーバーをトポロジに追加します。</span><span class="sxs-lookup"><span data-stu-id="7e46b-212">Add the new Front End Server to the topology when it is available again.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

