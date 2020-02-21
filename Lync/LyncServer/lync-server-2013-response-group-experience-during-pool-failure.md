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
ms.openlocfilehash: 2beb0a914fe5a2880926872ed1cab365fac988f0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182950"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="e9f23-102">Lync Server 2013 でのプール障害時の応答グループの動作</span><span class="sxs-lookup"><span data-stu-id="e9f23-102">Response group experience in Lync Server 2013 during pool failure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9f23-103">_**トピックの最終更新日:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="e9f23-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="e9f23-104">このセクションでは、次の各段階で応答グループのアクティビティへの影響について詳細に説明します。</span><span class="sxs-lookup"><span data-stu-id="e9f23-104">This section describes in detail how response group activity is affected in the following stages:</span></span>

  - <span data-ttu-id="e9f23-105">プライマリプールで停止が発生したが、フェールオーバーがまだ開始されていない。</span><span class="sxs-lookup"><span data-stu-id="e9f23-105">An outage occurs in the primary pool, but failover is not yet initiated.</span></span>

  - <span data-ttu-id="e9f23-106">サービスがバックアッププールにフェールオーバーされます。</span><span class="sxs-lookup"><span data-stu-id="e9f23-106">Service is failed over to the backup pool.</span></span>

  - <span data-ttu-id="e9f23-107">サービスがプライマリプールにフェールバックされます。</span><span class="sxs-lookup"><span data-stu-id="e9f23-107">Service is failed back to the primary pool.</span></span>

<div>

## <a name="user-experience-when-outage-occurs"></a><span data-ttu-id="e9f23-108">停止時のユーザーの作業状況</span><span class="sxs-lookup"><span data-stu-id="e9f23-108">User Experience When Outage Occurs</span></span>

<span data-ttu-id="e9f23-109">プールまたはサイトの停止が発生しても、管理者がまだフェールオーバーを開始していない場合、応答グループのアクティビティは次の表に示すように処理されます。</span><span class="sxs-lookup"><span data-stu-id="e9f23-109">When a pool or site outage occurs, but the administrator has not yet initiated failover, response group activity is handled as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e9f23-110">障害復旧時に、プライマリプール応答グループが回復時にバックアッププールにインポートされたかどうかによって、呼び出しの動作が異なります。</span><span class="sxs-lookup"><span data-stu-id="e9f23-110">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="e9f23-111">次の表では、インポートされた応答グループへの参照は、障害復旧モード中にプライマリプール応答グループがバックアッププールにインポートされたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="e9f23-111">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="outage-occurs"></a><span data-ttu-id="e9f23-112">停止が発生する</span><span class="sxs-lookup"><span data-stu-id="e9f23-112">Outage Occurs</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e9f23-113">通話またはユーザーの操作の種類</span><span class="sxs-lookup"><span data-stu-id="e9f23-113">Type of call or user action</span></span></th>
<th><span data-ttu-id="e9f23-114">停止中</span><span class="sxs-lookup"><span data-stu-id="e9f23-114">During outage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e9f23-115">エージェントに接続された通話</span><span class="sxs-lookup"><span data-stu-id="e9f23-115">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e9f23-116">通常の通話は接続されたままです。</span><span class="sxs-lookup"><span data-stu-id="e9f23-116">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="e9f23-117">匿名呼び出しは切断されます。</span><span class="sxs-lookup"><span data-stu-id="e9f23-117">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9f23-118">エージェントにまだ接続されていない呼び出し中</span><span class="sxs-lookup"><span data-stu-id="e9f23-118">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="e9f23-119">通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="e9f23-119">Calls are disconnected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9f23-120">新しい通話</span><span class="sxs-lookup"><span data-stu-id="e9f23-120">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e9f23-121">通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="e9f23-121">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="e9f23-122">応答グループがインポートされた場合、通話はバックアッププールに接続されますが、プライマリプールに所属するエージェントには到達できません。</span><span class="sxs-lookup"><span data-stu-id="e9f23-122">If response groups were imported, calls connect to backup pool, but agents homed in primary pool are unreachable.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9f23-123">応答グループの代理としてのエージェント呼び出し</span><span class="sxs-lookup"><span data-stu-id="e9f23-123">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="e9f23-124">この段階では機能は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="e9f23-124">Feature is disabled during this stage.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9f23-125">エージェントのサインインとエージェントの情報</span><span class="sxs-lookup"><span data-stu-id="e9f23-125">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e9f23-126">プライマリプールが所有するエージェントグループはエージェントコンソールで表示できますが、エージェントはサインインできません。</span><span class="sxs-lookup"><span data-stu-id="e9f23-126">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="e9f23-127">バックアッププールが所有するエージェントグループはエージェントコンソールで表示でき、エージェントはサインインできます。</span><span class="sxs-lookup"><span data-stu-id="e9f23-127">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="e9f23-128">インポートされたエージェントグループはエージェントコンソールに表示されません。</span><span class="sxs-lookup"><span data-stu-id="e9f23-128">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9f23-129">応答グループの構成</span><span class="sxs-lookup"><span data-stu-id="e9f23-129">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e9f23-130">プライマリプールで所有されている応答グループは、プライマリプールのバックエンドデータベースの可用性に応じて表示できますが、変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="e9f23-130">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="e9f23-131">バックアッププールが所有する応答グループは、表示および変更できます。</span><span class="sxs-lookup"><span data-stu-id="e9f23-131">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="e9f23-132">インポートされた応答グループは、Lync Server コントロールパネルまたは応答グループ構成ツールを使用して表示することはできませんが、Lync Server 管理シェルコマンドレットを使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="e9f23-132">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="e9f23-133">フェールオーバー中のユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="e9f23-133">User Experience During Failover</span></span>

<span data-ttu-id="e9f23-134">管理者がバックアッププールへのフェールオーバーを起動すると、次の表に示すように、応答グループのアクティビティはフェールオーバー中およびフェールオーバー後に処理されます。</span><span class="sxs-lookup"><span data-stu-id="e9f23-134">When an administrator invokes failover to a backup pool, response group activity is handled during and after the failover as described in the following table.</span></span> <span data-ttu-id="e9f23-135">最初の列は、発生する可能性のあるアクティビティの種類を示しています。</span><span class="sxs-lookup"><span data-stu-id="e9f23-135">The first column describes the type of activity that might be taking place.</span></span> <span data-ttu-id="e9f23-136">中央の列は、バックアッププールへのフェールオーバーの短時間に各アクティビティがどのように処理されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="e9f23-136">The middle column describes how each activity is handled during the brief time that it takes to fail over to the backup pool.</span></span> <span data-ttu-id="e9f23-137">最後の列は、フェールオーバープロセスが完了し、バックアッププールがプライマリプールに対して実行された後の、期間中にアクティビティが処理される方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e9f23-137">The last column describes how the activity is handled for the duration, after the failover process is complete and the backup pool is standing in for the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e9f23-138">障害復旧時に、プライマリプール応答グループが回復時にバックアッププールにインポートされたかどうかによって、呼び出しの動作が異なります。</span><span class="sxs-lookup"><span data-stu-id="e9f23-138">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="e9f23-139">次の表では、インポートされた応答グループへの参照は、障害復旧モード中にプライマリプール応答グループがバックアッププールにインポートされたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="e9f23-139">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="failover-is-initiated"></a><span data-ttu-id="e9f23-140">フェールオーバーの開始</span><span class="sxs-lookup"><span data-stu-id="e9f23-140">Failover Is Initiated</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e9f23-141">通話またはユーザーの操作の種類</span><span class="sxs-lookup"><span data-stu-id="e9f23-141">Type of call or user action</span></span></th>
<th><span data-ttu-id="e9f23-142">フェールオーバー中</span><span class="sxs-lookup"><span data-stu-id="e9f23-142">During Failover</span></span></th>
<th><span data-ttu-id="e9f23-143">フェールオーバーの完了後</span><span class="sxs-lookup"><span data-stu-id="e9f23-143">After Failover Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e9f23-144">エージェントに接続された通話</span><span class="sxs-lookup"><span data-stu-id="e9f23-144">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e9f23-145">通常の通話は接続されたままです。</span><span class="sxs-lookup"><span data-stu-id="e9f23-145">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="e9f23-146">匿名呼び出しは切断されます。</span><span class="sxs-lookup"><span data-stu-id="e9f23-146">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="e9f23-147">通常の通話は接続されたままです。</span><span class="sxs-lookup"><span data-stu-id="e9f23-147">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="e9f23-148">インポートされた応答グループの場合、バックアッププールに到達した匿名の通話は接続したままになります。</span><span class="sxs-lookup"><span data-stu-id="e9f23-148">For imported response groups, anonymous calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9f23-149">エージェントにまだ接続されていない呼び出し中</span><span class="sxs-lookup"><span data-stu-id="e9f23-149">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="e9f23-150">通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="e9f23-150">Calls are disconnected.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e9f23-151">応答グループがインポートされなかった場合、このステータスになる通話はありません。</span><span class="sxs-lookup"><span data-stu-id="e9f23-151">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="e9f23-152">インポートされた応答グループの場合、バックアッププールに到達した通話は接続したままになります。</span><span class="sxs-lookup"><span data-stu-id="e9f23-152">For imported response groups, calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9f23-153">新しい通話</span><span class="sxs-lookup"><span data-stu-id="e9f23-153">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e9f23-154">通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="e9f23-154">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="e9f23-155">インポートされた応答グループの場合、通話はバックアッププールに接続されますが、プライマリプールに所属するエージェントには到達できません。</span><span class="sxs-lookup"><span data-stu-id="e9f23-155">For imported response groups, calls connect to the backup pool, but agents homed in the primary pool are unreachable.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="e9f23-156">応答グループがインポートされなかった場合、通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="e9f23-156">If response groups were not imported, calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="e9f23-157">インポートされた応答グループでは、通話はバックアッププールに接続されます。</span><span class="sxs-lookup"><span data-stu-id="e9f23-157">For imported response groups, calls connect to the backup pool.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9f23-158">応答グループの代理としてのエージェント呼び出し</span><span class="sxs-lookup"><span data-stu-id="e9f23-158">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="e9f23-159">この段階では機能は無効になっています</span><span class="sxs-lookup"><span data-stu-id="e9f23-159">Feature is disabled during this stage</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e9f23-160">応答グループがインポートされなかった場合、通話は失敗します。</span><span class="sxs-lookup"><span data-stu-id="e9f23-160">If response groups were not imported, calls fail.</span></span></p></li>
<li><p><span data-ttu-id="e9f23-161">インポートされた応答グループの場合、通話は成功します。</span><span class="sxs-lookup"><span data-stu-id="e9f23-161">For imported response groups, calls succeed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9f23-162">エージェントのサインインとエージェントの情報</span><span class="sxs-lookup"><span data-stu-id="e9f23-162">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e9f23-163">プライマリプールが所有するエージェントグループはエージェントコンソールで表示できますが、エージェントはサインインできません。</span><span class="sxs-lookup"><span data-stu-id="e9f23-163">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="e9f23-164">バックアッププールが所有するエージェントグループはエージェントコンソールで表示でき、エージェントはサインインできます。</span><span class="sxs-lookup"><span data-stu-id="e9f23-164">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="e9f23-165">インポートされたエージェントグループはエージェントコンソールに表示され、エージェントはサインインできます。</span><span class="sxs-lookup"><span data-stu-id="e9f23-165">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="e9f23-166">プライマリプールが所有するエージェントグループはエージェントコンソールで表示できますが、エージェントはサインインできません。</span><span class="sxs-lookup"><span data-stu-id="e9f23-166">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="e9f23-167">バックアッププールが所有するエージェントグループはエージェントコンソールで表示でき、エージェントはサインインできます。</span><span class="sxs-lookup"><span data-stu-id="e9f23-167">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="e9f23-168">インポートされたエージェントグループはエージェントコンソールに表示され、エージェントはサインインできます。</span><span class="sxs-lookup"><span data-stu-id="e9f23-168">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9f23-169">応答グループの構成</span><span class="sxs-lookup"><span data-stu-id="e9f23-169">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e9f23-170">プライマリプールで所有されている応答グループは、プライマリプールのバックエンドデータベースの可用性に応じて表示できますが、変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="e9f23-170">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="e9f23-171">バックアッププールが所有する応答グループは、表示および変更できます。</span><span class="sxs-lookup"><span data-stu-id="e9f23-171">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="e9f23-172">インポートされた応答グループは、Lync Server コントロールパネルまたは応答グループ構成ツールを使用して表示することはできませんが、Lync Server 管理シェルコマンドレットを使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="e9f23-172">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="e9f23-173">プライマリプールが所有する応答グループは、バックエンドデータベースの可用性に応じて表示できますが、変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="e9f23-173">Response groups owned by the primary pool can be viewed, depending on the availability of the back end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="e9f23-174">バックアッププールが所有する応答グループは、表示および変更できます。</span><span class="sxs-lookup"><span data-stu-id="e9f23-174">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="e9f23-175">インポートされた応答グループは、Lync Server コントロールパネルまたは応答グループ構成ツールを使用して表示することはできませんが、Lync Server 管理シェルコマンドレットを使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="e9f23-175">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="e9f23-176">フェールバック中のユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="e9f23-176">User Experience During Failback</span></span>

<span data-ttu-id="e9f23-177">管理者がプライマリプールへのフェールバックを起動すると、次の表に示すように、応答グループのアクティビティはフェールバック中およびフェールバック後に処理されます。</span><span class="sxs-lookup"><span data-stu-id="e9f23-177">When an administrator invokes failback to the primary pool, response group activity is handled during and after the failback as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e9f23-178">障害復旧時に、プライマリプール応答グループが回復時にバックアッププールにインポートされたかどうかによって、呼び出しの動作が異なります。</span><span class="sxs-lookup"><span data-stu-id="e9f23-178">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="e9f23-179">次の表では、インポートされた応答グループへの参照は、障害復旧モード中にプライマリプール応答グループがバックアッププールにインポートされたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="e9f23-179">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="call-handling-in-failback"></a><span data-ttu-id="e9f23-180">フェールバックにおける通話の処理</span><span class="sxs-lookup"><span data-stu-id="e9f23-180">Call Handling in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e9f23-181">通話またはユーザーの操作の種類</span><span class="sxs-lookup"><span data-stu-id="e9f23-181">Type of call or user action</span></span></th>
<th><span data-ttu-id="e9f23-182">フェールバック中</span><span class="sxs-lookup"><span data-stu-id="e9f23-182">During Failback</span></span></th>
<th><span data-ttu-id="e9f23-183">フェールバックの完了後</span><span class="sxs-lookup"><span data-stu-id="e9f23-183">After Failback Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e9f23-184">エージェントに接続された通話</span><span class="sxs-lookup"><span data-stu-id="e9f23-184">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e9f23-185">通常の通話は接続されたままです。</span><span class="sxs-lookup"><span data-stu-id="e9f23-185">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="e9f23-186">応答グループがインポートされなかった場合、このステータスになる匿名通話はありません。</span><span class="sxs-lookup"><span data-stu-id="e9f23-186">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="e9f23-187">インポートされた応答グループの場合、匿名通話は接続したままになります。</span><span class="sxs-lookup"><span data-stu-id="e9f23-187">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="e9f23-188">通常の通話は接続されたままです。</span><span class="sxs-lookup"><span data-stu-id="e9f23-188">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="e9f23-189">応答グループがインポートされなかった場合、このステータスになる匿名通話はありません。</span><span class="sxs-lookup"><span data-stu-id="e9f23-189">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="e9f23-190">インポートされた応答グループの場合、匿名通話は接続したままになります。</span><span class="sxs-lookup"><span data-stu-id="e9f23-190">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9f23-191">エージェントにまだ接続されていない呼び出し中</span><span class="sxs-lookup"><span data-stu-id="e9f23-191">In progress calls not yet connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e9f23-192">応答グループがインポートされなかった場合、このステータスになる通話はありません。</span><span class="sxs-lookup"><span data-stu-id="e9f23-192">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="e9f23-193">インポートされた応答グループの場合、通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="e9f23-193">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="e9f23-194">応答グループがインポートされなかった場合、このステータスになる通話はありません。</span><span class="sxs-lookup"><span data-stu-id="e9f23-194">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="e9f23-195">インポートされた応答グループの場合、通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="e9f23-195">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9f23-196">新しい通話</span><span class="sxs-lookup"><span data-stu-id="e9f23-196">New calls</span></span></p></td>
<td><p><span data-ttu-id="e9f23-197">通話はプライマリプールに接続されますが、プライマリプールに所属するエージェントには到達できません。</span><span class="sxs-lookup"><span data-stu-id="e9f23-197">Calls connect to the primary pool, but agents homed in the primary pool are unreachable.</span></span></p></td>
<td><p><span data-ttu-id="e9f23-198">通話はプライマリプールに接続されます。</span><span class="sxs-lookup"><span data-stu-id="e9f23-198">Calls connect to the primary pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9f23-199">応答グループの代理としてのエージェント呼び出し</span><span class="sxs-lookup"><span data-stu-id="e9f23-199">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="e9f23-200">この段階では機能は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="e9f23-200">Feature is disabled during this stage.</span></span></p></td>
<td><p><span data-ttu-id="e9f23-201">呼び出しは成功します。</span><span class="sxs-lookup"><span data-stu-id="e9f23-201">Calls succeed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9f23-202">エージェントのサインインとエージェントの情報</span><span class="sxs-lookup"><span data-stu-id="e9f23-202">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e9f23-203">プライマリプールが所有するエージェントグループはエージェントコンソールで表示できますが、エージェントはサインインできません。</span><span class="sxs-lookup"><span data-stu-id="e9f23-203">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="e9f23-204">バックアッププールが所有するエージェントグループはエージェントコンソールで表示でき、エージェントはサインインできます。</span><span class="sxs-lookup"><span data-stu-id="e9f23-204">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="e9f23-205">インポートされたエージェントグループはエージェントコンソールに表示され、エージェントはサインインできます。</span><span class="sxs-lookup"><span data-stu-id="e9f23-205">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="e9f23-206">プライマリプールが所有するエージェントグループはエージェントコンソールで表示でき、エージェントはサインインできます。</span><span class="sxs-lookup"><span data-stu-id="e9f23-206">Agent groups owned by the primary pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="e9f23-207">バックアッププールが所有するエージェントグループはエージェントコンソールで表示でき、エージェントはサインインできます。</span><span class="sxs-lookup"><span data-stu-id="e9f23-207">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="e9f23-208">インポートされたエージェントグループはエージェントコンソールに表示されません。</span><span class="sxs-lookup"><span data-stu-id="e9f23-208">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9f23-209">応答グループの構成</span><span class="sxs-lookup"><span data-stu-id="e9f23-209">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e9f23-210">プライマリプールで所有されている応答グループは、プライマリプールのバックエンドデータベースの可用性に応じて表示できますが、変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="e9f23-210">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="e9f23-211">バックアッププールが所有する応答グループは、表示および変更できます。</span><span class="sxs-lookup"><span data-stu-id="e9f23-211">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="e9f23-212">インポートされた応答グループは、Lync Server コントロールパネルまたは応答グループ構成ツールを使用して表示することはできませんが、Lync Server 管理シェルコマンドレットを使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="e9f23-212">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="e9f23-213">プライマリプールが所有する応答グループは、表示および変更できます。</span><span class="sxs-lookup"><span data-stu-id="e9f23-213">Response groups owned by the primary pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="e9f23-214">バックアッププールが所有する応答グループは、表示および変更できます。</span><span class="sxs-lookup"><span data-stu-id="e9f23-214">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="e9f23-215">インポートされた応答グループは、Lync Server コントロールパネルまたは応答グループ構成ツールを使用して表示することはできませんが、Lync Server 管理シェルコマンドレットを使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="e9f23-215">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
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

