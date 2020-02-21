---
title: 'Lync Server 2013: 障害復旧時にグループ通話ピックアップを管理する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage Group Call Pickup during disaster recovery
ms:assetid: 2d32f19f-c649-4a72-a4fb-edd338e3a7cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945618(v=OCS.15)
ms:contentKeyID: 51541455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f58894a00c853f04d5d4c6f995edc17683b12e9f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42218253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manage-group-call-pickup-during-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="0df48-102">Lync Server 2013 での障害復旧時のグループ通話ピックアップの管理</span><span class="sxs-lookup"><span data-stu-id="0df48-102">Manage Group Call Pickup during disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0df48-103">_**トピックの最終更新日:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="0df48-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="0df48-104">予期しないインシデントが発生したためにフロントエンドプールが使用できなくなった場合、サービスはバックアッププールにフェールオーバーされます。</span><span class="sxs-lookup"><span data-stu-id="0df48-104">When a Front End pool becomes unavailable due an unplanned incident, service is failed over to the backup pool.</span></span> <span data-ttu-id="0df48-105">バックアッププールへのフェールオーバー中に、ユーザーはバックアッププールにリダイレクトされ、復元モードになります。</span><span class="sxs-lookup"><span data-stu-id="0df48-105">During failover to the backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="0df48-106">復元モードでは、ユーザーは他のユーザーの通話を選択したり、他のユーザーがその通話を選択したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="0df48-106">While in resiliency mode, users cannot pick up other users' calls or have their calls picked up by other users.</span></span> <span data-ttu-id="0df48-107">フェールオーバーが完了すると、ユーザーは通常どおりグループ通話ピックアップを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="0df48-107">When failover is complete, users can again use Group Call Pickup as usual.</span></span>

<span data-ttu-id="0df48-108">プライマリプールへのフェールバック時に、ユーザーはプライマリプールにリダイレクトされ、再び復元モードになります。</span><span class="sxs-lookup"><span data-stu-id="0df48-108">During failback to the primary pool, users are redirected to the primary pool and are again in resiliency mode.</span></span> <span data-ttu-id="0df48-109">グループ通話ピックアップ機能は、ユーザーが復元モードを終了するまで使用できません。</span><span class="sxs-lookup"><span data-stu-id="0df48-109">Group Call Pickup functionality is not available until the users are out of resiliency mode.</span></span>

<span data-ttu-id="0df48-110">このセクションでは、障害復旧時のグループ通話ピックアップと、ユーザー環境についての考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="0df48-110">This section discusses some considerations for Group Call Pickup during disaster recovery and also describes the user experience.</span></span>

<div>

## <a name="considerations-for-group-call-pickup-during-disaster-recovery"></a><span data-ttu-id="0df48-111">障害復旧時のグループ通話ピックアップに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="0df48-111">Considerations for Group Call Pickup During Disaster Recovery</span></span>

<span data-ttu-id="0df48-112">障害復旧時に、フェールオーバープロセスの一環としてバックアッププールにリダイレクトされたユーザーは、通話ピックアップグループ番号のバックアッププールで実行されているコールパークアプリケーションを使用します。</span><span class="sxs-lookup"><span data-stu-id="0df48-112">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application running in the backup pool for the call pickup group numbers.</span></span> <span data-ttu-id="0df48-113">そのため、障害復旧時にグループ通話ピックアップをサポートするには、プライマリプールとバックアッププールの両方でコールパークアプリケーションを展開して有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0df48-113">Therefore, support for Group Call Pickup during disaster recovery requires the Call Park application to be deployed and enabled in both the primary pool and the backup pool.</span></span>

<span data-ttu-id="0df48-114">コールパークオービットテーブルのグループ通話ピックアップ番号の範囲は、バックアッププールへのフェールオーバープロセスが完了した後に、バックアッププールにリダイレクトされる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0df48-114">The Group Call Pickup number ranges in the call park orbit table must be redirected to the backup pool after the failover process to the backup pool is complete.</span></span> <span data-ttu-id="0df48-115">プライマリプールへのフェールバックプロセスが完了したら、番号の範囲をプライマリプールにリダイレクトする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0df48-115">The number ranges must be redirected back to the primary pool after the failback process to the primary pool is complete.</span></span> <span data-ttu-id="0df48-116">グループ通話のピックアップ範囲をリダイレクトするには、 **get-cscallparkorbit**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="0df48-116">To redirect the Group Call Pickup ranges, use the **Set-CsCallParkOrbit** cmdlet.</span></span>

<span data-ttu-id="0df48-117">プライマリプールを置き換えるために別の完全修飾ドメイン名 (FQDN) を使用して新しいプールを展開する場合は、プライマリプールに関連付けられているすべてのグループ通話ピックアップ番号の範囲を新しいプールの FQDN に再割り当てする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0df48-117">If you deploy a new pool with a different fully qualified domain name (FQDN) to replace the primary pool, you need to reassign all the Group Call Pickup number ranges that were associated with the primary pool to the FQDN of the new pool.</span></span> <span data-ttu-id="0df48-118">番号範囲を新しいプールに再割り当てするには、 **get-cscallparkorbit**コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0df48-118">To reassign number ranges to the new pool, you can use the **Set-CsCallParkOrbit** cmdlet.</span></span> <span data-ttu-id="0df48-119">**Get-cscallparkorbit**コマンドレットの詳細については、「 [get-cscallparkorbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0df48-119">For details about the **Set-CsCallParkOrbit** cmdlet, see [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span></span>

</div>

<div>

## <a name="group-call-pickup-experience-during-pool-failure"></a><span data-ttu-id="0df48-120">プール障害時のグループ通話ピックアップ環境</span><span class="sxs-lookup"><span data-stu-id="0df48-120">Group Call Pickup Experience During Pool Failure</span></span>

<span data-ttu-id="0df48-121">次の表では、障害復旧のフェーズを通じてグループ通話ピックアップの使用状況を要約しています。</span><span class="sxs-lookup"><span data-stu-id="0df48-121">The following table summarizes the Group Call Pickup experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="0df48-122">障害復旧時のユーザーの利便性</span><span class="sxs-lookup"><span data-stu-id="0df48-122">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0df48-123">呼び出しの状態</span><span class="sxs-lookup"><span data-stu-id="0df48-123">Call state</span></span></th>
<th><span data-ttu-id="0df48-124">バックアッププールへのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="0df48-124">Failover to backup pool</span></span></th>
<th><span data-ttu-id="0df48-125">プライマリプールへのフェールバック</span><span class="sxs-lookup"><span data-stu-id="0df48-125">Failback to primary pool</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0df48-126">新しい通話</span><span class="sxs-lookup"><span data-stu-id="0df48-126">New calls</span></span></p></td>
<td><p><span data-ttu-id="0df48-127"><strong>フェールオーバー処理中:</strong></span><span class="sxs-lookup"><span data-stu-id="0df48-127"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="0df48-128">復元モードでユーザーがグループ通話ピックアップを使用できない</span><span class="sxs-lookup"><span data-stu-id="0df48-128">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="0df48-129"><strong>フェールオーバーが完了した後:</strong></span><span class="sxs-lookup"><span data-stu-id="0df48-129"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="0df48-130">ユーザーの復元性とグループ通話ピックアップ番号の範囲がバックアッププールにリダイレクトされるときに使用可能なグループ通話ピックアップ</span><span class="sxs-lookup"><span data-stu-id="0df48-130">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected to backup pool</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0df48-131"><strong>フェールバック処理中:</strong></span><span class="sxs-lookup"><span data-stu-id="0df48-131"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="0df48-132">復元モードでユーザーがグループ通話ピックアップを使用できない</span><span class="sxs-lookup"><span data-stu-id="0df48-132">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="0df48-133"><strong>フェールバックが完了すると、次のようになります。</strong></span><span class="sxs-lookup"><span data-stu-id="0df48-133"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="0df48-134">ユーザーが復元可能で、グループ通話ピックアップ番号の範囲がプライマリプールに再びリダイレクトされるときに使用できるグループ通話ピックアップ</span><span class="sxs-lookup"><span data-stu-id="0df48-134">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected back to primary pool</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0df48-135">グループ通話ピックアップキューの呼び出し</span><span class="sxs-lookup"><span data-stu-id="0df48-135">Calls in Group Call Pickup queue</span></span></p></td>
<td><p><span data-ttu-id="0df48-136"><strong>フェールオーバー処理中:</strong></span><span class="sxs-lookup"><span data-stu-id="0df48-136"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="0df48-137">キューの呼び出しは、グループ通話ピックアップで応答できません。</span><span class="sxs-lookup"><span data-stu-id="0df48-137">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="0df48-138"><strong>フェールオーバーが完了した後:</strong></span><span class="sxs-lookup"><span data-stu-id="0df48-138"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="0df48-139">この状態の通話はありません</span><span class="sxs-lookup"><span data-stu-id="0df48-139">No calls in this state</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0df48-140"><strong>フェールバック処理中:</strong></span><span class="sxs-lookup"><span data-stu-id="0df48-140"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="0df48-141">キューの呼び出しは、グループ通話ピックアップで応答できません。</span><span class="sxs-lookup"><span data-stu-id="0df48-141">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="0df48-142"><strong>フェールバックが完了すると、次のようになります。</strong></span><span class="sxs-lookup"><span data-stu-id="0df48-142"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="0df48-143">キューの呼び出しは、グループ通話ピックアップで応答できません。</span><span class="sxs-lookup"><span data-stu-id="0df48-143">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0df48-144">確立された通話</span><span class="sxs-lookup"><span data-stu-id="0df48-144">Established call</span></span></p></td>
<td><p><span data-ttu-id="0df48-145"><strong>フェールオーバー処理中:</strong></span><span class="sxs-lookup"><span data-stu-id="0df48-145"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="0df48-146">通話が接続されたまま</span><span class="sxs-lookup"><span data-stu-id="0df48-146">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="0df48-147"><strong>フェールオーバーが完了した後:</strong></span><span class="sxs-lookup"><span data-stu-id="0df48-147"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="0df48-148">通話が接続されたまま</span><span class="sxs-lookup"><span data-stu-id="0df48-148">Calls stay connected</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0df48-149"><strong>フェールバック処理中:</strong></span><span class="sxs-lookup"><span data-stu-id="0df48-149"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="0df48-150">通話が接続されたまま</span><span class="sxs-lookup"><span data-stu-id="0df48-150">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="0df48-151"><strong>フェールバックが完了すると、次のようになります。</strong></span><span class="sxs-lookup"><span data-stu-id="0df48-151"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="0df48-152">通話が接続されたまま</span><span class="sxs-lookup"><span data-stu-id="0df48-152">Calls stay connected</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

