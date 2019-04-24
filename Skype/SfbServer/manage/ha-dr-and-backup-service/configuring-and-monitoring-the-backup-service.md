---
title: バックアップ サービスの構成と監視
ms.reviewer: ''
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype ビジネス サーバー管理シェル コマンドを使用するにを構成し、バックアップ サービスを監視します。
ms.openlocfilehash: 3a41caecb4e123505da2d529ea74c22a5d0e28e7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199878"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a><span data-ttu-id="4b40b-103">構成して、Skype でバックアップ サービスをビジネス サーバーの監視</span><span class="sxs-lookup"><span data-stu-id="4b40b-103">Configuring and monitoring the Backup Service in Skype for Business Server</span></span>

<span data-ttu-id="4b40b-104">ビジネス サーバー管理シェル コマンドの次の Skype を使用するには構成し、バックアップ サービスを監視します。</span><span class="sxs-lookup"><span data-stu-id="4b40b-104">You can use the following Skype for Business Server Management Shell commands to configure and monitor the Backup Service.</span></span> <span data-ttu-id="4b40b-105">フロント エンド プールのファイル ストアに格納されている会議の情報を復元するには、下[バックアップ サービスを使用して会議の内容を復元](#restore-conference-contents-using-the-backup-service)するにはを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b40b-105">To restore conference information stored in the file store of a Front End pool, see [Restore conference contents using the Backup Service](#restore-conference-contents-using-the-backup-service), below.</span></span>

> [!NOTE]  
> <span data-ttu-id="4b40b-106">RTCUniversalServerAdmins グループは、既定では、 **Get CsBackupServiceStatus**を実行するアクセス許可を持つ唯一のグループです。</span><span class="sxs-lookup"><span data-stu-id="4b40b-106">The RTCUniversalServerAdmins group is the only group that has permissions to run **Get-CsBackupServiceStatus** by default.</span></span> <span data-ttu-id="4b40b-107">このコマンドレットを使用するには、このグループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="4b40b-107">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="4b40b-108">または、**セット CsBackupServiceConfiguration**コマンドレットを使用して他のグループ (たとえば、CSAdministrator) に次のコマンドへのアクセス権を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="4b40b-108">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the **Set-CsBackupServiceConfiguration** cmdlet.</span></span>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="4b40b-109">バックアップ サービス構成を確認するには</span><span class="sxs-lookup"><span data-stu-id="4b40b-109">To see the Backup Service configuration</span></span>

<span data-ttu-id="4b40b-110">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="4b40b-110">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="4b40b-111">SyncInterval の既定値は、2 つ分です。</span><span class="sxs-lookup"><span data-stu-id="4b40b-111">The default for SyncInterval is two minutes.</span></span>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="4b40b-112">バックアップ サービスの同期間隔を設定するのには</span><span class="sxs-lookup"><span data-stu-id="4b40b-112">To set the Backup Service sync interval</span></span>

<span data-ttu-id="4b40b-113">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="4b40b-113">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="4b40b-114">など、次の間隔を設定 3 分です。</span><span class="sxs-lookup"><span data-stu-id="4b40b-114">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> <span data-ttu-id="4b40b-115">バックアップ サービスの既定の同期間隔を変更するのには、このコマンドレットを使用できますを使用しないので、絶対に必要である限り、同期間隔が、バックアップ サービスのパフォーマンスと、目標復旧時点 (RPO) に大きな影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="4b40b-115">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="4b40b-116">特定のプールに対するバックアップ サービスの状態を取得するには</span><span class="sxs-lookup"><span data-stu-id="4b40b-116">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="4b40b-117">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="4b40b-117">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> <span data-ttu-id="4b40b-118">(P2) のバックアップのプールに、プール (P1) から、unidirectionally バックアップ サービスの同期の状態が定義されます。</span><span class="sxs-lookup"><span data-stu-id="4b40b-118">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="4b40b-119">同期状態を P1 から P2 を P1 を P2 からとは異なることができます。</span><span class="sxs-lookup"><span data-stu-id="4b40b-119">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="4b40b-120">P2 を P1、バックアップ サービスは「安定」状態で P1 で行われたすべての変更が完全にレプリケートされている場合 P2 に同期間隔内でします。</span><span class="sxs-lookup"><span data-stu-id="4b40b-120">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="4b40b-121">状態になって、"final"がある場合は、P1 と P2 を同期する変更です。</span><span class="sxs-lookup"><span data-stu-id="4b40b-121">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="4b40b-122">両方の状態は、コマンドレットの実行時に、バックアップ サービスのスナップショットを示しています。</span><span class="sxs-lookup"><span data-stu-id="4b40b-122">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="4b40b-123">その後は、返された状態のままとは限りません。</span><span class="sxs-lookup"><span data-stu-id="4b40b-123">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="4b40b-124">具体的には、「最後」の状態が引き続きかどうか P1 は生成されません、変更、コマンドレットが実行された後にのみ保持されます。</span><span class="sxs-lookup"><span data-stu-id="4b40b-124">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="4b40b-125">フェールオーバー P1 P2 を P1 が読み取り専用モードに**呼び出し CsPoolfailover**実行ロジックの一部として配置された後の場合も同様です。</span><span class="sxs-lookup"><span data-stu-id="4b40b-125">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the **Invoke-CsPoolfailover** execution logic.</span></span>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="4b40b-126">特定のプールに対するバックアップの関係についての情報を取得するには</span><span class="sxs-lookup"><span data-stu-id="4b40b-126">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="4b40b-127">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="4b40b-127">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="4b40b-128">バックアップ サービスの同期を強制するには</span><span class="sxs-lookup"><span data-stu-id="4b40b-128">To force a Backup Service sync</span></span>

<span data-ttu-id="4b40b-129">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="4b40b-129">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a><span data-ttu-id="4b40b-130">バックアップ サービスを使用して会議の内容を復元します。</span><span class="sxs-lookup"><span data-stu-id="4b40b-130">Restore conference contents using the Backup Service</span></span> 

<span data-ttu-id="4b40b-131">できるように、ユーザーのホーム プールに、この情報を復元する必要がありますフロント エンド プールのファイル ストアに格納されている会議の情報が使用できなくなった場合、会議のデータを保持します。</span><span class="sxs-lookup"><span data-stu-id="4b40b-131">If the conference information stored in the file store of a Front End pool becomes unavailable, you must restore this information so that users homed on the pool retain their conference data.</span></span> <span data-ttu-id="4b40b-132">会議のデータが失われたが、フロント エンド プールは、別のフロント エンド プールと共に場合、は、データを復元するバックアップ サービスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4b40b-132">If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="4b40b-133">プール全体が障害が発生し、バックアップ ・ プールには、そのユーザーがフェールオーバーする必要がある場合にも、このタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b40b-133">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool.</span></span> <span data-ttu-id="4b40b-134">これらのユーザーは、フェールバック、元のプールにときにも、元のプールに、会議のコンテンツをコピーするのにはこの手順を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b40b-134">When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="4b40b-135">Pool1、Pool2 とペアにし、Pool1 に会議のデータは失われますことを想定しています。</span><span class="sxs-lookup"><span data-stu-id="4b40b-135">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="4b40b-136">内容を復元するのにバックアップ サービスの起動には、次のコマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4b40b-136">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="4b40b-137">会議の内容を復元すると、そのサイズによっては、時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4b40b-137">Restoring the conference contents may take some time, depending on their size.</span></span> <span data-ttu-id="4b40b-138">次のコマンドレットを使用して、プロセスの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="4b40b-138">You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="4b40b-139">プロセスは、このコマンドレットは、データ会議モジュールの定常状態の値を返す場合に行われます。</span><span class="sxs-lookup"><span data-stu-id="4b40b-139">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>
