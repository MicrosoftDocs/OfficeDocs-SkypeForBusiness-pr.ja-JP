---
title: バックエンド サーバーの高可用性を実現するための SQL ミラーリングの展開
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying SQL mirroring for Back End Server high availability
ms:assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204992(v=OCS.15)
ms:contentKeyID: 48184451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8eb8c9647c24f326b1a2a51c99e7fa4ee5eafa23
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833539"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-sql-mirroring-for-back-end-server-high-availability-in-lync-server-2013"></a><span data-ttu-id="fe1ed-102">Lync Server 2013 でのバックエンド サーバーの高可用性を実現するための SQL ミラーリングの展開</span><span class="sxs-lookup"><span data-stu-id="fe1ed-102">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe1ed-103">_**最終更新日:** 2014-01-08_</span><span class="sxs-lookup"><span data-stu-id="fe1ed-103">_**Topic Last Modified:** 2014-01-08_</span></span>

<span data-ttu-id="fe1ed-104">SQL ミラーリングを展開できるようにするには、サーバーで最小限の SQL Server 2008 R2 を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-104">To be able to deploy SQL mirroring, your servers must run a minimum of SQL Server 2008 R2.</span></span> <span data-ttu-id="fe1ed-105">このバージョンは、すべての関連サーバー (プライマリ、ミラー、およびミラーリング監視の各サーバー) で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-105">This version must run on all the involved servers: the primary, mirror, and the witness.</span></span> <span data-ttu-id="fe1ed-106">詳細について[http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921)は、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-106">For details, see [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921).</span></span>

<span data-ttu-id="fe1ed-107">一般に、2 つのバックエンド サーバー間での SQL ミラーリングを設定するには、以下の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-107">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>

  - <span data-ttu-id="fe1ed-108">プライマリ サーバーの SQL Server のバージョンが SQL ミラーリングをサポートしている。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-108">The primary server’s version of SQL Server must support SQL mirroring.</span></span>

  - <span data-ttu-id="fe1ed-109">プライマリ、ミラー、およびミラーリング監視 (展開されている場合) の各 SQL Server が同一バージョンである。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-109">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span>

  - <span data-ttu-id="fe1ed-p102">プライマリおよびミラーの各 SQL Server が同一エディションである (ミラーリング監視のエディションは異なっていても構いません)。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-p102">The primary and the mirror must have the same edition of SQL Server. The witness may have a different edition.</span></span>

<span data-ttu-id="fe1ed-112">監視ロールでサポートされる SQL バージョンについては、SQL のベストプラクティスについては、MSDN ライブラリの「データベースミラーリング[http://go.microsoft.com/fwlink/p/?LinkId=247345](http://go.microsoft.com/fwlink/p/?linkid=247345)の監視」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-112">For SQL best practices in terms of what SQL versions are supported for a Witness role, see "Database Mirroring Witness" in the MSDN Library at [http://go.microsoft.com/fwlink/p/?LinkId=247345](http://go.microsoft.com/fwlink/p/?linkid=247345).</span></span>

<span data-ttu-id="fe1ed-113">SQL ミラーリングを展開するには、トポロジビルダーを使います。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-113">You use Topology Builder to deploy SQL mirroring.</span></span> <span data-ttu-id="fe1ed-114">トポロジビルダーでデータベースをミラーリングするオプションを選ぶと、トポロジビルダーは、トポロジを公開するときに、(必要に応じて、監視の設定を含む) ミラーリングを設定します。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-114">You select an option in Topology Builder to mirror the databases, and Topology Builder sets up the mirroring (including setting up a witness, if you want) when you publish the topology.</span></span> <span data-ttu-id="fe1ed-115">ミラーリング監視は、ミラーの設定または削除と同時に設定または削除することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-115">Note that you set up or remove the witness at the same time you set up or remove the mirror.</span></span> <span data-ttu-id="fe1ed-116">ミラーリング監視のみ展開または削除する独立したコマンドはありません。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-116">There is no separate command to deploy or remove only a witness.</span></span>

<span data-ttu-id="fe1ed-117">サーバー ミラーリングを構成するには、最初に SQL データベース アクセス許可を正しく設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-117">To configure server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="fe1ed-118">詳細については、の「データベースミラーリングまたは AlwaysOn 可用性グループ (SQL Server) のログインアカウント[http://go.microsoft.com/fwlink/p/?LinkId=268454](http://go.microsoft.com/fwlink/p/?linkid=268454)のセットアップ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-118">For details, see "Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=268454](http://go.microsoft.com/fwlink/p/?linkid=268454).</span></span>

<span data-ttu-id="fe1ed-p105">SQL ミラーリングでは、データベース復旧モードは常に [**完全**] に設定されます。これは、トランザクション ログ サイズを綿密に監視し、トランザクション ログを定期的にバックアップしてバックエンド サーバー上のディスク容量の不足を回避する必要があることを意味します。トランザクション ログのバックアップ頻度は、ログの増加率によって決まります。ログの増加率は、フロントエンド プールのユーザー アクティビティによるデータベース トランザクションによって決まります。Lync 展開ワークロードに対して予想されるトランザクション ログの増加を判断し、それに応じて計画することをお勧めします。次の記事では、SQL バックアップおよびログ管理に関する追加情報を提供しています。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-p105">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers. The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool. We recommend that you determine how much transaction log growth is expected for your Lync deployment workload so that you can do the planning accordingly. The following articles provide additional information on SQL backup and log management:</span></span>

  - <span data-ttu-id="fe1ed-123">データベースの回復モデル: "回復モデル (SQL Server)"[http://go.microsoft.com/fwlink/p/?LinkId=268446](http://go.microsoft.com/fwlink/p/?linkid=268446)</span><span class="sxs-lookup"><span data-stu-id="fe1ed-123">Database recovery models: "Recovery Models (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=268446](http://go.microsoft.com/fwlink/p/?linkid=268446)</span></span>

  - <span data-ttu-id="fe1ed-124">バックアップの概要: "バックアップの概要 (SQL Server)" を[http://go.microsoft.com/fwlink/p/?LinkId=268449](http://go.microsoft.com/fwlink/p/?linkid=268449)</span><span class="sxs-lookup"><span data-stu-id="fe1ed-124">Backup overview: "Backup Overview (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=268449](http://go.microsoft.com/fwlink/p/?linkid=268449)</span></span>

  - <span data-ttu-id="fe1ed-125">バックアップトランザクションログ: "トランザクションログ (SQL Server) をバックアップする"[http://go.microsoft.com/fwlink/p/?LinkId=268452](http://go.microsoft.com/fwlink/p/?linkid=268452)</span><span class="sxs-lookup"><span data-stu-id="fe1ed-125">Backup transaction log: "Backup a Transaction Log (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=268452](http://go.microsoft.com/fwlink/p/?linkid=268452)</span></span>

<span data-ttu-id="fe1ed-126">SQL ミラーリングでは、ミラーリングのトポロジの構成を、プールの作成時、またはプールが既に作成された後のどちらでも行うことができます。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-126">With SQL mirroring, you can either configure the topology for mirroring when you create the pools, or after the pools are already created.</span></span>



> [!IMPORTANT]
> <span data-ttu-id="fe1ed-127">SQL ミラーリングのセットアップと削除を行うためのトポロジビルダーまたはコマンドレットの使用は、プライマリ、ミラー、および監視 (必要な場合) サーバーがすべて同じドメインに属している場合にのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-127">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="fe1ed-128">異なるドメインのサーバーに SQL ミラーリングを設定する場合は、SQL Server のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-128">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span>





> [!IMPORTANT]
> <span data-ttu-id="fe1ed-129">バックエンド データベース ミラーリング関係を変更するたびに、プール内のすべてのフロントエンド サーバーを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-129">Whenever you make a change to a Back End Database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span><BR><span data-ttu-id="fe1ed-130">ミラーリング (ミラーの場所の変更など) を変更する場合は、次の3つの手順を実行するためにトポロジビルダーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-130">For a change in mirroring, (such as changing the location of a mirror), you must use Topology Builder to perform these three steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="fe1ed-131">古いミラー サーバーからミラーリングを削除します。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-131">Remove mirroring from the old mirror server.</span></span></P>
> <LI>
> <P><span data-ttu-id="fe1ed-132">新しいミラー サーバーにミラーリングを追加します。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-132">Add mirroring to the new mirror server.</span></span></P>
> <LI>
> <P><span data-ttu-id="fe1ed-133">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-133">Publish the topology.</span></span></P></LI></OL>




> [!NOTE]
> <span data-ttu-id="fe1ed-134">書き込み先のミラーファイルに対してファイル共有を作成し、SQL Server と SQL エージェントが実行されているサービスが読み取り/書き込みアクセスを必要とするようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-134">A file share has to be created for the mirror files to be written to, and the service that SQL Server and SQL Agent are running under needs read/write access.</span></span> <span data-ttu-id="fe1ed-135">SQL Server サービスが Network Service のコンテキストで実行されている場合は、 &lt;プリンシパル&gt;と&lt;ミラーの&gt;SQL server の両方のドメイン&#92;sqlservername $ を共有アクセス許可に追加できます。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-135">If the SQL Server service is running under the context of Network Service, you can add &lt;Domain&gt;&#92;&lt;SQLSERVERNAME&gt;$ of both the Principal and Mirror SQL Servers to the share permissions.</span></span> <span data-ttu-id="fe1ed-136">$ は、これがコンピュータアカウントであることを特定するために重要です。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-136">The $ is important to identify that this is a computer account.</span></span>


<div>

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a><span data-ttu-id="fe1ed-137">トポロジビルダーでプールを作成するときに SQL ミラーリングを構成するには</span><span class="sxs-lookup"><span data-stu-id="fe1ed-137">To configure SQL mirroring while creating a pool in Topology Builder</span></span>

1.  <span data-ttu-id="fe1ed-138">[**SQL ストアの定義**] ページで、[**SQL ストア**] ボックスの隣にある [**新規作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-138">On the **Define the SQL Store** page, click **New** next to the **SQL store** box.</span></span>

2.  <span data-ttu-id="fe1ed-139">[**新しい SQL ストアの定義**] ページで、プライマリ ストアを指定し、[**この SQL インスタンスはミラーリングの関係にある **] を選択して、SQL ミラーリングのポート番号 (既定値は 5022) を指定したうえで [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-139">On the **Define new SQL Store** page, specify the primary store, select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default is 5022), and then click **OK**.</span></span>

3.  <span data-ttu-id="fe1ed-140">[**SQL ストアの定義**] ページに戻ったら、[**SQL ストアのミラーリングを有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-140">Back on the **Define the SQL store** page, select **Enable SQL Store mirroring**.</span></span>

4.  <span data-ttu-id="fe1ed-p108">[**新しい SQL ストアの定義**] ページで、ミラーとして使用する SQL ストアを指定し、[**この SQL インスタンスはミラーリングの関係にある**] を選択して、ポート番号 (既定値は 5022) を指定したうえで [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-p108">In the **Define new SQL Store** page, specify the SQL store to be used as the mirror. Select **This SQL instance is in mirroring relation**, specify the port number (the default is 5022), and then click **OK**.</span></span>

5.  <span data-ttu-id="fe1ed-143">このミラーのミラーリング監視が必要な場合は、以下の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-143">If you want a witness for this mirror, do the following:</span></span>
    
    1.  <span data-ttu-id="fe1ed-144">[**SQL ミラーリング監視を使用して自動フェールオーバーを有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-144">Select **Use SQL mirroring witness to enable automatic failover**.</span></span>
    
    2.  <span data-ttu-id="fe1ed-145">[**SQL ストアの定義**] ページで、[**SQL ミラーリング監視を使用して自動フェールオーバーを有効にする**] を選択し、ミラーリング監視として使用する SQL ストアを指定します。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-145">In the **Define the SQL Store** page, select **Use SQL mirroring witness to enable automatic failover**, and specify the SQL store to be used as the witness.</span></span>
    
    3.  <span data-ttu-id="fe1ed-146">ポート番号 (既定値は 7022) を指定し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-146">Specify the port number (the default is 7022) and click **OK**.</span></span>

6.  <span data-ttu-id="fe1ed-147">フロントエンドプールとトポロジ内の他のすべての役割の定義が完了したら、トポロジビルダーを使用してトポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-147">After you are done defining your Front End pool and all other roles in your topology, use Topology Builder to publish the topology.</span></span> <span data-ttu-id="fe1ed-148">トポロジが公開されている場合、中央管理ストアをホストするフロントエンドプールに SQL ミラーリングが有効になっていると、プライマリとミラーの両方の SQL ストアデータベースを作成するオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-148">When the topology is published, if the Front End pool that hosts Central Management store has SQL mirroring enabled, you will see an option to create both primary and mirror SQL store databases.</span></span>
    
    <span data-ttu-id="fe1ed-149">[**設定**] をクリックし、ミラーリング バックアップのファイル共有として使用するパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-149">Click **Settings**, and type the path to use as the file share for the mirroring backup.</span></span>
    
    <span data-ttu-id="fe1ed-p110">[**OK**]、[**次へ**] の順にクリックして、データベースを作成し、トポロジを公開します。ミラーリングとミラーリング監視 (指定した場合) が展開されます。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-p110">Click **OK** and then **Next** to create the databases and publish the topology. The mirroring and the witness (if specified) will be deployed.</span></span>

<span data-ttu-id="fe1ed-152">トポロジビルダーを使用して、既存のプールのプロパティを編集し、SQL のミラーリングを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-152">You can use Topology Builder to edit the properties of an already existing pool to enable SQL mirroring.</span></span>

</div>

<div>

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a><span data-ttu-id="fe1ed-153">トポロジビルダーで既存のフロントエンドプールに SQL ミラーリングを追加するには</span><span class="sxs-lookup"><span data-stu-id="fe1ed-153">To add SQL mirroring to an existing Front End pool in Topology Builder</span></span>

1.  <span data-ttu-id="fe1ed-154">トポロジビルダーで、プールを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-154">In Topology Builder, right-click the pool and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="fe1ed-155">[**SQL ストアのミラーリングを有効にする**] を選択し、[**ミラーリング SQL ストア**] の横にある [**新規作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-155">Select **Enable SQL Store Mirroring**, and then click **New** next to **Mirroring SQL Store**.</span></span>

3.  <span data-ttu-id="fe1ed-156">ミラーとして使用する SQL ストアを指定します。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-156">Specify the SQL store that you want to use as the mirror.</span></span>

4.  <span data-ttu-id="fe1ed-157">[**この SQL インスタンスはミラーリングの関係にある**] を選択し、SQL ミラーリングのポート番号 (既定のポートは 5022 番) を指定して、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-157">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number the default port is 5022), and then click **OK**.</span></span>

5.  <span data-ttu-id="fe1ed-158">ミラーリング監視を構成する場合は、[**SQL ミラーリング監視を使用して自動フェールオーバーを有効にする**] を選択し、[**新規作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-158">If you want to configure a witness, select **Use SQL mirroring witness to enable automatic failover**, and click **New**.</span></span>

6.  <span data-ttu-id="fe1ed-159">ミラーリング監視として使用する SQL ストアを指定します。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-159">Specify the SQL store that you want to use as the witness.</span></span>

7.  <span data-ttu-id="fe1ed-160">[**この SQL インスタンスはミラーリングの関係にある**] を選択し、SQL ミラーリングのポート番号 (既定のポートは 7022 番) を指定して、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-160">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default port is 7022), and then click **OK**.</span></span>

8.  <span data-ttu-id="fe1ed-161">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-161">Click **OK**.</span></span>

9.  <span data-ttu-id="fe1ed-p111">トポロジを公開します。この操作を行うと、データベースをインストールするように求められます。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-p111">Publish the topology. When you do so, you will be prompted to install the database.</span></span>
    
    <span data-ttu-id="fe1ed-p112">トポロジ公開プロセスでは、ファイル共有パスの入力を求められます。ミラーリングを確立するには、ミラーリングに参加するすべての SQL Server に、このファイル共有への読み取り/書き込みのアクセス権が必要です。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-p112">During the topology publishing process, you will be asked to define a file share path. The SQL Servers that participate in the mirroring must have read/write access to this file share for the mirror to be established.</span></span>

<span data-ttu-id="fe1ed-166">その場合、次の手順に進む前にデータベースをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-166">You must then install the database before going on to the next procedure.</span></span>

<span data-ttu-id="fe1ed-167">SQL ミラーリングの設定時には次の点に留意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-167">You should keep the following in mind when setting up SQL mirroring:</span></span>

  - <span data-ttu-id="fe1ed-168">既に存在するミラーリング エンドポイントは、そこに定義されたポートを使用して再利用され、トポロジ内で指定したポートは無視されます。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-168">If a mirroring endpoint already exists, it will be reused using the ports defined there, and will ignore the ones you specify in the topology.</span></span>

  - <span data-ttu-id="fe1ed-p113">同じサーバー上の他のアプリケーションに既に割り当てられたポート (他の SQL インスタンス用のポートを含みます) は、ここでインストールする SQL インスタンスでは使用しないでください。これは、複数の SQL インスタンスを同じサーバー上にインストールしている場合、それらのインスタンスは同じポートをミラーリングに使用してはならないことを意味します。詳細については、以下の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-p113">Any port already allocated for other applications on the same server, including those for other SQL instances, should not be used for the installed SQL instances at hand. This implies that if you have more than one SQL instance installed on the same server, they must not use the same port for mirroring. For details, see the following articles:</span></span>
    
      - <span data-ttu-id="fe1ed-172">MSDN ライブラリの [サーバーネットワークアドレス (データベースのミラーリング) を指定してください][http://go.microsoft.com/fwlink/p/?LinkId=247346](http://go.microsoft.com/fwlink/p/?linkid=247346)</span><span class="sxs-lookup"><span data-stu-id="fe1ed-172">"Specify a Server Network Address (Database Mirroring)" in the MSDN Library at [http://go.microsoft.com/fwlink/p/?LinkId=247346](http://go.microsoft.com/fwlink/p/?linkid=247346)</span></span>
    
      - <span data-ttu-id="fe1ed-173">"データベースミラーリングエンドポイント (SQL Server)"[http://go.microsoft.com/fwlink/p/?LinkId=247347](http://go.microsoft.com/fwlink/p/?linkid=247347)</span><span class="sxs-lookup"><span data-stu-id="fe1ed-173">"The Database Mirroring Endpoint (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=247347](http://go.microsoft.com/fwlink/p/?linkid=247347)</span></span>

</div>

<div>

## <a name="using-lync-server-management-shell-cmdlets-to-set-up-sql-mirroring"></a><span data-ttu-id="fe1ed-174">Lync Server Management Shell コマンドレットを使用して SQL ミラーリングを設定する</span><span class="sxs-lookup"><span data-stu-id="fe1ed-174">Using Lync Server Management Shell Cmdlets to Set Up SQL Mirroring</span></span>

<span data-ttu-id="fe1ed-175">ミラーリングを設定する最も簡単な方法は、トポロジビルダーを使用することですが、コマンドレットを使って行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-175">The easiest way to set up mirroring is by using Topology Builder, but you can also do so using cmdlets.</span></span>

1.  <span data-ttu-id="fe1ed-176">Lync Server 管理シェルウィンドウを開いて、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-176">Open a Lync Server Management Shell window and run the following cmdlet:</span></span>
    
        Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose 
    
    <span data-ttu-id="fe1ed-177">例:</span><span class="sxs-lookup"><span data-stu-id="fe1ed-177">For example:</span></span>
    
        Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose 
    
    <span data-ttu-id="fe1ed-178">以下のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-178">You will see the following:</span></span>
    
        Database Name:rtcxds 
                Data File:D:\CsData\BackendStore\rtc\DbPath\rtcxds.mdf 
                 Log File:D:\CsData\BackendStore\rtc\LogPath\rtcxds.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rtcshared 
                Data File:D:\CsData\BackendStore\rtc\DbPath\rtcshared.mdf 
                 Log File:D:\CsData\BackendStore\rtc\LogPath\rtcshared.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rtcab 
                Data File:D:\CsData\ABSStore\rtc\DbPath\rtcab.mdf 
                 Log File:D:\CsData\ABSStore\rtc\LogPath\rtcab.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rgsconfig 
                Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsconfig.mdf 
                 Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsconfig.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rgsdyn 
                Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsdyn.mdf 
                 Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsdyn.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:cpsdyn 
                Data File:D:\CsData\ApplicationStore\rtc\DbPath\cpsdyn.mdf 
                 Log File:D:\CsData\ApplicationStore\rtc\LogPath\cpsdyn.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:xds 
                Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\xds.mdf 
                 Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\xds.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:lis 
                Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\lis.mdf 
                 Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\lis.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$
        [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): 

2.  <span data-ttu-id="fe1ed-179">次のことを確認します。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-179">Verify the following:</span></span>
    
      - <span data-ttu-id="fe1ed-180">プライマリ SQL Server e04-ocs\_\\Rtc で Windows ファイアウォールが有効になっている場合、ポート5022はファイアウォールを介してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-180">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the primary SQL Server e04-ocs.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="fe1ed-181">ミラー化された SQL Server K16-ocs\_\\Rtc で Windows ファイアウォールが有効になっている場合、ファイアウォール経由でポート5022にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-181">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the mirror SQL Server K16-ocs.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="fe1ed-182">監視 SQL Server AB14-lct\_\\Rtc で Windows ファイアウォールが有効になっている場合、ポート7022はファイアウォールを介してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-182">Port 7022 is accessible through the firewall if Windows Firewall is enabled in the witness SQL Server AB14-lct.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="fe1ed-183">すべてのプライマリとミラーの sql server で実行されているアカウントは、ファイル共有\\ \\E04\\の読み取り/書き込みアクセス許可を持っています。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-183">Accounts running the SQL Servers on all primary and mirror SQL servers have read/write permission to the file share \\\\E04-OCS\\csdatabackup</span></span>
    
      - <span data-ttu-id="fe1ed-p114">これらすべてのサーバーで、Windows Management Instrumentation (WMI) プロバイダーが実行されている。コマンドレットでは、このプロバイダーを使用して、すべてのプライマリ サーバー、ミラー サーバー、およびミラーリング監視サーバーで実行されている SQL Server サービスのアカウント情報が検索されます。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-p114">Verify that the Windows Management Instrumentation (WMI) provider is running on all these servers. The cmdlet uses this provider to find the account information for SQL Server services running on all primary, mirror and witness servers.</span></span>
    
      - <span data-ttu-id="fe1ed-186">このコマンドレットを実行しているアカウントに、すべてのミラー サーバーのデータおよびログ ファイル用のフォルダーを作成するためのアクセス許可がある。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-186">Verify that the account running this cmdlet has permission to create the folders for the data and log files for all the mirror servers.</span></span>
    
      - <span data-ttu-id="fe1ed-p115">SQL インスタンスの実行に使用するユーザー アカウントに、ファイル共有に対する読み取り/書き込みアクセス許可が必要であることに注意してください。ファイル共有が別のサーバーにあり、SQL インスタンスがローカル システム アカウントを実行している場合は、SQL インスタンスをホストするサーバーへのファイル共有アクセス許可を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-p115">Note that the user account that the SQL instance uses to run must have read/write permission to the file share. If the file share is on a different server, and the SQL instance runs a local system account, you must grant file share permissions to the server that hosts the SQL instance.</span></span>

3.  <span data-ttu-id="fe1ed-189">「A」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-189">Type A and press ENTER.</span></span>
    
    <span data-ttu-id="fe1ed-190">ミラーリングの構成が行われます。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-190">The mirroring will be configured.</span></span>

<span data-ttu-id="fe1ed-191">**CsMirrorDatabase をインストール**すると、ミラーがインストールされ、プライマリ SQL ストアに存在するすべてのデータベースのミラーリングが構成されます。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-191">**Install-CsMirrorDatabase** installs the mirror and configures mirroring for all the databases that are present on the primary SQL store.</span></span> <span data-ttu-id="fe1ed-192">特定のデータベースに対してのみミラーリングを構成する場合は、– DatabaseType オプションを使用できます。また、少数を除くすべてのデータベースのミラーリングを構成する場合は、-ExcludeDatabaseList オプションと、少数のデータベースのコンマ区切りリストを使うことができます。除外する名前。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-192">If you want to configure mirroring for only specific databases, you can use the –DatabaseType option, or if you want to configure mirroring for all databases except for a few, you can use the -ExcludeDatabaseList option, along with a comma-separated list of database names to exclude.</span></span>

<span data-ttu-id="fe1ed-193">たとえば、次のオプションを **Install-CsMirrorDatabase** に追加した場合は、rtcab と rtcxds を除くすべてのデータベースがミラーリングされます。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-193">For example, if you add the following option to **Install-CsMirrorDatabase**, all databases except rtcab and rtcxds will be mirrored.</span></span>

`-ExcludeDatabaseList rtcab,rtcxds`

<span data-ttu-id="fe1ed-194">たとえば、次のオプションを **Install-CsMirrorDatabase** に追加した場合は、rtcab、rtcshared、および rtcxds データベースのみがミラーリングされます。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-194">For example, if you add the following option to **Install-CsMirrorDatabase**, only the rtcab, rtcshared, and rtcxds databases will be mirrored.</span></span>

`-DatabaseType User`

</div>

<div>

## <a name="removing-or-changing-sql-mirroring"></a><span data-ttu-id="fe1ed-195">SQL ミラーリングの削除または変更</span><span class="sxs-lookup"><span data-stu-id="fe1ed-195">Removing or Changing SQL Mirroring</span></span>

<span data-ttu-id="fe1ed-p117">トポロジ ビルダーのプールの SQL ミラーリングを削除するには、最初にコマンドレットを使用して、SQL Server のミラーを削除する必要があります。次に、トポロジ ビルダーを使用して、トポロジからミラーを削除できます。SQL Server でミラーを削除するには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-p117">To remove the SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server. You can then use Topology Builder to remove the mirror from the topology. To remove the mirror in SQL Server, use the following cmdlet:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

<span data-ttu-id="fe1ed-199">たとえば、ミラーリングを削除し、User データベースのデータベースを削除するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-199">For example, to remove mirroring and drop the databases for the User databases, type the following:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

<span data-ttu-id="fe1ed-200">この`-DropExistingDatabasesOnMirror`オプションを選択すると、影響を受けるデータベースがミラーから削除されます。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-200">The `-DropExistingDatabasesOnMirror` option causes the affected databases to be deleted from the mirror.</span></span>

<span data-ttu-id="fe1ed-201">その後、トポロジからミラーを削除するために次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-201">Then, to remove the mirror from the topology, do the following:</span></span>

1.  <span data-ttu-id="fe1ed-202">トポロジ ビルダーで、プールを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-202">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="fe1ed-203">[**SQL ストアのミラーリングを有効にする**] チェック ボックスをオフにし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-203">Uncheck **Enable SQL Store Mirroring** and click **OK**.</span></span>

3.  <span data-ttu-id="fe1ed-204">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-204">Publish the topology.</span></span>

</div>

<div>

## <a name="removing-a-mirroring-witness"></a><span data-ttu-id="fe1ed-205">ミラーリング監視の削除</span><span class="sxs-lookup"><span data-stu-id="fe1ed-205">Removing a Mirroring Witness</span></span>

<span data-ttu-id="fe1ed-206">バックエンドサーバーのミラーリング構成から監視を削除する必要がある場合は、この手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-206">Use this procedure if you need to remove the witness from a Back End Server mirroring configuration.</span></span>

1.  <span data-ttu-id="fe1ed-207">トポロジ ビルダーで、プールを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-207">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="fe1ed-208">[**SQL Server ミラーリング監視を自動フェールオーバーの有効化のために使用**] をオフにし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-208">Uncheck **Use SQL Server mirroring witness to enable automatic failover** and click **OK**.</span></span>

3.  <span data-ttu-id="fe1ed-209">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-209">Publish the topology.</span></span>
    
    <span data-ttu-id="fe1ed-210">トポロジを公開すると、次のようなメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-210">After publishing the topology, Topology Builder you will see a message that includes the following</span></span>
    
        Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
    
    <span data-ttu-id="fe1ed-211">ただし、この手順に従ってはいけません。 `Uninstall-CsMirrorDatabase`また、ミラーリング構成全体をアンインストールするのと同じように入力しないでください。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-211">However, do not follow that step, and do not type `Uninstall-CsMirrorDatabase` as that would uninstall the entire mirroring configuration.</span></span>

4.  <span data-ttu-id="fe1ed-212">SQL Server の構成から監視のみを削除するには、の「データベースミラーリングセッション (SQL Server) からのミラーリングの削除」の手順[http://go.microsoft.com/fwlink/p/?LinkId=268456](http://go.microsoft.com/fwlink/p/?linkid=268456)に従います。</span><span class="sxs-lookup"><span data-stu-id="fe1ed-212">To remove just the witness from the SQL Server configuration, follow the instructions in "Remove the Witness from a Database Mirroring Session (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=268456](http://go.microsoft.com/fwlink/p/?linkid=268456).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

