---
title: 'Lync Server 2013: ウイルス対策スキャンの除外'
description: 'Lync Server 2013: ウイルス対策スキャンの除外。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Antivirus scanning exclusions for Lync Server 2013
ms:assetid: 71e1f1cc-2d16-4111-9864-9276bf24dfe0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440138(v=OCS.15)
ms:contentKeyID: 57793042
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20c395f529cad91993d003efdeb231bd66f4b9bc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561913"
---
# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a><span data-ttu-id="f73ed-103">Lync Server 2013 のウイルススキャン除外</span><span class="sxs-lookup"><span data-stu-id="f73ed-103">Antivirus scanning exclusions for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f73ed-104">_**トピックの最終更新日:** 2015-11-02_</span><span class="sxs-lookup"><span data-stu-id="f73ed-104">_**Topic Last Modified:** 2015-11-02_</span></span>

<span data-ttu-id="f73ed-105">ウイルス検出プログラムが Lync Server 2013 の動作に干渉しないようにするには、ウイルス対策スキャナーを実行する Lync Server 2013 サーバーまたはサーバーの役割ごとに特定のプロセスとディレクトリを除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f73ed-105">To ensure that the antivirus scanner does not interfere with the operation of Lync Server 2013, you must exclude specific processes and directories for each Lync Server 2013 server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="f73ed-106">除外が必要なプロセスとディレクトリを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="f73ed-106">The following processes and directories should be excluded:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f73ed-107">下にリストされているフォルダーとファイルの場所は、Lync Server 2013 の既定の場所です。</span><span class="sxs-lookup"><span data-stu-id="f73ed-107">Folder and file locations listed below are the default locations for Lync Server 2013.</span></span> <span data-ttu-id="f73ed-108">既定の設定を使用しなかったすべての場所については、ここに示す既定の場所の代わりに、組織で指定した場所を除外してください。</span><span class="sxs-lookup"><span data-stu-id="f73ed-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f73ed-109">一部のウイルス対策プログラムでは、除外リストに相対パスではなく、絶対的なパスが必要になることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f73ed-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>



</div>

  - <span data-ttu-id="f73ed-110">Lync Server 2013 プロセス:</span><span class="sxs-lookup"><span data-stu-id="f73ed-110">Lync Server 2013 processes:</span></span>
    
      - <span data-ttu-id="f73ed-111">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="f73ed-111">ABServer.exe</span></span>
    
      - <span data-ttu-id="f73ed-112">AcpMcuSvc.exe</span><span class="sxs-lookup"><span data-stu-id="f73ed-112">AcpMcuSvc.exe</span></span>
    
      - <span data-ttu-id="f73ed-113">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="f73ed-113">ASMCUSvc.exe</span></span>
    
      - <span data-ttu-id="f73ed-114">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="f73ed-114">AVMCUSvc.exe</span></span>
    
      - <span data-ttu-id="f73ed-115">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="f73ed-115">ChannelService.exe</span></span>
    
      - <span data-ttu-id="f73ed-116">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="f73ed-116">ClsAgent.exe</span></span>
    
      - <span data-ttu-id="f73ed-117">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="f73ed-117">ComplianceService.exe</span></span>
    
      - <span data-ttu-id="f73ed-118">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="f73ed-118">DataMCUSvc.exe</span></span>
    
      - <span data-ttu-id="f73ed-119">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="f73ed-119">DataProxy.exe</span></span>
    
      - <span data-ttu-id="f73ed-120">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="f73ed-120">FileTransferAgent.exe</span></span>
    
      - <span data-ttu-id="f73ed-121">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="f73ed-121">IMMCUSvc.exe</span></span>
    
      - <span data-ttu-id="f73ed-122">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="f73ed-122">LysSvc.exe</span></span>
    
      - <span data-ttu-id="f73ed-123">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="f73ed-123">MasterReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="f73ed-124">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="f73ed-124">MediaRelaySvc.exe</span></span>
    
      - <span data-ttu-id="f73ed-125">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="f73ed-125">MediationServerSvc.exe</span></span>
    
      - <span data-ttu-id="f73ed-126">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="f73ed-126">MRASSvc.exe</span></span>
    
      - <span data-ttu-id="f73ed-127">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="f73ed-127">OcsAppServerHost.exe</span></span>
    
      - <span data-ttu-id="f73ed-128">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="f73ed-128">ReplicaReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="f73ed-129">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="f73ed-129">ReplicationApp.exe</span></span>
    
      - <span data-ttu-id="f73ed-130">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="f73ed-130">RtcHost.exe</span></span>
    
      - <span data-ttu-id="f73ed-131">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="f73ed-131">RTCSrv.exe</span></span>
    
      - <span data-ttu-id="f73ed-132">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="f73ed-132">XmppProxy.exe</span></span>
    
      - <span data-ttu-id="f73ed-133">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="f73ed-133">XmppTGW.exe</span></span>

  - <span data-ttu-id="f73ed-134">Windows Fabric ホストサービスプロセス:</span><span class="sxs-lookup"><span data-stu-id="f73ed-134">Windows Fabric Host Service processes:</span></span>
    
      - <span data-ttu-id="f73ed-135">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="f73ed-135">Fabric.exe</span></span>
    
      - <span data-ttu-id="f73ed-136">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="f73ed-136">FabricDCA.exe</span></span>
    
      - <span data-ttu-id="f73ed-137">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="f73ed-137">FabricHost.exe</span></span>

  - <span data-ttu-id="f73ed-138">IIS のプロセス:</span><span class="sxs-lookup"><span data-stu-id="f73ed-138">IIS processes:</span></span>
    
      - <span data-ttu-id="f73ed-139">% systemroot% \\ system32 \\ inetsrv \\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="f73ed-139">%systemroot%\\system32\\inetsrv\\w3wp.exe</span></span>
    
      - <span data-ttu-id="f73ed-140">% systemroot% \\ SysWOW64 \\ inetsrv \\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="f73ed-140">%systemroot%\\SysWOW64\\inetsrv\\w3wp.exe</span></span>

  - <span data-ttu-id="f73ed-141">SQL Server Back-End プロセス:</span><span class="sxs-lookup"><span data-stu-id="f73ed-141">SQL Server Back-End processes:</span></span>
    
      - <span data-ttu-id="f73ed-142">% ProgramFiles% \\ MICROSOFT SQL Server \\ MSSQL11。MSSQLSERVER \\ MSSQL \\ Binn \\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="f73ed-142">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.MSSQLSERVER\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="f73ed-143">% ProgramFiles% \\ MICROSOFT SQL Server \\ MSRS11。MSSQLSERVER \\ Reporting Services \\ ReportServer \\ Bin \\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="f73ed-143">%ProgramFiles%\\Microsoft SQL Server\\MSRS11.MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService.exe</span></span>
    
      - <span data-ttu-id="f73ed-144">% ProgramFiles% \\ MICROSOFT SQL Server \\ MSAS11。MSSQLSERVER \\ OLAP \\ Bin \\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="f73ed-144">%ProgramFiles%\\Microsoft SQL Server\\MSAS11.MSSQLSERVER\\OLAP\\Bin\\MSMDSrv.exe</span></span>

  - <span data-ttu-id="f73ed-145">SQL Server Front-End プロセス:</span><span class="sxs-lookup"><span data-stu-id="f73ed-145">SQL Server Front-End processes:</span></span>
    
      - <span data-ttu-id="f73ed-146">% ProgramFiles% \\ MICROSOFT SQL Server \\ MSSQL11。LYNCLOCAL \\ MSSQL \\ Binn \\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="f73ed-146">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.LYNCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="f73ed-147">% ProgramFiles% \\ MICROSOFT SQL Server \\ MSSQL11。RTCLOCAL \\ MSSQL \\ Binn \\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="f73ed-147">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.RTCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>

  - <span data-ttu-id="f73ed-148">ディレクトリとファイル:</span><span class="sxs-lookup"><span data-stu-id="f73ed-148">Directories and files:</span></span>
    
      - <span data-ttu-id="f73ed-149">% systemroot% \\ System32 の \\ ログログ</span><span class="sxs-lookup"><span data-stu-id="f73ed-149">%systemroot%\\System32\\LogFiles</span></span>
    
      - <span data-ttu-id="f73ed-150">% systemroot% \\ SysWow64 \\ ログログ</span><span class="sxs-lookup"><span data-stu-id="f73ed-150">%systemroot%\\SysWow64\\LogFiles</span></span>
    
      - <span data-ttu-id="f73ed-151">% systemroot% \\ Microsoft.NET \\ assembly \\ GAC \_ MSIL</span><span class="sxs-lookup"><span data-stu-id="f73ed-151">%systemroot%\\Microsoft.NET\\assembly\\GAC\_MSIL</span></span>
    
      - <span data-ttu-id="f73ed-152">% programfiles% \\ Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f73ed-152">%programfiles%\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="f73ed-153">% programfiles% \\ Common Files \\ Microsoft Lync Server 2013 \\ 監視ノード</span><span class="sxs-lookup"><span data-stu-id="f73ed-153">%programfiles%\\Common Files\\Microsoft Lync Server 2013\\Watcher Node</span></span>
    
      - <span data-ttu-id="f73ed-154">% programfiles% \\ Common Files \\ Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f73ed-154">%programfiles%\\Common Files\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="f73ed-155">% SystemDrive% \\ RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="f73ed-155">%SystemDrive%\\RtcReplicaRoot</span></span>
    
      - <span data-ttu-id="f73ed-156">ファイル共有ストア (トポロジ ビルダーで指定)。</span><span class="sxs-lookup"><span data-stu-id="f73ed-156">File share store (specified in Topology Builder).</span></span> <span data-ttu-id="f73ed-157">ファイル ストアはトポロジ ビルダーで指定されています。</span><span class="sxs-lookup"><span data-stu-id="f73ed-157">File stores are specified in Topology Builder.</span></span>
    
      - <span data-ttu-id="f73ed-158">SQL Server のデータおよびログ ファイル (バックエンド データベース、ユーザー ストア、アーカイブ ストア、監視ストア、およびアプリケーション ストア用のものを含みます)。</span><span class="sxs-lookup"><span data-stu-id="f73ed-158">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="f73ed-159">データベースとログ ファイルは、トポロジ ビルダーで指定できます。</span><span class="sxs-lookup"><span data-stu-id="f73ed-159">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="f73ed-160">既定の名前など、各データベースのデータおよびログファイルの詳細については、「展開」のドキュメントの「 [SQL server data and log file placement For Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f73ed-160">For details about the data and log files for each database, including default names, see [SQL Server data and log file placement for Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="f73ed-161">SQL Server のデータおよびログファイル (フロントエンドデータベース、Lync ストア、および RtcDatabase store のものを含む)。</span><span class="sxs-lookup"><span data-stu-id="f73ed-161">SQL Server data and log files, including those for the Front-end database, Lync store, and RtcDatabase store.</span></span> <span data-ttu-id="f73ed-162">通常、% localdrive% csdata の下にあり \\ ます。</span><span class="sxs-lookup"><span data-stu-id="f73ed-162">They are normally under %localdrive%\\CSData.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

