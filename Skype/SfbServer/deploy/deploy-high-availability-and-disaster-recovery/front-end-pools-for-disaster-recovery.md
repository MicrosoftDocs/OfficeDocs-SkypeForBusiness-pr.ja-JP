---
title: ビジネス サーバーの Skype での災害復旧のための一対のフロント エンド プールを展開します。
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: ペアのフロント エンド プールを使い障害復旧保護を実現できますが、これは必須要件ではありません。
ms.openlocfilehash: 028e0b4966a15b81b3e6e5627e63261207835f1f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225540"
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="1659f-103">ビジネス サーバーの Skype での災害復旧のための一対のフロント エンド プールを展開します。</span><span class="sxs-lookup"><span data-stu-id="1659f-103">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="1659f-104">ペアのフロント エンド プールを使い障害復旧保護を実現できますが、これは必須要件ではありません。</span><span class="sxs-lookup"><span data-stu-id="1659f-104">You may decide to use paired Front End pools to provide disaster recovery protection, but doing so is not a requirement.</span></span>
  
<span data-ttu-id="1659f-105">トポロジ ビルダーを使用してペアのフロント エンド プールの災害復旧トポロジーを容易に展開できます。</span><span class="sxs-lookup"><span data-stu-id="1659f-105">You can easily deploy the disaster recovery topology of paired Front End pools using Topology Builder.</span></span> 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a><span data-ttu-id="1659f-106">フロント エンド プールのペアを展開するには</span><span class="sxs-lookup"><span data-stu-id="1659f-106">To deploy a pair of Front End pools</span></span>

1. <span data-ttu-id="1659f-107">プールは新しいし、まだ定義されていない場合、プールを作成するのにはトポロジ ビルダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="1659f-107">If the pools are new and not yet defined, use Topology Builder to create the pools.</span></span>
    
2. <span data-ttu-id="1659f-108">トポロジ ビルダーでは、2 つのプールでは、いずれかを右クリックし、**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1659f-108">In Topology Builder, right-click one of the two pools, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="1659f-109">左ウィンドウの **[復元]** をクリックし、右ウィンドウの **[関連付けられているバックアップ プール]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="1659f-109">Click **Resiliency** in the left pane, and then select **Associated Backup Pool** in the right pane.</span></span>
    
4. <span data-ttu-id="1659f-p101">**[関連付けられているバックアップ プール]** の下のボックスで、このプールとペアにするプールを選択します。ペアでない単独の既存のプールのみを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="1659f-p101">In the box below **Associated Backup Pool**, select the pool that you want to pair with this pool. Only existing pools that are not already paired with another pool will be available to select from.</span></span>
    
5. <span data-ttu-id="1659f-112">**[音声の自動フェールオーバーとフェールバック]** を選択し、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1659f-112">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
    
    <span data-ttu-id="1659f-113">このプールの詳細情報を表示すると、関連付けられているプールが右ウィンドウの **[復元]** の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="1659f-113">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span> 
    
6. <span data-ttu-id="1659f-114">トポロジ ビルダーを使用すると、トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="1659f-114">Use Topology Builder to publish the topology.</span></span>
    
7. <span data-ttu-id="1659f-p102">2 つのプールがまだ展開されていない場合は、これらを展開すると、構成が完了します。最後の 2 つの手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="1659f-p102">If the two pools were not yet deployed, deploy them now and the configuration will be complete. You can skip the final two steps in this procedure.</span></span>
    
    <span data-ttu-id="1659f-117">しかし、ペアの関係を定義する前にプールが既に展開されていた場合は、次の 2 つの最終手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1659f-117">However, if the pools were already deployed before you defined the paired relationship, you must complete the following two final steps.</span></span>
    
8. <span data-ttu-id="1659f-118">両方のプール内のすべてのフロントエンド サーバーで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1659f-118">On every Front End Server in both pools, run the following:</span></span>
    
   ```
   <system drive>\Program Files\Skype for Business Server 2015\Deployment\Bootstrapper.exe 
   ```

    <span data-ttu-id="1659f-119">これによって、バックアップ ペアが適切に動作するために必要な他のサービスが構成されます。</span><span class="sxs-lookup"><span data-stu-id="1659f-119">This configures other services required for backup pairing to work correctly.</span></span>
    
9. <span data-ttu-id="1659f-120">ビジネス サーバー管理シェル コマンド プロンプトの Skype では、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="1659f-120">From a Skype for Business Server Management Shell command prompt, run the following:</span></span> 
    
   ```
   Start-CsWindowsService -Name LYNCBACKUP
   ```

10. <span data-ttu-id="1659f-121">次のコマンドレットを実行して、両方のプールのユーザーおよび電話会議データが相互に同期されるようにします。</span><span class="sxs-lookup"><span data-stu-id="1659f-121">Force the user and conference data of both pools to be synchronized with each other, with the following cmdlets:</span></span>
    
    ```
    Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
    ```

    ```
    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
    ```

    <span data-ttu-id="1659f-p103">データの同期には時間がかかる場合があります。次のコマンドレットを使用して、状態を確認できます。両方向の状態が安定状態であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1659f-p103">Synchronizing the data may take some time. You can use the following cmdlets to check the status. Make sure that the status in both directions is in steady state.</span></span>
    
    ```
    Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
    ```

    ```
    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
    ```

> [!NOTE]
> <span data-ttu-id="1659f-125">**自動フェイル オーバーおよびフェイル バック音声**オプションおよびトポロジ ビルダーに関連付けられている時間間隔は、Lync Server で導入された音声の復元機能にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="1659f-125">The **Automatic failover and failback for Voice** option and the associated time intervals in Topology Builder apply only to the voice resiliency features that were introduced in Lync Server.</span></span> <span data-ttu-id="1659f-126">このオプションを選んでも、このドキュメントに記載されているプール フェールオーバーが自動的に行われるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="1659f-126">Selecting this option does not imply that the pool failover discussed in this document is automatic.</span></span> <span data-ttu-id="1659f-127">プールのフェールオーバーとフェールバックを行うには、フェールオーバーとフェールバックのコマンドレットを、常に管理者が手動でそれぞれ起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1659f-127">Pool failover and failback always require an administrator to manually invoke the failover and failback cmdlets, respectively.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1659f-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="1659f-128">See also</span></span>

[<span data-ttu-id="1659f-129">ビジネス サーバーの前面の Skype で最後のプール災害復旧</span><span class="sxs-lookup"><span data-stu-id="1659f-129">Front End pool disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)
