---
title: Skype for Business Server 2015 でバックエンド サーバーの高可用性を実現するための SQL ミラーリングの展開
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
description: SQL ミラーリングを展開できるようにするには、サーバーで最小限の SQL Server 2008 R2 を実行する必要があります。 このバージョンは、すべての関連サーバー (プライマリ、ミラー、およびミラーリング監視の各サーバー) で実行する必要があります。 詳細については、更新プログラム パッケージ 9 を SQL Server 2008 Service Pack 1 の累積を参照してください。
ms.openlocfilehash: 9ea6e8a48fbcc3f5938c33e9d06db3c882f28de2
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373801"
---
# <a name="deploy-sql-mirroring-for-back-end-server-high-availability-in-skype-for-business-server-2015"></a><span data-ttu-id="83983-105">ビジネス サーバー 2015 の Skype のバック エンド サーバーの高可用性の SQL のミラーリングを導入します。</span><span class="sxs-lookup"><span data-stu-id="83983-105">Deploy SQL mirroring for Back End Server high availability in Skype for Business server 2015</span></span>


<span data-ttu-id="83983-106">SQL ミラーリングを展開できるようにするには、サーバーで最小限の SQL Server 2008 R2 を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83983-106">To be able to deploy SQL mirroring, your servers must run a minimum of SQL Server 2008 R2.</span></span> <span data-ttu-id="83983-107">このバージョンは、すべての関連サーバー (プライマリ、ミラー、およびミラーリング監視の各サーバー) で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83983-107">This version must run on all the involved servers: the primary, mirror, and the witness.</span></span> <span data-ttu-id="83983-108">詳細については、[更新プログラム パッケージ 9 SQL Server 2008 Service Pack 1 の累積](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83983-108">For details, see [Cumulative update package 9 for SQL Server 2008 Service Pack 1 ](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921).</span></span>

<span data-ttu-id="83983-109">一般に、2 つのバックエンド サーバー間での SQL ミラーリングを設定するには、以下の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="83983-109">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>

- <span data-ttu-id="83983-110">SQL Server のプライマリ サーバーのバージョンでは、SQL のミラーリングをサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="83983-110">The primary server's version of SQL Server must support SQL mirroring.</span></span>

- <span data-ttu-id="83983-111">プライマリ、ミラー、およびミラーリング監視 (展開されている場合) の各 SQL Server が同一バージョンである。</span><span class="sxs-lookup"><span data-stu-id="83983-111">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span>

- <span data-ttu-id="83983-p103">プライマリおよびミラーの各 SQL Server が同一エディションである (ミラーリング監視のエディションは異なっていても構いません)。</span><span class="sxs-lookup"><span data-stu-id="83983-p103">The primary and the mirror must have the same edition of SQL Server. The witness may have a different edition.</span></span>

<span data-ttu-id="83983-114">ミラーリング監視ロールのどのような SQL のバージョンはサポートされているという点で SQL のベスト プラクティスは、[データベース ミラーリングの監視](https://go.microsoft.com/fwlink/p/?LinkId=247345)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83983-114">For SQL best practices in terms of what SQL versions are supported for a Witness role, see [Database Mirroring Witness](https://go.microsoft.com/fwlink/p/?LinkId=247345).</span></span>

<span data-ttu-id="83983-115">SQL のミラーリングを展開するのにには、トポロジ ビルダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="83983-115">You use Topology Builder to deploy SQL mirroring.</span></span> <span data-ttu-id="83983-116">データベースをミラー化するのにはトポロジ ビルダーのオプションを選択して、トポロジ ビルダーの設定をミラーリングなど、ミラーリング監視サーバーを設定する場合は、トポロジを公開するとします。</span><span class="sxs-lookup"><span data-stu-id="83983-116">You select an option in Topology Builder to mirror the databases, and Topology Builder sets up the mirroring (including setting up a witness, if you want) when you publish the topology.</span></span> <span data-ttu-id="83983-117">ミラーリング監視は、ミラーの設定または削除と同時に設定または削除することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="83983-117">Note that you set up or remove the witness at the same time you set up or remove the mirror.</span></span> <span data-ttu-id="83983-118">ミラーリング監視のみ展開または削除する独立したコマンドはありません。</span><span class="sxs-lookup"><span data-stu-id="83983-118">There is no separate command to deploy or remove only a witness.</span></span>

<span data-ttu-id="83983-119">サーバー ミラーリングを構成するには、最初に SQL データベース アクセス許可を正しく設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83983-119">To configure server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="83983-120">詳細については、[データベース ミラーリングまたは AlwaysOn 可用性グループ (SQL Server) には、[ログイン アカウントの設定](https://go.microsoft.com/fwlink/p/?LinkId=268454)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83983-120">For details, see [Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268454).</span></span>

<span data-ttu-id="83983-p106">SQL ミラーリングでは、データベース復旧モードは常に [**完全**] に設定されます。これは、トランザクション ログ サイズを綿密に監視し、トランザクション ログを定期的にバックアップしてバックエンド サーバー上のディスク容量の不足を回避する必要があることを意味します。トランザクション ログのバックアップ頻度は、ログの増加率によって決まります。ログの増加率は、フロントエンド プールのユーザー アクティビティによるデータベース トランザクションによって決まります。展開ワークロードに対して予想されるトランザクション ログの増加を判断し、それに応じて計画することをお勧めします。次の記事では、SQL バックアップおよびログ管理に関する追加情報を提供しています。</span><span class="sxs-lookup"><span data-stu-id="83983-p106">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers. The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool. We recommend that you determine how much transaction log growth is expected for your deployment workload so that you can do the planning accordingly. The following articles provide additional information on SQL backup and log management:</span></span>

- [<span data-ttu-id="83983-125">データベースのリカバリ モデル</span><span class="sxs-lookup"><span data-stu-id="83983-125">Database recovery models</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=268446)

- [<span data-ttu-id="83983-126">バックアップの概要</span><span class="sxs-lookup"><span data-stu-id="83983-126">Backup overview</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=268449)

- [<span data-ttu-id="83983-127">トランザクション ログのバックアップ</span><span class="sxs-lookup"><span data-stu-id="83983-127">Backup transaction log</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=268452)

<span data-ttu-id="83983-128">SQL ミラーリングでは、ミラーリングのトポロジの構成を、プールの作成時、またはプールが既に作成された後のどちらでも行うことができます。</span><span class="sxs-lookup"><span data-stu-id="83983-128">With SQL mirroring, you can either configure the topology for mirroring when you create the pools, or after the pools are already created.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="83983-129">設定し、SQL を削除するのにはトポロジ ビルダーまたはコマンドレットを使用してミラーリングがサポートされているプライマリ、ミラー、および (必要な場合)、ミラーリング監視サーバーが同じドメインに属している場合にのみです。</span><span class="sxs-lookup"><span data-stu-id="83983-129">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="83983-130">異なるドメインのサーバーに SQL ミラーリングを設定する場合は、SQL Server のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="83983-130">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="83983-131">バックエンド データベース ミラーリング関係を変更するたびに、プール内のすべてのフロントエンド サーバーを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83983-131">Whenever you make a change to a Back End Database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span> <span data-ttu-id="83983-132">> 変更するなど、ミラーの場所)、の変更がミラー化にこれら 3 つの手順を実行するのにはトポロジ ビルダーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83983-132">> For a change in mirroring, (such as changing the location of a mirror), you must use Topology Builder to perform these three steps:</span></span>

1. <span data-ttu-id="83983-133">古いミラー サーバーからミラーリングを削除します。</span><span class="sxs-lookup"><span data-stu-id="83983-133">Remove mirroring from the old mirror server.</span></span>

2. <span data-ttu-id="83983-134">新しいミラー サーバーにミラーリングを追加します。</span><span class="sxs-lookup"><span data-stu-id="83983-134">Add mirroring to the new mirror server.</span></span>

3. <span data-ttu-id="83983-135">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="83983-135">Publish the topology.</span></span>

> [!NOTE]
> <span data-ttu-id="83983-136">ファイル共有への書き込みをミラー ファイルを作成してで、SQL Server と SQL エージェントが実行されているサービスには、読み取り/書き込みアクセスが必要があります。</span><span class="sxs-lookup"><span data-stu-id="83983-136">A file share has to be created for the mirror files to be written to, and the service that SQL Server and SQL Agent are running under needs read/write access.</span></span> <span data-ttu-id="83983-137">追加するかどうかは、ネットワーク サービスのコンテキストで SQL Server サービスが実行されて、\<ドメイン\>\\< SQLSERVERNAME\>共有のアクセス許可にプリンシパルとミラーの SQL サーバーの両方の $。</span><span class="sxs-lookup"><span data-stu-id="83983-137">If the SQL Server service is running under the context of Network Service, you can add \<Domain\>\\<SQLSERVERNAME\>$ of both the Principal and Mirror SQL Servers to the share permissions.</span></span> <span data-ttu-id="83983-138">$ では、これは、コンピューター アカウントを識別する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83983-138">The $ is important to identify that this is a computer account.</span></span>

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a><span data-ttu-id="83983-139">トポロジ ビルダーでのプールの作成時に SQL のミラーリングを構成するのには</span><span class="sxs-lookup"><span data-stu-id="83983-139">To configure SQL mirroring while creating a pool in Topology Builder</span></span>

1. <span data-ttu-id="83983-140">[**SQL ストアの定義**] ページで、[**SQL ストア**] ボックスの隣にある [**新規作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="83983-140">On the **Define the SQL Store** page, click **New** next to the **SQL store** box.</span></span>

2. <span data-ttu-id="83983-141">[**新しい SQL ストアの定義**] ページで、プライマリ ストアを指定し、[**この SQL インスタンスはミラーリングの関係にある **] を選択して、SQL ミラーリングのポート番号 (既定値は 5022) を指定したうえで [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="83983-141">On the **Define new SQL Store** page, specify the primary store, select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default is 5022), and then click **OK**.</span></span>

3. <span data-ttu-id="83983-142">[**SQL ストアの定義**] ページに戻ったら、[**SQL ストアのミラーリングを有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="83983-142">Back on the **Define the SQL store** page, select **Enable SQL Store mirroring**.</span></span>

4. <span data-ttu-id="83983-p110">[**新しい SQL ストアの定義**] ページで、ミラーとして使用する SQL ストアを指定し、[**この SQL インスタンスはミラーリングの関係にある**] を選択して、ポート番号 (既定値は 5022) を指定したうえで [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="83983-p110">In the **Define new SQL Store** page, specify the SQL store to be used as the mirror. Select **This SQL instance is in mirroring relation**, specify the port number (the default is 5022), and then click **OK**.</span></span>

5. <span data-ttu-id="83983-145">このミラーのミラーリング監視が必要な場合は、以下の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="83983-145">If you want a witness for this mirror, do the following:</span></span>

    <span data-ttu-id="83983-146">a.</span><span class="sxs-lookup"><span data-stu-id="83983-146">a.</span></span> <span data-ttu-id="83983-147">[**SQL ミラーリング監視を使用して自動フェールオーバーを有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="83983-147">Select **Use SQL mirroring witness to enable automatic failover**.</span></span>

    <span data-ttu-id="83983-148">b.</span><span class="sxs-lookup"><span data-stu-id="83983-148">b.</span></span> <span data-ttu-id="83983-149">[**SQL ストアの定義**] ページで、[**SQL ミラーリング監視を使用して自動フェールオーバーを有効にする**] を選択し、ミラーリング監視として使用する SQL ストアを指定します。</span><span class="sxs-lookup"><span data-stu-id="83983-149">In the **Define the SQL Store** page, select **Use SQL mirroring witness to enable automatic failover**, and specify the SQL store to be used as the witness.</span></span>

    <span data-ttu-id="83983-150">c.</span><span class="sxs-lookup"><span data-stu-id="83983-150">c.</span></span> <span data-ttu-id="83983-151">ポート番号 (既定値は 7022) を指定し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="83983-151">Specify the port number (the default is 7022) and click **OK**.</span></span>

6. <span data-ttu-id="83983-152">終了したら、トポロジを公開するのにはトポロジ ビルダーを使用する、トポロジで、フロント エンド プールとその他のすべてのロールを定義します。</span><span class="sxs-lookup"><span data-stu-id="83983-152">After you are done defining your Front End pool and all other roles in your topology, use Topology Builder to publish the topology.</span></span> <span data-ttu-id="83983-153">トポロジを公開すると、中央管理ストアをホストするフロント エンド プールは、SQL ミラーリングが有効になっている場合は、両方のプライマリを作成し、SQL ストアのデータベースをミラーリングするためのオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="83983-153">When the topology is published, if the Front End pool that hosts Central Management store has SQL mirroring enabled, you will see an option to create both primary and mirror SQL store databases.</span></span>

    <span data-ttu-id="83983-154">[**設定**] をクリックし、ミラーリング バックアップのファイル共有として使用するパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="83983-154">Click **Settings**, and type the path to use as the file share for the mirroring backup.</span></span>

    <span data-ttu-id="83983-p115">[**OK**]、[**次へ**] の順にクリックして、データベースを作成し、トポロジを公開します。ミラーリングとミラーリング監視 (指定した場合) が展開されます。</span><span class="sxs-lookup"><span data-stu-id="83983-p115">Click **OK** and then **Next** to create the databases and publish the topology. The mirroring and the witness (if specified) will be deployed.</span></span>

<span data-ttu-id="83983-157">SQL のミラーリングを有効にするのに既存のプールのプロパティを編集するのには、トポロジ ビルダーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="83983-157">You can use Topology Builder to edit the properties of an already existing pool to enable SQL mirroring.</span></span>

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a><span data-ttu-id="83983-158">SQL のミラーリングには、トポロジ ビルダーで既存のフロント エンド プールを追加するのには</span><span class="sxs-lookup"><span data-stu-id="83983-158">To add SQL mirroring to an existing Front End pool in Topology Builder</span></span>

1. <span data-ttu-id="83983-159">トポロジ ビルダーでは、プールを右クリックし、**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="83983-159">In Topology Builder, right-click the pool and then click **Edit Properties**.</span></span>

2. <span data-ttu-id="83983-160">[**SQL ストアのミラーリングを有効にする**] を選択し、[**ミラーリング SQL ストア**] の横にある [**新規作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="83983-160">Select **Enable SQL Store Mirroring**, and then click **New** next to **Mirroring SQL Store**.</span></span>

3. <span data-ttu-id="83983-161">ミラーとして使用する SQL ストアを指定します。</span><span class="sxs-lookup"><span data-stu-id="83983-161">Specify the SQL store that you want to use as the mirror.</span></span>

4. <span data-ttu-id="83983-162">[**この SQL インスタンスはミラーリングの関係にある**] を選択し、SQL ミラーリングのポート番号 (既定のポートは 5022 番) を指定して、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="83983-162">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number the default port is 5022), and then click **OK**.</span></span>

5. <span data-ttu-id="83983-163">ミラーリング監視を構成する場合は、[**SQL ミラーリング監視を使用して自動フェールオーバーを有効にする**] を選択し、[**新規作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="83983-163">If you want to configure a witness, select **Use SQL mirroring witness to enable automatic failover**, and click **New**.</span></span>

6. <span data-ttu-id="83983-164">ミラーリング監視として使用する SQL ストアを指定します。</span><span class="sxs-lookup"><span data-stu-id="83983-164">Specify the SQL store that you want to use as the witness.</span></span>

7. <span data-ttu-id="83983-165">[**この SQL インスタンスはミラーリングの関係にある**] を選択し、SQL ミラーリングのポート番号 (既定のポートは 7022 番) を指定して、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="83983-165">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default port is 7022), and then click **OK**.</span></span>

8. <span data-ttu-id="83983-166">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="83983-166">Click **OK**.</span></span>

9. <span data-ttu-id="83983-p116">トポロジを公開します。この操作を行うと、データベースをインストールするように求められます。</span><span class="sxs-lookup"><span data-stu-id="83983-p116">Publish the topology. When you do so, you will be prompted to install the database.</span></span>

    <span data-ttu-id="83983-p117">トポロジ公開プロセスでは、ファイル共有パスの入力を求められます。ミラーリングを確立するには、ミラーリングに参加するすべての SQL Server に、このファイル共有への読み取り/書き込みのアクセス権が必要です。</span><span class="sxs-lookup"><span data-stu-id="83983-p117">During the topology publishing process, you will be asked to define a file share path. The SQL Servers that participate in the mirroring must have read/write access to this file share for the mirror to be established.</span></span>

<span data-ttu-id="83983-171">その場合、次の手順に進む前にデータベースをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="83983-171">You must then install the database before going on to the next procedure.</span></span>

<span data-ttu-id="83983-172">SQL ミラーリングの設定時には次の点に留意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83983-172">You should keep the following in mind when setting up SQL mirroring:</span></span>

- <span data-ttu-id="83983-173">既に存在するミラーリング エンドポイントは、そこに定義されたポートを使用して再利用され、トポロジ内で指定したポートは無視されます。</span><span class="sxs-lookup"><span data-stu-id="83983-173">If a mirroring endpoint already exists, it will be reused using the ports defined there, and will ignore the ones you specify in the topology.</span></span>

- <span data-ttu-id="83983-p118">同じサーバー上の他のアプリケーションに既に割り当てられたポート (他の SQL インスタンス用のポートを含みます) は、ここでインストールする SQL インスタンスでは使用しないでください。これは、複数の SQL インスタンスを同じサーバー上にインストールしている場合、それらのインスタンスは同じポートをミラーリングに使用してはならないことを意味します。詳細については、以下の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83983-p118">Any port already allocated for other applications on the same server, including those for other SQL instances, should not be used for the installed SQL instances at hand. This implies that if you have more than one SQL instance installed on the same server, they must not use the same port for mirroring. For details, see the following articles:</span></span>

  - [<span data-ttu-id="83983-177">(データベース ミラーリング)、サーバーのネットワーク アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="83983-177">Specify a Server Network Address (Database Mirroring)</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=247346)

  - [<span data-ttu-id="83983-178">データベース ミラーリング エンドポイント (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="83983-178">The Database Mirroring Endpoint (SQL Server)</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=247347)

## <a name="using-skype-for-business-server-2015-management-shell-cmdlets-to-set-up-sql-mirroring"></a><span data-ttu-id="83983-179">ビジネス サーバー 2015 管理シェル コマンドレット セットの Skype を使用して SQL ミラーのセットアップ</span><span class="sxs-lookup"><span data-stu-id="83983-179">Using Skype for Business Server 2015 Management Shell Cmdlets to Set Up SQL Mirroring</span></span>

<span data-ttu-id="83983-180">ミラーリングを設定する最も簡単な方法は、トポロジ ビルダーを使用してですが、コマンドレットを使用しても行うことができます。</span><span class="sxs-lookup"><span data-stu-id="83983-180">The easiest way to set up mirroring is by using Topology Builder, but you can also do so using cmdlets.</span></span>

1. <span data-ttu-id="83983-181">Skype ビジネス サーバー 2015 の管理シェル ウィンドウを開くし、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="83983-181">Open a Skype for Business Server 2015 Management Shell window and run the following cmdlet:</span></span>

   ```
   Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose
   ```

    <span data-ttu-id="83983-182">例:</span><span class="sxs-lookup"><span data-stu-id="83983-182">For example:</span></span>

   ```
   Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose
   ```

    <span data-ttu-id="83983-183">以下のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="83983-183">You will see the following:</span></span>

   <pre>
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
   </pre>

2. <span data-ttu-id="83983-184">次のことを確認します。</span><span class="sxs-lookup"><span data-stu-id="83983-184">Verify the following:</span></span>

    - <span data-ttu-id="83983-185">プライマリ SQL Server e04-ocs.los_a.lsipt.local\rtc で Windows ファイアウォールが有効になっている場合は、ポート 5022 がファイアウォール経由でアクセスできる。</span><span class="sxs-lookup"><span data-stu-id="83983-185">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the primary SQL Server e04-ocs.los_a.lsipt.local\rtc.</span></span>

    - <span data-ttu-id="83983-186">ミラー SQL Server K16-ocs.los_a.lsipt.local\rtc で Windows ファイアウォールが有効になっている場合は、ポート 5022 がファイアウォール経由でアクセスできる。</span><span class="sxs-lookup"><span data-stu-id="83983-186">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the mirror SQL Server K16-ocs.los_a.lsipt.local\rtc.</span></span>

    - <span data-ttu-id="83983-187">ミラーリング監視 SQL Server AB14-lct.los_a.lsipt.local\rtc で Windows ファイアウォールが有効になっている場合は、ポート 7022 がファイアウォール経由でアクセスできる。</span><span class="sxs-lookup"><span data-stu-id="83983-187">Port 7022 is accessible through the firewall if Windows Firewall is enabled in the witness SQL Server AB14-lct.los_a.lsipt.local\rtc.</span></span>

   - <span data-ttu-id="83983-188">アカウントは、プライマリのすべての SQL サーバーと SQL サーバーのミラーを実行しているファイル共有への読み取り/書き込み権限のある\\E04 OCS\csdatabackup</span><span class="sxs-lookup"><span data-stu-id="83983-188">Accounts running the SQL Servers on all primary and mirror SQL servers have read/write permission to the file share \\E04-OCS\csdatabackup</span></span>

   - <span data-ttu-id="83983-p119">これらすべてのサーバーで、Windows Management Instrumentation (WMI) プロバイダーが実行されている。コマンドレットでは、このプロバイダーを使用して、すべてのプライマリ サーバー、ミラー サーバー、およびミラーリング監視サーバーで実行されている SQL Server サービスのアカウント情報が検索されます。</span><span class="sxs-lookup"><span data-stu-id="83983-p119">Verify that the Windows Management Instrumentation (WMI) provider is running on all these servers. The cmdlet uses this provider to find the account information for SQL Server services running on all primary, mirror and witness servers.</span></span>

   - <span data-ttu-id="83983-191">このコマンドレットを実行しているアカウントに、すべてのミラー サーバーのデータおよびログ ファイル用のフォルダーを作成するためのアクセス許可がある。</span><span class="sxs-lookup"><span data-stu-id="83983-191">Verify that the account running this cmdlet has permission to create the folders for the data and log files for all the mirror servers.</span></span>

   - <span data-ttu-id="83983-p120">SQL インスタンスの実行に使用するユーザー アカウントに、ファイル共有に対する読み取り/書き込みアクセス許可が必要であることに注意してください。ファイル共有が別のサーバーにあり、SQL インスタンスがローカル システム アカウントを実行している場合は、SQL インスタンスをホストするサーバーへのファイル共有アクセス許可を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83983-p120">Note that the user account that the SQL instance uses to run must have read/write permission to the file share. If the file share is on a different server, and the SQL instance runs a local system account, you must grant file share permissions to the server that hosts the SQL instance.</span></span>

3. <span data-ttu-id="83983-194">「A」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="83983-194">Type A and press ENTER.</span></span>

    <span data-ttu-id="83983-195">ミラーリングの構成が行われます。</span><span class="sxs-lookup"><span data-stu-id="83983-195">The mirroring will be configured.</span></span>

    <span data-ttu-id="83983-196">**インストール CsMirrorDatabase**では、ミラーをインストールし、プライマリ SQL ストア上に存在するすべてのデータベースのミラーリングを構成します。</span><span class="sxs-lookup"><span data-stu-id="83983-196">**Install-CsMirrorDatabase** installs the mirror and configures mirroring for all the databases that are present on the primary SQL store.</span></span> <span data-ttu-id="83983-197">のみ特定のデータベースのミラーリングを構成する場合は、することができますオプションを使用して、- されていません、またはデータベースのコンマ区切りのリストと、- ExcludeDatabaseList オプションを使用するにはいくつかを除くすべてのデータベース ミラーリングを構成する場合は、除外する名前です。</span><span class="sxs-lookup"><span data-stu-id="83983-197">If you want to configure mirroring for only specific databases, you can use the -DatabaseType option, or if you want to configure mirroring for all databases except for a few, you can use the -ExcludeDatabaseList option, along with a comma-separated list of database names to exclude.</span></span>

    <span data-ttu-id="83983-198">などの**インストール CsMirrorDatabase**に次のオプションを追加する場合は、rtcab と rtcxds を除くすべてのデータベースがミラーされます。</span><span class="sxs-lookup"><span data-stu-id="83983-198">For example, if you add the following option to **Install-CsMirrorDatabase**, all databases except rtcab and rtcxds will be mirrored.</span></span>

    `-ExcludeDatabaseList rtcab,rtcxds`

   <span data-ttu-id="83983-199">たとえば、**インストール CsMirrorDatabase**に次のオプションを追加する場合のみ、rtcab、rtcshared、rtcxds データベースがミラーされます。</span><span class="sxs-lookup"><span data-stu-id="83983-199">For example, if you add the following option to **Install-CsMirrorDatabase**, only the rtcab, rtcshared, and rtcxds databases will be mirrored.</span></span>

    `-DatabaseType User`

## <a name="removing-or-changing-sql-mirroring"></a><span data-ttu-id="83983-200">SQL ミラーリングの削除または変更</span><span class="sxs-lookup"><span data-stu-id="83983-200">Removing or Changing SQL Mirroring</span></span>

<span data-ttu-id="83983-p122">トポロジ ビルダーのプールの SQL ミラーリングを削除するには、最初にコマンドレットを使用して、SQL Server のミラーを削除する必要があります。次に、トポロジ ビルダーを使用して、トポロジからミラーを削除できます。SQL Server でミラーを削除するには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="83983-p122">To remove the SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server. You can then use Topology Builder to remove the mirror from the topology. To remove the mirror in SQL Server, use the following cmdlet:</span></span>

```
Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]
```

<span data-ttu-id="83983-204">たとえば、ミラーリングを削除し、User データベースのデータベースを削除するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="83983-204">For example, to remove mirroring and drop the databases for the User databases, type the following:</span></span>

```
Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror
```

<span data-ttu-id="83983-205">`-DropExistingDatabasesOnMirror`オプションは、ミラーから削除するのには影響を受けるデータベースを指定します。</span><span class="sxs-lookup"><span data-stu-id="83983-205">The  `-DropExistingDatabasesOnMirror` option causes the affected databases to be deleted from the mirror.</span></span>

<span data-ttu-id="83983-206">その後、トポロジからミラーを削除するために次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="83983-206">Then, to remove the mirror from the topology, do the following:</span></span>

1. <span data-ttu-id="83983-207">トポロジ ビルダーで、プールを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="83983-207">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2. <span data-ttu-id="83983-208">[**SQL ストアのミラーリングを有効にする**] チェック ボックスをオフにし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="83983-208">Uncheck **Enable SQL Store Mirroring** and click **OK**.</span></span>

3. <span data-ttu-id="83983-209">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="83983-209">Publish the topology.</span></span>

## <a name="removing-a-mirroring-witness"></a><span data-ttu-id="83983-210">ミラーリング監視の削除</span><span class="sxs-lookup"><span data-stu-id="83983-210">Removing a Mirroring Witness</span></span>

<span data-ttu-id="83983-211">バック エンド サーバーの構成をミラー化から、ミラーリング監視サーバーを削除する必要がある場合は、この手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="83983-211">Use this procedure if you need to remove the witness from a Back End Server mirroring configuration.</span></span>

1. <span data-ttu-id="83983-212">トポロジ ビルダーで、プールを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="83983-212">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2. <span data-ttu-id="83983-213">[**SQL Server ミラーリング監視を自動フェールオーバーの有効化のために使用**] をオフにし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="83983-213">Uncheck **Use SQL Server mirroring witness to enable automatic failover** and click **OK**.</span></span>

3. <span data-ttu-id="83983-214">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="83983-214">Publish the topology.</span></span>

    <span data-ttu-id="83983-215">トポロジ ビルダーでトポロジを公開した後、次を含むメッセージが表示されます</span><span class="sxs-lookup"><span data-stu-id="83983-215">After publishing the topology, Topology Builder you will see a message that includes the following</span></span>

   ```
   Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
   ```

    <span data-ttu-id="83983-216">ただし、その手順に従っていないと、入力しないで`Uninstall-CsMirrorDatabase`全体のミラーリング構成をアンインストールするように。</span><span class="sxs-lookup"><span data-stu-id="83983-216">However, do not follow that step, and do not type  `Uninstall-CsMirrorDatabase` as that would uninstall the entire mirroring configuration.</span></span>

4. <span data-ttu-id="83983-217">SQL Server の構成から、ミラーリング監視サーバーだけを削除するには、[データベース ミラーリング セッション (SQL Server) からミラーリング監視サーバー](https://go.microsoft.com/fwlink/p/?LinkId=268456)の削除] 設定を指示します。</span><span class="sxs-lookup"><span data-stu-id="83983-217">To remove just the witness from the SQL Server configuration, follow the instructions in [Remove the Witness from a Database Mirroring Session (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268456).</span></span>


