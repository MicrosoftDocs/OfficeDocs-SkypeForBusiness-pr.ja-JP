---
title: Skype for Business Server のウイルス対策スキャンの除外
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Skype for Business Server とのウイルス対策スキャナーの相互運用の概要。
ms.openlocfilehash: 64646304b98de075fd9af0a82096da8c0bff2f12
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104243"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="04835-103">Skype for Business Server のウイルス対策スキャンの除外</span><span class="sxs-lookup"><span data-stu-id="04835-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="04835-104">Skype for Business Server とのウイルス対策スキャナーの相互運用の概要。</span><span class="sxs-lookup"><span data-stu-id="04835-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="04835-105">ウイルス対策スキャナーが Skype for Business Server の操作を妨げないよう、ウイルス対策スキャナーを実行する Skype for Business Server サーバーまたはサーバーの役割ごとに特定のプロセスとディレクトリを除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04835-105">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="04835-106">除外が必要なプロセスとディレクトリを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="04835-106">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="04835-107">以下に示すフォルダーとファイルの場所は、Skype for Business Server の既定の場所です。</span><span class="sxs-lookup"><span data-stu-id="04835-107">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="04835-108">既定の設定を使用しなかったすべての場所については、ここに示す既定の場所の代わりに、組織で指定した場所を除外してください。</span><span class="sxs-lookup"><span data-stu-id="04835-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="04835-109">一部のウイルス対策プログラムでは、除外リストに相対パスではなく絶対パスが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="04835-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="04835-110">Skype for Business Server プロセス:</span><span class="sxs-lookup"><span data-stu-id="04835-110">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="04835-111">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="04835-111">ABServer.exe</span></span>

  - <span data-ttu-id="04835-112">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="04835-112">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="04835-113">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="04835-113">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="04835-114">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="04835-114">ChannelService.exe</span></span>

  - <span data-ttu-id="04835-115">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="04835-115">ClsAgent.exe</span></span>

  - <span data-ttu-id="04835-116">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="04835-116">ComplianceService.exe</span></span>

  - <span data-ttu-id="04835-117">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="04835-117">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="04835-118">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="04835-118">DataProxy.exe</span></span>

  - <span data-ttu-id="04835-119">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="04835-119">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="04835-120">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="04835-120">HealthAgent.exe</span></span>

  - <span data-ttu-id="04835-121">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="04835-121">IMMCUSvc.exe</span></span>
  
  - <span data-ttu-id="04835-122">LyncBackupService.exe</span><span class="sxs-lookup"><span data-stu-id="04835-122">LyncBackupService.exe</span></span>

  - <span data-ttu-id="04835-123">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="04835-123">LysSvc.exe</span></span>

  - <span data-ttu-id="04835-124">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="04835-124">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="04835-125">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="04835-125">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="04835-126">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="04835-126">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="04835-127">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="04835-127">MRASSvc.exe</span></span>

  - <span data-ttu-id="04835-128">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="04835-128">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="04835-129">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="04835-129">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="04835-130">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="04835-130">ReplicationApp.exe</span></span>

  - <span data-ttu-id="04835-131">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="04835-131">RtcHost.exe</span></span>

  - <span data-ttu-id="04835-132">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="04835-132">RTCSrv.exe</span></span>

  - <span data-ttu-id="04835-133">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="04835-133">XmppProxy.exe</span></span>

  - <span data-ttu-id="04835-134">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="04835-134">XmppTGW.exe</span></span>

- <span data-ttu-id="04835-135">Windows Fabric Host Service プロセス:</span><span class="sxs-lookup"><span data-stu-id="04835-135">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="04835-136">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="04835-136">Fabric.exe</span></span>

  - <span data-ttu-id="04835-137">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="04835-137">FabricDCA.exe</span></span>

  - <span data-ttu-id="04835-138">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="04835-138">FabricHost.exe</span></span>

- <span data-ttu-id="04835-139">IIS のプロセス:</span><span class="sxs-lookup"><span data-stu-id="04835-139">IIS processes:</span></span>

  - <span data-ttu-id="04835-140">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="04835-140">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="04835-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="04835-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="04835-142">SQL Server Back-Endプロセス:</span><span class="sxs-lookup"><span data-stu-id="04835-142">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="04835-143">これらのパスは、特定のバージョンに固有SQL Server注意してください。</span><span class="sxs-lookup"><span data-stu-id="04835-143">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="04835-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="04835-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="04835-145">%ProgramFiles%\Microsoft SQL Server\MSRS11。MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="04835-145">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="04835-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="04835-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="04835-147">SQL Server Front-Endプロセス:</span><span class="sxs-lookup"><span data-stu-id="04835-147">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="04835-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="04835-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="04835-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="04835-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="04835-150">Standard Edition インストール RTC インスタンス</span><span class="sxs-lookup"><span data-stu-id="04835-150">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="04835-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="04835-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="04835-152">ディレクトリとファイル:</span><span class="sxs-lookup"><span data-stu-id="04835-152">Directories and files:</span></span>

  - <span data-ttu-id="04835-153">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="04835-153">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="04835-154">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="04835-154">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="04835-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="04835-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="04835-156">これらのパスは、Skype for Business Server のバージョンに固有のパスです。</span><span class="sxs-lookup"><span data-stu-id="04835-156">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="04835-157">%programfiles%\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="04835-157">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="04835-158">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span><span class="sxs-lookup"><span data-stu-id="04835-158">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="04835-159">%programfiles%\Common Files\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="04835-159">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="04835-160">%programfiles%\Common Files\Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="04835-160">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="04835-161">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="04835-161">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="04835-p103">ファイル共有ストア (トポロジ ビルダーで指定)。ファイル ストアはトポロジ ビルダーで指定されています。</span><span class="sxs-lookup"><span data-stu-id="04835-p103">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="04835-164">SQL Server のデータおよびログ ファイル (バックエンド データベース、ユーザー ストア、アーカイブ ストア、監視ストア、およびアプリケーション ストア用のものを含みます)。</span><span class="sxs-lookup"><span data-stu-id="04835-164">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="04835-165">データベースとログ ファイルは、トポロジ ビルダーで指定できます。</span><span class="sxs-lookup"><span data-stu-id="04835-165">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="04835-166">既定の名前など、各データベースのデータおよびログ ファイルの詳細については、展開のドキュメントの「[SQL Server Data and Log File Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04835-166">For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) in the Deployment documentation.</span></span>

  - <span data-ttu-id="04835-167">SQL Server、Skype for Business ストア、RtcDatabase ストアなどのデータ ファイルとログ ファイルを格納します。</span><span class="sxs-lookup"><span data-stu-id="04835-167">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="04835-168">通常、%localdrive%\CSData の下にあります。</span><span class="sxs-lookup"><span data-stu-id="04835-168">They are normally under %localdrive%\CSData.</span></span>