---
title: 'Lync Server 2013: プライマリ ミラーとログ配布セカンダリ データベース間での SQL Server ログ配布のセットアップ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database
ms:assetid: 4e8e9ce9-4301-47f2-a0c3-669afeb53295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204887(v=OCS.15)
ms:contentKeyID: 48184119
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3758e654826de42f6bf6bed8ead29ce03adb6ca5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-sql-server-log-shipping-between-the-primary-mirror-and-the-log-shipping-secondary-database-in-lync-server-2013"></a><span data-ttu-id="44d82-102">Lync Server 2013 でのプライマリ ミラーとログ配布セカンダリ データベース間での SQL Server ログ配布のセットアップ</span><span class="sxs-lookup"><span data-stu-id="44d82-102">Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44d82-103">_**最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="44d82-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="44d82-104">プライマリ常設チャットデータベースがミラーデータベースにフェールオーバーされた場合は、次の手順に従ってログの配布を続行します。</span><span class="sxs-lookup"><span data-stu-id="44d82-104">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>

1.  <span data-ttu-id="44d82-105">プライマリ永続的チャットデータベースをミラーに手動でフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="44d82-105">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="44d82-106">これを行うには、Lync Server 管理シェルと**Invoke-CsDatabaseFailover**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="44d82-106">This is done by using the Lync Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span> <span data-ttu-id="44d82-107">詳細については、「 [lync server 2013 でバックエンドサーバーの高可用性を実現するために SQL ミラーリングを展開](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)する」の「Lync Server 管理シェルコマンドレットの使用」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44d82-107">For details, see "Using Lync Server Management Shell Cmdlets" in [Deploying SQL mirroring for Back End Server high availability in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span></span>

2.  <span data-ttu-id="44d82-108">SQL Server Management Studio を使用して、プライマリ常設チャットサーバーのミラーインスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="44d82-108">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>

3.  <span data-ttu-id="44d82-109">SQL Server エージェントが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="44d82-109">Be sure that the SQL Server Agent is running.</span></span>

4.  <span data-ttu-id="44d82-110">mgc データベースを右クリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="44d82-110">Right-click the mgc database, and then click **Properties**.</span></span>

5.  <span data-ttu-id="44d82-111">[**ページの選択**] で、[**トランザクション ログの配布**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="44d82-111">Under **Select a page**, click **Transaction Log Shipping**.</span></span>

6.  <span data-ttu-id="44d82-112">[**ログ配布構成のプライマリ データベースとして有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="44d82-112">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>

7.  <span data-ttu-id="44d82-113">[**トランザクション ログのバックアップ**] で、[**バックアップの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="44d82-113">Under **Transaction log backups**, click **Backup Settings**.</span></span>

8.  <span data-ttu-id="44d82-114">[**バックアップ フォルダーのネットワーク パスを指定する**] ボックスに、トランザクション ログのバックアップ フォルダーとして作成した共有場所へのネットワーク パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="44d82-114">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>

9.  <span data-ttu-id="44d82-p102">バックアップ フォルダーがプライマリ サーバーに存在する場合は、[**バックアップ フォルダーがプライマリ サーバーに存在する場合は、バックアップ フォルダーのローカル パスを入力**] ボックスにバックアップ フォルダーのローカル パスを入力します (バックアップ フォルダーがプライマリ サーバーに存在しない場合は、このボックスを空のままにします)。</span><span class="sxs-lookup"><span data-stu-id="44d82-p102">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="44d82-117">プライマリサーバーの SQL Server サービスアカウントがローカルシステムアカウントで実行されている場合は、プライマリサーバー上にバックアップフォルダーを作成し、そのフォルダーへのローカルパスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="44d82-117">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span>

    
    </div>

10. <span data-ttu-id="44d82-118">[**次の期間を経過したファイルを削除する**] パラメーターと [**バックアップが次の期間内に行われない場合は警告する**] パラメーターを構成します。</span><span class="sxs-lookup"><span data-stu-id="44d82-118">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>

11. <span data-ttu-id="44d82-119">[**バックアップ ジョブ**] の [**スケジュール**] ボックスに一覧表示されるバックアップ スケジュールを確認してください。</span><span class="sxs-lookup"><span data-stu-id="44d82-119">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="44d82-120">インストールのスケジュールをカスタマイズするには、[**スケジュール**] をクリックし、必要に応じて SQL Server エージェントのスケジュールを調整します。</span><span class="sxs-lookup"><span data-stu-id="44d82-120">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="44d82-121">プライマリ データベースと同じ設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="44d82-121">Use the same settings that you used for the primary database.</span></span>

    
    </div>

12. <span data-ttu-id="44d82-122">[**圧縮**] で、[**既定のサーバー設定を使用する**] をクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="44d82-122">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>

13. <span data-ttu-id="44d82-123">[**セカンダリ サーバー インスタンスとデータベース**] で、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="44d82-123">Under **Secondary server instances and databases**, click **Add**.</span></span>

14. <span data-ttu-id="44d82-124">[**接続**] をクリックして、セカンダリ サーバーとして構成した SQL Server のインスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="44d82-124">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>

15. <span data-ttu-id="44d82-125">[**セカンダリ データベース**] ボックスで、一覧から [**mgc**] データベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="44d82-125">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>

16. <span data-ttu-id="44d82-126">[**セカンダリ データベースの初期化**] タブで、[**いいえ、セカンダリ データベースは初期化されています**] オプションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="44d82-126">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>

17. <span data-ttu-id="44d82-p104">[**ファイルのコピー**] タブの [**ファイルのコピー先フォルダー**] に、トランザクション ログのバックアップをコピーするフォルダーのパスを入力して、[**OK**] をクリックします。多くの場合、このフォルダーは、セカンダリ サーバー上にあります。</span><span class="sxs-lookup"><span data-stu-id="44d82-p104">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**. This folder is often located on the secondary server.</span></span>

18. <span data-ttu-id="44d82-129">[**スクリプトの構成**] ボックスの一覧を開き、[**スクリプト構成を新規クエリ ウィンドウに保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="44d82-129">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>

19. <span data-ttu-id="44d82-130">[**データベースのプロパティ**] に表示された新規クエリ ウィンドウで [**OK**] をクリックして、構成プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="44d82-130">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>

20. <span data-ttu-id="44d82-131">クエリの最初の半分 (手順18を参照) を選んで実行します。--- \* \* \* \* \* \* --------- \* \* \* \* \* \*---------------------------</span><span class="sxs-lookup"><span data-stu-id="44d82-131">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="44d82-132">Sql Server Management Studio では、SQL Server のログ配布構成で複数のプライマリデータベースがサポートされていないため、このスクリプトを手動で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="44d82-132">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span>

    
    </div>

21. <span data-ttu-id="44d82-133">[**キャンセル**] をクリックして、ログ配布構成パネルを閉じ、プライマリ データベースとミラー化されたデータベース (フェールオーバー時) の両方でログ ファイルの配布を適切に実装する実用的なセットアップを確立します。 </span><span class="sxs-lookup"><span data-stu-id="44d82-133">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>

22. <span data-ttu-id="44d82-134">プライマリ常設チャットデータベースを手動でプライマリにフェールバックします。</span><span class="sxs-lookup"><span data-stu-id="44d82-134">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="44d82-135">この操作を行うには、Lync Server 管理シェルと、または「 **CsDatabaseFailover** 」コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="44d82-135">This is done by using the Lync Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span> <span data-ttu-id="44d82-136">詳細については、「 [lync server 2013 でバックエンドサーバーの高可用性を実現するために SQL ミラーリングを展開](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)する」の「Lync Server 管理シェルコマンドレットの使用」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44d82-136">For details, see "Using Lync Server Management Shell Cmdlets" in [Deploying SQL mirroring for Back End Server high availability in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="44d82-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="44d82-137">See Also</span></span>


[<span data-ttu-id="44d82-138">Lync Server 2013 でのバックエンド サーバーの高可用性を実現するための SQL ミラーリングの展開</span><span class="sxs-lookup"><span data-stu-id="44d82-138">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)  
[<span data-ttu-id="44d82-139">Lync Server 2013 でのバックエンド サーバーの高可用性を実現するための SQL ミラーリングの展開</span><span class="sxs-lookup"><span data-stu-id="44d82-139">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

