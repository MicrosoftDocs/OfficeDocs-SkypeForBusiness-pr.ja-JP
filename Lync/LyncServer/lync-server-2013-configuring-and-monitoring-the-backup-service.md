---
title: 'Lync Server 2013: バックアップサービスの構成と監視'
description: 'Lync Server 2013: バックアップサービスの構成と監視。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring and monitoring the Backup Service
ms:assetid: c608280e-a7d1-4ae0-a75c-da6b524752fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205252(v=OCS.15)
ms:contentKeyID: 48185365
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35302aeb430e8591babd88969d4c5c158c1ac0bf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574643"
---
# <a name="configuring-and-monitoring-the-backup-service-in-lync-server-2013"></a><span data-ttu-id="e8564-103">Lync Server 2013 でのバックアップサービスの構成と監視</span><span class="sxs-lookup"><span data-stu-id="e8564-103">Configuring and monitoring the Backup Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8564-104">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e8564-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e8564-105">次の Lync Server 管理シェルコマンドを使用して、バックアップサービスの構成と監視を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e8564-105">You can use the following Lync Server Management Shell commands to configure and monitor the Backup Service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e8564-106">RTCUniversalServerAdmins グループは、既定で <STRONG>get-csbackupservicestatus</STRONG> を実行するためのアクセス許可を持つ唯一のグループです。</span><span class="sxs-lookup"><span data-stu-id="e8564-106">The RTCUniversalServerAdmins group is the only group that has permissions to run <STRONG>Get-CsBackupServiceStatus</STRONG> by default.</span></span> <span data-ttu-id="e8564-107">このコマンドレットを使用するには、このグループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="e8564-107">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="e8564-108">または、 <STRONG>get-csbackupserviceconfiguration</STRONG> コマンドレットを使用して、このコマンドへのアクセスを他のグループ (たとえば、csadministrator) に付与することもできます。</span><span class="sxs-lookup"><span data-stu-id="e8564-108">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the <STRONG>Set-CsBackupServiceConfiguration</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="e8564-109">バックアップサービスの構成を表示するには</span><span class="sxs-lookup"><span data-stu-id="e8564-109">To see the Backup Service configuration</span></span>

<span data-ttu-id="e8564-110">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e8564-110">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="e8564-111">SyncInterval の既定値は2分です。</span><span class="sxs-lookup"><span data-stu-id="e8564-111">The default for SyncInterval is two minutes.</span></span>

</div>

<div>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="e8564-112">バックアップサービスの同期間隔を設定するには</span><span class="sxs-lookup"><span data-stu-id="e8564-112">To set the Backup Service sync interval</span></span>

<span data-ttu-id="e8564-113">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e8564-113">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="e8564-114">たとえば、次のように指定すると間隔が3分に設定されます。</span><span class="sxs-lookup"><span data-stu-id="e8564-114">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e8564-115">バックアップサービスの既定の同期間隔を変更するには、このコマンドレットを使用できますが、同期間隔は、バックアップサービスのパフォーマンスおよび目標復旧時点 (RPO) に大きく影響するため、絶対に必要でない限り、このコマンドレットは実行しないでください。</span><span class="sxs-lookup"><span data-stu-id="e8564-115">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>



</div>

</div>

<div>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="e8564-116">特定のプールのバックアップサービスの状態を取得するには</span><span class="sxs-lookup"><span data-stu-id="e8564-116">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="e8564-117">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e8564-117">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

<div>


> [!NOTE]  
> <span data-ttu-id="e8564-118">バックアップサービスの同期状態は、プール (P1) からそのバックアッププール (P2) に対して、unidirectionally に定義されています。</span><span class="sxs-lookup"><span data-stu-id="e8564-118">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="e8564-119">P1 から P2 への同期の状態は、P2 から P1 までのものと異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e8564-119">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="e8564-120">P1 から P2 では、P1 で行われたすべての変更が同期間隔内に P2 に完全にレプリケートされると、バックアップサービスは "安定した" 状態になります。</span><span class="sxs-lookup"><span data-stu-id="e8564-120">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="e8564-121">これは、P1 から P2 への同期を変更しない場合、"最終" 状態になります。</span><span class="sxs-lookup"><span data-stu-id="e8564-121">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="e8564-122">両方の状態は、コマンドレットが実行された時点でのバックアップサービスのスナップショットを示しています。</span><span class="sxs-lookup"><span data-stu-id="e8564-122">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="e8564-123">返される状態が後のままになることを意味するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="e8564-123">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="e8564-124">特に、"final" 状態は、コマンドレットの実行後に P1 が変更を生成しない場合にのみ保持されます。</span><span class="sxs-lookup"><span data-stu-id="e8564-124">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="e8564-125">これは、p1 が <STRONG>initialize-cspoolfailover</STRONG> 実行ロジックの一部として読み取り専用モードに配置された後に、P1 を P2 にフェールオーバーする場合に当てはまります。</span><span class="sxs-lookup"><span data-stu-id="e8564-125">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the <STRONG>Invoke-CsPoolfailover</STRONG> execution logic.</span></span>



</div>

</div>

<div>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="e8564-126">特定のプールに対するバックアップ関係に関する情報を取得するには</span><span class="sxs-lookup"><span data-stu-id="e8564-126">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="e8564-127">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e8564-127">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

</div>

<div>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="e8564-128">バックアップサービスの同期を強制的に実行するには</span><span class="sxs-lookup"><span data-stu-id="e8564-128">To force a Backup Service sync</span></span>

<span data-ttu-id="e8564-129">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e8564-129">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

</div>

</div>

<span> </span>

</div>

</div>

</div>

