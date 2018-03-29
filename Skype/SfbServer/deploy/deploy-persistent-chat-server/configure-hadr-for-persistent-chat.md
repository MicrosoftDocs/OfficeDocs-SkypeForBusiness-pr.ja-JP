---
title: Skype for Business Server 2015 での常設チャット サーバーの高可用性および障害復旧の構成
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: '概要: ビジネス サーバー 2015 の Skype での永続的なチャット サーバーの高可用性と障害回復を構成する方法の詳細については、このトピックを読みます。'
ms.openlocfilehash: f0bf1a98bb8967a7310844d9aa85d17d4ef4d167
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="dbef4-103">Skype for Business Server 2015 での常設チャット サーバーの高可用性および障害復旧の構成</span><span class="sxs-lookup"><span data-stu-id="dbef4-103">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="dbef4-104">**の概要:**ビジネス サーバー 2015 の Skype での永続的なチャット サーバーの高可用性と障害回復を構成する方法の詳細については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbef4-104">**Summary:** Read this topic to learn how to configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="dbef4-105">ビジネス サーバー用の Skype は、バック エンド サーバー、データベース ・ ミラーリングなどの複数の高可用性モードをサポートします。</span><span class="sxs-lookup"><span data-stu-id="dbef4-105">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="dbef4-106">詳細については、[高可用性とビジネス サーバー 2015 の Skype での災害復旧の計画](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbef4-106">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="dbef4-107">AlwaysOn 可用性グループは、永続的なチャット サーバーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="dbef4-107">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="dbef4-108">高可用性と災害復旧について、永続的なチャットの展開を構成する前に、[高可用性とビジネス サーバー 2015 の Skype での永続的なチャット サーバーの障害回復の計画](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md)の概念に精通していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dbef4-108">Before you configure your Persistent Chat deployment for high availability and disaster recovery, be sure you are familiar with the concepts in [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="dbef4-109">拡大された永続的なチャット サーバー プールの永続的なチャット サーバーがこれらのトピックで説明されている災害復旧ソリューションがビルドされます。</span><span class="sxs-lookup"><span data-stu-id="dbef4-109">The disaster recovery solution for Persistent Chat Server described in these topics is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="dbef4-110">計画の内容は、リソース要件、および永続的なチャット サーバーは、SQL Server のミラーリングを使用して、高い可用性と SQL Server のログ配布を含む、高可用性と災害復旧を可能にする拡大されたプール トポロジについて説明します。災害復旧します。</span><span class="sxs-lookup"><span data-stu-id="dbef4-110">The planning content describes resource requirements, and the stretched pool topology that enables high availability and disaster recovery for Persistent Chat Server, including using SQL Server mirroring for high availability and SQL Server log shipping for disaster recovery.</span></span>
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a><span data-ttu-id="dbef4-111">トポロジ ビルダーを使用して高可用性と障害復旧を構成する</span><span class="sxs-lookup"><span data-stu-id="dbef4-111">Use Topology Builder to configure high availability and disaster recovery</span></span>

<span data-ttu-id="dbef4-112">トポロジ ビルダーで、次の手順に従って常設チャット サーバーのための高可用性と障害復旧を構成します。</span><span class="sxs-lookup"><span data-stu-id="dbef4-112">Within Topology Builder, perform the following steps to configure high availability and disaster recovery for Persistent Chat Server.</span></span>
  
1. <span data-ttu-id="dbef4-113">ミラー データベースとログ配布セカンダリ データベースの SQL Server の格納を追加します。</span><span class="sxs-lookup"><span data-stu-id="dbef4-113">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>
    
2. <span data-ttu-id="dbef4-114">永続的なチャット サーバー サービスのプロパティを編集します。</span><span class="sxs-lookup"><span data-stu-id="dbef4-114">Edit the Persistent Chat Server service properties to:</span></span>
    
    <span data-ttu-id="dbef4-115">a.</span><span class="sxs-lookup"><span data-stu-id="dbef4-115">a.</span></span> <span data-ttu-id="dbef4-116">プライマリ データベースのミラーリングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="dbef4-116">Enable mirroring for the primary database.</span></span>
    
    <span data-ttu-id="dbef4-117">b.</span><span class="sxs-lookup"><span data-stu-id="dbef4-117">b.</span></span> <span data-ttu-id="dbef4-118">プライマリ ・ ミラーの SQL Server ストアを追加します。</span><span class="sxs-lookup"><span data-stu-id="dbef4-118">Add the primary mirror SQL Server store.</span></span>
    
    <span data-ttu-id="dbef4-119">c.</span><span class="sxs-lookup"><span data-stu-id="dbef4-119">c.</span></span> <span data-ttu-id="dbef4-120">SQL Server のログ配布のデータベースを有効にします。</span><span class="sxs-lookup"><span data-stu-id="dbef4-120">Enable the SQL Server Log Shipping database.</span></span>
    
    <span data-ttu-id="dbef4-121">d.</span><span class="sxs-lookup"><span data-stu-id="dbef4-121">d.</span></span> <span data-ttu-id="dbef4-122">SQL Server のログ配布のセカンダリ SQL Server ストアを追加します。</span><span class="sxs-lookup"><span data-stu-id="dbef4-122">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    <span data-ttu-id="dbef4-123">e。</span><span class="sxs-lookup"><span data-stu-id="dbef4-123">e.</span></span> <span data-ttu-id="dbef4-124">セカンダリ データベースの SQL Server ストアのミラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="dbef4-124">Add the SQL Server store mirror for the secondary database.</span></span>
    
    <span data-ttu-id="dbef4-125">f。</span><span class="sxs-lookup"><span data-stu-id="dbef4-125">f.</span></span> <span data-ttu-id="dbef4-126">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="dbef4-126">Publish the topology.</span></span>
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="dbef4-127">常設チャット サーバーのプライマリ データベースの SQL Server ログ配布を設定する</span><span class="sxs-lookup"><span data-stu-id="dbef4-127">Set up SQL Server log shipping for the Persistent Chat Server primary database</span></span>

<span data-ttu-id="dbef4-128">SQL Server Management Studio を使用すると、永続的なチャット サーバー セカンダリ ログ配布のデータベースのインスタンスに接続し、SQL Server エージェントが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dbef4-128">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span> <span data-ttu-id="dbef4-129">プライマリ ・ データベースの永続的なチャット インスタンスに接続し、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="dbef4-129">Then connect to the Persistent Chat primary database instance and perform the following steps:</span></span>
  
1. <span data-ttu-id="dbef4-130">mgc データベースを右クリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbef4-130">Right-click the mgc database, and then click **Properties**.</span></span>
    
2. <span data-ttu-id="dbef4-131">[**ページの選択**] で、[**トランザクション ログの配布**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbef4-131">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
3. <span data-ttu-id="dbef4-132">[**ログ配布構成のプライマリ データベースとして有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="dbef4-132">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
4. <span data-ttu-id="dbef4-133">[**トランザクション ログのバックアップ**] で、[**バックアップの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbef4-133">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
5. <span data-ttu-id="dbef4-134">[**バックアップ フォルダーのネットワーク パスを指定する**] ボックスに、トランザクション ログのバックアップ用に作成した共有フォルダーへのネットワーク パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="dbef4-134">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>
    
6. <span data-ttu-id="dbef4-p110">バックアップ フォルダーがプライマリ サーバーに存在する場合は、[**バックアップ フォルダーがプライマリ サーバーに存在する場合は、バックアップ フォルダーのローカル パスを入力 (例: c:\backup)**] ボックスにバックアップ フォルダーのローカル パスを入力します (バックアップ フォルダーがプライマリ サーバーに存在しない場合は、このボックスを空のままにします)。</span><span class="sxs-lookup"><span data-stu-id="dbef4-p110">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\backup)** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="dbef4-137">プライマリ サーバー上の SQL Server サービス アカウントは、ローカル システム アカウントで実行する場合は、プライマリ サーバーで、バックアップ フォルダーを作成し、そのフォルダーのローカル パスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbef4-137">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
7. <span data-ttu-id="dbef4-138">[**次の期間を経過したファイルを削除する**] パラメーターと [**バックアップが次の期間内に行われない場合は警告する**] パラメーターを構成します。</span><span class="sxs-lookup"><span data-stu-id="dbef4-138">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
8. <span data-ttu-id="dbef4-139">[**バックアップ ジョブ**] の [**スケジュール**] ボックスに一覧表示されるバックアップ スケジュールを確認してください。</span><span class="sxs-lookup"><span data-stu-id="dbef4-139">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="dbef4-140">インストールのスケジュールをカスタマイズするには、**スケジュール**] をクリックし、必要に応じて SQL Server エージェントのスケジュールを調整します。</span><span class="sxs-lookup"><span data-stu-id="dbef4-140">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>
    
9. <span data-ttu-id="dbef4-141">[**圧縮**] の [**既定のサーバー設定を使用する**] を選択し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbef4-141">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>
    
10. <span data-ttu-id="dbef4-142">[**セカンダリ サーバー インスタンスとデータベース**] で、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbef4-142">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
11. <span data-ttu-id="dbef4-143">[**接続**] をクリックし、セカンダリ サーバーとして構成した SQL Server のインスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="dbef4-143">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
12. <span data-ttu-id="dbef4-144">[**セカンダリ データベース**] ボックスで、一覧から [**mgc**] データベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="dbef4-144">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
13. <span data-ttu-id="dbef4-145">[**セカンダリ データベースの初期化**] タブで、[**はい、プライマリ データベースの完全バックアップを生成して、セカンダリ データベースに復元します**] オプションを選択します (また、セカンダリ データベースが存在しない場合は作成します)。</span><span class="sxs-lookup"><span data-stu-id="dbef4-145">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>
    
14. <span data-ttu-id="dbef4-p112">[**ファイルのコピー**] タブの [**ファイルのコピー先フォルダー**] ボックスに、トランザクション ログのバックアップのコピー先フォルダーのパスを入力します。このフォルダーは通常はセカンダリ サーバー上にあります。</span><span class="sxs-lookup"><span data-stu-id="dbef4-p112">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied. This folder is often located on the secondary server.</span></span>
    
15. <span data-ttu-id="dbef4-148">[**コピー ジョブ**] の [**スケジュール**] ボックスに一覧表示されるコピー スケジュールを確認します。</span><span class="sxs-lookup"><span data-stu-id="dbef4-148">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="dbef4-149">インストールのスケジュールをカスタマイズするには、**スケジュール**] をクリックし、必要に応じて SQL Server エージェントのスケジュールを調整します。</span><span class="sxs-lookup"><span data-stu-id="dbef4-149">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="dbef4-150">このスケジュールは、バックアップ スケジュールとよく似た内容にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbef4-150">This schedule should be approximately the same as the backup schedule.</span></span>
    
16. <span data-ttu-id="dbef4-151">[**復元**] タブの [**バックアップ復元時のデータベース状態**] で、[**復旧モードなし**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="dbef4-151">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>
    
17. <span data-ttu-id="dbef4-152">[**バックアップの復元を最低限次の期間遅延する**] で [**0 分**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbef4-152">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>
    
18. <span data-ttu-id="dbef4-153">[**復元が次の期間内に行われない場合は警告する**] で警告のしきい値を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbef4-153">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>
    
19. <span data-ttu-id="dbef4-154">[**復元ジョブ**] の [**スケジュール**] ボックスに一覧表示される復元スケジュールを確認します。</span><span class="sxs-lookup"><span data-stu-id="dbef4-154">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="dbef4-155">インストールのスケジュールをカスタマイズするには、[**スケジュール**] をクリックして**]**を必要に応じて、SQL Server エージェントのスケジュールを調整します。</span><span class="sxs-lookup"><span data-stu-id="dbef4-155">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="dbef4-156">このスケジュールは、バックアップ スケジュールとよく似た内容にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbef4-156">This schedule should be approximately the same as the backup schedule.</span></span>
    
20. <span data-ttu-id="dbef4-157">[**データベースのプロパティ**] ダイアログ ボックスで、[**OK**] をクリックして構成のプロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="dbef4-157">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a><span data-ttu-id="dbef4-158">プライマリ ミラーとセカンダリ データベースとの間の SQL Server ログ配布をセットアップする</span><span class="sxs-lookup"><span data-stu-id="dbef4-158">Set up SQL Server log shipping between the primary mirror and the secondary database</span></span>

<span data-ttu-id="dbef4-159">ログ配布のプライマリの永続的なチャットのデータベースは、ミラー データベースにフェールオーバーしているかを続行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="dbef4-159">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>
  
1. <span data-ttu-id="dbef4-160">手動でミラーを永続的なチャットのプライマリ データベースにフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="dbef4-160">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="dbef4-161">これは、Skype をビジネス サーバー管理シェルを**呼び出し CsDatabaseFailover**コマンドレットを使用して行われます。</span><span class="sxs-lookup"><span data-stu-id="dbef4-161">This is done by using the Skype for Business Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    
2. <span data-ttu-id="dbef4-162">SQL Server Management Studio を使用すると、永続的なチャット サーバーのプライマリ ・ ミラー ・ インスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="dbef4-162">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>
    
3. <span data-ttu-id="dbef4-163">SQL Server エージェントが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dbef4-163">Be sure that the SQL Server Agent is running.</span></span>
    
4. <span data-ttu-id="dbef4-164">mgc データベースを右クリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbef4-164">Right-click the mgc database, and then click **Properties**.</span></span>
    
5. <span data-ttu-id="dbef4-165">[**ページの選択**] で、[**トランザクション ログの配布**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbef4-165">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
6. <span data-ttu-id="dbef4-166">[**ログ配布構成のプライマリ データベースとして有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="dbef4-166">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
7. <span data-ttu-id="dbef4-167">[**トランザクション ログのバックアップ**] で、[**バックアップの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbef4-167">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
8. <span data-ttu-id="dbef4-168">[**バックアップ フォルダーのネットワーク パスを指定する**] ボックスに、トランザクション ログのバックアップ フォルダーとして作成した共有場所へのネットワーク パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="dbef4-168">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>
    
9. <span data-ttu-id="dbef4-p116">バックアップ フォルダーがプライマリ サーバーに存在する場合は、[**バックアップ フォルダーがプライマリ サーバーに存在する場合は、バックアップ フォルダーのローカル パスを入力**] ボックスにバックアップ フォルダーのローカル パスを入力します (バックアップ フォルダーがプライマリ サーバーに存在しない場合は、このボックスを空のままにします)。</span><span class="sxs-lookup"><span data-stu-id="dbef4-p116">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="dbef4-171">プライマリ サーバー上の SQL Server サービス アカウントは、ローカル システム アカウントで実行する場合は、プライマリ サーバーで、バックアップ フォルダーを作成し、そのフォルダーのローカル パスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbef4-171">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
10. <span data-ttu-id="dbef4-172">[**次の期間を経過したファイルを削除する**] パラメーターと [**バックアップが次の期間内に行われない場合は警告する**] パラメーターを構成します。</span><span class="sxs-lookup"><span data-stu-id="dbef4-172">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
11. <span data-ttu-id="dbef4-173">[**バックアップ ジョブ**] の [**スケジュール**] ボックスに一覧表示されるバックアップ スケジュールを確認してください。</span><span class="sxs-lookup"><span data-stu-id="dbef4-173">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="dbef4-174">インストールのスケジュールをカスタマイズするには、**スケジュール**] をクリックし、必要に応じて、SQL Server エージェントのスケジュールを調整します。</span><span class="sxs-lookup"><span data-stu-id="dbef4-174">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="dbef4-175">プライマリ データベースと同じ設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="dbef4-175">Use the same settings that you used for the primary database.</span></span> 
  
12. <span data-ttu-id="dbef4-176">[**圧縮**] で、[**既定のサーバー設定を使用する**] をクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbef4-176">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>
    
13. <span data-ttu-id="dbef4-177">[**セカンダリ サーバー インスタンスとデータベース**] で、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbef4-177">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
14. <span data-ttu-id="dbef4-178">[**接続**] をクリックして、セカンダリ サーバーとして構成した SQL Server のインスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="dbef4-178">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
15. <span data-ttu-id="dbef4-179">[**セカンダリ データベース**] ボックスで、一覧から [**mgc**] データベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="dbef4-179">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
16. <span data-ttu-id="dbef4-180">[**セカンダリ データベースの初期化**] タブで、[**いいえ、セカンダリ データベースは初期化されています**] オプションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbef4-180">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>
    
17. <span data-ttu-id="dbef4-p118">[**ファイルのコピー**] タブの [**ファイルのコピー先フォルダー**] に、トランザクション ログのバックアップをコピーするフォルダーのパスを入力して、[**OK**] をクリックします。多くの場合、このフォルダーは、セカンダリ サーバー上にあります。</span><span class="sxs-lookup"><span data-stu-id="dbef4-p118">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**. This folder is often located on the secondary server.</span></span>
    
18. <span data-ttu-id="dbef4-183">[**スクリプトの構成**] ボックスの一覧を開き、[**スクリプト構成を新規クエリ ウィンドウに保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbef4-183">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>
    
19. <span data-ttu-id="dbef4-184">[**データベースのプロパティ**] に表示された新規クエリ ウィンドウで [**OK**] をクリックして、構成プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="dbef4-184">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>
    
20. <span data-ttu-id="dbef4-185">選択し、クエリの最初の実行 (を参照してください手順 18) 上の行に:- \* \* \* \* \* \*終了: プライマリ ・ サイトで実行するスクリプト: \* \* \* \* \* \*。</span><span class="sxs-lookup"><span data-stu-id="dbef4-185">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="dbef4-186">このスクリプトを手動で実行すると、SQL Server Management Studio は、SQL Server ログ配布構成の複数のプライマリ ・ データベースをサポートしていないために、必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbef4-186">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span> 
  
21. <span data-ttu-id="dbef4-187">[**キャンセル**] をクリックして、ログ配布構成パネルを閉じ、プライマリ データベースとミラー化されたデータベース (フェールオーバー時) の両方でログ ファイルの配布を適切に実装する実用的なセットアップを確立します。 </span><span class="sxs-lookup"><span data-stu-id="dbef4-187">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>
    
22. <span data-ttu-id="dbef4-188">プライマリに永続的なチャットのプライマリ ・ データベースの手動でフェイル バックします。</span><span class="sxs-lookup"><span data-stu-id="dbef4-188">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="dbef4-189">これは、Skype をビジネス サーバー管理シェル、および**呼び出し CsDatabaseFailover**コマンドレットを使用して行われます。</span><span class="sxs-lookup"><span data-stu-id="dbef4-189">This is done by using the Skype for Business Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    

