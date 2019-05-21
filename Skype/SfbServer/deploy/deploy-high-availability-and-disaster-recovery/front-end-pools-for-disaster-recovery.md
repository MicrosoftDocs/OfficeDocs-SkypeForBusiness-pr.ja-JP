---
title: Skype for Business Server での障害回復用にペアリングされたフロントエンドプールの展開
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: ペアのフロント エンド プールを使い障害復旧保護を実現できますが、これは必須要件ではありません。
ms.openlocfilehash: 49af49a4a8ff3dd0f543de6f1b13bfbe5b571788
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298509"
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="5d683-103">Skype for Business Server での障害回復用にペアリングされたフロントエンドプールの展開</span><span class="sxs-lookup"><span data-stu-id="5d683-103">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="5d683-104">ペアのフロント エンド プールを使い障害復旧保護を実現できますが、これは必須要件ではありません。</span><span class="sxs-lookup"><span data-stu-id="5d683-104">You may decide to use paired Front End pools to provide disaster recovery protection, but doing so is not a requirement.</span></span>
  
<span data-ttu-id="5d683-105">トポロジビルダーを使用すると、ペアリングされたフロントエンドプールの障害回復トポロジを簡単に展開できます。</span><span class="sxs-lookup"><span data-stu-id="5d683-105">You can easily deploy the disaster recovery topology of paired Front End pools using Topology Builder.</span></span> 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a><span data-ttu-id="5d683-106">フロント エンド プールのペアを展開するには</span><span class="sxs-lookup"><span data-stu-id="5d683-106">To deploy a pair of Front End pools</span></span>

1. <span data-ttu-id="5d683-107">プールが新しく、まだ定義されていない場合は、トポロジビルダーを使用してプールを作成します。</span><span class="sxs-lookup"><span data-stu-id="5d683-107">If the pools are new and not yet defined, use Topology Builder to create the pools.</span></span>
    
2. <span data-ttu-id="5d683-108">トポロジビルダーで、2つのプールのいずれかを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d683-108">In Topology Builder, right-click one of the two pools, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="5d683-109">左ウィンドウの **[復元]** をクリックし、右ウィンドウの **[関連付けられているバックアップ プール]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="5d683-109">Click **Resiliency** in the left pane, and then select **Associated Backup Pool** in the right pane.</span></span>
    
4. <span data-ttu-id="5d683-p101">**[関連付けられているバックアップ プール]** の下のボックスで、このプールとペアにするプールを選択します。ペアでない単独の既存のプールのみを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="5d683-p101">In the box below **Associated Backup Pool**, select the pool that you want to pair with this pool. Only existing pools that are not already paired with another pool will be available to select from.</span></span>
    
5. <span data-ttu-id="5d683-112">**[音声の自動フェールオーバーとフェールバック]** を選択し、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d683-112">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
    
    <span data-ttu-id="5d683-113">このプールの詳細情報を表示すると、関連付けられているプールが右ウィンドウの **[復元]** の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="5d683-113">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span> 
    
6. <span data-ttu-id="5d683-114">トポロジビルダーを使用してトポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="5d683-114">Use Topology Builder to publish the topology.</span></span>
    
7. <span data-ttu-id="5d683-p102">2 つのプールがまだ展開されていない場合は、これらを展開すると、構成が完了します。最後の 2 つの手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="5d683-p102">If the two pools were not yet deployed, deploy them now and the configuration will be complete. You can skip the final two steps in this procedure.</span></span>
    
    <span data-ttu-id="5d683-117">しかし、ペアの関係を定義する前にプールが既に展開されていた場合は、次の 2 つの最終手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d683-117">However, if the pools were already deployed before you defined the paired relationship, you must complete the following two final steps.</span></span>
    
8. <span data-ttu-id="5d683-118">両方のプール内のすべてのフロントエンド サーバーで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5d683-118">On every Front End Server in both pools, run the following:</span></span>
    
   ```
   <system drive>\Program Files\Skype for Business Server 2015\Deployment\Bootstrapper.exe 
   ```

    <span data-ttu-id="5d683-119">これによって、バックアップ ペアが適切に動作するために必要な他のサービスが構成されます。</span><span class="sxs-lookup"><span data-stu-id="5d683-119">This configures other services required for backup pairing to work correctly.</span></span>
    
9. <span data-ttu-id="5d683-120">Skype for Business Server Management Shell コマンドプロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5d683-120">From a Skype for Business Server Management Shell command prompt, run the following:</span></span> 
    
   ```
   Start-CsWindowsService -Name LYNCBACKUP
   ```

10. <span data-ttu-id="5d683-121">次のコマンドレットを実行して、両方のプールのユーザーおよび電話会議データが相互に同期されるようにします。</span><span class="sxs-lookup"><span data-stu-id="5d683-121">Force the user and conference data of both pools to be synchronized with each other, with the following cmdlets:</span></span>
    
    ```
    Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
    ```

    ```
    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
    ```

    <span data-ttu-id="5d683-p103">データの同期には時間がかかる場合があります。次のコマンドレットを使用して、状態を確認できます。両方向の状態が安定状態であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5d683-p103">Synchronizing the data may take some time. You can use the following cmdlets to check the status. Make sure that the status in both directions is in steady state.</span></span>
    
    ```
    Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
    ```

    ```
    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
    ```

> [!NOTE]
> <span data-ttu-id="5d683-125">[**音声の自動フェールオーバー** ] オプションと [トポロジビルダー] の関連付けられた時間間隔は、Lync Server で導入された音声回復機能のみに適用されます。</span><span class="sxs-lookup"><span data-stu-id="5d683-125">The **Automatic failover and failback for Voice** option and the associated time intervals in Topology Builder apply only to the voice resiliency features that were introduced in Lync Server.</span></span> <span data-ttu-id="5d683-126">このオプションを選んでも、このドキュメントに記載されているプール フェールオーバーが自動的に行われるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="5d683-126">Selecting this option does not imply that the pool failover discussed in this document is automatic.</span></span> <span data-ttu-id="5d683-127">プールのフェールオーバーとフェールバックを行うには、フェールオーバーとフェールバックのコマンドレットを、常に管理者が手動でそれぞれ起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d683-127">Pool failover and failback always require an administrator to manually invoke the failover and failback cmdlets, respectively.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5d683-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="5d683-128">See also</span></span>

[<span data-ttu-id="5d683-129">Skype for Business Server のフロントエンドプールの障害回復</span><span class="sxs-lookup"><span data-stu-id="5d683-129">Front End pool disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)
