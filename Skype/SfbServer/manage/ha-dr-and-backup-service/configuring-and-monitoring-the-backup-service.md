---
title: バックアップ サービスの構成と監視
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server 管理シェルコマンドを使用して、バックアップサービスの構成と監視を行うことができます。
ms.openlocfilehash: 80b15b2306807fe5bfc36449e16953466e3af75c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818218"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a><span data-ttu-id="5a7a1-103">Skype for Business Server のバックアップサービスの構成と監視</span><span class="sxs-lookup"><span data-stu-id="5a7a1-103">Configuring and monitoring the Backup Service in Skype for Business Server</span></span>

<span data-ttu-id="5a7a1-104">次の Skype for Business Server 管理シェルコマンドを使用して、バックアップサービスの構成と監視を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5a7a1-104">You can use the following Skype for Business Server Management Shell commands to configure and monitor the Backup Service.</span></span> <span data-ttu-id="5a7a1-105">フロントエンドプールのファイルストアに保存されている会議情報を復元するには、下記の「[バックアップサービスを使って会議コンテンツを復元](#restore-conference-contents-using-the-backup-service)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a7a1-105">To restore conference information stored in the file store of a Front End pool, see [Restore conference contents using the Backup Service](#restore-conference-contents-using-the-backup-service), below.</span></span>

> [!NOTE]  
> <span data-ttu-id="5a7a1-106">RTCUniversalServerAdmins グループは、既定で**Get-CsBackupServiceStatus**を実行する権限を持つ唯一のグループです。</span><span class="sxs-lookup"><span data-stu-id="5a7a1-106">The RTCUniversalServerAdmins group is the only group that has permissions to run **Get-CsBackupServiceStatus** by default.</span></span> <span data-ttu-id="5a7a1-107">このコマンドレットを使うには、このグループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="5a7a1-107">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="5a7a1-108">または、 **CsBackupServiceConfiguration**コマンドレットを使用して、このコマンドへのアクセス権を他のグループ (たとえば、csadministrator) に付与することができます。</span><span class="sxs-lookup"><span data-stu-id="5a7a1-108">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the **Set-CsBackupServiceConfiguration** cmdlet.</span></span>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="5a7a1-109">バックアップサービスの構成を確認するには</span><span class="sxs-lookup"><span data-stu-id="5a7a1-109">To see the Backup Service configuration</span></span>

<span data-ttu-id="5a7a1-110">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a7a1-110">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="5a7a1-111">SyncInterval の既定値は2分です。</span><span class="sxs-lookup"><span data-stu-id="5a7a1-111">The default for SyncInterval is two minutes.</span></span>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="5a7a1-112">バックアップサービスの同期間隔を設定するには</span><span class="sxs-lookup"><span data-stu-id="5a7a1-112">To set the Backup Service sync interval</span></span>

<span data-ttu-id="5a7a1-113">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a7a1-113">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="5a7a1-114">たとえば、次のように間隔を3分に設定します。</span><span class="sxs-lookup"><span data-stu-id="5a7a1-114">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> <span data-ttu-id="5a7a1-115">バックアップサービスの既定の同期間隔を変更するには、このコマンドレットを使用できますが、同期間隔はバックアップサービスのパフォーマンスと回復ポイントの目標 (RPO) に大きな影響を与えるため、絶対に必要な場合以外は、この操作を行わないでください。</span><span class="sxs-lookup"><span data-stu-id="5a7a1-115">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="5a7a1-116">特定のプールのバックアップサービスの状態を取得するには</span><span class="sxs-lookup"><span data-stu-id="5a7a1-116">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="5a7a1-117">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a7a1-117">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> <span data-ttu-id="5a7a1-118">バックアップサービスの同期状態は、プール (P1) からバックアッププール (P2) にまで1つずつ定義されています。</span><span class="sxs-lookup"><span data-stu-id="5a7a1-118">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="5a7a1-119">P1 から P2 への同期状態は、P2 から P1 までと異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5a7a1-119">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="5a7a1-120">P1 から P2 の場合、P1 で行ったすべての変更が同期間隔で P2 に完全に複製されている場合、バックアップサービスは "定常" 状態になります。</span><span class="sxs-lookup"><span data-stu-id="5a7a1-120">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="5a7a1-121">P1 から P2 への同期が必要な変更がない場合は、"最終" 状態になります。</span><span class="sxs-lookup"><span data-stu-id="5a7a1-121">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="5a7a1-122">どちらの状態も、コマンドレットが実行された時点でのバックアップサービスのスナップショットを示します。</span><span class="sxs-lookup"><span data-stu-id="5a7a1-122">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="5a7a1-123">返される状態が後のままになるというわけではありません。</span><span class="sxs-lookup"><span data-stu-id="5a7a1-123">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="5a7a1-124">特に、コマンドレットが実行された後も、P1 が変更を生成しない場合に限り、"final" 状態が保持されます。</span><span class="sxs-lookup"><span data-stu-id="5a7a1-124">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="5a7a1-125">これは、p1 が**CsPoolfailover**実行ロジックの一部として読み取り専用モードに配置された後に、P1 を P2 に移行した場合に当てはまります。</span><span class="sxs-lookup"><span data-stu-id="5a7a1-125">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the **Invoke-CsPoolfailover** execution logic.</span></span>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="5a7a1-126">特定のプールのバックアップ関係に関する情報を取得するには</span><span class="sxs-lookup"><span data-stu-id="5a7a1-126">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="5a7a1-127">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a7a1-127">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="5a7a1-128">バックアップサービスを強制的に同期するには</span><span class="sxs-lookup"><span data-stu-id="5a7a1-128">To force a Backup Service sync</span></span>

<span data-ttu-id="5a7a1-129">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a7a1-129">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a><span data-ttu-id="5a7a1-130">バックアップサービスを使用して会議のコンテンツを復元する</span><span class="sxs-lookup"><span data-stu-id="5a7a1-130">Restore conference contents using the Backup Service</span></span> 

<span data-ttu-id="5a7a1-131">フロントエンドプールのファイルストアに保存されている会議情報が利用できなくなった場合は、この情報を復元して、プールに所属しているユーザーが会議データを保持するようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a7a1-131">If the conference information stored in the file store of a Front End pool becomes unavailable, you must restore this information so that users homed on the pool retain their conference data.</span></span> <span data-ttu-id="5a7a1-132">会議データを紛失したフロントエンドプールが別のフロントエンドプールとペアリングされている場合は、バックアップサービスを使ってデータを復元することができます。</span><span class="sxs-lookup"><span data-stu-id="5a7a1-132">If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="5a7a1-133">また、プール全体で障害が発生し、ユーザーがバックアッププールにフェールオーバーしなければならない場合は、このタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a7a1-133">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool.</span></span> <span data-ttu-id="5a7a1-134">これらのユーザーが元のプールにフェールバックされた場合は、この手順を使用して、会議のコンテンツを元のプールにもコピーし直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a7a1-134">When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="5a7a1-135">Pool1 が Pool2 とペアリングされていることを前提としていますが、Pool1 の会議データは失われます。</span><span class="sxs-lookup"><span data-stu-id="5a7a1-135">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="5a7a1-136">次のコマンドレットを使用して、バックアップサービスを呼び出して内容を復元できます。</span><span class="sxs-lookup"><span data-stu-id="5a7a1-136">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="5a7a1-137">会議の内容の復元には、サイズによっては時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5a7a1-137">Restoring the conference contents may take some time, depending on their size.</span></span> <span data-ttu-id="5a7a1-138">プロセスの状態を確認するには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="5a7a1-138">You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="5a7a1-139">プロセスは、このコマンドレットがデータ会議モジュールの安定した状態の値を返すときに実行されます。</span><span class="sxs-lookup"><span data-stu-id="5a7a1-139">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>
