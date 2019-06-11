---
title: 'Lync Server 2013: SQL Server クラスタリングを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure SQL Server clustering
ms:assetid: d7b52ef1-573c-48ed-bb94-34e37b49645c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383982(v=OCS.15)
ms:contentKeyID: 56472032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 279c6581d0a56193c094c3dd7b9638fd74e2e60c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-clustering-for-lync-server-2013"></a><span data-ttu-id="2625b-102">Lync Server 2013 用の SQL Server クラスタリングを構成する</span><span class="sxs-lookup"><span data-stu-id="2625b-102">Configure SQL Server clustering for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2625b-103">_**最終更新日:** 2014-01-10_</span><span class="sxs-lookup"><span data-stu-id="2625b-103">_**Topic Last Modified:** 2014-01-10_</span></span>

<span data-ttu-id="2625b-104">Microsoft Lync Server 2013 は、SQL Server 2012 と SQL Server 2008 R2 のクラスタリングをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="2625b-104">Microsoft Lync Server 2013 supports clustering for SQL Server 2012 and SQL Server 2008 R2.</span></span> <span data-ttu-id="2625b-105">サポートされる機能の詳細については、「 [Lync Server 2013 でのデータベースソフトウェアのサポート](lync-server-2013-database-software-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2625b-105">For details about what is supported, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span>

<span data-ttu-id="2625b-106">Enterprise Edition フロントエンドサーバーとバックエンドデータベースをインストールして展開する前に、SQL Server クラスターをセットアップして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2625b-106">You should set up and configure the SQL Server cluster before you install and deploy the Enterprise Edition Front End Server and back-end database.</span></span> <span data-ttu-id="2625b-107">SQL Server 2012 のフェールオーバークラスタリングのベストプラクティスとセットアップ手順につい<http://technet.microsoft.com/en-us/library/hh231721.aspx>ては、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2625b-107">For best practices and setup instructions for failover clustering in SQL Server 2012, see <http://technet.microsoft.com/en-us/library/hh231721.aspx>.</span></span> <span data-ttu-id="2625b-108">SQL Server 2008 のフェールオーバークラスタリングについ<http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>ては、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2625b-108">For failover clustering in SQL Server 2008, see <http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>.</span></span>

<span data-ttu-id="2625b-p103">SQL Server をインストールする際は、SQL Server Management Studio をインストールしてデータベースとログ ファイルの場所を管理する必要があります。SQL Server Management Studio は、SQL Server のインストール時にオプション コンポーネントとしてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="2625b-p103">When you install SQL Server, you should install SQL Server Management Studio to manage the locations for database and log file locations. SQL Server Management Studio is installed as an optional component when you install SQL Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2625b-111">SQL Server ベースのサーバーにデータベースをインストールして展開するには、データベースファイルをインストールする SQL server ベースのサーバーの SQL Server sysadmin グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="2625b-111">To install and deploy the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmin group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="2625b-112">SQL Server sysadmin グループのメンバーでない場合は、データベースファイルが展開されるまで、グループに追加するように依頼する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2625b-112">If you are not a member of the SQL Server sysadmin group, you will need to request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="2625b-113">Sysadmin グループのメンバーになることができない場合は、SQL Server データベース管理者に、データベースを構成して展開するためのスクリプトを用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2625b-113">If you cannot be made a member of the sysadmin group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="2625b-114">手順を実行するために必要な適切なユーザー権限と権限の詳細については、「 <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync server 2013 の SQL Server の展開権限</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2625b-114">For details about the proper user rights and permissions that you need to accomplish the procedures, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-sql-server-clustering"></a><span data-ttu-id="2625b-115">SQL Server クラスタリングを構成するには</span><span class="sxs-lookup"><span data-stu-id="2625b-115">To configure SQL Server clustering</span></span>

1.  <span data-ttu-id="2625b-116">SQL Server クラスタリングのインストールと構成を完了した後は、sql server の仮想クラスター名 (SQL Server クラスタリングのセットアップで構成されます) とインスタンスを使用して、トポロジビルダーで SQL Server ストアを定義します。SQL Server データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="2625b-116">After you have completed the installation and configuration of SQL Server clustering, you define the SQL Server store in Topology Builder by using the SQL Server instance virtual cluster name (as configured in the setup for SQL Server clustering) and the instance name of the SQL Server database.</span></span> <span data-ttu-id="2625b-117">SQL Server ベースの1台のサーバーとは異なり、クラスター化された SQL Server ベースのサーバーには仮想ノードの完全修飾ドメイン名 (FQDN) を使用します。</span><span class="sxs-lookup"><span data-stu-id="2625b-117">Different from a single SQL Server-based server, you will use the virtual node fully qualified domain name (FQDN) for a clustered SQL Server-based server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2625b-118">個々の Windows Server クラスターノードは、トポロジビルダー用に構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2625b-118">The individual Windows Server cluster nodes do not have to be configured for Topology Builder.</span></span> <span data-ttu-id="2625b-119">仮想 SQL Server クラスター名のみが使用されます。</span><span class="sxs-lookup"><span data-stu-id="2625b-119">You will use only the virtual SQL Server cluster name.</span></span>

    
    </div>

2.  <span data-ttu-id="2625b-120">トポロジビルダーを使用してデータベースを展開している場合は、SQL Server sysadmin グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="2625b-120">If you are using Topology Builder to deploy your databases, you must be a member of the SQL Server sysadmin group.</span></span> <span data-ttu-id="2625b-121">SQL Server sysadmin グループのメンバーであるが、ドメインの権限がない場合 (たとえば、SQL Server データベース管理者の役割)、データベースを作成する権限はありますが、Lync Server で必要な情報を読み取ることはできません。</span><span class="sxs-lookup"><span data-stu-id="2625b-121">If you are a member of the SQL Server sysadmin group, but you do not have privileges in the domain (for example, a SQL Server database administrator role), then you have the rights to create the databases but not to read necessary information in Lync Server.</span></span> <span data-ttu-id="2625b-122">Lync Server の展開に必要なユーザー権限と権限の詳細については、「 [Lync server 2013 の SQL Server の展開権限](lync-server-2013-deployment-permissions-for-sql-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2625b-122">For details about the user rights and permissions necessary to deploying Lync Server, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

3.  <span data-ttu-id="2625b-123">SQL Server Management Studio を使用して、データベースフォルダーとログファイルフォルダーの既定値が、SQL Server クラスターの共有ディスクに正しくマッピングされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2625b-123">Ensure that the database folder and log files folder defaults are mapped correctly to the shared disks in the SQL Server cluster by using SQL Server Management Studio.</span></span> <span data-ttu-id="2625b-124">トポロジビルダーを使用してデータベースを作成する場合は、この手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2625b-124">This is a required procedure if you will create databases by using Topology Builder.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2625b-125">SQL Server Management Studio をインストールしていない場合は、SQL Server のインストールを再実行して、既存の SQL Server 展開の追加機能として管理ツールを選択してインストールできます。</span><span class="sxs-lookup"><span data-stu-id="2625b-125">If you did not install SQL Server Management Studio, you can install it by rerunning the SQL Server installation, and then selecting the management tool as an added feature for the existing SQL Server deployment.</span></span>

    
    </div>

4.  <span data-ttu-id="2625b-126">トポロジビルダーまたは Windows PowerShell コマンドレットを使用して、SQL Server ベースのサーバーのデータベースをインストールします。</span><span class="sxs-lookup"><span data-stu-id="2625b-126">Install the databases for the SQL Server-based server by using either Topology Builder or Windows PowerShell cmdlets.</span></span> <span data-ttu-id="2625b-127">トポロジビルダーを使用するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="2625b-127">To use Topology Builder, use the following procedure.</span></span> <span data-ttu-id="2625b-128">Windows PowerShell コマンドレットを使用するには、「 [lync server 2013 の Lync Server 管理シェルを使用したデータベースのインストール](lync-server-2013-database-installation-using-lync-server-management-shell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2625b-128">To use Windows PowerShell cmdlets, see [Database installation using Lync Server Management Shell in Lync Server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="to-create-databases-using-topology-builder"></a><span data-ttu-id="2625b-129">トポロジビルダーを使用してデータベースを作成するには</span><span class="sxs-lookup"><span data-stu-id="2625b-129">To create databases using Topology Builder</span></span>

1.  <span data-ttu-id="2625b-130">トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server Topology Builder**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="2625b-130">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="2625b-131">次の手順では、トポロジビルダーでトポロジを定義して構成していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="2625b-131">The following procedure assumes that you have defined and configured your topology in Topology Builder.</span></span> <span data-ttu-id="2625b-132">トポロジの定義の詳細については、「<A href="lync-server-2013-defining-and-configuring-the-topology.md">Lync Server 2013 でトポロジを定義して構成する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2625b-132">For details about defining your topology, see<A href="lync-server-2013-defining-and-configuring-the-topology.md">Defining and configuring the topology in Lync Server 2013</A>.</span></span> <span data-ttu-id="2625b-133">トポロジビルダーを使用してトポロジを公開し、データベースを構成するには、適切なユーザー権限とグループメンバーシップを持つユーザーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2625b-133">To use Topology Builder to publish the topology and configure the database, you must log on as a user with the correct user rights and group memberships.</span></span> <span data-ttu-id="2625b-134">必要な権限とグループメンバーシップの詳細については、「 <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync server 2013 の SQL Server の展開権限</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2625b-134">For details about the required rights and group memberships, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="2625b-135">トポロジビルダーでは、トポロジを公開するときに、[**データベースの作成**] ページで [**詳細設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2625b-135">In Topology Builder, as you publish the topology, on the **Create databases** page, click **Advanced**.</span></span>

3.  <span data-ttu-id="2625b-136">**[データベースファイルの場所の選択**] ページには、データベースファイルが SQL Server クラスターにどのように展開されるかを決定する2つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="2625b-136">The **Select Database File Location** page has two options that determine how the database files will be deployed to the SQL Server cluster.</span></span> <span data-ttu-id="2625b-137">次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="2625b-137">Select one of the following:</span></span>
    
      - <span data-ttu-id="2625b-138">**データベースファイルの場所を自動的に特定します。**</span><span class="sxs-lookup"><span data-stu-id="2625b-138">**Automatically determine the database file location.**</span></span> <span data-ttu-id="2625b-139">この選択では、アルゴリズムを使って、SQL Server ベースのサーバーのドライブ構成に基づいて、データベースログとデータファイルの場所を特定します。</span><span class="sxs-lookup"><span data-stu-id="2625b-139">This selection uses an algorithm to determine the database log and data file locations based on the drive configuration on the SQL Server-based server.</span></span> <span data-ttu-id="2625b-140">ファイルは、最適なパフォーマンスを実現するための手段として配布されます。</span><span class="sxs-lookup"><span data-stu-id="2625b-140">The files will be distributed in such a way as to attempt to provide optimal performance.</span></span>
    
      - <span data-ttu-id="2625b-141">[既定の SQL Server インスタンスを使用する]。</span><span class="sxs-lookup"><span data-stu-id="2625b-141">Use SQL Server instance defaults.</span></span> <span data-ttu-id="2625b-142">このオプションを選択すると、SQL Server インスタンスの設定に従ってログとデータファイルがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="2625b-142">Selecting this option will install the log and data files according to the SQL Server instance settings.</span></span> <span data-ttu-id="2625b-143">Sql server にデータベースファイルを展開した後、SQL server データベース管理者は、特定の SQL Server 構成要件のパフォーマンスを最適化するために、ファイルを再配置することができます。</span><span class="sxs-lookup"><span data-stu-id="2625b-143">After deployment of the database files to the SQL Server, your SQL Server database administrator may want to relocate the files to optimize performance for your particular SQL Server configuration requirements.</span></span>

4.  <span data-ttu-id="2625b-144">トポロジの発行を完了し、操作中にエラーがないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="2625b-144">Complete the publishing of the topology and confirm that there were no errors during the operation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

