---
title: 'Lync Server 2013: 障害回復中にグループ通話のピックアップを管理する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Manage Group Call Pickup during disaster recovery
ms:assetid: 2d32f19f-c649-4a72-a4fb-edd338e3a7cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945618(v=OCS.15)
ms:contentKeyID: 51541455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bed21a672dfecab4c3cc8d828fd40f52bd82a363
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828363"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-group-call-pickup-during-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="5482c-102">Lync Server 2013 での障害回復中にグループ通話のピックアップを管理する</span><span class="sxs-lookup"><span data-stu-id="5482c-102">Manage Group Call Pickup during disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5482c-103">_**最終更新日:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="5482c-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="5482c-104">予期しないインシデントが原因でフロントエンドプールが利用できなくなった場合、サービスはバックアッププールにフェールオーバーされます。</span><span class="sxs-lookup"><span data-stu-id="5482c-104">When a Front End pool becomes unavailable due an unplanned incident, service is failed over to the backup pool.</span></span> <span data-ttu-id="5482c-105">バックアッププールへのフェールオーバー中は、ユーザーはバックアッププールにリダイレクトされ、回復性モードになります。</span><span class="sxs-lookup"><span data-stu-id="5482c-105">During failover to the backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="5482c-106">回復性モードでは、ユーザーは他のユーザーの通話を受けたり、他のユーザーがその通話をピックアップしたりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="5482c-106">While in resiliency mode, users cannot pick up other users' calls or have their calls picked up by other users.</span></span> <span data-ttu-id="5482c-107">フェールオーバーが完了したら、ユーザーはグループ通話ピックアップを通常どおりに使うことができます。</span><span class="sxs-lookup"><span data-stu-id="5482c-107">When failover is complete, users can again use Group Call Pickup as usual.</span></span>

<span data-ttu-id="5482c-108">プライマリプールへのフェールバック中に、ユーザーはプライマリプールにリダイレクトされ、復元モードになります。</span><span class="sxs-lookup"><span data-stu-id="5482c-108">During failback to the primary pool, users are redirected to the primary pool and are again in resiliency mode.</span></span> <span data-ttu-id="5482c-109">グループ通話のピックアップ機能は、ユーザーが回復可能モードでなくなるまでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="5482c-109">Group Call Pickup functionality is not available until the users are out of resiliency mode.</span></span>

<span data-ttu-id="5482c-110">このセクションでは、障害回復中のグループ通話のピックアップに関するいくつかの考慮事項について説明し、ユーザーエクスペリエンスについても説明します。</span><span class="sxs-lookup"><span data-stu-id="5482c-110">This section discusses some considerations for Group Call Pickup during disaster recovery and also describes the user experience.</span></span>

<div>

## <a name="considerations-for-group-call-pickup-during-disaster-recovery"></a><span data-ttu-id="5482c-111">障害回復中のグループ通話のピックアップに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="5482c-111">Considerations for Group Call Pickup During Disaster Recovery</span></span>

<span data-ttu-id="5482c-112">障害回復中に、フェールオーバープロセスの一環としてバックアッププールにリダイレクトされたユーザーは、バックアッププールで実行されている Call パークアプリケーションを、通話ピックアップグループ番号として使用します。</span><span class="sxs-lookup"><span data-stu-id="5482c-112">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application running in the backup pool for the call pickup group numbers.</span></span> <span data-ttu-id="5482c-113">そのため、障害回復中のグループ通話のピックアップのサポートでは、プライマリプールとバックアッププールの両方でコールパークアプリケーションを展開して有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5482c-113">Therefore, support for Group Call Pickup during disaster recovery requires the Call Park application to be deployed and enabled in both the primary pool and the backup pool.</span></span>

<span data-ttu-id="5482c-114">通話パークのグループ通話の集配の番号範囲は、バックアッププールへのフェールオーバープロセスが完了した後に、バックアッププールにリダイレクトする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5482c-114">The Group Call Pickup number ranges in the call park orbit table must be redirected to the backup pool after the failover process to the backup pool is complete.</span></span> <span data-ttu-id="5482c-115">プライマリプールへのフェールバックプロセスが完了した後は、番号範囲をプライマリプールに戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="5482c-115">The number ranges must be redirected back to the primary pool after the failback process to the primary pool is complete.</span></span> <span data-ttu-id="5482c-116">グループ通話のピックアップ範囲をリダイレクトするには、 **CsCallParkOrbit**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="5482c-116">To redirect the Group Call Pickup ranges, use the **Set-CsCallParkOrbit** cmdlet.</span></span>

<span data-ttu-id="5482c-117">別の完全修飾ドメイン名 (FQDN) で新しいプールを展開してプライマリプールを置き換える場合は、プライマリプールに関連付けられていたすべてのグループ呼び出しのピックアップ番号の範囲を、新しいプールの FQDN に再割り当てする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5482c-117">If you deploy a new pool with a different fully qualified domain name (FQDN) to replace the primary pool, you need to reassign all the Group Call Pickup number ranges that were associated with the primary pool to the FQDN of the new pool.</span></span> <span data-ttu-id="5482c-118">番号範囲を新しいプールに再割り当てするには、 **CsCallParkOrbit**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="5482c-118">To reassign number ranges to the new pool, you can use the **Set-CsCallParkOrbit** cmdlet.</span></span> <span data-ttu-id="5482c-119">**CsCallParkOrbit**コマンドレットの詳細については、「 [set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5482c-119">For details about the **Set-CsCallParkOrbit** cmdlet, see [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span></span>

</div>

<div>

## <a name="group-call-pickup-experience-during-pool-failure"></a><span data-ttu-id="5482c-120">プール障害時のグループ通話のピックアップ操作</span><span class="sxs-lookup"><span data-stu-id="5482c-120">Group Call Pickup Experience During Pool Failure</span></span>

<span data-ttu-id="5482c-121">次の表は、障害回復のフェーズを通じたグループ通話のピックアップエクスペリエンスをまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="5482c-121">The following table summarizes the Group Call Pickup experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="5482c-122">障害回復中のユーザーエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="5482c-122">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5482c-123">通話の状態</span><span class="sxs-lookup"><span data-stu-id="5482c-123">Call state</span></span></th>
<th><span data-ttu-id="5482c-124">バックアッププールへのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="5482c-124">Failover to backup pool</span></span></th>
<th><span data-ttu-id="5482c-125">プライマリプールへのフェールバック</span><span class="sxs-lookup"><span data-stu-id="5482c-125">Failback to primary pool</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5482c-126">新規通話</span><span class="sxs-lookup"><span data-stu-id="5482c-126">New calls</span></span></p></td>
<td><p><span data-ttu-id="5482c-127"><strong>フェールオーバー処理中:</strong></span><span class="sxs-lookup"><span data-stu-id="5482c-127"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5482c-128">回復可能モードのユーザーに対してグループ通話のピックアップが利用できない</span><span class="sxs-lookup"><span data-stu-id="5482c-128">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="5482c-129"><strong>フェールオーバーが完了したら、次の操作を行います。</strong></span><span class="sxs-lookup"><span data-stu-id="5482c-129"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5482c-130">ユーザの回復性とグループ通話の集配番号範囲にアクセスできない場合に使用可能なグループ通話のピックアップがバックアッププールにリダイレクトされる</span><span class="sxs-lookup"><span data-stu-id="5482c-130">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected to backup pool</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="5482c-131"><strong>フェールバック処理中:</strong></span><span class="sxs-lookup"><span data-stu-id="5482c-131"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5482c-132">回復可能モードのユーザーに対してグループ通話のピックアップが利用できない</span><span class="sxs-lookup"><span data-stu-id="5482c-132">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="5482c-133"><strong>フェールバックが完了したら、次の操作を行います。</strong></span><span class="sxs-lookup"><span data-stu-id="5482c-133"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5482c-134">ユーザの回復性とグループ通話の集配番号の範囲を使用しているユーザーが、プライマリプールにリダイレクトされた場合に、グループ通話のピックアップが利用可能になる</span><span class="sxs-lookup"><span data-stu-id="5482c-134">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected back to primary pool</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5482c-135">グループ通話のピックアップキューでの通話</span><span class="sxs-lookup"><span data-stu-id="5482c-135">Calls in Group Call Pickup queue</span></span></p></td>
<td><p><span data-ttu-id="5482c-136"><strong>フェールオーバー処理中:</strong></span><span class="sxs-lookup"><span data-stu-id="5482c-136"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5482c-137">グループ通話のピックアップを使用して通話を発信することはできません。</span><span class="sxs-lookup"><span data-stu-id="5482c-137">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="5482c-138"><strong>フェールオーバーが完了したら、次の操作を行います。</strong></span><span class="sxs-lookup"><span data-stu-id="5482c-138"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5482c-139">この状態では通話はありません</span><span class="sxs-lookup"><span data-stu-id="5482c-139">No calls in this state</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="5482c-140"><strong>フェールバック処理中:</strong></span><span class="sxs-lookup"><span data-stu-id="5482c-140"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5482c-141">グループ通話のピックアップを使用して通話を発信することはできません。</span><span class="sxs-lookup"><span data-stu-id="5482c-141">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="5482c-142"><strong>フェールバックが完了したら、次の操作を行います。</strong></span><span class="sxs-lookup"><span data-stu-id="5482c-142"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5482c-143">グループ通話のピックアップを使用して通話を発信することはできません。</span><span class="sxs-lookup"><span data-stu-id="5482c-143">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5482c-144">確立された通話</span><span class="sxs-lookup"><span data-stu-id="5482c-144">Established call</span></span></p></td>
<td><p><span data-ttu-id="5482c-145"><strong>フェールオーバー処理中:</strong></span><span class="sxs-lookup"><span data-stu-id="5482c-145"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5482c-146">通話が接続されたまま</span><span class="sxs-lookup"><span data-stu-id="5482c-146">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="5482c-147"><strong>フェールオーバーが完了したら、次の操作を行います。</strong></span><span class="sxs-lookup"><span data-stu-id="5482c-147"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5482c-148">通話が接続されたまま</span><span class="sxs-lookup"><span data-stu-id="5482c-148">Calls stay connected</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="5482c-149"><strong>フェールバック処理中:</strong></span><span class="sxs-lookup"><span data-stu-id="5482c-149"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5482c-150">通話が接続されたまま</span><span class="sxs-lookup"><span data-stu-id="5482c-150">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="5482c-151"><strong>フェールバックが完了したら、次の操作を行います。</strong></span><span class="sxs-lookup"><span data-stu-id="5482c-151"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5482c-152">通話が接続されたまま</span><span class="sxs-lookup"><span data-stu-id="5482c-152">Calls stay connected</span></span></p></li>
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

