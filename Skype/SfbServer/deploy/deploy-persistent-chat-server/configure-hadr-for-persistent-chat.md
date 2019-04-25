---
title: Skype for Business Server 2015 での常設チャット サーバーの高可用性および障害復旧の構成
ms.reviewer: ''
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
ms.openlocfilehash: 7bc1ae0b71df3916c36acfdc7fabce91caa297e8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225449"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="7b334-103">Skype for Business Server 2015 での常設チャット サーバーの高可用性および障害復旧の構成</span><span class="sxs-lookup"><span data-stu-id="7b334-103">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7b334-104">**の概要:** ビジネス サーバー 2015 の Skype での永続的なチャット サーバーの高可用性と障害回復を構成する方法の詳細については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b334-104">**Summary:** Read this topic to learn how to configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="7b334-105">ビジネス サーバー用の Skype は、バック エンド サーバー、データベース ・ ミラーリングなどの複数の高可用性モードをサポートします。</span><span class="sxs-lookup"><span data-stu-id="7b334-105">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="7b334-106">詳細については、「[Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b334-106">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="7b334-107">AlwaysOn 可用性グループは、永続的なチャット サーバーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7b334-107">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 

> [!NOTE] 
> <span data-ttu-id="7b334-108">永続的なチャットですがビジネス サーバー 2015 の Skype で利用可能なビジネス サーバー 2019 の Skype でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7b334-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="7b334-109">同じ機能は、チームで使用できます。</span><span class="sxs-lookup"><span data-stu-id="7b334-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="7b334-110">詳細については、[マイクロソフトのチームにビジネス用の Skype からの旅](/microsoftteams/journey-skypeforbusiness-teams)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b334-110">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="7b334-111">永続的なチャットを使用する場合は、選択肢は、いずれかをチームでは、この機能を必要とするユーザーを移行するまたはビジネス サーバー 2015 の Skype を使用し続ける。</span><span class="sxs-lookup"><span data-stu-id="7b334-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="7b334-112">高可用性と災害復旧について、永続的なチャットの展開を構成する前に、[高可用性とビジネス サーバー 2015 の Skype での永続的なチャット サーバーの障害回復の計画](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md)の概念に精通していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7b334-112">Before you configure your Persistent Chat deployment for high availability and disaster recovery, be sure you are familiar with the concepts in [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="7b334-113">拡大された永続的なチャット サーバー プールの永続的なチャット サーバーがこれらのトピックで説明されている災害復旧ソリューションがビルドされます。</span><span class="sxs-lookup"><span data-stu-id="7b334-113">The disaster recovery solution for Persistent Chat Server described in these topics is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="7b334-114">計画の内容は、リソース要件、および永続的なチャット サーバーは、SQL Server のミラーリングを使用して、高い可用性と SQL Server のログ配布を含む、高可用性と災害復旧を可能にする拡大されたプール トポロジについて説明します。災害復旧します。</span><span class="sxs-lookup"><span data-stu-id="7b334-114">The planning content describes resource requirements, and the stretched pool topology that enables high availability and disaster recovery for Persistent Chat Server, including using SQL Server mirroring for high availability and SQL Server log shipping for disaster recovery.</span></span>
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a><span data-ttu-id="7b334-115">トポロジ ビルダーを使用して高可用性と障害復旧を構成する</span><span class="sxs-lookup"><span data-stu-id="7b334-115">Use Topology Builder to configure high availability and disaster recovery</span></span>

<span data-ttu-id="7b334-116">トポロジ ビルダーで、次の手順に従って常設チャット サーバーのための高可用性と障害復旧を構成します。</span><span class="sxs-lookup"><span data-stu-id="7b334-116">Within Topology Builder, perform the following steps to configure high availability and disaster recovery for Persistent Chat Server.</span></span>
  
1. <span data-ttu-id="7b334-117">ミラー データベースとログ配布セカンダリ データベースの SQL Server の格納を追加します。</span><span class="sxs-lookup"><span data-stu-id="7b334-117">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>
    
2. <span data-ttu-id="7b334-118">永続的なチャット サーバー サービスのプロパティを編集します。</span><span class="sxs-lookup"><span data-stu-id="7b334-118">Edit the Persistent Chat Server service properties to:</span></span>
    
    <span data-ttu-id="7b334-119">a.</span><span class="sxs-lookup"><span data-stu-id="7b334-119">a.</span></span> <span data-ttu-id="7b334-120">プライマリ データベースのミラーリングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="7b334-120">Enable mirroring for the primary database.</span></span>
    
    <span data-ttu-id="7b334-121">b.</span><span class="sxs-lookup"><span data-stu-id="7b334-121">b.</span></span> <span data-ttu-id="7b334-122">プライマリ ・ ミラーの SQL Server ストアを追加します。</span><span class="sxs-lookup"><span data-stu-id="7b334-122">Add the primary mirror SQL Server store.</span></span>
    
    <span data-ttu-id="7b334-123">c.</span><span class="sxs-lookup"><span data-stu-id="7b334-123">c.</span></span> <span data-ttu-id="7b334-124">SQL Server のログ配布のデータベースを有効にします。</span><span class="sxs-lookup"><span data-stu-id="7b334-124">Enable the SQL Server Log Shipping database.</span></span>
    
    <span data-ttu-id="7b334-125">d.</span><span class="sxs-lookup"><span data-stu-id="7b334-125">d.</span></span> <span data-ttu-id="7b334-126">SQL Server のログ配布のセカンダリ SQL Server ストアを追加します。</span><span class="sxs-lookup"><span data-stu-id="7b334-126">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    <span data-ttu-id="7b334-127">e。</span><span class="sxs-lookup"><span data-stu-id="7b334-127">e.</span></span> <span data-ttu-id="7b334-128">セカンダリ データベースの SQL Server ストアのミラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="7b334-128">Add the SQL Server store mirror for the secondary database.</span></span>
    
    <span data-ttu-id="7b334-129">f。</span><span class="sxs-lookup"><span data-stu-id="7b334-129">f.</span></span> <span data-ttu-id="7b334-130">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="7b334-130">Publish the topology.</span></span>
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="7b334-131">常設チャット サーバーのプライマリ データベースの SQL Server ログ配布を設定する</span><span class="sxs-lookup"><span data-stu-id="7b334-131">Set up SQL Server log shipping for the Persistent Chat Server primary database</span></span>

<span data-ttu-id="7b334-132">SQL Server Management Studio を使用すると、永続的なチャット サーバー セカンダリ ログ配布のデータベースのインスタンスに接続し、SQL Server エージェントが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7b334-132">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span> <span data-ttu-id="7b334-133">プライマリ ・ データベースの永続的なチャット インスタンスに接続し、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7b334-133">Then connect to the Persistent Chat primary database instance and perform the following steps:</span></span>
  
1. <span data-ttu-id="7b334-134">mgc データベースを右クリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7b334-134">Right-click the mgc database, and then click **Properties**.</span></span>
    
2. <span data-ttu-id="7b334-135">[**ページの選択**] で、[**トランザクション ログの配布**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7b334-135">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
3. <span data-ttu-id="7b334-136">[**ログ配布構成のプライマリ データベースとして有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="7b334-136">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
4. <span data-ttu-id="7b334-137">[**トランザクション ログのバックアップ**] で、[**バックアップの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7b334-137">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
5. <span data-ttu-id="7b334-138">[**バックアップ フォルダーのネットワーク パスを指定する**] ボックスに、トランザクション ログのバックアップ用に作成した共有フォルダーへのネットワーク パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="7b334-138">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>
    
6. <span data-ttu-id="7b334-p111">バックアップ フォルダーがプライマリ サーバーに存在する場合は、[**バックアップ フォルダーがプライマリ サーバーに存在する場合は、バックアップ フォルダーのローカル パスを入力 (例: c:\backup)**] ボックスにバックアップ フォルダーのローカル パスを入力します (バックアップ フォルダーがプライマリ サーバーに存在しない場合は、このボックスを空のままにします)。</span><span class="sxs-lookup"><span data-stu-id="7b334-p111">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\backup)** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7b334-141">プライマリ サーバー上の SQL Server サービス アカウントは、ローカル システム アカウントで実行する場合は、プライマリ サーバーで、バックアップ フォルダーを作成し、そのフォルダーのローカル パスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b334-141">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
7. <span data-ttu-id="7b334-142">[**次の期間を経過したファイルを削除する**] パラメーターと [**バックアップが次の期間内に行われない場合は警告する**] パラメーターを構成します。</span><span class="sxs-lookup"><span data-stu-id="7b334-142">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
8. <span data-ttu-id="7b334-143">[**バックアップ ジョブ**] の [**スケジュール**] ボックスに一覧表示されるバックアップ スケジュールを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7b334-143">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="7b334-144">インストールのスケジュールをカスタマイズするには、**スケジュール**] をクリックし、必要に応じて SQL Server エージェントのスケジュールを調整します。</span><span class="sxs-lookup"><span data-stu-id="7b334-144">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>
    
9. <span data-ttu-id="7b334-145">[**圧縮**] の [**既定のサーバー設定を使用する**] を選択し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7b334-145">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>
    
10. <span data-ttu-id="7b334-146">[**セカンダリ サーバー インスタンスとデータベース**] で、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7b334-146">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
11. <span data-ttu-id="7b334-147">[**接続**] をクリックし、セカンダリ サーバーとして構成した SQL Server のインスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="7b334-147">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
12. <span data-ttu-id="7b334-148">[**セカンダリ データベース**] ボックスで、一覧から [**mgc**] データベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="7b334-148">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
13. <span data-ttu-id="7b334-149">[**セカンダリ データベースの初期化**] タブで、[**はい、プライマリ データベースの完全バックアップを生成して、セカンダリ データベースに復元します**] オプションを選択します (また、セカンダリ データベースが存在しない場合は作成します)。</span><span class="sxs-lookup"><span data-stu-id="7b334-149">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>
    
14. <span data-ttu-id="7b334-p113">[**ファイルのコピー**] タブの [**ファイルのコピー先フォルダー**] ボックスに、トランザクション ログのバックアップのコピー先フォルダーのパスを入力します。このフォルダーは通常はセカンダリ サーバー上にあります。</span><span class="sxs-lookup"><span data-stu-id="7b334-p113">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied. This folder is often located on the secondary server.</span></span>
    
15. <span data-ttu-id="7b334-152">[**コピー ジョブ**] の [**スケジュール**] ボックスに一覧表示されるコピー スケジュールを確認します。</span><span class="sxs-lookup"><span data-stu-id="7b334-152">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="7b334-153">インストールのスケジュールをカスタマイズするには、**スケジュール**] をクリックし、必要に応じて SQL Server エージェントのスケジュールを調整します。</span><span class="sxs-lookup"><span data-stu-id="7b334-153">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="7b334-154">このスケジュールは、バックアップ スケジュールとよく似た内容にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b334-154">This schedule should be approximately the same as the backup schedule.</span></span>
    
16. <span data-ttu-id="7b334-155">[**復元**] タブの [**バックアップ復元時のデータベース状態**] で、[**復旧モードなし**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="7b334-155">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>
    
17. <span data-ttu-id="7b334-156">[**バックアップの復元を最低限次の期間遅延する**] で [**0 分**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b334-156">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>
    
18. <span data-ttu-id="7b334-157">[**復元が次の期間内に行われない場合は警告する**] で警告のしきい値を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b334-157">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>
    
19. <span data-ttu-id="7b334-158">[**復元ジョブ**] の [**スケジュール**] ボックスに一覧表示される復元スケジュールを確認します。</span><span class="sxs-lookup"><span data-stu-id="7b334-158">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="7b334-159">インストールのスケジュールをカスタマイズするには、[**スケジュール**] をクリックして **]** を必要に応じて、SQL Server エージェントのスケジュールを調整します。</span><span class="sxs-lookup"><span data-stu-id="7b334-159">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="7b334-160">このスケジュールは、バックアップ スケジュールとよく似た内容にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b334-160">This schedule should be approximately the same as the backup schedule.</span></span>
    
20. <span data-ttu-id="7b334-161">[**データベースのプロパティ**] ダイアログ ボックスで、[**OK**] をクリックして構成のプロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="7b334-161">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a><span data-ttu-id="7b334-162">プライマリ ミラーとセカンダリ データベースとの間の SQL Server ログ配布をセットアップする</span><span class="sxs-lookup"><span data-stu-id="7b334-162">Set up SQL Server log shipping between the primary mirror and the secondary database</span></span>

<span data-ttu-id="7b334-163">ログ配布のプライマリの永続的なチャットのデータベースは、ミラー データベースにフェールオーバーしているかを続行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7b334-163">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>
  
1. <span data-ttu-id="7b334-164">手動でミラーを永続的なチャットのプライマリ データベースにフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="7b334-164">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="7b334-165">これは、Skype をビジネス サーバー管理シェルを**呼び出し CsDatabaseFailover**コマンドレットを使用して行われます。</span><span class="sxs-lookup"><span data-stu-id="7b334-165">This is done by using the Skype for Business Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    
2. <span data-ttu-id="7b334-166">SQL Server Management Studio を使用すると、永続的なチャット サーバーのプライマリ ・ ミラー ・ インスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="7b334-166">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>
    
3. <span data-ttu-id="7b334-167">SQL Server エージェントが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7b334-167">Be sure that the SQL Server Agent is running.</span></span>
    
4. <span data-ttu-id="7b334-168">mgc データベースを右クリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7b334-168">Right-click the mgc database, and then click **Properties**.</span></span>
    
5. <span data-ttu-id="7b334-169">[**ページの選択**] で、[**トランザクション ログの配布**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7b334-169">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
6. <span data-ttu-id="7b334-170">[**ログ配布構成のプライマリ データベースとして有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="7b334-170">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
7. <span data-ttu-id="7b334-171">[**トランザクション ログのバックアップ**] で、[**バックアップの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7b334-171">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
8. <span data-ttu-id="7b334-172">[**バックアップ フォルダーのネットワーク パスを指定する**] ボックスに、トランザクション ログのバックアップ フォルダーとして作成した共有場所へのネットワーク パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="7b334-172">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>
    
9. <span data-ttu-id="7b334-p117">バックアップ フォルダーがプライマリ サーバーに存在する場合は、[**バックアップ フォルダーがプライマリ サーバーに存在する場合は、バックアップ フォルダーのローカル パスを入力**] ボックスにバックアップ フォルダーのローカル パスを入力します (バックアップ フォルダーがプライマリ サーバーに存在しない場合は、このボックスを空のままにします)。</span><span class="sxs-lookup"><span data-stu-id="7b334-p117">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7b334-175">プライマリ サーバー上の SQL Server サービス アカウントは、ローカル システム アカウントで実行する場合は、プライマリ サーバーで、バックアップ フォルダーを作成し、そのフォルダーのローカル パスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b334-175">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
10. <span data-ttu-id="7b334-176">[**次の期間を経過したファイルを削除する**] パラメーターと [**バックアップが次の期間内に行われない場合は警告する**] パラメーターを構成します。</span><span class="sxs-lookup"><span data-stu-id="7b334-176">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
11. <span data-ttu-id="7b334-177">[**バックアップ ジョブ**] の [**スケジュール**] ボックスに一覧表示されるバックアップ スケジュールを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7b334-177">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="7b334-178">インストールのスケジュールをカスタマイズするには、**スケジュール**] をクリックし、必要に応じて、SQL Server エージェントのスケジュールを調整します。</span><span class="sxs-lookup"><span data-stu-id="7b334-178">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7b334-179">プライマリ データベースと同じ設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="7b334-179">Use the same settings that you used for the primary database.</span></span> 
  
12. <span data-ttu-id="7b334-180">[**圧縮**] で、[**既定のサーバー設定を使用する**] をクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7b334-180">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>
    
13. <span data-ttu-id="7b334-181">[**セカンダリ サーバー インスタンスとデータベース**] で、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7b334-181">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
14. <span data-ttu-id="7b334-182">[**接続**] をクリックして、セカンダリ サーバーとして構成した SQL Server のインスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="7b334-182">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
15. <span data-ttu-id="7b334-183">[**セカンダリ データベース**] ボックスで、一覧から [**mgc**] データベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="7b334-183">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
16. <span data-ttu-id="7b334-184">[**セカンダリ データベースの初期化**] タブで、[**いいえ、セカンダリ データベースは初期化されています**] オプションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="7b334-184">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>
    
17. <span data-ttu-id="7b334-p119">[**ファイルのコピー**] タブの [**ファイルのコピー先フォルダー**] に、トランザクション ログのバックアップをコピーするフォルダーのパスを入力して、[**OK**] をクリックします。多くの場合、このフォルダーは、セカンダリ サーバー上にあります。</span><span class="sxs-lookup"><span data-stu-id="7b334-p119">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**. This folder is often located on the secondary server.</span></span>
    
18. <span data-ttu-id="7b334-187">[**スクリプトの構成**] ボックスの一覧を開き、[**スクリプト構成を新規クエリ ウィンドウに保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7b334-187">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>
    
19. <span data-ttu-id="7b334-188">[**データベースのプロパティ**] に表示された新規クエリ ウィンドウで [**OK**] をクリックして、構成プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="7b334-188">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>
    
20. <span data-ttu-id="7b334-189">選択し、クエリの最初の実行 (を参照してください手順 18) 上の行に:- \* \* \* \* \* \*終了: プライマリ ・ サイトで実行するスクリプト: \* \* \* \* \* \*。</span><span class="sxs-lookup"><span data-stu-id="7b334-189">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7b334-190">このスクリプトを手動で実行すると、SQL Server Management Studio は、SQL Server ログ配布構成の複数のプライマリ ・ データベースをサポートしていないために、必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b334-190">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span> 
  
21. <span data-ttu-id="7b334-191">[**キャンセル**] をクリックして、ログ配布構成パネルを閉じ、プライマリ データベースとミラー化されたデータベース (フェールオーバー時) の両方でログ ファイルの配布を適切に実装する実用的なセットアップを確立します。 </span><span class="sxs-lookup"><span data-stu-id="7b334-191">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>
    
22. <span data-ttu-id="7b334-192">プライマリに永続的なチャットのプライマリ ・ データベースの手動でフェイル バックします。</span><span class="sxs-lookup"><span data-stu-id="7b334-192">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="7b334-193">これは、Skype をビジネス サーバー管理シェル、および**呼び出し CsDatabaseFailover**コマンドレットを使用して行われます。</span><span class="sxs-lookup"><span data-stu-id="7b334-193">This is done by using the Skype for Business Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    

