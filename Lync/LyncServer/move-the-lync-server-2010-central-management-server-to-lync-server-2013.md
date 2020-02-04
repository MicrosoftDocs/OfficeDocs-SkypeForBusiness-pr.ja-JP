---
title: Lync Server 2010 Central Management Server を Lync Server 2013 に移動する
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
ms.openlocfilehash: 5f301c8f6e11ca3c8f19ed167489bb3fbf51fc63
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743697"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-the-lync-server-2010-central-management-server-to-lync-server-2013"></a><span data-ttu-id="4f52e-102">Lync Server 2010 Central Management Server を Lync Server 2013 に移動する</span><span class="sxs-lookup"><span data-stu-id="4f52e-102">Move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f52e-103">_**最終更新日:** 2013-11-25_</span><span class="sxs-lookup"><span data-stu-id="4f52e-103">_**Topic Last Modified:** 2013-11-25_</span></span>

<span data-ttu-id="4f52e-104">Lync server 2010 から Lync Server 2013 に移行した後、従来の Lync Server 2010 サーバーを削除する前に、lync Server 2010 Central Management Server を Lync Server 2013 フロントエンドサーバーまたはプールに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f52e-104">After migrating from Lync Server 2010 to Lync Server 2013, you need to move the Lync Server 2010 Central Management Server to the Lync Server 2013 Front End Server or pool, before you can remove the legacy Lync Server 2010 server.</span></span>

<span data-ttu-id="4f52e-105">サーバーの全体管理サーバーは、1つのマスター/マルチレプリカシステムです。このシステムでは、データベースの読み取り/書き込みのコピーが、中央管理サーバーを含むフロントエンドサーバーによって保持されています。</span><span class="sxs-lookup"><span data-stu-id="4f52e-105">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="4f52e-106">トポロジ内の各コンピューターには、サーバーを含むフロントエンドサーバーを含む、セットアップ時にコンピューターにインストールされた、SQL Server データベースの中央管理ストアデータの読み取り専用コピーがあります (既定では、RTCLOCAL という名前が付いています)。デプロイメント.</span><span class="sxs-lookup"><span data-stu-id="4f52e-106">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="4f52e-107">ローカルデータベースは、すべてのコンピューターでサービスとして実行される Lync Server Replica Replicator エージェントを介して、レプリカの更新を受信します。</span><span class="sxs-lookup"><span data-stu-id="4f52e-107">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="4f52e-108">サーバーの全体管理サーバー上の実際のデータベースの名前とローカルレプリカは XDS で、これらは xds と xds のファイルで構成されます。</span><span class="sxs-lookup"><span data-stu-id="4f52e-108">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="4f52e-109">Master データベースの場所は、Active Directory ドメインサービスのサービスコントロールポイント (SCP) によって参照されます。</span><span class="sxs-lookup"><span data-stu-id="4f52e-109">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="4f52e-110">一元管理サーバーを使用して Lync Server を管理および構成するすべてのツール SCP を使用して、中央管理ストアを検索します。</span><span class="sxs-lookup"><span data-stu-id="4f52e-110">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>

<span data-ttu-id="4f52e-111">サーバーの全体管理サーバーが正常に移動されたら、元のフロントエンドサーバーから中央管理サーバーのデータベースを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f52e-111">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="4f52e-112">サーバーの全体管理サーバーデータベースの削除については、「[フロントエンドプールの SQL Server データベースを削除](remove-the-sql-server-database-for-a-front-end-pool.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f52e-112">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>

<span data-ttu-id="4f52e-113">Lync server 管理シェルで Windows PowerShell コマンドレット**CsManagementServer**を使用して、lync SERVER 2010 sql server データベースから lync SERVER 2013 sql server データベースにデータベースを移動し、次に、lync Server 2013 中央管理サーバーの場所を指すように SCP を更新します。</span><span class="sxs-lookup"><span data-stu-id="4f52e-113">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Lync Server Management Shell to move the database from the Lync Server 2010 SQL Server database to the Lync Server 2013 SQL Server database, and then update the SCP to point to the Lync Server 2013 Central Management Server location.</span></span>

<div>

## <a name="preparing-lync-server-2013front-end-servers-before-moving-the-central-management-server"></a><span data-ttu-id="4f52e-114">サーバーの中央管理サーバーを移動する前に、Lync Server 2013 フロントエンドサーバーを準備する</span><span class="sxs-lookup"><span data-stu-id="4f52e-114">Preparing Lync Server 2013 Front End Servers before moving the Central Management Server</span></span>

<span data-ttu-id="4f52e-115">Lync Server 2010 Central Management Server を移動する前に、このセクションの手順を使用して、Lync Server 2013 フロントエンドサーバーを準備します。</span><span class="sxs-lookup"><span data-stu-id="4f52e-115">Use the procedures in this section to prepare the Lync Server 2013 Front End Servers before you move the Lync Server 2010 Central Management Server.</span></span>

<div>

## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="4f52e-116">Enterprise Edition フロントエンドプールを準備するには</span><span class="sxs-lookup"><span data-stu-id="4f52e-116">To prepare an Enterprise Edition Front End pool</span></span>

1.  <span data-ttu-id="4f52e-117">セントラル管理サーバーを再配置する Lync Server 2013 Enterprise Edition のフロントエンドプールで、 **RTCUniversalServerAdmins**グループのメンバーとして Lync Server 管理シェルがインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="4f52e-117">On the Lync Server 2013 Enterprise Edition Front End pool where you want to relocate the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="4f52e-118">また、中央管理ストアをインストールするデータベースの SQL Server データベース sysadmin ユーザー権限と権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="4f52e-118">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span>

2.  <span data-ttu-id="4f52e-119">Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="4f52e-119">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="4f52e-120">Lync Server 2013 SQL Server データベースに新しい中央管理ストアを作成するには、Lync Server 管理シェルで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="4f52e-120">To create the new Central Management store in the Lync Server 2013 SQL Server database, in the Lync Server Management Shell, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>

4.  <span data-ttu-id="4f52e-121">**Lync Server フロントエンド**サービスの状態が**開始**されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4f52e-121">Confirm that the status of the **Lync Server Front-End** service is **Started**.</span></span>

</div>

<div>

## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="4f52e-122">Standard Edition フロントエンドサーバーを準備するには</span><span class="sxs-lookup"><span data-stu-id="4f52e-122">To prepare a Standard Edition Front End Server</span></span>

1.  <span data-ttu-id="4f52e-123">セントラル管理サーバーを再配置する Lync Server 2013 Standard Edition フロントエンドサーバーで、 **RTCUniversalServerAdmins**グループのメンバーとして Lync Server 管理シェルがインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="4f52e-123">On the Lync Server 2013 Standard Edition Front End Server where you want to relocate the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span>

2.  <span data-ttu-id="4f52e-124">Lync Server 展開ウィザードを開きます。</span><span class="sxs-lookup"><span data-stu-id="4f52e-124">Open the Lync Server Deployment Wizard.</span></span>

3.  <span data-ttu-id="4f52e-125">Lync Server 展開ウィザードで、[**最初の Standard Edition サーバーの準備**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f52e-125">In the Lync Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>

4.  <span data-ttu-id="4f52e-126">[**コマンドの実行**] ページでは、SQL Server Express が中央管理サーバーとしてインストールされています。</span><span class="sxs-lookup"><span data-stu-id="4f52e-126">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="4f52e-127">必要なファイアウォールルールが作成されます。</span><span class="sxs-lookup"><span data-stu-id="4f52e-127">Necessary firewall rules are created.</span></span> <span data-ttu-id="4f52e-128">データベースと必須ソフトウェアのインストールが完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f52e-128">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4f52e-129">最初のインストールでは、コマンド出力の概要画面に表示される更新プログラムがないと、時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4f52e-129">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="4f52e-130">これは、SQL Server Express がインストールされているためです。</span><span class="sxs-lookup"><span data-stu-id="4f52e-130">This is due to the installation of the SQL Server Express.</span></span> <span data-ttu-id="4f52e-131">データベースのインストールを監視する必要がある場合は、タスクマネージャーを使用してセットアップを監視します。</span><span class="sxs-lookup"><span data-stu-id="4f52e-131">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span>

    
    </div>

5.  <span data-ttu-id="4f52e-132">Lync Server 2013 Standard Edition フロントエンドサーバーで新しい中央管理ストアを作成するには、Lync Server 管理シェルで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="4f52e-132">To create the new Central Management store on the Lync Server 2013 Standard Edition Front End Server, in the Lync Server Management Shell, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>

6.  <span data-ttu-id="4f52e-133">**Lync Server フロントエンド**サービスの状態が**開始**されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4f52e-133">Confirm that the status of the **Lync Server Front-End** service is **Started**.</span></span>

</div>

</div>

<div>

## <a name="to-move-the-lync-server-2010central-management-server-to-lync-server-2013"></a><span data-ttu-id="4f52e-134">Lync Server 2010 Central Management Server を Lync Server 2013 に移動するには</span><span class="sxs-lookup"><span data-stu-id="4f52e-134">To move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>

1.  <span data-ttu-id="4f52e-135">サーバーの全体管理サーバーとなる Lync Server 2013 サーバーで、 **RTCUniversalServerAdmins**グループのメンバーとして Lync Server 管理シェルがインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="4f52e-135">On the Lync Server 2013 server that will be the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="4f52e-136">SQL Server データベース管理者のユーザー権限と権限も必要です。</span><span class="sxs-lookup"><span data-stu-id="4f52e-136">You must also have the SQL Server database administrator user rights and permissions.</span></span>

2.  <span data-ttu-id="4f52e-137">Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="4f52e-137">Open Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="4f52e-138">Lync Server 管理シェルで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="4f52e-138">In the Lync Server Management Shell, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="4f52e-139">問題<CODE>Enable-CsTopology</CODE>が解決しない場合は、続行する前にコマンドの完了を妨げる問題を解決してください。</span><span class="sxs-lookup"><span data-stu-id="4f52e-139">If <CODE>Enable-CsTopology</CODE> is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="4f52e-140"><STRONG>Enable-CsTopology</STRONG>方法で問題が発生した場合は、移行が失敗し、中央管理ストアがない状態でトポロジが残る場合があります。</span><span class="sxs-lookup"><span data-stu-id="4f52e-140">If <STRONG>Enable-CsTopology</STRONG> is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span>

    
    </div>

4.  <span data-ttu-id="4f52e-141">Lync Server 2013 フロントエンドサーバーまたはフロントエンドプールの Lync Server 管理シェルで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="4f52e-141">On the Lync Server 2013 Front End Server or Front End pool, in the Lync Server Management Shell, type:</span></span>
    
        Move-CsManagementServer

5.  <span data-ttu-id="4f52e-142">Lync Server 管理シェルには、サーバー、ファイルストア、データベースストア、現在の状態と提案された状態のサービス接続ポイントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4f52e-142">Lync Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="4f52e-143">情報を慎重に読み、目的のソースと行先であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4f52e-143">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="4f52e-144">続行する場合は「 **Y** 」、移動を停止する場合は**N**を入力します。</span><span class="sxs-lookup"><span data-stu-id="4f52e-144">Type **Y** to continue, or **N** to stop the move.</span></span>

6.  <span data-ttu-id="4f52e-145">**CsManagementServer**コマンドによって生成された警告またはエラーを確認し、解決します。</span><span class="sxs-lookup"><span data-stu-id="4f52e-145">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span>

7.  <span data-ttu-id="4f52e-146">Lync Server 2013 サーバーで、Lync Server 展開ウィザードを開きます。</span><span class="sxs-lookup"><span data-stu-id="4f52e-146">On the Lync Server 2013 server, open the Lync Server Deployment Wizard.</span></span>

8.  <span data-ttu-id="4f52e-147">Lync Server の展開ウィザードで、[ **Lync Server System のインストールまたは更新**] をクリックし、[**手順 2: lync サーバーコンポーネントをセットアップまたは削除します**] をクリックし、[**次へ**] をクリックして概要を確認し、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f52e-147">In Lync Server Deployment Wizard, click **Install or Update Lync Server System**, click **Step 2: Setup or Remove Lync Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span>

9.  <span data-ttu-id="4f52e-148">Lync Server 2010 サーバーで、Lync Server 展開ウィザードを開きます。</span><span class="sxs-lookup"><span data-stu-id="4f52e-148">On the Lync Server 2010 server, open the Lync Server Deployment Wizard.</span></span>

10. <span data-ttu-id="4f52e-149">Lync Server の展開ウィザードで、[ **Lync Server System のインストールまたは更新**] をクリックし、[**手順 2: lync サーバーコンポーネントをセットアップまたは削除します**] をクリックし、[**次へ**] をクリックして概要を確認し、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f52e-149">In Lync Server Deployment Wizard, click **Install or Update Lync Server System**, click **Step 2: Setup or Remove Lync Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span>

11. <span data-ttu-id="4f52e-150">Lync Server 2013 サーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="4f52e-150">Reboot the Lync Server 2013 server.</span></span> <span data-ttu-id="4f52e-151">これが必要なのは、サーバーの全体管理サーバーデータベースにアクセスするためのグループメンバーシップが変更されたためです。</span><span class="sxs-lookup"><span data-stu-id="4f52e-151">This is required because of a group membership change to access Central Management Server database.</span></span>

12. <span data-ttu-id="4f52e-152">新しい中央管理ストアでのレプリケーションが行われていることを確認するには、Lync Server 管理シェルで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="4f52e-152">To confirm that replication with the new Central Management store is occurring, in the Lync Server Management Shell, type:</span></span>
    
        Get-CsManagementStoreReplicationStatus
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4f52e-153">レプリケーションは、現在のすべてのレプリカの更新に時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4f52e-153">The replication may take some time to update all current replicas.</span></span>

    
    </div>

</div>

<div>

## <a name="to-remove-lync-server-2010central-management-store-files-after-a-move"></a><span data-ttu-id="4f52e-154">移行後に Lync Server 2010 全体管理ストアのファイルを削除するには</span><span class="sxs-lookup"><span data-stu-id="4f52e-154">To remove Lync Server 2010 Central Management store files after a move</span></span>

1.  <span data-ttu-id="4f52e-155">Lync Server 2010 サーバーで、Lync Server 管理シェルが**RTCUniversalServerAdmins**グループのメンバーとしてインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="4f52e-155">On the Lync Server 2010 server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="4f52e-156">SQL Server データベース管理者のユーザー権限と権限も必要です。</span><span class="sxs-lookup"><span data-stu-id="4f52e-156">You must also have the SQL Server database administrator user rights and permissions.</span></span>

2.  <span data-ttu-id="4f52e-157">Lync Server 管理シェルを開く</span><span class="sxs-lookup"><span data-stu-id="4f52e-157">Open Lync Server Management Shell</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="4f52e-158">複製が完了し、安定しているまで、以前のデータベースファイルの削除は行わないでください。</span><span class="sxs-lookup"><span data-stu-id="4f52e-158">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="4f52e-159">複製処理を完了する前にファイルを削除すると、レプリケーションプロセスが中断され、新しく移動した中央管理サーバーは不明な状態のままになります。</span><span class="sxs-lookup"><span data-stu-id="4f52e-159">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="4f52e-160"><STRONG>CsManagementStoreReplicationStatus</STRONG>コマンドレットを使用して、レプリケーションの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="4f52e-160">Use the cmdlet <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> to confirm the replication status.</span></span>

    
    </div>

3.  <span data-ttu-id="4f52e-161">Lync Server 2010 Central Management サーバーから全体管理ストアデータベースファイルを削除するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="4f52e-161">To remove the Central Management store database files from the Lync Server 2010 Central Management Server, type:</span></span>
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
    
    <span data-ttu-id="4f52e-162">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4f52e-162">For example:</span></span>
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
    
    <span data-ttu-id="4f52e-163">SQL Server \<\>の FQDN は、Enterprise Edition の展開の Lync Server 2010 バックエンドサーバー、または STANDARD Edition サーバーの fqdn のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="4f52e-163">Where the \<FQDN of SQL Server\> is either the Lync Server 2010 Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

