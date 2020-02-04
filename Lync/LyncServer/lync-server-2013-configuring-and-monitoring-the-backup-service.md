---
title: 'Lync Server 2013: バックアップ サービスの構成と監視'
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
ms.openlocfilehash: 9992f0466ceb2e01fa54cb2b2d511eeb96af755a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-and-monitoring-the-backup-service-in-lync-server-2013"></a><span data-ttu-id="340ea-102">Lync Server 2013 でのバックアップ サービスの構成と監視</span><span class="sxs-lookup"><span data-stu-id="340ea-102">Configuring and monitoring the Backup Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="340ea-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="340ea-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="340ea-104">次の Lync Server 管理シェルコマンドを使用して、バックアップサービスの構成と監視を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="340ea-104">You can use the following Lync Server Management Shell commands to configure and monitor the Backup Service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="340ea-105">RTCUniversalServerAdmins グループは、既定で<STRONG>Get-CsBackupServiceStatus</STRONG>を実行する権限を持つ唯一のグループです。</span><span class="sxs-lookup"><span data-stu-id="340ea-105">The RTCUniversalServerAdmins group is the only group that has permissions to run <STRONG>Get-CsBackupServiceStatus</STRONG> by default.</span></span> <span data-ttu-id="340ea-106">このコマンドレットを使うには、このグループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="340ea-106">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="340ea-107">または、 <STRONG>CsBackupServiceConfiguration</STRONG>コマンドレットを使用して、このコマンドへのアクセス権を他のグループ (たとえば、csadministrator) に付与することができます。</span><span class="sxs-lookup"><span data-stu-id="340ea-107">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the <STRONG>Set-CsBackupServiceConfiguration</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="340ea-108">バックアップサービスの構成を確認するには</span><span class="sxs-lookup"><span data-stu-id="340ea-108">To see the Backup Service configuration</span></span>

<span data-ttu-id="340ea-109">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="340ea-109">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="340ea-110">SyncInterval の既定値は2分です。</span><span class="sxs-lookup"><span data-stu-id="340ea-110">The default for SyncInterval is two minutes.</span></span>

</div>

<div>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="340ea-111">バックアップサービスの同期間隔を設定するには</span><span class="sxs-lookup"><span data-stu-id="340ea-111">To set the Backup Service sync interval</span></span>

<span data-ttu-id="340ea-112">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="340ea-112">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="340ea-113">たとえば、次のように間隔を3分に設定します。</span><span class="sxs-lookup"><span data-stu-id="340ea-113">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00

<div>


> [!IMPORTANT]  
> <span data-ttu-id="340ea-114">バックアップサービスの既定の同期間隔を変更するには、このコマンドレットを使用できますが、同期間隔はバックアップサービスのパフォーマンスと回復ポイントの目標 (RPO) に大きな影響を与えるため、絶対に必要な場合以外は、この操作を行わないでください。</span><span class="sxs-lookup"><span data-stu-id="340ea-114">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>



</div>

</div>

<div>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="340ea-115">特定のプールのバックアップサービスの状態を取得するには</span><span class="sxs-lookup"><span data-stu-id="340ea-115">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="340ea-116">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="340ea-116">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

<div>


> [!NOTE]  
> <span data-ttu-id="340ea-117">バックアップサービスの同期状態は、プール (P1) からバックアッププール (P2) にまで1つずつ定義されています。</span><span class="sxs-lookup"><span data-stu-id="340ea-117">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="340ea-118">P1 から P2 への同期状態は、P2 から P1 までと異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="340ea-118">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="340ea-119">P1 から P2 の場合、P1 で行ったすべての変更が同期間隔で P2 に完全に複製されている場合、バックアップサービスは "定常" 状態になります。</span><span class="sxs-lookup"><span data-stu-id="340ea-119">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="340ea-120">P1 から P2 への同期が必要な変更がない場合は、"最終" 状態になります。</span><span class="sxs-lookup"><span data-stu-id="340ea-120">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="340ea-121">どちらの状態も、コマンドレットが実行された時点でのバックアップサービスのスナップショットを示します。</span><span class="sxs-lookup"><span data-stu-id="340ea-121">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="340ea-122">返される状態が後のままになるというわけではありません。</span><span class="sxs-lookup"><span data-stu-id="340ea-122">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="340ea-123">特に、コマンドレットが実行された後も、P1 が変更を生成しない場合に限り、"final" 状態が保持されます。</span><span class="sxs-lookup"><span data-stu-id="340ea-123">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="340ea-124">これは、p1 が<STRONG>CsPoolfailover</STRONG>実行ロジックの一部として読み取り専用モードに配置された後に、P1 を P2 に移行した場合に当てはまります。</span><span class="sxs-lookup"><span data-stu-id="340ea-124">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the <STRONG>Invoke-CsPoolfailover</STRONG> execution logic.</span></span>



</div>

</div>

<div>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="340ea-125">特定のプールのバックアップ関係に関する情報を取得するには</span><span class="sxs-lookup"><span data-stu-id="340ea-125">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="340ea-126">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="340ea-126">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

</div>

<div>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="340ea-127">バックアップサービスを強制的に同期するには</span><span class="sxs-lookup"><span data-stu-id="340ea-127">To force a Backup Service sync</span></span>

<span data-ttu-id="340ea-128">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="340ea-128">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

</div>

</div>

<span> </span>

</div>

</div>

</div>

