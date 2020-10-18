---
title: 'Lync Server 2013: SQL Server のクラスター化の構成'
description: 'Lync Server 2013: SQL Server クラスタリングを構成します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server clustering
ms:assetid: d7b52ef1-573c-48ed-bb94-34e37b49645c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383982(v=OCS.15)
ms:contentKeyID: 56472032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f4b81b62d086de27659f564427ad6adde99ecac
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576753"
---
# <a name="configure-sql-server-clustering-for-lync-server-2013"></a><span data-ttu-id="cb50e-103">Lync Server 2013 の SQL Server クラスタリングを構成する</span><span class="sxs-lookup"><span data-stu-id="cb50e-103">Configure SQL Server clustering for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb50e-104">_**トピックの最終更新日:** 2014-01-10_</span><span class="sxs-lookup"><span data-stu-id="cb50e-104">_**Topic Last Modified:** 2014-01-10_</span></span>

<span data-ttu-id="cb50e-105">Microsoft Lync Server 2013 は、SQL Server 2012 および SQL Server 2008 R2 のクラスタリングをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="cb50e-105">Microsoft Lync Server 2013 supports clustering for SQL Server 2012 and SQL Server 2008 R2.</span></span> <span data-ttu-id="cb50e-106">サポートされている機能の詳細については、「 [Lync Server 2013 のデータベースソフトウェアサポート](lync-server-2013-database-software-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb50e-106">For details about what is supported, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span>

<span data-ttu-id="cb50e-107">Enterprise Edition フロントエンドサーバーとバックエンドデータベースをインストールして展開する前に、SQL Server クラスターをセットアップして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb50e-107">You should set up and configure the SQL Server cluster before you install and deploy the Enterprise Edition Front End Server and back-end database.</span></span> <span data-ttu-id="cb50e-108">SQL Server 2012 のフェールオーバークラスタリングのベストプラクティスとセットアップ手順については、「」を参照してください <https://technet.microsoft.com/library/hh231721.aspx> 。</span><span class="sxs-lookup"><span data-stu-id="cb50e-108">For best practices and setup instructions for failover clustering in SQL Server 2012, see <https://technet.microsoft.com/library/hh231721.aspx>.</span></span> <span data-ttu-id="cb50e-109">SQL Server 2008 のフェールオーバークラスタリングについては、「」を参照してください <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx> 。</span><span class="sxs-lookup"><span data-stu-id="cb50e-109">For failover clustering in SQL Server 2008, see <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx>.</span></span>

<span data-ttu-id="cb50e-110">SQL Server をインストールする際には、データベースの場所とログ ファイルの場所を管理するための SQL Server Management Studio をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb50e-110">When you install SQL Server, you should install SQL Server Management Studio to manage the locations for database and log file locations.</span></span> <span data-ttu-id="cb50e-111">SQL Server Management Studio は、SQL Server のインストール時にオプションのコンポーネントとしてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="cb50e-111">SQL Server Management Studio is installed as an optional component when you install SQL Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cb50e-112">SQL Server ベースのサーバーにデータベースをインストールおよび展開するには、データベース ファイルをインストールする SQL Server ベースのサーバーの SQL Server の sysadmins グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb50e-112">To install and deploy the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmin group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="cb50e-113">SQL Server の sysadmin グループのメンバーではない場合は、データベース ファイルを展開するまで、そのグループに追加してもらうように要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb50e-113">If you are not a member of the SQL Server sysadmin group, you will need to request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="cb50e-114">sysadmin グループのメンバーになれない場合、SQL Server のデータベース管理者にデータベースを構成および展開するためのスクリプトを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb50e-114">If you cannot be made a member of the sysadmin group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="cb50e-115">手順を実行するために必要な正しいユーザー権限とアクセス許可の詳細については、「 <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync server 2013 の SQL Server の展開権限</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb50e-115">For details about the proper user rights and permissions that you need to accomplish the procedures, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-sql-server-clustering"></a><span data-ttu-id="cb50e-116">SQL Server クラスタリングを構成するには</span><span class="sxs-lookup"><span data-stu-id="cb50e-116">To configure SQL Server clustering</span></span>

1.  <span data-ttu-id="cb50e-117">SQL Server クラスタリングのインストールと構成が完了したら、sql server インスタンスの仮想クラスター名 (「SQL Server のクラスター化のセットアップ」で構成されている) と SQL Server データベースのインスタンス名を使用して、SQL Server ストアをトポロジビルダーで定義します。</span><span class="sxs-lookup"><span data-stu-id="cb50e-117">After you have completed the installation and configuration of SQL Server clustering, you define the SQL Server store in Topology Builder by using the SQL Server instance virtual cluster name (as configured in the setup for SQL Server clustering) and the instance name of the SQL Server database.</span></span> <span data-ttu-id="cb50e-118">単一の SQL Server ベースのサーバーとは異なり、クラスター化された SQL Server ベースのサーバーには仮想ノードの完全修飾ドメイン名 (FQDN) を使用します。</span><span class="sxs-lookup"><span data-stu-id="cb50e-118">Different from a single SQL Server-based server, you will use the virtual node fully qualified domain name (FQDN) for a clustered SQL Server-based server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cb50e-119">個々の Windows Server クラスターノードは、トポロジビルダー用に構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="cb50e-119">The individual Windows Server cluster nodes do not have to be configured for Topology Builder.</span></span> <span data-ttu-id="cb50e-120">仮想 SQL Server のクラスター名のみを使用します。</span><span class="sxs-lookup"><span data-stu-id="cb50e-120">You will use only the virtual SQL Server cluster name.</span></span>

    
    </div>

2.  <span data-ttu-id="cb50e-121">トポロジビルダーを使用してデータベースを展開している場合は、SQL Server sysadmin グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb50e-121">If you are using Topology Builder to deploy your databases, you must be a member of the SQL Server sysadmin group.</span></span> <span data-ttu-id="cb50e-122">SQL Server sysadmin グループのメンバーであっても、ドメイン内に権限がない (たとえば、SQL Server データベース管理者の役割) 場合は、データベースを作成する権限がありますが、Lync Server で必要な情報を読み取ることはできません。</span><span class="sxs-lookup"><span data-stu-id="cb50e-122">If you are a member of the SQL Server sysadmin group, but you do not have privileges in the domain (for example, a SQL Server database administrator role), then you have the rights to create the databases but not to read necessary information in Lync Server.</span></span> <span data-ttu-id="cb50e-123">Lync Server の展開に必要なユーザー権限とアクセス許可の詳細については、「 [Lync server 2013 の SQL Server の展開権限](lync-server-2013-deployment-permissions-for-sql-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb50e-123">For details about the user rights and permissions necessary to deploying Lync Server, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

3.  <span data-ttu-id="cb50e-p108">SQL Server Management Studio を使用して、データベース フォルダーとログ ファイル フォルダーの既定値が、SQL Server クラスター内の共有ディスクに正しくマッピングされていることを確認してください。 これは、トポロジ ビルダーを使用してデータベースを使用する予定がある場合に必要な手順です。</span><span class="sxs-lookup"><span data-stu-id="cb50e-p108">Ensure that the database folder and log files folder defaults are mapped correctly to the shared disks in the SQL Server cluster by using SQL Server Management Studio. This is a required procedure if you will create databases by using Topology Builder.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cb50e-126">SQL Server Management Studio をインストールしていなかった場合は、SQL Server のインストールを再実行し、管理ツールを既存の SQL Server 展開の追加機能として選択することでインストールできます。</span><span class="sxs-lookup"><span data-stu-id="cb50e-126">If you did not install SQL Server Management Studio, you can install it by rerunning the SQL Server installation, and then selecting the management tool as an added feature for the existing SQL Server deployment.</span></span>

    
    </div>

4.  <span data-ttu-id="cb50e-127">トポロジビルダーまたは Windows PowerShell コマンドレットのいずれかを使用して、SQL Server ベースのサーバーのデータベースをインストールします。</span><span class="sxs-lookup"><span data-stu-id="cb50e-127">Install the databases for the SQL Server-based server by using either Topology Builder or Windows PowerShell cmdlets.</span></span> <span data-ttu-id="cb50e-128">トポロジビルダーを使用するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="cb50e-128">To use Topology Builder, use the following procedure.</span></span> <span data-ttu-id="cb50e-129">Windows PowerShell コマンドレットを使用するには、「 [lync server 2013 での Lync Server 管理シェルを使用したデータベースのインストール](lync-server-2013-database-installation-using-lync-server-management-shell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb50e-129">To use Windows PowerShell cmdlets, see [Database installation using Lync Server Management Shell in Lync Server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="to-create-databases-using-topology-builder"></a><span data-ttu-id="cb50e-130">トポロジビルダーを使用してデータベースを作成するには</span><span class="sxs-lookup"><span data-stu-id="cb50e-130">To create databases using Topology Builder</span></span>

1.  <span data-ttu-id="cb50e-131">トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb50e-131">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="cb50e-132">次の手順では、トポロジビルダーでトポロジを定義して構成していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="cb50e-132">The following procedure assumes that you have defined and configured your topology in Topology Builder.</span></span> <span data-ttu-id="cb50e-133">トポロジの定義の詳細については、「<A href="lync-server-2013-defining-and-configuring-the-topology.md">Lync Server 2013 でのトポロジの定義と構成</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb50e-133">For details about defining your topology, see<A href="lync-server-2013-defining-and-configuring-the-topology.md">Defining and configuring the topology in Lync Server 2013</A>.</span></span> <span data-ttu-id="cb50e-134">トポロジ ビルダーを使用してトポロジを公開し、データベースを構成するには、正しいユーザー権限およびグループ メンバーシップを持つユーザーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb50e-134">To use Topology Builder to publish the topology and configure the database, you must log on as a user with the correct user rights and group memberships.</span></span> <span data-ttu-id="cb50e-135">必要な権限およびグループメンバーシップの詳細については、「 <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync server 2013 の SQL Server の展開権限</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb50e-135">For details about the required rights and group memberships, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="cb50e-136">トポロジビルダーで、トポロジを公開するときに、[ **データベースの作成** ] ページで [ **詳細設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb50e-136">In Topology Builder, as you publish the topology, on the **Create databases** page, click **Advanced**.</span></span>

3.  <span data-ttu-id="cb50e-p111">**[データベース ファイルの場所の選択]** ページには、SQL Server クラスターへのデータベース ファイルの展開方法を決定する 2 つのオプションがあります。次のどちらかを選択します。</span><span class="sxs-lookup"><span data-stu-id="cb50e-p111">The **Select Database File Location** page has two options that determine how the database files will be deployed to the SQL Server cluster. Select one of the following:</span></span>
    
      - <span data-ttu-id="cb50e-139">**データベースファイルの場所を自動的に決定します。**</span><span class="sxs-lookup"><span data-stu-id="cb50e-139">**Automatically determine the database file location.**</span></span> <span data-ttu-id="cb50e-140">この選択では、アルゴリズムを使用して、SQL Server ベースのサーバー上のドライブ構成に基づいてデータベースログとデータファイルの場所を特定します。</span><span class="sxs-lookup"><span data-stu-id="cb50e-140">This selection uses an algorithm to determine the database log and data file locations based on the drive configuration on the SQL Server-based server.</span></span> <span data-ttu-id="cb50e-141">これらのファイルは、最適なパフォーマンスを実現するための方法で配布されます。</span><span class="sxs-lookup"><span data-stu-id="cb50e-141">The files will be distributed in such a way as to attempt to provide optimal performance.</span></span>
    
      - <span data-ttu-id="cb50e-142">[既定の SQL Server インスタンスを使用する]。</span><span class="sxs-lookup"><span data-stu-id="cb50e-142">Use SQL Server instance defaults.</span></span> <span data-ttu-id="cb50e-143">このオプションを選択すると、SQL Server インスタンスの設定に従ってログおよびデータ ファイルがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="cb50e-143">Selecting this option will install the log and data files according to the SQL Server instance settings.</span></span> <span data-ttu-id="cb50e-144">SQL Server にデータベース ファイルを展開した後、特定の SQL Server の構成要件でパフォーマンスが最適となるよう、SQL Server データベースの管理者がファイルの場所を変更する場合があります。</span><span class="sxs-lookup"><span data-stu-id="cb50e-144">After deployment of the database files to the SQL Server, your SQL Server database administrator may want to relocate the files to optimize performance for your particular SQL Server configuration requirements.</span></span>

4.  <span data-ttu-id="cb50e-145">トポロジの公開を完了し、操作中にエラーが発生しなかったことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="cb50e-145">Complete the publishing of the topology and confirm that there were no errors during the operation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

