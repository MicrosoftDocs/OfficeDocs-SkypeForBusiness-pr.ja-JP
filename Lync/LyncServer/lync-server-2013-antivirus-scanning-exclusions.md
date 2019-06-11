---
title: 'Lync Server 2013: ウイルス スキャン除外範囲'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Antivirus scanning exclusions for Lync Server 2013
ms:assetid: 71e1f1cc-2d16-4111-9864-9276bf24dfe0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440138(v=OCS.15)
ms:contentKeyID: 57793042
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6f354b93bf21f054e9b5b24e3befd1787279bbe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841038"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a><span data-ttu-id="7d534-102">Lync Server 2013 用のウイルス スキャン除外範囲</span><span class="sxs-lookup"><span data-stu-id="7d534-102">Antivirus scanning exclusions for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d534-103">_**最終更新日:** 2015-11-02_</span><span class="sxs-lookup"><span data-stu-id="7d534-103">_**Topic Last Modified:** 2015-11-02_</span></span>

<span data-ttu-id="7d534-104">ウイルス対策スキャナーが Lync Server 2013 の動作を妨害しないようにするには、ウイルススキャンを実行している Lync Server 2013 サーバーまたはサーバーの役割ごとに、特定のプロセスとディレクトリを除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d534-104">To ensure that the antivirus scanner does not interfere with the operation of Lync Server 2013, you must exclude specific processes and directories for each Lync Server 2013 server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="7d534-105">除外が必要なプロセスとディレクトリを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="7d534-105">The following processes and directories should be excluded:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7d534-106">次に示すフォルダーとファイルの場所は、Lync Server 2013 の既定の場所です。</span><span class="sxs-lookup"><span data-stu-id="7d534-106">Folder and file locations listed below are the default locations for Lync Server 2013.</span></span> <span data-ttu-id="7d534-107">既定の設定を使用しなかったすべての場所については、ここに示す既定の場所の代わりに、組織で指定した場所を除外してください。</span><span class="sxs-lookup"><span data-stu-id="7d534-107">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7d534-108">一部のウイルス対策プログラムでは、除外リストに相対パスでなく絶対パスが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="7d534-108">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>



</div>

  - <span data-ttu-id="7d534-109">Lync Server 2013 のプロセス:</span><span class="sxs-lookup"><span data-stu-id="7d534-109">Lync Server 2013 processes:</span></span>
    
      - <span data-ttu-id="7d534-110">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="7d534-110">ABServer.exe</span></span>
    
      - <span data-ttu-id="7d534-111">AcpMcuSvc</span><span class="sxs-lookup"><span data-stu-id="7d534-111">AcpMcuSvc.exe</span></span>
    
      - <span data-ttu-id="7d534-112">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="7d534-112">ASMCUSvc.exe</span></span>
    
      - <span data-ttu-id="7d534-113">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="7d534-113">AVMCUSvc.exe</span></span>
    
      - <span data-ttu-id="7d534-114">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="7d534-114">ChannelService.exe</span></span>
    
      - <span data-ttu-id="7d534-115">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="7d534-115">ClsAgent.exe</span></span>
    
      - <span data-ttu-id="7d534-116">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="7d534-116">ComplianceService.exe</span></span>
    
      - <span data-ttu-id="7d534-117">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="7d534-117">DataMCUSvc.exe</span></span>
    
      - <span data-ttu-id="7d534-118">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="7d534-118">DataProxy.exe</span></span>
    
      - <span data-ttu-id="7d534-119">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="7d534-119">FileTransferAgent.exe</span></span>
    
      - <span data-ttu-id="7d534-120">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="7d534-120">IMMCUSvc.exe</span></span>
    
      - <span data-ttu-id="7d534-121">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="7d534-121">LysSvc.exe</span></span>
    
      - <span data-ttu-id="7d534-122">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="7d534-122">MasterReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="7d534-123">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="7d534-123">MediaRelaySvc.exe</span></span>
    
      - <span data-ttu-id="7d534-124">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="7d534-124">MediationServerSvc.exe</span></span>
    
      - <span data-ttu-id="7d534-125">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="7d534-125">MRASSvc.exe</span></span>
    
      - <span data-ttu-id="7d534-126">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="7d534-126">OcsAppServerHost.exe</span></span>
    
      - <span data-ttu-id="7d534-127">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="7d534-127">ReplicaReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="7d534-128">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="7d534-128">ReplicationApp.exe</span></span>
    
      - <span data-ttu-id="7d534-129">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="7d534-129">RtcHost.exe</span></span>
    
      - <span data-ttu-id="7d534-130">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="7d534-130">RTCSrv.exe</span></span>
    
      - <span data-ttu-id="7d534-131">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="7d534-131">XmppProxy.exe</span></span>
    
      - <span data-ttu-id="7d534-132">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="7d534-132">XmppTGW.exe</span></span>

  - <span data-ttu-id="7d534-133">Windows Fabric Host Service のプロセス:</span><span class="sxs-lookup"><span data-stu-id="7d534-133">Windows Fabric Host Service processes:</span></span>
    
      - <span data-ttu-id="7d534-134">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="7d534-134">Fabric.exe</span></span>
    
      - <span data-ttu-id="7d534-135">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="7d534-135">FabricDCA.exe</span></span>
    
      - <span data-ttu-id="7d534-136">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="7d534-136">FabricHost.exe</span></span>

  - <span data-ttu-id="7d534-137">IIS のプロセス:</span><span class="sxs-lookup"><span data-stu-id="7d534-137">IIS processes:</span></span>
    
      - <span data-ttu-id="7d534-138">% systemroot%\\system32\\inetsrv\\w3wp</span><span class="sxs-lookup"><span data-stu-id="7d534-138">%systemroot%\\system32\\inetsrv\\w3wp.exe</span></span>
    
      - <span data-ttu-id="7d534-139">% systemroot%\\SysWOW64\\inetsrv\\は、w3wp</span><span class="sxs-lookup"><span data-stu-id="7d534-139">%systemroot%\\SysWOW64\\inetsrv\\w3wp.exe</span></span>

  - <span data-ttu-id="7d534-140">SQL Server バックエンドのプロセス:</span><span class="sxs-lookup"><span data-stu-id="7d534-140">SQL Server Back-End processes:</span></span>
    
      - <span data-ttu-id="7d534-141">% ProgramFiles%\\Microsoft SQL Server\\MSSQL11。MSSQLSERVER\\MSSQL\\Binn\\sqlservr.exe</span><span class="sxs-lookup"><span data-stu-id="7d534-141">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.MSSQLSERVER\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="7d534-142">% ProgramFiles%\\Microsoft SQL Server\\MSRS11。MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\reportingサービスの service .exe</span><span class="sxs-lookup"><span data-stu-id="7d534-142">%ProgramFiles%\\Microsoft SQL Server\\MSRS11.MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService.exe</span></span>
    
      - <span data-ttu-id="7d534-143">% ProgramFiles%\\Microsoft SQL Server\\MSAS11。MSSQLSERVER\\OLAP\\Bin\\MSMDSrv</span><span class="sxs-lookup"><span data-stu-id="7d534-143">%ProgramFiles%\\Microsoft SQL Server\\MSAS11.MSSQLSERVER\\OLAP\\Bin\\MSMDSrv.exe</span></span>

  - <span data-ttu-id="7d534-144">SQL Server フロントエンドのプロセス:</span><span class="sxs-lookup"><span data-stu-id="7d534-144">SQL Server Front-End processes:</span></span>
    
      - <span data-ttu-id="7d534-145">% ProgramFiles%\\Microsoft SQL Server\\MSSQL11。LYNCLOCAL\\MSSQL\\Binn\\sqlservr.exe</span><span class="sxs-lookup"><span data-stu-id="7d534-145">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.LYNCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="7d534-146">% ProgramFiles%\\Microsoft SQL Server\\MSSQL11。RTCLOCAL\\MSSQL\\Binn\\sqlservr.exe</span><span class="sxs-lookup"><span data-stu-id="7d534-146">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.RTCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>

  - <span data-ttu-id="7d534-147">ディレクトリとファイル:</span><span class="sxs-lookup"><span data-stu-id="7d534-147">Directories and files:</span></span>
    
      - <span data-ttu-id="7d534-148">% systemroot%\\System32\\ログのログ</span><span class="sxs-lookup"><span data-stu-id="7d534-148">%systemroot%\\System32\\LogFiles</span></span>
    
      - <span data-ttu-id="7d534-149">% systemroot%\\SysWow64\\ログ</span><span class="sxs-lookup"><span data-stu-id="7d534-149">%systemroot%\\SysWow64\\LogFiles</span></span>
    
      - <span data-ttu-id="7d534-150">% systemroot%\\Microsoft.NET\\assembly\\GAC\_MSIL</span><span class="sxs-lookup"><span data-stu-id="7d534-150">%systemroot%\\Microsoft.NET\\assembly\\GAC\_MSIL</span></span>
    
      - <span data-ttu-id="7d534-151">% programfiles%\\Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d534-151">%programfiles%\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="7d534-152">% programfiles%\\共通ファイル\\Microsoft Lync Server 2013\\ウォッチャーノード</span><span class="sxs-lookup"><span data-stu-id="7d534-152">%programfiles%\\Common Files\\Microsoft Lync Server 2013\\Watcher Node</span></span>
    
      - <span data-ttu-id="7d534-153">% programfiles%\\(共通\\ファイル Microsoft Lync Server 2013)</span><span class="sxs-lookup"><span data-stu-id="7d534-153">%programfiles%\\Common Files\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="7d534-154">% SystemDrive%\\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="7d534-154">%SystemDrive%\\RtcReplicaRoot</span></span>
    
      - <span data-ttu-id="7d534-155">ファイル共有ストア (トポロジ ビルダーで指定)。</span><span class="sxs-lookup"><span data-stu-id="7d534-155">File share store (specified in Topology Builder).</span></span> <span data-ttu-id="7d534-156">ファイル ストアはトポロジ ビルダーで指定されています。</span><span class="sxs-lookup"><span data-stu-id="7d534-156">File stores are specified in Topology Builder.</span></span>
    
      - <span data-ttu-id="7d534-157">SQL Server のデータおよびログ ファイル (バックエンド データベース、ユーザー ストア、アーカイブ ストア、監視ストア、およびアプリケーション ストア用のものを含みます)。</span><span class="sxs-lookup"><span data-stu-id="7d534-157">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="7d534-158">データベースとログ ファイルは、トポロジ ビルダーで指定できます。</span><span class="sxs-lookup"><span data-stu-id="7d534-158">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="7d534-159">既定の名前など、各データベースのデータファイルとログファイルの詳細については、「 [SQL server のデータと、Lync Server 2013 用のログファイルの配置](lync-server-2013-sql-server-data-and-log-file-placement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d534-159">For details about the data and log files for each database, including default names, see [SQL Server data and log file placement for Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="7d534-160">SQL Server のデータファイルとログファイル (フロントエンドデータベース、Lync ストア、および RtcDatabase store のものを含む)。</span><span class="sxs-lookup"><span data-stu-id="7d534-160">SQL Server data and log files, including those for the Front-end database, Lync store, and RtcDatabase store.</span></span> <span data-ttu-id="7d534-161">通常、% localdrive%\\csdata の下にあります。</span><span class="sxs-lookup"><span data-stu-id="7d534-161">They are normally under %localdrive%\\CSData.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

