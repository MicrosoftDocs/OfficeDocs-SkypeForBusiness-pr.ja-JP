---
title: バックアップ サービスの構成と監視
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server 管理シェル コマンドを使用して、バックアップ サービスを構成および監視できます。
ms.openlocfilehash: d38c9d0b0261fb7e1da89b3422496d94307a791d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817197"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a><span data-ttu-id="202ce-103">Skype for Business Server でのバックアップ サービスの構成と監視</span><span class="sxs-lookup"><span data-stu-id="202ce-103">Configuring and monitoring the Backup Service in Skype for Business Server</span></span>

<span data-ttu-id="202ce-104">次の Skype for Business Server 管理シェル コマンドを使用して、バックアップ サービスを構成および監視できます。</span><span class="sxs-lookup"><span data-stu-id="202ce-104">You can use the following Skype for Business Server Management Shell commands to configure and monitor the Backup Service.</span></span> <span data-ttu-id="202ce-105">フロントエンド プールのファイル ストアに格納されている会議情報を復元するには、以下の「バックアップ サービスを使用して会議コンテンツを復元する [」](#restore-conference-contents-using-the-backup-service)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="202ce-105">To restore conference information stored in the file store of a Front End pool, see [Restore conference contents using the Backup Service](#restore-conference-contents-using-the-backup-service), below.</span></span>

> [!NOTE]  
> <span data-ttu-id="202ce-106">RTCUniversalServerAdmins グループは、既定で **Get-CsBackupServiceStatus** を実行する権限を持つ唯一のグループです。</span><span class="sxs-lookup"><span data-stu-id="202ce-106">The RTCUniversalServerAdmins group is the only group that has permissions to run **Get-CsBackupServiceStatus** by default.</span></span> <span data-ttu-id="202ce-107">このコマンドレットを使用するには、このグループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="202ce-107">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="202ce-108">また **、Set-CsBackupServiceConfiguration** コマンドレットを使用して、このコマンドへのアクセス権を他のグループ (CSAdministrator など) に付与することもできます。</span><span class="sxs-lookup"><span data-stu-id="202ce-108">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the **Set-CsBackupServiceConfiguration** cmdlet.</span></span>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="202ce-109">バックアップ サービスの構成を確認するには</span><span class="sxs-lookup"><span data-stu-id="202ce-109">To see the Backup Service configuration</span></span>

<span data-ttu-id="202ce-110">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="202ce-110">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="202ce-111">SyncInterval の既定値は 2 分です。</span><span class="sxs-lookup"><span data-stu-id="202ce-111">The default for SyncInterval is two minutes.</span></span>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="202ce-112">バックアップ サービスの同期間隔を設定するには</span><span class="sxs-lookup"><span data-stu-id="202ce-112">To set the Backup Service sync interval</span></span>

<span data-ttu-id="202ce-113">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="202ce-113">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="202ce-114">たとえば、次の例では間隔を 3 分に設定します。</span><span class="sxs-lookup"><span data-stu-id="202ce-114">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> <span data-ttu-id="202ce-115">このコマンドレットを使用してバックアップ サービスの既定の同期間隔を変更することもできますが、同期間隔はバックアップ サービスのパフォーマンスと目標復旧ポイント (RPO) に大きな影響を与えるので、絶対に必要な場合を限り変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="202ce-115">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="202ce-116">特定のプールのバックアップ サービスの状態を取得するには</span><span class="sxs-lookup"><span data-stu-id="202ce-116">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="202ce-117">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="202ce-117">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> <span data-ttu-id="202ce-118">バックアップ サービスの同期状態は、プール (P1) からバックアップ プール (P2) に一方向に定義されます。</span><span class="sxs-lookup"><span data-stu-id="202ce-118">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="202ce-119">P1 から P2 への同期状態は、P2 から P1 の同期状態とは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="202ce-119">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="202ce-120">P1 ~ P2 の場合、同期間隔内に P1 で行われたすべての変更が P2 に完全にレプリケートされる場合、バックアップ サービスは "安定" 状態になります。</span><span class="sxs-lookup"><span data-stu-id="202ce-120">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="202ce-121">P1 から P2 に同期する変更がこれ以上ない場合は、最終的な状態になります。</span><span class="sxs-lookup"><span data-stu-id="202ce-121">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="202ce-122">どちらの状態も、コマンドレットが実行された時点でのバックアップ サービスのスナップショットを示します。</span><span class="sxs-lookup"><span data-stu-id="202ce-122">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="202ce-123">返された状態が後の状態にとどまるというのではありません。</span><span class="sxs-lookup"><span data-stu-id="202ce-123">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="202ce-124">特に、"final" 状態は、コマンドレットの実行後に P1 が変更を生成しない場合にのみ保持されます。</span><span class="sxs-lookup"><span data-stu-id="202ce-124">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="202ce-125">これは **、Invoke-CsPoolfailover** 実行ロジックの一部として P1 を読み取り専用モードにした後に P1 を P2 にフェールオーバーする場合に当てはまる場合です。</span><span class="sxs-lookup"><span data-stu-id="202ce-125">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the **Invoke-CsPoolfailover** execution logic.</span></span>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="202ce-126">特定のプールのバックアップ関係に関する情報を取得するには</span><span class="sxs-lookup"><span data-stu-id="202ce-126">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="202ce-127">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="202ce-127">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="202ce-128">バックアップ サービスの同期を強制するには</span><span class="sxs-lookup"><span data-stu-id="202ce-128">To force a Backup Service sync</span></span>

<span data-ttu-id="202ce-129">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="202ce-129">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a><span data-ttu-id="202ce-130">バックアップ サービスを使用して会議コンテンツを復元する</span><span class="sxs-lookup"><span data-stu-id="202ce-130">Restore conference contents using the Backup Service</span></span> 

<span data-ttu-id="202ce-131">フロント エンド プールのファイル ストアに格納されている会議情報が使用できなくなった場合は、プールに格納されているユーザーが会議データを保持するためにこの情報を復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="202ce-131">If the conference information stored in the file store of a Front End pool becomes unavailable, you must restore this information so that users homed on the pool retain their conference data.</span></span> <span data-ttu-id="202ce-132">会議データを失ったフロントエンド プールと他のフロントエンド プールがペアになっている場合は、バックアップ サービスを使用してデータを復元できます。</span><span class="sxs-lookup"><span data-stu-id="202ce-132">If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="202ce-p105">プール全体で障害が発生し、ユーザーをバックアップ プールにフェールオーバーする必要がある場合も、このタスクを実行します。これらのユーザーが元のプールにフェールオーバーされるときに、この手順を使用して、会議コンテンツも元のプールにコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="202ce-p105">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool. When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="202ce-135">Pool1 と Pool2 がペアで、Pool1 の会議データが失われたとします。</span><span class="sxs-lookup"><span data-stu-id="202ce-135">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="202ce-136">次のコマンドレットを使用して、バックアップ サービスを呼び出してコンテンツを復元できます。</span><span class="sxs-lookup"><span data-stu-id="202ce-136">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="202ce-p107">会議コンテンツのサイズによっては、コンテンツを復元するのに時間がかかる場合があります。次のコマンドレットを使用すると、プロセスの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="202ce-p107">Restoring the conference contents may take some time, depending on their size. You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="202ce-139">このコマンドレットがデータ会議モジュールに対して安定状態の値を返すと、プロセスは完了です。</span><span class="sxs-lookup"><span data-stu-id="202ce-139">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>
