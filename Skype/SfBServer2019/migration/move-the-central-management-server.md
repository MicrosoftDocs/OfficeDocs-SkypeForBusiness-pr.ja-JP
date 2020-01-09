---
title: 中央管理サーバーを移動する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype for Business Server 2019 に移行した後は、従来のサーバーを削除する前に、中央管理サーバーを Skype for Business Server 2019 フロントエンドサーバーまたはプールに移動する必要があります。
ms.openlocfilehash: b6a2dd08949b5b15370f27e1da936009048982f6
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40990932"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="3e0cd-103">従来のサーバーの全体管理サーバーを Skype for Business Server 2019 に移動する</span><span class="sxs-lookup"><span data-stu-id="3e0cd-103">Move the legacy Central Management Server to Skype for Business Server 2019</span></span>

<span data-ttu-id="3e0cd-104">Skype for Business Server 2019 に移行した後、レガシサーバーを削除する前に、中央管理サーバーを Skype for Business Server 2019 フロントエンドサーバーまたはプールに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-104">After migrating to Skype for Business Server 2019, and before you can remove the legacy server, you need to move the Central Management Server to the Skype for Business Server 2019 Front End Server or pool.</span></span> 
  
<span data-ttu-id="3e0cd-105">サーバーの全体管理サーバーは、1つのマスター/マルチレプリカシステムです。このシステムでは、データベースの読み取り/書き込みのコピーが、中央管理サーバーを含むフロントエンドサーバーによって保持されています。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-105">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="3e0cd-106">トポロジ内の各コンピューターには、サーバーを含むフロントエンドサーバーを含む、セットアップ時にコンピューターにインストールされた、SQL Server データベースの中央管理ストアデータの読み取り専用コピーがあります (既定では、RTCLOCAL という名前が付いています)。デプロイメント.</span><span class="sxs-lookup"><span data-stu-id="3e0cd-106">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="3e0cd-107">ローカルデータベースは、すべてのコンピューターでサービスとして実行される Skype for Business Server Replica Replicator エージェントを介して、レプリカの更新を受信します。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-107">The local database receives replica updates by way of the Skype for Business Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="3e0cd-108">サーバーの全体管理サーバー上の実際のデータベースの名前とローカルレプリカは XDS で、これらは xds と xds のファイルで構成されます。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-108">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="3e0cd-109">Master データベースの場所は、Active Directory ドメインサービスのサービスコントロールポイント (SCP) によって参照されます。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-109">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="3e0cd-110">中央管理サーバーを使用して Skype for Business Server を管理および構成するすべてのツール SCP を使用して、中央管理ストアを検索します。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-110">All tools that use the Central Management Server to manage and configure Skype for Business Server use the SCP to locate the Central Management store.</span></span>
  
<span data-ttu-id="3e0cd-111">サーバーの全体管理サーバーが正常に移動されたら、元のフロントエンドサーバーから中央管理サーバーのデータベースを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-111">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="3e0cd-112">サーバーの全体管理サーバーデータベースの削除については、「[フロントエンドプールの SQL Server データベースを削除](remove-the-sql-server-database-for-a-front-end-pool.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-112">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>
  
<span data-ttu-id="3e0cd-113">Skype for Business Server 管理シェルで Windows PowerShell コマンドレット**CsManagementServer**を使用して、従来の sql server データベースから Skype For business SERVER 2019 SQL server データベースにデータベースを移動します。次に、Skype For business Server 2019 Central Management Server の場所を指すように SCP を更新します。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-113">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Skype for Business Server Management Shell to move the database from the legacy install SQL Server database to the Skype for Business Server 2019 SQL Server database, and then update the SCP to point to the Skype for Business Server 2019 Central Management Server location.</span></span> 
  
<span data-ttu-id="3e0cd-114">このセクションの手順を使用して、中央管理サーバーを移動する前に、Skype for Business Server 2019 フロントエンドサーバーを準備します。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-114">Use the procedures in this section to prepare the Skype for Business Server 2019 Front End Servers before you move the Central Management Server.</span></span>
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="3e0cd-115">Enterprise Edition フロントエンドプールを準備するには</span><span class="sxs-lookup"><span data-stu-id="3e0cd-115">To prepare an Enterprise Edition Front End pool</span></span>

1. <span data-ttu-id="3e0cd-116">中央管理サーバーを再配置する Skype for Business Server 2019 Enterprise Edition のフロントエンドプールで、Skype for Business Server 管理シェルが**RTCUniversalServerAdmins**グループのメンバーとしてインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-116">On the Skype for Business Server 2019 Enterprise Edition Front End pool where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="3e0cd-117">また、中央管理ストアをインストールするデータベースの SQL Server データベース sysadmin ユーザー権限と権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-117">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span> 
    
2. <span data-ttu-id="3e0cd-118">Skype for Business Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-118">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="3e0cd-119">Skype for Business Server 2019 SQL Server データベースに新しい中央管理ストアを作成するには、Skype for business Server 管理シェルで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-119">To create the new Central Management store in the Skype for Business Server 2019 SQL Server database, in the Skype for Business Server Management Shell, type:</span></span>
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. <span data-ttu-id="3e0cd-120">**Skype For Business Server フロントエンド**サービスの状態が**開始**されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-120">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="3e0cd-121">Standard Edition フロントエンドサーバーを準備するには</span><span class="sxs-lookup"><span data-stu-id="3e0cd-121">To prepare a Standard Edition Front End Server</span></span>

1. <span data-ttu-id="3e0cd-122">中央管理サーバーを再配置する Skype for Business Server 2019 Standard Edition フロントエンドサーバーで、Skype for Business Server 管理シェルが**RTCUniversalServerAdmins**グループのメンバーとしてインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-122">On the Skype for Business Server 2019 Standard Edition Front End Server where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> 
    
2. <span data-ttu-id="3e0cd-123">Skype for Business Server 展開ウィザードを開きます。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-123">Open the Skype for Business Server Deployment Wizard.</span></span>
    
3. <span data-ttu-id="3e0cd-124">Skype for Business Server の展開ウィザードで、[**最初の Standard Edition サーバーの準備**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-124">In the Skype for Business Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>
    
4. <span data-ttu-id="3e0cd-125">[**コマンドの実行**] ページでは、SQL Server Express が中央管理サーバーとしてインストールされています。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-125">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="3e0cd-126">必要なファイアウォールルールが作成されます。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-126">Necessary firewall rules are created.</span></span> <span data-ttu-id="3e0cd-127">データベースと必須ソフトウェアのインストールが完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-127">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3e0cd-128">最初のインストールでは、コマンド出力の概要画面に表示される更新プログラムがないと、時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-128">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="3e0cd-129">これは、SQL Server Express をインストールしているためです。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-129">This is due to the installation of SQL Server Express.</span></span> <span data-ttu-id="3e0cd-130">データベースのインストールを監視する必要がある場合は、タスクマネージャーを使用してセットアップを監視します。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-130">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span> 
  
5. <span data-ttu-id="3e0cd-131">Skype for Business Server 2019 Standard Edition のフロントエンドサーバーで新しい中央管理ストアを作成するには、Skype for business Server 管理シェルで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-131">To create the new Central Management store on the Skype for Business Server 2019 Standard Edition Front End Server, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. <span data-ttu-id="3e0cd-132">**Skype For Business Server フロントエンド**サービスの状態が**開始**されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-132">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="3e0cd-133">従来のインストールを移行するには、サーバーの全体管理サーバーを Skype for Business Server 2019 にインストールします。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-133">To move the legacy installs Central Management Server to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="3e0cd-134">中央管理サーバーとなる Skype for Business Server 2019 サーバーで、Skype for Business Server 管理シェルが**RTCUniversalServerAdmins**グループのメンバーとしてインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-134">On the Skype for Business Server 2019 server that will be the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="3e0cd-135">SQL Server データベース管理者のユーザー権限と権限も必要です。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-135">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="3e0cd-136">Skype for Business Server 管理シェル (管理者として実行) を開きます。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-136">Open Skype for Business Server Management Shell (run as administrator).</span></span>
    
3. <span data-ttu-id="3e0cd-137">Skype for Business Server 管理シェルで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-137">In the Skype for Business Server Management Shell, type:</span></span> 
    
   ```PowerShell
   Enable-CsTopology
   ```

    > [!CAUTION]
    > <span data-ttu-id="3e0cd-138">問題`Enable-CsTopology`が解決しない場合は、続行する前にコマンドの完了を妨げる問題を解決してください。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-138">If `Enable-CsTopology` is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="3e0cd-139">**Enable-CsTopology**方法で問題が発生した場合は、移行が失敗し、中央管理ストアがない状態でトポロジが残る場合があります。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-139">If **Enable-CsTopology** is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span> 
  
4. <span data-ttu-id="3e0cd-140">Skype for Business Server 2019 フロントエンドサーバーまたはフロントエンドプールの Skype for Business Server 管理シェルで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-140">On the Skype for Business Server 2019 Front End Server or Front End pool, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```PowerShell
   Move-CsManagementServer
   ```

5. <span data-ttu-id="3e0cd-141">Skype for Business Server 管理シェルには、サーバー、ファイルストア、データベースストア、現在の状態と提案された状態のサービス接続ポイントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-141">Skype for Business Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="3e0cd-142">情報を慎重に読み、目的のソースと行先であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-142">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="3e0cd-143">続行する場合は「 **Y** 」、移動を停止する場合は**N**を入力します。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-143">Type **Y** to continue, or **N** to stop the move.</span></span> 
    
6. <span data-ttu-id="3e0cd-144">**CsManagementServer**コマンドによって生成された警告またはエラーを確認し、解決します。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-144">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span> 
    
7. <span data-ttu-id="3e0cd-145">Skype for Business server 2019 サーバーで、Skype for Business Server Deployment ウィザードを開きます。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-145">On the Skype for Business Server 2019 server, open the Skype for Business Server Deployment Wizard.</span></span> 
    
8. <span data-ttu-id="3e0cd-146">Skype for Business Server の展開ウィザードで、[ **skype For Business Server システムのインストールまたは更新**] をクリックし、[**手順 2: Skype For business Server コンポーネントのセットアップまたは削除**] をクリックし、[**次へ**] をクリックして概要を確認し、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-146">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
9. <span data-ttu-id="3e0cd-147">従来のインストールサーバーで展開ウィザードを開きます。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-147">On the legacy install server, open the Deployment Wizard.</span></span> 
    
10. <span data-ttu-id="3e0cd-148">Skype for Business Server の展開ウィザードで、[ **skype For Business Server システムのインストールまたは更新**] をクリックし、[**手順 2: Skype For business Server コンポーネントのセットアップまたは削除**] をクリックし、[**次へ**] をクリックして概要を確認し、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-148">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
11. <span data-ttu-id="3e0cd-149">Skype for Business Server 2019 サーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-149">Reboot the Skype for Business Server 2019 server.</span></span> <span data-ttu-id="3e0cd-150">これが必要なのは、サーバーの全体管理サーバーデータベースにアクセスするためのグループメンバーシップが変更されたためです。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-150">This is required because of a group membership change to access Central Management Server database.</span></span>
    
12. <span data-ttu-id="3e0cd-151">新しい中央管理ストアでのレプリケーションが行われていることを確認するには、Skype for Business Server 管理シェルで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-151">To confirm that replication with the new Central Management store is occurring, in the Skype for Business Server Management Shell, type:</span></span> 
    
    ```PowerShell
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > <span data-ttu-id="3e0cd-152">レプリケーションは、現在のすべてのレプリカの更新に時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-152">The replication may take some time to update all current replicas.</span></span> 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a><span data-ttu-id="3e0cd-153">移行後に、従来の中央管理ストアのファイルを削除するには</span><span class="sxs-lookup"><span data-stu-id="3e0cd-153">To remove legacy install Central Management store files after a move</span></span>

1. <span data-ttu-id="3e0cd-154">従来のインストールサーバーで、Skype for Business Server 管理シェルが**RTCUniversalServerAdmins**グループのメンバーとしてインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-154">On the legacy install server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="3e0cd-155">SQL Server データベース管理者のユーザー権限と権限も必要です。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-155">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="3e0cd-156">Skype for Business Server 管理シェルを開く</span><span class="sxs-lookup"><span data-stu-id="3e0cd-156">Open Skype for Business Server Management Shell</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="3e0cd-157">複製が完了し、安定しているまで、以前のデータベースファイルの削除は行わないでください。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-157">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="3e0cd-158">複製処理を完了する前にファイルを削除すると、レプリケーションプロセスが中断され、新しく移動した中央管理サーバーは不明な状態のままになります。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-158">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="3e0cd-159">**CsManagementStoreReplicationStatus**コマンドレットを使用して、レプリケーションの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-159">Use the cmdlet **Get-CsManagementStoreReplicationStatus** to confirm the replication status.</span></span> 
  
3. <span data-ttu-id="3e0cd-160">従来のセントラルマネジメントサーバーから全体管理ストアデータベースファイルを削除するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-160">To remove the Central Management store database files from the legacy install Central Management Server, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    <span data-ttu-id="3e0cd-161">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-161">For example:</span></span>
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    <span data-ttu-id="3e0cd-162">_ \<SQL Server\>の FQDN_は、Enterprise Edition 展開または Standard edition サーバーの fqdn のレガシインストールバックエンドサーバーです。</span><span class="sxs-lookup"><span data-stu-id="3e0cd-162">Where the  _\<FQDN of SQL Server\>_ is either the legacy install Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span> 
    

