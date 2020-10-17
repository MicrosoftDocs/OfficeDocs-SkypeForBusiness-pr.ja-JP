---
title: Lync Server 2013 のプール障害時の応答グループの作業
description: Lync Server 2013 のプール障害時の応答グループの機能。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response group experience during pool failure
ms:assetid: 4e00fb38-64b1-4fd9-903d-7639177bc303
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204886(v=OCS.15)
ms:contentKeyID: 48184116
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d8d5904bc6934d4c330202bafa66d6dd8a16ff5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564573"
---
# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="d079e-103">Lync Server 2013 でのプール障害時の応答グループの動作</span><span class="sxs-lookup"><span data-stu-id="d079e-103">Response group experience in Lync Server 2013 during pool failure</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d079e-104">_**トピックの最終更新日:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="d079e-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="d079e-105">このセクションでは、次の各段階で応答グループのアクティビティへの影響について詳細に説明します。</span><span class="sxs-lookup"><span data-stu-id="d079e-105">This section describes in detail how response group activity is affected in the following stages:</span></span>

  - <span data-ttu-id="d079e-106">プライマリプールで停止が発生したが、フェールオーバーがまだ開始されていない。</span><span class="sxs-lookup"><span data-stu-id="d079e-106">An outage occurs in the primary pool, but failover is not yet initiated.</span></span>

  - <span data-ttu-id="d079e-107">サービスがバックアッププールにフェールオーバーされます。</span><span class="sxs-lookup"><span data-stu-id="d079e-107">Service is failed over to the backup pool.</span></span>

  - <span data-ttu-id="d079e-108">サービスがプライマリプールにフェールバックされます。</span><span class="sxs-lookup"><span data-stu-id="d079e-108">Service is failed back to the primary pool.</span></span>

<div>

## <a name="user-experience-when-outage-occurs"></a><span data-ttu-id="d079e-109">停止時のユーザーの作業状況</span><span class="sxs-lookup"><span data-stu-id="d079e-109">User Experience When Outage Occurs</span></span>

<span data-ttu-id="d079e-110">プールまたはサイトの停止が発生しても、管理者がまだフェールオーバーを開始していない場合、応答グループのアクティビティは次の表に示すように処理されます。</span><span class="sxs-lookup"><span data-stu-id="d079e-110">When a pool or site outage occurs, but the administrator has not yet initiated failover, response group activity is handled as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d079e-111">障害復旧時に、プライマリプール応答グループが回復時にバックアッププールにインポートされたかどうかによって、呼び出しの動作が異なります。</span><span class="sxs-lookup"><span data-stu-id="d079e-111">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="d079e-112">次の表では、インポートされた応答グループへの参照は、障害復旧モード中にプライマリプール応答グループがバックアッププールにインポートされたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="d079e-112">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="outage-occurs"></a><span data-ttu-id="d079e-113">停止が発生する</span><span class="sxs-lookup"><span data-stu-id="d079e-113">Outage Occurs</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d079e-114">通話またはユーザーの操作の種類</span><span class="sxs-lookup"><span data-stu-id="d079e-114">Type of call or user action</span></span></th>
<th><span data-ttu-id="d079e-115">停止中</span><span class="sxs-lookup"><span data-stu-id="d079e-115">During outage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d079e-116">エージェントに接続された通話</span><span class="sxs-lookup"><span data-stu-id="d079e-116">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d079e-117">通常の通話は接続されたままです。</span><span class="sxs-lookup"><span data-stu-id="d079e-117">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="d079e-118">匿名呼び出しは切断されます。</span><span class="sxs-lookup"><span data-stu-id="d079e-118">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d079e-119">エージェントにまだ接続されていない呼び出し中</span><span class="sxs-lookup"><span data-stu-id="d079e-119">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="d079e-120">通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="d079e-120">Calls are disconnected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d079e-121">新しい通話</span><span class="sxs-lookup"><span data-stu-id="d079e-121">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d079e-122">通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="d079e-122">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="d079e-123">応答グループがインポートされた場合、通話はバックアッププールに接続されますが、プライマリプールに所属するエージェントには到達できません。</span><span class="sxs-lookup"><span data-stu-id="d079e-123">If response groups were imported, calls connect to backup pool, but agents homed in primary pool are unreachable.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d079e-124">応答グループの代理としてのエージェント呼び出し</span><span class="sxs-lookup"><span data-stu-id="d079e-124">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="d079e-125">この段階では機能は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="d079e-125">Feature is disabled during this stage.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d079e-126">エージェントのサインインとエージェントの情報</span><span class="sxs-lookup"><span data-stu-id="d079e-126">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d079e-127">プライマリプールが所有するエージェントグループはエージェントコンソールで表示できますが、エージェントはサインインできません。</span><span class="sxs-lookup"><span data-stu-id="d079e-127">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="d079e-128">バックアッププールが所有するエージェントグループはエージェントコンソールで表示でき、エージェントはサインインできます。</span><span class="sxs-lookup"><span data-stu-id="d079e-128">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="d079e-129">インポートされたエージェントグループはエージェントコンソールに表示されません。</span><span class="sxs-lookup"><span data-stu-id="d079e-129">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d079e-130">応答グループの構成</span><span class="sxs-lookup"><span data-stu-id="d079e-130">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d079e-131">プライマリプールで所有されている応答グループは、プライマリプールのバックエンドデータベースの可用性に応じて表示できますが、変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="d079e-131">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="d079e-132">バックアッププールが所有する応答グループは、表示および変更できます。</span><span class="sxs-lookup"><span data-stu-id="d079e-132">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="d079e-133">インポートされた応答グループは、Lync Server コントロールパネルまたは応答グループ構成ツールを使用して表示することはできませんが、Lync Server 管理シェルコマンドレットを使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="d079e-133">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="d079e-134">フェールオーバー中のユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="d079e-134">User Experience During Failover</span></span>

<span data-ttu-id="d079e-135">管理者がバックアッププールへのフェールオーバーを起動すると、次の表に示すように、応答グループのアクティビティはフェールオーバー中およびフェールオーバー後に処理されます。</span><span class="sxs-lookup"><span data-stu-id="d079e-135">When an administrator invokes failover to a backup pool, response group activity is handled during and after the failover as described in the following table.</span></span> <span data-ttu-id="d079e-136">最初の列は、発生する可能性のあるアクティビティの種類を示しています。</span><span class="sxs-lookup"><span data-stu-id="d079e-136">The first column describes the type of activity that might be taking place.</span></span> <span data-ttu-id="d079e-137">中央の列は、バックアッププールへのフェールオーバーの短時間に各アクティビティがどのように処理されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="d079e-137">The middle column describes how each activity is handled during the brief time that it takes to fail over to the backup pool.</span></span> <span data-ttu-id="d079e-138">最後の列は、フェールオーバープロセスが完了し、バックアッププールがプライマリプールに対して実行された後の、期間中にアクティビティが処理される方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d079e-138">The last column describes how the activity is handled for the duration, after the failover process is complete and the backup pool is standing in for the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d079e-139">障害復旧時に、プライマリプール応答グループが回復時にバックアッププールにインポートされたかどうかによって、呼び出しの動作が異なります。</span><span class="sxs-lookup"><span data-stu-id="d079e-139">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="d079e-140">次の表では、インポートされた応答グループへの参照は、障害復旧モード中にプライマリプール応答グループがバックアッププールにインポートされたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="d079e-140">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="failover-is-initiated"></a><span data-ttu-id="d079e-141">フェールオーバーの開始</span><span class="sxs-lookup"><span data-stu-id="d079e-141">Failover Is Initiated</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d079e-142">通話またはユーザーの操作の種類</span><span class="sxs-lookup"><span data-stu-id="d079e-142">Type of call or user action</span></span></th>
<th><span data-ttu-id="d079e-143">フェールオーバー中</span><span class="sxs-lookup"><span data-stu-id="d079e-143">During Failover</span></span></th>
<th><span data-ttu-id="d079e-144">フェールオーバーの完了後</span><span class="sxs-lookup"><span data-stu-id="d079e-144">After Failover Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d079e-145">エージェントに接続された通話</span><span class="sxs-lookup"><span data-stu-id="d079e-145">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d079e-146">通常の通話は接続されたままです。</span><span class="sxs-lookup"><span data-stu-id="d079e-146">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="d079e-147">匿名呼び出しは切断されます。</span><span class="sxs-lookup"><span data-stu-id="d079e-147">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="d079e-148">通常の通話は接続されたままです。</span><span class="sxs-lookup"><span data-stu-id="d079e-148">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="d079e-149">インポートされた応答グループの場合、バックアッププールに到達した匿名の通話は接続したままになります。</span><span class="sxs-lookup"><span data-stu-id="d079e-149">For imported response groups, anonymous calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d079e-150">エージェントにまだ接続されていない呼び出し中</span><span class="sxs-lookup"><span data-stu-id="d079e-150">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="d079e-151">通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="d079e-151">Calls are disconnected.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d079e-152">応答グループがインポートされなかった場合、このステータスになる通話はありません。</span><span class="sxs-lookup"><span data-stu-id="d079e-152">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="d079e-153">インポートされた応答グループの場合、バックアッププールに到達した通話は接続したままになります。</span><span class="sxs-lookup"><span data-stu-id="d079e-153">For imported response groups, calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d079e-154">新しい通話</span><span class="sxs-lookup"><span data-stu-id="d079e-154">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d079e-155">通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="d079e-155">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="d079e-156">インポートされた応答グループの場合、通話はバックアッププールに接続されますが、プライマリプールに所属するエージェントには到達できません。</span><span class="sxs-lookup"><span data-stu-id="d079e-156">For imported response groups, calls connect to the backup pool, but agents homed in the primary pool are unreachable.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="d079e-157">応答グループがインポートされなかった場合、通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="d079e-157">If response groups were not imported, calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="d079e-158">インポートされた応答グループでは、通話はバックアッププールに接続されます。</span><span class="sxs-lookup"><span data-stu-id="d079e-158">For imported response groups, calls connect to the backup pool.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d079e-159">応答グループの代理としてのエージェント呼び出し</span><span class="sxs-lookup"><span data-stu-id="d079e-159">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="d079e-160">この段階では機能は無効になっています</span><span class="sxs-lookup"><span data-stu-id="d079e-160">Feature is disabled during this stage</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d079e-161">応答グループがインポートされなかった場合、通話は失敗します。</span><span class="sxs-lookup"><span data-stu-id="d079e-161">If response groups were not imported, calls fail.</span></span></p></li>
<li><p><span data-ttu-id="d079e-162">インポートされた応答グループの場合、通話は成功します。</span><span class="sxs-lookup"><span data-stu-id="d079e-162">For imported response groups, calls succeed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d079e-163">エージェントのサインインとエージェントの情報</span><span class="sxs-lookup"><span data-stu-id="d079e-163">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d079e-164">プライマリプールが所有するエージェントグループはエージェントコンソールで表示できますが、エージェントはサインインできません。</span><span class="sxs-lookup"><span data-stu-id="d079e-164">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="d079e-165">バックアッププールが所有するエージェントグループはエージェントコンソールで表示でき、エージェントはサインインできます。</span><span class="sxs-lookup"><span data-stu-id="d079e-165">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="d079e-166">インポートされたエージェントグループはエージェントコンソールに表示され、エージェントはサインインできます。</span><span class="sxs-lookup"><span data-stu-id="d079e-166">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="d079e-167">プライマリプールが所有するエージェントグループはエージェントコンソールで表示できますが、エージェントはサインインできません。</span><span class="sxs-lookup"><span data-stu-id="d079e-167">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="d079e-168">バックアッププールが所有するエージェントグループはエージェントコンソールで表示でき、エージェントはサインインできます。</span><span class="sxs-lookup"><span data-stu-id="d079e-168">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="d079e-169">インポートされたエージェントグループはエージェントコンソールに表示され、エージェントはサインインできます。</span><span class="sxs-lookup"><span data-stu-id="d079e-169">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d079e-170">応答グループの構成</span><span class="sxs-lookup"><span data-stu-id="d079e-170">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d079e-171">プライマリプールで所有されている応答グループは、プライマリプールのバックエンドデータベースの可用性に応じて表示できますが、変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="d079e-171">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="d079e-172">バックアッププールが所有する応答グループは、表示および変更できます。</span><span class="sxs-lookup"><span data-stu-id="d079e-172">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="d079e-173">インポートされた応答グループは、Lync Server コントロールパネルまたは応答グループ構成ツールを使用して表示することはできませんが、Lync Server 管理シェルコマンドレットを使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="d079e-173">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="d079e-174">プライマリプールが所有する応答グループは、バックエンドデータベースの可用性に応じて表示できますが、変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="d079e-174">Response groups owned by the primary pool can be viewed, depending on the availability of the back end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="d079e-175">バックアッププールが所有する応答グループは、表示および変更できます。</span><span class="sxs-lookup"><span data-stu-id="d079e-175">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="d079e-176">インポートされた応答グループは、Lync Server コントロールパネルまたは応答グループ構成ツールを使用して表示することはできませんが、Lync Server 管理シェルコマンドレットを使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="d079e-176">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="d079e-177">フェールバック中のユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="d079e-177">User Experience During Failback</span></span>

<span data-ttu-id="d079e-178">管理者がプライマリプールへのフェールバックを起動すると、次の表に示すように、応答グループのアクティビティはフェールバック中およびフェールバック後に処理されます。</span><span class="sxs-lookup"><span data-stu-id="d079e-178">When an administrator invokes failback to the primary pool, response group activity is handled during and after the failback as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d079e-179">障害復旧時に、プライマリプール応答グループが回復時にバックアッププールにインポートされたかどうかによって、呼び出しの動作が異なります。</span><span class="sxs-lookup"><span data-stu-id="d079e-179">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="d079e-180">次の表では、インポートされた応答グループへの参照は、障害復旧モード中にプライマリプール応答グループがバックアッププールにインポートされたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="d079e-180">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="call-handling-in-failback"></a><span data-ttu-id="d079e-181">フェールバックにおける通話の処理</span><span class="sxs-lookup"><span data-stu-id="d079e-181">Call Handling in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d079e-182">通話またはユーザーの操作の種類</span><span class="sxs-lookup"><span data-stu-id="d079e-182">Type of call or user action</span></span></th>
<th><span data-ttu-id="d079e-183">フェールバック中</span><span class="sxs-lookup"><span data-stu-id="d079e-183">During Failback</span></span></th>
<th><span data-ttu-id="d079e-184">フェールバックの完了後</span><span class="sxs-lookup"><span data-stu-id="d079e-184">After Failback Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d079e-185">エージェントに接続された通話</span><span class="sxs-lookup"><span data-stu-id="d079e-185">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d079e-186">通常の通話は接続されたままです。</span><span class="sxs-lookup"><span data-stu-id="d079e-186">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="d079e-187">応答グループがインポートされなかった場合、このステータスになる匿名通話はありません。</span><span class="sxs-lookup"><span data-stu-id="d079e-187">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="d079e-188">インポートされた応答グループの場合、匿名通話は接続したままになります。</span><span class="sxs-lookup"><span data-stu-id="d079e-188">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="d079e-189">通常の通話は接続されたままです。</span><span class="sxs-lookup"><span data-stu-id="d079e-189">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="d079e-190">応答グループがインポートされなかった場合、このステータスになる匿名通話はありません。</span><span class="sxs-lookup"><span data-stu-id="d079e-190">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="d079e-191">インポートされた応答グループの場合、匿名通話は接続したままになります。</span><span class="sxs-lookup"><span data-stu-id="d079e-191">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d079e-192">エージェントにまだ接続されていない呼び出し中</span><span class="sxs-lookup"><span data-stu-id="d079e-192">In progress calls not yet connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d079e-193">応答グループがインポートされなかった場合、このステータスになる通話はありません。</span><span class="sxs-lookup"><span data-stu-id="d079e-193">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="d079e-194">インポートされた応答グループの場合、通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="d079e-194">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="d079e-195">応答グループがインポートされなかった場合、このステータスになる通話はありません。</span><span class="sxs-lookup"><span data-stu-id="d079e-195">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="d079e-196">インポートされた応答グループの場合、通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="d079e-196">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d079e-197">新しい通話</span><span class="sxs-lookup"><span data-stu-id="d079e-197">New calls</span></span></p></td>
<td><p><span data-ttu-id="d079e-198">通話はプライマリプールに接続されますが、プライマリプールに所属するエージェントには到達できません。</span><span class="sxs-lookup"><span data-stu-id="d079e-198">Calls connect to the primary pool, but agents homed in the primary pool are unreachable.</span></span></p></td>
<td><p><span data-ttu-id="d079e-199">通話はプライマリプールに接続されます。</span><span class="sxs-lookup"><span data-stu-id="d079e-199">Calls connect to the primary pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d079e-200">応答グループの代理としてのエージェント呼び出し</span><span class="sxs-lookup"><span data-stu-id="d079e-200">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="d079e-201">この段階では機能は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="d079e-201">Feature is disabled during this stage.</span></span></p></td>
<td><p><span data-ttu-id="d079e-202">呼び出しは成功します。</span><span class="sxs-lookup"><span data-stu-id="d079e-202">Calls succeed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d079e-203">エージェントのサインインとエージェントの情報</span><span class="sxs-lookup"><span data-stu-id="d079e-203">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d079e-204">プライマリプールが所有するエージェントグループはエージェントコンソールで表示できますが、エージェントはサインインできません。</span><span class="sxs-lookup"><span data-stu-id="d079e-204">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="d079e-205">バックアッププールが所有するエージェントグループはエージェントコンソールで表示でき、エージェントはサインインできます。</span><span class="sxs-lookup"><span data-stu-id="d079e-205">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="d079e-206">インポートされたエージェントグループはエージェントコンソールに表示され、エージェントはサインインできます。</span><span class="sxs-lookup"><span data-stu-id="d079e-206">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="d079e-207">プライマリプールが所有するエージェントグループはエージェントコンソールで表示でき、エージェントはサインインできます。</span><span class="sxs-lookup"><span data-stu-id="d079e-207">Agent groups owned by the primary pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="d079e-208">バックアッププールが所有するエージェントグループはエージェントコンソールで表示でき、エージェントはサインインできます。</span><span class="sxs-lookup"><span data-stu-id="d079e-208">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="d079e-209">インポートされたエージェントグループはエージェントコンソールに表示されません。</span><span class="sxs-lookup"><span data-stu-id="d079e-209">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d079e-210">応答グループの構成</span><span class="sxs-lookup"><span data-stu-id="d079e-210">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d079e-211">プライマリプールで所有されている応答グループは、プライマリプールのバックエンドデータベースの可用性に応じて表示できますが、変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="d079e-211">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="d079e-212">バックアッププールが所有する応答グループは、表示および変更できます。</span><span class="sxs-lookup"><span data-stu-id="d079e-212">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="d079e-213">インポートされた応答グループは、Lync Server コントロールパネルまたは応答グループ構成ツールを使用して表示することはできませんが、Lync Server 管理シェルコマンドレットを使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="d079e-213">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="d079e-214">プライマリプールが所有する応答グループは、表示および変更できます。</span><span class="sxs-lookup"><span data-stu-id="d079e-214">Response groups owned by the primary pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="d079e-215">バックアッププールが所有する応答グループは、表示および変更できます。</span><span class="sxs-lookup"><span data-stu-id="d079e-215">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="d079e-216">インポートされた応答グループは、Lync Server コントロールパネルまたは応答グループ構成ツールを使用して表示することはできませんが、Lync Server 管理シェルコマンドレットを使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="d079e-216">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
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

