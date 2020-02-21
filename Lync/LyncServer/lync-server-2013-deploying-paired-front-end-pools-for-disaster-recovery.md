---
title: 'Lync Server 2013: 障害復旧用のペアのフロントエンドプールの展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying paired Front End pools for disaster recovery
ms:assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204773(v=OCS.15)
ms:contentKeyID: 48183727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7f33e72c6f7d02787f53d16de3a42a0b3227d67
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-paired-front-end-pools-for-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="03a6d-102">Lync Server 2013 での障害復旧用のペアのフロントエンドプールの展開</span><span class="sxs-lookup"><span data-stu-id="03a6d-102">Deploying paired Front End pools for disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03a6d-103">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="03a6d-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="03a6d-104">トポロジビルダーを使用して、ペアになったフロントエンドプールの障害復旧トポロジを簡単に展開できます。</span><span class="sxs-lookup"><span data-stu-id="03a6d-104">You can easily deploy the disaster recovery topology of paired Front End pools using Topology Builder.</span></span>

<div>

## <a name="to-deploy-a-pair-of-front-end-pools"></a><span data-ttu-id="03a6d-105">ペアのフロントエンド プールを展開するには</span><span class="sxs-lookup"><span data-stu-id="03a6d-105">To deploy a pair of Front End pools</span></span>

1.  <span data-ttu-id="03a6d-106">プールが新規でまだ定義されていない場合は、トポロジビルダーを使用してプールを作成します。</span><span class="sxs-lookup"><span data-stu-id="03a6d-106">If the pools are new and not yet defined, use Topology Builder to create the pools.</span></span>

2.  <span data-ttu-id="03a6d-107">トポロジビルダーで、2つのプールのいずれかを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="03a6d-107">In Topology Builder, right-click one of the two pools, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="03a6d-108">左ウィンドウの [**復元**] をクリックし、右ウィンドウの [**関連付けられているバックアップ プール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="03a6d-108">Click **Resiliency** in the left pane, and then select **Associated Backup Pool** in the right pane.</span></span>

4.  <span data-ttu-id="03a6d-p101">[**関連付けられているバックアップ プール**] の下のボックスで、このプールとペアにするプールを選択します。別のプールとペアでない既存のプールのみ選択できます。</span><span class="sxs-lookup"><span data-stu-id="03a6d-p101">In the box below **Associated Backup Pool**, select the pool that you want to pair with this pool. Only existing pools that are not already paired with another pool will be available to select from.</span></span>
    
    <span data-ttu-id="03a6d-111">![36080581-db76-497d-bf9e-f02b39574d0e](images/JJ204773.36080581-db76-497d-bf9e-f02b39574d0e(OCS.15).png "36080581-db76-497d-bf9e-f02b39574d0e")</span><span class="sxs-lookup"><span data-stu-id="03a6d-111">![36080581-db76-497d-bf9e-f02b39574d0e](images/JJ204773.36080581-db76-497d-bf9e-f02b39574d0e(OCS.15).png "36080581-db76-497d-bf9e-f02b39574d0e")</span></span>  

5.  <span data-ttu-id="03a6d-112">[**音声の自動フェールオーバーとフェールバック**] を選択し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="03a6d-112">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
    
    <span data-ttu-id="03a6d-113">このプールの詳細情報を表示すると、関連付けられているプールが右ウィンドウの [**復元**] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="03a6d-113">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span>

6.  <span data-ttu-id="03a6d-114">トポロジビルダーを使用してトポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="03a6d-114">Use Topology Builder to publish the topology.</span></span>

7.  <span data-ttu-id="03a6d-p102">2 つのプールがまだ展開されていない場合は、これらを展開すると、構成が完了します。最後の 2 つの手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="03a6d-p102">If the two pools were not yet deployed, deploy them now and the configuration will be complete. You can skip the final two steps in this procedure.</span></span>
    
    <span data-ttu-id="03a6d-117">しかし、ペアの関係を定義する前にプールが既に展開されていた場合は、次の 2 つの最終手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03a6d-117">However, if the pools were already deployed before you defined the paired relationship, you must complete the following two final steps.</span></span>

8.  <span data-ttu-id="03a6d-118">両方のプール内のすべてのフロントエンド サーバーで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="03a6d-118">On every Front End Server in both pools, run the following:</span></span>
    ```console
    <system drive>\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe 
    ```
    <span data-ttu-id="03a6d-119">これによって、バックアップ ペアが適切に動作するために必要な他のサービスが構成されます。</span><span class="sxs-lookup"><span data-stu-id="03a6d-119">This configures other services required for backup pairing to work correctly.</span></span>

9.  <span data-ttu-id="03a6d-120">Lync Server 管理シェルコマンドプロンプトで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="03a6d-120">From a Lync Server Management Shell command prompt, run the following:</span></span>
    ```powershell
    Start-CsWindowsService -Name LYNCBACKUP
    ```
10. <span data-ttu-id="03a6d-121">次のコマンドレットを実行して、両方のプールのユーザーおよび電話会議データが相互に同期されるようにします。</span><span class="sxs-lookup"><span data-stu-id="03a6d-121">Force the user and conference data of both pools to be synchronized with each other, with the following cmdlets:</span></span>
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
       ```
    
    <span data-ttu-id="03a6d-122">データの同期には時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="03a6d-122">Synchronizing the data may take some time.</span></span> <span data-ttu-id="03a6d-123">次のコマンドレットを使用して、状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="03a6d-123">You can use the following cmdlets to check the status.</span></span> <span data-ttu-id="03a6d-124">双方向の状態が安定していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="03a6d-124">Make sure that the status in both directions is in steady state.</span></span>
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
       ```

<div class="">


> [!NOTE]  
> <span data-ttu-id="03a6d-125">[<STRONG>音声の自動フェールオーバーとフェールバック</STRONG>] オプションおよびトポロジビルダーの関連付けられた時間間隔は、Lync Server 2010 で導入された音声復元機能にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="03a6d-125">The <STRONG>Automatic failover and failback for Voice</STRONG> option and the associated time intervals in Topology Builder apply only to the voice resiliency features that were introduced in Lync Server 2010.</span></span> <span data-ttu-id="03a6d-126">このオプションを選択しても、このドキュメントに記載されているプール フェールオーバーが自動的に行われるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="03a6d-126">Selecting this option does not imply that the pool failover discussed in this document is automatic.</span></span> <span data-ttu-id="03a6d-127">プールのフェールオーバーとフェールバックを行うには、フェールオーバーとフェールバックのコマンドレットを、常に管理者が手動でそれぞれ起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03a6d-127">Pool failover and failback always require an administrator to manually invoke the failover and failback cmdlets, respectively.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

