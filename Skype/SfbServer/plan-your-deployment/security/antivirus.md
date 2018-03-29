---
title: Skype for Business Server 2015 のウイルス スキャン除外範囲
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/24/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: ビジネス サーバー 2015 の Skype でのウイルス対策プログラムの相互運用の概要です。
ms.openlocfilehash: bb188b25c61269ee7c38829e1887a3443a0f77c4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server-2015"></a><span data-ttu-id="24960-103">Skype for Business Server 2015 のウイルス スキャン除外範囲</span><span class="sxs-lookup"><span data-stu-id="24960-103">Antivirus scanning exclusions for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="24960-104">ビジネス サーバー 2015 の Skype でのウイルス対策プログラムの相互運用の概要です。</span><span class="sxs-lookup"><span data-stu-id="24960-104">Overview of antivirus scanner interoperation with Skype for Business Server 2015.</span></span> 
  
<span data-ttu-id="24960-105">ウイルス対策スキャナーがビジネス サーバー 2015 の Skype の操作に干渉しないことを確認するには、ウイルス対策スキャナーを実行するビジネス サーバー 2015 のサーバーまたはサーバーの役割の各 Skype の特定のプロセスおよびディレクトリを除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24960-105">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server 2015, you must exclude specific processes and directories for each Skype for Business Server 2015 server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="24960-106">除外が必要なプロセスとディレクトリを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="24960-106">The following processes and directories should be excluded:</span></span>
  
> [!NOTE]
> <span data-ttu-id="24960-107">以下のフォルダーとファイルの場所は、ビジネス サーバー 2015 の Skype のデフォルトの場所です。</span><span class="sxs-lookup"><span data-stu-id="24960-107">Folder and file locations listed below are the default locations for Skype for Business Server 2015.</span></span> <span data-ttu-id="24960-108">既定の設定を使用しなかったすべての場所については、ここに示す既定の場所の代わりに、組織で指定した場所を除外してください。</span><span class="sxs-lookup"><span data-stu-id="24960-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="24960-109">一部のウイルス対策プログラムでは、除外リストに相対パスでなく絶対パスが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="24960-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span> 
  
- <span data-ttu-id="24960-110">ビジネス サーバー 2015 の Skype を処理します。</span><span class="sxs-lookup"><span data-stu-id="24960-110">Skype for Business Server 2015 processes:</span></span>
    
  - <span data-ttu-id="24960-111">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="24960-111">ABServer.exe</span></span>
    
  - <span data-ttu-id="24960-112">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="24960-112">ASMCUSvc.exe</span></span>
    
  - <span data-ttu-id="24960-113">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="24960-113">AVMCUSvc.exe</span></span>
    
  - <span data-ttu-id="24960-114">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="24960-114">ChannelService.exe</span></span>
    
  - <span data-ttu-id="24960-115">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="24960-115">ClsAgent.exe</span></span>
    
  - <span data-ttu-id="24960-116">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="24960-116">ComplianceService.exe</span></span>
    
  - <span data-ttu-id="24960-117">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="24960-117">DataMCUSvc.exe</span></span>
    
  - <span data-ttu-id="24960-118">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="24960-118">DataProxy.exe</span></span>
    
  - <span data-ttu-id="24960-119">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="24960-119">FileTransferAgent.exe</span></span>
    
  - <span data-ttu-id="24960-120">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="24960-120">HealthAgent.exe</span></span>
    
  - <span data-ttu-id="24960-121">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="24960-121">IMMCUSvc.exe</span></span>
    
  - <span data-ttu-id="24960-122">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="24960-122">LysSvc.exe</span></span>
    
  - <span data-ttu-id="24960-123">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="24960-123">MasterReplicatorAgent.exe</span></span>
    
  - <span data-ttu-id="24960-124">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="24960-124">MediaRelaySvc.exe</span></span>
    
  - <span data-ttu-id="24960-125">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="24960-125">MediationServerSvc.exe</span></span>
    
  - <span data-ttu-id="24960-126">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="24960-126">MRASSvc.exe</span></span>
    
  - <span data-ttu-id="24960-127">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="24960-127">OcsAppServerHost.exe</span></span>
    
  - <span data-ttu-id="24960-128">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="24960-128">ReplicaReplicatorAgent.exe</span></span>
    
  - <span data-ttu-id="24960-129">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="24960-129">ReplicationApp.exe</span></span>
    
  - <span data-ttu-id="24960-130">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="24960-130">RtcHost.exe</span></span>
    
  - <span data-ttu-id="24960-131">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="24960-131">RTCSrv.exe</span></span>
    
  - <span data-ttu-id="24960-132">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="24960-132">XmppProxy.exe</span></span>
    
  - <span data-ttu-id="24960-133">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="24960-133">XmppTGW.exe</span></span>
    
- <span data-ttu-id="24960-134">Windows Fabric Host Service のプロセス:</span><span class="sxs-lookup"><span data-stu-id="24960-134">Windows Fabric Host Service processes:</span></span>
    
  - <span data-ttu-id="24960-135">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="24960-135">Fabric.exe</span></span>
    
  - <span data-ttu-id="24960-136">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="24960-136">FabricDCA.exe</span></span>
    
  - <span data-ttu-id="24960-137">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="24960-137">FabricHost.exe</span></span>
    
- <span data-ttu-id="24960-138">IIS のプロセス:</span><span class="sxs-lookup"><span data-stu-id="24960-138">IIS processes:</span></span>
    
  - <span data-ttu-id="24960-139">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="24960-139">%systemroot%\system32\inetsrv\w3wp.exe</span></span>
    
  - <span data-ttu-id="24960-140">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="24960-140">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>
    
- <span data-ttu-id="24960-141">SQL Server バックエンドのプロセス:</span><span class="sxs-lookup"><span data-stu-id="24960-141">SQL Server Back-End processes:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="24960-142">これらのパスは、SQL Server バージョン固有のパスです。</span><span class="sxs-lookup"><span data-stu-id="24960-142">Note that these paths are specific to SQL Server version.</span></span> 
  
  - <span data-ttu-id="24960-143">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="24960-143">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>
    
  - <span data-ttu-id="24960-144">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="24960-144">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>
    
  - <span data-ttu-id="24960-145">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="24960-145">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>
    
- <span data-ttu-id="24960-146">SQL Server フロントエンドのプロセス:</span><span class="sxs-lookup"><span data-stu-id="24960-146">SQL Server Front-End processes:</span></span>
    
  - <span data-ttu-id="24960-147">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="24960-147">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>
    
  - <span data-ttu-id="24960-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="24960-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>
    
  - <span data-ttu-id="24960-149">Standard Edition インストールの RTC インスタンス</span><span class="sxs-lookup"><span data-stu-id="24960-149">Standard Edition Installation RTC Instance</span></span> 
    
  - <span data-ttu-id="24960-150">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="24960-150">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>
    
- <span data-ttu-id="24960-151">ディレクトリとファイル:</span><span class="sxs-lookup"><span data-stu-id="24960-151">Directories and files:</span></span>
    
  - <span data-ttu-id="24960-152">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="24960-152">%systemroot%\System32\LogFiles</span></span>
    
  - <span data-ttu-id="24960-153">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="24960-153">%systemroot%\SysWow64\LogFiles</span></span>
    
  - <span data-ttu-id="24960-154">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="24960-154">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>
    
  - <span data-ttu-id="24960-155">%programfiles%\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="24960-155">%programfiles%\Skype for Business Server 2015</span></span>
    
  - <span data-ttu-id="24960-156">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span><span class="sxs-lookup"><span data-stu-id="24960-156">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>
    
  - <span data-ttu-id="24960-157">%programfiles%\Common Files\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="24960-157">%programfiles%\Common Files\Skype for Business Server 2015</span></span>
    
  - <span data-ttu-id="24960-158">%programfiles%\Common Files\Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="24960-158">%programfiles%\Common Files\Skype for Business Online</span></span>
    
  - <span data-ttu-id="24960-159">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="24960-159">%SystemDrive%\RtcReplicaRoot</span></span>
    
  - <span data-ttu-id="24960-p103">ファイル共有ストア (トポロジ ビルダーで指定)。ファイル ストアはトポロジ ビルダーで指定されています。</span><span class="sxs-lookup"><span data-stu-id="24960-p103">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>
    
  - <span data-ttu-id="24960-162">SQL Server のデータおよびログ ファイル (バックエンド データベース、ユーザー ストア、アーカイブ ストア、監視ストア、およびアプリケーション ストア用のものを含みます)。</span><span class="sxs-lookup"><span data-stu-id="24960-162">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="24960-163">データベースとログ ファイルは、トポロジ ビルダーで指定できます。</span><span class="sxs-lookup"><span data-stu-id="24960-163">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="24960-164">既定の名前を含む、各データベースのデータとログ ファイルの詳細については、展開に関するドキュメントで[SQL Server のデータとログ ファイルの配置](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24960-164">For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>
    
  - <span data-ttu-id="24960-165">SQL Server データ ファイルとログ ファイル、Skype ビジネス ストア、および RtcDatabase のストアのフロント エンド データベースを含みます。</span><span class="sxs-lookup"><span data-stu-id="24960-165">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="24960-166">これらは通常、%localdrive%\CSData の下位にあります。</span><span class="sxs-lookup"><span data-stu-id="24960-166">They are normally under %localdrive%\CSData.</span></span>
    

