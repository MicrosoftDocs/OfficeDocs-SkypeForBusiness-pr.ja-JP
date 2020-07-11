---
title: フロントエンドプールの高可用性と管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: Skype for Business Server のフロントエンドプール管理について説明します。これには、プールの管理、クォーラムの損失、および2台のフロントエンドサーバーのみのプールの特別な手順が含まれます。
ms.openlocfilehash: 2982e2da0e7a103b5b598019baa7403a73da826d
ms.sourcegitcommit: 397c4840fb053238de24b8b24ae75588b33b693d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2020
ms.locfileid: "45098435"
---
# <a name="front-end-pool-high-availability-and-management"></a><span data-ttu-id="98fae-103">フロントエンドプールの高可用性と管理</span><span class="sxs-lookup"><span data-stu-id="98fae-103">Front End Pool high availability and management</span></span>
 
<span data-ttu-id="98fae-104">Skype for Business Server のフロントエンドプール管理について説明します。これには、プールの管理、クォーラムの損失、および2台のフロントエンドサーバーのみのプールの特別な手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="98fae-104">Learn about Front End pool management in Skype for Business Server, including managing pools, quorum loss, and special steps for pools with only two Front End Servers.</span></span>
  
<span data-ttu-id="98fae-105">Skype for Business Server では、フロントエンドプールのアーキテクチャは分散システムモデルを使用しており、各ユーザーのデータはプール内の3台のフロントエンドサーバーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="98fae-105">In Skype for Business Server, the architecture of Front End pools uses a distributed systems model, with each user's data kept on as many as three Front End Servers in the pool.</span></span> <span data-ttu-id="98fae-106">すべての Enterprise Edition フロントエンドプールに、少なくとも3台のフロントエンドサーバーが含まれるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="98fae-106">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers.</span></span>

> [!NOTE]
> <span data-ttu-id="98fae-107">Skype for Business Server 2019 は、2台のフロントエンドサーバーを持つ Enterprise Edition フロントエンドプールをサポートしていません。このシナリオでは、トポロジを公開することはできません。</span><span class="sxs-lookup"><span data-stu-id="98fae-107">Skype for Business Server 2019 does not support Enterprise Edition Front End pools with two Front End Servers, and will not allow the topology to be published in that scenario.</span></span>
  
## <a name="planning-for-the-management-of-front-end-pools"></a><span data-ttu-id="98fae-108">フロントエンドプールの管理の計画</span><span class="sxs-lookup"><span data-stu-id="98fae-108">Planning for the management of Front End pools</span></span>

 <span data-ttu-id="98fae-109">Skype for Business Server は、Windows Fabric に基づく分散システムモデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="98fae-109">Skype for Business Server uses a distributed systems model based on Windows Fabric.</span></span> <span data-ttu-id="98fae-110">このモデルでは、各ユーザーおよび会議の重要なデータは、フロントエンドプール内の3つのフロントエンドサーバーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="98fae-110">In this model, important data for each user and conference is stored on three Front End Servers in a Front End pool.</span></span> <span data-ttu-id="98fae-111">特定のデータセットを格納する3つのサーバーは、レプリカと呼びます。</span><span class="sxs-lookup"><span data-stu-id="98fae-111">These three servers storing a certain set of data are calledreplicas.</span></span>
  
<span data-ttu-id="98fae-112">フロントエンドプールの分散モデルでは、プールが機能するためには特定の数のプールのサーバーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="98fae-112">With the distributed model for Front End pools, a certain numbers of a pool's servers must be running for the pool to function.</span></span> <span data-ttu-id="98fae-113">プールには、2つの損失モードがあります。</span><span class="sxs-lookup"><span data-stu-id="98fae-113">There are two loss modes for a pool.</span></span>
  
- <span data-ttu-id="98fae-114">特定のルーティンググループに十分な数のレプリカサーバーがないことによって発生した、ルーティンググループレベルのクォーラム損失。</span><span class="sxs-lookup"><span data-stu-id="98fae-114">Routing Group Level quorum loss, caused by not enough replica servers for a particular routing group.</span></span> <span data-ttu-id="98fae-115">ルーティンググループとは、プールに所属する一連のユーザーのことです。</span><span class="sxs-lookup"><span data-stu-id="98fae-115">A routing group is a set of users homed in the pool.</span></span> <span data-ttu-id="98fae-116">各ルーティンググループのプールには、1つのプライマリレプリカと2つのセカンダリレプリカの3つのレプリカがあります。</span><span class="sxs-lookup"><span data-stu-id="98fae-116">Each routing group has three replicas in the pool: one primary replica and two secondary replicas.</span></span>
    
- <span data-ttu-id="98fae-117">プールレベルのクォーラム損失。プール内で十分な数のシードサーバーが実行されていない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="98fae-117">Pool Level quorum loss, caused when not enough seed servers are running in the pool.</span></span> 
    
### <a name="routing-group-level-quorum-loss"></a><span data-ttu-id="98fae-118">ルーティンググループレベルのクォーラム損失</span><span class="sxs-lookup"><span data-stu-id="98fae-118">Routing Group Level quorum loss</span></span>

<span data-ttu-id="98fae-119">新しいフロントエンドプールを初めて起動するときは、次の表に示すように、サーバーの85% が稼働していることが重要です。</span><span class="sxs-lookup"><span data-stu-id="98fae-119">The first time you start a new Front End pool, it is essential that 85% of the servers are up and running, as shown in the following table.</span></span> <span data-ttu-id="98fae-120">実行されているサーバーの数が少ない場合、サービスが開始状態になり、プールが開始されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="98fae-120">If fewer servers are running, the services might be stuck in the starting state and the pool might not start.</span></span>
  
|<span data-ttu-id="98fae-121">プール内のサーバーの合計数</span><span class="sxs-lookup"><span data-stu-id="98fae-121">Total number of servers in the pool</span></span>  <br/> |<span data-ttu-id="98fae-122">プールを初めて起動するために実行する必要があるサーバーの数</span><span class="sxs-lookup"><span data-stu-id="98fae-122">Number of servers that must be running for the pool to be started the first time</span></span>  <br/> |
|:-----|:-----|
|<span data-ttu-id="98fae-123">2 </span><span class="sxs-lookup"><span data-stu-id="98fae-123">2</span></span>  <br/> |<span data-ttu-id="98fae-124">1 </span><span class="sxs-lookup"><span data-stu-id="98fae-124">1</span></span>  <br/> |
|<span data-ttu-id="98fae-125">3 </span><span class="sxs-lookup"><span data-stu-id="98fae-125">3</span></span>  <br/> |<span data-ttu-id="98fae-126">3 </span><span class="sxs-lookup"><span data-stu-id="98fae-126">3</span></span>  <br/> |
|<span data-ttu-id="98fae-127">4 </span><span class="sxs-lookup"><span data-stu-id="98fae-127">4</span></span>  <br/> |<span data-ttu-id="98fae-128">3 </span><span class="sxs-lookup"><span data-stu-id="98fae-128">3</span></span>  <br/> |
|<span data-ttu-id="98fae-129">5 </span><span class="sxs-lookup"><span data-stu-id="98fae-129">5</span></span>  <br/> |<span data-ttu-id="98fae-130">4 </span><span class="sxs-lookup"><span data-stu-id="98fae-130">4</span></span>  <br/> |
|<span data-ttu-id="98fae-131">6 </span><span class="sxs-lookup"><span data-stu-id="98fae-131">6</span></span>  <br/> |<span data-ttu-id="98fae-132">5 </span><span class="sxs-lookup"><span data-stu-id="98fae-132">5</span></span>  <br/> |
|<span data-ttu-id="98fae-133">7 </span><span class="sxs-lookup"><span data-stu-id="98fae-133">7</span></span>  <br/> |<span data-ttu-id="98fae-134">5 </span><span class="sxs-lookup"><span data-stu-id="98fae-134">5</span></span>  <br/> |
|<span data-ttu-id="98fae-135">8 </span><span class="sxs-lookup"><span data-stu-id="98fae-135">8</span></span>  <br/> |<span data-ttu-id="98fae-136">6 </span><span class="sxs-lookup"><span data-stu-id="98fae-136">6</span></span>  <br/> |
|<span data-ttu-id="98fae-137">9 </span><span class="sxs-lookup"><span data-stu-id="98fae-137">9</span></span>  <br/> |<span data-ttu-id="98fae-138">7 </span><span class="sxs-lookup"><span data-stu-id="98fae-138">7</span></span>  <br/> |
|<span data-ttu-id="98fae-139">10 </span><span class="sxs-lookup"><span data-stu-id="98fae-139">10</span></span>  <br/> |<span data-ttu-id="98fae-140">8 </span><span class="sxs-lookup"><span data-stu-id="98fae-140">8</span></span>  <br/> |
|<span data-ttu-id="98fae-141">11 </span><span class="sxs-lookup"><span data-stu-id="98fae-141">11</span></span>  <br/> |<span data-ttu-id="98fae-142">9 </span><span class="sxs-lookup"><span data-stu-id="98fae-142">9</span></span>  <br/> |
|<span data-ttu-id="98fae-143">12 </span><span class="sxs-lookup"><span data-stu-id="98fae-143">12</span></span>  <br/> |<span data-ttu-id="98fae-144">10 </span><span class="sxs-lookup"><span data-stu-id="98fae-144">10</span></span>  <br/> |
|<span data-ttu-id="98fae-145">Skype for business **Server 2019 の場合は**16</span><span class="sxs-lookup"><span data-stu-id="98fae-145">16 **For Skype for Business Server 2019**</span></span> <br/> |<span data-ttu-id="98fae-146">12 </span><span class="sxs-lookup"><span data-stu-id="98fae-146">12</span></span>  <br/> |


   
<span data-ttu-id="98fae-147">今後プールが起動されるたびに、サーバーの85% が開始されます (前の表に示すように)。</span><span class="sxs-lookup"><span data-stu-id="98fae-147">Every subsequent time the pool is started, 85% of the servers should be started (as shown in the preceding table).</span></span> <span data-ttu-id="98fae-148">この数のサーバーを開始できない場合 (ただし、プールレベルのクォーラム損失が発生しないように十分な数のサーバーを起動できる場合) は、コマンドレットを使用して、 `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` このルーティンググループレベルのクォーラム損失から回復し、進行状況を発生させるためにプールを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="98fae-148">If this number of servers cannot be started (but enough servers can be started so that you are not at pool-level quorum loss), you can use the  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` cmdlet to enable the pool to recover from this routing group level quorum loss and make progress.</span></span> <span data-ttu-id="98fae-149">このコマンドレットの使用方法の詳細については、「 [reset-cspoolregistrarstate](https://docs.microsoft.com/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98fae-149">For more information about how to use this cmdlet, see [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="98fae-150">サーバー数が偶数のプールでは、Skype for Business Server はプライマリ SQL データベースをミラーリング監視として使用します。</span><span class="sxs-lookup"><span data-stu-id="98fae-150">In pools with an even number of servers, Skype for Business Server uses the Primary SQL database as Witness.</span></span> <span data-ttu-id="98fae-151">このようなプールでは、プライマリデータベースをシャットダウンし、ミラーコピーに切り替えて、前の表に従って十分な数が実行されないように十分な数のフロントエンドサーバーをシャットダウンすると、プール全体がダウンします。</span><span class="sxs-lookup"><span data-stu-id="98fae-151">In a pool like this, if you shut down the primary database and switch to the Mirror copy, and shut down enough Front End servers so that not enough are running according to the preceding table, the entire pool will go down.</span></span> <span data-ttu-id="98fae-152">詳細については、「[データベースミラーリング監視](https://go.microsoft.com/fwlink/?LinkId=393672)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98fae-152">For more information, see [Database Mirroring Witness](https://go.microsoft.com/fwlink/?LinkId=393672).</span></span> 
  
#### <a name="pool-level-quorum-loss"></a><span data-ttu-id="98fae-153">プールレベルのクォーラム損失</span><span class="sxs-lookup"><span data-stu-id="98fae-153">Pool-level quorum loss</span></span>

<span data-ttu-id="98fae-154">フロントエンドプールが完全に機能するために、プールレベルのクォーラム損失になることはありません。</span><span class="sxs-lookup"><span data-stu-id="98fae-154">For a Front End pool to function at all, it cannot be in pool-level quorum loss.</span></span> <span data-ttu-id="98fae-155">次の表に示すように、実行しているサーバーの数が機能レベルを下回っている場合、プール内の残りのサーバーはすべての Skype for Business Server サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="98fae-155">If the number of servers running falls below the functional level as shown in the following table, the remaining servers in the pool will stop all Skype for Business Server services.</span></span> <span data-ttu-id="98fae-156">次の表の番号は、プール内のバックエンドサーバーが動作していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="98fae-156">Note that the numbers in the following table assume that the Back End Servers in the pool are running.</span></span>
  
|<span data-ttu-id="98fae-157">プール内のフロントエンド サーバーの総数</span><span class="sxs-lookup"><span data-stu-id="98fae-157">Total number of Front End Servers in the pool</span></span>  <br/> |<span data-ttu-id="98fae-158">プールが機能するために実行されている必要のあるサーバーの数</span><span class="sxs-lookup"><span data-stu-id="98fae-158">Number of servers that must be running for pool to be functional</span></span>  <br/> |
|:-----|:-----|
|<span data-ttu-id="98fae-159">2 </span><span class="sxs-lookup"><span data-stu-id="98fae-159">2</span></span>  <br/> |<span data-ttu-id="98fae-160">1 </span><span class="sxs-lookup"><span data-stu-id="98fae-160">1</span></span>  <br/> |
|<span data-ttu-id="98fae-161">3-4</span><span class="sxs-lookup"><span data-stu-id="98fae-161">3-4</span></span>  <br/> |<span data-ttu-id="98fae-162">任意の2</span><span class="sxs-lookup"><span data-stu-id="98fae-162">Any 2</span></span>  <br/> |
|<span data-ttu-id="98fae-163">5-6</span><span class="sxs-lookup"><span data-stu-id="98fae-163">5-6</span></span>  <br/> |<span data-ttu-id="98fae-164">任意の3つ</span><span class="sxs-lookup"><span data-stu-id="98fae-164">Any 3</span></span>  <br/> |
|<span data-ttu-id="98fae-165">7 </span><span class="sxs-lookup"><span data-stu-id="98fae-165">7</span></span>  <br/> |<span data-ttu-id="98fae-166">任意4</span><span class="sxs-lookup"><span data-stu-id="98fae-166">Any 4</span></span>  <br/> |
|<span data-ttu-id="98fae-167">8-9</span><span class="sxs-lookup"><span data-stu-id="98fae-167">8-9</span></span>  <br/> |<span data-ttu-id="98fae-168">最初の7台のサーバーのうち4台</span><span class="sxs-lookup"><span data-stu-id="98fae-168">Any 4 of the first 7 servers</span></span>  <br/> |
|<span data-ttu-id="98fae-169">10-12</span><span class="sxs-lookup"><span data-stu-id="98fae-169">10-12</span></span>  <br/> |<span data-ttu-id="98fae-170">最初の9台のサーバーのうち5台</span><span class="sxs-lookup"><span data-stu-id="98fae-170">Any 5 of the first 9 servers</span></span>  <br/> |
|<span data-ttu-id="98fae-171">**Skype For Business Server 2019 の場合は**12-16</span><span class="sxs-lookup"><span data-stu-id="98fae-171">12-16  **For Skype for Business Server 2019**</span></span>  <br/> |<span data-ttu-id="98fae-172">最初の12台のサーバーのうち7台</span><span class="sxs-lookup"><span data-stu-id="98fae-172">Any 7 of the first 12 servers</span></span>  <br/> |
   
<span data-ttu-id="98fae-173">上記の表では、最初にプールが開始されたときに、最初に開始されたサーバーが "最初のサーバー" です。</span><span class="sxs-lookup"><span data-stu-id="98fae-173">In the preceding table, the "first servers" are the servers which were brought up first, chronologically, when the pool was started for the first time.</span></span> <span data-ttu-id="98fae-174">これらのサーバーを決定するには、 `Get-CsComputer` オプションでコマンドレットを使用でき `-PoolFqdn` ます。</span><span class="sxs-lookup"><span data-stu-id="98fae-174">To determine these servers, you can use the  `Get-CsComputer` cmdlet with the `-PoolFqdn` option.</span></span> <span data-ttu-id="98fae-175">このコマンドレットでは、トポロジに表示される順序でサーバーが表示され、一覧の一番上にあるサーバーが最初のサーバーになります。</span><span class="sxs-lookup"><span data-stu-id="98fae-175">This cmdlet will show the servers in the order that they appear in the topology, and the ones at the top of the list are the first servers.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="98fae-176">[Skype For Business Server 2019](https://docs.microsoft.com/skypeforbusiness/plan/user-model-2019)では、フロントエンドサーバーの最大数が16に増加しています。</span><span class="sxs-lookup"><span data-stu-id="98fae-176">The maximum number of front end servers has been increased to 16 in [Skype for Business Server 2019](https://docs.microsoft.com/skypeforbusiness/plan/user-model-2019)</span></span>
> 
#### <a name="additional-steps-to-ensure-pools-are-functional"></a><span data-ttu-id="98fae-177">プールが機能していることを確認するための追加の手順</span><span class="sxs-lookup"><span data-stu-id="98fae-177">Additional steps to ensure pools are functional</span></span>

<span data-ttu-id="98fae-178">フロントエンドプールが機能していることを確認するには、他にもいくつかの要因を監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98fae-178">You should watch for a couple of other factors to ensure that your Front End pools remain functional.</span></span>
  
- <span data-ttu-id="98fae-179">ユーザーをプールに初めて移動するときは、少なくとも3台のフロントエンドサーバーが稼働していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="98fae-179">When you move users to the pool for the first time, be sure at least three of the Front End Servers are running.</span></span>
    
- <span data-ttu-id="98fae-180">このプールと障害復旧のために別のプールとの間にペアリング関係を確立している場合は、その関係を確立した後で、その関係を確立した後、データをバックアッププールと同期するために、同時に3台のフロントエンドサーバーがこのプールに存在することを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98fae-180">If you establish a pairing relationship between this pool and another pool for disaster recovery purposes, then after establishing that relationship you must be sure this pool has three Front End servers running simultaneously at some time to properly synchronize data with the backup pool.</span></span> <span data-ttu-id="98fae-181">プールのペアリングと障害復旧機能の詳細については、「 [Plan for high availability and disaster recovery In Skype For Business Server](high-availability-and-disaster-recovery.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98fae-181">For more information on pool pairing and disaster recovery features, see [Plan for high availability and disaster recovery in Skype for Business Server](high-availability-and-disaster-recovery.md).</span></span> 
    
## <a name="front-end-pool-with-two-front-end-servers"></a><span data-ttu-id="98fae-182">2台のフロントエンドサーバーを備えたフロントエンドプール</span><span class="sxs-lookup"><span data-stu-id="98fae-182">Front End pool with two Front End servers</span></span>

<span data-ttu-id="98fae-183">2台のフロントエンドサーバーのみが含まれるフロントエンドプールを展開することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="98fae-183">We do not recommend deploying a Front End pool that contains only two Front End Servers.</span></span> <span data-ttu-id="98fae-184">この小規模プールでは、より大規模なプールのような高可用性ソリューションは提供されません。また、管理に特に注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="98fae-184">This small pool will not provide a robust high-availability solution like a larger pool would, and needs extra care in managing.</span></span> <span data-ttu-id="98fae-185">さらに、2台のサーバープールのバックエンドサーバーがダウンした場合は、プール全体がすぐに停止する可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="98fae-185">Additionally, if the Back End Server of a two-server pool went down, the whole pool itself would likely soon go down as well.</span></span> <span data-ttu-id="98fae-186">Skype for Business Server を実行している1台または2台のサーバーのみを展開する場合は、Standard Edition サーバーとして展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="98fae-186">If you want to deploy just one or two servers running Skype for Business Server, we recommend you deploy them as Standard Edition servers.</span></span>
  
<span data-ttu-id="98fae-187">2台のフロントエンドサーバーでプールを展開する必要がある場合は、次のガイドラインに従ってください。</span><span class="sxs-lookup"><span data-stu-id="98fae-187">If you do ever need to deploy a pool with two Front End Servers, follow these guidelines:</span></span>
  
- <span data-ttu-id="98fae-188">2台のフロントエンドサーバーのうち1台がダウンした場合は、障害が発生したサーバーをできるだけ早く復旧するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="98fae-188">If one of the two Front End Servers goes down, you should try to bring the failed server back up as soon as you can.</span></span> <span data-ttu-id="98fae-189">同様に、2台のサーバーのいずれかをアップグレードする必要がある場合は、アップグレードが完了したらすぐにオンラインに戻します。</span><span class="sxs-lookup"><span data-stu-id="98fae-189">Similarly, if you need to upgrade one of the two servers, bring it back online as soon as the upgrade is finished.</span></span>
    
- <span data-ttu-id="98fae-190">何らかの理由で両方のサーバーを同時に停止する必要がある場合は、プールのダウンタイムが終了したら、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="98fae-190">If for some reason you need to bring both servers down at the same time, do the following when the downtime for the pool is finished:</span></span>
    
  - <span data-ttu-id="98fae-191">ベストプラクティスは、両方のフロントエンドサーバーを同時に再起動することです。</span><span class="sxs-lookup"><span data-stu-id="98fae-191">The best practice is to restart both Front End Servers at the same time.</span></span> 
    
  - <span data-ttu-id="98fae-192">2台のサーバーを同時に再起動できない場合は、停止した順序とは逆の順序でバックアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="98fae-192">If the two servers cannot be restarted at the same time, you should bring them back up in the reverse order of the order they went down.</span></span>
    
  - <span data-ttu-id="98fae-193">その順序で復元できない場合は、プールを復旧する前に、次のコマンドレットを使用します。`Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`</span><span class="sxs-lookup"><span data-stu-id="98fae-193">If you cannot bring them back up in that order, then use the following cmdlet before bringing the pool back up:  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`</span></span>
    
## <a name="front-end-pool-configuration-failures-and-changes"></a><span data-ttu-id="98fae-194">フロントエンドプール構成のエラーと変更</span><span class="sxs-lookup"><span data-stu-id="98fae-194">Front End pool configuration failures and changes</span></span>

<span data-ttu-id="98fae-195">フロントエンドサーバーに障害が発生した場合、数日間またはそれ以上の交換が必要になる可能性がある場合は、サーバーをトポロジから削除します。</span><span class="sxs-lookup"><span data-stu-id="98fae-195">If a Front End server fails and is unlikely to be replaced for a few days or more, remove the server from the topology.</span></span> <span data-ttu-id="98fae-196">再び使用できるようになったら、新しいフロントエンドサーバーをトポロジに追加します。</span><span class="sxs-lookup"><span data-stu-id="98fae-196">Add the new Front End server to the topology when it is available again.</span></span>
  
<span data-ttu-id="98fae-197">サーバーの追加や削除など、フロントエンドプールに構成の変更を行う場合は、次のガイドラインに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="98fae-197">Whenever you make a configuration change to a Front End pool, such as adding or removing servers, you must follow these guidelines:</span></span>
  
- <span data-ttu-id="98fae-198">新しいトポロジが公開されたら、プール内の各フロントエンドサーバーを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98fae-198">After the new topology has been published, you must restart each Front End server in the pool.</span></span> <span data-ttu-id="98fae-199">一度に1つずつ再起動します。</span><span class="sxs-lookup"><span data-stu-id="98fae-199">Restart them one at a time.</span></span>
    
- <span data-ttu-id="98fae-200">構成の変更中にプール全体がダウンしていた場合は、新しいトポロジが公開された後、次のコマンドレットを実行します。`Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`</span><span class="sxs-lookup"><span data-stu-id="98fae-200">If the entire pool has been down during the configuration change, then run the following cmdlet after the new topology is published:  `Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`</span></span>
    

