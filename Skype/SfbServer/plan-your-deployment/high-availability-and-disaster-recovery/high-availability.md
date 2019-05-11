---
title: フロントエンド プールの高可用性と管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: プール、クォーラムの損失、および 2 つのフロント エンド サーバーとプールの特別な手順の管理を含むビジネス サーバーは、Skype でのフロント エンド プールの管理について説明します。
ms.openlocfilehash: bab9d4b40132665719a1e9d019b8f34e2d96622d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910229"
---
# <a name="front-end-pool-high-availability-and-management"></a><span data-ttu-id="24f05-103">フロントエンド プールの高可用性と管理</span><span class="sxs-lookup"><span data-stu-id="24f05-103">Front End Pool high availability and management</span></span>
 
<span data-ttu-id="24f05-104">プール、クォーラムの損失、および 2 つのフロント エンド サーバーとプールの特別な手順の管理を含むビジネス サーバーは、Skype でのフロント エンド プールの管理について説明します。</span><span class="sxs-lookup"><span data-stu-id="24f05-104">Learn about Front End pool management in Skype for Business Server, including managing pools, quorum loss, and special steps for pools with only two Front End Servers.</span></span>
  
<span data-ttu-id="24f05-105">ビジネス サーバーの Skype は、フロント エンド プールのアーキテクチャは、プール内に 3 つのフロント エンド サーバー上に保存する各ユーザーのデータを分散システムのモデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="24f05-105">In Skype for Business Server, the architecture of Front End pools uses a distributed systems model, with each user's data kept on as many as three Front End servers in the pool.</span></span> <span data-ttu-id="24f05-106">すべてのエンタープライズ エディションのフロント エンド プールに少なくとも 3 つのフロント エンド サーバーが含まれていることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="24f05-106">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers.</span></span> 
  
## <a name="planning-for-the-management-of-front-end-pools"></a><span data-ttu-id="24f05-107">フロント エンド プール管理の計画</span><span class="sxs-lookup"><span data-stu-id="24f05-107">Planning for the management of Front End pools</span></span>

 <span data-ttu-id="24f05-108">Skype ビジネス サーバーは、Windows のファブリックに基づく分散システムのモデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="24f05-108">Skype for Business Server uses a distributed systems model based on Windows Fabric.</span></span> <span data-ttu-id="24f05-109">このモデルでは、各ユーザーと会議の重要なデータはフロント エンド プール内の次の 3 つのフロント エンド サーバーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="24f05-109">In this model, important data for each user and conference is stored on three Front End Servers in a Front End pool.</span></span> <span data-ttu-id="24f05-110">データの特定のセットを格納するこれら 3 つのサーバーは、calledreplicas です。</span><span class="sxs-lookup"><span data-stu-id="24f05-110">These three servers storing a certain set of data are calledreplicas.</span></span>
  
<span data-ttu-id="24f05-111">モデルでは、分散のフロント エンド プール、プールのサーバーの特定の番号をプールの機能を実行しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="24f05-111">With the distributed model for Front End pools, a certain numbers of a pool's servers must be running for the pool to function.</span></span> <span data-ttu-id="24f05-112">プールの 2 つの損失モードがあります。</span><span class="sxs-lookup"><span data-stu-id="24f05-112">There are two loss modes for a pool.</span></span>
  
- <span data-ttu-id="24f05-113">クォーラムの損失のグループ レベルのルーティングは、十分な特定のルーティング グループのレプリカ ・ サーバによって発生します。</span><span class="sxs-lookup"><span data-stu-id="24f05-113">Routing Group Level quorum loss, caused by not enough replica servers for a particular routing group.</span></span> <span data-ttu-id="24f05-114">ルーティング グループは、一連のユーザーのホーム プールにします。</span><span class="sxs-lookup"><span data-stu-id="24f05-114">A routing group is a set of users homed in the pool.</span></span> <span data-ttu-id="24f05-115">各ルーティング グループが、プールの 3 つのレプリカ: 1 つのプライマリ レプリカとセカンダリの 2 つのレプリカです。</span><span class="sxs-lookup"><span data-stu-id="24f05-115">Each routing group has three replicas in the pool: one primary replica and two secondary replicas.</span></span>
    
- <span data-ttu-id="24f05-116">プール レベル クォーラム損失。プールで十分な数のシード サーバーが実行されていない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="24f05-116">Pool Level quorum loss, caused when not enough seed servers are running in the pool.</span></span> 
    
### <a name="routing-group-level-quorum-loss"></a><span data-ttu-id="24f05-117">ルーティング グループ レベル クォーラム損失</span><span class="sxs-lookup"><span data-stu-id="24f05-117">Routing Group Level quorum loss</span></span>

<span data-ttu-id="24f05-p105">新しいフロント エンド プールを初めて起動するときには、次の表に示すように、サーバーの 85% が実行されていることが必要です。実行されているサーバーの数がそれより少ないと、サービスが起動状態で行き詰まり、プールが起動されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="24f05-p105">The first time you start a new Front End pool, it is essential that 85% of the servers are up and running, as shown in the following table. If fewer servers are running, the services might be stuck in the starting state and the pool might not start.</span></span>
  
|<span data-ttu-id="24f05-120">プール内のサーバーの合計数</span><span class="sxs-lookup"><span data-stu-id="24f05-120">Total number of servers in the pool</span></span>  <br/> |<span data-ttu-id="24f05-121">プールを初めて起動させるために実行する必要があるサーバー数</span><span class="sxs-lookup"><span data-stu-id="24f05-121">Number of servers that must be running for the pool to be started the first time</span></span>  <br/> |
|:-----|:-----|
|<span data-ttu-id="24f05-122">2</span><span class="sxs-lookup"><span data-stu-id="24f05-122">2</span></span>  <br/> |<span data-ttu-id="24f05-123">1</span><span class="sxs-lookup"><span data-stu-id="24f05-123">1</span></span>  <br/> |
|<span data-ttu-id="24f05-124">3</span><span class="sxs-lookup"><span data-stu-id="24f05-124">3</span></span>  <br/> |<span data-ttu-id="24f05-125">3</span><span class="sxs-lookup"><span data-stu-id="24f05-125">3</span></span>  <br/> |
|<span data-ttu-id="24f05-126">4</span><span class="sxs-lookup"><span data-stu-id="24f05-126">4</span></span>  <br/> |<span data-ttu-id="24f05-127">3</span><span class="sxs-lookup"><span data-stu-id="24f05-127">3</span></span>  <br/> |
|<span data-ttu-id="24f05-128">5</span><span class="sxs-lookup"><span data-stu-id="24f05-128">5</span></span>  <br/> |<span data-ttu-id="24f05-129">4</span><span class="sxs-lookup"><span data-stu-id="24f05-129">4</span></span>  <br/> |
|<span data-ttu-id="24f05-130">6</span><span class="sxs-lookup"><span data-stu-id="24f05-130">6</span></span>  <br/> |<span data-ttu-id="24f05-131">5</span><span class="sxs-lookup"><span data-stu-id="24f05-131">5</span></span>  <br/> |
|<span data-ttu-id="24f05-132">7</span><span class="sxs-lookup"><span data-stu-id="24f05-132">7</span></span>  <br/> |<span data-ttu-id="24f05-133">5</span><span class="sxs-lookup"><span data-stu-id="24f05-133">5</span></span>  <br/> |
|<span data-ttu-id="24f05-134">8</span><span class="sxs-lookup"><span data-stu-id="24f05-134">8</span></span>  <br/> |<span data-ttu-id="24f05-135">6</span><span class="sxs-lookup"><span data-stu-id="24f05-135">6</span></span>  <br/> |
|<span data-ttu-id="24f05-136">9</span><span class="sxs-lookup"><span data-stu-id="24f05-136">9</span></span>  <br/> |<span data-ttu-id="24f05-137">7</span><span class="sxs-lookup"><span data-stu-id="24f05-137">7</span></span>  <br/> |
|<span data-ttu-id="24f05-138">10</span><span class="sxs-lookup"><span data-stu-id="24f05-138">10</span></span>  <br/> |<span data-ttu-id="24f05-139">8</span><span class="sxs-lookup"><span data-stu-id="24f05-139">8</span></span>  <br/> |
|<span data-ttu-id="24f05-140">11</span><span class="sxs-lookup"><span data-stu-id="24f05-140">11</span></span>  <br/> |<span data-ttu-id="24f05-141">9</span><span class="sxs-lookup"><span data-stu-id="24f05-141">9</span></span>  <br/> |
|<span data-ttu-id="24f05-142">12</span><span class="sxs-lookup"><span data-stu-id="24f05-142">12</span></span>  <br/> |<span data-ttu-id="24f05-143">10</span><span class="sxs-lookup"><span data-stu-id="24f05-143">10</span></span>  <br/> |
   
<span data-ttu-id="24f05-144">その後もプールが起動されるたびに、サーバーの 85% が起動されている必要があります (前出の表を参照)。</span><span class="sxs-lookup"><span data-stu-id="24f05-144">Every subsequent time the pool is started, 85% of the servers should be started (as shown in the preceding table).</span></span> <span data-ttu-id="24f05-145">数のサーバを起動できません (ただし、プールレベルのクォーラムが失われるように、十分なサーバーを開始することができます) を使って、`Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery`このルーティング グループ レベルのクォーラムの損失から回復し、進行状況を確認するのには、プールを有効にするコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="24f05-145">If this number of servers cannot be started (but enough servers can be started so that you are not at pool-level quorum loss), you can use the  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` cmdlet to enable the pool to recover from this routing group level quorum loss and make progress.</span></span> <span data-ttu-id="24f05-146">このコマンドレットを使用する方法の詳細についてを参照してください<link Reset-CsPoolRegistrarState>。</span><span class="sxs-lookup"><span data-stu-id="24f05-146">For more information about how to use this cmdlet, see <link Reset-CsPoolRegistrarState>.</span></span>
  
> [!NOTE]
> <span data-ttu-id="24f05-147">サーバー数が偶数のプールの場合、Skype for Business Server は監視にプライマリ SQL データベースを使います。</span><span class="sxs-lookup"><span data-stu-id="24f05-147">In pools with an even number of servers, Skype for Business Server uses the Primary SQL database as Witness.</span></span> <span data-ttu-id="24f05-148">このようなプールでは、プライマリ データベースをシャットダウンしてミラー データベースに切り替え、前述の表の必要な実行数に足りなくなるまでフロント エンド サーバーをシャットダウンすると、プール全体がダウンします。</span><span class="sxs-lookup"><span data-stu-id="24f05-148">In a pool like this, if you shut down the primary database and switch to the Mirror copy, and shut down enough Front End servers so that not enough are running according to the preceding table, the entire pool will go down.</span></span> <span data-ttu-id="24f05-149">詳細については、[データベース ミラーリングの監視](https://go.microsoft.com/fwlink/?LinkId=393672)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24f05-149">For more information, see [Database Mirroring Witness](https://go.microsoft.com/fwlink/?LinkId=393672).</span></span> 
  
#### <a name="pool-level-quorum-loss"></a><span data-ttu-id="24f05-150">プール レベル クォーラム損失</span><span class="sxs-lookup"><span data-stu-id="24f05-150">Pool-level quorum loss</span></span>

<span data-ttu-id="24f05-151">すべての機能をフロント エンド プール、プール レベルのクォーラムが失われるは指定できません。</span><span class="sxs-lookup"><span data-stu-id="24f05-151">For a Front End pool to function at all, it cannot be in pool-level quorum loss.</span></span> <span data-ttu-id="24f05-152">実行中のサーバーの数が次の表に示す機能レベルを下回ると、プールに属する残りのサーバーがすべての Skype for Business Server サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="24f05-152">If the number of servers running falls below the functional level as shown in the following table, the remaining servers in the pool will stop all Skype for Business Server services.</span></span> <span data-ttu-id="24f05-153">次の表の数値が、プールのバック エンド サーバーが実行されていることを想定して ことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="24f05-153">Note that the numbers in the following table assume that the Back End Servers in the pool are running.</span></span>
  
|<span data-ttu-id="24f05-154">プール内のフロント エンド サーバーの合計数</span><span class="sxs-lookup"><span data-stu-id="24f05-154">Total number of Front End Servers in the pool</span></span>  <br/> |<span data-ttu-id="24f05-155">プールを機能させるために実行する必要があるサーバーの数</span><span class="sxs-lookup"><span data-stu-id="24f05-155">Number of servers that must be running for pool to be functional</span></span>  <br/> |
|:-----|:-----|
|<span data-ttu-id="24f05-156">2</span><span class="sxs-lookup"><span data-stu-id="24f05-156">2</span></span>  <br/> |<span data-ttu-id="24f05-157">1</span><span class="sxs-lookup"><span data-stu-id="24f05-157">1</span></span>  <br/> |
|<span data-ttu-id="24f05-158">3 ～ 4</span><span class="sxs-lookup"><span data-stu-id="24f05-158">3-4</span></span>  <br/> |<span data-ttu-id="24f05-159">任意の 2 台</span><span class="sxs-lookup"><span data-stu-id="24f05-159">Any 2</span></span>  <br/> |
|<span data-ttu-id="24f05-160">5 ～ 6</span><span class="sxs-lookup"><span data-stu-id="24f05-160">5-6</span></span>  <br/> |<span data-ttu-id="24f05-161">任意の 3 台</span><span class="sxs-lookup"><span data-stu-id="24f05-161">Any 3</span></span>  <br/> |
|<span data-ttu-id="24f05-162">7</span><span class="sxs-lookup"><span data-stu-id="24f05-162">7</span></span>  <br/> |<span data-ttu-id="24f05-163">任意の 4 台</span><span class="sxs-lookup"><span data-stu-id="24f05-163">Any 4</span></span>  <br/> |
|<span data-ttu-id="24f05-164">8 ～ 9</span><span class="sxs-lookup"><span data-stu-id="24f05-164">8-9</span></span>  <br/> |<span data-ttu-id="24f05-165">最初の 7 台のうちの任意の 4 台</span><span class="sxs-lookup"><span data-stu-id="24f05-165">Any 4 of the first 7 servers</span></span>  <br/> |
|<span data-ttu-id="24f05-166">10 ～ 12</span><span class="sxs-lookup"><span data-stu-id="24f05-166">10-12</span></span>  <br/> |<span data-ttu-id="24f05-167">最初の 9 台のうちの任意の 5 台</span><span class="sxs-lookup"><span data-stu-id="24f05-167">Any 5 of the first 9 servers</span></span>  <br/> |
   
<span data-ttu-id="24f05-168">上記の表には、「最初のサーバー」が国々 を最初に、日付順、プールが最初に起動された場合サーバーです。</span><span class="sxs-lookup"><span data-stu-id="24f05-168">In the preceding table, the "first servers" are the servers which were brought up first, chronologically, when the pool was started for the first time.</span></span> <span data-ttu-id="24f05-169">これらのサーバーを特定するには、使用することができます、`Get-CsComputer`コマンドレットで、` -PoolFqdn`オプションです。</span><span class="sxs-lookup"><span data-stu-id="24f05-169">To determine these servers, you can use the  `Get-CsComputer` cmdlet with the ` -PoolFqdn` option.</span></span> <span data-ttu-id="24f05-170">このコマンドレットはサーバーをトポロジ内に出現した順に表示するので、そのリストの先頭にある方が最初のサーバーです。</span><span class="sxs-lookup"><span data-stu-id="24f05-170">This cmdlet will show the servers in the order that they appear in the topology, and the ones at the top of the list are the first servers.</span></span>
  
#### <a name="additional-steps-to-ensure-pools-are-functional"></a><span data-ttu-id="24f05-171">プールが機能していることを確認するための追加手順</span><span class="sxs-lookup"><span data-stu-id="24f05-171">Additional steps to ensure pools are functional</span></span>

<span data-ttu-id="24f05-172">フロント エンド プールを確実に機能させておくために、他にもいくつかの要因を監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24f05-172">You should watch for a couple of other factors to ensure that your Front End pools remain functional.</span></span>
  
- <span data-ttu-id="24f05-173">最初にユーザーをプールに移動するときに必ず少なくとも 3 つのフロント エンド サーバーを実行しています。</span><span class="sxs-lookup"><span data-stu-id="24f05-173">When you move users to the pool for the first time, be sure at least three of the Front End Servers are running.</span></span>
    
- <span data-ttu-id="24f05-174">障害復旧の目的でこのプールと別のプールの間にペアの関係を確立する場合は、データをバックアップ プールと正しく同期するために、関係を確立した後で、このプールの 3 台のフロントエンド サーバーがどこかのタイミングで同時に実行されることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24f05-174">If you establish a pairing relationship between this pool and another pool for disaster recovery purposes, then after establishing that relationship you must be sure this pool has three Front End servers running simultaneously at some time to properly synchronize data with the backup pool.</span></span> <span data-ttu-id="24f05-175">プールの組み合わせと災害復旧の機能の詳細については、[高可用性とビジネスのサーバー用の Skype での災害復旧の計画](high-availability-and-disaster-recovery.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24f05-175">For more information on pool pairing and disaster recovery features, see [Plan for high availability and disaster recovery in Skype for Business Server](high-availability-and-disaster-recovery.md).</span></span> 
    
## <a name="front-end-pool-with-two-front-end-servers"></a><span data-ttu-id="24f05-176">フロントエンド サーバーが 2 台のフロントエンド プール</span><span class="sxs-lookup"><span data-stu-id="24f05-176">Front End pool with two Front End servers</span></span>

<span data-ttu-id="24f05-177">2 つのフロント エンド サーバーが含まれるフロント エンド プールの展開はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="24f05-177">We do not recommend deploying a Front End pool that contains only two Front End Servers.</span></span> <span data-ttu-id="24f05-178">このような小規模なプールでは、大規模なプールのように堅牢な高可用性は実現できないので、管理に余計な配慮が必要になります。</span><span class="sxs-lookup"><span data-stu-id="24f05-178">This small pool will not provide a robust high-availability solution like a larger pool would, and needs extra care in managing.</span></span> <span data-ttu-id="24f05-179">さらに、2 台のサーバー プールのバック エンド サーバーが停止した場合全体のプール自体ことになるでしょうすぐにもします。</span><span class="sxs-lookup"><span data-stu-id="24f05-179">Additionally, if the Back End Server of a two-server pool went down, the whole pool itself would likely soon go down as well.</span></span> <span data-ttu-id="24f05-180">Skype を実行して、ビジネスのサーバーの 1 つか 2 つのサーバーを展開するには、Standard Edition サーバーとして展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="24f05-180">If you want to deploy just one or two servers running Skype for Business Server, we recommend you deploy them as Standard Edition servers.</span></span>
  
<span data-ttu-id="24f05-181">2 つのフロント エンド サーバー プールを展開する必要が場合は、これらのガイドラインに従います。</span><span class="sxs-lookup"><span data-stu-id="24f05-181">If you do ever need to deploy a pool with two Front End Servers, follow these guidelines:</span></span>
  
- <span data-ttu-id="24f05-182">2 つのフロント エンド サーバーのいずれかがダウンした場合に障害が発生したサーバーをバックアップすることができ、すぐにしてください。</span><span class="sxs-lookup"><span data-stu-id="24f05-182">If one of the two Front End Servers goes down, you should try to bring the failed server back up as soon as you can.</span></span> <span data-ttu-id="24f05-183">同様に、2 台のサーバーのうち 1 台をアップグレードする必要がある場合は、アップグレードが終わり次第、オンラインにします。</span><span class="sxs-lookup"><span data-stu-id="24f05-183">Similarly, if you need to upgrade one of the two servers, bring it back online as soon as the upgrade is finished.</span></span>
    
- <span data-ttu-id="24f05-184">何らかの理由で両方のサーバーを同時に停止する必要がある場合は、プールのダウンタイムが終わったら次のことをします。</span><span class="sxs-lookup"><span data-stu-id="24f05-184">If for some reason you need to bring both servers down at the same time, do the following when the downtime for the pool is finished:</span></span>
    
  - <span data-ttu-id="24f05-185">同時に両方のフロント エンド サーバーを再起動することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="24f05-185">The best practice is to restart both Front End Servers at the same time.</span></span> 
    
  - <span data-ttu-id="24f05-186">2 台のサーバーを同時に再起動できない場合は、停止した順序とは逆の順序で復旧する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24f05-186">If the two servers cannot be restarted at the same time, you should bring them back up in the reverse order of the order they went down.</span></span>
    
  - <span data-ttu-id="24f05-187">できない場合にバックアップを作成順に、バックアップのプールを導入する前に次のコマンドレットを使用します。`Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`</span><span class="sxs-lookup"><span data-stu-id="24f05-187">If you cannot bring them back up in that order, then use the following cmdlet before bringing the pool back up:  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`</span></span>
    
## <a name="front-end-pool-configuration-failures-and-changes"></a><span data-ttu-id="24f05-188">フロント エンド プール構成のエラーと変更</span><span class="sxs-lookup"><span data-stu-id="24f05-188">Front End pool configuration failures and changes</span></span>

<span data-ttu-id="24f05-p113">フロント エンド サーバーが故障し、数日以内に交換できそうにない場合は、そのサーバーをトポロジから削除します。再び使用できるようになったときに、新しいフロント エンド サーバーをトポロジに追加します。</span><span class="sxs-lookup"><span data-stu-id="24f05-p113">If a Front End server fails and is unlikely to be replaced for a few days or more, remove the server from the topology. Add the new Front End server to the topology when it is available again.</span></span>
  
<span data-ttu-id="24f05-191">サーバーの追加や削除など、フロント エンド プールの構成を変更するたびに、次のガイドラインに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="24f05-191">Whenever you make a configuration change to a Front End pool, such as adding or removing servers, you must follow these guidelines:</span></span>
  
- <span data-ttu-id="24f05-p114">新しいトポロジが公開された後で、プール内の各フロント エンド サーバーを再起動する必要があります。1 台ずつ再起動してください。</span><span class="sxs-lookup"><span data-stu-id="24f05-p114">After the new topology has been published, you must restart each Front End server in the pool. Restart them one at a time.</span></span>
    
- <span data-ttu-id="24f05-194">プール全体が構成の変更中にダウンしていた場合、は、新しいトポロジを公開した後、次のコマンドレットを実行します。`Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`</span><span class="sxs-lookup"><span data-stu-id="24f05-194">If the entire pool has been down during the configuration change, then run the following cmdlet after the new topology is published:  `Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`</span></span>
    

