---
title: Skype for Business Server 2015 での常設チャット サーバーの高可用性と障害復旧の構成
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: '概要: このトピックでは、Skype for Business Server 2015 で常設チャット サーバーの高可用性と障害復旧を構成する方法について説明します。'
ms.openlocfilehash: 0b58f820c1157da8ff36f8dcc68d9e08465bcddc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830627"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="ae124-103">Skype for Business Server 2015 での常設チャット サーバーの高可用性と障害復旧の構成</span><span class="sxs-lookup"><span data-stu-id="ae124-103">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ae124-104">**概要:** このトピックでは、Skype for Business Server 2015 で常設チャット サーバーの高可用性と障害復旧を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ae124-104">**Summary:** Read this topic to learn how to configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="ae124-105">Skype for Business Server は、データベース ミラーリングを含む、バック エンド サーバーの高可用性の複数のモードをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="ae124-105">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="ae124-106">詳細については [、「Plan for high availability and disaster recovery in Skype for Business Server 2015」を参照](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)してください。</span><span class="sxs-lookup"><span data-stu-id="ae124-106">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ae124-107">AlwaysOn 可用性グループは、常設チャット サーバーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ae124-107">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="ae124-108">高可用性と障害復旧用に常設チャット展開を構成する前に [、「Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015」](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md)の概念を理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae124-108">Before you configure your Persistent Chat deployment for high availability and disaster recovery, be sure you are familiar with the concepts in [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="ae124-109">これらのトピックで説明されている常設チャット サーバーの障害復旧ソリューションは、拡大された常設チャット サーバー プール上に構築されています。</span><span class="sxs-lookup"><span data-stu-id="ae124-109">The disaster recovery solution for Persistent Chat Server described in these topics is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="ae124-110">計画に関するコンテンツでは、リソース要件と、高可用性のための SQL Server ミラーリングの使用や障害復旧のための SQL Server ログ配布など、常設チャット サーバーの高可用性と障害復旧を可能にする拡大プール トポロジについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ae124-110">The planning content describes resource requirements, and the stretched pool topology that enables high availability and disaster recovery for Persistent Chat Server, including using SQL Server mirroring for high availability and SQL Server log shipping for disaster recovery.</span></span>
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a><span data-ttu-id="ae124-111">トポロジ ビルダーを使用して高可用性と障害復旧を構成する</span><span class="sxs-lookup"><span data-stu-id="ae124-111">Use Topology Builder to configure high availability and disaster recovery</span></span>

<span data-ttu-id="ae124-112">トポロジ ビルダー内で、以下の手順を実行して、常設チャット サーバーの高可用性と障害復旧を構成します。</span><span class="sxs-lookup"><span data-stu-id="ae124-112">Within Topology Builder, perform the following steps to configure high availability and disaster recovery for Persistent Chat Server.</span></span>
  
1. <span data-ttu-id="ae124-113">ミラー データベースとログ配布セカンダリ データベースをストアにSQL Serverします。</span><span class="sxs-lookup"><span data-stu-id="ae124-113">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>
    
2. <span data-ttu-id="ae124-114">常設チャット サーバー サービスのプロパティを次の内容に編集します。</span><span class="sxs-lookup"><span data-stu-id="ae124-114">Edit the Persistent Chat Server service properties to:</span></span>
    
    <span data-ttu-id="ae124-115">a. </span><span class="sxs-lookup"><span data-stu-id="ae124-115">a.</span></span> <span data-ttu-id="ae124-116">プライマリ データベースのミラーリングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ae124-116">Enable mirroring for the primary database.</span></span>
    
    <span data-ttu-id="ae124-117">b.</span><span class="sxs-lookup"><span data-stu-id="ae124-117">b.</span></span> <span data-ttu-id="ae124-118">プライマリ ミラー サーバー ストアSQL Serverします。</span><span class="sxs-lookup"><span data-stu-id="ae124-118">Add the primary mirror SQL Server store.</span></span>
    
    <span data-ttu-id="ae124-119">c.</span><span class="sxs-lookup"><span data-stu-id="ae124-119">c.</span></span> <span data-ttu-id="ae124-120">ログ配布SQL Server有効にする。</span><span class="sxs-lookup"><span data-stu-id="ae124-120">Enable the SQL Server Log Shipping database.</span></span>
    
    <span data-ttu-id="ae124-121">d. </span><span class="sxs-lookup"><span data-stu-id="ae124-121">d.</span></span> <span data-ttu-id="ae124-122">ログ配布SQL ServerストアにSQL Serverします。</span><span class="sxs-lookup"><span data-stu-id="ae124-122">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    <span data-ttu-id="ae124-123">e. </span><span class="sxs-lookup"><span data-stu-id="ae124-123">e.</span></span> <span data-ttu-id="ae124-124">セカンダリ データベースSQL Serverストア ミラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="ae124-124">Add the SQL Server store mirror for the secondary database.</span></span>
    
    <span data-ttu-id="ae124-125">f.</span><span class="sxs-lookup"><span data-stu-id="ae124-125">f.</span></span> <span data-ttu-id="ae124-126">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="ae124-126">Publish the topology.</span></span>
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="ae124-127">常設チャット SQL Serverデータベースのログ配布をセットアップする</span><span class="sxs-lookup"><span data-stu-id="ae124-127">Set up SQL Server log shipping for the Persistent Chat Server primary database</span></span>

<span data-ttu-id="ae124-128">このSQL Server Management Studio使用して、常設チャット サーバーのセカンダリ ログ配布データベース インスタンスに接続し、SQL Serverエージェントが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae124-128">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span> <span data-ttu-id="ae124-129">次に、常設チャットプライマリ データベース インスタンスに接続し、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ae124-129">Then connect to the Persistent Chat primary database instance and perform the following steps:</span></span>
  
1. <span data-ttu-id="ae124-130">mgc データベースを右クリックしてから、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae124-130">Right-click the mgc database, and then click **Properties**.</span></span>
    
2. <span data-ttu-id="ae124-131">[**ページの選択**] で、[**トランザクション ログの配布**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae124-131">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
3. <span data-ttu-id="ae124-132">[**ログ配布構成のプライマリ データベースとして有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="ae124-132">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
4. <span data-ttu-id="ae124-133">[**トランザクション ログのバックアップ**] で、[**バックアップの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae124-133">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
5. <span data-ttu-id="ae124-134">[バックアップ **フォルダーのネットワーク パス** ] ボックスに、トランザクション ログ バックアップ フォルダー用に作成した共有へのネットワーク パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="ae124-134">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>
    
6. <span data-ttu-id="ae124-135">バックアップ フォルダーがプライマリ サーバーにある場合は、[バックアップ フォルダーがプライマリ サーバーにある場合] にバックアップ フォルダーへのローカル パスを入力し、フォルダーへのローカル パス **(例: c:\backup)** ボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="ae124-135">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\backup)** box.</span></span> <span data-ttu-id="ae124-136">(バックアップ フォルダーがプライマリ サーバー上にない場合は、このボックスを空のままにできます)。</span><span class="sxs-lookup"><span data-stu-id="ae124-136">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ae124-137">プライマリ サーバーの SQL Server サービス アカウントがローカル システム アカウントで実行されている場合は、プライマリ サーバーにバックアップ フォルダーを作成し、そのフォルダーへのローカル パスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae124-137">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
7. <span data-ttu-id="ae124-138">[**次の期間を経過したファイルを削除する**] パラメーターと [**バックアップが次の期間内に行われない場合は警告する**] パラメーターを構成します。</span><span class="sxs-lookup"><span data-stu-id="ae124-138">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
8. <span data-ttu-id="ae124-139">[**バックアップ ジョブ**] の [**スケジュール**] ボックスに一覧表示されるバックアップ スケジュールを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ae124-139">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="ae124-140">インストールのスケジュールをカスタマイズするには、[スケジュール] **をクリックし**、必要に応SQL Serverエージェントのスケジュールを調整します。</span><span class="sxs-lookup"><span data-stu-id="ae124-140">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>
    
9. <span data-ttu-id="ae124-141">[ **圧縮] で**、[既定の **サーバー設定を使用する**] を選択し **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="ae124-141">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>
    
10. <span data-ttu-id="ae124-142">[**セカンダリ サーバー インスタンスとデータベース**] で、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae124-142">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
11. <span data-ttu-id="ae124-143">[ **接続** ] をクリックし、セカンダリ サーバー SQL Server構成したサーバーのインスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="ae124-143">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
12. <span data-ttu-id="ae124-144">[**セカンダリ データベース**] ボックスで、一覧から [**mgc**] データベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="ae124-144">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
13. <span data-ttu-id="ae124-145">[ **セカンダリ** データベースの初期化] タブで、[はい] オプションを選択し、プライマリ データベースの完全バックアップを生成し、セカンダリ データベースに復元 **します (** 存在しない場合はセカンダリ データベースを作成します)。</span><span class="sxs-lookup"><span data-stu-id="ae124-145">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>
    
14. <span data-ttu-id="ae124-146">[ファイル **のコピー** ] タブの[コピー先のファイル] フォルダーボックスに、トランザクション ログのバックアップをコピーするフォルダーのパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="ae124-146">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied.</span></span> <span data-ttu-id="ae124-147">多くの場合、このフォルダーは、セカンダリ サーバー上にあります。</span><span class="sxs-lookup"><span data-stu-id="ae124-147">This folder is often located on the secondary server.</span></span>
    
15. <span data-ttu-id="ae124-148">[ジョブのコピー] の [スケジュール] ボックスに **表示** されるコピー スケジュール **をメモします**。</span><span class="sxs-lookup"><span data-stu-id="ae124-148">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="ae124-149">インストールのスケジュールをカスタマイズするには、[スケジュール] **をクリックし**、必要に応SQL Serverエージェントのスケジュールを調整します。</span><span class="sxs-lookup"><span data-stu-id="ae124-149">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="ae124-150">このスケジュールは、バックアップ スケジュールとほぼ同じにしてください。</span><span class="sxs-lookup"><span data-stu-id="ae124-150">This schedule should be approximately the same as the backup schedule.</span></span>
    
16. <span data-ttu-id="ae124-151">[復元 **] タブ** の [バックアップ復元時 **のデータベース** の状態] で、[回復モードなし] **オプションを選択** します。</span><span class="sxs-lookup"><span data-stu-id="ae124-151">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>
    
17. <span data-ttu-id="ae124-152">[**バックアップの復元の遅延] で、少なくとも [0\*\*\*\*分] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ae124-152">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>
    
18. <span data-ttu-id="ae124-153">Choose an alert threshold under **Alert if no restore occurs within**.</span><span class="sxs-lookup"><span data-stu-id="ae124-153">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>
    
19. <span data-ttu-id="ae124-154">[復元ジョブ] の [スケジュール] ボックスに **一** 覧表示されている復元スケジュール **を確認します**。</span><span class="sxs-lookup"><span data-stu-id="ae124-154">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="ae124-155">インストールのスケジュールをカスタマイズするには、[スケジュール]をクリックし、必要に応じて SQL Server エージェントのスケジュールを調整し **、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae124-155">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="ae124-156">このスケジュールは、バックアップ スケジュールとほぼ同じにしてください。</span><span class="sxs-lookup"><span data-stu-id="ae124-156">This schedule should be approximately the same as the backup schedule.</span></span>
    
20. <span data-ttu-id="ae124-157">[データベースの **プロパティ] ダイアログ** ボックスで **、[OK]** をクリックして構成プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="ae124-157">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a><span data-ttu-id="ae124-158">プライマリ ミラー SQL Serverセカンダリ データベース間のログ配布をセットアップする</span><span class="sxs-lookup"><span data-stu-id="ae124-158">Set up SQL Server log shipping between the primary mirror and the secondary database</span></span>

<span data-ttu-id="ae124-159">プライマリ常設チャット データベースがミラー データベースにフェールオーバーされた場合にログ配布を続行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ae124-159">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>
  
1. <span data-ttu-id="ae124-160">プライマリ 常設チャット データベースを手動でミラーにフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="ae124-160">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="ae124-161">これは、Skype for Business Server 管理シェルと **Invoke-CsDatabaseFailover コマンドレットを使用して行** います。</span><span class="sxs-lookup"><span data-stu-id="ae124-161">This is done by using the Skype for Business Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    
2. <span data-ttu-id="ae124-162">新しいSQL Server Management Studio使用して、プライマリ常設チャット サーバー ミラー インスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="ae124-162">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>
    
3. <span data-ttu-id="ae124-163">エージェントが実行SQL Server確認します。</span><span class="sxs-lookup"><span data-stu-id="ae124-163">Be sure that the SQL Server Agent is running.</span></span>
    
4. <span data-ttu-id="ae124-164">mgc データベースを右クリックしてから、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae124-164">Right-click the mgc database, and then click **Properties**.</span></span>
    
5. <span data-ttu-id="ae124-165">[**ページの選択**] で、[**トランザクション ログの配布**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae124-165">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
6. <span data-ttu-id="ae124-166">[**ログ配布構成のプライマリ データベースとして有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="ae124-166">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
7. <span data-ttu-id="ae124-167">[**トランザクション ログのバックアップ**] で、[**バックアップの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae124-167">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
8. <span data-ttu-id="ae124-168">[**バックアップ フォルダーのネットワーク パスを指定する**] ボックスに、トランザクション ログのバックアップ フォルダーとして作成した共有場所へのネットワーク パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="ae124-168">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>
    
9. <span data-ttu-id="ae124-p116">バックアップ フォルダーがプライマリ サーバーに存在する場合は、[**バックアップ フォルダーがプライマリ サーバーに存在する場合は、バックアップ フォルダーのローカル パスを入力**] ボックスにバックアップ フォルダーへのローカル パスを入力します (バックアップ フォルダーがプライマリ サーバーに存在しない場合は、このボックスを空のままにします)。</span><span class="sxs-lookup"><span data-stu-id="ae124-p116">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ae124-171">プライマリ サーバーの SQL Server サービス アカウントがローカル システム アカウントで実行されている場合は、プライマリ サーバーにバックアップ フォルダーを作成し、そのフォルダーへのローカル パスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae124-171">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
10. <span data-ttu-id="ae124-172">[**次の期間を経過したファイルを削除する**] パラメーターと [**バックアップが次の期間内に行われない場合は警告する**] パラメーターを構成します。</span><span class="sxs-lookup"><span data-stu-id="ae124-172">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
11. <span data-ttu-id="ae124-173">[**バックアップ ジョブ**] の [**スケジュール**] ボックスに一覧表示されるバックアップ スケジュールを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ae124-173">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="ae124-174">インストールのスケジュールをカスタマイズするには、[スケジュール] **をクリックし**、必要に応SQL Serverエージェントのスケジュールを調整します。</span><span class="sxs-lookup"><span data-stu-id="ae124-174">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ae124-175">プライマリ データベースと同じ設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="ae124-175">Use the same settings that you used for the primary database.</span></span> 
  
12. <span data-ttu-id="ae124-176">[**圧縮**] で、[**既定のサーバー設定を使用する**] をクリックして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae124-176">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>
    
13. <span data-ttu-id="ae124-177">[**セカンダリ サーバー インスタンスとデータベース**] で、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae124-177">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
14. <span data-ttu-id="ae124-178">[**接続**] をクリックして、セカンダリ サーバーとして構成した SQL Server のインスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="ae124-178">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
15. <span data-ttu-id="ae124-179">[**セカンダリ データベース**] ボックスで、一覧から [**mgc**] データベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="ae124-179">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
16. <span data-ttu-id="ae124-180">[**セカンダリ データベースの初期化**] タブで、[**いいえ、セカンダリ データベースは初期化されています**] オプションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae124-180">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>
    
17. <span data-ttu-id="ae124-p118">[**ファイルのコピー**] タブの [**ファイルのコピー先フォルダー**] に、トランザクション ログのバックアップをコピーするフォルダーのパスを入力して、[**OK**] をクリックします。多くの場合、このフォルダーは、セカンダリ サーバー上にあります。</span><span class="sxs-lookup"><span data-stu-id="ae124-p118">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**. This folder is often located on the secondary server.</span></span>
    
18. <span data-ttu-id="ae124-183">[**スクリプトの構成**] ドロップダウン リストを開き、[**スクリプト構成を新規クエリ ウィンドウに保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae124-183">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>
    
19. <span data-ttu-id="ae124-184">[**データベースのプロパティ**] に表示された新規クエリ ウィンドウで [**OK**] をクリックして、構成プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="ae124-184">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>
    
20. <span data-ttu-id="ae124-185">クエリの前半 (手順 18 を参照) を選択して実行します。-- End: プライマリで実行する \* \* \* \* \* \* スクリプト: \* \* \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="ae124-185">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ae124-186">このスクリプトを手動で実行するSQL Server Management Studioログ配布構成で複数のプライマリ データベースをサポートSQL Server必要です。</span><span class="sxs-lookup"><span data-stu-id="ae124-186">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span> 
  
21. <span data-ttu-id="ae124-187">[**キャンセル**] をクリックして、ログ配布構成パネルを閉じ、(フェールオーバー時に) プライマリ データベースとミラー化されたデータベース両方でログ配布を適切に実装する実用的なセットアップを確立します。</span><span class="sxs-lookup"><span data-stu-id="ae124-187">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>
    
22. <span data-ttu-id="ae124-188">プライマリ常設チャット データベースをプライマリに手動でフェールバックします。</span><span class="sxs-lookup"><span data-stu-id="ae124-188">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="ae124-189">これは、Skype for Business Server 管理シェルと **Invoke-CsDatabaseFailover** コマンドレットを使用して行います。</span><span class="sxs-lookup"><span data-stu-id="ae124-189">This is done by using the Skype for Business Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    

