---
title: 'Lync Server 2013: Lync Server 管理シェルを使用したデータベースのインストール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database installation using Lync Server Management Shell
ms:assetid: c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398832(v=OCS.15)
ms:contentKeyID: 48185401
ms.date: 06/16/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c617d323eb00476b53677b670c8cc6db0b8d05c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728577"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-installation-using-lync-server-management-shell-in-lync-server-2013"></a><span data-ttu-id="55753-102">Lync Server 2013 での Lync Server 管理シェルを使用したデータベースのインストール</span><span class="sxs-lookup"><span data-stu-id="55753-102">Database installation using Lync Server Management Shell in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55753-103">_**最終更新日:** 2016-06-16_</span><span class="sxs-lookup"><span data-stu-id="55753-103">_**Topic Last Modified:** 2016-06-16_</span></span>

<span data-ttu-id="55753-104">サーバー管理者と SQL Server 管理者との間で役割と責任を分離すると、実装で遅延が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="55753-104">Separation of roles and responsibilities between server administrators and SQL Server administrators can result in delays in implementation.</span></span> <span data-ttu-id="55753-105">Lync Server 2013 は、役割ベースのアクセス制御 (RBAC) を使用して、このような問題を軽減します。</span><span class="sxs-lookup"><span data-stu-id="55753-105">Lync Server 2013 uses role-based access control (RBAC) to mitigate these difficulties.</span></span> <span data-ttu-id="55753-106">場合によっては、SQL Server 管理者が、RBAC の外部の SQL Server ベースのサーバーにデータベースのインストールを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="55753-106">In some instances, the SQL Server administrator must manage the installation of databases on the SQL Server-based server outside RBAC.</span></span> <span data-ttu-id="55753-107">Lync Server 2013 管理シェルは、SQL Server 管理者が Windows PowerShell コマンドレットを実行して、適切なデータとログファイルを使ってデータベースを構成するための手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="55753-107">The Lync Server 2013 Management Shell provides a way for the SQL Server administrator to run Windows PowerShell cmdlets designed to configure the databases with the correct data and log files.</span></span> <span data-ttu-id="55753-108">詳細については、「 [Lync server 2013 の SQL Server の展開権限](lync-server-2013-deployment-permissions-for-sql-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55753-108">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="55753-109">次の手順では、少なくとも Lync Server 2013 OCSCore .msi、SQL Server Native Client (sqlncli) Microsoft SQL server 2012 の管理オブジェクト、Microsoft sql Server 2012 および Microsoft SQL Server 2012 ADOMD.NET の CLR 型がインストールされていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="55753-109">The following procedure assumes that at a minimum the Lync Server 2013 OCSCore.msi, SQL Server Native Client (sqlncli.msi) Microsoft SQL Server 2012 Management Objects, CLR Types for Microsoft SQL Server 2012 and Microsoft SQL Server 2012 ADOMD.NET are installed.</span></span> <span data-ttu-id="55753-110">OCSCore .msi は、インストールメディアの \Setup\AMD64\Setup ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="55753-110">The OCSCore.msi is located on the installation media in the \Setup\AMD64\Setup directory.</span></span> <span data-ttu-id="55753-111">残りのコンポーネントは、「¥の場合」に記載されています。</span><span class="sxs-lookup"><span data-stu-id="55753-111">The remaining components are located in \Setup\amd64.</span></span> <span data-ttu-id="55753-112">さらに、Lync Server 2013 の Active Directory の準備が正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="55753-112">Additionally, Active Directory preparation for Lync Server 2013 has been successfully completed.</span></span>



</div>

<span data-ttu-id="55753-113">**CsDatabase をインストール**すると、データベースのインストールに使用する Windows PowerShell コマンドレットが表示されます。</span><span class="sxs-lookup"><span data-stu-id="55753-113">**Install-CsDatabase** is the Windows PowerShell cmdlet you use to install the databases.</span></span> <span data-ttu-id="55753-114">**CsDatabase**コマンドレットには、多数のパラメーターがあります。一部のパラメーターはここで説明しています。</span><span class="sxs-lookup"><span data-stu-id="55753-114">The **Install-CsDatabase** cmdlet has a large number of parameters, only a few of which are discussed here.</span></span> <span data-ttu-id="55753-115">使用可能なパラメーターの詳細については、「Lync Server 2013 管理シェルのドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55753-115">For details about the possible parameters, see the Lync Server 2013 Management Shell documentation.</span></span>

<div class=" ">


> [!WARNING]  
> <span data-ttu-id="55753-116">パフォーマンスが低下したり、タイムアウトの問題が発生したりする場合は、SQL Server ベースのサーバーを参照するときに常に完全修飾ドメイン名 (Fqdn) を使用します。</span><span class="sxs-lookup"><span data-stu-id="55753-116">To avoid performance and possible time-out issues, always use fully qualified domain names (FQDNs) when referring to SQL Server-based servers.</span></span> <span data-ttu-id="55753-117">ホスト名のみの参照を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="55753-117">Avoid using host name-only references.</span></span> <span data-ttu-id="55753-118">たとえば、sqlbe01.contoso.net を使用しますが、SQLBE01 の使用は避けてください。</span><span class="sxs-lookup"><span data-stu-id="55753-118">For example, use sqlbe01.contoso.net, but avoid using SQLBE01.</span></span>



</div>

<span data-ttu-id="55753-119">データベースをインストールするには、 **CsDatabase をインストール**するために、準備された SQL server ベースのサーバーにデータベースを配置するために、3つの主な方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="55753-119">For installing databases, **Install-CsDatabase** uses three primary methods for placing the databases onto the prepared SQL Server-based server:</span></span>

  - <span data-ttu-id="55753-120">DatabasePaths または UseDefaultSqlPath なしで **、CsDatabase を**実行します。</span><span class="sxs-lookup"><span data-stu-id="55753-120">Run **Install-CsDatabase** without DatabasePaths or UseDefaultSqlPath.</span></span> <span data-ttu-id="55753-121">このコマンドレットは、組み込みのアルゴリズムを使って、ログファイルとデータファイルの最適な配置を決定します。</span><span class="sxs-lookup"><span data-stu-id="55753-121">The cmdlet uses a built in algorithm to determine the best placement for the log and data files.</span></span> <span data-ttu-id="55753-122">このアルゴリズムは、スタンドアロンの SQL Server 実装でのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="55753-122">The algorithm only works for stand-alone SQL Server implementations.</span></span>

  - <span data-ttu-id="55753-123">DatabasePaths パラメーターを使用して**CsDatabase Install**を実行します。</span><span class="sxs-lookup"><span data-stu-id="55753-123">Run **Install-CsDatabase** with the DatabasePaths parameter.</span></span> <span data-ttu-id="55753-124">DatabasePaths パラメーターが定義されている場合、ログとデータファイルの場所を最適化する組み込みアルゴリズムは使用されません。</span><span class="sxs-lookup"><span data-stu-id="55753-124">The built-in algorithm to optimize log and data file locations is not used if the DatabasePaths parameter is defined.</span></span> <span data-ttu-id="55753-125">このパラメーターを使うと、ログとデータファイルが配置される場所を定義できます。</span><span class="sxs-lookup"><span data-stu-id="55753-125">Using this parameter allows you to define the locations where log and data files will be deployed.</span></span>

  - <span data-ttu-id="55753-126">UseDefaultSqlPaths で**CsDatabase Install**を実行します。</span><span class="sxs-lookup"><span data-stu-id="55753-126">Run **Install-CsDatabase** with UseDefaultSqlPaths.</span></span> <span data-ttu-id="55753-127">このオプションでは、組み込みのアルゴリズムを使ってログとデータファイルの場所を最適化しません。</span><span class="sxs-lookup"><span data-stu-id="55753-127">This option does not use the built-in algorithm to optimize the log and data file locations.</span></span> <span data-ttu-id="55753-128">ログとデータファイルは、SQL Server 管理者が設定した既定値に従って展開されます。</span><span class="sxs-lookup"><span data-stu-id="55753-128">Log and data file are deployed according to the defaults set by the SQL Server administrator.</span></span> <span data-ttu-id="55753-129">通常、これらのパスは、SQL Server のログファイルとデータファイルの自動管理を目的として設定され、Lync Server 2013 のセットアップには関連付けられません。</span><span class="sxs-lookup"><span data-stu-id="55753-129">These paths are typically set for the purpose of automatic administration of log and data files on the SQL Server in advance, and are not associated with the setup of Lync Server 2013.</span></span>

  - <span data-ttu-id="55753-130">DatabasePathMap パラメーターを使って、各データベースとそのログファイルの場所を明示的に指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="55753-130">The DatabasePathMap parameter can also be used to explicitly specify a location for each database and its respective log file.</span></span>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-central-management-store"></a><span data-ttu-id="55753-131">Windows PowerShell コマンドレットを使用して SQL Server の中央管理ストアを構成するには</span><span class="sxs-lookup"><span data-stu-id="55753-131">To use Windows PowerShell cmdlets to configure the SQL Server Central Management store</span></span>

1.  <span data-ttu-id="55753-132">任意のコンピューターで、SQL Server ベースのサーバー上でデータベースを作成するための管理者資格情報を使ってログオンします。</span><span class="sxs-lookup"><span data-stu-id="55753-132">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="55753-133">詳細については、「 [Lync server 2013 の SQL Server の展開権限](lync-server-2013-deployment-permissions-for-sql-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55753-133">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

2.  <span data-ttu-id="55753-134">Lync Server 2013 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="55753-134">Open the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="55753-135">Windows PowerShell の実行ポリシーを調整していない場合は、Windows PowerShell スクリプトの実行を許可するようにポリシーを調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="55753-135">If you have not adjusted the execution policy for Windows PowerShell, you must adjust the policy to allow Windows PowerShell scripts to run.</span></span> <span data-ttu-id="55753-136">詳細については、の「実行ポリシーを[http://go.microsoft.com/fwlink/p/?linkId=203093](http://go.microsoft.com/fwlink/p/?linkid=203093)調査する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55753-136">For details, see “Examining the Execution Policy” at [http://go.microsoft.com/fwlink/p/?linkId=203093](http://go.microsoft.com/fwlink/p/?linkid=203093).</span></span>

3.  <span data-ttu-id="55753-137">[**インストール-CsDatabase**コマンドレットを使用して、中央管理ストアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="55753-137">Use the **Install-CsDatabase** cmdlet to install the Central Management store.</span></span>
    
       ```powershell
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <fully qualified domain name of SQL Server> 
        -SqlInstanceName <named instance> -DatabasePaths <logfile path>,<database file path> 
        -Report <path to report file>
       ```
    
       ```powershell
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn sqlbe.contoso.net -SqlInstanceName rtc -DatabasePaths "C:\CSDB-Logs","C:\CSDB-CMS" -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="55753-138">Report パラメーターは省略可能ですが、インストールプロセスを文書化する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="55753-138">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

4.  <span data-ttu-id="55753-139">**CsDatabase-DatabasePaths**では、最大6つの path パラメーターを使うことができます。それぞれ、SQL Server データとログファイルの配置で定義されたドライブのパスを定義します。</span><span class="sxs-lookup"><span data-stu-id="55753-139">**Install-CsDatabase –DatabasePaths** can use up to six path parameters, each defining the paths for the drives as defined in SQL Server Data and Log File Placement.</span></span> <span data-ttu-id="55753-140">Lync Server 2013 のデータベース構成の論理的なルールにより、ドライブは2、4、または6のバケットに分けて解析されます。</span><span class="sxs-lookup"><span data-stu-id="55753-140">By the logical rules of the database configuration in Lync Server 2013, drives are parsed out into buckets of two, four, or six.</span></span> <span data-ttu-id="55753-141">SQL Server の構成とバケット数に応じて、2つのパス、4つのパス、または6つのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="55753-141">Depending on your SQL Server configuration and the number of buckets, you will supply two paths, four paths, or six paths.</span></span>
    
    <span data-ttu-id="55753-142">3つのドライブがある場合は、ログが優先され、データファイルは後で配布されます。</span><span class="sxs-lookup"><span data-stu-id="55753-142">If you have three drives, the log gets priority and the data files are distributed after.</span></span> <span data-ttu-id="55753-143">6台のドライブで構成された SQL Server ベースのサーバーの例:</span><span class="sxs-lookup"><span data-stu-id="55753-143">An example for a SQL Server-based server configured with six drives:</span></span>
    ```powershell
    Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"
    ```
5.  <span data-ttu-id="55753-144">データベースのインストールが完了したら、Lync Server 2013 管理シェルを閉じるか、またはトポロジビルダーで定義されている Lync Server 2013 構成データベースのインストールに進みます。</span><span class="sxs-lookup"><span data-stu-id="55753-144">When the database installation completes, you can close Lync Server 2013 Management Shell or proceed to the installation of the Lync Server 2013 configured databases defined in Topology Builder.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-configured-databases"></a><span data-ttu-id="55753-145">Windows PowerShell コマンドレットを使用して、SQL Server トポロジで構成されたデータベースを構成するには</span><span class="sxs-lookup"><span data-stu-id="55753-145">To use Windows PowerShell cmdlets to configure the SQL Server topology configured databases</span></span>

1.  <span data-ttu-id="55753-146">Lync server 2013 用にトポロジビルダーで構成されたデータベースをインストールするには、Lync Server 2013 管理者がトポロジを公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="55753-146">To install the Topology Builder configured databases for Lync Server 2013, the Lync Server 2013 administrator must publish the topology.</span></span> <span data-ttu-id="55753-147">詳細については、展開ドキュメントの「 [Lync Server 2013 でトポロジを発行](lync-server-2013-publish-the-topology.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55753-147">For details, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="55753-148">任意のコンピューターで、SQL Server ベースのサーバー上でデータベースを作成するための管理者資格情報を使ってログオンします。</span><span class="sxs-lookup"><span data-stu-id="55753-148">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="55753-149">「 [Lync server 2013 の SQL Server の展開権限](lync-server-2013-deployment-permissions-for-sql-server.md)」のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="55753-149">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="55753-150">SQL Server ベースのデータベースを構成できるようにするには、ここで説明する手順を実行するために使用した SQL Server 管理者アカウントも、SQL Server を実行しているサーバー上の管理者グループ (または同等の機能) のメンバーであることを確認して、一元管理を保持する必要があります。サーバーの役割。</span><span class="sxs-lookup"><span data-stu-id="55753-150">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="55753-151">これは、SQL Server のデータベースのインストールまたは構成が必要な追加の Lync Server 2013 プールを確認する場合に特に重要です。</span><span class="sxs-lookup"><span data-stu-id="55753-151">This is especially important to check for any additional Lync Server 2013 pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="55753-152">たとえば、2つ目のプール (pool02) を展開しているが、サーバーの全体管理サーバーの役割が pool01 によって保持されている場合です。</span><span class="sxs-lookup"><span data-stu-id="55753-152">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="55753-153">Sql Server sysadmin グループ (または同等の機能) には、SQL Server ベースの両方のデータベースに対するアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="55753-153">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="55753-154">まだ開いていない場合は、Lync Server 2013 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="55753-154">Open Lync Server 2013 Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="55753-155">**CsDatabase**コマンドレットを使用して、トポロジビルダーで構成されたデータベースをインストールします。</span><span class="sxs-lookup"><span data-stu-id="55753-155">Use the **Install-CsDatabase** cmdlet to install the Topology Builder configured databases.</span></span>
    
       ```powershell
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <fully qualified domain name of SQL Server> 
         -DatabasePaths <logfile path>,<database file path> -Report <path to report file>
       ```
    
       ```powershell
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe.contoso.net 
        -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="55753-156">Report パラメーターは省略可能ですが、インストールプロセスを文書化する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="55753-156">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

5.  <span data-ttu-id="55753-157">データベースのインストールが完了したら、Lync Server 2013 Management Shell を閉じます。</span><span class="sxs-lookup"><span data-stu-id="55753-157">When the database installation completes, close Lync Server 2013 Management Shell.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-using-the-databasepathmap-parameter"></a><span data-ttu-id="55753-158">Windows PowerShell コマンドレットを使用して、DatabasePathMap パラメーターを使って SQL Server トポロジを構成するには</span><span class="sxs-lookup"><span data-stu-id="55753-158">To use Windows PowerShell cmdlets to configure the SQL Server topology using the DatabasePathMap parameter</span></span>

1.  <span data-ttu-id="55753-159">Lync server 2013 のデータベースをインストールするには、Lync Server の管理者が、パスを作成し、事前定義された一連のルールに従ってデータベースファイルとログファイルを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="55753-159">To install databases for Lync Server 2013, the Lync Server administrator must create the paths and deploy the databases files and log files according to a predefined set of rules.</span></span>

2.  <span data-ttu-id="55753-160">任意のコンピューターで、SQL Server ベースのサーバー上でデータベースを作成するための管理者資格情報を使ってログオンします。</span><span class="sxs-lookup"><span data-stu-id="55753-160">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="55753-161">「 [Lync server 2013 の SQL Server の展開権限](lync-server-2013-deployment-permissions-for-sql-server.md)」のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="55753-161">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="55753-162">SQL Server ベースのデータベースを構成できるようにするには、ここで説明する手順を実行するために使用した SQL Server 管理者アカウントも、SQL Server を実行しているサーバー上の管理者グループ (または同等の機能) のメンバーであることを確認して、一元管理を保持する必要があります。サーバーの役割。</span><span class="sxs-lookup"><span data-stu-id="55753-162">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="55753-163">これは、SQL Server データベースのインストールまたは構成が必要な追加の Lync Server プールを確認する場合に特に重要です。</span><span class="sxs-lookup"><span data-stu-id="55753-163">This is especially important to check for any additional Lync Server pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="55753-164">たとえば、2つ目のプール (pool02) を展開しているが、サーバーの全体管理サーバーの役割が pool01 によって保持されている場合です。</span><span class="sxs-lookup"><span data-stu-id="55753-164">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="55753-165">Sql Server sysadmin グループ (または同等の機能) には、SQL Server ベースの両方のデータベースに対するアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="55753-165">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="55753-166">まだ開いていない場合は、Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="55753-166">Open Lync Server Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="55753-167">DatabasePathMap パラメーターと PowerShell ハッシュテーブルを使って、 **CsDatabase**コマンドレットを使用して、トポロジビルダーで構成されたデータベースをインストールします。</span><span class="sxs-lookup"><span data-stu-id="55753-167">Use the **Install-CsDatabase** cmdlet with the DatabasePathMap parameter and a PowerShell hash table to install the Topology Builder configured databases.</span></span>

5.  <span data-ttu-id="55753-168">このコード例では、データベースに対して定義されているパスは、– DatabasePathMap パラメーターと定義されたハッシュテーブル (すべてのデータベース (.mdf) ファイルの場合\\は "c: csdata"、すべてのログ (.ldf) ファイルに\\ついては "c: csdata" を使用します) を使って特定できます。</span><span class="sxs-lookup"><span data-stu-id="55753-168">In the example code, the paths defined for the databases can be determined in a granular manner by using the –DatabasePathMap parameter and a defined hash table as follows (the example uses “C:\\CSData” for all database (.mdf) files, and “C:\\CSLogFiles” for all log (.ldf) files.</span></span> <span data-ttu-id="55753-169">必要に応じて、CsDatabase からフォルダーを作成します):</span><span class="sxs-lookup"><span data-stu-id="55753-169">Folder will be created as needed by Install-CsDatabase):</span></span>
    ```powershell
    $pathmap = @{
    "BackendStore:BlobStore:DbPath"="C:\CsData";"BackendStore:BlobStore:LogPath"="C:\CsLogFiles"
    "BackendStore:RtcSharedDatabase:DbPath"="C:\CsData";"BackendStore:RtcSharedDatabase:LogPath"="C:\CsLogFiles"
    "ABSStore:AbsDatabase:DbPath"="C:\CsData";"ABSStore:AbsDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:RgsConfigDatabase:DbPath"="C:\CsData";"ApplicationStore:RgsConfigDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:RgsDynDatabase:DbPath"="C:\CsData";"ApplicationStore:RgsDynDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:CpsDynDatabase:DbPath"="C:\CsData";"ApplicationStore:CpsDynDatabase:LogPath"="C:\CsLogFiles"
    "ArchivingStore:ArchivingDatabase:DbPath"="C:\CsData";"ArchivingStore:ArchivingDatabase:LogPath"="C:\CsLogFiles"
    "MonitoringStore:MonitoringDatabase:DbPath"="C:\CsData";"MonitoringStore:MonitoringDatabase:LogPath"="C:\CsLogFiles"
    "MonitoringStore:QoEMetricsDatabase:DbPath"="C:\CsData";"MonitoringStore:QoEMetricsDatabase:LogPath"="C:\CsLogFiles"
    }
    Install-CsDatabase -ConfigureDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathMap $pathmap
    ```
6.  <span data-ttu-id="55753-170">データベースとログファイルには、ターゲットデータベースサーバー上の場所と共に明示的に名前が付けられているため、サービスの種類ごとに実際のデータベースとログの場所の特定の場所を定義できます。</span><span class="sxs-lookup"><span data-stu-id="55753-170">Because the database and log files are explicitly named with their location on the destination database server, you can define specific locations for each service type’s actual database and log location.</span></span> <span data-ttu-id="55753-171">次の例では、特定のサービスの種類ごとにデータベースを別々のディスクに配置し、関連するログファイルを別のディスクに配置します。</span><span class="sxs-lookup"><span data-stu-id="55753-171">The following example puts databases for each specific service type on separate disks, and associated log files on another.</span></span> <span data-ttu-id="55753-172">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="55753-172">For example:</span></span>
    
      - <span data-ttu-id="55753-173">すべての RTC データベースの "D\\: rtcdatabase"</span><span class="sxs-lookup"><span data-stu-id="55753-173">All RTC databases to “D:\\RTCDatabase”</span></span>
    
      - <span data-ttu-id="55753-174">"E:\\rtclogs" のすべての RTC ログファイル</span><span class="sxs-lookup"><span data-stu-id="55753-174">All RTC log files to “E:\\RTCLogs”</span></span>
    
      - <span data-ttu-id="55753-175">すべてのアプリケーションストアデータベースを "F\\: cpsdatabases" に保存する</span><span class="sxs-lookup"><span data-stu-id="55753-175">All application store databases to “F:\\CPSDatabases”</span></span>
    
      - <span data-ttu-id="55753-176">すべてのアプリケーションストアログを "G\\: cpslogs" に記録する</span><span class="sxs-lookup"><span data-stu-id="55753-176">All application store logs to “G:\\CPSLogs”</span></span>
    
      - <span data-ttu-id="55753-177">すべての応答グループストアデータベースの "H\\: RGSDatabases"</span><span class="sxs-lookup"><span data-stu-id="55753-177">All response group store databases to “H:\\RGSDatabases”</span></span>
    
      - <span data-ttu-id="55753-178">すべての応答グループは、"I:\\RGSLogs" に記録します。</span><span class="sxs-lookup"><span data-stu-id="55753-178">All response group store logs to “I:\\RGSLogs”</span></span>
    
      - <span data-ttu-id="55753-179">すべてのアドレス帳ストアデータベースを "J\\: ABSDatabases" にする</span><span class="sxs-lookup"><span data-stu-id="55753-179">All address book store databases to “J:\\ABSDatabases”</span></span>
    
      - <span data-ttu-id="55753-180">すべてのアドレス帳ストアのログファイルを "\\K: ABSLogs" に保存します。</span><span class="sxs-lookup"><span data-stu-id="55753-180">All address book store log files to “K:\\ABSLogs”</span></span>
    
      - <span data-ttu-id="55753-181">"L:\\ArchivingDatabases" のすべてのアーカイブストアデータベース</span><span class="sxs-lookup"><span data-stu-id="55753-181">All archiving store databases to “L:\\ArchivingDatabases”</span></span>
    
      - <span data-ttu-id="55753-182">すべてのアーカイブストアログは "M\\: ArchivingLogs" になります。</span><span class="sxs-lookup"><span data-stu-id="55753-182">All archiving store logs to “M:\\ArchivingLogs”</span></span>
    
      - <span data-ttu-id="55753-183">すべての監視ストアデータベースを "N\\: monitoringdatabases" に保存する</span><span class="sxs-lookup"><span data-stu-id="55753-183">All monitoring store databases to “N:\\MonitoringDatabases”</span></span>
    
      - <span data-ttu-id="55753-184">すべての監視ストアのログファイルを "\\O: monitoringlogfiles monitoringlogfiles" に保存する</span><span class="sxs-lookup"><span data-stu-id="55753-184">All monitoring store log files to “O:\\MonitoringLogfiles”</span></span>
    
    <!-- end list -->
    
    ```powershell    
    $pathmap = @{
    "BackendStore:BlobStore:DbPath"="D:\RTCDatabase";"BackendStore:BlobStore:LogPath"="E:\RTCLogs"
    "BackendStore:RtcSharedDatabase:DbPath"="D:\RTCDatabase";"BackendStore:RtcSharedDatabase:LogPath"="E:\RTCLogs"
    "ABSStore:AbsDatabase:DbPath"="J:\ABSDatabases";"ABSStore:AbsDatabase:LogPath"="K:\ABSLogs"
    "ApplicationStore:RgsConfigDatabase:DbPath"="H:\RGSDatabases";"ApplicationStore:RgsConfigDatabase:LogPath"="G:\CPSLogs"
    "ApplicationStore:RgsDynDatabase:DbPath"="H:\RGSDatabases";"ApplicationStore:RgsDynDatabase:LogPath"="I:\RGSLogs"
    "ApplicationStore:CpsDynDatabase:DbPath"="F:\CPSDatabases";"ApplicationStore:CpsDynDatabase:LogPath"="G:\CsLogFiles"
    "ArchivingStore:ArchivingDatabase:DbPath"="M:\ArchivingLogs";"ArchivingStore:ArchivingDatabase:LogPath"="N:\MonitoringDatabases"
    "MonitoringStore:MonitoringDatabase:DbPath"="N:\MonitoringDatabases";"MonitoringStore:MonitoringDatabase:LogPath"="O:\MonitoringLogfiles"
    "MonitoringStore:QoEMetricsDatabase:DbPath"="N:\MonitoringDatabases";"MonitoringStore:QoEMetricsDatabase:LogPath"="O:\MonitoringLogfiles"
    }
    
    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathMap $pathmap
    ```
    
    <span data-ttu-id="55753-185">– DatabasePathMap パラメーターを使用すると、SQL Server のパフォーマンスと配置の要件に最適なソリューションを提供する論理ドライブ文字のマッピングの組み合わせを定義できます。</span><span class="sxs-lookup"><span data-stu-id="55753-185">Using the –DatabasePathMap parameter, you can define any logical drive letter mapping combination that provides the best solution for your SQL Server performance and placement requirements.</span></span>

<span data-ttu-id="55753-186">**DatabasePathMap**メソッドを使用してデータベースデータファイルとログファイルを構成する場合は、トポロジビルダーを使用するときに、通常のプロセスに若干の変更を加える必要があります。</span><span class="sxs-lookup"><span data-stu-id="55753-186">If you configure your database data files and log files by using the **DatabasePathMap** method, you will need to make a slight change to your normal process when using Topology Builder.</span></span> <span data-ttu-id="55753-187">通常は、トポロジの選択肢を定義し、トポロジを公開して、選択したデータベースを展開します。</span><span class="sxs-lookup"><span data-stu-id="55753-187">Typically, you would define your topology choices, publish the topology, and choose to deploy the database selections.</span></span>

<span data-ttu-id="55753-188">**DatabasePathMap**を使ったことがある場合は、既にトポロジビルダープロセスの3番目の部分を完了しています。</span><span class="sxs-lookup"><span data-stu-id="55753-188">If you have used **DatabasePathMap** you have already accomplished the third part of the Topology Builder process.</span></span> <span data-ttu-id="55753-189">トポロジビルダーの実行前に完全に構成されたデータベースサーバーがある場合は、すべてのサーバーの役割とオプションを定義したままで、データベースを作成するオプションの選択を解除します。</span><span class="sxs-lookup"><span data-stu-id="55753-189">In the case of having a completely configured database server in advance of running Topology Builder, you would still define all of your server roles and options, but deselect the option to create the databases.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

