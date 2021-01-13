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
description: プールの管理、クォーラム損失、および 2 台のフロントエンド サーバーのみを持つプールの特別な手順など、Skype for Business Server でのフロントエンド プールの管理について説明します。
ms.openlocfilehash: 3f1924b7a8ad26b880f8674ada4f0c99a1bc4596
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802797"
---
# <a name="front-end-pool-high-availability-and-management"></a><span data-ttu-id="a55a7-103">フロントエンド プールの高可用性と管理</span><span class="sxs-lookup"><span data-stu-id="a55a7-103">Front End Pool high availability and management</span></span>
 
<span data-ttu-id="a55a7-104">プールの管理、クォーラム損失、および 2 台のフロントエンド サーバーのみを持つプールの特別な手順など、Skype for Business Server でのフロントエンド プールの管理について説明します。</span><span class="sxs-lookup"><span data-stu-id="a55a7-104">Learn about Front End pool management in Skype for Business Server, including managing pools, quorum loss, and special steps for pools with only two Front End Servers.</span></span>
  
<span data-ttu-id="a55a7-105">Skype for Business Server では、フロントエンド プールのアーキテクチャは分散システム モデルを使用し、各ユーザーのデータはプール内の 3 つのフロントエンド サーバーに保持されます。</span><span class="sxs-lookup"><span data-stu-id="a55a7-105">In Skype for Business Server, the architecture of Front End pools uses a distributed systems model, with each user's data kept on as many as three Front End Servers in the pool.</span></span> <span data-ttu-id="a55a7-106">すべての Enterprise Edition フロントエンド プールには、少なくとも 3 つのフロントエンド サーバーを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="a55a7-106">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers.</span></span>

> [!NOTE]
> <span data-ttu-id="a55a7-107">Skype for Business Server 2019 は、2 台のフロント エンド サーバーを持つ Enterprise Edition フロントエンド プールをサポートしていないので、そのシナリオでトポロジを公開できません。</span><span class="sxs-lookup"><span data-stu-id="a55a7-107">Skype for Business Server 2019 does not support Enterprise Edition Front End pools with two Front End Servers, and will not allow the topology to be published in that scenario.</span></span>
  
## <a name="planning-for-the-management-of-front-end-pools"></a><span data-ttu-id="a55a7-108">フロントエンド プールの管理の計画</span><span class="sxs-lookup"><span data-stu-id="a55a7-108">Planning for the management of Front End pools</span></span>

 <span data-ttu-id="a55a7-109">Skype for Business Server は、Windows Fabric に基づく分散システム モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="a55a7-109">Skype for Business Server uses a distributed systems model based on Windows Fabric.</span></span> <span data-ttu-id="a55a7-110">このモデルでは、各ユーザーおよび会議の重要なデータは、フロントエンド プール内の 3 つのフロントエンド サーバーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="a55a7-110">In this model, important data for each user and conference is stored on three Front End Servers in a Front End pool.</span></span> <span data-ttu-id="a55a7-111">特定のデータ セットを格納するこれら 3 つのサーバーは、replicas と呼ばれる名前です。</span><span class="sxs-lookup"><span data-stu-id="a55a7-111">These three servers storing a certain set of data are calledreplicas.</span></span>
  
<span data-ttu-id="a55a7-112">フロントエンド プールの分散モデルでは、プールが機能するには、プールのサーバーの特定の数が実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a55a7-112">With the distributed model for Front End pools, a certain numbers of a pool's servers must be running for the pool to function.</span></span> <span data-ttu-id="a55a7-113">プールには 2 つの損失モードがあります。</span><span class="sxs-lookup"><span data-stu-id="a55a7-113">There are two loss modes for a pool.</span></span>
  
- <span data-ttu-id="a55a7-114">ルーティング グループ レベルクォーラム損失。特定のルーティング グループのレプリカ サーバーが不十分な場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="a55a7-114">Routing Group Level quorum loss, caused by not enough replica servers for a particular routing group.</span></span> <span data-ttu-id="a55a7-115">ルーティング グループは、プールにホームとして設定されているユーザーのセットです。</span><span class="sxs-lookup"><span data-stu-id="a55a7-115">A routing group is a set of users homed in the pool.</span></span> <span data-ttu-id="a55a7-116">各ルーティング グループには、プール内に 3 つのレプリカ (1 つのプライマリ レプリカと 2 つのセカンダリ レプリカ) があります。</span><span class="sxs-lookup"><span data-stu-id="a55a7-116">Each routing group has three replicas in the pool: one primary replica and two secondary replicas.</span></span>
    
- <span data-ttu-id="a55a7-117">プール レベルクォーラム損失。プールで十分なシード サーバーが実行されていない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="a55a7-117">Pool Level quorum loss, caused when not enough seed servers are running in the pool.</span></span> 
    
### <a name="routing-group-level-quorum-loss"></a><span data-ttu-id="a55a7-118">ルーティング グループ レベルクォーラム損失</span><span class="sxs-lookup"><span data-stu-id="a55a7-118">Routing Group Level quorum loss</span></span>

<span data-ttu-id="a55a7-119">新しいフロントエンド プールを初めて起動する場合は、次の表に示すように、サーバーの 85% が稼働状態であることが重要です。</span><span class="sxs-lookup"><span data-stu-id="a55a7-119">The first time you start a new Front End pool, it is essential that 85% of the servers are up and running, as shown in the following table.</span></span> <span data-ttu-id="a55a7-120">実行中のサーバーが少ない場合は、サービスが開始状態でスタックし、プールが開始されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a55a7-120">If fewer servers are running, the services might be stuck in the starting state and the pool might not start.</span></span>
  
|<span data-ttu-id="a55a7-121">プール内のサーバーの総数</span><span class="sxs-lookup"><span data-stu-id="a55a7-121">Total number of servers in the pool</span></span>  <br/> |<span data-ttu-id="a55a7-122">プールを初めて起動するために実行する必要が生じなければならないサーバーの数</span><span class="sxs-lookup"><span data-stu-id="a55a7-122">Number of servers that must be running for the pool to be started the first time</span></span>  <br/> |
|:-----|:-----|
|<span data-ttu-id="a55a7-123">2 </span><span class="sxs-lookup"><span data-stu-id="a55a7-123">2</span></span>  <br/> |<span data-ttu-id="a55a7-124">1 </span><span class="sxs-lookup"><span data-stu-id="a55a7-124">1</span></span>  <br/> |
|<span data-ttu-id="a55a7-125">3 </span><span class="sxs-lookup"><span data-stu-id="a55a7-125">3</span></span>  <br/> |<span data-ttu-id="a55a7-126">3 </span><span class="sxs-lookup"><span data-stu-id="a55a7-126">3</span></span>  <br/> |
|<span data-ttu-id="a55a7-127">4 </span><span class="sxs-lookup"><span data-stu-id="a55a7-127">4</span></span>  <br/> |<span data-ttu-id="a55a7-128">3 </span><span class="sxs-lookup"><span data-stu-id="a55a7-128">3</span></span>  <br/> |
|<span data-ttu-id="a55a7-129">5 </span><span class="sxs-lookup"><span data-stu-id="a55a7-129">5</span></span>  <br/> |<span data-ttu-id="a55a7-130">4 </span><span class="sxs-lookup"><span data-stu-id="a55a7-130">4</span></span>  <br/> |
|<span data-ttu-id="a55a7-131">6 </span><span class="sxs-lookup"><span data-stu-id="a55a7-131">6</span></span>  <br/> |<span data-ttu-id="a55a7-132">5 </span><span class="sxs-lookup"><span data-stu-id="a55a7-132">5</span></span>  <br/> |
|<span data-ttu-id="a55a7-133">7 </span><span class="sxs-lookup"><span data-stu-id="a55a7-133">7</span></span>  <br/> |<span data-ttu-id="a55a7-134">5 </span><span class="sxs-lookup"><span data-stu-id="a55a7-134">5</span></span>  <br/> |
|<span data-ttu-id="a55a7-135">8 </span><span class="sxs-lookup"><span data-stu-id="a55a7-135">8</span></span>  <br/> |<span data-ttu-id="a55a7-136">6 </span><span class="sxs-lookup"><span data-stu-id="a55a7-136">6</span></span>  <br/> |
|<span data-ttu-id="a55a7-137">9 </span><span class="sxs-lookup"><span data-stu-id="a55a7-137">9</span></span>  <br/> |<span data-ttu-id="a55a7-138">7 </span><span class="sxs-lookup"><span data-stu-id="a55a7-138">7</span></span>  <br/> |
|<span data-ttu-id="a55a7-139">10 </span><span class="sxs-lookup"><span data-stu-id="a55a7-139">10</span></span>  <br/> |<span data-ttu-id="a55a7-140">8 </span><span class="sxs-lookup"><span data-stu-id="a55a7-140">8</span></span>  <br/> |
|<span data-ttu-id="a55a7-141">11 </span><span class="sxs-lookup"><span data-stu-id="a55a7-141">11</span></span>  <br/> |<span data-ttu-id="a55a7-142">9 </span><span class="sxs-lookup"><span data-stu-id="a55a7-142">9</span></span>  <br/> |
|<span data-ttu-id="a55a7-143">12 </span><span class="sxs-lookup"><span data-stu-id="a55a7-143">12</span></span>  <br/> |<span data-ttu-id="a55a7-144">10 </span><span class="sxs-lookup"><span data-stu-id="a55a7-144">10</span></span>  <br/> |
|<span data-ttu-id="a55a7-145">16 **For Skype for Business Server 2019**</span><span class="sxs-lookup"><span data-stu-id="a55a7-145">16 **For Skype for Business Server 2019**</span></span> <br/> |<span data-ttu-id="a55a7-146">12 </span><span class="sxs-lookup"><span data-stu-id="a55a7-146">12</span></span>  <br/> |


   
<span data-ttu-id="a55a7-147">それ以降にプールが開始されるごとに、サーバーの 85% を開始する必要があります (前の表を参照)。</span><span class="sxs-lookup"><span data-stu-id="a55a7-147">Every subsequent time the pool is started, 85% of the servers should be started (as shown in the preceding table).</span></span> <span data-ttu-id="a55a7-148">この数のサーバーを開始できない場合 (ただし、プール レベルのクォーラム損失が発生しないほど十分な数のサーバーを開始できる場合)、このコマンドレットを使用して、プールでこのルーティング グループ レベルのクォーラム損失から回復し、処理を進めできます。 `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery`</span><span class="sxs-lookup"><span data-stu-id="a55a7-148">If this number of servers cannot be started (but enough servers can be started so that you are not at pool-level quorum loss), you can use the  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` cmdlet to enable the pool to recover from this routing group level quorum loss and make progress.</span></span> <span data-ttu-id="a55a7-149">このコマンドレットの使い方の詳細については [、「Reset-CsPoolRegistrarState」を参照してください](https://docs.microsoft.com/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="a55a7-149">For more information about how to use this cmdlet, see [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a55a7-150">サーバーの数が等しいプールでは、Skype for Business Server はプライマリ サーバー データベースを監視SQL使用します。</span><span class="sxs-lookup"><span data-stu-id="a55a7-150">In pools with an even number of servers, Skype for Business Server uses the Primary SQL database as Witness.</span></span> <span data-ttu-id="a55a7-151">このようなプールでは、プライマリ データベースをシャットダウンしてミラー コピーに切り替え、前の表に従って十分に実行されていないフロントエンド サーバーをシャットダウンすると、プール全体がダウンします。</span><span class="sxs-lookup"><span data-stu-id="a55a7-151">In a pool like this, if you shut down the primary database and switch to the Mirror copy, and shut down enough Front End servers so that not enough are running according to the preceding table, the entire pool will go down.</span></span> <span data-ttu-id="a55a7-152">詳細については、「データベース ミラーリング [監視」を参照してください](https://go.microsoft.com/fwlink/?LinkId=393672)。</span><span class="sxs-lookup"><span data-stu-id="a55a7-152">For more information, see [Database Mirroring Witness](https://go.microsoft.com/fwlink/?LinkId=393672).</span></span> 
  
#### <a name="pool-level-quorum-loss"></a><span data-ttu-id="a55a7-153">プール レベルクォーラム損失</span><span class="sxs-lookup"><span data-stu-id="a55a7-153">Pool-level quorum loss</span></span>

<span data-ttu-id="a55a7-154">フロントエンド プールが機能するには、プール レベルのクォーラム損失にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a55a7-154">For a Front End pool to function at all, it cannot be in pool-level quorum loss.</span></span> <span data-ttu-id="a55a7-155">次の表に示すように、実行されているサーバーの数が機能レベルを下回った場合、プール内の残りのサーバーは、すべての Skype for Business Server サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="a55a7-155">If the number of servers running falls below the functional level as shown in the following table, the remaining servers in the pool will stop all Skype for Business Server services.</span></span> <span data-ttu-id="a55a7-156">次の表の数値は、プール内のバック エンド サーバーが実行されている場合を想定しています。</span><span class="sxs-lookup"><span data-stu-id="a55a7-156">Note that the numbers in the following table assume that the Back End Servers in the pool are running.</span></span>
  
|<span data-ttu-id="a55a7-157">プール内のフロントエンド サーバーの総数</span><span class="sxs-lookup"><span data-stu-id="a55a7-157">Total number of Front End Servers in the pool</span></span>  <br/> |<span data-ttu-id="a55a7-158">プールが機能するために実行されている必要のあるサーバーの数</span><span class="sxs-lookup"><span data-stu-id="a55a7-158">Number of servers that must be running for pool to be functional</span></span>  <br/> |
|:-----|:-----|
|<span data-ttu-id="a55a7-159">2 </span><span class="sxs-lookup"><span data-stu-id="a55a7-159">2</span></span>  <br/> |<span data-ttu-id="a55a7-160">1 </span><span class="sxs-lookup"><span data-stu-id="a55a7-160">1</span></span>  <br/> |
|<span data-ttu-id="a55a7-161">3-4</span><span class="sxs-lookup"><span data-stu-id="a55a7-161">3-4</span></span>  <br/> |<span data-ttu-id="a55a7-162">任意の 2</span><span class="sxs-lookup"><span data-stu-id="a55a7-162">Any 2</span></span>  <br/> |
|<span data-ttu-id="a55a7-163">5-6</span><span class="sxs-lookup"><span data-stu-id="a55a7-163">5-6</span></span>  <br/> |<span data-ttu-id="a55a7-164">任意の 3</span><span class="sxs-lookup"><span data-stu-id="a55a7-164">Any 3</span></span>  <br/> |
|<span data-ttu-id="a55a7-165">7 </span><span class="sxs-lookup"><span data-stu-id="a55a7-165">7</span></span>  <br/> |<span data-ttu-id="a55a7-166">任意の 4</span><span class="sxs-lookup"><span data-stu-id="a55a7-166">Any 4</span></span>  <br/> |
|<span data-ttu-id="a55a7-167">8-9</span><span class="sxs-lookup"><span data-stu-id="a55a7-167">8-9</span></span>  <br/> |<span data-ttu-id="a55a7-168">最初の 7 つのサーバーの任意の 4 つ</span><span class="sxs-lookup"><span data-stu-id="a55a7-168">Any 4 of the first 7 servers</span></span>  <br/> |
|<span data-ttu-id="a55a7-169">10-12</span><span class="sxs-lookup"><span data-stu-id="a55a7-169">10-12</span></span>  <br/> |<span data-ttu-id="a55a7-170">最初の 9 つのサーバーの任意の 5 つ</span><span class="sxs-lookup"><span data-stu-id="a55a7-170">Any 5 of the first 9 servers</span></span>  <br/> |
|<span data-ttu-id="a55a7-171">12-16  **For Skype for Business Server 2019**</span><span class="sxs-lookup"><span data-stu-id="a55a7-171">12-16  **For Skype for Business Server 2019**</span></span>  <br/> |<span data-ttu-id="a55a7-172">最初の 12 台のサーバーの任意の 7 台</span><span class="sxs-lookup"><span data-stu-id="a55a7-172">Any 7 of the first 12 servers</span></span>  <br/> |
   
<span data-ttu-id="a55a7-173">前の表の "最初のサーバー" は、プールが初めて起動された際に、時系列的に最初に起動されたサーバーです。</span><span class="sxs-lookup"><span data-stu-id="a55a7-173">In the preceding table, the "first servers" are the servers which were brought up first, chronologically, when the pool was started for the first time.</span></span> <span data-ttu-id="a55a7-174">これらのサーバーを確認するには、このコマンドレット  `Get-CsComputer` をオプションと一緒に使用 `-PoolFqdn` します。</span><span class="sxs-lookup"><span data-stu-id="a55a7-174">To determine these servers, you can use the  `Get-CsComputer` cmdlet with the `-PoolFqdn` option.</span></span> <span data-ttu-id="a55a7-175">このコマンドレットでは、サーバーがトポロジに表示される順序で表示され、一覧の上部にあるサーバーが最初のサーバーになります。</span><span class="sxs-lookup"><span data-stu-id="a55a7-175">This cmdlet will show the servers in the order that they appear in the topology, and the ones at the top of the list are the first servers.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a55a7-176">[Skype for Business Server 2019](https://docs.microsoft.com/skypeforbusiness/plan/user-model-2019)では、フロントエンド サーバーの最大数が 16 台に増やされました。</span><span class="sxs-lookup"><span data-stu-id="a55a7-176">The maximum number of front end servers has been increased to 16 in [Skype for Business Server 2019](https://docs.microsoft.com/skypeforbusiness/plan/user-model-2019)</span></span>
> 
#### <a name="additional-steps-to-ensure-pools-are-functional"></a><span data-ttu-id="a55a7-177">プールが機能するための追加の手順</span><span class="sxs-lookup"><span data-stu-id="a55a7-177">Additional steps to ensure pools are functional</span></span>

<span data-ttu-id="a55a7-178">フロント エンド プールの機能を維持するために、その他のいくつかの要因を監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a55a7-178">You should watch for a couple of other factors to ensure that your Front End pools remain functional.</span></span>
  
- <span data-ttu-id="a55a7-179">ユーザーを初めてプールに移動する場合は、少なくとも 3 つのフロントエンド サーバーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a55a7-179">When you move users to the pool for the first time, be sure at least three of the Front End Servers are running.</span></span>
    
- <span data-ttu-id="a55a7-180">障害復旧を目的としてこのプールと別のプールの間にペアリング関係を確立する場合は、その関係を確立した後、データをバックアップ プールと適切に同期するために、このプールに同時に 3 つのフロントエンド サーバーが同時に実行されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a55a7-180">If you establish a pairing relationship between this pool and another pool for disaster recovery purposes, then after establishing that relationship you must be sure this pool has three Front End servers running simultaneously at some time to properly synchronize data with the backup pool.</span></span> <span data-ttu-id="a55a7-181">プールのペアリングと障害復旧機能の詳細については [、「Plan for high availability and disaster recovery in Skype for Business Server 」を参照してください](high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="a55a7-181">For more information on pool pairing and disaster recovery features, see [Plan for high availability and disaster recovery in Skype for Business Server](high-availability-and-disaster-recovery.md).</span></span> 
    
## <a name="front-end-pool-with-two-front-end-servers"></a><span data-ttu-id="a55a7-182">2 台のフロントエンド サーバーを含むフロントエンド プール</span><span class="sxs-lookup"><span data-stu-id="a55a7-182">Front End pool with two Front End servers</span></span>

<span data-ttu-id="a55a7-183">2 台のフロントエンド サーバーのみを含むフロントエンド プールを展開はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="a55a7-183">We do not recommend deploying a Front End pool that contains only two Front End Servers.</span></span> <span data-ttu-id="a55a7-184">この小規模なプールでは、大規模なプールのように堅牢な高可用性ソリューションは提供されないので、管理に特別な注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="a55a7-184">This small pool will not provide a robust high-availability solution like a larger pool would, and needs extra care in managing.</span></span> <span data-ttu-id="a55a7-185">また、2 台のサーバー プールのバック エンド サーバーがダウンした場合は、プール全体もすぐにダウンする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a55a7-185">Additionally, if the Back End Server of a two-server pool went down, the whole pool itself would likely soon go down as well.</span></span> <span data-ttu-id="a55a7-186">Skype for Business Server を実行している 1 台または 2 台のサーバーを展開する場合は、Standard Edition サーバーとして展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a55a7-186">If you want to deploy just one or two servers running Skype for Business Server, we recommend you deploy them as Standard Edition servers.</span></span>
  
<span data-ttu-id="a55a7-187">2 台のフロントエンド サーバーを持つプールを展開する必要がある場合は、次のガイドラインに従います。</span><span class="sxs-lookup"><span data-stu-id="a55a7-187">If you do ever need to deploy a pool with two Front End Servers, follow these guidelines:</span></span>
  
- <span data-ttu-id="a55a7-188">2 台のフロントエンド サーバーの 1 つがダウンした場合は、できるだけ早く障害が発生したサーバーをバックアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a55a7-188">If one of the two Front End Servers goes down, you should try to bring the failed server back up as soon as you can.</span></span> <span data-ttu-id="a55a7-189">同様に、2 台のサーバーのいずれかをアップグレードする必要がある場合は、アップグレードが完了したらすぐにオンラインに戻します。</span><span class="sxs-lookup"><span data-stu-id="a55a7-189">Similarly, if you need to upgrade one of the two servers, bring it back online as soon as the upgrade is finished.</span></span>
    
- <span data-ttu-id="a55a7-190">何らかの理由で両方のサーバーを同時に停止する必要がある場合は、プールのダウンタイムが終了したら、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a55a7-190">If for some reason you need to bring both servers down at the same time, do the following when the downtime for the pool is finished:</span></span>
    
  - <span data-ttu-id="a55a7-191">ベスト プラクティスは、両方のフロントエンド サーバーを同時に再起動する方法です。</span><span class="sxs-lookup"><span data-stu-id="a55a7-191">The best practice is to restart both Front End Servers at the same time.</span></span> 
    
  - <span data-ttu-id="a55a7-192">2 台のサーバーを同時に再起動できない場合は、停止した順序と逆の順序でサーバーを戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="a55a7-192">If the two servers cannot be restarted at the same time, you should bring them back up in the reverse order of the order they went down.</span></span>
    
  - <span data-ttu-id="a55a7-193">その順序でバックアップできない場合は、プールをバックアップする前に次のコマンドレットを使用します。  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`</span><span class="sxs-lookup"><span data-stu-id="a55a7-193">If you cannot bring them back up in that order, then use the following cmdlet before bringing the pool back up:  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`</span></span>
    
## <a name="front-end-pool-configuration-failures-and-changes"></a><span data-ttu-id="a55a7-194">フロントエンド プールの構成の失敗と変更</span><span class="sxs-lookup"><span data-stu-id="a55a7-194">Front End pool configuration failures and changes</span></span>

<span data-ttu-id="a55a7-195">フロントエンド サーバーに障害が発生し、数日以上交換する可能性が低い場合は、トポロジからサーバーを削除します。</span><span class="sxs-lookup"><span data-stu-id="a55a7-195">If a Front End server fails and is unlikely to be replaced for a few days or more, remove the server from the topology.</span></span> <span data-ttu-id="a55a7-196">新しいフロントエンド サーバーが再び使用可能な場合は、トポロジに追加します。</span><span class="sxs-lookup"><span data-stu-id="a55a7-196">Add the new Front End server to the topology when it is available again.</span></span>
  
<span data-ttu-id="a55a7-197">サーバーの追加や削除など、フロントエンド プールの構成を変更するたびに、次のガイドラインに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="a55a7-197">Whenever you make a configuration change to a Front End pool, such as adding or removing servers, you must follow these guidelines:</span></span>
  
- <span data-ttu-id="a55a7-198">新しいトポロジが公開された後、プール内の各フロントエンド サーバーを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a55a7-198">After the new topology has been published, you must restart each Front End server in the pool.</span></span> <span data-ttu-id="a55a7-199">一度に 1 回再起動します。</span><span class="sxs-lookup"><span data-stu-id="a55a7-199">Restart them one at a time.</span></span>
    
- <span data-ttu-id="a55a7-200">構成変更中にプール全体がダウンした場合は、新しいトポロジの公開後に次のコマンドレットを実行します。  `Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`</span><span class="sxs-lookup"><span data-stu-id="a55a7-200">If the entire pool has been down during the configuration change, then run the following cmdlet after the new topology is published:  `Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`</span></span>
    

