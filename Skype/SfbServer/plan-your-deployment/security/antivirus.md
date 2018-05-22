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
ms.openlocfilehash: 054ed03146964de7ec0621138186e3c41843c236
ms.sourcegitcommit: 1cb8ab7d1e3debb84f051be404403e4a116ee741
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2018
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server-2015"></a><span data-ttu-id="910b1-103">Skype for Business Server 2015 のウイルス スキャン除外範囲</span><span class="sxs-lookup"><span data-stu-id="910b1-103">Antivirus scanning exclusions for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="910b1-104">ビジネス サーバー 2015 の Skype でのウイルス対策プログラムの相互運用の概要です。</span><span class="sxs-lookup"><span data-stu-id="910b1-104">Overview of antivirus scanner interoperation with Skype for Business Server 2015.</span></span>

<span data-ttu-id="910b1-105">この資料には、管理者は Active Directory ドメインでのウイルス対策ソフトウェアで使用されている場合、サポートされているバージョンの Microsoft Windows を実行しているコンピューター上の潜在的な不安定の原因を特定するのに役立つ推奨事項が含まれています。環境またはマネージ ビジネス環境です。</span><span class="sxs-lookup"><span data-stu-id="910b1-105">This article contains recommendations that may help an administrator determine the cause of potential instability on a computer that is running a supported version of Microsoft Windows when it is used with antivirus software in an Active Directory domain environment or in a managed business environment.</span></span>

<span data-ttu-id="910b1-106">システムを評価するためにこれらの手順を一時的に適用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="910b1-106">We recommend that you temporarily apply these procedures to evaluate a system.</span></span> <span data-ttu-id="910b1-107">場合はここで行われるための推奨事項により、システムのパフォーマンスや安定性が向上し、またはウイルス対策ソフトウェアの更新されたバージョンの手順については、ウイルス対策ソフトウェアの製造元に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="910b1-107">If your system performance or stability is improved by the recommendations that are made in this article, contact your antivirus software vendor for instructions or for an updated version of the antivirus software.</span></span>

<span data-ttu-id="910b1-108">この資料には、セキュリティ設定を低くする方法、またはコンピューターのセキュリティ機能を一時的に無効する方法を示す情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="910b1-108">This article contains information that shows how to help lower security settings or how to temporarily turn off security features on a computer.</span></span> <span data-ttu-id="910b1-109">特定の問題の性質を理解するのにはこれらの変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="910b1-109">You can make these changes to understand the nature of a specific problem.</span></span> <span data-ttu-id="910b1-110">これらの変更を行う前に、特定の環境でこの回避策の実装に関連付けられているリスクを評価することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="910b1-110">Before you make these changes, we recommend that you evaluate the risks that are associated with implementing this workaround in your particular environment.</span></span> <span data-ttu-id="910b1-111">この回避策を実装する場合は、不要になったウイルス対策ソフトウェアによってスキャンされているファイルには、コンピューターを保護するために適切な追加の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="910b1-111">If you implement this workaround, take any appropriate additional steps to help protect the computer for the files that are no longer being scanned by your antivirus software.</span></span>
  
<span data-ttu-id="910b1-112">ウイルス対策スキャナーがビジネス サーバー 2015 の Skype の操作に干渉しないことを確認するには、ウイルス対策スキャナーを実行するビジネス サーバー 2015 のサーバーまたはサーバーの役割の各 Skype の特定のプロセスおよびディレクトリを除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="910b1-112">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server 2015, you must exclude specific processes and directories for each Skype for Business Server 2015 server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="910b1-113">除外が必要なプロセスとディレクトリを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="910b1-113">The following processes and directories should be excluded:</span></span>
  
> [!NOTE]
> <span data-ttu-id="910b1-114">以下のフォルダーとファイルの場所は、ビジネス サーバー 2015 の Skype のデフォルトの場所です。</span><span class="sxs-lookup"><span data-stu-id="910b1-114">Folder and file locations listed below are the default locations for Skype for Business Server 2015.</span></span> <span data-ttu-id="910b1-115">既定の設定を使用しなかったすべての場所については、ここに示す既定の場所の代わりに、組織で指定した場所を除外してください。</span><span class="sxs-lookup"><span data-stu-id="910b1-115">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="910b1-116">一部のウイルス対策プログラムでは、除外リストに相対パスでなく絶対パスが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="910b1-116">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span> 
  
- <span data-ttu-id="910b1-117">ビジネス サーバー 2015 の Skype を処理します。</span><span class="sxs-lookup"><span data-stu-id="910b1-117">Skype for Business Server 2015 processes:</span></span>
    
  - <span data-ttu-id="910b1-118">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="910b1-118">ABServer.exe</span></span>
    
  - <span data-ttu-id="910b1-119">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="910b1-119">ASMCUSvc.exe</span></span>
    
  - <span data-ttu-id="910b1-120">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="910b1-120">AVMCUSvc.exe</span></span>
    
  - <span data-ttu-id="910b1-121">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="910b1-121">ChannelService.exe</span></span>
    
  - <span data-ttu-id="910b1-122">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="910b1-122">ClsAgent.exe</span></span>
    
  - <span data-ttu-id="910b1-123">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="910b1-123">ComplianceService.exe</span></span>
    
  - <span data-ttu-id="910b1-124">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="910b1-124">DataMCUSvc.exe</span></span>
    
  - <span data-ttu-id="910b1-125">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="910b1-125">DataProxy.exe</span></span>
    
  - <span data-ttu-id="910b1-126">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="910b1-126">FileTransferAgent.exe</span></span>
    
  - <span data-ttu-id="910b1-127">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="910b1-127">HealthAgent.exe</span></span>
    
  - <span data-ttu-id="910b1-128">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="910b1-128">IMMCUSvc.exe</span></span>
    
  - <span data-ttu-id="910b1-129">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="910b1-129">LysSvc.exe</span></span>
    
  - <span data-ttu-id="910b1-130">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="910b1-130">MasterReplicatorAgent.exe</span></span>
    
  - <span data-ttu-id="910b1-131">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="910b1-131">MediaRelaySvc.exe</span></span>
    
  - <span data-ttu-id="910b1-132">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="910b1-132">MediationServerSvc.exe</span></span>
    
  - <span data-ttu-id="910b1-133">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="910b1-133">MRASSvc.exe</span></span>
    
  - <span data-ttu-id="910b1-134">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="910b1-134">OcsAppServerHost.exe</span></span>
    
  - <span data-ttu-id="910b1-135">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="910b1-135">ReplicaReplicatorAgent.exe</span></span>
    
  - <span data-ttu-id="910b1-136">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="910b1-136">ReplicationApp.exe</span></span>
    
  - <span data-ttu-id="910b1-137">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="910b1-137">RtcHost.exe</span></span>
    
  - <span data-ttu-id="910b1-138">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="910b1-138">RTCSrv.exe</span></span>
    
  - <span data-ttu-id="910b1-139">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="910b1-139">XmppProxy.exe</span></span>
    
  - <span data-ttu-id="910b1-140">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="910b1-140">XmppTGW.exe</span></span>
    
- <span data-ttu-id="910b1-141">Windows Fabric Host Service のプロセス:</span><span class="sxs-lookup"><span data-stu-id="910b1-141">Windows Fabric Host Service processes:</span></span>
    
  - <span data-ttu-id="910b1-142">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="910b1-142">Fabric.exe</span></span>
    
  - <span data-ttu-id="910b1-143">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="910b1-143">FabricDCA.exe</span></span>
    
  - <span data-ttu-id="910b1-144">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="910b1-144">FabricHost.exe</span></span>
    
- <span data-ttu-id="910b1-145">IIS のプロセス:</span><span class="sxs-lookup"><span data-stu-id="910b1-145">IIS processes:</span></span>
    
  - <span data-ttu-id="910b1-146">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="910b1-146">%systemroot%\system32\inetsrv\w3wp.exe</span></span>
    
  - <span data-ttu-id="910b1-147">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="910b1-147">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>
    
- <span data-ttu-id="910b1-148">SQL Server バックエンドのプロセス:</span><span class="sxs-lookup"><span data-stu-id="910b1-148">SQL Server Back-End processes:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="910b1-149">これらのパスは、SQL Server バージョン固有のパスです。</span><span class="sxs-lookup"><span data-stu-id="910b1-149">Note that these paths are specific to SQL Server version.</span></span> 
  
  - <span data-ttu-id="910b1-150">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="910b1-150">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>
    
  - <span data-ttu-id="910b1-151">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="910b1-151">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>
    
  - <span data-ttu-id="910b1-152">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="910b1-152">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>
    
- <span data-ttu-id="910b1-153">SQL Server フロントエンドのプロセス:</span><span class="sxs-lookup"><span data-stu-id="910b1-153">SQL Server Front-End processes:</span></span>
    
  - <span data-ttu-id="910b1-154">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="910b1-154">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>
    
  - <span data-ttu-id="910b1-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="910b1-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>
    
  - <span data-ttu-id="910b1-156">Standard Edition インストールの RTC インスタンス</span><span class="sxs-lookup"><span data-stu-id="910b1-156">Standard Edition Installation RTC Instance</span></span> 
    
  - <span data-ttu-id="910b1-157">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="910b1-157">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>
    
- <span data-ttu-id="910b1-158">ディレクトリとファイル:</span><span class="sxs-lookup"><span data-stu-id="910b1-158">Directories and files:</span></span>
    
  - <span data-ttu-id="910b1-159">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="910b1-159">%systemroot%\System32\LogFiles</span></span>
    
  - <span data-ttu-id="910b1-160">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="910b1-160">%systemroot%\SysWow64\LogFiles</span></span>
    
  - <span data-ttu-id="910b1-161">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="910b1-161">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>
    
  - <span data-ttu-id="910b1-162">%programfiles%\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="910b1-162">%programfiles%\Skype for Business Server 2015</span></span>
    
  - <span data-ttu-id="910b1-163">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span><span class="sxs-lookup"><span data-stu-id="910b1-163">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>
    
  - <span data-ttu-id="910b1-164">%programfiles%\Common Files\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="910b1-164">%programfiles%\Common Files\Skype for Business Server 2015</span></span>
    
  - <span data-ttu-id="910b1-165">%programfiles%\Common Files\Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="910b1-165">%programfiles%\Common Files\Skype for Business Online</span></span>
    
  - <span data-ttu-id="910b1-166">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="910b1-166">%SystemDrive%\RtcReplicaRoot</span></span>
    
  - <span data-ttu-id="910b1-p105">ファイル共有ストア (トポロジ ビルダーで指定)。ファイル ストアはトポロジ ビルダーで指定されています。</span><span class="sxs-lookup"><span data-stu-id="910b1-p105">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>
    
  - <span data-ttu-id="910b1-169">SQL Server のデータおよびログ ファイル (バックエンド データベース、ユーザー ストア、アーカイブ ストア、監視ストア、およびアプリケーション ストア用のものを含みます)。</span><span class="sxs-lookup"><span data-stu-id="910b1-169">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="910b1-170">データベースとログ ファイルは、トポロジ ビルダーで指定できます。</span><span class="sxs-lookup"><span data-stu-id="910b1-170">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="910b1-171">既定の名前を含む、各データベースのデータとログ ファイルの詳細については、展開に関するドキュメントで[SQL Server のデータとログ ファイルの配置](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="910b1-171">For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>
    
  - <span data-ttu-id="910b1-172">SQL Server データ ファイルとログ ファイル、Skype ビジネス ストア、および RtcDatabase のストアのフロント エンド データベースを含みます。</span><span class="sxs-lookup"><span data-stu-id="910b1-172">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="910b1-173">これらは通常、%localdrive%\CSData の下位にあります。</span><span class="sxs-lookup"><span data-stu-id="910b1-173">They are normally under %localdrive%\CSData.</span></span>
    

