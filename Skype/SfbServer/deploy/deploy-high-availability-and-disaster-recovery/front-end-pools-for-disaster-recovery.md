---
title: Skype for Business Server での障害回復用にペアリングされたフロントエンドプールの展開
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: ペアのフロント エンド プールを使い障害復旧保護を実現できますが、これは必須要件ではありません。
ms.openlocfilehash: 73f7d7619efbfc82124507234ebea8ebbcf4a7e8
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002907"
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="2e30e-103">Skype for Business Server での障害回復用にペアリングされたフロントエンドプールの展開</span><span class="sxs-lookup"><span data-stu-id="2e30e-103">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="2e30e-104">ペアのフロント エンド プールを使い障害復旧保護を実現できますが、これは必須要件ではありません。</span><span class="sxs-lookup"><span data-stu-id="2e30e-104">You may decide to use paired Front End pools to provide disaster recovery protection, but doing so is not a requirement.</span></span>
  
<span data-ttu-id="2e30e-105">トポロジビルダーを使用すると、ペアリングされたフロントエンドプールの障害回復トポロジを簡単に展開できます。</span><span class="sxs-lookup"><span data-stu-id="2e30e-105">You can easily deploy the disaster recovery topology of paired Front End pools using Topology Builder.</span></span> 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a><span data-ttu-id="2e30e-106">フロント エンド プールのペアを展開するには</span><span class="sxs-lookup"><span data-stu-id="2e30e-106">To deploy a pair of Front End pools</span></span>

1. <span data-ttu-id="2e30e-107">プールが新しく、まだ定義されていない場合は、トポロジビルダーを使用してプールを作成します。</span><span class="sxs-lookup"><span data-stu-id="2e30e-107">If the pools are new and not yet defined, use Topology Builder to create the pools.</span></span>
    
2. <span data-ttu-id="2e30e-108">トポロジビルダーで、2つのプールのいずれかを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e30e-108">In Topology Builder, right-click one of the two pools, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="2e30e-109">左ウィンドウの **[復元]** をクリックし、右ウィンドウの **[関連付けられているバックアップ プール]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="2e30e-109">Click **Resiliency** in the left pane, and then select **Associated Backup Pool** in the right pane.</span></span>
    
4. <span data-ttu-id="2e30e-p101">**[関連付けられているバックアップ プール]** の下のボックスで、このプールとペアにするプールを選択します。ペアでない単独の既存のプールのみを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="2e30e-p101">In the box below **Associated Backup Pool**, select the pool that you want to pair with this pool. Only existing pools that are not already paired with another pool will be available to select from.</span></span>
    
5. <span data-ttu-id="2e30e-112">**[音声の自動フェールオーバーとフェールバック]** を選択し、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e30e-112">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
    
    <span data-ttu-id="2e30e-113">このプールの詳細情報を表示すると、関連付けられているプールが右ウィンドウの **[復元]** の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2e30e-113">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span> 
    
6. <span data-ttu-id="2e30e-114">トポロジビルダーを使用してトポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="2e30e-114">Use Topology Builder to publish the topology.</span></span>
    
7. <span data-ttu-id="2e30e-115">2 つのプールがまだ展開されていない場合は、これらを展開すると、構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="2e30e-115">If the two pools were not yet deployed, deploy them now and the configuration will be complete.</span></span> <span data-ttu-id="2e30e-116">この手順の最後の手順はスキップできます。</span><span class="sxs-lookup"><span data-stu-id="2e30e-116">You can skip the final steps in this procedure.</span></span>
    
    <span data-ttu-id="2e30e-117">ただし、ペアのリレーションシップを定義する前に、プールを既に展開している場合は、次の最終的な手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e30e-117">However, if the pools were already deployed before you defined the paired relationship, you must complete the following final steps.</span></span>
    
8. <span data-ttu-id="2e30e-118">両方のプール内のすべてのフロントエンド サーバーで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2e30e-118">On every Front End Server in both pools, run the following:</span></span>
    
   ```powershell
   <system drive>\Program Files\Skype for Business Server 2019\Deployment\Bootstrapper.exe 
   ```

    <span data-ttu-id="2e30e-119">これによって、バックアップ ペアが適切に動作するために必要な他のサービスが構成されます。</span><span class="sxs-lookup"><span data-stu-id="2e30e-119">This configures other services required for backup pairing to work correctly.</span></span>
    
9. <span data-ttu-id="2e30e-120">両方のプールの各フロントエンドサーバー上のバックアップペアリングに必要なコンポーネントのインストールが完了したら、両方のプールの各フロントエンドサーバーに既に適用されていた既存の累積的な更新プログラムを再度適用してから、続行してください。次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2e30e-120">Once Bootstrapper finishes installing the required components for backup pairing on every Front end Server in both pools, please be sure to re-apply any existing Cumulative Update that was previously applied on these Front End Servers in both pools and then continue with the next step.</span></span>

10. <span data-ttu-id="2e30e-121">Skype for Business Server Management Shell コマンドプロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2e30e-121">From a Skype for Business Server Management Shell command prompt, run the following:</span></span> 
    
   ```powershell
   Start-CsWindowsService -Name LYNCBACKUP
   ```

11. <span data-ttu-id="2e30e-122">次のコマンドレットを使用して、両方のプールのユーザーと会議のデータを相互に同期させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e30e-122">Force the user and conference data of both pools to be synchronized with each other with the following cmdlets:</span></span>
    
    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
    ```

    <span data-ttu-id="2e30e-p103">データの同期には時間がかかる場合があります。次のコマンドレットを使用して、状態を確認できます。両方向の状態が安定状態であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2e30e-p103">Synchronizing the data may take some time. You can use the following cmdlets to check the status. Make sure that the status in both directions is in steady state.</span></span>
    
    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
    ```

> [!NOTE]
> <span data-ttu-id="2e30e-126">[**音声の自動フェールオーバー** ] オプションと [トポロジビルダー] の関連付けられた時間間隔は、Lync Server で導入された音声回復機能のみに適用されます。</span><span class="sxs-lookup"><span data-stu-id="2e30e-126">The **Automatic failover and failback for Voice** option and the associated time intervals in Topology Builder apply only to the voice resiliency features that were introduced in Lync Server.</span></span> <span data-ttu-id="2e30e-127">このオプションを選んでも、このドキュメントに記載されているプール フェールオーバーが自動的に行われるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="2e30e-127">Selecting this option does not imply that the pool failover discussed in this document is automatic.</span></span> <span data-ttu-id="2e30e-128">プールのフェールオーバーとフェールバックを行うには、フェールオーバーとフェールバックのコマンドレットを、常に管理者が手動でそれぞれ起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e30e-128">Pool failover and failback always require an administrator to manually invoke the failover and failback cmdlets, respectively.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2e30e-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="2e30e-129">See also</span></span>

[<span data-ttu-id="2e30e-130">Skype for Business Server のフロントエンドプールの障害回復</span><span class="sxs-lookup"><span data-stu-id="2e30e-130">Front End pool disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)
