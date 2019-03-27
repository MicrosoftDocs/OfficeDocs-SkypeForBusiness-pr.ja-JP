---
title: プールのフェールオーバーおよびフェールバック
ms.reviewer: ''
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: .
ms.openlocfilehash: 809d0305eaa4c8e2197c5137a647ff9354cbf9bd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899779"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a><span data-ttu-id="5ba61-103">Skype でプールをビジネス サーバーのフェイル バックをし、障害が発生しました。</span><span class="sxs-lookup"><span data-stu-id="5ba61-103">Failing over and failing back a pool in Skype for Business Server</span></span> 

<span data-ttu-id="5ba61-104">ニーズへのフェイル オーバー、または障害が発生したプールがオンラインに戻ると展開を通常の稼動状態に復元する必要があります 1 つのフロント エンド プールが失敗した場合は、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-104">Use the following procedures if a single Front End pool has failed and needs to be failed over, or the pool that experienced the disaster is back online and you need to restore your deployment to regular working status.</span></span> <span data-ttu-id="5ba61-105">フェイル オーバーおよびフェイル バックのビジネス連合の XMPP フェデレーションでは、Skype の使用しているエッジ プールする方法について説明し、フロント エンド プールに関連付けられているエッジ プールを変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="5ba61-105">Also  learn how to fail over and fail back the Edge pool used for Skype for Business federation or XMPP federation, or change the Edge pool associated with a Front End pool.</span></span>

- [<span data-ttu-id="5ba61-106">フロント エンド プールをフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="5ba61-106">Fail over a Front End pool</span></span>](#fail-over-a-front-end-pool)
- [<span data-ttu-id="5ba61-107">プールのフェイル バック</span><span class="sxs-lookup"><span data-stu-id="5ba61-107">Fail back a pool</span></span>](#fail-back-a-pool)
- [<span data-ttu-id="5ba61-108">Skype のビジネス サーバー連合を使用しているエッジ プールのフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="5ba61-108">Fail over the Edge pool used for Skype for Business Server federation</span></span>](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [<span data-ttu-id="5ba61-109">ビジネス サーバーの Skype の XMPP のフェデレーションに使用するエッジ プールのフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="5ba61-109">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span>](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [<span data-ttu-id="5ba61-110">ビジネス サーバーのフェデレーションまたは XMPP フェデレーションの Skype の使用されるエッジ プールのフェイル バック</span><span class="sxs-lookup"><span data-stu-id="5ba61-110">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span>](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [<span data-ttu-id="5ba61-111">フロント エンド プールに関連付けられたエッジ プールを変更します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-111">Change the Edge pool associated with a Front End pool</span></span>](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a><span data-ttu-id="5ba61-112">フロント エンド プールをフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="5ba61-112">Fail over a Front End pool</span></span>

<span data-ttu-id="5ba61-113">ここで Datacenter1 に Pool1 が含まれているし、Pool1 に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="5ba61-113">In this procedure, Datacenter1 contains Pool1, and Pool1 has failed.</span></span> <span data-ttu-id="5ba61-114">Datacenter2 にある Pool2 にフェールオーバーするとします。</span><span class="sxs-lookup"><span data-stu-id="5ba61-114">You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="5ba61-115">プールのフェールオーバーの処理のほとんどは、中央管理ストアでは、フェールオーバーが必要な場合。</span><span class="sxs-lookup"><span data-stu-id="5ba61-115">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="5ba61-116">プールのユーザーがフェールオーバーすると、中央管理ストアが機能する必要がありますので、これは重要です。</span><span class="sxs-lookup"><span data-stu-id="5ba61-116">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="5ba61-117">さらに、フロント エンド プールで障害が発生した場合はそのサイトのエッジ プールがまだ実行中、エッジ プールで障害が発生したプールを使用して、次ホップ プールとしてかどうかを知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ba61-117">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool.</span></span> <span data-ttu-id="5ba61-118">場合は、エッジ プールに障害が発生したフロント エンド プールで障害が発生した前に別のフロント エンド プールを使用してを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ba61-118">If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool.</span></span> <span data-ttu-id="5ba61-119">次ホップの設定を変更する方法は、エッジ、エッジのプールと同じサイトまたは別のサイトでプールを使用できるかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="5ba61-119">How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="5ba61-120">**同じサイトにある次ホップ プールを使用するのには、エッジ プールを設定するのには**</span><span class="sxs-lookup"><span data-stu-id="5ba61-120">**To set an Edge pool to use a next hop pool at the same site**</span></span>

1.  <span data-ttu-id="5ba61-121">トポロジ ビルダーを開き、変更する必要があるエッジ プールを右クリックし**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ba61-121">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="5ba61-122">[**次ホップ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ba61-122">Click **Next Hop**.</span></span> <span data-ttu-id="5ba61-123">**プールを次ホップ:** リストで、次ホップ プールとしてここで使用するプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-123">From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="5ba61-124">**[Ok]** をクリックし、変更内容を発行します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-124">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="5ba61-125">**別のサイトにある次ホップ プールを使用するのには、エッジ プールを設定するのには**</span><span class="sxs-lookup"><span data-stu-id="5ba61-125">**To set an Edge pool to use a next hop pool at a different site**</span></span>

1.  <span data-ttu-id="5ba61-126">Skype ビジネス サーバー管理シェル ウィンドウを開くし、次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-126">Open a Skype for Business Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="5ba61-127">**フェイル オーバー、災害時にプールに**</span><span class="sxs-lookup"><span data-stu-id="5ba61-127">**To fail over a pool in a disaster**</span></span>

1.  <span data-ttu-id="5ba61-128">プールは、Pool2 内のフロント エンド サーバーで次のコマンドレットを入力してサーバーの全体管理サーバーのホストを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ba61-128">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="5ba61-129">このプールは、サーバーの全体管理サーバーを現在ホスト コマンドレットの表示] の結果。</span><span class="sxs-lookup"><span data-stu-id="5ba61-129">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="5ba61-130">この手順の残りの部分で、このプールが CMS と呼ばれる\_プールです。</span><span class="sxs-lookup"><span data-stu-id="5ba61-130">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="5ba61-131">Cms を実行しているビジネス サーバーの Skype のバージョンを検索するのにはトポロジ ビルダーを使用して\_プールです。</span><span class="sxs-lookup"><span data-stu-id="5ba61-131">Use Topology Builder to find the version of Skype for Business Server running on the CMS\_Pool.</span></span> <span data-ttu-id="5ba61-132">Skype ビジネス サーバーは、実行している場合は、プール 1 のバックアップ ・ プールを検索するのには次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-132">If it is running Skype for Business Server, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="5ba61-133">バックアップを\_プールは、バックアップ ・ プールをします。</span><span class="sxs-lookup"><span data-stu-id="5ba61-133">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="5ba61-134">次のコマンドレットを使用して中央管理ストアの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-134">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="5ba61-135">このコマンドレットが ActiveMasterFQDN と ActiveFileTransferAgents の両方に、CMS の FQDN を指していることを表示する必要があります\_プールです。</span><span class="sxs-lookup"><span data-stu-id="5ba61-135">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="5ba61-136">空場合は、中央の管理サーバーが利用できないと、それをフェイル オーバーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ba61-136">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="5ba61-137">Pool1 に中央管理ストアが実行されていた場合、または中央管理ストアが利用できない場合 (つまり、障害が発生した)、プール、プールで障害が発生した前にサーバーの全体管理サーバーをフェールオーバーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ba61-137">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="5ba61-138">Skype を実行して、ビジネスのサーバーのプールでホストされるサーバーの全体管理サーバーのフェールオーバーが必要な場合は、この手順のステップ 5 で、コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-138">If you need to fail over the Central Management Server that was hosted on a pool running Skype for Business Server, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="5ba61-139">中央管理サーバーにフェールオーバーする必要がない場合は、この手順の手順 7 に進んでください。</span><span class="sxs-lookup"><span data-stu-id="5ba61-139">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="5ba61-140">Skype を実行して、ビジネスのサーバーのプールを中央管理ストアをフェールオーバーするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5ba61-140">To fail over the Central Management store on a pool running Skype for Business Server, do the following:</span></span>
    
      - <span data-ttu-id="5ba61-141">バック エンド サーバーのバックアップを確認して最初に、\_プールは、次を入力して主体の中央管理ストアのインスタンスを実行します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-141">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="5ba61-142">場合、プライマリ バック エンド サーバーのバックアップに\_プールでは、プリンシパルの種類。</span><span class="sxs-lookup"><span data-stu-id="5ba61-142">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="5ba61-143">場合ミラー バックアップでは、バック エンド サーバー\_プールでは、プリンシパルの種類。</span><span class="sxs-lookup"><span data-stu-id="5ba61-143">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="5ba61-144">中央管理サーバーのフェールオーバーが完了したことを検証します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-144">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="5ba61-145">次に入力します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-145">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="5ba61-146">ActiveMasterFQDN と ActiveFileTransferAgents の両方に、FQDN のバックアップを指していることを確認\_プールです。</span><span class="sxs-lookup"><span data-stu-id="5ba61-146">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="5ba61-147">最後に、次を入力してすべてのフロント エンド サーバーのレプリカの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-147">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="5ba61-148">True の値をすべてのレプリカがあることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5ba61-148">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="5ba61-149">この手順の手順 7 に進んでください。</span><span class="sxs-lookup"><span data-stu-id="5ba61-149">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="5ba61-150">バック エンド サーバーのバックアップを中央管理ストアにインストール\_プールです。</span><span class="sxs-lookup"><span data-stu-id="5ba61-150">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="5ba61-151">最初に、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-151">First, run the following command:</span></span>
        
        ``` 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="5ba61-152">フロント エンド サーバーのバックアップのいずれかで次のコマンドを実行\_プールを強制的に中央管理ストアの移動します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-152">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="5ba61-153">検証移動が完了します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-153">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="5ba61-154">ActiveMasterFQDN と ActiveFileTransferAgents の両方に、FQDN のバックアップを指していることを確認\_プールです。</span><span class="sxs-lookup"><span data-stu-id="5ba61-154">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="5ba61-155">次を入力して、すべてのフロント エンド サーバーのレプリカの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-155">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="5ba61-156">True の値をすべてのレプリカがあることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5ba61-156">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="5ba61-157">バックアップでは、フロント エンド サーバーの他のサーバーの全体管理サーバーのサービスをインストールする\_プールです。</span><span class="sxs-lookup"><span data-stu-id="5ba61-157">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="5ba61-158">これを行うには、すべてのフロント エンド サーバーで次のコマンドを実行して、ストアがこの手順で前に移動以外のサーバーの全体管理を強制するときに使用しました。</span><span class="sxs-lookup"><span data-stu-id="5ba61-158">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="5ba61-159">Pool1 から Pool2 へのユーザーは失敗し、Skype ビジネス サーバー管理シェル ウィンドウで次のコマンドレットを実行しています。</span><span class="sxs-lookup"><span data-stu-id="5ba61-159">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Skype for Business Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="5ba61-160">中央管理ストアの状態を確認する手順を次の手順の前の部分ではユニバーサルではないために、まだ確率中央管理ストアがまだ完全にフェイル オーバーされなかったために、このコマンドレットは失敗します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-160">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="5ba61-161">この例では、表示されるエラー メッセージに基づく中央管理ストアを修正してこのコマンドレットを再度実行してください。</span><span class="sxs-lookup"><span data-stu-id="5ba61-161">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="5ba61-162">次のエラー メッセージが表示された場合は、エッジでプール プールで障害が発生した前に次のホップとして別のプールを使用するには、このサイトを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ba61-162">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool.</span></span> <span data-ttu-id="5ba61-163">詳細については、このトピックの先頭に手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ba61-163">For details, see the procedures at the beginning of this topic.</span></span>
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a><span data-ttu-id="5ba61-164">プールのフェイル バック</span><span class="sxs-lookup"><span data-stu-id="5ba61-164">Fail back a pool</span></span>

<span data-ttu-id="5ba61-165">障害が発生したプールがオンラインに戻った後 (つまり、Pool1 この例では)、通常の動作状態を配置を復元するのには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-165">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="5ba61-166">フェイル バック ・ プロセスは、いくつかの分を完了することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5ba61-166">Note that the failback process takes several minute to complete.</span></span><span data-ttu-id="5ba61-167">リファレンスについては、最大 60 分まで 20,000 名のユーザーのプールを実行する予定です。</span><span class="sxs-lookup"><span data-stu-id="5ba61-167">  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="5ba61-168">Pool1 にホームが最初とされて失敗した上で Pool2 を次のコマンドレットを入力してユーザーのフェイル バックします。</span><span class="sxs-lookup"><span data-stu-id="5ba61-168">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="5ba61-169">その他の手順を実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5ba61-169">No other steps are necessary.</span></span> <span data-ttu-id="5ba61-170">中央管理サーバーをフェールオーバーする場合は、Pool2 のままにします。</span><span class="sxs-lookup"><span data-stu-id="5ba61-170">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a><span data-ttu-id="5ba61-171">Skype のビジネス サーバー連合を使用しているエッジ プールのフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="5ba61-171">Fail over the Edge pool used for Skype for Business Server federation</span></span> 

<span data-ttu-id="5ba61-172">構成されているビジネス サーバーのフェデレーション用に Skype があるエッジ プールで障害が発生した場合は、作業を別のエッジ プールのフェデレーションを使用するフェデレーションを変更しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="5ba61-172">If the Edge pool where you have Skype for Business Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

1.  <span data-ttu-id="5ba61-173">フロント エンド サーバーでは、トポロジ ビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="5ba61-173">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="5ba61-174">**エッジ プール**を展開し、エッジ サーバーまたはフェデレーション用に構成されているエッジ サーバー プールを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="5ba61-174">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="5ba61-175">**プロパティの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-175">Select **Edit properties**.</span></span>

2.  <span data-ttu-id="5ba61-176">[**全般**の**プロパティの編集** **(ポート 5061) エッジ プールのフェデレーションを有効にする**をオフにします。</span><span class="sxs-lookup"><span data-stu-id="5ba61-176">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="5ba61-177">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ba61-177">Click **OK**.</span></span>

3.  <span data-ttu-id="5ba61-178">**エッジ プール**を展開し、フェデレーションに使用するようになりました、エッジ サーバーまたはエッジ サーバー プールを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="5ba61-178">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that you now want to use for Federation.</span></span> <span data-ttu-id="5ba61-179">**プロパティの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-179">Select **Edit properties**.</span></span>

4.  <span data-ttu-id="5ba61-180">[**全般\*\*\*\*プロパティの編集**] で、**このエッジ プール (ポート 5061) のフェデレーションを有効にする**を選択します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-180">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="5ba61-181">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ba61-181">Click **OK**.</span></span>

5.  <span data-ttu-id="5ba61-182">[**アクション**] をクリックして、**トポロジ**を選択し、**発行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-182">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="5ba61-183">**公開トポロジ**でメッセージが表示されたら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ba61-183">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="5ba61-184">発行が完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ba61-184">When the Publish is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="5ba61-185">エッジ サーバーでは、ビジネスのサーバーの展開ウィザードの Skype を開きます。</span><span class="sxs-lookup"><span data-stu-id="5ba61-185">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="5ba61-186">**インストールまたはサーバーのビジネス システムの更新プログラムの Skype**をクリックし、[**セットアップ] または [サーバー コンポーネントのビジネスの Skype を削除**します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-186">Click **Install or Update Skype for Business Server System**, and then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="5ba61-187">**もう一度実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ba61-187">Click **Run Again**.</span></span>

7.  <span data-ttu-id="5ba61-188">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ba61-188">Click **Next**.</span></span> <span data-ttu-id="5ba61-189">サマリー画面で実行されたアクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5ba61-189">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="5ba61-190">展開が完了すると、利用可能なログ ファイルを表示する**ログの表示**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ba61-190">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="5ba61-191">展開を完了する**完了**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ba61-191">Click **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="5ba61-192">障害が発生したエッジのプールが含まれるサイトにまだ実行されているフロント エンド サーバーが含まれている場合は、Web 会議サービス、および A を更新する必要があります ◆ リモート エッジ プールを使用するのには、これらのフロント エンド プールの V 会議サービスがまだ実行中です。</span><span class="sxs-lookup"><span data-stu-id="5ba61-192">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to use an Edge pool in a remote site that is still running.</span></span> 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a><span data-ttu-id="5ba61-193">ビジネス サーバーの Skype の XMPP のフェデレーションに使用するエッジ プールのフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="5ba61-193">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span> 

<span data-ttu-id="5ba61-194">組織では、XMPP のフェデレーションに使用するプールとして指定されている 1 つのエッジ プールがあります。</span><span class="sxs-lookup"><span data-stu-id="5ba61-194">In your organization, there is one Edge pool designated as the pool to use for XMPP federation.</span></span> <span data-ttu-id="5ba61-195">このプールで障害が発生した場合は、フェイル オーバーは、XMPP のフェデレーション XMPP フェデレーションが再び動作することができます前に、別のエッジ プールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ba61-195">If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="5ba61-196">まず、エッジ プールをインストールし、XMPP フェデレーションを有効にする、エッジ プールの 1 つだけではなく、XMPP フェデレーションのすべての外部の DNS SRV レコードを設定することにより災害復旧プロセスを簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="5ba61-196">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="5ba61-197">これらの SRV レコードの各には、別の優先順位が設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="5ba61-197">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="5ba61-198">XMPP フェデレーションのすべてのトラフィックは、優先順位が高い SRV レコードを持つプールを通過します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-198">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> 

<span data-ttu-id="5ba61-199">次の手順では最初、XMPP フェデレーションをホストするプール、EdgePool1、EdgePool2 XMPP フェデレーションをホストするようになりましたが、プール。</span><span class="sxs-lookup"><span data-stu-id="5ba61-199">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="5ba61-200">XMPP のフェデレーションに使用するエッジ プールでエラーが発生するには</span><span class="sxs-lookup"><span data-stu-id="5ba61-200">To fail over the Edge pool used for XMPP federation</span></span>

1.  <span data-ttu-id="5ba61-201">展開 (現在下にある 1 つ) だけでなく、別のエッジ プールを持っていない場合は、そのプールを展開します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-201">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> 

2.  <span data-ttu-id="5ba61-202">XMPP フェデレーション (EdgePool2) をホストするようになりましたが、新しいエッジ プール内の各エッジ サーバーを導入すると、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-202">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="5ba61-203">EdgePool2 に XMPP フェデレーション ルートへの再接続には、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-203">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="5ba61-204">この例では、サイト 2 は XMPP フェデレーション ルートをホストするようになりましたが、エッジのプールが含まれているサイトで、EdgeServer2.contoso.com は、そのプール内のエッジ サーバーの FQDN です。</span><span class="sxs-lookup"><span data-stu-id="5ba61-204">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="5ba61-205">外部の DNS サーバーでは、EdgeServer2.contoso.com を指すように XMPP フェデレーション用の DNS A レコードを変更します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-205">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="5ba61-206">XMPP フェデレーション XMPP フェデレーションをホストするようになりましたが、エッジ プールに解決するための DNS SRV レコードがあるない場合、次の例のようにを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ba61-206">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="5ba61-207">この SRV レコードには、5269 のポートの値が必要です。</span><span class="sxs-lookup"><span data-stu-id="5ba61-207">This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="5ba61-208">XMPP フェデレーションをホストするようになりましたが、エッジ プールにポート 5269 を開いて外部を確認します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-208">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="5ba61-209">XMPP フェデレーションをホストするようになりましたが、エッジ プール内のすべてのエッジ サーバーでサービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-209">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a><span data-ttu-id="5ba61-210">ビジネス サーバーのフェデレーションまたは XMPP フェデレーションの Skype の使用されるエッジ プールのフェイル バック</span><span class="sxs-lookup"><span data-stu-id="5ba61-210">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span> 

<span data-ttu-id="5ba61-211">障害が発生したエッジの後フェデレーションをホストするために使用するプールをオンラインに復帰されましたが、ビジネス サーバーのフェデレーション ルートと XMPP フェデレーション ルートにもう一度この復元されたエッジ プールを使用する Skype でフェイル バックするにはこの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-211">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Skype for Business Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

1.  <span data-ttu-id="5ba61-212">現在は再び利用可能なエッジ プールのエッジ サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-212">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="5ba61-213">復元されたエッジ サーバーを使用するビジネス サーバーのフェデレーション ルートの Skype でフェイル バックする場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5ba61-213">If you want to fail back the Skype for Business Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="5ba61-214">フロント エンド サーバーでは、トポロジ ビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="5ba61-214">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="5ba61-215">**エッジ プール**を展開し、エッジ サーバーまたはフェデレーション用に構成されているエッジ サーバー プールを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="5ba61-215">Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="5ba61-216">**プロパティの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-216">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="5ba61-217">[**全般**の**プロパティの編集** **(ポート 5061) エッジ プールのフェデレーションを有効にする**をオフにします。</span><span class="sxs-lookup"><span data-stu-id="5ba61-217">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="5ba61-218">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ba61-218">Click **OK**.</span></span>
    
      - <span data-ttu-id="5ba61-219">**エッジ プール**を展開し、フェデレーションに使用する場合、元のエッジ サーバーまたはエッジ サーバー プールを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="5ba61-219">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation.</span></span> <span data-ttu-id="5ba61-220">**プロパティの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-220">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="5ba61-221">[**全般\*\*\*\*プロパティの編集**] で、**このエッジ プール (ポート 5061) のフェデレーションを有効にする**を選択します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-221">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="5ba61-222">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ba61-222">Click **OK**.</span></span>
    
      - <span data-ttu-id="5ba61-223">[**アクション**] をクリックして、**トポロジ**を選択し、**発行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-223">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="5ba61-224">**公開トポロジ**でメッセージが表示されたら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ba61-224">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="5ba61-225">発行が完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ba61-225">When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="5ba61-226">エッジ サーバーでは、ビジネスのサーバーの展開ウィザードの Skype を開きます。</span><span class="sxs-lookup"><span data-stu-id="5ba61-226">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="5ba61-227">**インストールまたはサーバーのビジネス システムの更新プログラムの Skype**をクリックし、[**セットアップ] または [サーバー コンポーネントのビジネスの Skype を削除**します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-227">Click **Install or Update Skype for Business Server System**, then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="5ba61-228">**もう一度実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ba61-228">Click **Run Again**.</span></span>
    
      - <span data-ttu-id="5ba61-229">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ba61-229">Click **Next**.</span></span> <span data-ttu-id="5ba61-230">サマリー画面で実行されたアクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5ba61-230">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="5ba61-231">展開が完了すると、利用可能なログ ファイルを表示する**ログの表示**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ba61-231">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="5ba61-232">展開を完了する**完了**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ba61-232">Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="5ba61-233">復元されたエッジ サーバーを使用する XMPP フェデレーション ルートをフェールバックするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5ba61-233">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="5ba61-234">XMPP フェデレーション ルート (この例では、EdgeServer1) では、XMPP フェデレーションをホストするようになりましたが、エッジのプールへの再接続には、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-234">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="5ba61-235">この例では、Site1 XMPP フェデレーション ルートをホストするようになりましたが、エッジのプールが含まれるサイトは、EdgeServer1.contoso.com では、プール内のエッジ サーバーの FQDN です。</span><span class="sxs-lookup"><span data-stu-id="5ba61-235">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="5ba61-236">XMPP フェデレーション XMPP フェデレーションをホストするようになりましたが、エッジ プールに解決するための DNS SRV レコードがあるない場合、次の例のようにを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ba61-236">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="5ba61-237">この SRV レコードには、5269 のポートの値が必要です。</span><span class="sxs-lookup"><span data-stu-id="5ba61-237">This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="5ba61-238">外部の DNS サーバーでは、EdgeServer2.contoso.com を指すように XMPP フェデレーション用の DNS A レコードを変更します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-238">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="5ba61-239">XMPP フェデレーションをホストするようになりましたが、エッジ プールにポート 5269 を開いて外部を確認します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-239">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="5ba61-240">フロント エンド プールに残っている障害が発生し、復元されたエッジ プールを含むサイトで実行中、する場合は、Web 会議サービス、および A を更新する必要がありますこれらのフロント エンドでの V 会議サービス プール再使用する、ローカル サイトにあるエッジ プールとします。</span><span class="sxs-lookup"><span data-stu-id="5ba61-240">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span>

5.  <span data-ttu-id="5ba61-241">障害が発生したエッジのプールと同じサイトでフロント エンド プールも失敗した場合、使えるようになりました呼び出し – CsPoolFailback フロント エンド プールをフェールバックするためです。</span><span class="sxs-lookup"><span data-stu-id="5ba61-241">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="5ba61-242">フロント エンド プールに関連付けられたエッジ プールを変更します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-242">Change the Edge pool associated with a Front End pool</span></span>

<span data-ttu-id="5ba61-243">エッジ プールは、障害が発生した場合は、同じサイトのフロント エンド プールがまだ実行中は、障害が発生したエッジ プールが復元されるまで、別のサイトで、エッジのプールを使用するフロント エンド プールを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ba61-243">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

1.  <span data-ttu-id="5ba61-244">トポロジ ビルダーでは、変更する必要がありますフロント エンド プールの名前に移動します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-244">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="5ba61-245">プールを右クリックし、 **[プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ba61-245">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="5ba61-246">**関連付け**] セクションの [**エッジ プールを (メディア コンポーネント) の関連付け**] の下で、リスト ボックスでは、このフロント エンド プールに関連付けるエッジ プールを選択するのにはドロップを使用します。</span><span class="sxs-lookup"><span data-stu-id="5ba61-246">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="5ba61-247">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ba61-247">Click **OK**.</span></span>
