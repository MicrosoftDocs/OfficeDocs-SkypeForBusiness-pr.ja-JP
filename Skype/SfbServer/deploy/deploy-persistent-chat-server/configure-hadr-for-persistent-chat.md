---
title: Skype for Business Server 2015 での常設チャット サーバーの高可用性および障害復旧の構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: '概要: このトピックでは、Skype for Business Server 2015 で常設チャットサーバーの高可用性と障害回復を構成する方法について説明します。'
ms.openlocfilehash: e9e313cf83fd784e94efe98fe7a49bbbb800f83f
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239838"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="9ddea-103">Skype for Business Server 2015 での常設チャット サーバーの高可用性および障害復旧の構成</span><span class="sxs-lookup"><span data-stu-id="9ddea-103">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9ddea-104">**概要:** このトピックでは、Skype for Business Server 2015 で常設チャットサーバーの高可用性と障害回復を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9ddea-104">**Summary:** Read this topic to learn how to configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="9ddea-105">Skype for Business Server では、データベースミラーリングなど、バックエンドサーバーでの高可用性の複数のモードがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9ddea-105">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="9ddea-106">詳細については、「[Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ddea-106">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9ddea-107">AlwaysOn 可用性グループは、常設チャットサーバーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="9ddea-107">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 

> [!NOTE] 
> <span data-ttu-id="9ddea-108">常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="9ddea-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="9ddea-109">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9ddea-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="9ddea-110">詳細については、「 [Microsoft Teams のアップグレードの](/microsoftteams/upgrade-start-here)概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ddea-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="9ddea-111">常設チャットを使用する必要がある場合は、この機能が必要なユーザーをチームに移行するか、Skype for Business Server 2015 を使い続けるかのいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="9ddea-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="9ddea-112">高可用性と障害回復のための常設チャットの展開を構成する前に、「 [Skype For Business server 2015 の常設チャットサーバーの高可用性と障害回復の計画](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md)」の概念に精通していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9ddea-112">Before you configure your Persistent Chat deployment for high availability and disaster recovery, be sure you are familiar with the concepts in [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="9ddea-113">これらのトピックで説明する常設チャットサーバーの障害回復ソリューションは、ストレッチされた常設チャットサーバープールに基づいています。</span><span class="sxs-lookup"><span data-stu-id="9ddea-113">The disaster recovery solution for Persistent Chat Server described in these topics is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="9ddea-114">計画コンテンツでは、リソース要件と、SQL Server ミラーリングを使用して高可用性と障害回復を実現している、常設チャットサーバーの高可用性と災害復旧を可能にする拡張プールトポロジを示しています。障害回復。</span><span class="sxs-lookup"><span data-stu-id="9ddea-114">The planning content describes resource requirements, and the stretched pool topology that enables high availability and disaster recovery for Persistent Chat Server, including using SQL Server mirroring for high availability and SQL Server log shipping for disaster recovery.</span></span>
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a><span data-ttu-id="9ddea-115">トポロジ ビルダーを使用して高可用性と障害復旧を構成する</span><span class="sxs-lookup"><span data-stu-id="9ddea-115">Use Topology Builder to configure high availability and disaster recovery</span></span>

<span data-ttu-id="9ddea-116">トポロジ ビルダーで、次の手順に従って常設チャット サーバーのための高可用性と障害復旧を構成します。</span><span class="sxs-lookup"><span data-stu-id="9ddea-116">Within Topology Builder, perform the following steps to configure high availability and disaster recovery for Persistent Chat Server.</span></span>
  
1. <span data-ttu-id="9ddea-117">ミラーデータベースとログ配布のセカンダリデータベース SQL Server ストアを追加します。</span><span class="sxs-lookup"><span data-stu-id="9ddea-117">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>
    
2. <span data-ttu-id="9ddea-118">常設チャットサーバーサービスのプロパティを編集するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9ddea-118">Edit the Persistent Chat Server service properties to:</span></span>
    
    <span data-ttu-id="9ddea-119">a.</span><span class="sxs-lookup"><span data-stu-id="9ddea-119">a.</span></span> <span data-ttu-id="9ddea-120">プライマリ データベースのミラーリングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="9ddea-120">Enable mirroring for the primary database.</span></span>
    
    <span data-ttu-id="9ddea-121">b.</span><span class="sxs-lookup"><span data-stu-id="9ddea-121">b.</span></span> <span data-ttu-id="9ddea-122">プライマリミラー SQL Server ストアを追加します。</span><span class="sxs-lookup"><span data-stu-id="9ddea-122">Add the primary mirror SQL Server store.</span></span>
    
    <span data-ttu-id="9ddea-123">c.</span><span class="sxs-lookup"><span data-stu-id="9ddea-123">c.</span></span> <span data-ttu-id="9ddea-124">SQL Server のログ配布データベースを有効にします。</span><span class="sxs-lookup"><span data-stu-id="9ddea-124">Enable the SQL Server Log Shipping database.</span></span>
    
    <span data-ttu-id="9ddea-125">d.</span><span class="sxs-lookup"><span data-stu-id="9ddea-125">d.</span></span> <span data-ttu-id="9ddea-126">SQL Server ログ配布のセカンダリ SQL Server ストアを追加します。</span><span class="sxs-lookup"><span data-stu-id="9ddea-126">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    <span data-ttu-id="9ddea-127">•.</span><span class="sxs-lookup"><span data-stu-id="9ddea-127">e.</span></span> <span data-ttu-id="9ddea-128">セカンダリデータベースの SQL Server ストアミラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="9ddea-128">Add the SQL Server store mirror for the secondary database.</span></span>
    
    <span data-ttu-id="9ddea-129">f.</span><span class="sxs-lookup"><span data-stu-id="9ddea-129">f.</span></span> <span data-ttu-id="9ddea-130">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="9ddea-130">Publish the topology.</span></span>
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="9ddea-131">常設チャット サーバーのプライマリ データベースの SQL Server ログ配布を設定する</span><span class="sxs-lookup"><span data-stu-id="9ddea-131">Set up SQL Server log shipping for the Persistent Chat Server primary database</span></span>

<span data-ttu-id="9ddea-132">SQL Server Management Studio を使用して、常設チャットサーバーセカンダリログ配布データベースインスタンスに接続し、SQL Server エージェントが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9ddea-132">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span> <span data-ttu-id="9ddea-133">次に、常設チャットプライマリデータベースインスタンスに接続し、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9ddea-133">Then connect to the Persistent Chat primary database instance and perform the following steps:</span></span>
  
1. <span data-ttu-id="9ddea-134">mgc データベースを右クリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ddea-134">Right-click the mgc database, and then click **Properties**.</span></span>
    
2. <span data-ttu-id="9ddea-135">[**ページの選択**] で、[**トランザクション ログの配布**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ddea-135">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
3. <span data-ttu-id="9ddea-136">[**ログ配布構成のプライマリ データベースとして有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="9ddea-136">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
4. <span data-ttu-id="9ddea-137">[**トランザクション ログのバックアップ**] で、[**バックアップの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ddea-137">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
5. <span data-ttu-id="9ddea-138">[**バックアップ フォルダーのネットワーク パスを指定する**] ボックスに、トランザクション ログのバックアップ用に作成した共有フォルダーへのネットワーク パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="9ddea-138">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>
    
6. <span data-ttu-id="9ddea-p111">バックアップ フォルダーがプライマリ サーバーに存在する場合は、[**バックアップ フォルダーがプライマリ サーバーに存在する場合は、バックアップ フォルダーのローカル パスを入力 (例: c:\backup)**] ボックスにバックアップ フォルダーのローカル パスを入力します (バックアップ フォルダーがプライマリ サーバーに存在しない場合は、このボックスを空のままにします)。</span><span class="sxs-lookup"><span data-stu-id="9ddea-p111">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\backup)** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="9ddea-141">プライマリサーバーの SQL Server サービスアカウントがローカルシステムアカウントで実行されている場合は、プライマリサーバー上にバックアップフォルダーを作成し、そのフォルダーへのローカルパスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ddea-141">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
7. <span data-ttu-id="9ddea-142">[**次の期間を経過したファイルを削除する**] パラメーターと [**バックアップが次の期間内に行われない場合は警告する**] パラメーターを構成します。</span><span class="sxs-lookup"><span data-stu-id="9ddea-142">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
8. <span data-ttu-id="9ddea-143">[**バックアップ ジョブ**] の [**スケジュール**] ボックスに一覧表示されるバックアップ スケジュールを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9ddea-143">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="9ddea-144">インストールのスケジュールをカスタマイズするには、[**スケジュール**] をクリックし、必要に応じて SQL Server エージェントのスケジュールを調整します。</span><span class="sxs-lookup"><span data-stu-id="9ddea-144">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>
    
9. <span data-ttu-id="9ddea-145">[**圧縮**] の [**既定のサーバー設定を使用する**] を選択し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ddea-145">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>
    
10. <span data-ttu-id="9ddea-146">[**セカンダリ サーバー インスタンスとデータベース**] で、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ddea-146">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
11. <span data-ttu-id="9ddea-147">[**接続**] をクリックし、セカンダリサーバーとして構成した SQL Server のインスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="9ddea-147">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
12. <span data-ttu-id="9ddea-148">[**セカンダリ データベース**] ボックスで、一覧から [**mgc**] データベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="9ddea-148">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
13. <span data-ttu-id="9ddea-149">[**セカンダリ データベースの初期化**] タブで、[**はい、プライマリ データベースの完全バックアップを生成して、セカンダリ データベースに復元します**] オプションを選択します (また、セカンダリ データベースが存在しない場合は作成します)。</span><span class="sxs-lookup"><span data-stu-id="9ddea-149">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>
    
14. <span data-ttu-id="9ddea-p113">[**ファイルのコピー**] タブの [**ファイルのコピー先フォルダー**] ボックスに、トランザクション ログのバックアップのコピー先フォルダーのパスを入力します。このフォルダーは通常はセカンダリ サーバー上にあります。</span><span class="sxs-lookup"><span data-stu-id="9ddea-p113">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied. This folder is often located on the secondary server.</span></span>
    
15. <span data-ttu-id="9ddea-152">[**コピー ジョブ**] の [**スケジュール**] ボックスに一覧表示されるコピー スケジュールを確認します。</span><span class="sxs-lookup"><span data-stu-id="9ddea-152">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="9ddea-153">インストールのスケジュールをカスタマイズするには、[**スケジュール**] をクリックし、必要に応じて SQL Server エージェントのスケジュールを調整します。</span><span class="sxs-lookup"><span data-stu-id="9ddea-153">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="9ddea-154">このスケジュールは、バックアップ スケジュールとよく似た内容にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ddea-154">This schedule should be approximately the same as the backup schedule.</span></span>
    
16. <span data-ttu-id="9ddea-155">[**復元**] タブの [**バックアップ復元時のデータベース状態**] で、[**復旧モードなし**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="9ddea-155">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>
    
17. <span data-ttu-id="9ddea-156">[**バックアップの復元を最低限次の期間遅延する**] で [**0 分**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ddea-156">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>
    
18. <span data-ttu-id="9ddea-157">[**復元が次の期間内に行われない場合は警告する**] で警告のしきい値を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ddea-157">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>
    
19. <span data-ttu-id="9ddea-158">[**復元ジョブ**] の [**スケジュール**] ボックスに一覧表示される復元スケジュールを確認します。</span><span class="sxs-lookup"><span data-stu-id="9ddea-158">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="9ddea-159">インストールのスケジュールをカスタマイズするには、[**スケジュール**] をクリックし、必要に応じて SQL Server エージェントのスケジュールを調整して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ddea-159">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="9ddea-160">このスケジュールは、バックアップ スケジュールとよく似た内容にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ddea-160">This schedule should be approximately the same as the backup schedule.</span></span>
    
20. <span data-ttu-id="9ddea-161">[**データベースのプロパティ**] ダイアログ ボックスで、[**OK**] をクリックして構成のプロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="9ddea-161">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a><span data-ttu-id="9ddea-162">プライマリ ミラーとセカンダリ データベースとの間の SQL Server ログ配布をセットアップする</span><span class="sxs-lookup"><span data-stu-id="9ddea-162">Set up SQL Server log shipping between the primary mirror and the secondary database</span></span>

<span data-ttu-id="9ddea-163">プライマリ常設チャットデータベースがミラーデータベースにフェールオーバーされた場合は、次の手順に従ってログの配布を続行します。</span><span class="sxs-lookup"><span data-stu-id="9ddea-163">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>
  
1. <span data-ttu-id="9ddea-164">プライマリ永続的チャットデータベースをミラーに手動でフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="9ddea-164">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="9ddea-165">これを行うには、Skype for Business Server 管理シェルと**Invoke-CsDatabaseFailover**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9ddea-165">This is done by using the Skype for Business Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    
2. <span data-ttu-id="9ddea-166">SQL Server Management Studio を使用して、プライマリ常設チャットサーバーのミラーインスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="9ddea-166">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>
    
3. <span data-ttu-id="9ddea-167">SQL Server エージェントが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9ddea-167">Be sure that the SQL Server Agent is running.</span></span>
    
4. <span data-ttu-id="9ddea-168">mgc データベースを右クリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ddea-168">Right-click the mgc database, and then click **Properties**.</span></span>
    
5. <span data-ttu-id="9ddea-169">[**ページの選択**] で、[**トランザクション ログの配布**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ddea-169">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
6. <span data-ttu-id="9ddea-170">[**ログ配布構成のプライマリ データベースとして有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="9ddea-170">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
7. <span data-ttu-id="9ddea-171">[**トランザクション ログのバックアップ**] で、[**バックアップの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ddea-171">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
8. <span data-ttu-id="9ddea-172">[**バックアップ フォルダーのネットワーク パスを指定する**] ボックスに、トランザクション ログのバックアップ フォルダーとして作成した共有場所へのネットワーク パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="9ddea-172">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>
    
9. <span data-ttu-id="9ddea-p117">バックアップ フォルダーがプライマリ サーバーに存在する場合は、[**バックアップ フォルダーがプライマリ サーバーに存在する場合は、バックアップ フォルダーのローカル パスを入力**] ボックスにバックアップ フォルダーのローカル パスを入力します (バックアップ フォルダーがプライマリ サーバーに存在しない場合は、このボックスを空のままにします)。</span><span class="sxs-lookup"><span data-stu-id="9ddea-p117">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="9ddea-175">プライマリサーバーの SQL Server サービスアカウントがローカルシステムアカウントで実行されている場合は、プライマリサーバー上にバックアップフォルダーを作成し、そのフォルダーへのローカルパスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ddea-175">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
10. <span data-ttu-id="9ddea-176">[**次の期間を経過したファイルを削除する**] パラメーターと [**バックアップが次の期間内に行われない場合は警告する**] パラメーターを構成します。</span><span class="sxs-lookup"><span data-stu-id="9ddea-176">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
11. <span data-ttu-id="9ddea-177">[**バックアップ ジョブ**] の [**スケジュール**] ボックスに一覧表示されるバックアップ スケジュールを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9ddea-177">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="9ddea-178">インストールのスケジュールをカスタマイズするには、[**スケジュール**] をクリックし、必要に応じて SQL Server エージェントのスケジュールを調整します。</span><span class="sxs-lookup"><span data-stu-id="9ddea-178">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="9ddea-179">プライマリ データベースと同じ設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="9ddea-179">Use the same settings that you used for the primary database.</span></span> 
  
12. <span data-ttu-id="9ddea-180">[**圧縮**] で、[**既定のサーバー設定を使用する**] をクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ddea-180">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>
    
13. <span data-ttu-id="9ddea-181">[**セカンダリ サーバー インスタンスとデータベース**] で、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ddea-181">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
14. <span data-ttu-id="9ddea-182">[**接続**] をクリックして、セカンダリ サーバーとして構成した SQL Server のインスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="9ddea-182">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
15. <span data-ttu-id="9ddea-183">[**セカンダリ データベース**] ボックスで、一覧から [**mgc**] データベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="9ddea-183">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
16. <span data-ttu-id="9ddea-184">[**セカンダリ データベースの初期化**] タブで、[**いいえ、セカンダリ データベースは初期化されています**] オプションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ddea-184">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>
    
17. <span data-ttu-id="9ddea-p119">[**ファイルのコピー**] タブの [**ファイルのコピー先フォルダー**] に、トランザクション ログのバックアップをコピーするフォルダーのパスを入力して、[**OK**] をクリックします。多くの場合、このフォルダーは、セカンダリ サーバー上にあります。</span><span class="sxs-lookup"><span data-stu-id="9ddea-p119">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**. This folder is often located on the secondary server.</span></span>
    
18. <span data-ttu-id="9ddea-187">[**スクリプトの構成**] ボックスの一覧を開き、[**スクリプト構成を新規クエリ ウィンドウに保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ddea-187">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>
    
19. <span data-ttu-id="9ddea-188">[**データベースのプロパティ**] に表示された新規クエリ ウィンドウで [**OK**] をクリックして、構成プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="9ddea-188">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>
    
20. <span data-ttu-id="9ddea-189">クエリの最初の半分 (手順18を参照) を選んで実行します。--- \* \* \* \* \* \* --------- \* \* \* \* \* \*---------------------------</span><span class="sxs-lookup"><span data-stu-id="9ddea-189">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="9ddea-190">Sql Server Management Studio では、SQL Server のログ配布構成で複数のプライマリデータベースがサポートされていないため、このスクリプトを手動で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ddea-190">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span> 
  
21. <span data-ttu-id="9ddea-191">[**キャンセル**] をクリックして、ログ配布構成パネルを閉じ、プライマリ データベースとミラー化されたデータベース (フェールオーバー時) の両方でログ ファイルの配布を適切に実装する実用的なセットアップを確立します。 </span><span class="sxs-lookup"><span data-stu-id="9ddea-191">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>
    
22. <span data-ttu-id="9ddea-192">プライマリ常設チャットデータベースを手動でプライマリにフェールバックします。</span><span class="sxs-lookup"><span data-stu-id="9ddea-192">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="9ddea-193">これを行うには、Skype for Business Server 管理シェルと**Invoke-CsDatabaseFailover**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9ddea-193">This is done by using the Skype for Business Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    

