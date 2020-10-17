---
title: Lync Server 2010 Central Management サーバーを Lync Server 2013 に移動する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move the Lync Server 2010 Central Management Server to Lync Server 2013
ms:assetid: 30cc98f2-1916-4dbe-99d0-8df5368ed3ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688013(v=OCS.15)
ms:contentKeyID: 49733602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53251e03c55d6d61ae360d7b0739c07ac44dccdc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500134"
---
# <a name="move-the-lync-server-2010-central-management-server-to-lync-server-2013"></a><span data-ttu-id="61be9-102">Lync Server 2010 Central Management サーバーを Lync Server 2013 に移動する</span><span class="sxs-lookup"><span data-stu-id="61be9-102">Move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61be9-103">_**トピックの最終更新日:** 2013-11-25_</span><span class="sxs-lookup"><span data-stu-id="61be9-103">_**Topic Last Modified:** 2013-11-25_</span></span>

<span data-ttu-id="61be9-104">Lync server 2010 から Lync Server 2013 に移行した後、lync server 2010 Central Management サーバーを Lync Server の2013フロントエンドサーバーまたはプールに移動してから、従来の Lync 2010 Server のサーバーを使用しているサーバーを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61be9-104">After migrating from Lync Server 2010 to Lync Server 2013, you need to move the Lync Server 2010 Central Management Server to the Lync Server 2013 Front End Server or pool, before you can remove the legacy Lync Server 2010 server.</span></span>

<span data-ttu-id="61be9-105">中央管理サーバーは、中央管理サーバーを含むフロントエンドサーバーによって、データベースの読み取り/書き込みコピーが保持されている単一のマスター/マルチレプリカシステムです。</span><span class="sxs-lookup"><span data-stu-id="61be9-105">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="61be9-106">トポロジ内の各コンピューター (中央管理サーバーを含むフロントエンドサーバーを含む) には、セットアップと展開時にコンピューターにインストールされた SQL Server データベース内の中央管理ストアデータの読み取り専用コピーがあります (既定では RTCLOCAL という名前が付いています)。</span><span class="sxs-lookup"><span data-stu-id="61be9-106">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="61be9-107">ローカルデータベースは、すべてのコンピューターでサービスとして実行される Lync Server Replica Replicator エージェントを経由して、レプリカの更新を受信します。</span><span class="sxs-lookup"><span data-stu-id="61be9-107">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="61be9-108">中央管理サーバーとローカルレプリカの実際のデータベースの名前は XDS で、このファイルは xds ファイルと xds ファイルで構成されています。</span><span class="sxs-lookup"><span data-stu-id="61be9-108">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="61be9-109">Master データベースの場所は、Active Directory ドメインサービスのサービスコントロールポイント (SCP) によって参照されます。</span><span class="sxs-lookup"><span data-stu-id="61be9-109">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="61be9-110">中央管理サーバーを使用して Lync Server を管理および構成するすべてのツール SCP を使用して、中央管理ストアを特定します。</span><span class="sxs-lookup"><span data-stu-id="61be9-110">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>

<span data-ttu-id="61be9-111">中央管理サーバーを正常に移動したら、元のフロントエンドサーバーから中央管理サーバーデータベースを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61be9-111">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="61be9-112">中央管理サーバーデータベースの削除の詳細については、「 [フロントエンドプールの SQL Server データベースを削除](remove-the-sql-server-database-for-a-front-end-pool.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61be9-112">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>

<span data-ttu-id="61be9-113">Lync server 管理シェルで **move-csmanagementserver** コマンドレットを使用して、lync SERVER 2010 sql server データベースから lync SERVER 2013 sql server データベースにデータベースを移動した後、lync Server 2013 中央管理サーバーの場所を指すように SCP を更新します。</span><span class="sxs-lookup"><span data-stu-id="61be9-113">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Lync Server Management Shell to move the database from the Lync Server 2010 SQL Server database to the Lync Server 2013 SQL Server database, and then update the SCP to point to the Lync Server 2013 Central Management Server location.</span></span>

<div>

## <a name="preparing-lync-server-2013front-end-servers-before-moving-the-central-management-server"></a><span data-ttu-id="61be9-114">中央管理サーバーを移動する前に Lync Server 2013 フロントエンドサーバーを準備する</span><span class="sxs-lookup"><span data-stu-id="61be9-114">Preparing Lync Server 2013 Front End Servers before moving the Central Management Server</span></span>

<span data-ttu-id="61be9-115">Lync Server 2010 Central Management サーバーを移動する前に、このセクションの手順を使用して、Lync Server 2013 フロントエンドサーバーを準備します。</span><span class="sxs-lookup"><span data-stu-id="61be9-115">Use the procedures in this section to prepare the Lync Server 2013 Front End Servers before you move the Lync Server 2010 Central Management Server.</span></span>

<div>

## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="61be9-116">Enterprise Edition フロントエンドプールを準備するには</span><span class="sxs-lookup"><span data-stu-id="61be9-116">To prepare an Enterprise Edition Front End pool</span></span>

1.  <span data-ttu-id="61be9-117">中央管理サーバーを再配置する Lync Server 2013 Enterprise Edition フロントエンドプールで、 **RTCUniversalServerAdmins** グループのメンバーとして Lync Server 管理シェルがインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="61be9-117">On the Lync Server 2013 Enterprise Edition Front End pool where you want to relocate the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="61be9-118">また、中央管理ストアをインストールするデータベースに対して、SQL Server データベース sysadmin のユーザー権限とアクセス許可も持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="61be9-118">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span>

2.  <span data-ttu-id="61be9-119">Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="61be9-119">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="61be9-120">Lync server 2013 の SQL Server データベースに新しい中央管理ストアを作成するには、Lync Server 管理シェルで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="61be9-120">To create the new Central Management store in the Lync Server 2013 SQL Server database, in the Lync Server Management Shell, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>

4.  <span data-ttu-id="61be9-121">[**Lync Server フロントエンド**] サービスのステータスが [**開始**] であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="61be9-121">Confirm that the status of the **Lync Server Front-End** service is **Started**.</span></span>

</div>

<div>

## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="61be9-122">Standard Edition フロントエンドサーバーを準備するには</span><span class="sxs-lookup"><span data-stu-id="61be9-122">To prepare a Standard Edition Front End Server</span></span>

1.  <span data-ttu-id="61be9-123">中央管理サーバーを再配置する Lync Server 2013 Standard Edition フロントエンドサーバーで、 **RTCUniversalServerAdmins** グループのメンバーとして Lync Server 管理シェルがインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="61be9-123">On the Lync Server 2013 Standard Edition Front End Server where you want to relocate the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span>

2.  <span data-ttu-id="61be9-124">[Lync Server 展開ウィザード] を開きます。</span><span class="sxs-lookup"><span data-stu-id="61be9-124">Open the Lync Server Deployment Wizard.</span></span>

3.  <span data-ttu-id="61be9-125">Lync Server 展開ウィザードで、[ **最初の Standard Edition サーバーの準備**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="61be9-125">In the Lync Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>

4.  <span data-ttu-id="61be9-126">[ **コマンドの実行** ] ページで、中央管理サーバーとして SQL Server Express がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="61be9-126">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="61be9-127">必要なファイアウォール規則が作成されます。</span><span class="sxs-lookup"><span data-stu-id="61be9-127">Necessary firewall rules are created.</span></span> <span data-ttu-id="61be9-128">データベースと必要なソフトウェアのインストールが完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="61be9-128">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="61be9-129">最初のインストールには、コマンド出力の概要画面に表示される更新がないと、しばらく時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="61be9-129">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="61be9-130">これは、SQL Server Express がインストールされているためです。</span><span class="sxs-lookup"><span data-stu-id="61be9-130">This is due to the installation of the SQL Server Express.</span></span> <span data-ttu-id="61be9-131">データベースのインストールを監視する必要がある場合は、タスクマネージャーを使用してセットアップを監視します。</span><span class="sxs-lookup"><span data-stu-id="61be9-131">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span>

    
    </div>

5.  <span data-ttu-id="61be9-132">Lync server 2013 Standard Edition フロントエンドサーバー上に新しい中央管理ストアを作成するには、Lync Server 管理シェルで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="61be9-132">To create the new Central Management store on the Lync Server 2013 Standard Edition Front End Server, in the Lync Server Management Shell, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>

6.  <span data-ttu-id="61be9-133">[**Lync Server フロントエンド**] サービスのステータスが [**開始**] であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="61be9-133">Confirm that the status of the **Lync Server Front-End** service is **Started**.</span></span>

</div>

</div>

<div>

## <a name="to-move-the-lync-server-2010central-management-server-to-lync-server-2013"></a><span data-ttu-id="61be9-134">Lync Server 2010 Central Management サーバーを Lync Server 2013 に移動するには</span><span class="sxs-lookup"><span data-stu-id="61be9-134">To move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>

1.  <span data-ttu-id="61be9-135">中央管理サーバーとなる Lync Server 2013 サーバー上で、Lync Server 管理シェルがインストールされているコンピューターに **RTCUniversalServerAdmins** グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="61be9-135">On the Lync Server 2013 server that will be the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="61be9-136">また、SQL Server データベース管理者のユーザー権限とアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="61be9-136">You must also have the SQL Server database administrator user rights and permissions.</span></span>

2.  <span data-ttu-id="61be9-137">Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="61be9-137">Open Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="61be9-138">Lync Server 管理シェルで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="61be9-138">In the Lync Server Management Shell, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="61be9-139"><CODE>Enable-CsTopology</CODE>成功しない場合は、続行する前に、コマンドの完了を妨げている問題を解決してください。</span><span class="sxs-lookup"><span data-stu-id="61be9-139">If <CODE>Enable-CsTopology</CODE> is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="61be9-140"><STRONG>Enable-CsTopology テクノロジ</STRONG>が成功しなかった場合、移動は失敗し、中央管理ストアがない状態で、トポロジがそのまま残る場合があります。</span><span class="sxs-lookup"><span data-stu-id="61be9-140">If <STRONG>Enable-CsTopology</STRONG> is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span>

    
    </div>

4.  <span data-ttu-id="61be9-141">Lync server 2013 のフロントエンドサーバーまたはフロントエンドプールの場合は、Lync Server 管理シェルで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="61be9-141">On the Lync Server 2013 Front End Server or Front End pool, in the Lync Server Management Shell, type:</span></span>
    
        Move-CsManagementServer

5.  <span data-ttu-id="61be9-142">Lync Server 管理シェルには、サーバー、ファイルストア、データベースストア、および現在の状態のサービス接続ポイントと提案済みの状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="61be9-142">Lync Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="61be9-143">この情報を注意深く読み、移動元と移動先が意図したものであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="61be9-143">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="61be9-144">続行するには「**Y**」を入力し、移動を中止するには「**N**」を入力します。</span><span class="sxs-lookup"><span data-stu-id="61be9-144">Type **Y** to continue, or **N** to stop the move.</span></span>

6.  <span data-ttu-id="61be9-145">**Move-CsManagementServer** コマンドで表示される警告またはエラーを確認して解決します。</span><span class="sxs-lookup"><span data-stu-id="61be9-145">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span>

7.  <span data-ttu-id="61be9-146">Lync Server 2013 サーバーで、[Lync Server 展開ウィザード] を開きます。</span><span class="sxs-lookup"><span data-stu-id="61be9-146">On the Lync Server 2013 server, open the Lync Server Deployment Wizard.</span></span>

8.  <span data-ttu-id="61be9-147">Lync Server 展開ウィザードで、[ **Lync Server システムのインストールまたは更新**] をクリックし、[ **ステップ 2: lync Server コンポーネントのセットアップまたは削除**] をクリックし、[ **次へ**] をクリックして概要を確認し、[ **完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="61be9-147">In Lync Server Deployment Wizard, click **Install or Update Lync Server System**, click **Step 2: Setup or Remove Lync Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span>

9.  <span data-ttu-id="61be9-148">Lync Server 2010 サーバーで、[Lync Server 展開ウィザード] を開きます。</span><span class="sxs-lookup"><span data-stu-id="61be9-148">On the Lync Server 2010 server, open the Lync Server Deployment Wizard.</span></span>

10. <span data-ttu-id="61be9-149">Lync Server 展開ウィザードで、[ **Lync Server システムのインストールまたは更新**] をクリックし、[ **ステップ 2: lync Server コンポーネントのセットアップまたは削除**] をクリックし、[ **次へ**] をクリックして概要を確認し、[ **完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="61be9-149">In Lync Server Deployment Wizard, click **Install or Update Lync Server System**, click **Step 2: Setup or Remove Lync Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span>

11. <span data-ttu-id="61be9-150">Lync Server 2013 サーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="61be9-150">Reboot the Lync Server 2013 server.</span></span> <span data-ttu-id="61be9-151">これは、グループメンバーシップの変更によって中央管理サーバーデータベースにアクセスするために必要です。</span><span class="sxs-lookup"><span data-stu-id="61be9-151">This is required because of a group membership change to access Central Management Server database.</span></span>

12. <span data-ttu-id="61be9-152">新しい中央管理ストアとのレプリケーションが行われていることを確認するには、Lync Server 管理シェルで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="61be9-152">To confirm that replication with the new Central Management store is occurring, in the Lync Server Management Shell, type:</span></span>
    
        Get-CsManagementStoreReplicationStatus
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="61be9-153">レプリケーションが現在のすべてのレプリカを更新するには、少し時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="61be9-153">The replication may take some time to update all current replicas.</span></span>

    
    </div>

</div>

<div>

## <a name="to-remove-lync-server-2010central-management-store-files-after-a-move"></a><span data-ttu-id="61be9-154">移行後に Lync Server 2010 Central Management store ファイルを削除するには</span><span class="sxs-lookup"><span data-stu-id="61be9-154">To remove Lync Server 2010 Central Management store files after a move</span></span>

1.  <span data-ttu-id="61be9-155">Lync server 2010 サーバー上で、Lync Server 管理シェルがインストールされているコンピューターに **RTCUniversalServerAdmins** グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="61be9-155">On the Lync Server 2010 server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="61be9-156">また、SQL Server データベース管理者のユーザー権限とアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="61be9-156">You must also have the SQL Server database administrator user rights and permissions.</span></span>

2.  <span data-ttu-id="61be9-157">Lync Server 管理シェルを開く</span><span class="sxs-lookup"><span data-stu-id="61be9-157">Open Lync Server Management Shell</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="61be9-158">レプリケーションが完了して安定するまで、以前のデータベース ファイルを削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="61be9-158">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="61be9-159">レプリケーションを完了する前にファイルを削除すると、レプリケーションプロセスが中断され、新しく移動した中央管理サーバーが不明な状態のままになります。</span><span class="sxs-lookup"><span data-stu-id="61be9-159">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="61be9-160">レプリケーションの状態を確認するには、<STRONG>Get-CsManagementStoreReplicationStatus</STRONG> コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="61be9-160">Use the cmdlet <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> to confirm the replication status.</span></span>

    
    </div>

3.  <span data-ttu-id="61be9-161">Lync Server 2010 Central Management サーバーから中央管理ストアデータベースファイルを削除するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="61be9-161">To remove the Central Management store database files from the Lync Server 2010 Central Management Server, type:</span></span>
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
    
    <span data-ttu-id="61be9-162">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="61be9-162">For example:</span></span>
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
    
    <span data-ttu-id="61be9-163">は、 \<FQDN of SQL Server\> Enterprise Edition 展開の Lync Server 2010 バックエンドサーバー、または Standard Edition サーバーの FQDN のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="61be9-163">Where the \<FQDN of SQL Server\> is either the Lync Server 2010 Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

