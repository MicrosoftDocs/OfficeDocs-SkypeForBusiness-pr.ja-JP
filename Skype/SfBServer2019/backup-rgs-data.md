---
title: Skype for Business Server 2019 での応答グループサービス (RGS) データのバックアップ
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: Skype for Business Server 2019 で応答グループサービス (RGS) データをバックアップする方法について説明します。
ms.openlocfilehash: f9c62953dcb859be2aa34bdee84ca76e3303d738
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824071"
---
# <a name="back-up-response-group-service-rgs-data"></a><span data-ttu-id="5a16c-103">応答グループサービス (RGS) データをバックアップする</span><span class="sxs-lookup"><span data-stu-id="5a16c-103">Back up Response Group Service (RGS) data</span></span>

<span data-ttu-id="5a16c-104">Skype for Business Server 2019 年7月の累積更新プログラムでは、標準バックアップの一部として RGS データを含める機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5a16c-104">With the Skype for Business Server 2019 July cumulative update, we’ve included the ability to include RGS data as part of the standard backup.</span></span>

## <a name="rgs-data-replication"></a><span data-ttu-id="5a16c-105">RGS データレプリケーション</span><span class="sxs-lookup"><span data-stu-id="5a16c-105">RGS data replication</span></span>

<span data-ttu-id="5a16c-106">RG データレプリケーション機能を試すには、次の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="5a16c-106">To try RGS data replication functionality, please follow the steps below:</span></span>

1. <span data-ttu-id="5a16c-107">ペアリングされたプールのすべてのフロントエンド (FEs) に、7月の累積更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5a16c-107">Install the July cumulative update on all front-ends (FEs) of your paired pool.</span></span>
1. <span data-ttu-id="5a16c-108">ペアリングされたプールの両方のメンバーに RGS データベースをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5a16c-108">Install the RGS database on both members of the paired pool:</span></span>
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool1 BackendDatabase FQDN>`
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool2 BackendDatabase FQDN>`
1. <span data-ttu-id="5a16c-109">次のコマンドレットを両方のプールで実行して、RGSBackupService でデータを取得できるように、既存の RGS データをバックアップテーブルに複製します。</span><span class="sxs-lookup"><span data-stu-id="5a16c-109">Run the following cmdlet on both pools to replicate existing RGS Data to the backup tables so that the data can be picked up by RGSBackupService:</span></span>
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool1 FQDN>`
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool2 FQDN>`
1. <span data-ttu-id="5a16c-110">RGSBackupService を有効にします (これにより RGSBackupService がグローバルに有効になります。</span><span class="sxs-lookup"><span data-stu-id="5a16c-110">Enable RGSBackupService (This will enable RGSBackupService globally.</span></span> <span data-ttu-id="5a16c-111">このパラメーターが true に設定されている場合は、RGSBackupService によってペアプール上の RG データの同期が開始されます (どちらのプールも CU1 である必要があります)。</span><span class="sxs-lookup"><span data-stu-id="5a16c-111">If this parameter is set to true , RGSBackupService will start syncing RGS data on paired pools (both pools needs to be CU1).</span></span> <span data-ttu-id="5a16c-112">数分待ってから開始してください。</span><span class="sxs-lookup"><span data-stu-id="5a16c-112">Wait for a few minutes to get it started.</span></span> <span data-ttu-id="5a16c-113">最初に、RGS BackupService の状態は初期化されません。):</span><span class="sxs-lookup"><span data-stu-id="5a16c-113">Initially, RGS BackupService status will be NotInitialized.):</span></span>
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 1`
1. <span data-ttu-id="5a16c-114">BackupServiceStatus を確認するには:</span><span class="sxs-lookup"><span data-stu-id="5a16c-114">To check BackupServiceStatus:</span></span>
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
1. <span data-ttu-id="5a16c-115">プール間で DataReplication を確認するには、次のコマンドレットを使用します (これらのコマンドレットは、所有者プールデータのみを示します)。</span><span class="sxs-lookup"><span data-stu-id="5a16c-115">To check DataReplication across pools, use these cmdlets (These cmdlets show only owner pool data):</span></span>
    - `Get-csRGSWorkflow`
    - `Get-csRGSQueue`
    - `Get-csRGSAgentGroup`
    - `Get-csRGSHourOfBusiness`
    - `Get-csRGSHolidaySet`
1. <span data-ttu-id="5a16c-116">所有者プール RG データとそのバックアップデータを確認するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5a16c-116">To check Owner pool RGS data and its backup data:</span></span>
    - `Get-csRGSWorkflow -showAll`
    - `Get-csRGSQueue  -showAll`
    - `Get-csRGSAgentGroup -showAll`
    - `Get-csRGSHourOfBusiness -showAll`
    - `Get-csRGSHolidaySet -showAll`
1. <span data-ttu-id="5a16c-117">ワークフローへの音声通話を行うことによってワークフローの機能を確認します。</span><span class="sxs-lookup"><span data-stu-id="5a16c-117">Verify workflow functionality by making an audio call to Workflow.</span></span>
1. <span data-ttu-id="5a16c-118">RG 所有者プールをフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="5a16c-118">Failover your RGS Owner pool.</span></span>
1. <span data-ttu-id="5a16c-119">ワークフローへの音声通話を行うことによってワークフローの機能を確認します。</span><span class="sxs-lookup"><span data-stu-id="5a16c-119">Verify workflow functionality by making an audio call to Workflow.</span></span>
1. <span data-ttu-id="5a16c-120">プールをフェイルバックします。</span><span class="sxs-lookup"><span data-stu-id="5a16c-120">Failback the pool.</span></span>
1. <span data-ttu-id="5a16c-121">ソースプールの RGS データを更新し、別のフェールオーバーを実行して、変更がバックアッププールに反映されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5a16c-121">Update RGS Data on source pool and perform another failover to check that changes are reflected on backup pool.</span></span> <span data-ttu-id="5a16c-122">RGS は、フェールオーバー前に動作していたときと同じように動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a16c-122">RGS should behave in same way as it was behaving before failover.</span></span>

> [!TIP]
> <span data-ttu-id="5a16c-123">これらの手順は大量のデータに対して実行することをお勧めし、フェールオーバーと failbacks を頻繁に行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5a16c-123">It is recommended you perform these steps on a bulk of data and do frequent failover and failbacks.</span></span> <span data-ttu-id="5a16c-124">この CU 更新後に作成されたすべての新しい RG も複製する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a16c-124">Any new RGS created after this CU update should also be replicated.</span></span>

## <a name="rgs-cmdlets"></a><span data-ttu-id="5a16c-125">RGS コマンドレット</span><span class="sxs-lookup"><span data-stu-id="5a16c-125">RGS cmdlets</span></span>

- <span data-ttu-id="5a16c-126">BackupServiceStatus を確認するには、エクスポートの状態が最終または定常状態である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a16c-126">To check BackupServiceStatus (The export status should be in the Final or Steady state.</span></span> <span data-ttu-id="5a16c-127">インポートの状態は、通常の状態である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a16c-127">The import status should be in the Normal state.</span></span> <span data-ttu-id="5a16c-128">RGSBackupservice を有効にする必要があります。):</span><span class="sxs-lookup"><span data-stu-id="5a16c-128">RGSBackupservice should be enabled.):</span></span>
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
- <span data-ttu-id="5a16c-129">バックアッププールの RGS データを完全に同期するには (これにより、バックアッププール上の完全な RGS データが同期されます):</span><span class="sxs-lookup"><span data-stu-id="5a16c-129">To Fully Sync RGS Data on the backup pool (This will sync the full RGS data on the backup pool.):</span></span>
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSDataStore`
- <span data-ttu-id="5a16c-130">バックアッププールの RGS filestore を完全に同期するには (これにより、バックアッププール上の完全な RG データが同期されます):</span><span class="sxs-lookup"><span data-stu-id="5a16c-130">To Fully Sync the RGS filestore on the backup pool (This will sync the full RGS data on the backup pool.):</span></span>
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSFileStore`
- <span data-ttu-id="5a16c-131">バックアッププール上の RGS デルタデータを同期するには (これにより、RG のバックアッププールの差分データのみが同期されます):</span><span class="sxs-lookup"><span data-stu-id="5a16c-131">To Sync RGS delta data on the backup pool (This will sync delta data on backup pool for RGS only.):</span></span>
    - `Backup-CsPool -PoolFqdn <Pool FQDN> -Category RGS`
- <span data-ttu-id="5a16c-132">RGS を含むすべてのモジュールデータを同期するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5a16c-132">To sync all module data including RGS:</span></span>
    - `Backup-CsPool -PoolFqdn <Pool FQDN>`
- <span data-ttu-id="5a16c-133">RGSBackupService を無効にするには、RGSBackupService をグローバルに無効にします。</span><span class="sxs-lookup"><span data-stu-id="5a16c-133">To disable RGSBackupService (This will disable RGSBackupService globally.</span></span> <span data-ttu-id="5a16c-134">このパラメーターが true に設定されている場合、RGSBackupService はすべてのペアプールで無効になります。):</span><span class="sxs-lookup"><span data-stu-id="5a16c-134">If this parameter is set to true , RGSBackupService will be disabled on all paired pools.):</span></span>
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 0`
