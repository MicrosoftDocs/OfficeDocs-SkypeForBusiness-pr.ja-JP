---
title: プールのフェール オーバーおよびフェール バック
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: .
ms.openlocfilehash: 1ebd4e8110b8783c869530d95eda0646a895b88e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826567"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a><span data-ttu-id="7bf84-103">Skype for Business Server のプールのフェールオーバーとフェールバック</span><span class="sxs-lookup"><span data-stu-id="7bf84-103">Failing over and failing back a pool in Skype for Business Server</span></span> 

<span data-ttu-id="7bf84-104">単一のフロントエンド プールが障害を起こしてフェールオーバーする必要がある場合、または障害が発生したプールがオンラインに戻り、展開を通常の作業状態に復元する必要がある場合は、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-104">Use the following procedures if a single Front End pool has failed and needs to be failed over, or the pool that experienced the disaster is back online and you need to restore your deployment to regular working status.</span></span> <span data-ttu-id="7bf84-105">また、Skype for Business フェデレーションまたは XMPP フェデレーションに使用されるエッジ プールをフェールオーバーおよびフェールバックする方法、またはフロントエンド プールに関連付けられているエッジ プールを変更する方法も説明します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-105">Also  learn how to fail over and fail back the Edge pool used for Skype for Business federation or XMPP federation, or change the Edge pool associated with a Front End pool.</span></span>

- [<span data-ttu-id="7bf84-106">フロントエンド プールのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="7bf84-106">Fail over a Front End pool</span></span>](#fail-over-a-front-end-pool)
- [<span data-ttu-id="7bf84-107">プールをフェールバックする</span><span class="sxs-lookup"><span data-stu-id="7bf84-107">Fail back a pool</span></span>](#fail-back-a-pool)
- [<span data-ttu-id="7bf84-108">Skype for Business Server フェデレーションに使用されるエッジ プールをフェールオーバーする</span><span class="sxs-lookup"><span data-stu-id="7bf84-108">Fail over the Edge pool used for Skype for Business Server federation</span></span>](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [<span data-ttu-id="7bf84-109">Skype for Business Server で XMPP フェデレーションに使用されるエッジ プールをフェールオーバーする</span><span class="sxs-lookup"><span data-stu-id="7bf84-109">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span>](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [<span data-ttu-id="7bf84-110">Skype for Business Server フェデレーションまたは XMPP フェデレーションに使用されるエッジ プールのフェールバック</span><span class="sxs-lookup"><span data-stu-id="7bf84-110">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span>](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [<span data-ttu-id="7bf84-111">フロントエンド プールに関連付けられているエッジ プールを変更する</span><span class="sxs-lookup"><span data-stu-id="7bf84-111">Change the Edge pool associated with a Front End pool</span></span>](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a><span data-ttu-id="7bf84-112">フロントエンド プールのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="7bf84-112">Fail over a Front End pool</span></span>

<span data-ttu-id="7bf84-113">この手順では、Datacenter1 に Pool1 があり、Pool1 で障害が発生した状況を想定しています。</span><span class="sxs-lookup"><span data-stu-id="7bf84-113">In this procedure, Datacenter1 contains Pool1, and Pool1 has failed.</span></span> <span data-ttu-id="7bf84-114">フェールオーバー先は Datacenter2 の Pool2 です。</span><span class="sxs-lookup"><span data-stu-id="7bf84-114">You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="7bf84-115">プールフェールオーバーの作業の大部分は、中央管理ストア (必要な場合) をフェールオーバーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7bf84-115">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="7bf84-116">これは、プールのユーザーがフェールオーバーするときに中央管理ストアが機能している必要があるから重要です。</span><span class="sxs-lookup"><span data-stu-id="7bf84-116">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="7bf84-p104">また、フロントエンド プールで障害が発生しているが、そのサイトのエッジ プールはまだ実行されている場合は、障害が発生しているプールをエッジ プールで次ホップ プールとして使用するかどうかを把握する必要があります。次ホップ プールとして使用する場合は、障害が発生しているフロントエンド プールをフェールオーバーする前に、エッジ プールを変更して別のフロントエンド プールを使用する必要があります。次ホップの設定を変更する方法は、エッジでエッジ プールと同じサイトのプールを使用するか、別のサイトのプールを使用するかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="7bf84-p104">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool. If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool. How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="7bf84-120">**同じサイトで次ホップ プールを使用するエッジ プールを設定するには**</span><span class="sxs-lookup"><span data-stu-id="7bf84-120">**To set an Edge pool to use a next hop pool at the same site**</span></span>

1.  <span data-ttu-id="7bf84-121">トポロジ ビルダーを開き、変更する必要があるエッジ プールを右クリックし、[プロパティの編集] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="7bf84-121">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="7bf84-p105">[**次ホップ**] をクリックします。[**次ホップ プール**] の一覧で、次ホップ プールとして使用するプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-p105">Click **Next Hop**. From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="7bf84-124">[**OK**] をクリックし、変更を公開します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-124">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="7bf84-125">**別のサイトで次ホップ プールを使用するエッジ プールを設定するには**</span><span class="sxs-lookup"><span data-stu-id="7bf84-125">**To set an Edge pool to use a next hop pool at a different site**</span></span>

1.  <span data-ttu-id="7bf84-126">Skype for Business Server 管理シェル ウィンドウを開き、次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-126">Open a Skype for Business Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="7bf84-127">**障害時にプールをフェールオーバーする**</span><span class="sxs-lookup"><span data-stu-id="7bf84-127">**To fail over a pool in a disaster**</span></span>

1.  <span data-ttu-id="7bf84-128">Pool2 のフロントエンド サーバーで次のコマンドレットを入力して、中央管理サーバーのホストであるプールを見つける。</span><span class="sxs-lookup"><span data-stu-id="7bf84-128">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="7bf84-129">このコマンドレットの結果は、中央管理サーバーを現在ホストしているプールを示します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-129">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="7bf84-130">この手順の残りの部分では、このプールを CMS プールと呼 \_ します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-130">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="7bf84-131">トポロジ ビルダーを使用して、CMS プールで実行されている Skype for Business Server のバージョンを検索 \_ します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-131">Use Topology Builder to find the version of Skype for Business Server running on the CMS\_Pool.</span></span> <span data-ttu-id="7bf84-132">Skype for Business Server を実行している場合は、次のコマンドレットを使用してプール 1 のバックアップ プールを検索します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-132">If it is running Skype for Business Server, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="7bf84-133">バックアップ プール \_ をバックアップ プールとします。</span><span class="sxs-lookup"><span data-stu-id="7bf84-133">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="7bf84-134">次のコマンドレットを使用して、中央管理ストアの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-134">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="7bf84-135">このコマンドレットは、ActiveMasterFQDN と ActiveFileTransferAgents の両方が CMS プールの FQDN をポイントしている必要 \_ があります。</span><span class="sxs-lookup"><span data-stu-id="7bf84-135">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="7bf84-136">サーバーが空の場合、中央管理サーバーは使用できません。サーバーをフェールオーバーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7bf84-136">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="7bf84-137">中央管理ストアが使用できない場合、または中央管理ストアが Pool1 で実行されている場合 (つまり、障害が発生したプール)、プールをフェールオーバーする前に中央管理サーバーをフェールオーバーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7bf84-137">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="7bf84-138">Skype for Business Server を実行しているプールでホストされている中央管理サーバーをフェールオーバーする必要がある場合は、この手順の手順 5 のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-138">If you need to fail over the Central Management Server that was hosted on a pool running Skype for Business Server, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="7bf84-139">中央管理サーバーをフェールオーバーする必要がない場合は、この手順の手順 7 に進みます。</span><span class="sxs-lookup"><span data-stu-id="7bf84-139">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="7bf84-140">Skype for Business Server を実行しているプールで中央管理ストアをフェールオーバーするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-140">To fail over the Central Management store on a pool running Skype for Business Server, do the following:</span></span>
    
      - <span data-ttu-id="7bf84-141">最初に、次のように入力して、バックアップ プール内のどのバック エンド サーバーが中央管理ストアのプリンシパル インスタンスを実行 \_ しているのか確認します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-141">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="7bf84-142">バックアップ プールのプライマリ バック エンド サーバーがプリンシパルの場合 \_ は、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-142">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="7bf84-143">バックアップ プール内のミラー のバック エンド サーバーがプリンシパル \_ である場合は、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-143">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="7bf84-144">中央管理サーバーのフェールオーバーが完了したと確認します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-144">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="7bf84-145">次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-145">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="7bf84-146">ActiveMasterFQDN と ActiveFileTransferAgents の両方がバックアップ プールの FQDN をポイントしているのを確認 \_ します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-146">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="7bf84-147">最後に、次のように入力して、すべてのフロントエンド サーバーのレプリカの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-147">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="7bf84-148">すべてのレプリカの値が True であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-148">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="7bf84-149">手順 7. に進みます。</span><span class="sxs-lookup"><span data-stu-id="7bf84-149">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="7bf84-150">バックアップ プールのバック エンド サーバーに中央管理ストアをインストール \_ します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-150">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="7bf84-151">最初に、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-151">First, run the following command:</span></span>
        ```PowerShell
         
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="7bf84-152">バックアップ プールのフロントエンド サーバーの 1 つで次のコマンドを実行して、中央管理ストアの移動 \_ を強制します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-152">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="7bf84-153">移動が完了したことを検証します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-153">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="7bf84-154">ActiveMasterFQDN と ActiveFileTransferAgents の両方がバックアップ プールの FQDN をポイントしているのを確認 \_ します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-154">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="7bf84-155">すべてのフロントエンド サーバーのレプリカの状態を確認するために、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-155">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="7bf84-156">すべてのレプリカの値が True であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-156">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="7bf84-157">バックアップ プール内の残りのフロントエンド サーバーに中央管理サーバー サービスをインストール \_ します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-157">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="7bf84-158">これを行うには、すべてのフロントエンド サーバーで次のコマンドを実行します。ただし、この手順の前に中央管理ストアを移動する際に使用したコマンドを除く。</span><span class="sxs-lookup"><span data-stu-id="7bf84-158">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="7bf84-159">Skype for Business Server 管理シェル ウィンドウで次のコマンドレットを実行して、Pool1 から Pool2 にユーザーをフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="7bf84-159">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Skype for Business Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="7bf84-160">中央管理ストアの状態を確認するためにこの手順の前の部分で実行した手順は汎用的ではないので、中央管理ストアがまだ完全にフェールオーバーしていないので、このコマンドレットが失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7bf84-160">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="7bf84-161">この場合は、表示されるエラー メッセージに基づいて中央管理ストアを修正し、このコマンドレットを再度実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7bf84-161">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="7bf84-p113">次のエラー メッセージが表示される場合は、プールをフェールオーバーする前に、このサイトのエッジ プールを変更して別のプールを次ホップとして使用する必要があります。詳細については、このトピックの冒頭に掲載される手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7bf84-p113">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool. For details, see the procedures at the beginning of this topic.</span></span>
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a><span data-ttu-id="7bf84-164">プールをフェールバックする</span><span class="sxs-lookup"><span data-stu-id="7bf84-164">Fail back a pool</span></span>

<span data-ttu-id="7bf84-165">障害が起きたプール (この例では Pool1) がオンラインに戻ったら、次の手順を実行して、展開を通常の状態に稼働状態に戻します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-165">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="7bf84-166">フェールバック プロセスは完了するまで数分かかることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7bf84-166">Note that the failback process takes several minute to complete.</span></span>  <span data-ttu-id="7bf84-167">参考として、20,000 名のユーザーのプールでは、最大 60 分かかることが予想されます。</span><span class="sxs-lookup"><span data-stu-id="7bf84-167">For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="7bf84-168">次のコマンドレットを入力して、もともと Pool1 に属していて Pool2 にフェールオーバーされたユーザーをフェールバックします。</span><span class="sxs-lookup"><span data-stu-id="7bf84-168">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="7bf84-169">それ以外の操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="7bf84-169">No other steps are necessary.</span></span> <span data-ttu-id="7bf84-170">中央管理サーバーをフェールオーバーした場合は、Pool2 のままにしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="7bf84-170">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a><span data-ttu-id="7bf84-171">Skype for Business Server フェデレーションに使用されるエッジ プールをフェールオーバーする</span><span class="sxs-lookup"><span data-stu-id="7bf84-171">Fail over the Edge pool used for Skype for Business Server federation</span></span> 

<span data-ttu-id="7bf84-172">Skype for Business Server フェデレーションが構成されているエッジ プールがダウンした場合は、フェデレーションが機能するために別のエッジ プールを使用するようにフェデレーションを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7bf84-172">If the Edge pool where you have Skype for Business Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

1.  <span data-ttu-id="7bf84-173">フロントエンド サーバーでトポロジ ビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="7bf84-173">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="7bf84-174">[ **エッジ プール]** を展開し、フェデレーション用に現在構成されているエッジ サーバーまたはエッジ サーバー プールを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="7bf84-174">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="7bf84-175">[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7bf84-175">Select **Edit properties**.</span></span>

2.  <span data-ttu-id="7bf84-176">[**全般**] の [**プロパティの編集**] で、[**このエッジ プールのフェデレーションの有効化 (ポート 5061)**] をオフにします。</span><span class="sxs-lookup"><span data-stu-id="7bf84-176">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="7bf84-177">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7bf84-177">Click **OK**.</span></span>

3.  <span data-ttu-id="7bf84-178">[ **エッジ プール]** を展開し、フェデレーションに使用するエッジ サーバーまたはエッジ サーバー プールを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="7bf84-178">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that you now want to use for Federation.</span></span> <span data-ttu-id="7bf84-179">[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7bf84-179">Select **Edit properties**.</span></span>

4.  <span data-ttu-id="7bf84-p119">[**全般**] の [**プロパティの編集**] で、[**このエッジ プールのフェデレーションの有効化 (ポート 5061)**] をオンにします。[**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-p119">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>

5.  <span data-ttu-id="7bf84-p120">[**アクション**] をクリックし、[**トポロジ**]、[**公開**] の順に選択します。[**トポロジの公開**] で入力を求められたら、[**次へ**] をクリックします。公開の終了後、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7bf84-p120">Click **Action**, select **Topology**, select **Publish**. When prompted on **Publish the topology**, click **Next**. When the Publish is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="7bf84-185">エッジ サーバーで、Skype for Business Server 展開ウィザードを開きます。</span><span class="sxs-lookup"><span data-stu-id="7bf84-185">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="7bf84-186">[Skype **for Business Server システムのインストールまたは更新] を** クリックし、[Skype for Business Server コンポーネントのセットアップまたは削除] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="7bf84-186">Click **Install or Update Skype for Business Server System**, and then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="7bf84-187">[**再実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7bf84-187">Click **Run Again**.</span></span>

7.  <span data-ttu-id="7bf84-188">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7bf84-188">Click **Next**.</span></span> <span data-ttu-id="7bf84-189">概要画面に、実行されたアクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7bf84-189">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="7bf84-190">展開が完了したら、[**ログの表示**] をクリックして、参照できるログ ファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-190">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="7bf84-191">[**完了**] をクリックして、展開を完了します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-191">Click **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="7bf84-192">失敗したエッジ プールを含むサイトにまだ稼動中のフロントエンド サーバーがある場合は、まだ稼動中のリモート サイトのエッジ プールを使用するように、これらのフロントエンド プールの Web 会議サービスおよび音声ビデオ会議サービスを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7bf84-192">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to use an Edge pool in a remote site that is still running.</span></span> 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a><span data-ttu-id="7bf84-193">Skype for Business Server で XMPP フェデレーションに使用されるエッジ プールをフェールオーバーする</span><span class="sxs-lookup"><span data-stu-id="7bf84-193">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span> 

<span data-ttu-id="7bf84-p123">組織内に XMPP フェデレーションに使用するプールとして指定されたエッジ プールが 1 つあるとします。このプールがダウンした場合、XMPP フェデレーションを再び機能させるには、XMPP フェデレーションをフェールオーバーして別のエッジ プールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7bf84-p123">In your organization, there is one Edge pool designated as the pool to use for XMPP federation. If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="7bf84-196">エッジ プールを初めてインストールし、XMPP フェデレーションを有効にするときに、1 つのエッジ プールではなく、すべてのエッジ プールで XMPP フェデレーションの外部 DNS SRV レコードを設定することで障害復旧プロセスを簡素化できます。</span><span class="sxs-lookup"><span data-stu-id="7bf84-196">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="7bf84-197">これらの SRV レコードには、それぞれ異なる優先順位が設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7bf84-197">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="7bf84-198">すべての XMPP フェデレーション トラフィックは、優先順位が最も高い SRV レコードを使用してプールを通過します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-198">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> 

<span data-ttu-id="7bf84-199">次の手順では、EdgePool1 は XMPP フェデレーションをホストしていた元のプールを表し、EdgePool2 は XMPP フェデレーションをこれからホストするプールを表します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-199">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="7bf84-200">XMPP フェデレーションに使用するエッジ プールをフェールオーバーするには</span><span class="sxs-lookup"><span data-stu-id="7bf84-200">To fail over the Edge pool used for XMPP federation</span></span>

1.  <span data-ttu-id="7bf84-201">(現在ダウンしているエッジ プール以外の) 別のエッジ プールをまだ展開していない場合は、そのプールを展開します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-201">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> 

2.  <span data-ttu-id="7bf84-202">XMPP フェデレーションをホストする新しいエッジ プール (EdgePool2) の各エッジ サーバーで、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-202">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="7bf84-203">XMPP フェデレーション ルートを変更して EdgePool2 を指すようにするには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-203">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="7bf84-204">この例で、Site2 は XMPP フェデレーション ルートをこれからホストするエッジ プールを含むサイトを表します。また、EdgeServer2.contoso.com はそのプール内のエッジ サーバーの FQDN です。</span><span class="sxs-lookup"><span data-stu-id="7bf84-204">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="7bf84-205">外部 DNS サーバーで、XMPP フェデレーションの DNS A レコードを変更して、EdgeServer2.contoso.com を指すようにします。</span><span class="sxs-lookup"><span data-stu-id="7bf84-205">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="7bf84-p125">XMPP フェデレーションをホストする新しいエッジ プールに解決される、XMPP フェデレーションの DNS SRV レコードがまだない場合は、次の例に示すように、このレコードを追加する必要があります。この SRV レコードには、ポート値 5269 が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7bf84-p125">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="7bf84-208">XMPP フェデレーションをホストする新しいエッジ プールで、ポート 5269 が外部に開いていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-208">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="7bf84-209">XMPP フェデレーションをホストする新しいエッジ プール内のすべてのエッジ サーバーでサービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-209">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a><span data-ttu-id="7bf84-210">Skype for Business Server フェデレーションまたは XMPP フェデレーションに使用されるエッジ プールのフェールバック</span><span class="sxs-lookup"><span data-stu-id="7bf84-210">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span> 

<span data-ttu-id="7bf84-211">フェデレーションをホストするために使用した障害が発生したエッジ プールをオンラインに戻した後、この手順を使用して Skype for Business Server フェデレーション ルートまたは XMPP フェデレーション ルートをフェールバックし、この復元されたエッジ プールを再度使用します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-211">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Skype for Business Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

1.  <span data-ttu-id="7bf84-212">再び使用できるようになったエッジ プールで、エッジ サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-212">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="7bf84-213">復元されたエッジ サーバーを使用するために Skype for Business Server フェデレーション ルートをフェールバックする場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-213">If you want to fail back the Skype for Business Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="7bf84-p126">フロントエンド サーバーでトポロジ ビルダーを開きます。[**エッジ プール**] を展開し、現在フェデレーションに構成されているエッジ サーバーまたはエッジ サーバー プールを右クリックして、[**プロパティの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-p126">On a Front End server, open Topology Builder. Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation. Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="7bf84-p127">[**プロパティの編集**] の [**全般**] で、[**このエッジ プールのフェデレーションの有効化 (ポート 5061)**] をクリアします。[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7bf84-p127">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>
    
      - <span data-ttu-id="7bf84-p128">[**エッジ プール**] を展開し、フェデレーションに再び使用する元のエッジ サーバーまたはエッジ サーバー プールを右クリックします。[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7bf84-p128">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation. Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="7bf84-p129">[**プロパティの編集**] の [**全般**] で、[**このエッジ プールのフェデレーションの有効化 (ポート 5061)**] を選択します。[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7bf84-p129">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>
    
      - <span data-ttu-id="7bf84-p130">[**アクション**] をクリックし、[**トポロジ**]、[**公開**] の順に選択します。[**トポロジの公開**] で入力を求められたら、[**次へ**] をクリックします。公開の終了後、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7bf84-p130">Click **Action**, select **Topology**, select **Publish**. When prompted on **Publish the topology**, click **Next**. When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="7bf84-226">エッジ サーバーで、Skype for Business Server 展開ウィザードを開きます。</span><span class="sxs-lookup"><span data-stu-id="7bf84-226">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="7bf84-227">[Skype **for Business Server システムのインストールまたは更新] を** クリックし、[Skype for Business Server コンポーネントのセットアップまたは削除] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="7bf84-227">Click **Install or Update Skype for Business Server System**, then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="7bf84-228">[**再実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7bf84-228">Click **Run Again**.</span></span>
    
      - <span data-ttu-id="7bf84-229">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7bf84-229">Click **Next**.</span></span> <span data-ttu-id="7bf84-230">概要画面に、実行されたアクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7bf84-230">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="7bf84-231">展開が完了したら、[**ログの表示**] をクリックして、参照できるログ ファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-231">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="7bf84-232">[**完了**] をクリックして、展開を完了します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-232">Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="7bf84-233">復旧されたエッジ サーバーが使用されるように XMPP フェデレーション ルートをフェールバックするには以下を行います。</span><span class="sxs-lookup"><span data-stu-id="7bf84-233">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="7bf84-234">以下のコマンドレットを実行して、XMPP フェデレーション ルートが、XMPP フェデレーションをホストするようになるエッジ プール (この例では、EdgeServer1) を再び指すようにします。</span><span class="sxs-lookup"><span data-stu-id="7bf84-234">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="7bf84-235">この例では、Site1 は XMPP フェデレーション ルートをホストするようになるエッジ プールを含むサイトです。EdgeServer1.contoso.com はそのプール内のエッジ サーバーの FQDN です。</span><span class="sxs-lookup"><span data-stu-id="7bf84-235">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="7bf84-p133">XMPP フェデレーションをホストするようになるエッジ プールに解決される、XMPP フェデレーション用の DNS SRV レコードがまだない場合は、以下の例のようにそれを追加する必要があります。この SRV レコードはポート値が 5269 である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7bf84-p133">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="7bf84-238">外部 DNS サーバーで、XMPP フェデレーション用の DNS A レコードが EdgeServer2.contoso.com を指すように変更します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-238">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="7bf84-239">XMPP フェデレーションをホストするようになるエッジ プールがポート 5269 を外部にオープンしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-239">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="7bf84-240">障害発生後に復旧されたエッジ プールを含むサイトで、フロントエンド プールが実行を続けていた場合は、それらのフロントエンド プール上の Web 会議サービスおよび音声ビデオ会議サービスを更新して、ローカル サイトのエッジ プールが再び使用されるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="7bf84-240">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span>

5.  <span data-ttu-id="7bf84-241">停止したエッジ プールと同じサイトでフロントエンド プールも停止していた場合は、Invoke–CsPoolFailback を使ってフロントエンド プールをフェールバックできます。</span><span class="sxs-lookup"><span data-stu-id="7bf84-241">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="7bf84-242">フロントエンド プールに関連付けられているエッジ プールを変更する</span><span class="sxs-lookup"><span data-stu-id="7bf84-242">Change the Edge pool associated with a Front End pool</span></span>

<span data-ttu-id="7bf84-243">エッジ プールがダウンして同じサイトのフロントエンド プールがまだ実行中の場合、問題の発生したエッジ プールが復元されるまで、別のサイトのエッジ プールを使用するようにフロントエンド プールを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7bf84-243">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

1.  <span data-ttu-id="7bf84-244">トポロジ ビルダーで、変更するフロントエンド プールの名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-244">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="7bf84-245">プールを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7bf84-245">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="7bf84-246">[**関連付け**] セクションの、[**エッジ プールの関連付け (メディア コンポーネント用) の**] 下のドロップダウン ボックスを使用して、このフロントエンド プールを関連付けるエッジ プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="7bf84-246">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="7bf84-247">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7bf84-247">Click **OK**.</span></span>
