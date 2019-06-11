---
title: Lync Server 2013 のプール障害時の応答グループのエクスペリエンス
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response group experience during pool failure
ms:assetid: 4e00fb38-64b1-4fd9-903d-7639177bc303
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204886(v=OCS.15)
ms:contentKeyID: 48184116
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90911bebc7c3e60847f5b3fcb8f69523697af0f8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823295"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="407cd-102">Lync Server 2013 でのプール障害時の応答グループのエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="407cd-102">Response group experience in Lync Server 2013 during pool failure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="407cd-103">_**最終更新日:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="407cd-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="407cd-104">このセクションでは、次のステージでの応答グループのアクティビティへの影響について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="407cd-104">This section describes in detail how response group activity is affected in the following stages:</span></span>

  - <span data-ttu-id="407cd-105">プライマリプールで障害が発生しましたが、フェイルオーバーはまだ開始されていません。</span><span class="sxs-lookup"><span data-stu-id="407cd-105">An outage occurs in the primary pool, but failover is not yet initiated.</span></span>

  - <span data-ttu-id="407cd-106">サービスはバックアッププールにフェールオーバーされました。</span><span class="sxs-lookup"><span data-stu-id="407cd-106">Service is failed over to the backup pool.</span></span>

  - <span data-ttu-id="407cd-107">サービスがプライマリプールに戻されました。</span><span class="sxs-lookup"><span data-stu-id="407cd-107">Service is failed back to the primary pool.</span></span>

<div>

## <a name="user-experience-when-outage-occurs"></a><span data-ttu-id="407cd-108">障害が発生したときのユーザーエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="407cd-108">User Experience When Outage Occurs</span></span>

<span data-ttu-id="407cd-109">プールまたはサイトの障害が発生したときに、管理者がフェールオーバーを開始していない場合は、次の表で説明するように、応答グループのアクティビティが処理されます。</span><span class="sxs-lookup"><span data-stu-id="407cd-109">When a pool or site outage occurs, but the administrator has not yet initiated failover, response group activity is handled as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="407cd-110">障害回復中は、プライマリプール応答グループが回復中にバックアッププールにインポートされたかどうかによって、通話の動作が異なります。</span><span class="sxs-lookup"><span data-stu-id="407cd-110">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="407cd-111">次の表では、インポートされた応答グループを参照することで、障害回復モード中にプライマリプール応答グループがバックアッププールにインポートされたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="407cd-111">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="outage-occurs"></a><span data-ttu-id="407cd-112">停止が発生する</span><span class="sxs-lookup"><span data-stu-id="407cd-112">Outage Occurs</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="407cd-113">通話の種類またはユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="407cd-113">Type of call or user action</span></span></th>
<th><span data-ttu-id="407cd-114">停止中</span><span class="sxs-lookup"><span data-stu-id="407cd-114">During outage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="407cd-115">エージェントに接続された通話</span><span class="sxs-lookup"><span data-stu-id="407cd-115">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="407cd-116">通常の通話は接続されたままです。</span><span class="sxs-lookup"><span data-stu-id="407cd-116">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="407cd-117">匿名通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="407cd-117">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="407cd-118">進行中の通話はまだエージェントに接続されていません</span><span class="sxs-lookup"><span data-stu-id="407cd-118">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="407cd-119">通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="407cd-119">Calls are disconnected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="407cd-120">新規通話</span><span class="sxs-lookup"><span data-stu-id="407cd-120">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="407cd-121">通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="407cd-121">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="407cd-122">応答グループがインポートされた場合、通話はバックアッププールに接続されますが、プライマリプールに所属しているエージェントにはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="407cd-122">If response groups were imported, calls connect to backup pool, but agents homed in primary pool are unreachable.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="407cd-123">応答グループの代理としてのエージェントの呼び出し</span><span class="sxs-lookup"><span data-stu-id="407cd-123">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="407cd-124">このステージでは、機能が無効になっています。</span><span class="sxs-lookup"><span data-stu-id="407cd-124">Feature is disabled during this stage.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="407cd-125">エージェントのサインインとエージェントの情報</span><span class="sxs-lookup"><span data-stu-id="407cd-125">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="407cd-126">プライマリプールによって所有されているエージェントグループは、エージェントコンソールで確認できますが、エージェントはサインインできません。</span><span class="sxs-lookup"><span data-stu-id="407cd-126">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="407cd-127">バックアッププールによって所有されているエージェントグループは、エージェントコンソールで確認でき、エージェントはサインインできます。</span><span class="sxs-lookup"><span data-stu-id="407cd-127">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="407cd-128">インポートされたエージェントグループは、エージェントコンソールには表示されません。</span><span class="sxs-lookup"><span data-stu-id="407cd-128">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="407cd-129">応答グループの構成</span><span class="sxs-lookup"><span data-stu-id="407cd-129">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="407cd-130">プライマリプールによって所有される応答グループは、プライマリプールのバックエンドデータベースの可用性に応じて表示できますが、変更はできません。</span><span class="sxs-lookup"><span data-stu-id="407cd-130">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="407cd-131">バックアッププールによって所有されている応答グループを表示したり、変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="407cd-131">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="407cd-132">インポートされた応答グループは、Lync Server コントロールパネルまたは応答グループ構成ツールでは表示できませんが、Lync Server 管理シェルコマンドレットを使用して構成することができます。</span><span class="sxs-lookup"><span data-stu-id="407cd-132">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="407cd-133">フェールオーバー中のユーザーエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="407cd-133">User Experience During Failover</span></span>

<span data-ttu-id="407cd-134">管理者がバックアッププールへのフェールオーバーを呼び出すと、次の表で説明するように、フェールオーバーの際に応答グループのアクティビティが処理されます。</span><span class="sxs-lookup"><span data-stu-id="407cd-134">When an administrator invokes failover to a backup pool, response group activity is handled during and after the failover as described in the following table.</span></span> <span data-ttu-id="407cd-135">最初の列は、実行される可能性があるアクティビティの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="407cd-135">The first column describes the type of activity that might be taking place.</span></span> <span data-ttu-id="407cd-136">中央の列は、バックアッププールへのフェールオーバーにかかる時間の短い間に各アクティビティが処理される方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="407cd-136">The middle column describes how each activity is handled during the brief time that it takes to fail over to the backup pool.</span></span> <span data-ttu-id="407cd-137">最後の列は、フェールオーバープロセスが完了し、バックアッププールがプライマリプールに対して有効になった後の、アクティビティが継続して処理される方法を示します。</span><span class="sxs-lookup"><span data-stu-id="407cd-137">The last column describes how the activity is handled for the duration, after the failover process is complete and the backup pool is standing in for the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="407cd-138">障害回復中は、プライマリプール応答グループが回復中にバックアッププールにインポートされたかどうかによって、通話の動作が異なります。</span><span class="sxs-lookup"><span data-stu-id="407cd-138">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="407cd-139">次の表では、インポートされた応答グループを参照することで、障害回復モード中にプライマリプール応答グループがバックアッププールにインポートされたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="407cd-139">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="failover-is-initiated"></a><span data-ttu-id="407cd-140">フェールオーバーが開始される</span><span class="sxs-lookup"><span data-stu-id="407cd-140">Failover Is Initiated</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="407cd-141">通話の種類またはユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="407cd-141">Type of call or user action</span></span></th>
<th><span data-ttu-id="407cd-142">フェールオーバー中</span><span class="sxs-lookup"><span data-stu-id="407cd-142">During Failover</span></span></th>
<th><span data-ttu-id="407cd-143">フェールオーバーの完了後</span><span class="sxs-lookup"><span data-stu-id="407cd-143">After Failover Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="407cd-144">エージェントに接続された通話</span><span class="sxs-lookup"><span data-stu-id="407cd-144">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="407cd-145">通常の通話は接続されたままです。</span><span class="sxs-lookup"><span data-stu-id="407cd-145">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="407cd-146">匿名通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="407cd-146">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="407cd-147">通常の通話は接続されたままです。</span><span class="sxs-lookup"><span data-stu-id="407cd-147">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="407cd-148">インポートした応答グループについては、バックアッププールに到達した匿名の通話が接続されたままになります。</span><span class="sxs-lookup"><span data-stu-id="407cd-148">For imported response groups, anonymous calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="407cd-149">進行中の通話はまだエージェントに接続されていません</span><span class="sxs-lookup"><span data-stu-id="407cd-149">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="407cd-150">通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="407cd-150">Calls are disconnected.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="407cd-151">応答グループがインポートされなかった場合、この状態の通話はありません。</span><span class="sxs-lookup"><span data-stu-id="407cd-151">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="407cd-152">インポートした応答グループの場合、バックアッププールに到達した通話は接続されたままになります。</span><span class="sxs-lookup"><span data-stu-id="407cd-152">For imported response groups, calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="407cd-153">新規通話</span><span class="sxs-lookup"><span data-stu-id="407cd-153">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="407cd-154">通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="407cd-154">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="407cd-155">インポートされた応答グループの場合、通話はバックアッププールに接続しますが、プライマリプールに所属するエージェントにはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="407cd-155">For imported response groups, calls connect to the backup pool, but agents homed in the primary pool are unreachable.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="407cd-156">応答グループがインポートされなかった場合、通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="407cd-156">If response groups were not imported, calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="407cd-157">インポートされた応答グループの場合、通話はバックアッププールに接続します。</span><span class="sxs-lookup"><span data-stu-id="407cd-157">For imported response groups, calls connect to the backup pool.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="407cd-158">応答グループの代理としてのエージェントの呼び出し</span><span class="sxs-lookup"><span data-stu-id="407cd-158">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="407cd-159">このステージでは機能が無効になっています</span><span class="sxs-lookup"><span data-stu-id="407cd-159">Feature is disabled during this stage</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="407cd-160">応答グループがインポートされなかった場合、通話は失敗します。</span><span class="sxs-lookup"><span data-stu-id="407cd-160">If response groups were not imported, calls fail.</span></span></p></li>
<li><p><span data-ttu-id="407cd-161">インポートされた応答グループの場合、通話は成功します。</span><span class="sxs-lookup"><span data-stu-id="407cd-161">For imported response groups, calls succeed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="407cd-162">エージェントのサインインとエージェントの情報</span><span class="sxs-lookup"><span data-stu-id="407cd-162">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="407cd-163">プライマリプールによって所有されているエージェントグループは、エージェントコンソールで確認できますが、エージェントはサインインできません。</span><span class="sxs-lookup"><span data-stu-id="407cd-163">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="407cd-164">バックアッププールによって所有されているエージェントグループは、エージェントコンソールで確認でき、エージェントはサインインできます。</span><span class="sxs-lookup"><span data-stu-id="407cd-164">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="407cd-165">インポートされたエージェントグループはエージェントコンソールに表示され、エージェントはサインインできます。</span><span class="sxs-lookup"><span data-stu-id="407cd-165">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="407cd-166">プライマリプールによって所有されているエージェントグループは、エージェントコンソールで確認できますが、エージェントはサインインできません。</span><span class="sxs-lookup"><span data-stu-id="407cd-166">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="407cd-167">バックアッププールによって所有されているエージェントグループは、エージェントコンソールで確認でき、エージェントはサインインできます。</span><span class="sxs-lookup"><span data-stu-id="407cd-167">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="407cd-168">インポートされたエージェントグループはエージェントコンソールに表示され、エージェントはサインインできます。</span><span class="sxs-lookup"><span data-stu-id="407cd-168">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="407cd-169">応答グループの構成</span><span class="sxs-lookup"><span data-stu-id="407cd-169">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="407cd-170">プライマリプールによって所有される応答グループは、プライマリプールのバックエンドデータベースの可用性に応じて表示できますが、変更はできません。</span><span class="sxs-lookup"><span data-stu-id="407cd-170">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="407cd-171">バックアッププールによって所有されている応答グループを表示したり、変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="407cd-171">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="407cd-172">インポートされた応答グループは、Lync Server コントロールパネルまたは応答グループ構成ツールでは表示できませんが、Lync Server 管理シェルコマンドレットを使用して構成することができます。</span><span class="sxs-lookup"><span data-stu-id="407cd-172">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="407cd-173">プライマリプールによって所有されている応答グループは、バックエンドデータベースの可用性によっては表示できますが、変更はできません。</span><span class="sxs-lookup"><span data-stu-id="407cd-173">Response groups owned by the primary pool can be viewed, depending on the availability of the back end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="407cd-174">バックアッププールによって所有されている応答グループを表示したり、変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="407cd-174">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="407cd-175">インポートされた応答グループは、Lync Server コントロールパネルまたは応答グループ構成ツールでは表示できませんが、Lync Server 管理シェルコマンドレットを使用して構成することができます。</span><span class="sxs-lookup"><span data-stu-id="407cd-175">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="407cd-176">フェールバック中のユーザーエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="407cd-176">User Experience During Failback</span></span>

<span data-ttu-id="407cd-177">管理者がプライマリプールへのフェールバックを起動すると、次の表で説明するように、フェールバックの際に応答グループのアクティビティが処理されます。</span><span class="sxs-lookup"><span data-stu-id="407cd-177">When an administrator invokes failback to the primary pool, response group activity is handled during and after the failback as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="407cd-178">障害回復中は、プライマリプール応答グループが回復中にバックアッププールにインポートされたかどうかによって、通話の動作が異なります。</span><span class="sxs-lookup"><span data-stu-id="407cd-178">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="407cd-179">次の表では、インポートされた応答グループを参照することで、障害回復モード中にプライマリプール応答グループがバックアッププールにインポートされたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="407cd-179">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="call-handling-in-failback"></a><span data-ttu-id="407cd-180">フェールバックでの通話の処理</span><span class="sxs-lookup"><span data-stu-id="407cd-180">Call Handling in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="407cd-181">通話の種類またはユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="407cd-181">Type of call or user action</span></span></th>
<th><span data-ttu-id="407cd-182">フェールバック中</span><span class="sxs-lookup"><span data-stu-id="407cd-182">During Failback</span></span></th>
<th><span data-ttu-id="407cd-183">フェールバックの完了後</span><span class="sxs-lookup"><span data-stu-id="407cd-183">After Failback Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="407cd-184">エージェントに接続された通話</span><span class="sxs-lookup"><span data-stu-id="407cd-184">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="407cd-185">通常の通話は接続されたままです。</span><span class="sxs-lookup"><span data-stu-id="407cd-185">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="407cd-186">応答グループがインポートされなかった場合、この状態の匿名通話はありません。</span><span class="sxs-lookup"><span data-stu-id="407cd-186">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="407cd-187">インポートした応答グループでは、匿名の通話は接続されたままになります。</span><span class="sxs-lookup"><span data-stu-id="407cd-187">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="407cd-188">通常の通話は接続されたままです。</span><span class="sxs-lookup"><span data-stu-id="407cd-188">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="407cd-189">応答グループがインポートされなかった場合、この状態の匿名通話はありません。</span><span class="sxs-lookup"><span data-stu-id="407cd-189">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="407cd-190">インポートした応答グループでは、匿名の通話は接続されたままになります。</span><span class="sxs-lookup"><span data-stu-id="407cd-190">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="407cd-191">進行中の通話はまだエージェントに接続されていません</span><span class="sxs-lookup"><span data-stu-id="407cd-191">In progress calls not yet connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="407cd-192">応答グループがインポートされなかった場合、この状態の通話はありません。</span><span class="sxs-lookup"><span data-stu-id="407cd-192">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="407cd-193">インポートされた応答グループの場合、通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="407cd-193">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="407cd-194">応答グループがインポートされなかった場合、この状態の通話はありません。</span><span class="sxs-lookup"><span data-stu-id="407cd-194">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="407cd-195">インポートされた応答グループの場合、通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="407cd-195">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="407cd-196">新規通話</span><span class="sxs-lookup"><span data-stu-id="407cd-196">New calls</span></span></p></td>
<td><p><span data-ttu-id="407cd-197">通話はプライマリプールに接続しますが、プライマリプールに所属しているエージェントにはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="407cd-197">Calls connect to the primary pool, but agents homed in the primary pool are unreachable.</span></span></p></td>
<td><p><span data-ttu-id="407cd-198">通話はプライマリプールに接続します。</span><span class="sxs-lookup"><span data-stu-id="407cd-198">Calls connect to the primary pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="407cd-199">応答グループの代理としてのエージェントの呼び出し</span><span class="sxs-lookup"><span data-stu-id="407cd-199">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="407cd-200">このステージでは、機能が無効になっています。</span><span class="sxs-lookup"><span data-stu-id="407cd-200">Feature is disabled during this stage.</span></span></p></td>
<td><p><span data-ttu-id="407cd-201">通話が成功します。</span><span class="sxs-lookup"><span data-stu-id="407cd-201">Calls succeed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="407cd-202">エージェントのサインインとエージェントの情報</span><span class="sxs-lookup"><span data-stu-id="407cd-202">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="407cd-203">プライマリプールによって所有されているエージェントグループは、エージェントコンソールで確認できますが、エージェントはサインインできません。</span><span class="sxs-lookup"><span data-stu-id="407cd-203">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="407cd-204">バックアッププールによって所有されているエージェントグループは、エージェントコンソールで確認でき、エージェントはサインインできます。</span><span class="sxs-lookup"><span data-stu-id="407cd-204">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="407cd-205">インポートされたエージェントグループはエージェントコンソールに表示され、エージェントはサインインできます。</span><span class="sxs-lookup"><span data-stu-id="407cd-205">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="407cd-206">プライマリプールによって所有されているエージェントグループは、エージェントコンソールで確認でき、エージェントはサインインできます。</span><span class="sxs-lookup"><span data-stu-id="407cd-206">Agent groups owned by the primary pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="407cd-207">バックアッププールによって所有されているエージェントグループは、エージェントコンソールで確認でき、エージェントはサインインできます。</span><span class="sxs-lookup"><span data-stu-id="407cd-207">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="407cd-208">インポートされたエージェントグループは、エージェントコンソールには表示されません。</span><span class="sxs-lookup"><span data-stu-id="407cd-208">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="407cd-209">応答グループの構成</span><span class="sxs-lookup"><span data-stu-id="407cd-209">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="407cd-210">プライマリプールによって所有される応答グループは、プライマリプールのバックエンドデータベースの可用性に応じて表示できますが、変更はできません。</span><span class="sxs-lookup"><span data-stu-id="407cd-210">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="407cd-211">バックアッププールによって所有されている応答グループを表示したり、変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="407cd-211">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="407cd-212">インポートされた応答グループは、Lync Server コントロールパネルまたは応答グループ構成ツールでは表示できませんが、Lync Server 管理シェルコマンドレットを使用して構成することができます。</span><span class="sxs-lookup"><span data-stu-id="407cd-212">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="407cd-213">プライマリプールによって所有されている応答グループを表示したり、変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="407cd-213">Response groups owned by the primary pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="407cd-214">バックアッププールによって所有されている応答グループを表示したり、変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="407cd-214">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="407cd-215">インポートされた応答グループは、Lync Server コントロールパネルまたは応答グループ構成ツールでは表示できませんが、Lync Server 管理シェルコマンドレットを使用して構成することができます。</span><span class="sxs-lookup"><span data-stu-id="407cd-215">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
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

