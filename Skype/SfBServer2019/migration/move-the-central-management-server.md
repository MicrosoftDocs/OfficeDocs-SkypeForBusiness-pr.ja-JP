---
title: 中央管理サーバーを移動します。
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ビジネス サーバー 2019 の Skype に移行した後は、中央管理サーバーを移動する、Skype ビジネス 2019 フロント エンド サーバーまたはプールのレガシ サーバーを削除する前にする必要があります。
ms.openlocfilehash: dc85548a3c81e55267bc0ed3a32e53860e4bce09
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894748"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="a72ee-103">ビジネス サーバー 2019 の Skype に従来のサーバーの全体管理サーバーを移動します。</span><span class="sxs-lookup"><span data-stu-id="a72ee-103">Move the legacy Central Management Server to Skype for Business Server 2019</span></span>

<span data-ttu-id="a72ee-104">ビジネス サーバー 2019、および従来のサーバーを削除する前に Skype に移行した後、Skype をビジネス 2019 フロント エンド サーバーまたはプールのサーバーの全体管理サーバーを移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a72ee-104">After migrating to Skype for Business Server 2019, and before you can remove the legacy server, you need to move the Central Management Server to the Skype for Business Server 2019 Front End Server or pool.</span></span> 
  
<span data-ttu-id="a72ee-105">サーバーの全体管理サーバーは、マスターまたは複数の単一のレプリカのシステムでは、中央管理サーバーが含まれるフロント エンド サーバーでデータベースの読み取り/書き込みコピーを保持する場所。</span><span class="sxs-lookup"><span data-stu-id="a72ee-105">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="a72ee-106">中央の管理サーバーを含むフロント エンド サーバーを含め、トポロジ内の各コンピューターには、中央管理ストア内のデータのセットアップ中にコンピューターにインストールされている SQL Server データベース (既定では RTCLOCAL という名前) の読み取り専用コピーし、展開します。</span><span class="sxs-lookup"><span data-stu-id="a72ee-106">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="a72ee-107">ローカル データベースは、すべてのコンピューターでサービスとして実行されるビジネス サーバー レプリカ複製エージェントの Skype を使用してレプリカの更新を受信します。</span><span class="sxs-lookup"><span data-stu-id="a72ee-107">The local database receives replica updates by way of the Skype for Business Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="a72ee-108">中央管理サーバーとローカルのレプリカには、実際のデータベースの名前は、XDS で、xds.mdf および xds.ldf ファイルの構成です。</span><span class="sxs-lookup"><span data-stu-id="a72ee-108">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="a72ee-109">Master データベースの場所は、Active Directory ドメイン サービスでサービス コントロール ポイント (SCP) によって参照されます。</span><span class="sxs-lookup"><span data-stu-id="a72ee-109">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="a72ee-110">管理し、Skype をビジネスのサーバーの構成をサーバーの全体管理サーバーを使用するすべてのツールでは、SCP を使用して、中央管理ストアを探します。</span><span class="sxs-lookup"><span data-stu-id="a72ee-110">All tools that use the Central Management Server to manage and configure Skype for Business Server use the SCP to locate the Central Management store.</span></span>
  
<span data-ttu-id="a72ee-111">中央管理サーバーを正常に移動した後は、元のフロント エンド サーバーからサーバーの全体管理サーバーのデータベースを削除してください。</span><span class="sxs-lookup"><span data-stu-id="a72ee-111">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="a72ee-112">中央管理サーバーのデータベースを削除する方法の詳細については、[フロント エンド プールの SQL Server データベースを削除する](remove-the-sql-server-database-for-a-front-end-pool.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a72ee-112">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>
  
<span data-ttu-id="a72ee-113">ビジネス サーバー 2019 の SQL Server データベースでは、Skype にレガシー インストールの SQL Server データベースからデータベースを移動し、更新するサーバー管理シェルをビジネス用の Skype に**移動 CsManagementServer**の Windows PowerShell コマンドレットを使用する、ビジネス 2019 中央管理サーバーの場所の Skype を指すように SCP です。</span><span class="sxs-lookup"><span data-stu-id="a72ee-113">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Skype for Business Server Management Shell to move the database from the legacy install SQL Server database to the Skype for Business Server 2019 SQL Server database, and then update the SCP to point to the Skype for Business Server 2019 Central Management Server location.</span></span> 
  
<span data-ttu-id="a72ee-114">ビジネス サーバー 2019 フロント エンド サーバーのサーバーの全体管理サーバーを移動する前に、Skype を準備するのに、このセクションの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="a72ee-114">Use the procedures in this section to prepare the Skype for Business Server 2019 Front End Servers before you move the Central Management Server.</span></span>
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="a72ee-115">エンタープライズ エディションのフロント エンド プールを準備するのには</span><span class="sxs-lookup"><span data-stu-id="a72ee-115">To prepare an Enterprise Edition Front End pool</span></span>

1. <span data-ttu-id="a72ee-116">ビジネス サーバー 2019 エンタープライズ エディションのフロント エンド プールのサーバーの全体管理サーバーに再配置する Skype、上には**RTCUniversalServerAdmins のメンバーとしてビジネス サーバー管理シェルの Skype がインストールされているコンピューターにログオンします。** グループです。</span><span class="sxs-lookup"><span data-stu-id="a72ee-116">On the Skype for Business Server 2019 Enterprise Edition Front End pool where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="a72ee-117">中央管理ストアをインストールするデータベースの SQL Server データベースのシステム管理者のユーザー権利とアクセス許可を必要することもあります。</span><span class="sxs-lookup"><span data-stu-id="a72ee-117">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span> 
    
2. <span data-ttu-id="a72ee-118">Skype をビジネス サーバー管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a72ee-118">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="a72ee-119">ビジネス サーバー 2019 の SQL Server データベースでは、ビジネス サーバー管理シェルには、Skype での Skype の新しい中央管理ストアを作成するのには次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="a72ee-119">To create the new Central Management store in the Skype for Business Server 2019 SQL Server database, in the Skype for Business Server Management Shell, type:</span></span>
    
   ```
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. <span data-ttu-id="a72ee-120">**Skype**ビジネス サーバーのフロント エンドのサービスの状態が**開始**ことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a72ee-120">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="a72ee-121">標準 Edition フロント エンド サーバーを準備するのには</span><span class="sxs-lookup"><span data-stu-id="a72ee-121">To prepare a Standard Edition Front End Server</span></span>

1. <span data-ttu-id="a72ee-122">ビジネス サーバー 2019 標準エディション フロント エンド サーバーのサーバーの全体管理サーバーに再配置する Skype、上には**RTCUniversalServerAdmins のメンバーとしてビジネス サーバー管理シェルの Skype がインストールされているコンピューターにログオンします。** グループです。</span><span class="sxs-lookup"><span data-stu-id="a72ee-122">On the Skype for Business Server 2019 Standard Edition Front End Server where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> 
    
2. <span data-ttu-id="a72ee-123">Skype をビジネス サーバーの展開ウィザードを開きます。</span><span class="sxs-lookup"><span data-stu-id="a72ee-123">Open the Skype for Business Server Deployment Wizard.</span></span>
    
3. <span data-ttu-id="a72ee-124">ビジネス サーバーの展開ウィザードの Skype、 **Standard Edition サーバーの最初の準備**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a72ee-124">In the Skype for Business Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>
    
4. <span data-ttu-id="a72ee-125">**コマンドの実行**] ページで、SQL Server Express は、サーバーの全体管理サーバーとしてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="a72ee-125">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="a72ee-126">必要なファイアウォール規則が作成されます。</span><span class="sxs-lookup"><span data-stu-id="a72ee-126">Necessary firewall rules are created.</span></span> <span data-ttu-id="a72ee-127">データベースと必要なソフトウェアのインストールが完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a72ee-127">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a72ee-128">最初のインストール コマンドの出力の概要] 画面に表示内容は更新に時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="a72ee-128">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="a72ee-129">これは、SQL Server Express をインストールするためです。</span><span class="sxs-lookup"><span data-stu-id="a72ee-129">This is due to the installation of SQL Server Express.</span></span> <span data-ttu-id="a72ee-130">データベースのインストールを監視する場合は、セットアップを監視するのにはタスク マネージャーを使用します。</span><span class="sxs-lookup"><span data-stu-id="a72ee-130">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span> 
  
5. <span data-ttu-id="a72ee-131">ビジネス サーバー 2019 標準 Edition フロント エンド サーバー、ビジネス サーバー管理シェルには、Skype では、Skype の新しい中央管理ストアを作成するのには次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="a72ee-131">To create the new Central Management store on the Skype for Business Server 2019 Standard Edition Front End Server, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. <span data-ttu-id="a72ee-132">**Skype**ビジネス サーバーのフロント エンドのサービスの状態が**開始**ことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a72ee-132">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="a72ee-133">従来の移動には、ビジネス サーバー 2019 用 Skype を中央の管理サーバーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a72ee-133">To move the legacy installs Central Management Server to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="a72ee-134">ビジネス サーバー 2019 のサーバーにサーバーの全体管理サーバーの Skype、 **RTCUniversalServerAdmins**グループのメンバーとしてビジネス サーバー管理シェルの Skype がインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a72ee-134">On the Skype for Business Server 2019 server that will be the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="a72ee-135">SQL Server データベース管理者のユーザー権利とアクセス許可も必要です。</span><span class="sxs-lookup"><span data-stu-id="a72ee-135">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="a72ee-136">Skype をビジネス サーバー管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a72ee-136">Open Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="a72ee-137">ビジネス サーバー管理シェルの Skype で次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="a72ee-137">In the Skype for Business Server Management Shell, type:</span></span> 
    
   ```
   Enable-CsTopology
   ```

    > [!CAUTION]
    > <span data-ttu-id="a72ee-138">場合`Enable-CsTopology`が失敗した場合は、コマンドが続行する前に完了するを防止する問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="a72ee-138">If `Enable-CsTopology` is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="a72ee-139">移動は失敗します、それが状態のままに、トポロジ**を有効にする CsTopology**が成功しない場合は、中央管理ストアが存在しません。</span><span class="sxs-lookup"><span data-stu-id="a72ee-139">If **Enable-CsTopology** is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span> 
  
4. <span data-ttu-id="a72ee-140">ビジネス 2019 フロント エンド サーバーまたはフロント エンド プール、ビジネス サーバー管理シェルには、Skype の Skype で次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="a72ee-140">On the Skype for Business Server 2019 Front End Server or Front End pool, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```
   Move-CsManagementServer
   ```

5. <span data-ttu-id="a72ee-141">Skype ビジネス サーバー管理シェルには、サーバー、ファイル ストア、データベース ストア、および現在の状態を提案済み状態のサービス接続ポイントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a72ee-141">Skype for Business Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="a72ee-142">情報をよく読んで、目的のソースと宛先を確認します。</span><span class="sxs-lookup"><span data-stu-id="a72ee-142">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="a72ee-143">続けるには、 **Y**または移動を停止するのには**N**を入力します。</span><span class="sxs-lookup"><span data-stu-id="a72ee-143">Type **Y** to continue, or **N** to stop the move.</span></span> 
    
6. <span data-ttu-id="a72ee-144">**移動-CsManagementServer**コマンドによって生成されるエラーまたは警告を確認し、それらを解決します。</span><span class="sxs-lookup"><span data-stu-id="a72ee-144">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span> 
    
7. <span data-ttu-id="a72ee-145">ビジネス サーバー 2019 サーバーの Skype、Skype ビジネス サーバーの展開ウィザードを開きます。</span><span class="sxs-lookup"><span data-stu-id="a72ee-145">On the Skype for Business Server 2019 server, open the Skype for Business Server Deployment Wizard.</span></span> 
    
8. <span data-ttu-id="a72ee-146">ビジネス サーバーの展開ウィザードの Skype は、の**インストールまたはサーバーのビジネス システムの更新プログラムの Skype**をクリックして**手順 2: セットアップまたは削除の Skype ビジネス サーバー コンポーネントの**は、[**次へ**] をクリックしの概要を確認 **[完了] をクリックし、**.</span><span class="sxs-lookup"><span data-stu-id="a72ee-146">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
9. <span data-ttu-id="a72ee-147">従来のサーバーをインストール、展開ウィザードを開きます。</span><span class="sxs-lookup"><span data-stu-id="a72ee-147">On the legacy install server, open the Deployment Wizard.</span></span> 
    
10. <span data-ttu-id="a72ee-148">ビジネス サーバーの展開ウィザードの Skype は、の**インストールまたはサーバーのビジネス システムの更新プログラムの Skype**をクリックして**手順 2: セットアップまたは削除の Skype ビジネス サーバー コンポーネントの**は、[**次へ**] をクリックしの概要を確認 **[完了] をクリックし、**.</span><span class="sxs-lookup"><span data-stu-id="a72ee-148">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
11. <span data-ttu-id="a72ee-149">ビジネス サーバー 2019 サーバーの Skype を再起動します。</span><span class="sxs-lookup"><span data-stu-id="a72ee-149">Reboot the Skype for Business Server 2019 server.</span></span> <span data-ttu-id="a72ee-150">グループ メンバーシップの変更をサーバーの全体管理サーバーのデータベースにアクセスするために必要です。</span><span class="sxs-lookup"><span data-stu-id="a72ee-150">This is required because of a group membership change to access Central Management Server database.</span></span>
    
12. <span data-ttu-id="a72ee-151">新しい中央管理ストアで発生している、ビジネス サーバー管理シェルには、Skype では、そのレプリケーションを確認するのには次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="a72ee-151">To confirm that replication with the new Central Management store is occurring, in the Skype for Business Server Management Shell, type:</span></span> 
    
    ```
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > <span data-ttu-id="a72ee-152">レプリケーション現在のすべてのレプリカを更新するのには時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a72ee-152">The replication may take some time to update all current replicas.</span></span> 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a><span data-ttu-id="a72ee-153">移動後のレガシー インストールの中央管理ストアのファイルを削除するのには</span><span class="sxs-lookup"><span data-stu-id="a72ee-153">To remove legacy install Central Management store files after a move</span></span>

1. <span data-ttu-id="a72ee-154">従来のサーバーのインストール、 **RTCUniversalServerAdmins**グループのメンバーとしてビジネス サーバー管理シェルの Skype がインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a72ee-154">On the legacy install server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="a72ee-155">SQL Server データベース管理者のユーザー権利とアクセス許可も必要です。</span><span class="sxs-lookup"><span data-stu-id="a72ee-155">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="a72ee-156">ビジネス サーバー管理シェルの Skype を開く</span><span class="sxs-lookup"><span data-stu-id="a72ee-156">Open Skype for Business Server Management Shell</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="a72ee-157">レプリケーションが完了し、安定するまでは、以前のデータベース ファイルの削除を続行しないでください。</span><span class="sxs-lookup"><span data-stu-id="a72ee-157">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="a72ee-158">レプリケーションを完了する前にファイルを削除する場合レプリケーション ・ プロセスを中断し、状態が不明で新しく移動されたサーバーの全体管理サーバーのままにします。</span><span class="sxs-lookup"><span data-stu-id="a72ee-158">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="a72ee-159">レプリケーションの状態を確認するのには、 **Get CsManagementStoreReplicationStatus**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="a72ee-159">Use the cmdlet **Get-CsManagementStoreReplicationStatus** to confirm the replication status.</span></span> 
  
3. <span data-ttu-id="a72ee-160">レガシー インストールのサーバーの全体管理サーバーから中央管理ストアのデータベース ファイルを削除するのには次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="a72ee-160">To remove the Central Management store database files from the legacy install Central Management Server, type:</span></span>
    
   ```
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    <span data-ttu-id="a72ee-161">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a72ee-161">For example:</span></span>
    
   ```
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    <span data-ttu-id="a72ee-162">場所、 _ \<SQL Server の FQDN\>_ は、従来のいずれか、Enterprise Edition または Standard Edition サーバーの FQDN のバック エンド サーバーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a72ee-162">Where the  _\<FQDN of SQL Server\>_ is either the legacy install Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span> 
    

