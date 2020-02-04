---
title: 'Lync Server 2013: プールのフェールオーバー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over a pool
ms:assetid: 10b13732-bc80-4cb2-a71c-56b1d6cb5bbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204678(v=OCS.15)
ms:contentKeyID: 48183432
ms.date: 10/10/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea66ae4a224d78e40a9fdb9de867d4738a5e3714
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-pool-in-lync-server-2013"></a><span data-ttu-id="c68d3-102">Lync Server 2013 でのプールのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="c68d3-102">Failing over a pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c68d3-103">_**最終更新日:** 2014-10-10_</span><span class="sxs-lookup"><span data-stu-id="c68d3-103">_**Topic Last Modified:** 2014-10-10_</span></span>

<span data-ttu-id="c68d3-104">1つのフロントエンドプールで障害が発生し、フェールオーバーを行う必要がある場合は、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="c68d3-104">If a single Front End pool has failed and needs to be failed over, use the following procedure.</span></span> <span data-ttu-id="c68d3-105">この手順では、Datacenter1 に Pool1 が含まれており、Pool1 は失敗しています。</span><span class="sxs-lookup"><span data-stu-id="c68d3-105">In this procedure, Datacenter1 contains Pool1, and Pool1 has failed.</span></span> <span data-ttu-id="c68d3-106">Datacenter2 にある Pool2 にフェイルオーバーしています。</span><span class="sxs-lookup"><span data-stu-id="c68d3-106">You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="c68d3-107">プールフェールオーバーのほとんどの作業には、必要に応じて、中央管理ストアのフェールオーバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c68d3-107">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="c68d3-108">プールのユーザーがフェールオーバーされた場合は、中央管理ストアが機能している必要があるため、これは重要です。</span><span class="sxs-lookup"><span data-stu-id="c68d3-108">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="c68d3-109">さらに、フロントエンドプールに障害が発生しても、そのサイトの Edge プールがまだ実行されている場合は、Edge プールが、失敗したプールを次のホッププールとして使用するかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c68d3-109">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool.</span></span> <span data-ttu-id="c68d3-110">問題が発生した場合は、失敗したフロントエンドプールを使用するようにエッジプールを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c68d3-110">If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool.</span></span> <span data-ttu-id="c68d3-111">次ホップの設定を変更する方法は、エッジプールと同じサイトのプールを使用するか、または別のサイトを使うかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="c68d3-111">How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="c68d3-112">**エッジプールで、同じサイトの次ホッププールを使用するように設定するには**</span><span class="sxs-lookup"><span data-stu-id="c68d3-112">**To Set an Edge Pool to Use a Next Hop Pool at the Same Site**</span></span>

1.  <span data-ttu-id="c68d3-113">トポロジビルダーを開き、変更する必要があるエッジプールを右クリックして、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c68d3-113">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="c68d3-114">[**次ホップ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c68d3-114">Click **Next Hop**.</span></span> <span data-ttu-id="c68d3-115">[ **Next ホッププール:** ] ボックスの一覧で、次ホッププールとして機能するプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="c68d3-115">From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="c68d3-116">[ **OK**] をクリックして、変更を公開します。</span><span class="sxs-lookup"><span data-stu-id="c68d3-116">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="c68d3-117">**別のサイトで次ホッププールを使用するようにエッジプールを設定するには**</span><span class="sxs-lookup"><span data-stu-id="c68d3-117">**To Set an Edge Pool to Use a Next Hop Pool at a Different Site**</span></span>

1.  <span data-ttu-id="c68d3-118">Lync Server 管理シェルウィンドウを開いて、次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="c68d3-118">Open a Lync Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="c68d3-119">**障害が発生したプールをフェイルオーバーするには**</span><span class="sxs-lookup"><span data-stu-id="c68d3-119">**To Fail Over a Pool in a Disaster**</span></span>

1.  <span data-ttu-id="c68d3-120">Pool2 のフロントエンドサーバーに次のコマンドレットを入力して、中央管理サーバーのホストとなるプールを見つけます。</span><span class="sxs-lookup"><span data-stu-id="c68d3-120">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="c68d3-121">このコマンドレットの結果は、現在中央管理サーバーをホストしているプールを示します。</span><span class="sxs-lookup"><span data-stu-id="c68d3-121">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="c68d3-122">この手順の残りの部分では、このプールを CMS\_プールと呼びます。</span><span class="sxs-lookup"><span data-stu-id="c68d3-122">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="c68d3-123">トポロジビルダーを使用して、CMS\_プールで実行されている Lync Server のバージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="c68d3-123">Use Topology Builder to find the version of Lync Server running on the CMS\_Pool.</span></span> <span data-ttu-id="c68d3-124">Lync Server 2013 を実行している場合は、次のコマンドレットを使用して、Pool 1 のバックアッププールを検索します。</span><span class="sxs-lookup"><span data-stu-id="c68d3-124">If it is running Lync Server 2013, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="c68d3-125">バックアップ\_プールをバックアッププールにします。</span><span class="sxs-lookup"><span data-stu-id="c68d3-125">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="c68d3-126">次のコマンドレットを使用して、サーバーの全体管理ストアの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="c68d3-126">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="c68d3-127">このコマンドレットでは、ActiveMasterFQDN と ActiveFileTransferAgents の両方が CMS\_プールの FQDN を指していることを示しています。</span><span class="sxs-lookup"><span data-stu-id="c68d3-127">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="c68d3-128">空の場合は、サーバーの全体管理サーバーを利用できないため、フェールオーバーを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="c68d3-128">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="c68d3-129">中央管理ストアを使用できない場合、または Pool1 で中央管理ストアが実行されている場合 (つまり、失敗したプール)、プールをフェールオーバーする前に、中央管理サーバーをフェールオーバーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c68d3-129">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="c68d3-130">Lync Server 2013 を実行しているプールでホストされていた中央管理サーバーをフェールオーバーする必要がある場合は、この手順の手順5のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c68d3-130">If you need to fail over the Central Management Server that was hosted on a pool running Lync Server 2013, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="c68d3-131">Lync Server 2010 を実行しているプールでホストされていた中央管理サーバーをフェールオーバーする必要がある場合は、この手順の手順6でコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c68d3-131">If you need to fail over the Central Management Server that was hosted on a pool running Lync Server 2010, use the cmdlet in step 6 of this procedure.</span></span> <span data-ttu-id="c68d3-132">サーバーの全体管理サーバーにフェールオーバーする必要がない場合は、手順7に進んでください。</span><span class="sxs-lookup"><span data-stu-id="c68d3-132">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="c68d3-133">Lync Server 2013 を実行しているプールの中央管理ストアをフェールオーバーするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c68d3-133">To fail over the Central Management store on a pool running Lync Server 2013, do the following:</span></span>
    
      - <span data-ttu-id="c68d3-134">まず、次のように入力して\_、バックアッププールのどのバックエンドサーバーで中央管理ストアのプリンシパルインスタンスを実行するかを確認します。</span><span class="sxs-lookup"><span data-stu-id="c68d3-134">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="c68d3-135">バックアップ\_プールのプライマリバックエンドサーバーがプリンシパルである場合は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="c68d3-135">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="c68d3-136">バックアップ\_プールのミラーバックエンドサーバーがプリンシパルである場合は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="c68d3-136">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="c68d3-137">サーバーの全体のフェールオーバーが完了していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c68d3-137">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="c68d3-138">次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="c68d3-138">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="c68d3-139">ActiveMasterFQDN と ActiveFileTransferAgents の両方がバックアップ\_プールの FQDN を指していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c68d3-139">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="c68d3-140">最後に、次のように入力して、すべてのフロントエンドサーバーのレプリカの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="c68d3-140">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="c68d3-141">すべてのレプリカの値が True であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c68d3-141">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="c68d3-142">この手順の手順7に進みます。</span><span class="sxs-lookup"><span data-stu-id="c68d3-142">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="c68d3-143">バックアップ\_プールのバックエンドサーバーに中央管理ストアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="c68d3-143">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="c68d3-144">最初に、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c68d3-144">First, run the following command:</span></span>
        
        ```PowerShell 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="c68d3-145">バックアップ\_プールのいずれかのフロントエンドサーバーで次のコマンドを実行して、中央管理ストアの移動を強制します。</span><span class="sxs-lookup"><span data-stu-id="c68d3-145">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="c68d3-146">移動が完了したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="c68d3-146">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="c68d3-147">ActiveMasterFQDN と ActiveFileTransferAgents の両方がバックアップ\_プールの FQDN を指していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c68d3-147">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="c68d3-148">次のように入力して、すべてのフロントエンドサーバーのレプリカの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="c68d3-148">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="c68d3-149">すべてのレプリカの値が True であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c68d3-149">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="c68d3-150">中央管理サーバーサービスを、バックアップ\_プールのフロントエンドサーバーの残りの部分にインストールします。</span><span class="sxs-lookup"><span data-stu-id="c68d3-150">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="c68d3-151">この操作を行うには、この手順の最初に中央管理ストアを強制するときに使用したものを除き、すべてのフロントエンドサーバーで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c68d3-151">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="c68d3-152">Lync Server 管理シェルウィンドウで次のコマンドレットを実行して、Pool1 から Pool2 にユーザーをフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="c68d3-152">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Lync Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="c68d3-153">この手順の前の部分で実行した手順では、全体管理ストアの状態を確認する必要があるため、中央管理ストアはまだ完全にフェールオーバーしていないため、このコマンドレットは失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c68d3-153">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="c68d3-154">この場合は、表示されるエラーメッセージに基づいて、中央管理ストアを修正し、このコマンドレットをもう一度実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c68d3-154">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="c68d3-155">次のエラーメッセージが表示された場合は、プールをフェールオーバーする前に、このサイトの Edge プールを別のホップとして使用するように変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c68d3-155">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool.</span></span> <span data-ttu-id="c68d3-156">詳細については、このトピックの最初の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c68d3-156">For details, see the procedures at the beginning of this topic.</span></span>
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.

</div>

<span> </span>

</div>

</div>

</div>

