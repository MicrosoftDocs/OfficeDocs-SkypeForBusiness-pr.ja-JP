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
ms.openlocfilehash: b59a5c474a96d312ebe3a648536ebe827e684931
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832267"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="3d49e-103">Skype for Business Server のウイルス対策スキャンの除外</span><span class="sxs-lookup"><span data-stu-id="3d49e-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="3d49e-104">Skype for Business Server とのウイルス対策スキャナーの相互運用の概要。</span><span class="sxs-lookup"><span data-stu-id="3d49e-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="3d49e-105">ウイルス対策スキャナーが Skype for Business Server の動作に干渉しないようにするには、ウイルス対策スキャナーを実行する Skype for Business Server サーバーまたはサーバーの役割ごとに特定のプロセスとディレクトリを除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d49e-105">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="3d49e-106">除外が必要なプロセスとディレクトリを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="3d49e-106">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="3d49e-107">次に示すフォルダーとファイルの場所は、Skype for Business Server の既定の場所です。</span><span class="sxs-lookup"><span data-stu-id="3d49e-107">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="3d49e-108">既定の設定を使用しなかったすべての場所については、ここに示す既定の場所の代わりに、組織で指定した場所を除外してください。</span><span class="sxs-lookup"><span data-stu-id="3d49e-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3d49e-109">一部のウイルス対策プログラムでは、除外一覧に相対パスではなく絶対パスが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="3d49e-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="3d49e-110">Skype for Business Server プロセス:</span><span class="sxs-lookup"><span data-stu-id="3d49e-110">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="3d49e-111">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="3d49e-111">ABServer.exe</span></span>

  - <span data-ttu-id="3d49e-112">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="3d49e-112">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="3d49e-113">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="3d49e-113">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="3d49e-114">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="3d49e-114">ChannelService.exe</span></span>

  - <span data-ttu-id="3d49e-115">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="3d49e-115">ClsAgent.exe</span></span>

  - <span data-ttu-id="3d49e-116">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="3d49e-116">ComplianceService.exe</span></span>

  - <span data-ttu-id="3d49e-117">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="3d49e-117">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="3d49e-118">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="3d49e-118">DataProxy.exe</span></span>

  - <span data-ttu-id="3d49e-119">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="3d49e-119">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="3d49e-120">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="3d49e-120">HealthAgent.exe</span></span>

  - <span data-ttu-id="3d49e-121">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="3d49e-121">IMMCUSvc.exe</span></span>
  
  - <span data-ttu-id="3d49e-122">LyncBackupService.exe</span><span class="sxs-lookup"><span data-stu-id="3d49e-122">LyncBackupService.exe</span></span>

  - <span data-ttu-id="3d49e-123">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="3d49e-123">LysSvc.exe</span></span>

  - <span data-ttu-id="3d49e-124">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="3d49e-124">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="3d49e-125">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="3d49e-125">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="3d49e-126">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="3d49e-126">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="3d49e-127">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="3d49e-127">MRASSvc.exe</span></span>

  - <span data-ttu-id="3d49e-128">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="3d49e-128">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="3d49e-129">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="3d49e-129">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="3d49e-130">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="3d49e-130">ReplicationApp.exe</span></span>

  - <span data-ttu-id="3d49e-131">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="3d49e-131">RtcHost.exe</span></span>

  - <span data-ttu-id="3d49e-132">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="3d49e-132">RTCSrv.exe</span></span>

  - <span data-ttu-id="3d49e-133">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="3d49e-133">XmppProxy.exe</span></span>

  - <span data-ttu-id="3d49e-134">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="3d49e-134">XmppTGW.exe</span></span>

- <span data-ttu-id="3d49e-135">Windows Fabric Host Service プロセス:</span><span class="sxs-lookup"><span data-stu-id="3d49e-135">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="3d49e-136">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="3d49e-136">Fabric.exe</span></span>

  - <span data-ttu-id="3d49e-137">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="3d49e-137">FabricDCA.exe</span></span>

  - <span data-ttu-id="3d49e-138">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="3d49e-138">FabricHost.exe</span></span>

- <span data-ttu-id="3d49e-139">IIS のプロセス:</span><span class="sxs-lookup"><span data-stu-id="3d49e-139">IIS processes:</span></span>

  - <span data-ttu-id="3d49e-140">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="3d49e-140">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="3d49e-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="3d49e-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="3d49e-142">SQL Server Back-Endプロセス:</span><span class="sxs-lookup"><span data-stu-id="3d49e-142">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="3d49e-143">これらのパスは、特定のバージョンに固有SQL Server注意してください。</span><span class="sxs-lookup"><span data-stu-id="3d49e-143">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="3d49e-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="3d49e-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="3d49e-145">%ProgramFiles%\Microsoft SQL Server\MSRS11。MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="3d49e-145">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="3d49e-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="3d49e-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="3d49e-147">SQL Server Front-Endプロセス:</span><span class="sxs-lookup"><span data-stu-id="3d49e-147">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="3d49e-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="3d49e-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="3d49e-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="3d49e-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="3d49e-150">Standard Edition インストール RTC インスタンス</span><span class="sxs-lookup"><span data-stu-id="3d49e-150">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="3d49e-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="3d49e-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="3d49e-152">ディレクトリとファイル:</span><span class="sxs-lookup"><span data-stu-id="3d49e-152">Directories and files:</span></span>

  - <span data-ttu-id="3d49e-153">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="3d49e-153">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="3d49e-154">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="3d49e-154">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="3d49e-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="3d49e-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="3d49e-156">これらのパスは、Skype for Business Server のバージョンに固有のパスです。</span><span class="sxs-lookup"><span data-stu-id="3d49e-156">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="3d49e-157">%programfiles%\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3d49e-157">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="3d49e-158">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span><span class="sxs-lookup"><span data-stu-id="3d49e-158">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="3d49e-159">%programfiles%\Common Files\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3d49e-159">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="3d49e-160">%programfiles%\Common Files\Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="3d49e-160">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="3d49e-161">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="3d49e-161">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="3d49e-p103">ファイル共有ストア (トポロジ ビルダーで指定)。ファイル ストアはトポロジ ビルダーで指定されています。</span><span class="sxs-lookup"><span data-stu-id="3d49e-p103">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="3d49e-164">SQL Server のデータおよびログ ファイル (バックエンド データベース、ユーザー ストア、アーカイブ ストア、監視ストア、およびアプリケーション ストア用のものを含みます)。</span><span class="sxs-lookup"><span data-stu-id="3d49e-164">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="3d49e-165">データベースとログ ファイルは、トポロジ ビルダーで指定できます。</span><span class="sxs-lookup"><span data-stu-id="3d49e-165">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="3d49e-166">既定の名前など、各データベースのデータおよびログ ファイルの詳細については、展開のドキュメントの「[SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d49e-166">For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

  - <span data-ttu-id="3d49e-167">SQL Server、フロントエンド データベース、Skype for Business ストア、RtcDatabase ストア用のデータファイルやログ ファイルを含めます。</span><span class="sxs-lookup"><span data-stu-id="3d49e-167">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="3d49e-168">通常、%localdrive%\CSData の下にあります。</span><span class="sxs-lookup"><span data-stu-id="3d49e-168">They are normally under %localdrive%\CSData.</span></span>


