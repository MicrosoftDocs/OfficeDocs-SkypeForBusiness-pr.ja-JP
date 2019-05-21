---
title: プールのフェールオーバーおよびフェールバック
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: .
ms.openlocfilehash: 2848261164ac568d3db4dd05160b7e50ec3981d3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303891"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a><span data-ttu-id="261e4-103">Skype for Business Server でのプールのフェイルオーバーとフェイルバック</span><span class="sxs-lookup"><span data-stu-id="261e4-103">Failing over and failing back a pool in Skype for Business Server</span></span> 

<span data-ttu-id="261e4-104">1つのフロントエンドプールで障害が発生してフェールオーバーが発生した場合、または障害が発生したプールがオンライン状態に戻っている場合は、次の手順を実行します。展開を通常の作業状態に戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="261e4-104">Use the following procedures if a single Front End pool has failed and needs to be failed over, or the pool that experienced the disaster is back online and you need to restore your deployment to regular working status.</span></span> <span data-ttu-id="261e4-105">また、Skype for Business フェデレーションまたは XMPP フェデレーションに使用されるエッジプールをフェイルオーバーしてフェールバックする方法や、フロントエンドプールに関連付けられているエッジプールを変更する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="261e4-105">Also  learn how to fail over and fail back the Edge pool used for Skype for Business federation or XMPP federation, or change the Edge pool associated with a Front End pool.</span></span>

- [<span data-ttu-id="261e4-106">フロントエンドプールのフェイルオーバー</span><span class="sxs-lookup"><span data-stu-id="261e4-106">Fail over a Front End pool</span></span>](#fail-over-a-front-end-pool)
- [<span data-ttu-id="261e4-107">プールのフェイルバック</span><span class="sxs-lookup"><span data-stu-id="261e4-107">Fail back a pool</span></span>](#fail-back-a-pool)
- [<span data-ttu-id="261e4-108">Skype for Business Server federation で使用されるエッジプールをフェイルオーバーする</span><span class="sxs-lookup"><span data-stu-id="261e4-108">Fail over the Edge pool used for Skype for Business Server federation</span></span>](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [<span data-ttu-id="261e4-109">Skype for Business Server の XMPP フェデレーションに使用されるエッジプールをフェールオーバーする</span><span class="sxs-lookup"><span data-stu-id="261e4-109">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span>](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [<span data-ttu-id="261e4-110">Skype for Business Server federation または XMPP フェデレーションに使用されるエッジプールのフェイルバック</span><span class="sxs-lookup"><span data-stu-id="261e4-110">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span>](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [<span data-ttu-id="261e4-111">フロントエンドプールに関連付けられているエッジプールを変更する</span><span class="sxs-lookup"><span data-stu-id="261e4-111">Change the Edge pool associated with a Front End pool</span></span>](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a><span data-ttu-id="261e4-112">フロントエンドプールのフェイルオーバー</span><span class="sxs-lookup"><span data-stu-id="261e4-112">Fail over a Front End pool</span></span>

<span data-ttu-id="261e4-113">この手順では、Datacenter1 に Pool1 が含まれており、Pool1 は失敗しています。</span><span class="sxs-lookup"><span data-stu-id="261e4-113">In this procedure, Datacenter1 contains Pool1, and Pool1 has failed.</span></span> <span data-ttu-id="261e4-114">Datacenter2 にある Pool2 にフェイルオーバーしています。</span><span class="sxs-lookup"><span data-stu-id="261e4-114">You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="261e4-115">プールフェールオーバーのほとんどの作業には、必要に応じて、中央管理ストアのフェールオーバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="261e4-115">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="261e4-116">プールのユーザーがフェールオーバーされた場合は、中央管理ストアが機能している必要があるため、これは重要です。</span><span class="sxs-lookup"><span data-stu-id="261e4-116">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="261e4-117">さらに、フロントエンドプールに障害が発生しても、そのサイトの Edge プールがまだ実行されている場合は、Edge プールが、失敗したプールを次のホッププールとして使用するかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="261e4-117">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool.</span></span> <span data-ttu-id="261e4-118">問題が発生した場合は、失敗したフロントエンドプールを使用するようにエッジプールを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="261e4-118">If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool.</span></span> <span data-ttu-id="261e4-119">次ホップの設定を変更する方法は、エッジプールと同じサイトのプールを使用するか、または別のサイトを使うかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="261e4-119">How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="261e4-120">**エッジプールで、同じサイトの次ホッププールを使用するように設定するには**</span><span class="sxs-lookup"><span data-stu-id="261e4-120">**To set an Edge pool to use a next hop pool at the same site**</span></span>

1.  <span data-ttu-id="261e4-121">トポロジビルダーを開き、変更する必要があるエッジプールを右クリックして、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="261e4-121">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="261e4-122">[**次ホップ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="261e4-122">Click **Next Hop**.</span></span> <span data-ttu-id="261e4-123">[ **Next ホッププール:** ] ボックスの一覧で、次ホッププールとして機能するプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="261e4-123">From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="261e4-124">[ **OK**] をクリックして、変更を公開します。</span><span class="sxs-lookup"><span data-stu-id="261e4-124">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="261e4-125">**別のサイトで次ホッププールを使用するようにエッジプールを設定するには**</span><span class="sxs-lookup"><span data-stu-id="261e4-125">**To set an Edge pool to use a next hop pool at a different site**</span></span>

1.  <span data-ttu-id="261e4-126">Skype for Business Server 管理シェルウィンドウを開いて、次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="261e4-126">Open a Skype for Business Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="261e4-127">**障害が発生したプールをフェイルオーバーするには**</span><span class="sxs-lookup"><span data-stu-id="261e4-127">**To fail over a pool in a disaster**</span></span>

1.  <span data-ttu-id="261e4-128">Pool2 のフロントエンドサーバーに次のコマンドレットを入力して、中央管理サーバーのホストとなるプールを見つけます。</span><span class="sxs-lookup"><span data-stu-id="261e4-128">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="261e4-129">このコマンドレットの結果は、現在中央管理サーバーをホストしているプールを示します。</span><span class="sxs-lookup"><span data-stu-id="261e4-129">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="261e4-130">この手順の残りの部分では、このプールを CMS\_プールと呼びます。</span><span class="sxs-lookup"><span data-stu-id="261e4-130">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="261e4-131">トポロジビルダーを使用して、CMS\_プールで実行されている Skype For business Server のバージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="261e4-131">Use Topology Builder to find the version of Skype for Business Server running on the CMS\_Pool.</span></span> <span data-ttu-id="261e4-132">Skype for Business Server を実行している場合は、次のコマンドレットを使用して、Pool 1 のバックアッププールを検索します。</span><span class="sxs-lookup"><span data-stu-id="261e4-132">If it is running Skype for Business Server, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="261e4-133">バックアップ\_プールをバックアッププールにします。</span><span class="sxs-lookup"><span data-stu-id="261e4-133">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="261e4-134">次のコマンドレットを使用して、サーバーの全体管理ストアの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="261e4-134">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="261e4-135">このコマンドレットでは、ActiveMasterFQDN と ActiveFileTransferAgents の両方が CMS\_プールの FQDN を指していることを示しています。</span><span class="sxs-lookup"><span data-stu-id="261e4-135">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="261e4-136">空の場合は、サーバーの全体管理サーバーを利用できないため、フェールオーバーを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="261e4-136">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="261e4-137">中央管理ストアを使用できない場合、または Pool1 で中央管理ストアが実行されている場合 (つまり、失敗したプール)、プールをフェールオーバーする前に、中央管理サーバーをフェールオーバーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="261e4-137">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="261e4-138">Skype for Business Server を実行しているプールでホストされていた中央管理サーバーをフェールオーバーする必要がある場合は、この手順の手順5のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="261e4-138">If you need to fail over the Central Management Server that was hosted on a pool running Skype for Business Server, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="261e4-139">サーバーの全体管理サーバーにフェールオーバーする必要がない場合は、手順7に進んでください。</span><span class="sxs-lookup"><span data-stu-id="261e4-139">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="261e4-140">Skype for Business Server を実行しているプールの中央管理ストアをフェールオーバーするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="261e4-140">To fail over the Central Management store on a pool running Skype for Business Server, do the following:</span></span>
    
      - <span data-ttu-id="261e4-141">まず、次のように入力して\_、バックアッププールのどのバックエンドサーバーで中央管理ストアのプリンシパルインスタンスを実行するかを確認します。</span><span class="sxs-lookup"><span data-stu-id="261e4-141">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="261e4-142">バックアップ\_プールのプライマリバックエンドサーバーがプリンシパルである場合は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="261e4-142">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="261e4-143">バックアップ\_プールのミラーバックエンドサーバーがプリンシパルである場合は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="261e4-143">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="261e4-144">サーバーの全体のフェールオーバーが完了していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="261e4-144">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="261e4-145">次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="261e4-145">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="261e4-146">ActiveMasterFQDN と ActiveFileTransferAgents の両方がバックアップ\_プールの FQDN を指していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="261e4-146">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="261e4-147">最後に、次のように入力して、すべてのフロントエンドサーバーのレプリカの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="261e4-147">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="261e4-148">すべてのレプリカの値が True であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="261e4-148">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="261e4-149">この手順の手順7に進みます。</span><span class="sxs-lookup"><span data-stu-id="261e4-149">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="261e4-150">バックアップ\_プールのバックエンドサーバーに中央管理ストアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="261e4-150">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="261e4-151">最初に、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="261e4-151">First, run the following command:</span></span>
        
        ``` 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="261e4-152">バックアップ\_プールのいずれかのフロントエンドサーバーで次のコマンドを実行して、中央管理ストアの移動を強制します。</span><span class="sxs-lookup"><span data-stu-id="261e4-152">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="261e4-153">移動が完了したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="261e4-153">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="261e4-154">ActiveMasterFQDN と ActiveFileTransferAgents の両方がバックアップ\_プールの FQDN を指していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="261e4-154">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="261e4-155">次のように入力して、すべてのフロントエンドサーバーのレプリカの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="261e4-155">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="261e4-156">すべてのレプリカの値が True であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="261e4-156">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="261e4-157">中央管理サーバーサービスを、バックアップ\_プールのフロントエンドサーバーの残りの部分にインストールします。</span><span class="sxs-lookup"><span data-stu-id="261e4-157">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="261e4-158">この操作を行うには、この手順の最初に中央管理ストアを強制するときに使用したものを除き、すべてのフロントエンドサーバーで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="261e4-158">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="261e4-159">Skype for Business Server 管理シェルウィンドウで次のコマンドレットを実行して、Pool1 から Pool2 にユーザーをフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="261e4-159">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Skype for Business Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="261e4-160">この手順の前の部分で実行した手順では、全体管理ストアの状態を確認する必要があるため、中央管理ストアはまだ完全にフェールオーバーしていないため、このコマンドレットは失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="261e4-160">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="261e4-161">この場合は、表示されるエラーメッセージに基づいて、中央管理ストアを修正し、このコマンドレットをもう一度実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="261e4-161">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="261e4-162">次のエラーメッセージが表示された場合は、プールをフェールオーバーする前に、このサイトの Edge プールを別のホップとして使用するように変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="261e4-162">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool.</span></span> <span data-ttu-id="261e4-163">詳細については、このトピックの最初の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="261e4-163">For details, see the procedures at the beginning of this topic.</span></span>
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a><span data-ttu-id="261e4-164">プールのフェイルバック</span><span class="sxs-lookup"><span data-stu-id="261e4-164">Fail back a pool</span></span>

<span data-ttu-id="261e4-165">障害が発生したプールがオンラインに戻る (この例では Pool1 である) 場合は、次の手順を実行して、展開を通常の作業状態に戻します。</span><span class="sxs-lookup"><span data-stu-id="261e4-165">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="261e4-166">フェイルバックプロセスが完了するまでに数分かかることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="261e4-166">Note that the failback process takes several minute to complete.</span></span><span data-ttu-id="261e4-167">参照の場合、2万ユーザーのプールには最大60分かかることが予想されます。</span><span class="sxs-lookup"><span data-stu-id="261e4-167">  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="261e4-168">最初に Pool1 をホームにし、次のコマンドレットを入力して、Pool2 にフェイルオーバーしているユーザーをフェールバックします。</span><span class="sxs-lookup"><span data-stu-id="261e4-168">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="261e4-169">その他の手順は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="261e4-169">No other steps are necessary.</span></span> <span data-ttu-id="261e4-170">中央管理サーバーで障害が発生した場合は、Pool2 にそのままにしておくことができます。</span><span class="sxs-lookup"><span data-stu-id="261e4-170">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a><span data-ttu-id="261e4-171">Skype for Business Server federation で使用されるエッジプールをフェイルオーバーする</span><span class="sxs-lookup"><span data-stu-id="261e4-171">Fail over the Edge pool used for Skype for Business Server federation</span></span> 

<span data-ttu-id="261e4-172">Skype for Business Server フェデレーションが構成されている Edge プールが停止している場合は、フェデレーションが機能するために別のエッジプールを使用するようにフェデレーションを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="261e4-172">If the Edge pool where you have Skype for Business Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

1.  <span data-ttu-id="261e4-173">フロントエンドサーバーで、[トポロジビルダー] を開きます。</span><span class="sxs-lookup"><span data-stu-id="261e4-173">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="261e4-174">[**エッジプール**] を展開し、現在フェデレーション用に構成されているエッジサーバープールまたはエッジサーバープールを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="261e4-174">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="261e4-175">[**プロパティの編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="261e4-175">Select **Edit properties**.</span></span>

2.  <span data-ttu-id="261e4-176">[**プロパティの編集**] の [**全般**] で、[**このエッジプールに対してフェデレーションを有効にする (ポート 5061)**] をオフにします。</span><span class="sxs-lookup"><span data-stu-id="261e4-176">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="261e4-177">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="261e4-177">Click **OK**.</span></span>

3.  <span data-ttu-id="261e4-178">[**エッジプール**] を展開して、フェデレーションに使用するエッジサーバーまたはエッジサーバープールを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="261e4-178">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that you now want to use for Federation.</span></span> <span data-ttu-id="261e4-179">[**プロパティの編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="261e4-179">Select **Edit properties**.</span></span>

4.  <span data-ttu-id="261e4-180">[**プロパティの編集**] の [**全般**] で、[**このエッジプールに対してフェデレーションを有効にする (ポート 5061)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="261e4-180">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="261e4-181">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="261e4-181">Click **OK**.</span></span>

5.  <span data-ttu-id="261e4-182">[**アクション**] をクリックし、[**トポロジ**] を選択し、[**発行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="261e4-182">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="261e4-183">**トポロジの発行**を求められたら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="261e4-183">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="261e4-184">発行が完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="261e4-184">When the Publish is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="261e4-185">エッジサーバーで、Skype for Business Server 展開ウィザードを開きます。</span><span class="sxs-lookup"><span data-stu-id="261e4-185">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="261e4-186">[ **Skype For Business Server システムのインストールまたは更新**] をクリックし、[**セットアップ] または [Skype For business Server コンポーネントの削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="261e4-186">Click **Install or Update Skype for Business Server System**, and then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="261e4-187">[**実行] をもう一度**クリックします。</span><span class="sxs-lookup"><span data-stu-id="261e4-187">Click **Run Again**.</span></span>

7.  <span data-ttu-id="261e4-188">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="261e4-188">Click **Next**.</span></span> <span data-ttu-id="261e4-189">概要画面には、実行中の操作が表示されます。</span><span class="sxs-lookup"><span data-stu-id="261e4-189">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="261e4-190">展開が完了したら、[**ログの表示**] をクリックして、利用可能なログファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="261e4-190">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="261e4-191">[**完了**] をクリックして展開を完了します。</span><span class="sxs-lookup"><span data-stu-id="261e4-191">Click **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="261e4-192">問題のあるエッジプールを含むサイトにまだ実行されているフロントエンドサーバーが含まれている場合は、これらのフロントエンドプールの Web 会議サービスと A/V 会議サービスを更新して、まだ実行中のリモートサイトでエッジプールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="261e4-192">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to use an Edge pool in a remote site that is still running.</span></span> 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a><span data-ttu-id="261e4-193">Skype for Business Server の XMPP フェデレーションに使用されるエッジプールをフェールオーバーする</span><span class="sxs-lookup"><span data-stu-id="261e4-193">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span> 

<span data-ttu-id="261e4-194">組織では、1つのエッジプールがプールとして指定されています。</span><span class="sxs-lookup"><span data-stu-id="261e4-194">In your organization, there is one Edge pool designated as the pool to use for XMPP federation.</span></span> <span data-ttu-id="261e4-195">このプールがダウンした場合は、xmpp フェデレーションを再度使用する前に、別のエッジプールを使用するために XMPP フェデレーションをフェイルオーバーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="261e4-195">If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="261e4-196">最初に Edge プールをインストールして XMPP フェデレーションを有効にすると、1つの代わりに XMPP のすべてのエッジプールの外部 DNS SRV レコードを設定することで、障害回復プロセスを簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="261e4-196">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="261e4-197">各 SRV レコードには、異なる優先順位を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="261e4-197">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="261e4-198">すべての XMPP フェデレーショントラフィックは、最も優先度の高い SRV レコードを持つプールを通過します。</span><span class="sxs-lookup"><span data-stu-id="261e4-198">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> 

<span data-ttu-id="261e4-199">次の手順では、EdgePool1 は最初に XMPP フェデレーションをホストしたプールであり、EdgePool2 は XMPP フェデレーションをホストするプールです。</span><span class="sxs-lookup"><span data-stu-id="261e4-199">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="261e4-200">XMPP フェデレーションに使用されるエッジプールをフェイルオーバーするには</span><span class="sxs-lookup"><span data-stu-id="261e4-200">To fail over the Edge pool used for XMPP federation</span></span>

1.  <span data-ttu-id="261e4-201">(現在ダウンしている) 別の Edge プールをまだ展開していない場合は、そのプールを展開します。</span><span class="sxs-lookup"><span data-stu-id="261e4-201">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> 

2.  <span data-ttu-id="261e4-202">新しいエッジプールの各エッジサーバーで XMPP federation (EdgePool2) をホストするために、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="261e4-202">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="261e4-203">XMPP フェデレーションルートを EdgePool2 に再ポイントするには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="261e4-203">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="261e4-204">この例では、Site2 は、XMPP フェデレーションルートをホストするエッジプールが含まれているサイトで、EdgeServer2.contoso.com はそのプールのエッジサーバーの FQDN です。</span><span class="sxs-lookup"><span data-stu-id="261e4-204">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="261e4-205">外部 DNS サーバーで、XMPP フェデレーション用の DNS A レコードを EdgeServer2.contoso.com に変更します。</span><span class="sxs-lookup"><span data-stu-id="261e4-205">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="261e4-206">Xmpp フェデレーション用の DNS SRV レコードをまだ持っていない場合は、次の例のように、それを追加する必要があります。これは、現在 XMPP フェデレーションをホストしています。</span><span class="sxs-lookup"><span data-stu-id="261e4-206">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="261e4-207">この SRV レコードには、5269のポート値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="261e4-207">This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="261e4-208">XMPP フェデレーションをホストしている Edge プールのポート5269が外部で開かれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="261e4-208">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="261e4-209">Edge プール内のすべてのエッジサーバーでサービスを開始します。これで、XMPP フェデレーションがホストされます。</span><span class="sxs-lookup"><span data-stu-id="261e4-209">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a><span data-ttu-id="261e4-210">Skype for Business Server federation または XMPP フェデレーションに使用されるエッジプールのフェイルバック</span><span class="sxs-lookup"><span data-stu-id="261e4-210">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span> 

<span data-ttu-id="261e4-211">フェデレーションをホストするために使用された、失敗したエッジプールをオンラインに戻した後、次の手順を実行して、Skype for Business Server フェデレーションルートまたは XMPP フェデレーションルートをフェイルバックし、この復元されたエッジプールを再び使用します。</span><span class="sxs-lookup"><span data-stu-id="261e4-211">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Skype for Business Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

1.  <span data-ttu-id="261e4-212">もう一度使用できるようになったエッジプールで、エッジサービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="261e4-212">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="261e4-213">復元されたエッジサーバーを使用するために Skype for Business Server フェデレーションルートをフェイルバックする場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="261e4-213">If you want to fail back the Skype for Business Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="261e4-214">フロントエンドサーバーで、[トポロジビルダー] を開きます。</span><span class="sxs-lookup"><span data-stu-id="261e4-214">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="261e4-215">[ **Edge プール**] を展開して、フェデレーション用に現在構成されているエッジサーバープールまたはエッジサーバープールを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="261e4-215">Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="261e4-216">[**プロパティの編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="261e4-216">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="261e4-217">[**プロパティの編集**] の [**全般**] で、[**このエッジプールに対してフェデレーションを有効にする (ポート 5061)**] をオフにします。</span><span class="sxs-lookup"><span data-stu-id="261e4-217">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="261e4-218">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="261e4-218">Click **OK**.</span></span>
    
      - <span data-ttu-id="261e4-219">[ **Edge プール**] を展開し、もう一度フェデレーションに使用する元のエッジサーバープールまたはエッジサーバープールを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="261e4-219">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation.</span></span> <span data-ttu-id="261e4-220">[**プロパティの編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="261e4-220">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="261e4-221">[**プロパティの編集**] の [**全般**] で、[**このエッジプールに対してフェデレーションを有効にする (ポート 5061)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="261e4-221">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="261e4-222">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="261e4-222">Click **OK**.</span></span>
    
      - <span data-ttu-id="261e4-223">[**アクション**] をクリックし、[**トポロジ**] を選択し、[**発行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="261e4-223">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="261e4-224">**トポロジの発行**を求められたら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="261e4-224">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="261e4-225">発行が完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="261e4-225">When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="261e4-226">エッジサーバーで、Skype for Business Server 展開ウィザードを開きます。</span><span class="sxs-lookup"><span data-stu-id="261e4-226">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="261e4-227">[ **Skype For Business Server System をインストールまたは更新**する] をクリックし、[**セットアップ] または [Skype For business Server コンポーネントの削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="261e4-227">Click **Install or Update Skype for Business Server System**, then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="261e4-228">[**実行] をもう一度**クリックします。</span><span class="sxs-lookup"><span data-stu-id="261e4-228">Click **Run Again**.</span></span>
    
      - <span data-ttu-id="261e4-229">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="261e4-229">Click **Next**.</span></span> <span data-ttu-id="261e4-230">概要画面には、実行中の操作が表示されます。</span><span class="sxs-lookup"><span data-stu-id="261e4-230">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="261e4-231">展開が完了したら、[**ログの表示**] をクリックして、利用可能なログファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="261e4-231">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="261e4-232">[**完了**] をクリックして展開を完了します。</span><span class="sxs-lookup"><span data-stu-id="261e4-232">Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="261e4-233">復元されたエッジサーバーを使用するために XMPP フェデレーションルートをフェイルバックする場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="261e4-233">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="261e4-234">次のコマンドレットを実行して、xmpp フェデレーションルートを Edge プールに再ポイントします。これにより、XMPP フェデレーションがホストされます (この例では EdgeServer1)。</span><span class="sxs-lookup"><span data-stu-id="261e4-234">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="261e4-235">この例では、Site1 は、XMPP フェデレーションルートをホストするエッジプールが含まれているサイトで、EdgeServer1.contoso.com はそのプールのエッジサーバーの FQDN です。</span><span class="sxs-lookup"><span data-stu-id="261e4-235">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="261e4-236">Xmpp フェデレーション用の DNS SRV レコードをまだ持っていない場合は、次の例のように、それを追加する必要があります。これは、現在 XMPP フェデレーションをホストしています。</span><span class="sxs-lookup"><span data-stu-id="261e4-236">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="261e4-237">この SRV レコードには、5269のポート値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="261e4-237">This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="261e4-238">外部 DNS サーバーで、XMPP フェデレーション用の DNS A レコードを EdgeServer2.contoso.com に変更します。</span><span class="sxs-lookup"><span data-stu-id="261e4-238">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="261e4-239">XMPP フェデレーションをホストしている Edge プールのポート5269が外部で開かれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="261e4-239">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="261e4-240">フロントエンドプールが、失敗して復元されたエッジプールが含まれているサイトでまだ実行されている場合は、これらのフロントエンドプールの Web 会議サービスと A/V 会議サービスを更新して、もう一度ローカルサイトでエッジプールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="261e4-240">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span>

5.  <span data-ttu-id="261e4-241">障害が発生したエッジプールと同じサイトのフロントエンドプールでもエラーが発生する場合は、CsPoolFailback を使ってフロントエンドプールをフェールバックすることができます。</span><span class="sxs-lookup"><span data-stu-id="261e4-241">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="261e4-242">フロントエンドプールに関連付けられているエッジプールを変更する</span><span class="sxs-lookup"><span data-stu-id="261e4-242">Change the Edge pool associated with a Front End pool</span></span>

<span data-ttu-id="261e4-243">エッジプールがダウンしていても、同じサイトのフロントエンドプールがまだ実行されている場合は、失敗したエッジプールが復元されるまで、別のサイトでエッジプールを使用するようにフロントエンドプールを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="261e4-243">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

1.  <span data-ttu-id="261e4-244">[Topology Builder] で、変更する必要があるフロントエンドプールの名前に移動します。</span><span class="sxs-lookup"><span data-stu-id="261e4-244">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="261e4-245">プールを右クリックし、[プロパティの**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="261e4-245">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="261e4-246">[**関連付け**] セクションの [ **Edge プールの関連付け (メディアコンポーネントの場合)**] で、ドロップダウンボックスを使用して、このフロントエンドプールを関連付けるエッジプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="261e4-246">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="261e4-247">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="261e4-247">Click **OK**.</span></span>
