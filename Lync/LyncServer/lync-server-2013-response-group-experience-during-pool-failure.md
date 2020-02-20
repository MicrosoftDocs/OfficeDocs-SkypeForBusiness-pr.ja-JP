---
title: Lync Server 2013 のプール障害時の応答グループの作業
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
ms.openlocfilehash: d3977d05c0916cc23f628c0af26be1cbc8a79990
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144794"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="70e44-102">Lync Server 2013 でのプール障害時の応答グループの動作</span><span class="sxs-lookup"><span data-stu-id="70e44-102">Response group experience in Lync Server 2013 during pool failure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70e44-103">_**トピックの最終更新日:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="70e44-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="70e44-104">このセクションでは、次の各段階で応答グループのアクティビティへの影響について詳細に説明します。</span><span class="sxs-lookup"><span data-stu-id="70e44-104">This section describes in detail how response group activity is affected in the following stages:</span></span>

  - <span data-ttu-id="70e44-105">プライマリプールで停止が発生したが、フェールオーバーがまだ開始されていない。</span><span class="sxs-lookup"><span data-stu-id="70e44-105">An outage occurs in the primary pool, but failover is not yet initiated.</span></span>

  - <span data-ttu-id="70e44-106">サービスがバックアッププールにフェールオーバーされます。</span><span class="sxs-lookup"><span data-stu-id="70e44-106">Service is failed over to the backup pool.</span></span>

  - <span data-ttu-id="70e44-107">サービスがプライマリプールにフェールバックされます。</span><span class="sxs-lookup"><span data-stu-id="70e44-107">Service is failed back to the primary pool.</span></span>

<div>

## <a name="user-experience-when-outage-occurs"></a><span data-ttu-id="70e44-108">停止時のユーザーの作業状況</span><span class="sxs-lookup"><span data-stu-id="70e44-108">User Experience When Outage Occurs</span></span>

<span data-ttu-id="70e44-109">プールまたはサイトの停止が発生しても、管理者がまだフェールオーバーを開始していない場合、応答グループのアクティビティは次の表に示すように処理されます。</span><span class="sxs-lookup"><span data-stu-id="70e44-109">When a pool or site outage occurs, but the administrator has not yet initiated failover, response group activity is handled as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="70e44-110">障害復旧時に、プライマリプール応答グループが回復時にバックアッププールにインポートされたかどうかによって、呼び出しの動作が異なります。</span><span class="sxs-lookup"><span data-stu-id="70e44-110">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="70e44-111">次の表では、インポートされた応答グループへの参照は、障害復旧モード中にプライマリプール応答グループがバックアッププールにインポートされたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="70e44-111">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="outage-occurs"></a><span data-ttu-id="70e44-112">停止が発生する</span><span class="sxs-lookup"><span data-stu-id="70e44-112">Outage Occurs</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70e44-113">通話またはユーザーの操作の種類</span><span class="sxs-lookup"><span data-stu-id="70e44-113">Type of call or user action</span></span></th>
<th><span data-ttu-id="70e44-114">停止中</span><span class="sxs-lookup"><span data-stu-id="70e44-114">During outage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70e44-115">エージェントに接続された通話</span><span class="sxs-lookup"><span data-stu-id="70e44-115">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="70e44-116">通常の通話は接続されたままです。</span><span class="sxs-lookup"><span data-stu-id="70e44-116">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="70e44-117">匿名呼び出しは切断されます。</span><span class="sxs-lookup"><span data-stu-id="70e44-117">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70e44-118">エージェントにまだ接続されていない呼び出し中</span><span class="sxs-lookup"><span data-stu-id="70e44-118">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="70e44-119">通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="70e44-119">Calls are disconnected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70e44-120">新しい通話</span><span class="sxs-lookup"><span data-stu-id="70e44-120">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="70e44-121">通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="70e44-121">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="70e44-122">応答グループがインポートされた場合、通話はバックアッププールに接続されますが、プライマリプールに所属するエージェントには到達できません。</span><span class="sxs-lookup"><span data-stu-id="70e44-122">If response groups were imported, calls connect to backup pool, but agents homed in primary pool are unreachable.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70e44-123">応答グループの代理としてのエージェント呼び出し</span><span class="sxs-lookup"><span data-stu-id="70e44-123">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="70e44-124">この段階では機能は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="70e44-124">Feature is disabled during this stage.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70e44-125">エージェントのサインインとエージェントの情報</span><span class="sxs-lookup"><span data-stu-id="70e44-125">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="70e44-126">プライマリプールが所有するエージェントグループはエージェントコンソールで表示できますが、エージェントはサインインできません。</span><span class="sxs-lookup"><span data-stu-id="70e44-126">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="70e44-127">バックアッププールが所有するエージェントグループはエージェントコンソールで表示でき、エージェントはサインインできます。</span><span class="sxs-lookup"><span data-stu-id="70e44-127">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="70e44-128">インポートされたエージェントグループはエージェントコンソールに表示されません。</span><span class="sxs-lookup"><span data-stu-id="70e44-128">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70e44-129">応答グループの構成</span><span class="sxs-lookup"><span data-stu-id="70e44-129">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="70e44-130">プライマリプールで所有されている応答グループは、プライマリプールのバックエンドデータベースの可用性に応じて表示できますが、変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="70e44-130">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="70e44-131">バックアッププールが所有する応答グループは、表示および変更できます。</span><span class="sxs-lookup"><span data-stu-id="70e44-131">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="70e44-132">インポートされた応答グループは、Lync Server コントロールパネルまたは応答グループ構成ツールを使用して表示することはできませんが、Lync Server 管理シェルコマンドレットを使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="70e44-132">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="70e44-133">フェールオーバー中のユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="70e44-133">User Experience During Failover</span></span>

<span data-ttu-id="70e44-134">管理者がバックアッププールへのフェールオーバーを起動すると、次の表に示すように、応答グループのアクティビティはフェールオーバー中およびフェールオーバー後に処理されます。</span><span class="sxs-lookup"><span data-stu-id="70e44-134">When an administrator invokes failover to a backup pool, response group activity is handled during and after the failover as described in the following table.</span></span> <span data-ttu-id="70e44-135">最初の列は、発生する可能性のあるアクティビティの種類を示しています。</span><span class="sxs-lookup"><span data-stu-id="70e44-135">The first column describes the type of activity that might be taking place.</span></span> <span data-ttu-id="70e44-136">中央の列は、バックアッププールへのフェールオーバーの短時間に各アクティビティがどのように処理されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="70e44-136">The middle column describes how each activity is handled during the brief time that it takes to fail over to the backup pool.</span></span> <span data-ttu-id="70e44-137">最後の列は、フェールオーバープロセスが完了し、バックアッププールがプライマリプールに対して実行された後の、期間中にアクティビティが処理される方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="70e44-137">The last column describes how the activity is handled for the duration, after the failover process is complete and the backup pool is standing in for the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="70e44-138">障害復旧時に、プライマリプール応答グループが回復時にバックアッププールにインポートされたかどうかによって、呼び出しの動作が異なります。</span><span class="sxs-lookup"><span data-stu-id="70e44-138">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="70e44-139">次の表では、インポートされた応答グループへの参照は、障害復旧モード中にプライマリプール応答グループがバックアッププールにインポートされたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="70e44-139">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="failover-is-initiated"></a><span data-ttu-id="70e44-140">フェールオーバーの開始</span><span class="sxs-lookup"><span data-stu-id="70e44-140">Failover Is Initiated</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70e44-141">通話またはユーザーの操作の種類</span><span class="sxs-lookup"><span data-stu-id="70e44-141">Type of call or user action</span></span></th>
<th><span data-ttu-id="70e44-142">フェールオーバー中</span><span class="sxs-lookup"><span data-stu-id="70e44-142">During Failover</span></span></th>
<th><span data-ttu-id="70e44-143">フェールオーバーの完了後</span><span class="sxs-lookup"><span data-stu-id="70e44-143">After Failover Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70e44-144">エージェントに接続された通話</span><span class="sxs-lookup"><span data-stu-id="70e44-144">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="70e44-145">通常の通話は接続されたままです。</span><span class="sxs-lookup"><span data-stu-id="70e44-145">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="70e44-146">匿名呼び出しは切断されます。</span><span class="sxs-lookup"><span data-stu-id="70e44-146">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="70e44-147">通常の通話は接続されたままです。</span><span class="sxs-lookup"><span data-stu-id="70e44-147">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="70e44-148">インポートされた応答グループの場合、バックアッププールに到達した匿名の通話は接続したままになります。</span><span class="sxs-lookup"><span data-stu-id="70e44-148">For imported response groups, anonymous calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70e44-149">エージェントにまだ接続されていない呼び出し中</span><span class="sxs-lookup"><span data-stu-id="70e44-149">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="70e44-150">通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="70e44-150">Calls are disconnected.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="70e44-151">応答グループがインポートされなかった場合、このステータスになる通話はありません。</span><span class="sxs-lookup"><span data-stu-id="70e44-151">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="70e44-152">インポートされた応答グループの場合、バックアッププールに到達した通話は接続したままになります。</span><span class="sxs-lookup"><span data-stu-id="70e44-152">For imported response groups, calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70e44-153">新しい通話</span><span class="sxs-lookup"><span data-stu-id="70e44-153">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="70e44-154">通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="70e44-154">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="70e44-155">インポートされた応答グループの場合、通話はバックアッププールに接続されますが、プライマリプールに所属するエージェントには到達できません。</span><span class="sxs-lookup"><span data-stu-id="70e44-155">For imported response groups, calls connect to the backup pool, but agents homed in the primary pool are unreachable.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="70e44-156">応答グループがインポートされなかった場合、通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="70e44-156">If response groups were not imported, calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="70e44-157">インポートされた応答グループでは、通話はバックアッププールに接続されます。</span><span class="sxs-lookup"><span data-stu-id="70e44-157">For imported response groups, calls connect to the backup pool.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70e44-158">応答グループの代理としてのエージェント呼び出し</span><span class="sxs-lookup"><span data-stu-id="70e44-158">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="70e44-159">この段階では機能は無効になっています</span><span class="sxs-lookup"><span data-stu-id="70e44-159">Feature is disabled during this stage</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="70e44-160">応答グループがインポートされなかった場合、通話は失敗します。</span><span class="sxs-lookup"><span data-stu-id="70e44-160">If response groups were not imported, calls fail.</span></span></p></li>
<li><p><span data-ttu-id="70e44-161">インポートされた応答グループの場合、通話は成功します。</span><span class="sxs-lookup"><span data-stu-id="70e44-161">For imported response groups, calls succeed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70e44-162">エージェントのサインインとエージェントの情報</span><span class="sxs-lookup"><span data-stu-id="70e44-162">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="70e44-163">プライマリプールが所有するエージェントグループはエージェントコンソールで表示できますが、エージェントはサインインできません。</span><span class="sxs-lookup"><span data-stu-id="70e44-163">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="70e44-164">バックアッププールが所有するエージェントグループはエージェントコンソールで表示でき、エージェントはサインインできます。</span><span class="sxs-lookup"><span data-stu-id="70e44-164">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="70e44-165">インポートされたエージェントグループはエージェントコンソールに表示され、エージェントはサインインできます。</span><span class="sxs-lookup"><span data-stu-id="70e44-165">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="70e44-166">プライマリプールが所有するエージェントグループはエージェントコンソールで表示できますが、エージェントはサインインできません。</span><span class="sxs-lookup"><span data-stu-id="70e44-166">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="70e44-167">バックアッププールが所有するエージェントグループはエージェントコンソールで表示でき、エージェントはサインインできます。</span><span class="sxs-lookup"><span data-stu-id="70e44-167">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="70e44-168">インポートされたエージェントグループはエージェントコンソールに表示され、エージェントはサインインできます。</span><span class="sxs-lookup"><span data-stu-id="70e44-168">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70e44-169">応答グループの構成</span><span class="sxs-lookup"><span data-stu-id="70e44-169">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="70e44-170">プライマリプールで所有されている応答グループは、プライマリプールのバックエンドデータベースの可用性に応じて表示できますが、変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="70e44-170">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="70e44-171">バックアッププールが所有する応答グループは、表示および変更できます。</span><span class="sxs-lookup"><span data-stu-id="70e44-171">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="70e44-172">インポートされた応答グループは、Lync Server コントロールパネルまたは応答グループ構成ツールを使用して表示することはできませんが、Lync Server 管理シェルコマンドレットを使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="70e44-172">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="70e44-173">プライマリプールが所有する応答グループは、バックエンドデータベースの可用性に応じて表示できますが、変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="70e44-173">Response groups owned by the primary pool can be viewed, depending on the availability of the back end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="70e44-174">バックアッププールが所有する応答グループは、表示および変更できます。</span><span class="sxs-lookup"><span data-stu-id="70e44-174">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="70e44-175">インポートされた応答グループは、Lync Server コントロールパネルまたは応答グループ構成ツールを使用して表示することはできませんが、Lync Server 管理シェルコマンドレットを使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="70e44-175">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="70e44-176">フェールバック中のユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="70e44-176">User Experience During Failback</span></span>

<span data-ttu-id="70e44-177">管理者がプライマリプールへのフェールバックを起動すると、次の表に示すように、応答グループのアクティビティはフェールバック中およびフェールバック後に処理されます。</span><span class="sxs-lookup"><span data-stu-id="70e44-177">When an administrator invokes failback to the primary pool, response group activity is handled during and after the failback as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="70e44-178">障害復旧時に、プライマリプール応答グループが回復時にバックアッププールにインポートされたかどうかによって、呼び出しの動作が異なります。</span><span class="sxs-lookup"><span data-stu-id="70e44-178">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="70e44-179">次の表では、インポートされた応答グループへの参照は、障害復旧モード中にプライマリプール応答グループがバックアッププールにインポートされたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="70e44-179">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="call-handling-in-failback"></a><span data-ttu-id="70e44-180">フェールバックにおける通話の処理</span><span class="sxs-lookup"><span data-stu-id="70e44-180">Call Handling in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70e44-181">通話またはユーザーの操作の種類</span><span class="sxs-lookup"><span data-stu-id="70e44-181">Type of call or user action</span></span></th>
<th><span data-ttu-id="70e44-182">フェールバック中</span><span class="sxs-lookup"><span data-stu-id="70e44-182">During Failback</span></span></th>
<th><span data-ttu-id="70e44-183">フェールバックの完了後</span><span class="sxs-lookup"><span data-stu-id="70e44-183">After Failback Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70e44-184">エージェントに接続された通話</span><span class="sxs-lookup"><span data-stu-id="70e44-184">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="70e44-185">通常の通話は接続されたままです。</span><span class="sxs-lookup"><span data-stu-id="70e44-185">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="70e44-186">応答グループがインポートされなかった場合、このステータスになる匿名通話はありません。</span><span class="sxs-lookup"><span data-stu-id="70e44-186">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="70e44-187">インポートされた応答グループの場合、匿名通話は接続したままになります。</span><span class="sxs-lookup"><span data-stu-id="70e44-187">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="70e44-188">通常の通話は接続されたままです。</span><span class="sxs-lookup"><span data-stu-id="70e44-188">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="70e44-189">応答グループがインポートされなかった場合、このステータスになる匿名通話はありません。</span><span class="sxs-lookup"><span data-stu-id="70e44-189">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="70e44-190">インポートされた応答グループの場合、匿名通話は接続したままになります。</span><span class="sxs-lookup"><span data-stu-id="70e44-190">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70e44-191">エージェントにまだ接続されていない呼び出し中</span><span class="sxs-lookup"><span data-stu-id="70e44-191">In progress calls not yet connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="70e44-192">応答グループがインポートされなかった場合、このステータスになる通話はありません。</span><span class="sxs-lookup"><span data-stu-id="70e44-192">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="70e44-193">インポートされた応答グループの場合、通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="70e44-193">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="70e44-194">応答グループがインポートされなかった場合、このステータスになる通話はありません。</span><span class="sxs-lookup"><span data-stu-id="70e44-194">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="70e44-195">インポートされた応答グループの場合、通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="70e44-195">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70e44-196">新しい通話</span><span class="sxs-lookup"><span data-stu-id="70e44-196">New calls</span></span></p></td>
<td><p><span data-ttu-id="70e44-197">通話はプライマリプールに接続されますが、プライマリプールに所属するエージェントには到達できません。</span><span class="sxs-lookup"><span data-stu-id="70e44-197">Calls connect to the primary pool, but agents homed in the primary pool are unreachable.</span></span></p></td>
<td><p><span data-ttu-id="70e44-198">通話はプライマリプールに接続されます。</span><span class="sxs-lookup"><span data-stu-id="70e44-198">Calls connect to the primary pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70e44-199">応答グループの代理としてのエージェント呼び出し</span><span class="sxs-lookup"><span data-stu-id="70e44-199">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="70e44-200">この段階では機能は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="70e44-200">Feature is disabled during this stage.</span></span></p></td>
<td><p><span data-ttu-id="70e44-201">呼び出しは成功します。</span><span class="sxs-lookup"><span data-stu-id="70e44-201">Calls succeed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70e44-202">エージェントのサインインとエージェントの情報</span><span class="sxs-lookup"><span data-stu-id="70e44-202">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="70e44-203">プライマリプールが所有するエージェントグループはエージェントコンソールで表示できますが、エージェントはサインインできません。</span><span class="sxs-lookup"><span data-stu-id="70e44-203">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="70e44-204">バックアッププールが所有するエージェントグループはエージェントコンソールで表示でき、エージェントはサインインできます。</span><span class="sxs-lookup"><span data-stu-id="70e44-204">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="70e44-205">インポートされたエージェントグループはエージェントコンソールに表示され、エージェントはサインインできます。</span><span class="sxs-lookup"><span data-stu-id="70e44-205">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="70e44-206">プライマリプールが所有するエージェントグループはエージェントコンソールで表示でき、エージェントはサインインできます。</span><span class="sxs-lookup"><span data-stu-id="70e44-206">Agent groups owned by the primary pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="70e44-207">バックアッププールが所有するエージェントグループはエージェントコンソールで表示でき、エージェントはサインインできます。</span><span class="sxs-lookup"><span data-stu-id="70e44-207">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="70e44-208">インポートされたエージェントグループはエージェントコンソールに表示されません。</span><span class="sxs-lookup"><span data-stu-id="70e44-208">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70e44-209">応答グループの構成</span><span class="sxs-lookup"><span data-stu-id="70e44-209">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="70e44-210">プライマリプールで所有されている応答グループは、プライマリプールのバックエンドデータベースの可用性に応じて表示できますが、変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="70e44-210">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="70e44-211">バックアッププールが所有する応答グループは、表示および変更できます。</span><span class="sxs-lookup"><span data-stu-id="70e44-211">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="70e44-212">インポートされた応答グループは、Lync Server コントロールパネルまたは応答グループ構成ツールを使用して表示することはできませんが、Lync Server 管理シェルコマンドレットを使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="70e44-212">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="70e44-213">プライマリプールが所有する応答グループは、表示および変更できます。</span><span class="sxs-lookup"><span data-stu-id="70e44-213">Response groups owned by the primary pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="70e44-214">バックアッププールが所有する応答グループは、表示および変更できます。</span><span class="sxs-lookup"><span data-stu-id="70e44-214">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="70e44-215">インポートされた応答グループは、Lync Server コントロールパネルまたは応答グループ構成ツールを使用して表示することはできませんが、Lync Server 管理シェルコマンドレットを使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="70e44-215">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
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

