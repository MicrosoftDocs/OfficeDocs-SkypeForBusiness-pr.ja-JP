---
title: 'Lync Server 2013: 常設チャットサーバーのプライマリデータベースの SQL Server ログ配布のセットアップ'
description: 'Lync Server 2013: 常設チャットサーバーのプライマリデータベースの SQL Server ログ配布のセットアップ。'
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
ms.openlocfilehash: 72b7e68bd0cb7b9f544b86a15204d3e832692ec1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554263"
---
# <a name="setting-up-sql-server-log-shipping-in-lync-server-2013-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="c74cb-103">常設チャットサーバーのプライマリデータベースのための Lync Server 2013 での SQL Server ログ配布のセットアップ</span><span class="sxs-lookup"><span data-stu-id="c74cb-103">Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c74cb-104">_**トピックの最終更新日:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="c74cb-104">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="c74cb-105">SQL Server Management Studio を使用して、常設チャットサーバーのセカンダリログ配布データベースのインスタンスに接続し、SQL Server エージェントが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c74cb-105">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span>

<span data-ttu-id="c74cb-106">常設チャットプライマリデータベースインスタンスに接続された SQL Server Management Studio を使用して、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c74cb-106">Using SQL Server Management Studio connected to the Persistent Chat primary database instance, perform the following steps:</span></span>

1.  <span data-ttu-id="c74cb-107">SQL Server エージェントが実行されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c74cb-107">Be sure that the SQL Server Agent is running.</span></span>

2.  <span data-ttu-id="c74cb-108">mgc データベースを右クリックしてから、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c74cb-108">Right-click the mgc database, and then click **Properties**.</span></span>

3.  <span data-ttu-id="c74cb-109">[**ページの選択**] で、[**トランザクション ログの配布**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c74cb-109">Under **Select a page**, click **Transaction Log Shipping**.</span></span>

4.  <span data-ttu-id="c74cb-110">[**ログ配布構成のプライマリ データベースとして有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="c74cb-110">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>

5.  <span data-ttu-id="c74cb-111">[**トランザクション ログのバックアップ**] で、[**バックアップの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c74cb-111">Under **Transaction log backups**, click **Backup Settings**.</span></span>

6.  <span data-ttu-id="c74cb-112">[ **バックアップフォルダーへのネットワークパス** ] ボックスに、トランザクションログのバックアップフォルダーとして作成した共有へのネットワークパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="c74cb-112">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>

7.  <span data-ttu-id="c74cb-113">バックアップフォルダーがプライマリサーバー上にある場合は、バックアップフォルダーがプライマリサーバー上にある場合は、そのフォルダーへのローカルパスを入力します **(例: c: \\ backup) ボックスに、フォルダーへのローカルパスを入力** します。</span><span class="sxs-lookup"><span data-stu-id="c74cb-113">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\\backup)** box.</span></span> <span data-ttu-id="c74cb-114">(バックアップフォルダーがプライマリサーバー上にない場合は、このボックスを空のままにしておくことができます。)</span><span class="sxs-lookup"><span data-stu-id="c74cb-114">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c74cb-115">プライマリサーバー上の SQL Server サービスアカウントがローカルシステムアカウントで実行されている場合は、プライマリサーバー上にバックアップフォルダーを作成し、そのフォルダーへのローカルパスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c74cb-115">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span>

    
    </div>

8.  <span data-ttu-id="c74cb-116">[**次の期間を経過したファイルを削除する**] パラメーターと [**バックアップが次の期間内に行われない場合は警告する**] パラメーターを構成します。</span><span class="sxs-lookup"><span data-stu-id="c74cb-116">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>

9.  <span data-ttu-id="c74cb-117">[**バックアップ ジョブ**] の [**スケジュール**] ボックスに一覧表示されるバックアップ スケジュールを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c74cb-117">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="c74cb-118">インストールのスケジュールをカスタマイズするには、[ **スケジュール**] をクリックし、必要に応じて SQL Server エージェントのスケジュールを調整します。</span><span class="sxs-lookup"><span data-stu-id="c74cb-118">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>

10. <span data-ttu-id="c74cb-119">[ **圧縮**] で、[ **既定のサーバー設定を使用する**] を選択し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c74cb-119">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>

11. <span data-ttu-id="c74cb-120">[**セカンダリ サーバー インスタンスとデータベース**] で、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c74cb-120">Under **Secondary server instances and databases**, click **Add**.</span></span>

12. <span data-ttu-id="c74cb-121">[ **接続** ] をクリックして、セカンダリサーバーとして構成した SQL Server のインスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="c74cb-121">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>

13. <span data-ttu-id="c74cb-122">[**セカンダリ データベース**] ボックスで、一覧から [**mgc**] データベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="c74cb-122">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>

14. <span data-ttu-id="c74cb-123">[ **セカンダリデータベースの初期化** ] タブで、[ **はい、プライマリデータベースの完全バックアップを生成し、セカンダリデータベースに復元**します] を選択します (存在しない場合はセカンダリデータベースを作成します)。</span><span class="sxs-lookup"><span data-stu-id="c74cb-123">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>

15. <span data-ttu-id="c74cb-124">[ **ファイルのコピー** ] タブの [ **ファイルのコピー先フォルダー** ] ボックスに、トランザクションログのバックアップのコピー先フォルダーのパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="c74cb-124">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied.</span></span> <span data-ttu-id="c74cb-125">多くの場合、このフォルダーは、セカンダリ サーバー上にあります。</span><span class="sxs-lookup"><span data-stu-id="c74cb-125">This folder is often located on the secondary server.</span></span>

16. <span data-ttu-id="c74cb-126">[**コピージョブ**] の下にある [**スケジュール**] ボックスに一覧表示されるコピースケジュールを確認します。</span><span class="sxs-lookup"><span data-stu-id="c74cb-126">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="c74cb-127">インストールのスケジュールをカスタマイズするには、[ **スケジュール**] をクリックし、必要に応じて SQL Server エージェントのスケジュールを調整します。</span><span class="sxs-lookup"><span data-stu-id="c74cb-127">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="c74cb-128">このスケジュールは、バックアップスケジュールとほぼ同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c74cb-128">This schedule should be approximately the same as the backup schedule.</span></span>

17. <span data-ttu-id="c74cb-129">[ **復元** ] タブの [ **バックアップ復元時のデータベース状態**] で、[ **復旧モードなし** ] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="c74cb-129">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>

18. <span data-ttu-id="c74cb-130">[ **バックアップの復元を少なく**する] の下で、[ **0 分**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c74cb-130">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>

19. <span data-ttu-id="c74cb-131">[ **復元が実行中でない場合、警告**] で警告のしきい値を選択します。</span><span class="sxs-lookup"><span data-stu-id="c74cb-131">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>

20. <span data-ttu-id="c74cb-132">[復元**ジョブ**] の下にある [**スケジュール**] ボックスに表示されている復元スケジュールを確認します。</span><span class="sxs-lookup"><span data-stu-id="c74cb-132">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="c74cb-133">インストールのスケジュールをカスタマイズするには、[ **スケジュール**] をクリックし、必要に応じて SQL Server エージェントのスケジュールを調整して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c74cb-133">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="c74cb-134">このスケジュールは、バックアップスケジュールとほぼ同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c74cb-134">This schedule should be approximately the same as the backup schedule.</span></span>

21. <span data-ttu-id="c74cb-135">[ **データベースのプロパティ** ] ダイアログボックスで、[ **OK** ] をクリックして構成プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="c74cb-135">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

