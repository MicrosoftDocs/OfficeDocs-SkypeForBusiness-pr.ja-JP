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
ms.openlocfilehash: 9ec13b31328744bb154c9eb5e09dff7665c4b540
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296974"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="256b0-103">Skype for Business Server のウイルススキャン除外の除外</span><span class="sxs-lookup"><span data-stu-id="256b0-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="256b0-104">Skype for Business Server とのウイルス対策スキャナーの相互運用の概要。</span><span class="sxs-lookup"><span data-stu-id="256b0-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="256b0-105">この記事には、サポートされているバージョンの Microsoft Windows を実行しているコンピューターで、Active Directory ドメインでウイルス対策ソフトウェアを使用している場合に発生する可能性のある原因を特定するための推奨事項が記載されています。環境または管理されたビジネス環境。</span><span class="sxs-lookup"><span data-stu-id="256b0-105">This article contains recommendations that may help an administrator determine the cause of potential instability on a computer that is running a supported version of Microsoft Windows when it is used with antivirus software in an Active Directory domain environment or in a managed business environment.</span></span>

<span data-ttu-id="256b0-106">システムを評価するために、これらの手順を一時的に適用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="256b0-106">We recommend that you temporarily apply these procedures to evaluate a system.</span></span> <span data-ttu-id="256b0-107">この記事に記載されている推奨事項に従ってシステムのパフォーマンスまたは安定性が改善された場合は、ウイルス対策ソフトウェアベンダーに問い合わせてください。または、ウイルス対策ソフトウェアの更新版をお探しください。</span><span class="sxs-lookup"><span data-stu-id="256b0-107">If your system performance or stability is improved by the recommendations that are made in this article, contact your antivirus software vendor for instructions or for an updated version of the antivirus software.</span></span>

<span data-ttu-id="256b0-108">この記事では、セキュリティ設定のレベルを下げる方法、またはコンピューターのセキュリティ機能を一時的に無効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="256b0-108">This article contains information that shows how to help lower security settings or how to temporarily turn off security features on a computer.</span></span> <span data-ttu-id="256b0-109">これらの変更を加えて、特定の問題の性質を理解することができます。</span><span class="sxs-lookup"><span data-stu-id="256b0-109">You can make these changes to understand the nature of a specific problem.</span></span> <span data-ttu-id="256b0-110">これらの変更を行う前に、この回避策の実装に関連するリスクを特定の環境で評価することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="256b0-110">Before you make these changes, we recommend that you evaluate the risks that are associated with implementing this workaround in your particular environment.</span></span> <span data-ttu-id="256b0-111">この回避策を実装する場合は、ウイルス対策ソフトウェアによってスキャンされなくなったファイルをコンピューターで保護するために、適切な追加の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="256b0-111">If you implement this workaround, take any appropriate additional steps to help protect the computer for the files that are no longer being scanned by your antivirus software.</span></span>

<span data-ttu-id="256b0-112">ウイルス対策スキャナーが Skype for Business Server の動作に干渉しないようにするには、ウイルス対策ソフトウェアを実行している各 Skype for Business Server サーバーまたはサーバーロールの特定のプロセスとディレクトリを除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="256b0-112">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="256b0-113">除外が必要なプロセスとディレクトリを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="256b0-113">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="256b0-114">次に示すフォルダーとファイルの場所は、Skype for Business Server の既定の場所です。</span><span class="sxs-lookup"><span data-stu-id="256b0-114">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="256b0-115">既定の設定を使用しなかったすべての場所については、ここに示す既定の場所の代わりに、組織で指定した場所を除外してください。</span><span class="sxs-lookup"><span data-stu-id="256b0-115">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="256b0-116">一部のウイルス対策プログラムでは、除外リストに相対パスでなく絶対パスが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="256b0-116">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="256b0-117">Skype for Business Server のプロセス:</span><span class="sxs-lookup"><span data-stu-id="256b0-117">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="256b0-118">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="256b0-118">ABServer.exe</span></span>

  - <span data-ttu-id="256b0-119">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="256b0-119">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="256b0-120">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="256b0-120">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="256b0-121">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="256b0-121">ChannelService.exe</span></span>

  - <span data-ttu-id="256b0-122">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="256b0-122">ClsAgent.exe</span></span>

  - <span data-ttu-id="256b0-123">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="256b0-123">ComplianceService.exe</span></span>

  - <span data-ttu-id="256b0-124">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="256b0-124">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="256b0-125">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="256b0-125">DataProxy.exe</span></span>

  - <span data-ttu-id="256b0-126">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="256b0-126">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="256b0-127">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="256b0-127">HealthAgent.exe</span></span>

  - <span data-ttu-id="256b0-128">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="256b0-128">IMMCUSvc.exe</span></span>
  
  - <span data-ttu-id="256b0-129">LyncBackupService</span><span class="sxs-lookup"><span data-stu-id="256b0-129">LyncBackupService.exe</span></span>

  - <span data-ttu-id="256b0-130">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="256b0-130">LysSvc.exe</span></span>

  - <span data-ttu-id="256b0-131">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="256b0-131">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="256b0-132">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="256b0-132">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="256b0-133">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="256b0-133">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="256b0-134">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="256b0-134">MRASSvc.exe</span></span>

  - <span data-ttu-id="256b0-135">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="256b0-135">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="256b0-136">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="256b0-136">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="256b0-137">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="256b0-137">ReplicationApp.exe</span></span>

  - <span data-ttu-id="256b0-138">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="256b0-138">RtcHost.exe</span></span>

  - <span data-ttu-id="256b0-139">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="256b0-139">RTCSrv.exe</span></span>

  - <span data-ttu-id="256b0-140">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="256b0-140">XmppProxy.exe</span></span>

  - <span data-ttu-id="256b0-141">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="256b0-141">XmppTGW.exe</span></span>

- <span data-ttu-id="256b0-142">Windows Fabric Host Service のプロセス:</span><span class="sxs-lookup"><span data-stu-id="256b0-142">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="256b0-143">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="256b0-143">Fabric.exe</span></span>

  - <span data-ttu-id="256b0-144">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="256b0-144">FabricDCA.exe</span></span>

  - <span data-ttu-id="256b0-145">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="256b0-145">FabricHost.exe</span></span>

- <span data-ttu-id="256b0-146">IIS のプロセス:</span><span class="sxs-lookup"><span data-stu-id="256b0-146">IIS processes:</span></span>

  - <span data-ttu-id="256b0-147">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="256b0-147">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="256b0-148">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="256b0-148">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="256b0-149">SQL Server バックエンドのプロセス:</span><span class="sxs-lookup"><span data-stu-id="256b0-149">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="256b0-150">これらのパスは、SQL Server バージョン固有のパスです。</span><span class="sxs-lookup"><span data-stu-id="256b0-150">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="256b0-151">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="256b0-151">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="256b0-152">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="256b0-152">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="256b0-153">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="256b0-153">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="256b0-154">SQL Server フロントエンドのプロセス:</span><span class="sxs-lookup"><span data-stu-id="256b0-154">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="256b0-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="256b0-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="256b0-156">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="256b0-156">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="256b0-157">Standard Edition インストールの RTC インスタンス</span><span class="sxs-lookup"><span data-stu-id="256b0-157">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="256b0-158">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="256b0-158">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="256b0-159">ディレクトリとファイル:</span><span class="sxs-lookup"><span data-stu-id="256b0-159">Directories and files:</span></span>

  - <span data-ttu-id="256b0-160">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="256b0-160">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="256b0-161">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="256b0-161">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="256b0-162">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="256b0-162">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="256b0-163">これらのパスは、Skype for Business Server のバージョンに固有のものであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="256b0-163">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="256b0-164">%programfiles%\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="256b0-164">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="256b0-165">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span><span class="sxs-lookup"><span data-stu-id="256b0-165">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="256b0-166">%programfiles%\Common Files\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="256b0-166">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="256b0-167">%programfiles%\Common Files\Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="256b0-167">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="256b0-168">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="256b0-168">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="256b0-p105">ファイル共有ストア (トポロジ ビルダーで指定)。ファイル ストアはトポロジ ビルダーで指定されています。</span><span class="sxs-lookup"><span data-stu-id="256b0-p105">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="256b0-p106">SQL Server のデータおよびログ ファイル (バックエンド データベース、ユーザー ストア、アーカイブ ストア、監視ストア、およびアプリケーション ストア用のものを含みます)。データベースとログ ファイルは、トポロジ ビルダーで指定できます。既定の名前など、各データベースのデータおよびログ ファイルの詳細については、「展開」のドキュメントの「[SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="256b0-p106">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store. Database and log files can be specified in Topology Builder. For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

  - <span data-ttu-id="256b0-174">SQL Server のデータとログファイル (フロントエンドデータベース、Skype for Business ストア、および RtcDatabase store のものを含む)。</span><span class="sxs-lookup"><span data-stu-id="256b0-174">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="256b0-175">これらは通常、%localdrive%\CSData の下位にあります。</span><span class="sxs-lookup"><span data-stu-id="256b0-175">They are normally under %localdrive%\CSData.</span></span>


