---
title: 'Lync Server 2013: 常設チャットサーバーのプライマリデータベースの SQL Server ログ配布のセットアップ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up SQL Server Log Shipping for the Persistent Chat Server primary database
ms:assetid: 088ea1c2-d592-4a11-b3b8-f1e2f8beae93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204653(v=OCS.15)
ms:contentKeyID: 48183337
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4da247e50975ecbed5e64a6e4bebc31d531218b3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040806"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-sql-server-log-shipping-in-lync-server-2013-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="a279f-102">常設チャットサーバーのプライマリデータベースのための Lync Server 2013 での SQL Server ログ配布のセットアップ</span><span class="sxs-lookup"><span data-stu-id="a279f-102">Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a279f-103">_**トピックの最終更新日:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="a279f-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="a279f-104">SQL Server Management Studio を使用して、常設チャットサーバーのセカンダリログ配布データベースのインスタンスに接続し、SQL Server エージェントが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a279f-104">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span>

<span data-ttu-id="a279f-105">常設チャットプライマリデータベースインスタンスに接続された SQL Server Management Studio を使用して、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a279f-105">Using SQL Server Management Studio connected to the Persistent Chat primary database instance, perform the following steps:</span></span>

1.  <span data-ttu-id="a279f-106">SQL Server エージェントが実行されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a279f-106">Be sure that the SQL Server Agent is running.</span></span>

2.  <span data-ttu-id="a279f-107">mgc データベースを右クリックしてから、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a279f-107">Right-click the mgc database, and then click **Properties**.</span></span>

3.  <span data-ttu-id="a279f-108">[**ページの選択**] で、[**トランザクション ログの配布**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a279f-108">Under **Select a page**, click **Transaction Log Shipping**.</span></span>

4.  <span data-ttu-id="a279f-109">[**ログ配布構成のプライマリ データベースとして有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="a279f-109">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>

5.  <span data-ttu-id="a279f-110">[**トランザクション ログのバックアップ**] で、[**バックアップの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a279f-110">Under **Transaction log backups**, click **Backup Settings**.</span></span>

6.  <span data-ttu-id="a279f-111">[**バックアップフォルダーへのネットワークパス**] ボックスに、トランザクションログのバックアップフォルダーとして作成した共有へのネットワークパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="a279f-111">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>

7.  <span data-ttu-id="a279f-112">バックアップフォルダーがプライマリサーバー上にある場合は、バックアップフォルダーがプライマリサーバー上にある場合は、そのフォルダーへのローカルパスを入力します **(例: c:\\backup) ボックスに、フォルダーへのローカルパスを入力**します。</span><span class="sxs-lookup"><span data-stu-id="a279f-112">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\\backup)** box.</span></span> <span data-ttu-id="a279f-113">(バックアップフォルダーがプライマリサーバー上にない場合は、このボックスを空のままにしておくことができます。)</span><span class="sxs-lookup"><span data-stu-id="a279f-113">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a279f-114">プライマリサーバー上の SQL Server サービスアカウントがローカルシステムアカウントで実行されている場合は、プライマリサーバー上にバックアップフォルダーを作成し、そのフォルダーへのローカルパスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a279f-114">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span>

    
    </div>

8.  <span data-ttu-id="a279f-115">[**次の期間を経過したファイルを削除する**] パラメーターと [**バックアップが次の期間内に行われない場合は警告する**] パラメーターを構成します。</span><span class="sxs-lookup"><span data-stu-id="a279f-115">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>

9.  <span data-ttu-id="a279f-116">[**バックアップ ジョブ**] の [**スケジュール**] ボックスに一覧表示されるバックアップ スケジュールを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a279f-116">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="a279f-117">インストールのスケジュールをカスタマイズするには、[**スケジュール**] をクリックし、必要に応じて SQL Server エージェントのスケジュールを調整します。</span><span class="sxs-lookup"><span data-stu-id="a279f-117">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>

10. <span data-ttu-id="a279f-118">[**圧縮**] で、[**既定のサーバー設定を使用する**] を選択し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a279f-118">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>

11. <span data-ttu-id="a279f-119">[**セカンダリ サーバー インスタンスとデータベース**] で、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a279f-119">Under **Secondary server instances and databases**, click **Add**.</span></span>

12. <span data-ttu-id="a279f-120">[**接続**] をクリックして、セカンダリサーバーとして構成した SQL Server のインスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="a279f-120">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>

13. <span data-ttu-id="a279f-121">[**セカンダリ データベース**] ボックスで、一覧から [**mgc**] データベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="a279f-121">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>

14. <span data-ttu-id="a279f-122">[**セカンダリデータベースの初期化**] タブで、[**はい、プライマリデータベースの完全バックアップを生成し、セカンダリデータベースに復元**します] を選択します (存在しない場合はセカンダリデータベースを作成します)。</span><span class="sxs-lookup"><span data-stu-id="a279f-122">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>

15. <span data-ttu-id="a279f-123">[**ファイルのコピー** ] タブの [**ファイルのコピー先フォルダー** ] ボックスに、トランザクションログのバックアップのコピー先フォルダーのパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="a279f-123">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied.</span></span> <span data-ttu-id="a279f-124">多くの場合、このフォルダーは、セカンダリ サーバー上にあります。</span><span class="sxs-lookup"><span data-stu-id="a279f-124">This folder is often located on the secondary server.</span></span>

16. <span data-ttu-id="a279f-125">[**コピージョブ**] の下にある [**スケジュール**] ボックスに一覧表示されるコピースケジュールを確認します。</span><span class="sxs-lookup"><span data-stu-id="a279f-125">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="a279f-126">インストールのスケジュールをカスタマイズするには、[**スケジュール**] をクリックし、必要に応じて SQL Server エージェントのスケジュールを調整します。</span><span class="sxs-lookup"><span data-stu-id="a279f-126">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="a279f-127">このスケジュールは、バックアップスケジュールとほぼ同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a279f-127">This schedule should be approximately the same as the backup schedule.</span></span>

17. <span data-ttu-id="a279f-128">[**復元**] タブの [**バックアップ復元時のデータベース状態**] で、[**復旧モードなし**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="a279f-128">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>

18. <span data-ttu-id="a279f-129">[**バックアップの復元を少なく**する] の下で、[ **0 分**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a279f-129">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>

19. <span data-ttu-id="a279f-130">[**復元が実行中でない場合、警告**] で警告のしきい値を選択します。</span><span class="sxs-lookup"><span data-stu-id="a279f-130">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>

20. <span data-ttu-id="a279f-131">[復元**ジョブ**] の下にある [**スケジュール**] ボックスに表示されている復元スケジュールを確認します。</span><span class="sxs-lookup"><span data-stu-id="a279f-131">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="a279f-132">インストールのスケジュールをカスタマイズするには、[**スケジュール**] をクリックし、必要に応じて SQL Server エージェントのスケジュールを調整して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a279f-132">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="a279f-133">このスケジュールは、バックアップスケジュールとほぼ同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a279f-133">This schedule should be approximately the same as the backup schedule.</span></span>

21. <span data-ttu-id="a279f-134">[**データベースのプロパティ**] ダイアログボックスで、[ **OK** ] をクリックして構成プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="a279f-134">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

