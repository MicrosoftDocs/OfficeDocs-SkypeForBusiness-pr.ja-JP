---
title: フロントエンド プールの高可用性と管理
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: 2 つのフロントエンド サーバーのみを使用するプールのプール、クォーラム損失、特別な手順の管理など、Skype for Business Server のフロントエンド プール管理について説明します。
ms.openlocfilehash: 47e4b2157961a2856256e3d96a0676dd86d3f996
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093075"
---
# <a name="front-end-pool-high-availability-and-management"></a><span data-ttu-id="a14ec-103">フロントエンド プールの高可用性と管理</span><span class="sxs-lookup"><span data-stu-id="a14ec-103">Front End Pool high availability and management</span></span>
 
<span data-ttu-id="a14ec-104">2 つのフロントエンド サーバーのみを使用するプールのプール、クォーラム損失、特別な手順の管理など、Skype for Business Server のフロントエンド プール管理について説明します。</span><span class="sxs-lookup"><span data-stu-id="a14ec-104">Learn about Front End pool management in Skype for Business Server, including managing pools, quorum loss, and special steps for pools with only two Front End Servers.</span></span>
  
<span data-ttu-id="a14ec-105">Skype for Business Server では、フロントエンド プールのアーキテクチャでは分散システム モデルが使用され、各ユーザーのデータはプール内の 3 つのフロントエンド サーバーに保持されます。</span><span class="sxs-lookup"><span data-stu-id="a14ec-105">In Skype for Business Server, the architecture of Front End pools uses a distributed systems model, with each user's data kept on as many as three Front End Servers in the pool.</span></span> <span data-ttu-id="a14ec-106">すべての Enterprise Edition フロントエンド プールに少なくとも 3 つのフロント エンド サーバーを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="a14ec-106">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers.</span></span>

> [!NOTE]
> <span data-ttu-id="a14ec-107">Skype for Business Server 2019 は、2 台のフロント エンド サーバーを持つ Enterprise Edition フロントエンド プールをサポートしていないので、そのシナリオではトポロジを公開できません。</span><span class="sxs-lookup"><span data-stu-id="a14ec-107">Skype for Business Server 2019 does not support Enterprise Edition Front End pools with two Front End Servers, and will not allow the topology to be published in that scenario.</span></span>
  
## <a name="planning-for-the-management-of-front-end-pools"></a><span data-ttu-id="a14ec-108">フロントエンド プールの管理の計画</span><span class="sxs-lookup"><span data-stu-id="a14ec-108">Planning for the management of Front End pools</span></span>

 <span data-ttu-id="a14ec-109">Skype for Business Server は、Windows Fabric に基づく分散システム モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="a14ec-109">Skype for Business Server uses a distributed systems model based on Windows Fabric.</span></span> <span data-ttu-id="a14ec-110">このモデルでは、ユーザーと会議ごとに重要なデータが、フロントエンド プール内の 3 つのフロントエンド サーバーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="a14ec-110">In this model, important data for each user and conference is stored on three Front End Servers in a Front End pool.</span></span> <span data-ttu-id="a14ec-111">データの特定のセットを格納するこれら 3 つのサーバーは、replicas と呼ばれる。</span><span class="sxs-lookup"><span data-stu-id="a14ec-111">These three servers storing a certain set of data are calledreplicas.</span></span>
  
<span data-ttu-id="a14ec-112">フロントエンド プールの分散モデルでは、プールが機能するために、プールのサーバーの特定の数が実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a14ec-112">With the distributed model for Front End pools, a certain numbers of a pool's servers must be running for the pool to function.</span></span> <span data-ttu-id="a14ec-113">プールには 2 つの損失モードがあります。</span><span class="sxs-lookup"><span data-stu-id="a14ec-113">There are two loss modes for a pool.</span></span>
  
- <span data-ttu-id="a14ec-114">ルーティング グループ レベルのクォーラム損失(特定のルーティング グループのレプリカ サーバーが不十分な場合)。</span><span class="sxs-lookup"><span data-stu-id="a14ec-114">Routing Group Level quorum loss, caused by not enough replica servers for a particular routing group.</span></span> <span data-ttu-id="a14ec-115">ルーティング グループは、プールに含む一連のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="a14ec-115">A routing group is a set of users homed in the pool.</span></span> <span data-ttu-id="a14ec-116">各ルーティング グループには、プール内に 3 つのレプリカ (1 つのプライマリ レプリカと 2 つのセカンダリ レプリカ) があります。</span><span class="sxs-lookup"><span data-stu-id="a14ec-116">Each routing group has three replicas in the pool: one primary replica and two secondary replicas.</span></span>
    
- <span data-ttu-id="a14ec-117">プール レベルのクォーラムの損失 。プールで十分なシード サーバーが実行されていない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="a14ec-117">Pool Level quorum loss, caused when not enough seed servers are running in the pool.</span></span> 
    
### <a name="routing-group-level-quorum-loss"></a><span data-ttu-id="a14ec-118">ルーティング グループ レベルのクォーラム損失</span><span class="sxs-lookup"><span data-stu-id="a14ec-118">Routing Group Level quorum loss</span></span>

<span data-ttu-id="a14ec-119">新しいフロントエンド プールを初めて起動する場合、次の表に示すように、サーバーの 85% が稼働中であることが不可欠です。</span><span class="sxs-lookup"><span data-stu-id="a14ec-119">The first time you start a new Front End pool, it is essential that 85% of the servers are up and running, as shown in the following table.</span></span> <span data-ttu-id="a14ec-120">実行中のサーバーが少ない場合、サービスが開始状態でスタックし、プールが起動しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a14ec-120">If fewer servers are running, the services might be stuck in the starting state and the pool might not start.</span></span>
  
|<span data-ttu-id="a14ec-121">プール内のサーバーの総数</span><span class="sxs-lookup"><span data-stu-id="a14ec-121">Total number of servers in the pool</span></span>  <br/> |<span data-ttu-id="a14ec-122">プールを初めて開始するために実行する必要がありますサーバーの数</span><span class="sxs-lookup"><span data-stu-id="a14ec-122">Number of servers that must be running for the pool to be started the first time</span></span>  <br/> |
|:-----|:-----|
|<span data-ttu-id="a14ec-123">2</span><span class="sxs-lookup"><span data-stu-id="a14ec-123">2</span></span>  <br/> |<span data-ttu-id="a14ec-124">1</span><span class="sxs-lookup"><span data-stu-id="a14ec-124">1</span></span>  <br/> |
|<span data-ttu-id="a14ec-125">3</span><span class="sxs-lookup"><span data-stu-id="a14ec-125">3</span></span>  <br/> |<span data-ttu-id="a14ec-126">3</span><span class="sxs-lookup"><span data-stu-id="a14ec-126">3</span></span>  <br/> |
|<span data-ttu-id="a14ec-127">4</span><span class="sxs-lookup"><span data-stu-id="a14ec-127">4</span></span>  <br/> |<span data-ttu-id="a14ec-128">3</span><span class="sxs-lookup"><span data-stu-id="a14ec-128">3</span></span>  <br/> |
|<span data-ttu-id="a14ec-129">5</span><span class="sxs-lookup"><span data-stu-id="a14ec-129">5</span></span>  <br/> |<span data-ttu-id="a14ec-130">4</span><span class="sxs-lookup"><span data-stu-id="a14ec-130">4</span></span>  <br/> |
|<span data-ttu-id="a14ec-131">6</span><span class="sxs-lookup"><span data-stu-id="a14ec-131">6</span></span>  <br/> |<span data-ttu-id="a14ec-132">5</span><span class="sxs-lookup"><span data-stu-id="a14ec-132">5</span></span>  <br/> |
|<span data-ttu-id="a14ec-133">7</span><span class="sxs-lookup"><span data-stu-id="a14ec-133">7</span></span>  <br/> |<span data-ttu-id="a14ec-134">5</span><span class="sxs-lookup"><span data-stu-id="a14ec-134">5</span></span>  <br/> |
|<span data-ttu-id="a14ec-135">8</span><span class="sxs-lookup"><span data-stu-id="a14ec-135">8</span></span>  <br/> |<span data-ttu-id="a14ec-136">6</span><span class="sxs-lookup"><span data-stu-id="a14ec-136">6</span></span>  <br/> |
|<span data-ttu-id="a14ec-137">9</span><span class="sxs-lookup"><span data-stu-id="a14ec-137">9</span></span>  <br/> |<span data-ttu-id="a14ec-138">7</span><span class="sxs-lookup"><span data-stu-id="a14ec-138">7</span></span>  <br/> |
|<span data-ttu-id="a14ec-139">10</span><span class="sxs-lookup"><span data-stu-id="a14ec-139">10</span></span>  <br/> |<span data-ttu-id="a14ec-140">8</span><span class="sxs-lookup"><span data-stu-id="a14ec-140">8</span></span>  <br/> |
|<span data-ttu-id="a14ec-141">11</span><span class="sxs-lookup"><span data-stu-id="a14ec-141">11</span></span>  <br/> |<span data-ttu-id="a14ec-142">9</span><span class="sxs-lookup"><span data-stu-id="a14ec-142">9</span></span>  <br/> |
|<span data-ttu-id="a14ec-143">12 </span><span class="sxs-lookup"><span data-stu-id="a14ec-143">12</span></span>  <br/> |<span data-ttu-id="a14ec-144">10</span><span class="sxs-lookup"><span data-stu-id="a14ec-144">10</span></span>  <br/> |
|<span data-ttu-id="a14ec-145">16 **For Skype for Business Server 2019**</span><span class="sxs-lookup"><span data-stu-id="a14ec-145">16 **For Skype for Business Server 2019**</span></span> <br/> |<span data-ttu-id="a14ec-146">12 </span><span class="sxs-lookup"><span data-stu-id="a14ec-146">12</span></span>  <br/> |


   
<span data-ttu-id="a14ec-147">それ以降、プールが開始されるごとに、サーバーの 85% を開始する必要があります (前の表に示すように)。</span><span class="sxs-lookup"><span data-stu-id="a14ec-147">Every subsequent time the pool is started, 85% of the servers should be started (as shown in the preceding table).</span></span> <span data-ttu-id="a14ec-148">この数のサーバーを開始できない場合 (ただし、プール レベルのクォーラム損失が発生しないので十分なサーバーを開始できます)、このコマンドレットを使用して、このルーティング グループ レベルのクォーラム損失からプールを回復し、進行状況を確認できます。 `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery`</span><span class="sxs-lookup"><span data-stu-id="a14ec-148">If this number of servers cannot be started (but enough servers can be started so that you are not at pool-level quorum loss), you can use the  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` cmdlet to enable the pool to recover from this routing group level quorum loss and make progress.</span></span> <span data-ttu-id="a14ec-149">このコマンドレットの使用方法の詳細については [、「Reset-CsPoolRegistrarState」を参照してください](/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="a14ec-149">For more information about how to use this cmdlet, see [Reset-CsPoolRegistrarState](/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a14ec-150">サーバーの数が 1 つでも多いプールでは、Skype for Business Server はプライマリ サーバー データベースSQLミラーリング監視として使用します。</span><span class="sxs-lookup"><span data-stu-id="a14ec-150">In pools with an even number of servers, Skype for Business Server uses the Primary SQL database as Witness.</span></span> <span data-ttu-id="a14ec-151">このようなプールでは、プライマリ データベースをシャットダウンしてミラー コピーに切り替えて、前の表に従って十分に実行されない十分なフロントエンド サーバーをシャットダウンすると、プール全体がダウンします。</span><span class="sxs-lookup"><span data-stu-id="a14ec-151">In a pool like this, if you shut down the primary database and switch to the Mirror copy, and shut down enough Front End servers so that not enough are running according to the preceding table, the entire pool will go down.</span></span> <span data-ttu-id="a14ec-152">詳細については、「データベース ミラーリング [監視」を参照してください](/sql/database-engine/database-mirroring/database-mirroring-witness)。</span><span class="sxs-lookup"><span data-stu-id="a14ec-152">For more information, see [Database Mirroring Witness](/sql/database-engine/database-mirroring/database-mirroring-witness).</span></span> 
  
#### <a name="pool-level-quorum-loss"></a><span data-ttu-id="a14ec-153">プール レベルのクォーラム損失</span><span class="sxs-lookup"><span data-stu-id="a14ec-153">Pool-level quorum loss</span></span>

<span data-ttu-id="a14ec-154">フロントエンド プールが全く機能するには、プール レベルのクォーラム損失にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a14ec-154">For a Front End pool to function at all, it cannot be in pool-level quorum loss.</span></span> <span data-ttu-id="a14ec-155">次の表に示すように、実行中のサーバーの数が機能レベルを下回った場合、プール内の残りのサーバーは、すべての Skype for Business Server サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="a14ec-155">If the number of servers running falls below the functional level as shown in the following table, the remaining servers in the pool will stop all Skype for Business Server services.</span></span> <span data-ttu-id="a14ec-156">次の表の数値では、プール内のバック エンド サーバーが実行されている前提に注意してください。</span><span class="sxs-lookup"><span data-stu-id="a14ec-156">Note that the numbers in the following table assume that the Back End Servers in the pool are running.</span></span>
  
|<span data-ttu-id="a14ec-157">プール内のフロントエンド サーバーの総数</span><span class="sxs-lookup"><span data-stu-id="a14ec-157">Total number of Front End Servers in the pool</span></span>  <br/> |<span data-ttu-id="a14ec-158">プールが機能するために実行されている必要のあるサーバーの数</span><span class="sxs-lookup"><span data-stu-id="a14ec-158">Number of servers that must be running for pool to be functional</span></span>  <br/> |
|:-----|:-----|
|<span data-ttu-id="a14ec-159">2</span><span class="sxs-lookup"><span data-stu-id="a14ec-159">2</span></span>  <br/> |<span data-ttu-id="a14ec-160">1</span><span class="sxs-lookup"><span data-stu-id="a14ec-160">1</span></span>  <br/> |
|<span data-ttu-id="a14ec-161">3-4</span><span class="sxs-lookup"><span data-stu-id="a14ec-161">3-4</span></span>  <br/> |<span data-ttu-id="a14ec-162">Any 2</span><span class="sxs-lookup"><span data-stu-id="a14ec-162">Any 2</span></span>  <br/> |
|<span data-ttu-id="a14ec-163">5-6</span><span class="sxs-lookup"><span data-stu-id="a14ec-163">5-6</span></span>  <br/> |<span data-ttu-id="a14ec-164">Any 3</span><span class="sxs-lookup"><span data-stu-id="a14ec-164">Any 3</span></span>  <br/> |
|<span data-ttu-id="a14ec-165">7</span><span class="sxs-lookup"><span data-stu-id="a14ec-165">7</span></span>  <br/> |<span data-ttu-id="a14ec-166">Any 4</span><span class="sxs-lookup"><span data-stu-id="a14ec-166">Any 4</span></span>  <br/> |
|<span data-ttu-id="a14ec-167">8-9</span><span class="sxs-lookup"><span data-stu-id="a14ec-167">8-9</span></span>  <br/> |<span data-ttu-id="a14ec-168">最初の 7 つのサーバーの 4 つ</span><span class="sxs-lookup"><span data-stu-id="a14ec-168">Any 4 of the first 7 servers</span></span>  <br/> |
|<span data-ttu-id="a14ec-169">10-12</span><span class="sxs-lookup"><span data-stu-id="a14ec-169">10-12</span></span>  <br/> |<span data-ttu-id="a14ec-170">最初の 9 つのサーバーの 5 つ</span><span class="sxs-lookup"><span data-stu-id="a14ec-170">Any 5 of the first 9 servers</span></span>  <br/> |
|<span data-ttu-id="a14ec-171">12-16  **Skype for Business Server 2019**</span><span class="sxs-lookup"><span data-stu-id="a14ec-171">12-16  **For Skype for Business Server 2019**</span></span>  <br/> |<span data-ttu-id="a14ec-172">最初の 12 台のサーバーの 7 つ</span><span class="sxs-lookup"><span data-stu-id="a14ec-172">Any 7 of the first 12 servers</span></span>  <br/> |
   
<span data-ttu-id="a14ec-173">前の表では、"最初のサーバー" は、プールが初めて開始された最初に、時系列的に起動されたサーバーです。</span><span class="sxs-lookup"><span data-stu-id="a14ec-173">In the preceding table, the "first servers" are the servers which were brought up first, chronologically, when the pool was started for the first time.</span></span> <span data-ttu-id="a14ec-174">これらのサーバーを確認するには、オプションで  `Get-CsComputer` コマンドレットを使用 `-PoolFqdn` できます。</span><span class="sxs-lookup"><span data-stu-id="a14ec-174">To determine these servers, you can use the  `Get-CsComputer` cmdlet with the `-PoolFqdn` option.</span></span> <span data-ttu-id="a14ec-175">このコマンドレットは、サーバーがトポロジに表示される順序で表示され、一覧の上部にあるサーバーが最初のサーバーになります。</span><span class="sxs-lookup"><span data-stu-id="a14ec-175">This cmdlet will show the servers in the order that they appear in the topology, and the ones at the top of the list are the first servers.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a14ec-176">Skype [for Business Server 2019](../../../SfBServer2019/plan/user-model-2019.md)のフロントエンド サーバーの最大数が 16 に増加しました</span><span class="sxs-lookup"><span data-stu-id="a14ec-176">The maximum number of front end servers has been increased to 16 in [Skype for Business Server 2019](../../../SfBServer2019/plan/user-model-2019.md)</span></span>
> 
#### <a name="additional-steps-to-ensure-pools-are-functional"></a><span data-ttu-id="a14ec-177">プールが機能する追加の手順</span><span class="sxs-lookup"><span data-stu-id="a14ec-177">Additional steps to ensure pools are functional</span></span>

<span data-ttu-id="a14ec-178">フロントエンド プールが機能を維持するために、いくつかの他の要因を監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a14ec-178">You should watch for a couple of other factors to ensure that your Front End pools remain functional.</span></span>
  
- <span data-ttu-id="a14ec-179">ユーザーを初めてプールに移動する場合は、少なくとも 3 つのフロント エンド サーバーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a14ec-179">When you move users to the pool for the first time, be sure at least three of the Front End Servers are running.</span></span>
    
- <span data-ttu-id="a14ec-180">障害復旧のためにこのプールと別のプールの間にペアリング関係を確立する場合、その関係を確立した後、このプールに 3 つのフロントエンド サーバーが同時に実行されていることを確認して、データをバックアップ プールと適切に同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a14ec-180">If you establish a pairing relationship between this pool and another pool for disaster recovery purposes, then after establishing that relationship you must be sure this pool has three Front End servers running simultaneously at some time to properly synchronize data with the backup pool.</span></span> <span data-ttu-id="a14ec-181">プールのペアリングと障害復旧機能の詳細については、「Skype for Business Server で高可用性と障害復旧を計画する [」を参照してください](high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="a14ec-181">For more information on pool pairing and disaster recovery features, see [Plan for high availability and disaster recovery in Skype for Business Server](high-availability-and-disaster-recovery.md).</span></span> 
    
## <a name="front-end-pool-with-two-front-end-servers"></a><span data-ttu-id="a14ec-182">2 台のフロント エンド サーバーを備え、フロントエンド プール</span><span class="sxs-lookup"><span data-stu-id="a14ec-182">Front End pool with two Front End servers</span></span>

<span data-ttu-id="a14ec-183">2 つのフロントエンド サーバーのみを含むフロントエンド プールを展開することをお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="a14ec-183">We do not recommend deploying a Front End pool that contains only two Front End Servers.</span></span> <span data-ttu-id="a14ec-184">この小さなプールでは、大規模なプールのように堅牢な高可用性ソリューションは提供されないので、管理に特別な注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="a14ec-184">This small pool will not provide a robust high-availability solution like a larger pool would, and needs extra care in managing.</span></span> <span data-ttu-id="a14ec-185">さらに、2 サーバー プールのバック エンド サーバーがダウンした場合、プール全体もすぐにダウンする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a14ec-185">Additionally, if the Back End Server of a two-server pool went down, the whole pool itself would likely soon go down as well.</span></span> <span data-ttu-id="a14ec-186">Skype for Business Server を実行している 1 台または 2 台のサーバーを展開する場合は、Standard Edition サーバーとして展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a14ec-186">If you want to deploy just one or two servers running Skype for Business Server, we recommend you deploy them as Standard Edition servers.</span></span>
  
<span data-ttu-id="a14ec-187">2 つのフロント エンド サーバーを使用してプールを展開する必要がある場合は、次のガイドラインに従います。</span><span class="sxs-lookup"><span data-stu-id="a14ec-187">If you do ever need to deploy a pool with two Front End Servers, follow these guidelines:</span></span>
  
- <span data-ttu-id="a14ec-188">2 つのフロント エンド サーバーの 1 つがダウンした場合は、できるだけ早く障害が発生したサーバーをバックアップしてください。</span><span class="sxs-lookup"><span data-stu-id="a14ec-188">If one of the two Front End Servers goes down, you should try to bring the failed server back up as soon as you can.</span></span> <span data-ttu-id="a14ec-189">同様に、2 台のサーバーのいずれかをアップグレードする必要がある場合は、アップグレードが完了するとすぐにオンラインに戻します。</span><span class="sxs-lookup"><span data-stu-id="a14ec-189">Similarly, if you need to upgrade one of the two servers, bring it back online as soon as the upgrade is finished.</span></span>
    
- <span data-ttu-id="a14ec-190">何らかの理由で両方のサーバーを同時にダウンする必要がある場合は、プールのダウンタイムが終了したら、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a14ec-190">If for some reason you need to bring both servers down at the same time, do the following when the downtime for the pool is finished:</span></span>
    
  - <span data-ttu-id="a14ec-191">ベスト プラクティスは、両方のフロントエンド サーバーを同時に再起動する方法です。</span><span class="sxs-lookup"><span data-stu-id="a14ec-191">The best practice is to restart both Front End Servers at the same time.</span></span> 
    
  - <span data-ttu-id="a14ec-192">2 台のサーバーを同時に再起動できない場合は、ダウンした順序の逆の順序でサーバーを元に戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="a14ec-192">If the two servers cannot be restarted at the same time, you should bring them back up in the reverse order of the order they went down.</span></span>
    
  - <span data-ttu-id="a14ec-193">その順序でバックアップできない場合は、プールをバックアップする前に次のコマンドレットを使用します。  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`</span><span class="sxs-lookup"><span data-stu-id="a14ec-193">If you cannot bring them back up in that order, then use the following cmdlet before bringing the pool back up:  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`</span></span>
    
## <a name="front-end-pool-configuration-failures-and-changes"></a><span data-ttu-id="a14ec-194">フロントエンド プールの構成の失敗と変更</span><span class="sxs-lookup"><span data-stu-id="a14ec-194">Front End pool configuration failures and changes</span></span>

<span data-ttu-id="a14ec-195">フロントエンド サーバーが失敗し、数日以上交換される可能性が低い場合は、トポロジからサーバーを削除します。</span><span class="sxs-lookup"><span data-stu-id="a14ec-195">If a Front End server fails and is unlikely to be replaced for a few days or more, remove the server from the topology.</span></span> <span data-ttu-id="a14ec-196">新しいフロントエンド サーバーをトポロジに追加します。このサーバーが再び使用できる場合は、トポロジに追加します。</span><span class="sxs-lookup"><span data-stu-id="a14ec-196">Add the new Front End server to the topology when it is available again.</span></span>
  
<span data-ttu-id="a14ec-197">サーバーの追加や削除など、フロントエンド プールに構成を変更するたびに、次のガイドラインに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="a14ec-197">Whenever you make a configuration change to a Front End pool, such as adding or removing servers, you must follow these guidelines:</span></span>
  
- <span data-ttu-id="a14ec-198">新しいトポロジが公開された後、プール内の各フロントエンド サーバーを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a14ec-198">After the new topology has been published, you must restart each Front End server in the pool.</span></span> <span data-ttu-id="a14ec-199">一度に 1 つ再起動します。</span><span class="sxs-lookup"><span data-stu-id="a14ec-199">Restart them one at a time.</span></span>
    
- <span data-ttu-id="a14ec-200">構成変更中にプール全体がダウンしている場合は、新しいトポロジが公開された後に次のコマンドレットを実行します。  `Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`</span><span class="sxs-lookup"><span data-stu-id="a14ec-200">If the entire pool has been down during the configuration change, then run the following cmdlet after the new topology is published:  `Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`</span></span>
