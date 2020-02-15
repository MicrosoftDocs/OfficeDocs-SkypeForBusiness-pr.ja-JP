---
title: 'Lync Server 2013: ウイルス対策スキャンの除外'
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
ms.openlocfilehash: f8faeba1d3b661110bcaf633d3c780dc2c2ad2b1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029038"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a><span data-ttu-id="68b06-102">Lync Server 2013 のウイルススキャン除外</span><span class="sxs-lookup"><span data-stu-id="68b06-102">Antivirus scanning exclusions for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68b06-103">_**トピックの最終更新日:** 2015-11-02_</span><span class="sxs-lookup"><span data-stu-id="68b06-103">_**Topic Last Modified:** 2015-11-02_</span></span>

<span data-ttu-id="68b06-104">ウイルス検出プログラムが Lync Server 2013 の動作に干渉しないようにするには、ウイルス対策スキャナーを実行する Lync Server 2013 サーバーまたはサーバーの役割ごとに特定のプロセスとディレクトリを除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68b06-104">To ensure that the antivirus scanner does not interfere with the operation of Lync Server 2013, you must exclude specific processes and directories for each Lync Server 2013 server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="68b06-105">除外が必要なプロセスとディレクトリを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="68b06-105">The following processes and directories should be excluded:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="68b06-106">下にリストされているフォルダーとファイルの場所は、Lync Server 2013 の既定の場所です。</span><span class="sxs-lookup"><span data-stu-id="68b06-106">Folder and file locations listed below are the default locations for Lync Server 2013.</span></span> <span data-ttu-id="68b06-107">既定の設定を使用しなかったすべての場所については、ここに示す既定の場所の代わりに、組織で指定した場所を除外してください。</span><span class="sxs-lookup"><span data-stu-id="68b06-107">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="68b06-108">一部のウイルス対策プログラムでは、除外リストに相対パスではなく、絶対的なパスが必要になることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="68b06-108">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>



</div>

  - <span data-ttu-id="68b06-109">Lync Server 2013 プロセス:</span><span class="sxs-lookup"><span data-stu-id="68b06-109">Lync Server 2013 processes:</span></span>
    
      - <span data-ttu-id="68b06-110">ABServer</span><span class="sxs-lookup"><span data-stu-id="68b06-110">ABServer.exe</span></span>
    
      - <span data-ttu-id="68b06-111">AcpMcuSvc</span><span class="sxs-lookup"><span data-stu-id="68b06-111">AcpMcuSvc.exe</span></span>
    
      - <span data-ttu-id="68b06-112">ASMCUSvc .exe</span><span class="sxs-lookup"><span data-stu-id="68b06-112">ASMCUSvc.exe</span></span>
    
      - <span data-ttu-id="68b06-113">AVMCUSvc .exe</span><span class="sxs-lookup"><span data-stu-id="68b06-113">AVMCUSvc.exe</span></span>
    
      - <span data-ttu-id="68b06-114">ChannelService .exe</span><span class="sxs-lookup"><span data-stu-id="68b06-114">ChannelService.exe</span></span>
    
      - <span data-ttu-id="68b06-115">ClsAgent .exe</span><span class="sxs-lookup"><span data-stu-id="68b06-115">ClsAgent.exe</span></span>
    
      - <span data-ttu-id="68b06-116">ComplianceService</span><span class="sxs-lookup"><span data-stu-id="68b06-116">ComplianceService.exe</span></span>
    
      - <span data-ttu-id="68b06-117">DataMCUSvc</span><span class="sxs-lookup"><span data-stu-id="68b06-117">DataMCUSvc.exe</span></span>
    
      - <span data-ttu-id="68b06-118">DataProxy .exe</span><span class="sxs-lookup"><span data-stu-id="68b06-118">DataProxy.exe</span></span>
    
      - <span data-ttu-id="68b06-119">FileTransferAgent</span><span class="sxs-lookup"><span data-stu-id="68b06-119">FileTransferAgent.exe</span></span>
    
      - <span data-ttu-id="68b06-120">IMMCUSvc .exe</span><span class="sxs-lookup"><span data-stu-id="68b06-120">IMMCUSvc.exe</span></span>
    
      - <span data-ttu-id="68b06-121">LysSvc</span><span class="sxs-lookup"><span data-stu-id="68b06-121">LysSvc.exe</span></span>
    
      - <span data-ttu-id="68b06-122">MasterReplicatorAgent .exe</span><span class="sxs-lookup"><span data-stu-id="68b06-122">MasterReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="68b06-123">メディア Relaysvc</span><span class="sxs-lookup"><span data-stu-id="68b06-123">MediaRelaySvc.exe</span></span>
    
      - <span data-ttu-id="68b06-124">MediationServerSvc</span><span class="sxs-lookup"><span data-stu-id="68b06-124">MediationServerSvc.exe</span></span>
    
      - <span data-ttu-id="68b06-125">MRASSvc</span><span class="sxs-lookup"><span data-stu-id="68b06-125">MRASSvc.exe</span></span>
    
      - <span data-ttu-id="68b06-126">OcsAppServerHost</span><span class="sxs-lookup"><span data-stu-id="68b06-126">OcsAppServerHost.exe</span></span>
    
      - <span data-ttu-id="68b06-127">ReplicaReplicatorAgent</span><span class="sxs-lookup"><span data-stu-id="68b06-127">ReplicaReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="68b06-128">ReplicationApp .exe</span><span class="sxs-lookup"><span data-stu-id="68b06-128">ReplicationApp.exe</span></span>
    
      - <span data-ttu-id="68b06-129">RtcHost</span><span class="sxs-lookup"><span data-stu-id="68b06-129">RtcHost.exe</span></span>
    
      - <span data-ttu-id="68b06-130">RTCSrv</span><span class="sxs-lookup"><span data-stu-id="68b06-130">RTCSrv.exe</span></span>
    
      - <span data-ttu-id="68b06-131">XmppProxy .exe</span><span class="sxs-lookup"><span data-stu-id="68b06-131">XmppProxy.exe</span></span>
    
      - <span data-ttu-id="68b06-132">XmppTGW. .exe</span><span class="sxs-lookup"><span data-stu-id="68b06-132">XmppTGW.exe</span></span>

  - <span data-ttu-id="68b06-133">Windows Fabric ホストサービスプロセス:</span><span class="sxs-lookup"><span data-stu-id="68b06-133">Windows Fabric Host Service processes:</span></span>
    
      - <span data-ttu-id="68b06-134">Fabric</span><span class="sxs-lookup"><span data-stu-id="68b06-134">Fabric.exe</span></span>
    
      - <span data-ttu-id="68b06-135">FabricDCA</span><span class="sxs-lookup"><span data-stu-id="68b06-135">FabricDCA.exe</span></span>
    
      - <span data-ttu-id="68b06-136">FabricHost</span><span class="sxs-lookup"><span data-stu-id="68b06-136">FabricHost.exe</span></span>

  - <span data-ttu-id="68b06-137">IIS のプロセス:</span><span class="sxs-lookup"><span data-stu-id="68b06-137">IIS processes:</span></span>
    
      - <span data-ttu-id="68b06-138">% systemroot%\\system32\\inetsrv\\</span><span class="sxs-lookup"><span data-stu-id="68b06-138">%systemroot%\\system32\\inetsrv\\w3wp.exe</span></span>
    
      - <span data-ttu-id="68b06-139">% systemroot%\\SysWOW64\\inetsrv\\w3wp</span><span class="sxs-lookup"><span data-stu-id="68b06-139">%systemroot%\\SysWOW64\\inetsrv\\w3wp.exe</span></span>

  - <span data-ttu-id="68b06-140">SQL Server バックエンドプロセス:</span><span class="sxs-lookup"><span data-stu-id="68b06-140">SQL Server Back-End processes:</span></span>
    
      - <span data-ttu-id="68b06-141">% ProgramFiles%\\Microsoft SQL Server\\MSSQL11。MSSQLSERVER\\MSSQL\\Binn\\sqlservr.exe</span><span class="sxs-lookup"><span data-stu-id="68b06-141">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.MSSQLSERVER\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="68b06-142">% ProgramFiles%\\Microsoft SQL Server\\MSRS11。MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\reportingサービス .exe</span><span class="sxs-lookup"><span data-stu-id="68b06-142">%ProgramFiles%\\Microsoft SQL Server\\MSRS11.MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService.exe</span></span>
    
      - <span data-ttu-id="68b06-143">% ProgramFiles%\\Microsoft SQL Server\\MSAS11。MSSQLSERVER\\OLAP\\Bin\\msmdsrv.ini</span><span class="sxs-lookup"><span data-stu-id="68b06-143">%ProgramFiles%\\Microsoft SQL Server\\MSAS11.MSSQLSERVER\\OLAP\\Bin\\MSMDSrv.exe</span></span>

  - <span data-ttu-id="68b06-144">SQL Server フロントエンドプロセス:</span><span class="sxs-lookup"><span data-stu-id="68b06-144">SQL Server Front-End processes:</span></span>
    
      - <span data-ttu-id="68b06-145">% ProgramFiles%\\Microsoft SQL Server\\MSSQL11。LYNCLOCAL\\MSSQL\\Binn\\sqlservr.exe</span><span class="sxs-lookup"><span data-stu-id="68b06-145">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.LYNCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="68b06-146">% ProgramFiles%\\Microsoft SQL Server\\MSSQL11。RTCLOCAL\\MSSQL\\Binn\\sqlservr.exe</span><span class="sxs-lookup"><span data-stu-id="68b06-146">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.RTCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>

  - <span data-ttu-id="68b06-147">ディレクトリとファイル:</span><span class="sxs-lookup"><span data-stu-id="68b06-147">Directories and files:</span></span>
    
      - <span data-ttu-id="68b06-148">% systemroot%\\System32\\のログログ</span><span class="sxs-lookup"><span data-stu-id="68b06-148">%systemroot%\\System32\\LogFiles</span></span>
    
      - <span data-ttu-id="68b06-149">% systemroot%\\SysWow64\\ログログ</span><span class="sxs-lookup"><span data-stu-id="68b06-149">%systemroot%\\SysWow64\\LogFiles</span></span>
    
      - <span data-ttu-id="68b06-150">% systemroot%\\Microsoft.NET\\assembly\\GAC\_MSIL</span><span class="sxs-lookup"><span data-stu-id="68b06-150">%systemroot%\\Microsoft.NET\\assembly\\GAC\_MSIL</span></span>
    
      - <span data-ttu-id="68b06-151">% programfiles%\\Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68b06-151">%programfiles%\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="68b06-152">% programfiles%\\Common Files\\Microsoft Lync Server 2013\\監視ノード</span><span class="sxs-lookup"><span data-stu-id="68b06-152">%programfiles%\\Common Files\\Microsoft Lync Server 2013\\Watcher Node</span></span>
    
      - <span data-ttu-id="68b06-153">% programfiles%\\Common Files\\Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68b06-153">%programfiles%\\Common Files\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="68b06-154">% SystemDrive%\\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="68b06-154">%SystemDrive%\\RtcReplicaRoot</span></span>
    
      - <span data-ttu-id="68b06-155">ファイル共有ストア (トポロジ ビルダーで指定)。</span><span class="sxs-lookup"><span data-stu-id="68b06-155">File share store (specified in Topology Builder).</span></span> <span data-ttu-id="68b06-156">ファイル ストアはトポロジ ビルダーで指定されています。</span><span class="sxs-lookup"><span data-stu-id="68b06-156">File stores are specified in Topology Builder.</span></span>
    
      - <span data-ttu-id="68b06-157">SQL Server のデータおよびログ ファイル (バックエンド データベース、ユーザー ストア、アーカイブ ストア、監視ストア、およびアプリケーション ストア用のものを含みます)。</span><span class="sxs-lookup"><span data-stu-id="68b06-157">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="68b06-158">データベースとログ ファイルは、トポロジ ビルダーで指定できます。</span><span class="sxs-lookup"><span data-stu-id="68b06-158">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="68b06-159">既定の名前など、各データベースのデータおよびログファイルの詳細については、「展開」のドキュメントの「 [SQL server data and log file placement For Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68b06-159">For details about the data and log files for each database, including default names, see [SQL Server data and log file placement for Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="68b06-160">SQL Server のデータおよびログファイル (フロントエンドデータベース、Lync ストア、および RtcDatabase store のものを含む)。</span><span class="sxs-lookup"><span data-stu-id="68b06-160">SQL Server data and log files, including those for the Front-end database, Lync store, and RtcDatabase store.</span></span> <span data-ttu-id="68b06-161">通常、% localdrive%\\csdata の下にあります。</span><span class="sxs-lookup"><span data-stu-id="68b06-161">They are normally under %localdrive%\\CSData.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

