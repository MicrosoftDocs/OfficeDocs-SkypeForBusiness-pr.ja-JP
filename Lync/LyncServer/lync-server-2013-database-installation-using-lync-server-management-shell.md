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
ms.openlocfilehash: b602e29e0f90a49a031c25d6bb919337bef87b8d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516544"
---
# <a name="database-installation-using-lync-server-management-shell-in-lync-server-2013"></a><span data-ttu-id="9634d-102">Lync Server 2013 での Lync Server 管理シェルを使用したデータベースインストール</span><span class="sxs-lookup"><span data-stu-id="9634d-102">Database installation using Lync Server Management Shell in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9634d-103">_**トピックの最終更新日:** 2016-06-16_</span><span class="sxs-lookup"><span data-stu-id="9634d-103">_**Topic Last Modified:** 2016-06-16_</span></span>

<span data-ttu-id="9634d-104">サーバーの管理者と SQL Server 管理者の間で役割と責任を分割すると、実装で遅延が生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9634d-104">Separation of roles and responsibilities between server administrators and SQL Server administrators can result in delays in implementation.</span></span> <span data-ttu-id="9634d-105">Lync Server 2013 は、役割ベースのアクセス制御 (RBAC) を使用してこれらの問題を軽減します。</span><span class="sxs-lookup"><span data-stu-id="9634d-105">Lync Server 2013 uses role-based access control (RBAC) to mitigate these difficulties.</span></span> <span data-ttu-id="9634d-106">場合によっては、SQL Server 管理者は、RBAC の外部で SQL Server ベース サーバーでのデータベースのインストールを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9634d-106">In some instances, the SQL Server administrator must manage the installation of databases on the SQL Server-based server outside RBAC.</span></span> <span data-ttu-id="9634d-107">Lync Server 2013 管理シェルは、SQL Server 管理者が、適切なデータおよびログファイルを使用してデータベースを構成するために設計された Windows PowerShell コマンドレットを実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9634d-107">The Lync Server 2013 Management Shell provides a way for the SQL Server administrator to run Windows PowerShell cmdlets designed to configure the databases with the correct data and log files.</span></span> <span data-ttu-id="9634d-108">詳細については、「 [Lync server 2013 の SQL Server の展開権限](lync-server-2013-deployment-permissions-for-sql-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9634d-108">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="9634d-109">次の手順では、少なくとも Lync Server 2013 OCSCore.msi、SQL Server Native Client (sqlncli.msi) Microsoft SQL Server 2012 管理オブジェクト、Microsoft SQL Server 2012 および Microsoft SQL Server 2012 ADOMD.NET の CLR Types がインストールされていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="9634d-109">The following procedure assumes that at a minimum the Lync Server 2013 OCSCore.msi, SQL Server Native Client (sqlncli.msi) Microsoft SQL Server 2012 Management Objects, CLR Types for Microsoft SQL Server 2012 and Microsoft SQL Server 2012 ADOMD.NET are installed.</span></span> <span data-ttu-id="9634d-110">OCSCore.msi は、インストール メディアの \Setup\AMD64\Setup ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="9634d-110">The OCSCore.msi is located on the installation media in the \Setup\AMD64\Setup directory.</span></span> <span data-ttu-id="9634d-111">残りのコンポーネントは、\ が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9634d-111">The remaining components are located in \Setup\amd64.</span></span> <span data-ttu-id="9634d-112">さらに、Lync Server 2013 の Active Directory の準備が正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="9634d-112">Additionally, Active Directory preparation for Lync Server 2013 has been successfully completed.</span></span>



</div>

<span data-ttu-id="9634d-113">**Install-CsDatabase** は、データベースのインストールに使用する Windows PowerShell コマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="9634d-113">**Install-CsDatabase** is the Windows PowerShell cmdlet you use to install the databases.</span></span> <span data-ttu-id="9634d-114">**Install-CsDatabase** コマンドレットには数多くのパラメーターがありますが、ここではその一部についてのみ説明します。</span><span class="sxs-lookup"><span data-stu-id="9634d-114">The **Install-CsDatabase** cmdlet has a large number of parameters, only a few of which are discussed here.</span></span> <span data-ttu-id="9634d-115">使用可能なパラメーターの詳細については、「Lync Server 2013 Management Shell」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9634d-115">For details about the possible parameters, see the Lync Server 2013 Management Shell documentation.</span></span>

<div class=" ">


> [!WARNING]  
> <span data-ttu-id="9634d-116">パフォーマンスの問題と考えられるタイムアウトの問題を防止するため、SQL Server ベースのサーバーを参照するときには、必ず完全修飾ドメイン名 (FQDN) を使用してください。</span><span class="sxs-lookup"><span data-stu-id="9634d-116">To avoid performance and possible time-out issues, always use fully qualified domain names (FQDNs) when referring to SQL Server-based servers.</span></span> <span data-ttu-id="9634d-117">ホスト名のみの参照は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="9634d-117">Avoid using host name-only references.</span></span> <span data-ttu-id="9634d-118">たとえば、sqlbe01.contoso.net を使用しますが、SQLBE01 は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="9634d-118">For example, use sqlbe01.contoso.net, but avoid using SQLBE01.</span></span>



</div>

<span data-ttu-id="9634d-119">データベースをインストールするには、を **インストール** するには、データベースを準備した SQL server ベースのサーバーに配置するための3つの主な方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="9634d-119">For installing databases, **Install-CsDatabase** uses three primary methods for placing the databases onto the prepared SQL Server-based server:</span></span>

  - <span data-ttu-id="9634d-120">DatabasePaths または UseDefaultSqlPath なしで **Install-CsDatabase** を実行します。</span><span class="sxs-lookup"><span data-stu-id="9634d-120">Run **Install-CsDatabase** without DatabasePaths or UseDefaultSqlPath.</span></span> <span data-ttu-id="9634d-121">このコマンドレットは、組み込みアルゴリズムを使用して、ログおよびデータ ファイルの最善の配置方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="9634d-121">The cmdlet uses a built in algorithm to determine the best placement for the log and data files.</span></span> <span data-ttu-id="9634d-122">このアルゴリズムは、スタンドアロンの SQL Server 実装に対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="9634d-122">The algorithm only works for stand-alone SQL Server implementations.</span></span>

  - <span data-ttu-id="9634d-123">DatabasePaths パラメーターを指定して **Install-CsDatabase** を実行します。</span><span class="sxs-lookup"><span data-stu-id="9634d-123">Run **Install-CsDatabase** with the DatabasePaths parameter.</span></span> <span data-ttu-id="9634d-124">DtabasePaths パラメーターが定義されている場合、ログおよびデータ ファイルの場所を最適化する組み込みアルゴリズムは使用されません。</span><span class="sxs-lookup"><span data-stu-id="9634d-124">The built-in algorithm to optimize log and data file locations is not used if the DatabasePaths parameter is defined.</span></span> <span data-ttu-id="9634d-125">このパラメーターを使用すると、ログおよびデータ ファイルを展開する場所を定義できます。</span><span class="sxs-lookup"><span data-stu-id="9634d-125">Using this parameter allows you to define the locations where log and data files will be deployed.</span></span>

  - <span data-ttu-id="9634d-126">UseDefaultSqlPaths を指定して **Install-CsDatabase** を実行します。</span><span class="sxs-lookup"><span data-stu-id="9634d-126">Run **Install-CsDatabase** with UseDefaultSqlPaths.</span></span> <span data-ttu-id="9634d-127">このオプションでは、組み込みアルゴリズムを使用してログおよびデータ ファイルの場所を最適化しません。</span><span class="sxs-lookup"><span data-stu-id="9634d-127">This option does not use the built-in algorithm to optimize the log and data file locations.</span></span> <span data-ttu-id="9634d-128">ログおよびデータ ファイルは、SQL Server 管理者が設定する既定値に従って展開されます。</span><span class="sxs-lookup"><span data-stu-id="9634d-128">Log and data file are deployed according to the defaults set by the SQL Server administrator.</span></span> <span data-ttu-id="9634d-129">これらのパスは、通常、SQL Server 上のログおよびデータファイルを事前に自動管理する目的で設定されており、Lync Server 2013 のセットアップには関連付けられていません。</span><span class="sxs-lookup"><span data-stu-id="9634d-129">These paths are typically set for the purpose of automatic administration of log and data files on the SQL Server in advance, and are not associated with the setup of Lync Server 2013.</span></span>

  - <span data-ttu-id="9634d-130">DatabasePathMap パラメーターを使用して、各データベースおよびそれぞれのログファイルの場所を明示的に指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="9634d-130">The DatabasePathMap parameter can also be used to explicitly specify a location for each database and its respective log file.</span></span>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-central-management-store"></a><span data-ttu-id="9634d-131">Windows PowerShell コマンドレットを使用して SQL Server 中央管理ストアを構成するには</span><span class="sxs-lookup"><span data-stu-id="9634d-131">To use Windows PowerShell cmdlets to configure the SQL Server Central Management store</span></span>

1.  <span data-ttu-id="9634d-132">任意のコンピューターで、SQL Server ベースのサーバーでデータベースを作成するための管理資格情報を使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="9634d-132">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="9634d-133">詳細については、「 [Lync server 2013 の SQL Server の展開権限](lync-server-2013-deployment-permissions-for-sql-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9634d-133">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

2.  <span data-ttu-id="9634d-134">Lync Server 2013 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="9634d-134">Open the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="9634d-135">Windows PowerShell の実行ポリシーを調整していない場合は、Windows PowerShell スクリプトの実行を許可するようにポリシーを調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9634d-135">If you have not adjusted the execution policy for Windows PowerShell, you must adjust the policy to allow Windows PowerShell scripts to run.</span></span> <span data-ttu-id="9634d-136">詳細については、「」の「実行ポリシーを調べる」を参照してください [https://go.microsoft.com/fwlink/p/?linkId=203093](https://go.microsoft.com/fwlink/p/?linkid=203093) 。</span><span class="sxs-lookup"><span data-stu-id="9634d-136">For details, see “Examining the Execution Policy” at [https://go.microsoft.com/fwlink/p/?linkId=203093](https://go.microsoft.com/fwlink/p/?linkid=203093).</span></span>

3.  <span data-ttu-id="9634d-137">中央管理ストアをインストールするには、 **インストール-CsDatabase** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9634d-137">Use the **Install-CsDatabase** cmdlet to install the Central Management store.</span></span>
    
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
    > <span data-ttu-id="9634d-138">Report パラメーターはオプションですが、インストール プロセスを文書化する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9634d-138">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

4.  <span data-ttu-id="9634d-139">**Install-CsDatabase – DatabasePaths** は最大6つのパスパラメーターを使用できます。各パラメーターには、SQL Server データとログファイルの配置で定義されたドライブのパスを定義します。</span><span class="sxs-lookup"><span data-stu-id="9634d-139">**Install-CsDatabase –DatabasePaths** can use up to six path parameters, each defining the paths for the drives as defined in SQL Server Data and Log File Placement.</span></span> <span data-ttu-id="9634d-140">Lync Server 2013 のデータベース構成の論理ルールによって、ドライブは2、4、または6のバケットで解析されます。</span><span class="sxs-lookup"><span data-stu-id="9634d-140">By the logical rules of the database configuration in Lync Server 2013, drives are parsed out into buckets of two, four, or six.</span></span> <span data-ttu-id="9634d-141">SQL Server の構成とバケット数に応じて、2つのパス、4つのパス、または6つのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="9634d-141">Depending on your SQL Server configuration and the number of buckets, you will supply two paths, four paths, or six paths.</span></span>
    
    <span data-ttu-id="9634d-142">ドライブが 3 つの場合は、ログに優先順位が付けられ、データ ファイルはその優先順位に従って配布されます。</span><span class="sxs-lookup"><span data-stu-id="9634d-142">If you have three drives, the log gets priority and the data files are distributed after.</span></span> <span data-ttu-id="9634d-143">6つのドライブを使用して構成された SQL Server ベースのサーバーの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9634d-143">An example for a SQL Server-based server configured with six drives:</span></span>
    ```powershell
    Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"
    ```
5.  <span data-ttu-id="9634d-144">データベースのインストールが完了したら、Lync Server 2013 管理シェルを閉じるか、またはトポロジビルダーで定義された Lync Server 2013 構成済みデータベースのインストールに進むことができます。</span><span class="sxs-lookup"><span data-stu-id="9634d-144">When the database installation completes, you can close Lync Server 2013 Management Shell or proceed to the installation of the Lync Server 2013 configured databases defined in Topology Builder.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-configured-databases"></a><span data-ttu-id="9634d-145">Windows PowerShell コマンドレットを使用して SQL Server トポロジ構成のデータベースを構成するには</span><span class="sxs-lookup"><span data-stu-id="9634d-145">To use Windows PowerShell cmdlets to configure the SQL Server topology configured databases</span></span>

1.  <span data-ttu-id="9634d-146">Lync server 2013 のトポロジビルダー構成データベースをインストールするには、Lync Server 2013 管理者がトポロジを公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9634d-146">To install the Topology Builder configured databases for Lync Server 2013, the Lync Server 2013 administrator must publish the topology.</span></span> <span data-ttu-id="9634d-147">詳細については、「展開」のドキュメントの「 [Publish the topology In Lync Server 2013](lync-server-2013-publish-the-topology.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9634d-147">For details, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="9634d-148">任意のコンピューターで、SQL Server ベースのサーバーでデータベースを作成するための管理資格情報を使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="9634d-148">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="9634d-149">「 [Lync server 2013 の SQL Server の展開権限](lync-server-2013-deployment-permissions-for-sql-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9634d-149">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9634d-150">SQL Server ベースのデータベースを構成できるようにするには、ここで説明する手順の実行に使用する SQL Server 管理者アカウントが、SQL Server を実行しているサーバー上のシステム管理者グループ (または同等のもの) のメンバーであることを確認し、中央管理サーバーの役割を保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9634d-150">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="9634d-151">これは、SQL Server データベースのインストールまたは構成を必要とする追加の Lync Server 2013 プールがあるかどうかを確認する場合に特に重要です。</span><span class="sxs-lookup"><span data-stu-id="9634d-151">This is especially important to check for any additional Lync Server 2013 pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="9634d-152">たとえば、2番目のプール (pool02) を展開している場合に、中央管理サーバーの役割が pool01 によって保持されているとします。</span><span class="sxs-lookup"><span data-stu-id="9634d-152">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="9634d-153">SQL server の sysadmin グループ (または同等のもの) は、両方の SQL Server ベースのデータベースに対する権限を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9634d-153">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="9634d-154">まだ開いていない場合は、Lync Server 2013 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="9634d-154">Open Lync Server 2013 Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="9634d-155">トポロジビルダーによって構成されたデータベースをインストールするには、コマンドレットの **インストール** を使用します。</span><span class="sxs-lookup"><span data-stu-id="9634d-155">Use the **Install-CsDatabase** cmdlet to install the Topology Builder configured databases.</span></span>
    
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
    > <span data-ttu-id="9634d-156">Report パラメーターはオプションですが、インストール プロセスを文書化する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9634d-156">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

5.  <span data-ttu-id="9634d-157">データベースのインストールが完了したら、Lync Server 2013 管理シェルを閉じます。</span><span class="sxs-lookup"><span data-stu-id="9634d-157">When the database installation completes, close Lync Server 2013 Management Shell.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-using-the-databasepathmap-parameter"></a><span data-ttu-id="9634d-158">Windows PowerShell コマンドレットを使用して SQL Server トポロジを構成するには、DatabasePathMap パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="9634d-158">To use Windows PowerShell cmdlets to configure the SQL Server topology using the DatabasePathMap parameter</span></span>

1.  <span data-ttu-id="9634d-159">Lync server 2013 のデータベースをインストールするには、Lync Server 管理者がパスを作成し、定義済みのルールセットに従ってデータベースファイルとログファイルを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9634d-159">To install databases for Lync Server 2013, the Lync Server administrator must create the paths and deploy the databases files and log files according to a predefined set of rules.</span></span>

2.  <span data-ttu-id="9634d-160">任意のコンピューターで、SQL Server ベースのサーバーでデータベースを作成するための管理資格情報を使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="9634d-160">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="9634d-161">「 [Lync server 2013 の SQL Server の展開権限](lync-server-2013-deployment-permissions-for-sql-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9634d-161">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9634d-162">SQL Server ベースのデータベースを構成できるようにするには、ここで説明する手順の実行に使用する SQL Server 管理者アカウントが、SQL Server を実行しているサーバー上のシステム管理者グループ (または同等のもの) のメンバーであることを確認し、中央管理サーバーの役割を保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9634d-162">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="9634d-163">これは、SQL Server データベースのインストールまたは構成を必要とする追加の Lync Server プールがあるかどうかを確認する場合に特に重要です。</span><span class="sxs-lookup"><span data-stu-id="9634d-163">This is especially important to check for any additional Lync Server pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="9634d-164">たとえば、2番目のプール (pool02) を展開している場合に、中央管理サーバーの役割が pool01 によって保持されているとします。</span><span class="sxs-lookup"><span data-stu-id="9634d-164">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="9634d-165">SQL server の sysadmin グループ (または同等のもの) は、両方の SQL Server ベースのデータベースに対する権限を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9634d-165">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="9634d-166">まだ開いていない場合は、Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="9634d-166">Open Lync Server Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="9634d-167">トポロジビルダーで構成されたデータベースをインストールするには、DatabasePathMap パラメーターと PowerShell ハッシュテーブルを使用して、 **インストール-CsDatabase** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9634d-167">Use the **Install-CsDatabase** cmdlet with the DatabasePathMap parameter and a PowerShell hash table to install the Topology Builder configured databases.</span></span>

5.  <span data-ttu-id="9634d-168">このコード例では、-DatabasePathMap パラメーターと定義済みのハッシュテーブルを次のように使用して、データベースに対して定義されているパスを詳細に判断できます (例では、 \\ すべてのデータベース (.mdf) ファイルに "c: csdata"、 \\ すべてのログ (.ldf) ファイルの "c: csdata" を使用します)</span><span class="sxs-lookup"><span data-stu-id="9634d-168">In the example code, the paths defined for the databases can be determined in a granular manner by using the –DatabasePathMap parameter and a defined hash table as follows (the example uses “C:\\CSData” for all database (.mdf) files, and “C:\\CSLogFiles” for all log (.ldf) files.</span></span> <span data-ttu-id="9634d-169">フォルダーは、必要に応じて、-CsDatabase をインストールすることによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="9634d-169">Folder will be created as needed by Install-CsDatabase):</span></span>
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
6.  <span data-ttu-id="9634d-170">データベースとログファイルには、移動先のデータベースサーバー上の場所が明示的に指定されているため、サービスの種類ごとに固有のデータベースとログの場所を定義できます。</span><span class="sxs-lookup"><span data-stu-id="9634d-170">Because the database and log files are explicitly named with their location on the destination database server, you can define specific locations for each service type’s actual database and log location.</span></span> <span data-ttu-id="9634d-171">次の例では、個別のディスク上の特定のサービスタイプごとにデータベースを配置し、関連するログファイルを別のディスクに格納します。</span><span class="sxs-lookup"><span data-stu-id="9634d-171">The following example puts databases for each specific service type on separate disks, and associated log files on another.</span></span> <span data-ttu-id="9634d-172">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9634d-172">For example:</span></span>
    
      - <span data-ttu-id="9634d-173">"D: rtcdatabase" のすべての RTC データベース \\</span><span class="sxs-lookup"><span data-stu-id="9634d-173">All RTC databases to “D:\\RTCDatabase”</span></span>
    
      - <span data-ttu-id="9634d-174">すべての RTC ログファイルから "E: \\ rtclogs" へ</span><span class="sxs-lookup"><span data-stu-id="9634d-174">All RTC log files to “E:\\RTCLogs”</span></span>
    
      - <span data-ttu-id="9634d-175">すべてのアプリケーションストアデータベースを "F: \\ cpsdatabases" にする</span><span class="sxs-lookup"><span data-stu-id="9634d-175">All application store databases to “F:\\CPSDatabases”</span></span>
    
      - <span data-ttu-id="9634d-176">すべてのアプリケーションストアのログを "G: \\ cpslogs" にする</span><span class="sxs-lookup"><span data-stu-id="9634d-176">All application store logs to “G:\\CPSLogs”</span></span>
    
      - <span data-ttu-id="9634d-177">すべての応答グループストアデータベースを "H: RGSDatabases" にします。 \\</span><span class="sxs-lookup"><span data-stu-id="9634d-177">All response group store databases to “H:\\RGSDatabases”</span></span>
    
      - <span data-ttu-id="9634d-178">"I: RGSLogs" へのすべての応答グループストアログ \\</span><span class="sxs-lookup"><span data-stu-id="9634d-178">All response group store logs to “I:\\RGSLogs”</span></span>
    
      - <span data-ttu-id="9634d-179">すべてのアドレス帳ストアデータベースを "J: \\ ABSDatabases" にする</span><span class="sxs-lookup"><span data-stu-id="9634d-179">All address book store databases to “J:\\ABSDatabases”</span></span>
    
      - <span data-ttu-id="9634d-180">すべてのアドレス帳ストアのログファイルを "K: \\ ABSLogs" に</span><span class="sxs-lookup"><span data-stu-id="9634d-180">All address book store log files to “K:\\ABSLogs”</span></span>
    
      - <span data-ttu-id="9634d-181">すべてのアーカイブストアデータベースを "L: \\ ArchivingDatabases" にする</span><span class="sxs-lookup"><span data-stu-id="9634d-181">All archiving store databases to “L:\\ArchivingDatabases”</span></span>
    
      - <span data-ttu-id="9634d-182">すべてのアーカイブストアログを "M: ArchivingLogs" にします。 \\</span><span class="sxs-lookup"><span data-stu-id="9634d-182">All archiving store logs to “M:\\ArchivingLogs”</span></span>
    
      - <span data-ttu-id="9634d-183">すべての監視ストアデータベースを "N: \\ monitoringdatabases" にする</span><span class="sxs-lookup"><span data-stu-id="9634d-183">All monitoring store databases to “N:\\MonitoringDatabases”</span></span>
    
      - <span data-ttu-id="9634d-184">すべての監視ストアのログファイルを "O: monitoringlogfiles" にします。 \\</span><span class="sxs-lookup"><span data-stu-id="9634d-184">All monitoring store log files to “O:\\MonitoringLogfiles”</span></span>
    
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
    
    <span data-ttu-id="9634d-185">– DatabasePathMap パラメーターを使用すると、SQL Server のパフォーマンスと配置の要件に最適なソリューションを提供する任意の論理ドライブ文字マッピングの組み合わせを定義できます。</span><span class="sxs-lookup"><span data-stu-id="9634d-185">Using the –DatabasePathMap parameter, you can define any logical drive letter mapping combination that provides the best solution for your SQL Server performance and placement requirements.</span></span>

<span data-ttu-id="9634d-186">**DatabasePathMap**メソッドを使用してデータベースデータファイルとログファイルを構成する場合は、トポロジビルダーを使用しているときに通常のプロセスに少し変更を加える必要があります。</span><span class="sxs-lookup"><span data-stu-id="9634d-186">If you configure your database data files and log files by using the **DatabasePathMap** method, you will need to make a slight change to your normal process when using Topology Builder.</span></span> <span data-ttu-id="9634d-187">通常は、トポロジの選択を定義し、トポロジを公開して、データベースの選択を展開します。</span><span class="sxs-lookup"><span data-stu-id="9634d-187">Typically, you would define your topology choices, publish the topology, and choose to deploy the database selections.</span></span>

<span data-ttu-id="9634d-188">**DatabasePathMap**を使用した場合は、トポロジビルダープロセスの3番目の部分が既に完了しています。</span><span class="sxs-lookup"><span data-stu-id="9634d-188">If you have used **DatabasePathMap** you have already accomplished the third part of the Topology Builder process.</span></span> <span data-ttu-id="9634d-189">トポロジビルダーを実行する前に、完全に構成されたデータベースサーバーがある場合は、すべてのサーバーの役割とオプションを定義しますが、データベースを作成するためのオプションの選択を解除します。</span><span class="sxs-lookup"><span data-stu-id="9634d-189">In the case of having a completely configured database server in advance of running Topology Builder, you would still define all of your server roles and options, but deselect the option to create the databases.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

