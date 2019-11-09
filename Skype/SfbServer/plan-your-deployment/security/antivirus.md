---
title: Skype for Business Server のウイルススキャン除外の除外
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Skype for Business Server とのウイルス対策スキャナーの相互運用の概要。
ms.openlocfilehash: 69fb02d04f27b7444a3b8cadaacafc05654a1c9f
ms.sourcegitcommit: 1aa98e3865d5a0f7be5e1cba497dea4ac7b9c607
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2019
ms.locfileid: "38074629"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="6b0a5-103">Skype for Business Server のウイルススキャン除外の除外</span><span class="sxs-lookup"><span data-stu-id="6b0a5-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="6b0a5-104">Skype for Business Server とのウイルス対策スキャナーの相互運用の概要。</span><span class="sxs-lookup"><span data-stu-id="6b0a5-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="6b0a5-105">ウイルス対策スキャナーが Skype for Business Server の動作に干渉しないようにするには、ウイルス対策ソフトウェアを実行している各 Skype for Business Server サーバーまたはサーバーロールの特定のプロセスとディレクトリを除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b0a5-105">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="6b0a5-106">除外が必要なプロセスとディレクトリを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="6b0a5-106">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="6b0a5-107">次に示すフォルダーとファイルの場所は、Skype for Business Server の既定の場所です。</span><span class="sxs-lookup"><span data-stu-id="6b0a5-107">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="6b0a5-108">既定の設定を使用しなかったすべての場所については、ここに示す既定の場所の代わりに、組織で指定した場所を除外してください。</span><span class="sxs-lookup"><span data-stu-id="6b0a5-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6b0a5-109">一部のウイルス対策プログラムでは、除外リストに相対パスでなく絶対パスが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="6b0a5-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="6b0a5-110">Skype for Business Server のプロセス:</span><span class="sxs-lookup"><span data-stu-id="6b0a5-110">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="6b0a5-111">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="6b0a5-111">ABServer.exe</span></span>

  - <span data-ttu-id="6b0a5-112">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="6b0a5-112">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="6b0a5-113">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="6b0a5-113">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="6b0a5-114">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="6b0a5-114">ChannelService.exe</span></span>

  - <span data-ttu-id="6b0a5-115">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="6b0a5-115">ClsAgent.exe</span></span>

  - <span data-ttu-id="6b0a5-116">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="6b0a5-116">ComplianceService.exe</span></span>

  - <span data-ttu-id="6b0a5-117">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="6b0a5-117">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="6b0a5-118">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="6b0a5-118">DataProxy.exe</span></span>

  - <span data-ttu-id="6b0a5-119">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="6b0a5-119">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="6b0a5-120">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="6b0a5-120">HealthAgent.exe</span></span>

  - <span data-ttu-id="6b0a5-121">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="6b0a5-121">IMMCUSvc.exe</span></span>
  
  - <span data-ttu-id="6b0a5-122">LyncBackupService</span><span class="sxs-lookup"><span data-stu-id="6b0a5-122">LyncBackupService.exe</span></span>

  - <span data-ttu-id="6b0a5-123">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="6b0a5-123">LysSvc.exe</span></span>

  - <span data-ttu-id="6b0a5-124">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="6b0a5-124">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="6b0a5-125">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="6b0a5-125">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="6b0a5-126">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="6b0a5-126">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="6b0a5-127">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="6b0a5-127">MRASSvc.exe</span></span>

  - <span data-ttu-id="6b0a5-128">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="6b0a5-128">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="6b0a5-129">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="6b0a5-129">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="6b0a5-130">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="6b0a5-130">ReplicationApp.exe</span></span>

  - <span data-ttu-id="6b0a5-131">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="6b0a5-131">RtcHost.exe</span></span>

  - <span data-ttu-id="6b0a5-132">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="6b0a5-132">RTCSrv.exe</span></span>

  - <span data-ttu-id="6b0a5-133">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="6b0a5-133">XmppProxy.exe</span></span>

  - <span data-ttu-id="6b0a5-134">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="6b0a5-134">XmppTGW.exe</span></span>

- <span data-ttu-id="6b0a5-135">Windows Fabric Host Service のプロセス:</span><span class="sxs-lookup"><span data-stu-id="6b0a5-135">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="6b0a5-136">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="6b0a5-136">Fabric.exe</span></span>

  - <span data-ttu-id="6b0a5-137">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="6b0a5-137">FabricDCA.exe</span></span>

  - <span data-ttu-id="6b0a5-138">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="6b0a5-138">FabricHost.exe</span></span>

- <span data-ttu-id="6b0a5-139">IIS のプロセス:</span><span class="sxs-lookup"><span data-stu-id="6b0a5-139">IIS processes:</span></span>

  - <span data-ttu-id="6b0a5-140">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="6b0a5-140">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="6b0a5-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="6b0a5-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="6b0a5-142">SQL Server バックエンドのプロセス:</span><span class="sxs-lookup"><span data-stu-id="6b0a5-142">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="6b0a5-143">これらのパスは、SQL Server バージョン固有のパスです。</span><span class="sxs-lookup"><span data-stu-id="6b0a5-143">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="6b0a5-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="6b0a5-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="6b0a5-145">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="6b0a5-145">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="6b0a5-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="6b0a5-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="6b0a5-147">SQL Server フロントエンドのプロセス:</span><span class="sxs-lookup"><span data-stu-id="6b0a5-147">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="6b0a5-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="6b0a5-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="6b0a5-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="6b0a5-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="6b0a5-150">Standard Edition インストールの RTC インスタンス</span><span class="sxs-lookup"><span data-stu-id="6b0a5-150">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="6b0a5-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="6b0a5-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="6b0a5-152">ディレクトリとファイル:</span><span class="sxs-lookup"><span data-stu-id="6b0a5-152">Directories and files:</span></span>

  - <span data-ttu-id="6b0a5-153">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="6b0a5-153">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="6b0a5-154">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="6b0a5-154">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="6b0a5-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="6b0a5-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="6b0a5-156">これらのパスは、Skype for Business Server のバージョンに固有のものであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6b0a5-156">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="6b0a5-157">%programfiles%\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="6b0a5-157">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="6b0a5-158">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span><span class="sxs-lookup"><span data-stu-id="6b0a5-158">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="6b0a5-159">%programfiles%\Common Files\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="6b0a5-159">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="6b0a5-160">%programfiles%\Common Files\Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6b0a5-160">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="6b0a5-161">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="6b0a5-161">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="6b0a5-p103">ファイル共有ストア (トポロジ ビルダーで指定)。ファイル ストアはトポロジ ビルダーで指定されています。</span><span class="sxs-lookup"><span data-stu-id="6b0a5-p103">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="6b0a5-p104">SQL Server のデータおよびログ ファイル (バックエンド データベース、ユーザー ストア、アーカイブ ストア、監視ストア、およびアプリケーション ストア用のものを含みます)。データベースとログ ファイルは、トポロジ ビルダーで指定できます。既定の名前など、各データベースのデータおよびログ ファイルの詳細については、「展開」のドキュメントの「[SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b0a5-p104">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store. Database and log files can be specified in Topology Builder. For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

  - <span data-ttu-id="6b0a5-167">SQL Server のデータとログファイル (フロントエンドデータベース、Skype for Business ストア、および RtcDatabase store のものを含む)。</span><span class="sxs-lookup"><span data-stu-id="6b0a5-167">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="6b0a5-168">これらは通常、%localdrive%\CSData の下位にあります。</span><span class="sxs-lookup"><span data-stu-id="6b0a5-168">They are normally under %localdrive%\CSData.</span></span>


