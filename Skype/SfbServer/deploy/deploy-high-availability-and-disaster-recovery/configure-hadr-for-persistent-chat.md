---
title: Skype for Business Server 2015 での常設チャット サーバーの高可用性および障害復旧の構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: '概要: このトピックでは、Skype for Business Server 2015 で常設チャットサーバーの高可用性と障害回復を構成する方法について説明します。'
ms.openlocfilehash: a771479eccc88c6ff30864a44649fe3d309a7ca2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298487"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="bf20c-103">Skype for Business Server 2015 での常設チャット サーバーの高可用性および障害復旧の構成</span><span class="sxs-lookup"><span data-stu-id="bf20c-103">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="bf20c-104">**概要:** このトピックでは、Skype for Business Server 2015 で常設チャットサーバーの高可用性と障害回復を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bf20c-104">**Summary:** Read this topic to learn how to configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="bf20c-105">Skype for Business Server では、データベースミラーリングなど、バックエンドサーバーでの高可用性の複数のモードがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="bf20c-105">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="bf20c-106">詳細については、「[Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf20c-106">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="bf20c-107">AlwaysOn 可用性グループは、常設チャットサーバーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="bf20c-107">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="bf20c-108">高可用性と障害回復のための常設チャットの展開を構成する前に、「 [Skype For Business server 2015 の常設チャットサーバーの高可用性と障害回復の計画](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md)」の概念に精通していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="bf20c-108">Before you configure your Persistent Chat deployment for high availability and disaster recovery, be sure you are familiar with the concepts in [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="bf20c-109">これらのトピックで説明する常設チャットサーバーの障害回復ソリューションは、ストレッチされた常設チャットサーバープールに基づいています。</span><span class="sxs-lookup"><span data-stu-id="bf20c-109">The disaster recovery solution for Persistent Chat Server described in these topics is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="bf20c-110">計画コンテンツでは、リソース要件と、SQL Server ミラーリングを使用して高可用性と障害回復を実現している、常設チャットサーバーの高可用性と災害復旧を可能にする拡張プールトポロジを示しています。障害回復。</span><span class="sxs-lookup"><span data-stu-id="bf20c-110">The planning content describes resource requirements, and the stretched pool topology that enables high availability and disaster recovery for Persistent Chat Server, including using SQL Server mirroring for high availability and SQL Server log shipping for disaster recovery.</span></span>
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a><span data-ttu-id="bf20c-111">トポロジ ビルダーを使用して高可用性と障害復旧を構成する</span><span class="sxs-lookup"><span data-stu-id="bf20c-111">Use Topology Builder to configure high availability and disaster recovery</span></span>

<span data-ttu-id="bf20c-112">トポロジ ビルダーで、次の手順に従って常設チャット サーバーのための高可用性と障害復旧を構成します。</span><span class="sxs-lookup"><span data-stu-id="bf20c-112">Within Topology Builder, perform the following steps to configure high availability and disaster recovery for Persistent Chat Server.</span></span>
  
1. <span data-ttu-id="bf20c-113">ミラーデータベースとログ配布のセカンダリデータベース SQL Server ストアを追加します。</span><span class="sxs-lookup"><span data-stu-id="bf20c-113">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>
    
2. <span data-ttu-id="bf20c-114">常設チャットサーバーサービスのプロパティを編集するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="bf20c-114">Edit the Persistent Chat Server service properties to:</span></span>
    
    <span data-ttu-id="bf20c-115">a.</span><span class="sxs-lookup"><span data-stu-id="bf20c-115">a.</span></span> <span data-ttu-id="bf20c-116">プライマリ データベースのミラーリングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="bf20c-116">Enable mirroring for the primary database.</span></span>
    
    <span data-ttu-id="bf20c-117">b.</span><span class="sxs-lookup"><span data-stu-id="bf20c-117">b.</span></span> <span data-ttu-id="bf20c-118">プライマリミラー SQL Server ストアを追加します。</span><span class="sxs-lookup"><span data-stu-id="bf20c-118">Add the primary mirror SQL Server store.</span></span>
    
    <span data-ttu-id="bf20c-119">c.</span><span class="sxs-lookup"><span data-stu-id="bf20c-119">c.</span></span> <span data-ttu-id="bf20c-120">SQL Server のログ配布データベースを有効にします。</span><span class="sxs-lookup"><span data-stu-id="bf20c-120">Enable the SQL Server Log Shipping database.</span></span>
    
    <span data-ttu-id="bf20c-121">d.</span><span class="sxs-lookup"><span data-stu-id="bf20c-121">d.</span></span> <span data-ttu-id="bf20c-122">SQL Server ログ配布のセカンダリ SQL Server ストアを追加します。</span><span class="sxs-lookup"><span data-stu-id="bf20c-122">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    <span data-ttu-id="bf20c-123">•.</span><span class="sxs-lookup"><span data-stu-id="bf20c-123">e.</span></span> <span data-ttu-id="bf20c-124">セカンダリデータベースの SQL Server ストアミラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="bf20c-124">Add the SQL Server store mirror for the secondary database.</span></span>
    
    <span data-ttu-id="bf20c-125">f.</span><span class="sxs-lookup"><span data-stu-id="bf20c-125">f.</span></span> <span data-ttu-id="bf20c-126">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="bf20c-126">Publish the topology.</span></span>
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="bf20c-127">常設チャット サーバーのプライマリ データベースの SQL Server ログ配布を設定する</span><span class="sxs-lookup"><span data-stu-id="bf20c-127">Set up SQL Server log shipping for the Persistent Chat Server primary database</span></span>

<span data-ttu-id="bf20c-128">SQL Server Management Studio を使用して、常設チャットサーバーセカンダリログ配布データベースインスタンスに接続し、SQL Server エージェントが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bf20c-128">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span> <span data-ttu-id="bf20c-129">次に、常設チャットプライマリデータベースインスタンスに接続し、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bf20c-129">Then connect to the Persistent Chat primary database instance and perform the following steps:</span></span>
  
1. <span data-ttu-id="bf20c-130">mgc データベースを右クリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf20c-130">Right-click the mgc database, and then click **Properties**.</span></span>
    
2. <span data-ttu-id="bf20c-131">[**ページの選択**] で、[**トランザクション ログの配布**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf20c-131">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
3. <span data-ttu-id="bf20c-132">[**ログ配布構成のプライマリ データベースとして有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="bf20c-132">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
4. <span data-ttu-id="bf20c-133">[**トランザクション ログのバックアップ**] で、[**バックアップの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf20c-133">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
5. <span data-ttu-id="bf20c-134">[**バックアップ フォルダーのネットワーク パスを指定する**] ボックスに、トランザクション ログのバックアップ用に作成した共有フォルダーへのネットワーク パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="bf20c-134">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>
    
6. <span data-ttu-id="bf20c-p110">バックアップ フォルダーがプライマリ サーバーに存在する場合は、[**バックアップ フォルダーがプライマリ サーバーに存在する場合は、バックアップ フォルダーのローカル パスを入力 (例: c:\backup)**] ボックスにバックアップ フォルダーのローカル パスを入力します (バックアップ フォルダーがプライマリ サーバーに存在しない場合は、このボックスを空のままにします)。</span><span class="sxs-lookup"><span data-stu-id="bf20c-p110">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\backup)** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="bf20c-137">プライマリサーバーの SQL Server サービスアカウントがローカルシステムアカウントで実行されている場合は、プライマリサーバー上にバックアップフォルダーを作成し、そのフォルダーへのローカルパスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf20c-137">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
7. <span data-ttu-id="bf20c-138">[**次の期間を経過したファイルを削除する**] パラメーターと [**バックアップが次の期間内に行われない場合は警告する**] パラメーターを構成します。</span><span class="sxs-lookup"><span data-stu-id="bf20c-138">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
8. <span data-ttu-id="bf20c-139">[**バックアップ ジョブ**] の [**スケジュール**] ボックスに一覧表示されるバックアップ スケジュールを確認してください。</span><span class="sxs-lookup"><span data-stu-id="bf20c-139">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="bf20c-140">インストールのスケジュールをカスタマイズするには、[**スケジュール**] をクリックし、必要に応じて SQL Server エージェントのスケジュールを調整します。</span><span class="sxs-lookup"><span data-stu-id="bf20c-140">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>
    
9. <span data-ttu-id="bf20c-141">[**圧縮**] の [**既定のサーバー設定を使用する**] を選択し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf20c-141">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>
    
10. <span data-ttu-id="bf20c-142">[**セカンダリ サーバー インスタンスとデータベース**] で、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf20c-142">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
11. <span data-ttu-id="bf20c-143">[**接続**] をクリックし、セカンダリサーバーとして構成した SQL Server のインスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="bf20c-143">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
12. <span data-ttu-id="bf20c-144">[**セカンダリ データベース**] ボックスで、一覧から [**mgc**] データベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="bf20c-144">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
13. <span data-ttu-id="bf20c-145">[**セカンダリ データベースの初期化**] タブで、[**はい、プライマリ データベースの完全バックアップを生成して、セカンダリ データベースに復元します**] オプションを選択します (また、セカンダリ データベースが存在しない場合は作成します)。</span><span class="sxs-lookup"><span data-stu-id="bf20c-145">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>
    
14. <span data-ttu-id="bf20c-p112">[**ファイルのコピー**] タブの [**ファイルのコピー先フォルダー**] ボックスに、トランザクション ログのバックアップのコピー先フォルダーのパスを入力します。このフォルダーは通常はセカンダリ サーバー上にあります。</span><span class="sxs-lookup"><span data-stu-id="bf20c-p112">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied. This folder is often located on the secondary server.</span></span>
    
15. <span data-ttu-id="bf20c-148">[**コピー ジョブ**] の [**スケジュール**] ボックスに一覧表示されるコピー スケジュールを確認します。</span><span class="sxs-lookup"><span data-stu-id="bf20c-148">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="bf20c-149">インストールのスケジュールをカスタマイズするには、[**スケジュール**] をクリックし、必要に応じて SQL Server エージェントのスケジュールを調整します。</span><span class="sxs-lookup"><span data-stu-id="bf20c-149">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="bf20c-150">このスケジュールは、バックアップ スケジュールとよく似た内容にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf20c-150">This schedule should be approximately the same as the backup schedule.</span></span>
    
16. <span data-ttu-id="bf20c-151">[**復元**] タブの [**バックアップ復元時のデータベース状態**] で、[**復旧モードなし**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="bf20c-151">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>
    
17. <span data-ttu-id="bf20c-152">[**バックアップの復元を最低限次の期間遅延する**] で [**0 分**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bf20c-152">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>
    
18. <span data-ttu-id="bf20c-153">[**復元が次の期間内に行われない場合は警告する**] で警告のしきい値を選択します。</span><span class="sxs-lookup"><span data-stu-id="bf20c-153">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>
    
19. <span data-ttu-id="bf20c-154">[**復元ジョブ**] の [**スケジュール**] ボックスに一覧表示される復元スケジュールを確認します。</span><span class="sxs-lookup"><span data-stu-id="bf20c-154">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="bf20c-155">インストールのスケジュールをカスタマイズするには、[**スケジュール**] をクリックし、必要に応じて SQL Server エージェントのスケジュールを調整して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf20c-155">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="bf20c-156">このスケジュールは、バックアップ スケジュールとよく似た内容にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf20c-156">This schedule should be approximately the same as the backup schedule.</span></span>
    
20. <span data-ttu-id="bf20c-157">[**データベースのプロパティ**] ダイアログ ボックスで、[**OK**] をクリックして構成のプロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="bf20c-157">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a><span data-ttu-id="bf20c-158">プライマリ ミラーとセカンダリ データベースとの間の SQL Server ログ配布をセットアップする</span><span class="sxs-lookup"><span data-stu-id="bf20c-158">Set up SQL Server log shipping between the primary mirror and the secondary database</span></span>

<span data-ttu-id="bf20c-159">プライマリ常設チャットデータベースがミラーデータベースにフェールオーバーされた場合は、次の手順に従ってログの配布を続行します。</span><span class="sxs-lookup"><span data-stu-id="bf20c-159">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>
  
1. <span data-ttu-id="bf20c-160">プライマリ永続的チャットデータベースをミラーに手動でフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="bf20c-160">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="bf20c-161">これを行うには、Skype for Business Server 管理シェルと**Invoke-CsDatabaseFailover**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="bf20c-161">This is done by using the Skype for Business Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    
2. <span data-ttu-id="bf20c-162">SQL Server Management Studio を使用して、プライマリ常設チャットサーバーのミラーインスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="bf20c-162">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>
    
3. <span data-ttu-id="bf20c-163">SQL Server エージェントが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bf20c-163">Be sure that the SQL Server Agent is running.</span></span>
    
4. <span data-ttu-id="bf20c-164">mgc データベースを右クリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf20c-164">Right-click the mgc database, and then click **Properties**.</span></span>
    
5. <span data-ttu-id="bf20c-165">[**ページの選択**] で、[**トランザクション ログの配布**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf20c-165">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
6. <span data-ttu-id="bf20c-166">[**ログ配布構成のプライマリ データベースとして有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="bf20c-166">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
7. <span data-ttu-id="bf20c-167">[**トランザクション ログのバックアップ**] で、[**バックアップの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf20c-167">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
8. <span data-ttu-id="bf20c-168">[**バックアップ フォルダーのネットワーク パスを指定する**] ボックスに、トランザクション ログのバックアップ フォルダーとして作成した共有場所へのネットワーク パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="bf20c-168">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>
    
9. <span data-ttu-id="bf20c-p116">バックアップ フォルダーがプライマリ サーバーに存在する場合は、[**バックアップ フォルダーがプライマリ サーバーに存在する場合は、バックアップ フォルダーのローカル パスを入力**] ボックスにバックアップ フォルダーのローカル パスを入力します (バックアップ フォルダーがプライマリ サーバーに存在しない場合は、このボックスを空のままにします)。</span><span class="sxs-lookup"><span data-stu-id="bf20c-p116">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="bf20c-171">プライマリサーバーの SQL Server サービスアカウントがローカルシステムアカウントで実行されている場合は、プライマリサーバー上にバックアップフォルダーを作成し、そのフォルダーへのローカルパスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf20c-171">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
10. <span data-ttu-id="bf20c-172">[**次の期間を経過したファイルを削除する**] パラメーターと [**バックアップが次の期間内に行われない場合は警告する**] パラメーターを構成します。</span><span class="sxs-lookup"><span data-stu-id="bf20c-172">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
11. <span data-ttu-id="bf20c-173">[**バックアップ ジョブ**] の [**スケジュール**] ボックスに一覧表示されるバックアップ スケジュールを確認してください。</span><span class="sxs-lookup"><span data-stu-id="bf20c-173">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="bf20c-174">インストールのスケジュールをカスタマイズするには、[**スケジュール**] をクリックし、必要に応じて SQL Server エージェントのスケジュールを調整します。</span><span class="sxs-lookup"><span data-stu-id="bf20c-174">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="bf20c-175">プライマリ データベースと同じ設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="bf20c-175">Use the same settings that you used for the primary database.</span></span> 
  
12. <span data-ttu-id="bf20c-176">[**圧縮**] で、[**既定のサーバー設定を使用する**] をクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf20c-176">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>
    
13. <span data-ttu-id="bf20c-177">[**セカンダリ サーバー インスタンスとデータベース**] で、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf20c-177">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
14. <span data-ttu-id="bf20c-178">[**接続**] をクリックして、セカンダリ サーバーとして構成した SQL Server のインスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="bf20c-178">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
15. <span data-ttu-id="bf20c-179">[**セカンダリ データベース**] ボックスで、一覧から [**mgc**] データベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="bf20c-179">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
16. <span data-ttu-id="bf20c-180">[**セカンダリ データベースの初期化**] タブで、[**いいえ、セカンダリ データベースは初期化されています**] オプションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf20c-180">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>
    
17. <span data-ttu-id="bf20c-p118">[**ファイルのコピー**] タブの [**ファイルのコピー先フォルダー**] に、トランザクション ログのバックアップをコピーするフォルダーのパスを入力して、[**OK**] をクリックします。多くの場合、このフォルダーは、セカンダリ サーバー上にあります。</span><span class="sxs-lookup"><span data-stu-id="bf20c-p118">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**. This folder is often located on the secondary server.</span></span>
    
18. <span data-ttu-id="bf20c-183">[**スクリプトの構成**] ボックスの一覧を開き、[**スクリプト構成を新規クエリ ウィンドウに保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf20c-183">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>
    
19. <span data-ttu-id="bf20c-184">[**データベースのプロパティ**] に表示された新規クエリ ウィンドウで [**OK**] をクリックして、構成プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="bf20c-184">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>
    
20. <span data-ttu-id="bf20c-185">クエリの最初の半分 (手順18を参照) を選んで実行します。--- \* \* \* \* \* \* --------- \* \* \* \* \* \*---------------------------</span><span class="sxs-lookup"><span data-stu-id="bf20c-185">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="bf20c-186">Sql Server Management Studio では、SQL Server のログ配布構成で複数のプライマリデータベースがサポートされていないため、このスクリプトを手動で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf20c-186">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span> 
  
21. <span data-ttu-id="bf20c-187">[**キャンセル**] をクリックして、ログ配布構成パネルを閉じ、プライマリ データベースとミラー化されたデータベース (フェールオーバー時) の両方でログ ファイルの配布を適切に実装する実用的なセットアップを確立します。 </span><span class="sxs-lookup"><span data-stu-id="bf20c-187">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>
    
22. <span data-ttu-id="bf20c-188">プライマリ常設チャットデータベースを手動でプライマリにフェールバックします。</span><span class="sxs-lookup"><span data-stu-id="bf20c-188">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="bf20c-189">これを行うには、Skype for Business Server 管理シェルと**Invoke-CsDatabaseFailover**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="bf20c-189">This is done by using the Skype for Business Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    

