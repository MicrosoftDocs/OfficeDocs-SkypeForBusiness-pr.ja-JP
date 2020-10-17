---
title: 'Lync Server 2013: プールのフェールオーバー'
description: 'Lync Server 2013: プールのフェールオーバー。'
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
ms.openlocfilehash: 819137c1277c5058f4e5d36ef5dbe71e672e8641
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554983"
---
# <a name="failing-over-a-pool-in-lync-server-2013"></a><span data-ttu-id="2d19b-103">Lync Server 2013 でのプールのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="2d19b-103">Failing over a pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d19b-104">_**トピックの最終更新日:** 2014-10-10_</span><span class="sxs-lookup"><span data-stu-id="2d19b-104">_**Topic Last Modified:** 2014-10-10_</span></span>

<span data-ttu-id="2d19b-p101">1 つのフロントエンド プールで障害が発生し、フェールオーバーが必要な場合は、次の手順を使用します。この手順では、Datacenter1 に Pool1 があり、Pool1 で障害が発生した状況を想定しています。フェールオーバー先は Datacenter2 の Pool2 です。</span><span class="sxs-lookup"><span data-stu-id="2d19b-p101">If a single Front End pool has failed and needs to be failed over, use the following procedure. In this procedure, Datacenter1 contains Pool1, and Pool1 has failed. You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="2d19b-108">プールフェールオーバーの作業のほとんどは、必要な場合に中央管理ストアをフェールオーバーすることになります。</span><span class="sxs-lookup"><span data-stu-id="2d19b-108">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="2d19b-109">これは、プールのユーザーがフェールオーバーしたときに中央管理ストアが機能する必要があるため、重要です。</span><span class="sxs-lookup"><span data-stu-id="2d19b-109">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="2d19b-p103">また、フロントエンド プールで障害が発生しているが、そのサイトのエッジ プールはまだ実行されている場合は、障害が発生しているプールをエッジ プールで次ホップ プールとして使用するかどうかを把握する必要があります。次ホップ プールとして使用する場合は、障害が発生しているフロントエンド プールをフェールオーバーする前に、エッジ プールを変更して別のフロントエンド プールを使用する必要があります。次ホップの設定を変更する方法は、エッジでエッジ プールと同じサイトのプールを使用するか、別のサイトのプールを使用するかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="2d19b-p103">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool. If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool. How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="2d19b-113">**同じサイトの次ホップ プールを使用するようにエッジ プールを設定するには**</span><span class="sxs-lookup"><span data-stu-id="2d19b-113">**To Set an Edge Pool to Use a Next Hop Pool at the Same Site**</span></span>

1.  <span data-ttu-id="2d19b-114">トポロジビルダーを開き、変更する必要があるエッジプールを右クリックして、[ **プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d19b-114">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="2d19b-p104">[**次ホップ**] をクリックします。[**次ホップ プール**] の一覧で、次ホップ プールとして使用するプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="2d19b-p104">Click **Next Hop**. From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="2d19b-117">[**OK**] をクリックし、変更を公開します。</span><span class="sxs-lookup"><span data-stu-id="2d19b-117">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="2d19b-118">**別のサイトの次ホップ プールを使用するようにエッジ プールを設定するには**</span><span class="sxs-lookup"><span data-stu-id="2d19b-118">**To Set an Edge Pool to Use a Next Hop Pool at a Different Site**</span></span>

1.  <span data-ttu-id="2d19b-119">[Lync Server 管理シェル] ウィンドウを開き、次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="2d19b-119">Open a Lync Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="2d19b-120">**障害が発生したプールをフェールオーバーするには**</span><span class="sxs-lookup"><span data-stu-id="2d19b-120">**To Fail Over a Pool in a Disaster**</span></span>

1.  <span data-ttu-id="2d19b-121">Pool2 のフロントエンドサーバーに次のコマンドレットを入力することによって、中央管理サーバーのホストであるプールを検索します。</span><span class="sxs-lookup"><span data-stu-id="2d19b-121">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="2d19b-122">このコマンドレットの結果は、現在中央管理サーバーをホストしているプールを示しています。</span><span class="sxs-lookup"><span data-stu-id="2d19b-122">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="2d19b-123">この手順の残りの部分では、このプールを CMS \_ プールと呼びます。</span><span class="sxs-lookup"><span data-stu-id="2d19b-123">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="2d19b-124">トポロジビルダーを使用して、CMS プールで実行されている Lync Server のバージョンを検索し \_ ます。</span><span class="sxs-lookup"><span data-stu-id="2d19b-124">Use Topology Builder to find the version of Lync Server running on the CMS\_Pool.</span></span> <span data-ttu-id="2d19b-125">Lync Server 2013 を実行している場合は、次のコマンドレットを使用して、プール1のバックアッププールを検索します。</span><span class="sxs-lookup"><span data-stu-id="2d19b-125">If it is running Lync Server 2013, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="2d19b-126">バックアップ \_ プールをバックアッププールとして使用します。</span><span class="sxs-lookup"><span data-stu-id="2d19b-126">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="2d19b-127">次のコマンドレットを使用して、中央管理ストアの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="2d19b-127">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="2d19b-128">このコマンドレットでは、ActiveMasterFQDN と ActiveFileTransferAgents の両方が CMS プールの FQDN を指していることを示して \_ います。</span><span class="sxs-lookup"><span data-stu-id="2d19b-128">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="2d19b-129">これらが空の場合は、中央管理サーバーを使用できないので、フェールオーバーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d19b-129">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="2d19b-130">中央管理ストアが使用できない場合、または中央管理ストアが Pool1 (つまり、障害が発生したプール) 上で実行されている場合は、プールをフェールオーバーする前に中央管理サーバーをフェールオーバーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d19b-130">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="2d19b-131">Lync Server 2013 を実行しているプールでホストされていた中央管理サーバーをフェールオーバーする必要がある場合は、この手順の手順5でコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="2d19b-131">If you need to fail over the Central Management Server that was hosted on a pool running Lync Server 2013, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="2d19b-132">Lync Server 2010 を実行しているプールでホストされていた中央管理サーバーをフェールオーバーする必要がある場合は、この手順の手順6でコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="2d19b-132">If you need to fail over the Central Management Server that was hosted on a pool running Lync Server 2010, use the cmdlet in step 6 of this procedure.</span></span> <span data-ttu-id="2d19b-133">中央管理サーバーをフェールオーバーする必要がない場合は、この手順の手順7に進みます。</span><span class="sxs-lookup"><span data-stu-id="2d19b-133">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="2d19b-134">Lync Server 2013 を実行しているプールの中央管理ストアをフェールオーバーするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2d19b-134">To fail over the Central Management store on a pool running Lync Server 2013, do the following:</span></span>
    
      - <span data-ttu-id="2d19b-135">最初に、次のように入力して、バックアッププールのどのバックエンドサーバーが \_ 中央管理ストアのプリンシパルインスタンスを実行するかを確認します。</span><span class="sxs-lookup"><span data-stu-id="2d19b-135">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="2d19b-136">バックアッププールのプライマリバックエンドサーバー \_ がプリンシパルの場合は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="2d19b-136">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="2d19b-137">バックアッププールのミラーバックエンドサーバー \_ がプリンシパルの場合は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="2d19b-137">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="2d19b-138">中央管理サーバーのフェールオーバーが完了していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2d19b-138">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="2d19b-139">次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="2d19b-139">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="2d19b-140">ActiveMasterFQDN と ActiveFileTransferAgents の両方がバックアッププールの FQDN を指していることを確認して \_ ください。</span><span class="sxs-lookup"><span data-stu-id="2d19b-140">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="2d19b-141">最後に、次のように入力して、すべてのフロントエンドサーバーのレプリカの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="2d19b-141">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="2d19b-142">すべてのレプリカの値が True であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2d19b-142">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="2d19b-143">手順 7. に進みます。</span><span class="sxs-lookup"><span data-stu-id="2d19b-143">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="2d19b-144">中央管理ストアをバックアッププールのバックエンドサーバーにインストールし \_ ます。</span><span class="sxs-lookup"><span data-stu-id="2d19b-144">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="2d19b-145">最初に、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2d19b-145">First, run the following command:</span></span>
        
        ```PowerShell 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="2d19b-146">バックアッププールのフロントエンドサーバーの1つで次のコマンドを実行して、 \_ 中央管理ストアの移動を強制します。</span><span class="sxs-lookup"><span data-stu-id="2d19b-146">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="2d19b-147">移動が完了したことを検証します。</span><span class="sxs-lookup"><span data-stu-id="2d19b-147">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="2d19b-148">ActiveMasterFQDN と ActiveFileTransferAgents の両方がバックアッププールの FQDN を指していることを確認して \_ ください。</span><span class="sxs-lookup"><span data-stu-id="2d19b-148">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="2d19b-149">すべてのフロントエンド サーバーのレプリカの状態を確認するために、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="2d19b-149">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="2d19b-150">すべてのレプリカの値が True であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2d19b-150">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="2d19b-151">中央管理サーバーサービスをバックアッププール内の残りのフロントエンドサーバーにインストールし \_ ます。</span><span class="sxs-lookup"><span data-stu-id="2d19b-151">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="2d19b-152">これを行うには、すべてのフロントエンドサーバー上で次のコマンドを実行します。ただし、この手順の最初に中央管理ストアを強制的に移動するときに使用したものを除きます。</span><span class="sxs-lookup"><span data-stu-id="2d19b-152">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="2d19b-153">Lync Server 管理シェルウィンドウで次のコマンドレットを実行して、Pool1 から Pool2 にユーザーをフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="2d19b-153">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Lync Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="2d19b-154">中央管理ストアの状態を確認するために、この手順の前の部分で説明した手順がユニバーサルではないため、中央管理ストアがまだ完全にフェールオーバーされていないため、このコマンドレットが失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2d19b-154">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="2d19b-155">この場合は、表示されるエラーメッセージに基づいて中央管理ストアを修正してから、このコマンドレットを再度実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d19b-155">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="2d19b-p112">次のエラー メッセージが表示される場合は、プールをフェールオーバーする前に、このサイトのエッジ プールを変更して別のプールを次ホップとして使用する必要があります。詳細については、このトピックの冒頭に掲載される手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d19b-p112">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool. For details, see the procedures at the beginning of this topic.</span></span>
    
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

