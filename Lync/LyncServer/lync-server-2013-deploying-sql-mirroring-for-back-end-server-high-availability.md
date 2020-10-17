---
title: バックエンドサーバーの高可用性を実現するための SQL ミラーリングの展開
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying SQL mirroring for Back End Server high availability
ms:assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204992(v=OCS.15)
ms:contentKeyID: 48184451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 085b7c10416fddefa8b869bbb617160f03b1e89a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522944"
---
# <a name="deploying-sql-mirroring-for-back-end-server-high-availability-in-lync-server-2013"></a><span data-ttu-id="46d19-102">Lync Server 2013 でバックエンドサーバーの高可用性を実現するための SQL ミラーリングの展開</span><span class="sxs-lookup"><span data-stu-id="46d19-102">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46d19-103">_**トピックの最終更新日:** 2014-01-08_</span><span class="sxs-lookup"><span data-stu-id="46d19-103">_**Topic Last Modified:** 2014-01-08_</span></span>

<span data-ttu-id="46d19-104">SQL ミラーリングを展開できるようにするには、サーバーで最小限の SQL Server 2008 R2 を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46d19-104">To be able to deploy SQL mirroring, your servers must run a minimum of SQL Server 2008 R2.</span></span> <span data-ttu-id="46d19-105">このバージョンは、すべての関連サーバー (プライマリ、ミラー、およびミラーリング監視の各サーバー) で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46d19-105">This version must run on all the involved servers: the primary, mirror, and the witness.</span></span> <span data-ttu-id="46d19-106">詳細については、「」を参照してください [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921) 。</span><span class="sxs-lookup"><span data-stu-id="46d19-106">For details, see [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921).</span></span>

<span data-ttu-id="46d19-107">一般に、2 つのバックエンド サーバー間での SQL ミラーリングを設定するには、以下の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="46d19-107">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>

  - <span data-ttu-id="46d19-108">プライマリ サーバーの SQL Server のバージョンが SQL ミラーリングをサポートしている。</span><span class="sxs-lookup"><span data-stu-id="46d19-108">The primary server’s version of SQL Server must support SQL mirroring.</span></span>

  - <span data-ttu-id="46d19-109">プライマリ、ミラー、およびミラーリング監視 (展開されている場合) の各 SQL Server が同一バージョンである。</span><span class="sxs-lookup"><span data-stu-id="46d19-109">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span>

  - <span data-ttu-id="46d19-p102">プライマリおよびミラーの各 SQL Server が同一エディションである (ミラーリング監視のエディションは異なっていても構いません)。</span><span class="sxs-lookup"><span data-stu-id="46d19-p102">The primary and the mirror must have the same edition of SQL Server. The witness may have a different edition.</span></span>

<span data-ttu-id="46d19-112">ミラーリング監視の役割でサポートされる SQL のバージョンに関する SQL のベストプラクティスについては、MSDN ライブラリの「データベースミラーリング監視」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=247345](https://go.microsoft.com/fwlink/p/?linkid=247345) 。</span><span class="sxs-lookup"><span data-stu-id="46d19-112">For SQL best practices in terms of what SQL versions are supported for a Witness role, see "Database Mirroring Witness" in the MSDN Library at [https://go.microsoft.com/fwlink/p/?LinkId=247345](https://go.microsoft.com/fwlink/p/?linkid=247345).</span></span>

<span data-ttu-id="46d19-113">SQL ミラーリングを展開するには、トポロジビルダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="46d19-113">You use Topology Builder to deploy SQL mirroring.</span></span> <span data-ttu-id="46d19-114">トポロジビルダーでデータベースをミラー化するオプションを選択すると、トポロジビルダーは、トポロジを公開するときに、ミラーリング (必要な場合は、監視の設定を含む) を設定します。</span><span class="sxs-lookup"><span data-stu-id="46d19-114">You select an option in Topology Builder to mirror the databases, and Topology Builder sets up the mirroring (including setting up a witness, if you want) when you publish the topology.</span></span> <span data-ttu-id="46d19-115">ミラーリング監視は、ミラーの設定または削除と同時に設定または削除します。</span><span class="sxs-lookup"><span data-stu-id="46d19-115">Note that you set up or remove the witness at the same time you set up or remove the mirror.</span></span> <span data-ttu-id="46d19-116">ミラーリング監視のみ展開または削除する独立したコマンドはありません。</span><span class="sxs-lookup"><span data-stu-id="46d19-116">There is no separate command to deploy or remove only a witness.</span></span>

<span data-ttu-id="46d19-117">サーバー ミラーリングを構成するには、最初に SQL データベース アクセス許可を正しく設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46d19-117">To configure server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="46d19-118">詳細については、「」の「データベースミラーリングまたは AlwaysOn 可用性グループのログインアカウントをセットアップする (SQL Server)」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=268454](https://go.microsoft.com/fwlink/p/?linkid=268454) 。</span><span class="sxs-lookup"><span data-stu-id="46d19-118">For details, see "Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268454](https://go.microsoft.com/fwlink/p/?linkid=268454).</span></span>

<span data-ttu-id="46d19-p105">SQL ミラーリングでは、データベース復旧モードは常に [**完全**] に設定されます。これは、トランザクション ログ サイズを綿密に監視し、トランザクション ログを定期的にバックアップしてバックエンド サーバー上のディスク容量の不足を回避する必要があることを意味します。トランザクション ログのバックアップ頻度は、ログの増加率によって決まります。ログの増加率は、フロントエンド プールのユーザー アクティビティによるデータベース トランザクションによって決まります。Lync 展開ワークロードに対して予想されるトランザクション ログの増加を判断し、それに応じて計画することをお勧めします。次の記事では、SQL バックアップおよびログ管理に関する追加情報を提供しています。</span><span class="sxs-lookup"><span data-stu-id="46d19-p105">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers. The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool. We recommend that you determine how much transaction log growth is expected for your Lync deployment workload so that you can do the planning accordingly. The following articles provide additional information on SQL backup and log management:</span></span>

  - <span data-ttu-id="46d19-123">データベース回復モデル: "復旧モデル (SQL Server)" [https://go.microsoft.com/fwlink/p/?LinkId=268446](https://go.microsoft.com/fwlink/p/?linkid=268446)</span><span class="sxs-lookup"><span data-stu-id="46d19-123">Database recovery models: "Recovery Models (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268446](https://go.microsoft.com/fwlink/p/?linkid=268446)</span></span>

  - <span data-ttu-id="46d19-124">バックアップの概要: 「バックアップの概要 (SQL Server)」 [https://go.microsoft.com/fwlink/p/?LinkId=268449](https://go.microsoft.com/fwlink/p/?linkid=268449)</span><span class="sxs-lookup"><span data-stu-id="46d19-124">Backup overview: "Backup Overview (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268449](https://go.microsoft.com/fwlink/p/?linkid=268449)</span></span>

  - <span data-ttu-id="46d19-125">バックアップトランザクションログ: "トランザクションログのバックアップ (SQL Server)" [https://go.microsoft.com/fwlink/p/?LinkId=268452](https://go.microsoft.com/fwlink/p/?linkid=268452)</span><span class="sxs-lookup"><span data-stu-id="46d19-125">Backup transaction log: "Backup a Transaction Log (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268452](https://go.microsoft.com/fwlink/p/?linkid=268452)</span></span>

<span data-ttu-id="46d19-126">SQL ミラーリングでは、ミラーリングのトポロジの構成を、プールの作成時、またはプールが既に作成された後のどちらでも行うことができます。</span><span class="sxs-lookup"><span data-stu-id="46d19-126">With SQL mirroring, you can either configure the topology for mirroring when you create the pools, or after the pools are already created.</span></span>



> [!IMPORTANT]
> <span data-ttu-id="46d19-127">トポロジビルダーまたはコマンドレットを使用した SQL ミラーリングの設定および削除は、プライマリ、ミラー、およびミラーリング監視 (必要な場合) がすべて同じドメインに属している場合にのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="46d19-127">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="46d19-128">異なるドメインのサーバーに SQL ミラーリングを設定する場合は、SQL Server のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="46d19-128">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span>





> [!IMPORTANT]
> <span data-ttu-id="46d19-129">バックエンド データベース ミラーリング関係を変更するたびに、プール内のすべてのフロントエンド サーバーを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46d19-129">Whenever you make a change to a Back End Database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span><BR><span data-ttu-id="46d19-130">ミラーリングの変更 (ミラーの場所の変更など) については、トポロジビルダーを使用して、次の3つの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46d19-130">For a change in mirroring, (such as changing the location of a mirror), you must use Topology Builder to perform these three steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="46d19-131">古いミラー サーバーからミラーリングを削除します。</span><span class="sxs-lookup"><span data-stu-id="46d19-131">Remove mirroring from the old mirror server.</span></span></P>
> <LI>
> <P><span data-ttu-id="46d19-132">新しいミラー サーバーにミラーリングを追加します。</span><span class="sxs-lookup"><span data-stu-id="46d19-132">Add mirroring to the new mirror server.</span></span></P>
> <LI>
> <P><span data-ttu-id="46d19-133">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="46d19-133">Publish the topology.</span></span></P></LI></OL>




> [!NOTE]
> <span data-ttu-id="46d19-134">ミラーファイルに書き込むためのファイル共有を作成する必要があります。また、SQL Server と SQL エージェントが実行しているサービスには、読み取り/書き込みアクセス権が必要です。</span><span class="sxs-lookup"><span data-stu-id="46d19-134">A file share has to be created for the mirror files to be written to, and the service that SQL Server and SQL Agent are running under needs read/write access.</span></span> <span data-ttu-id="46d19-135">SQL Server サービスがネットワークサービスのコンテキストで実行されている場合は、 &lt; ドメイン &gt;&#92;&lt; Sqlservername &gt; $ のプリンシパルとミラーの両方の sql サーバーを共有のアクセス許可に追加できます。</span><span class="sxs-lookup"><span data-stu-id="46d19-135">If the SQL Server service is running under the context of Network Service, you can add &lt;Domain&gt;&#92;&lt;SQLSERVERNAME&gt;$ of both the Principal and Mirror SQL Servers to the share permissions.</span></span> <span data-ttu-id="46d19-136">$ は、これがコンピューターアカウントであることを識別するために重要です。</span><span class="sxs-lookup"><span data-stu-id="46d19-136">The $ is important to identify that this is a computer account.</span></span>


<div>

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a><span data-ttu-id="46d19-137">トポロジビルダーでプールを作成しているときに SQL ミラーリングを構成するには</span><span class="sxs-lookup"><span data-stu-id="46d19-137">To configure SQL mirroring while creating a pool in Topology Builder</span></span>

1.  <span data-ttu-id="46d19-138">[**SQL ストアの定義**] ページで、[**SQL ストア**] ボックスの横にある [**新規作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46d19-138">On the **Define the SQL Store** page, click **New** next to the **SQL store** box.</span></span>

2.  <span data-ttu-id="46d19-139">[**新しい SQL ストアの定義**] ページで、プライマリ ストアを指定し、[**この SQL インスタンスはミラーリングの関係にある**] を選択して、SQL ミラーリングのポート番号 (既定値は 5022) を指定したうえで [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46d19-139">On the **Define new SQL Store** page, specify the primary store, select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default is 5022), and then click **OK**.</span></span>

3.  <span data-ttu-id="46d19-140">[**SQL ストアの定義**] ページに戻ったら、[**SQL ストアのミラーリングを有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="46d19-140">Back on the **Define the SQL store** page, select **Enable SQL Store mirroring**.</span></span>

4.  <span data-ttu-id="46d19-p108">[**新しい SQL ストアの定義**] ページで、ミラーとして使用する SQL ストアを指定し、[**この SQL インスタンスはミラーリングの関係にある**] を選択して、ポート番号 (既定値は 5022) を指定したうえで [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46d19-p108">In the **Define new SQL Store** page, specify the SQL store to be used as the mirror. Select **This SQL instance is in mirroring relation**, specify the port number (the default is 5022), and then click **OK**.</span></span>

5.  <span data-ttu-id="46d19-143">このミラーのミラーリング監視が必要な場合は、以下の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="46d19-143">If you want a witness for this mirror, do the following:</span></span>
    
    1.  <span data-ttu-id="46d19-144">[**SQL ミラーリング監視を使用して自動フェールオーバーを有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="46d19-144">Select **Use SQL mirroring witness to enable automatic failover**.</span></span>
    
    2.  <span data-ttu-id="46d19-145">[**SQL ストアの定義**] ページで、[**SQL ミラーリング監視を使用して自動フェールオーバーを有効にする**] を選択し、ミラーリング監視として使用する SQL ストアを指定します。</span><span class="sxs-lookup"><span data-stu-id="46d19-145">In the **Define the SQL Store** page, select **Use SQL mirroring witness to enable automatic failover**, and specify the SQL store to be used as the witness.</span></span>
    
    3.  <span data-ttu-id="46d19-146">ポート番号 (既定値は 7022) を指定し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46d19-146">Specify the port number (the default is 7022) and click **OK**.</span></span>

6.  <span data-ttu-id="46d19-147">フロントエンドプールの定義とトポロジ内の他のすべての役割を終えたら、トポロジビルダーを使用してトポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="46d19-147">After you are done defining your Front End pool and all other roles in your topology, use Topology Builder to publish the topology.</span></span> <span data-ttu-id="46d19-148">トポロジの公開時に、中央管理ストアをホストするフロントエンドプールの SQL ミラーリングが有効になっている場合は、プライマリとミラーの両方の SQL ストアデータベースを作成するオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="46d19-148">When the topology is published, if the Front End pool that hosts Central Management store has SQL mirroring enabled, you will see an option to create both primary and mirror SQL store databases.</span></span>
    
    <span data-ttu-id="46d19-149">[**設定**] をクリックし、ミラーリング バックアップのファイル共有として使用するパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="46d19-149">Click **Settings**, and type the path to use as the file share for the mirroring backup.</span></span>
    
    <span data-ttu-id="46d19-p110">[**OK**]、[**次へ**] の順にクリックして、データベースを作成し、トポロジを公開します。ミラーリングとミラーリング監視 (指定した場合) が展開されます。</span><span class="sxs-lookup"><span data-stu-id="46d19-p110">Click **OK** and then **Next** to create the databases and publish the topology. The mirroring and the witness (if specified) will be deployed.</span></span>

<span data-ttu-id="46d19-152">トポロジビルダーを使用して、既存のプールのプロパティを編集し、SQL ミラーリングを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="46d19-152">You can use Topology Builder to edit the properties of an already existing pool to enable SQL mirroring.</span></span>

</div>

<div>

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a><span data-ttu-id="46d19-153">トポロジビルダーで既存のフロントエンドプールに SQL ミラーリングを追加するには</span><span class="sxs-lookup"><span data-stu-id="46d19-153">To add SQL mirroring to an existing Front End pool in Topology Builder</span></span>

1.  <span data-ttu-id="46d19-154">トポロジビルダーで、プールを右クリックし、[ **プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46d19-154">In Topology Builder, right-click the pool and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="46d19-155">[**SQL ストアのミラーリングを有効にする**] を選択し、[**ミラーリング SQL ストア**] の横にある [**新規作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46d19-155">Select **Enable SQL Store Mirroring**, and then click **New** next to **Mirroring SQL Store**.</span></span>

3.  <span data-ttu-id="46d19-156">ミラーとして使用する SQL ストアを指定します。</span><span class="sxs-lookup"><span data-stu-id="46d19-156">Specify the SQL store that you want to use as the mirror.</span></span>

4.  <span data-ttu-id="46d19-157">[**この SQL インスタンスはミラーリングの関係にある**] を選択し、SQL ミラーリングのポート番号 (既定のポートは 5022 番) を指定して、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46d19-157">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number the default port is 5022), and then click **OK**.</span></span>

5.  <span data-ttu-id="46d19-158">ミラーリング監視を構成する場合は、[**SQL ミラーリング監視を使用して自動フェールオーバーを有効にする**] を選択し、[**新規作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46d19-158">If you want to configure a witness, select **Use SQL mirroring witness to enable automatic failover**, and click **New**.</span></span>

6.  <span data-ttu-id="46d19-159">ミラーリング監視として使用する SQL ストアを指定します。</span><span class="sxs-lookup"><span data-stu-id="46d19-159">Specify the SQL store that you want to use as the witness.</span></span>

7.  <span data-ttu-id="46d19-160">[**この SQL インスタンスはミラーリングの関係にある**] を選択し、SQL ミラーリングのポート番号 (既定のポートは 7022 番) を指定して、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46d19-160">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default port is 7022), and then click **OK**.</span></span>

8.  <span data-ttu-id="46d19-161">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46d19-161">Click **OK**.</span></span>

9.  <span data-ttu-id="46d19-p111">トポロジを公開します。この操作を行うと、データベースをインストールするように求められます。</span><span class="sxs-lookup"><span data-stu-id="46d19-p111">Publish the topology. When you do so, you will be prompted to install the database.</span></span>
    
    <span data-ttu-id="46d19-164">トポロジの公開プロセス時に、ファイル共有パスの定義を求められます。</span><span class="sxs-lookup"><span data-stu-id="46d19-164">During the topology publishing process, you will be asked to define a file share path.</span></span> <span data-ttu-id="46d19-165">ミラーリングに参加する SQL サーバーは、ミラーを確立するために、このファイル共有への読み取り/書き込みアクセス権を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="46d19-165">The SQL Servers that participate in the mirroring must have read/write access to this file share for the mirror to be established.</span></span>

<span data-ttu-id="46d19-166">その場合、次の手順に進む前にデータベースをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="46d19-166">You must then install the database before going on to the next procedure.</span></span>

<span data-ttu-id="46d19-167">SQL ミラーリングの設定時には次の点に留意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46d19-167">You should keep the following in mind when setting up SQL mirroring:</span></span>

  - <span data-ttu-id="46d19-168">既に存在するミラーリング エンドポイントは、そこに定義されたポートを使用して再利用され、トポロジ内で指定したポートは無視されます。</span><span class="sxs-lookup"><span data-stu-id="46d19-168">If a mirroring endpoint already exists, it will be reused using the ports defined there, and will ignore the ones you specify in the topology.</span></span>

  - <span data-ttu-id="46d19-p113">同じサーバー上の他のアプリケーションに既に割り当てられたポート (他の SQL インスタンス用のポートを含みます) は、ここでインストールする SQL インスタンスでは使用しないでください。これは、複数の SQL インスタンスを同じサーバー上にインストールしている場合、それらのインスタンスは同じポートをミラーリングに使用してはならないことを意味します。詳細については、以下の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46d19-p113">Any port already allocated for other applications on the same server, including those for other SQL instances, should not be used for the installed SQL instances at hand. This implies that if you have more than one SQL instance installed on the same server, they must not use the same port for mirroring. For details, see the following articles:</span></span>
    
      - <span data-ttu-id="46d19-172">MSDN ライブラリの「サーバーネットワークアドレス (データベースミラーリング) を指定する」 [https://go.microsoft.com/fwlink/p/?LinkId=247346](https://go.microsoft.com/fwlink/p/?linkid=247346)</span><span class="sxs-lookup"><span data-stu-id="46d19-172">"Specify a Server Network Address (Database Mirroring)" in the MSDN Library at [https://go.microsoft.com/fwlink/p/?LinkId=247346](https://go.microsoft.com/fwlink/p/?linkid=247346)</span></span>
    
      - <span data-ttu-id="46d19-173">"データベースミラーリングエンドポイント (SQL Server)" [https://go.microsoft.com/fwlink/p/?LinkId=247347](https://go.microsoft.com/fwlink/p/?linkid=247347)</span><span class="sxs-lookup"><span data-stu-id="46d19-173">"The Database Mirroring Endpoint (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=247347](https://go.microsoft.com/fwlink/p/?linkid=247347)</span></span>

</div>

<div>

## <a name="using-lync-server-management-shell-cmdlets-to-set-up-sql-mirroring"></a><span data-ttu-id="46d19-174">Lync Server 管理シェルコマンドレットを使用して SQL ミラーリングをセットアップする</span><span class="sxs-lookup"><span data-stu-id="46d19-174">Using Lync Server Management Shell Cmdlets to Set Up SQL Mirroring</span></span>

<span data-ttu-id="46d19-175">ミラーリングをセットアップする最も簡単な方法は、トポロジビルダーを使用することですが、コマンドレットを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="46d19-175">The easiest way to set up mirroring is by using Topology Builder, but you can also do so using cmdlets.</span></span>

1.  <span data-ttu-id="46d19-176">Lync Server 管理シェルウィンドウを開き、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="46d19-176">Open a Lync Server Management Shell window and run the following cmdlet:</span></span>
    
        Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose 
    
    <span data-ttu-id="46d19-177">例:</span><span class="sxs-lookup"><span data-stu-id="46d19-177">For example:</span></span>
    
        Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose 
    
    <span data-ttu-id="46d19-178">以下のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="46d19-178">You will see the following:</span></span>
    
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

2.  <span data-ttu-id="46d19-179">次のことを確認します。</span><span class="sxs-lookup"><span data-stu-id="46d19-179">Verify the following:</span></span>
    
      - <span data-ttu-id="46d19-180">プライマリ SQL Server e04-ocs で Windows ファイアウォールが有効になっている場合は、ポート5022がファイアウォール経由でアクセス可能 \_ です。 \\</span><span class="sxs-lookup"><span data-stu-id="46d19-180">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the primary SQL Server e04-ocs.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="46d19-181">ミラー SQL Server K16-ocs で Windows ファイアウォールが有効になっている場合は、ファイアウォール経由でポート5022にアクセスでき \_ ます。 \\</span><span class="sxs-lookup"><span data-stu-id="46d19-181">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the mirror SQL Server K16-ocs.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="46d19-182">ミラーリング監視 SQL Server AB14-lct で Windows ファイアウォールが有効になっている場合は、ファイアウォール経由でポート7022にアクセスでき \_ ます。 \\</span><span class="sxs-lookup"><span data-stu-id="46d19-182">Port 7022 is accessible through the firewall if Windows Firewall is enabled in the witness SQL Server AB14-lct.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="46d19-183">すべてのプライマリおよびミラー SQL サーバーで SQL Server を実行しているアカウントには、ファイル共有 \\ \\ E04 \\ cs に対する読み取り/書き込みアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="46d19-183">Accounts running the SQL Servers on all primary and mirror SQL servers have read/write permission to the file share \\\\E04-OCS\\csdatabackup</span></span>
    
      - <span data-ttu-id="46d19-p114">これらすべてのサーバーで、Windows Management Instrumentation (WMI) プロバイダーが実行されている。コマンドレットでは、このプロバイダーを使用して、すべてのプライマリ サーバー、ミラー サーバー、およびミラーリング監視サーバーで実行されている SQL Server サービスのアカウント情報が検索されます。</span><span class="sxs-lookup"><span data-stu-id="46d19-p114">Verify that the Windows Management Instrumentation (WMI) provider is running on all these servers. The cmdlet uses this provider to find the account information for SQL Server services running on all primary, mirror and witness servers.</span></span>
    
      - <span data-ttu-id="46d19-186">このコマンドレットを実行しているアカウントに、すべてのミラー サーバーのデータおよびログ ファイル用のフォルダーを作成するためのアクセス許可がある。</span><span class="sxs-lookup"><span data-stu-id="46d19-186">Verify that the account running this cmdlet has permission to create the folders for the data and log files for all the mirror servers.</span></span>
    
      - <span data-ttu-id="46d19-p115">SQL インスタンスの実行に使用するユーザー アカウントに、ファイル共有に対する読み取り/書き込みアクセス許可がある。ファイル共有が別のサーバーにあり、SQL インスタンスがローカル システム アカウントを実行している場合は、SQL インスタンスをホストするサーバーへのファイル共有アクセス許可を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46d19-p115">Note that the user account that the SQL instance uses to run must have read/write permission to the file share. If the file share is on a different server, and the SQL instance runs a local system account, you must grant file share permissions to the server that hosts the SQL instance.</span></span>

3.  <span data-ttu-id="46d19-189">「A」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="46d19-189">Type A and press ENTER.</span></span>
    
    <span data-ttu-id="46d19-190">ミラーリングの構成が行われます。</span><span class="sxs-lookup"><span data-stu-id="46d19-190">The mirroring will be configured.</span></span>

<span data-ttu-id="46d19-191">**Install-csmirrordatabase** は、ミラーをインストールし、プライマリ SQL ストアに存在するすべてのデータベースのミラーリングを構成します。</span><span class="sxs-lookup"><span data-stu-id="46d19-191">**Install-CsMirrorDatabase** installs the mirror and configures mirroring for all the databases that are present on the primary SQL store.</span></span> <span data-ttu-id="46d19-192">特定のデータベースに対してのみミラーリングを構成する場合は、-DatabaseType オプションを使用できます。また、一部のデータベースでミラーリングを構成する場合は、-ExcludeDatabaseList オプションを使用して、除外するデータベース名のコンマ区切りリストを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="46d19-192">If you want to configure mirroring for only specific databases, you can use the –DatabaseType option, or if you want to configure mirroring for all databases except for a few, you can use the -ExcludeDatabaseList option, along with a comma-separated list of database names to exclude.</span></span>

<span data-ttu-id="46d19-193">たとえば、次のオプションを **Install-CsMirrorDatabase** に追加した場合は、rtcab と rtcxds を除くすべてのデータベースがミラーリングされます。</span><span class="sxs-lookup"><span data-stu-id="46d19-193">For example, if you add the following option to **Install-CsMirrorDatabase**, all databases except rtcab and rtcxds will be mirrored.</span></span>

`-ExcludeDatabaseList rtcab,rtcxds`

<span data-ttu-id="46d19-194">たとえば、次のオプションを **Install-CsMirrorDatabase** に追加した場合は、rtcab、rtcshared、および rtcxds データベースのみミラーリングされます。</span><span class="sxs-lookup"><span data-stu-id="46d19-194">For example, if you add the following option to **Install-CsMirrorDatabase**, only the rtcab, rtcshared, and rtcxds databases will be mirrored.</span></span>

`-DatabaseType User`

</div>

<div>

## <a name="removing-or-changing-sql-mirroring"></a><span data-ttu-id="46d19-195">SQL ミラーリングの削除または変更</span><span class="sxs-lookup"><span data-stu-id="46d19-195">Removing or Changing SQL Mirroring</span></span>

<span data-ttu-id="46d19-p117">トポロジ ビルダーのプールの SQL ミラーリングを削除するには、最初にコマンドレットを使用して、SQL Server のミラーを削除する必要があります。次に、トポロジ ビルダーを使用して、トポロジからミラーを削除できます。SQL Server でミラーを削除するには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="46d19-p117">To remove the SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server. You can then use Topology Builder to remove the mirror from the topology. To remove the mirror in SQL Server, use the following cmdlet:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

<span data-ttu-id="46d19-199">たとえば、ミラーリングを削除し、User データベースのデータベースを削除するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="46d19-199">For example, to remove mirroring and drop the databases for the User databases, type the following:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

<span data-ttu-id="46d19-200">この `-DropExistingDatabasesOnMirror` オプションを指定すると、影響を受けるデータベースがミラーから削除されます。</span><span class="sxs-lookup"><span data-stu-id="46d19-200">The `-DropExistingDatabasesOnMirror` option causes the affected databases to be deleted from the mirror.</span></span>

<span data-ttu-id="46d19-201">次に、トポロジからミラーを削除するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="46d19-201">Then, to remove the mirror from the topology, do the following:</span></span>

1.  <span data-ttu-id="46d19-202">トポロジ ビルダーで、プールを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46d19-202">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="46d19-203">[**SQL ストアのミラーリングを有効にする**] チェック ボックスをオフにし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46d19-203">Uncheck **Enable SQL Store Mirroring** and click **OK**.</span></span>

3.  <span data-ttu-id="46d19-204">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="46d19-204">Publish the topology.</span></span>

</div>

<div>

## <a name="removing-a-mirroring-witness"></a><span data-ttu-id="46d19-205">ミラーリング監視の削除</span><span class="sxs-lookup"><span data-stu-id="46d19-205">Removing a Mirroring Witness</span></span>

<span data-ttu-id="46d19-206">バックエンドサーバーのミラーリング構成からミラーリング監視を削除する必要がある場合は、この手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="46d19-206">Use this procedure if you need to remove the witness from a Back End Server mirroring configuration.</span></span>

1.  <span data-ttu-id="46d19-207">トポロジ ビルダーで、プールを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46d19-207">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="46d19-208">[**SQL Server ミラーリング監視を自動フェールオーバーの有効化のために使用**] をオフにし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46d19-208">Uncheck **Use SQL Server mirroring witness to enable automatic failover** and click **OK**.</span></span>

3.  <span data-ttu-id="46d19-209">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="46d19-209">Publish the topology.</span></span>
    
    <span data-ttu-id="46d19-210">トポロジを公開すると、トポロジビルダーに、次のようなメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="46d19-210">After publishing the topology, Topology Builder you will see a message that includes the following</span></span>
    
        Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
    
    <span data-ttu-id="46d19-211">ただし、その手順を実行するのではなく、 `Uninstall-CsMirrorDatabase` ミラーリング構成全体をアンインストールするのではなく、と入力してください。</span><span class="sxs-lookup"><span data-stu-id="46d19-211">However, do not follow that step, and do not type `Uninstall-CsMirrorDatabase` as that would uninstall the entire mirroring configuration.</span></span>

4.  <span data-ttu-id="46d19-212">SQL Server 構成からミラーリング監視のみを削除するには、「データベースミラーリングセッション (SQL Server) からのミラーリング監視を削除する」の手順に従って [https://go.microsoft.com/fwlink/p/?LinkId=268456](https://go.microsoft.com/fwlink/p/?linkid=268456) ください。</span><span class="sxs-lookup"><span data-stu-id="46d19-212">To remove just the witness from the SQL Server configuration, follow the instructions in "Remove the Witness from a Database Mirroring Session (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268456](https://go.microsoft.com/fwlink/p/?linkid=268456).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

