---
title: 'Lync Server 2013: tblNode'
description: 'Lync Server 2013: tblNode。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblNode
ms:assetid: a31d2961-aa83-4286-a12e-15d279c95f19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615024(v=OCS.15)
ms:contentKeyID: 48184960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0a5d630621c32cbc54501249c7a679bf4023c60
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547553"
---
# <a name="tblnode-in-lync-server-2013"></a><span data-ttu-id="1ba54-103">Lync Server 2013 の tblNode</span><span class="sxs-lookup"><span data-stu-id="1ba54-103">tblNode in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ba54-104">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="1ba54-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="1ba54-105">tblNode には、Lync Server 2013 コントロールパネルおよび管理コマンドレットで管理されるオブジェクトツリー (カテゴリまたはチャットルームノードを含む) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1ba54-105">tblNode contains the object tree (with category or chat room nodes) as managed in the Lync Server 2013 Control Panel and administrative cmdlets.</span></span>

### <a name="columns"></a><span data-ttu-id="1ba54-106">段組み</span><span class="sxs-lookup"><span data-stu-id="1ba54-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ba54-107">Column</span><span class="sxs-lookup"><span data-stu-id="1ba54-107">Column</span></span></th>
<th><span data-ttu-id="1ba54-108">種類</span><span class="sxs-lookup"><span data-stu-id="1ba54-108">Type</span></span></th>
<th><span data-ttu-id="1ba54-109">説明</span><span class="sxs-lookup"><span data-stu-id="1ba54-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ba54-110">nodeID</span><span class="sxs-lookup"><span data-stu-id="1ba54-110">nodeID</span></span></p></td>
<td><p><span data-ttu-id="1ba54-111">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="1ba54-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="1ba54-112">ノード ID (一意の番号)。</span><span class="sxs-lookup"><span data-stu-id="1ba54-112">Node ID (unique number).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ba54-113">Tblnode.nodeguid</span><span class="sxs-lookup"><span data-stu-id="1ba54-113">nodeGuid</span></span></p></td>
<td><p><span data-ttu-id="1ba54-114">NULL でない GUID</span><span class="sxs-lookup"><span data-stu-id="1ba54-114">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="1ba54-115">ノード GUID。</span><span class="sxs-lookup"><span data-stu-id="1ba54-115">Node GUID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ba54-116">parentID</span><span class="sxs-lookup"><span data-stu-id="1ba54-116">parentID</span></span></p></td>
<td><p><span data-ttu-id="1ba54-117">int</span><span class="sxs-lookup"><span data-stu-id="1ba54-117">int</span></span></p></td>
<td><p><span data-ttu-id="1ba54-118">親のノード ID。</span><span class="sxs-lookup"><span data-stu-id="1ba54-118">Node ID of parent.</span></span> <span data-ttu-id="1ba54-119">ルートノード (ID 1 の) には、それ自体も親として含まれています。</span><span class="sxs-lookup"><span data-stu-id="1ba54-119">The root node (with ID 1) includes itself as parent as well.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ba54-120">nodeType</span><span class="sxs-lookup"><span data-stu-id="1ba54-120">nodeType</span></span></p></td>
<td><p><span data-ttu-id="1ba54-121">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="1ba54-121">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="1ba54-122">ノードがカテゴリの場合は True。</span><span class="sxs-lookup"><span data-stu-id="1ba54-122">True if the node is a category.</span></span></p>
<p><span data-ttu-id="1ba54-123">False ノードがチャットルームの場合。</span><span class="sxs-lookup"><span data-stu-id="1ba54-123">False if the node is a chat room.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ba54-124">ノード</span><span class="sxs-lookup"><span data-stu-id="1ba54-124">nodeName</span></span></p></td>
<td><p><span data-ttu-id="1ba54-125">NULL でない nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1ba54-125">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="1ba54-126">ノード名。</span><span class="sxs-lookup"><span data-stu-id="1ba54-126">Node name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ba54-127">nodeDesc</span><span class="sxs-lookup"><span data-stu-id="1ba54-127">nodeDesc</span></span></p></td>
<td><p><span data-ttu-id="1ba54-128">NULL でない nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1ba54-128">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="1ba54-129">ノードの説明。</span><span class="sxs-lookup"><span data-stu-id="1ba54-129">Node description.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ba54-130">invite</span><span class="sxs-lookup"><span data-stu-id="1ba54-130">invite</span></span></p></td>
<td><p><span data-ttu-id="1ba54-131">若干</span><span class="sxs-lookup"><span data-stu-id="1ba54-131">bit</span></span></p></td>
<td><p><span data-ttu-id="1ba54-132">カテゴリの場合:</span><span class="sxs-lookup"><span data-stu-id="1ba54-132">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="1ba54-133">招待がオンの場合は True。</span><span class="sxs-lookup"><span data-stu-id="1ba54-133">True if invites are on.</span></span></p></li>
<li><p><span data-ttu-id="1ba54-134">招待がオフの場合は False。</span><span class="sxs-lookup"><span data-stu-id="1ba54-134">False if invites are off.</span></span></p></li>
</ul>
<p><span data-ttu-id="1ba54-135">ルームの場合:</span><span class="sxs-lookup"><span data-stu-id="1ba54-135">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="1ba54-136">招待がオフの場合は False (親カテゴリは上書きされます)。</span><span class="sxs-lookup"><span data-stu-id="1ba54-136">False if invites are off (overrides the parent category).</span></span></p></li>
<li><p><span data-ttu-id="1ba54-137">招待の設定が親カテゴリから継承されている場合は Null。</span><span class="sxs-lookup"><span data-stu-id="1ba54-137">Null if the invites setting is inherited from the parent category.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ba54-138">ログオン</span><span class="sxs-lookup"><span data-stu-id="1ba54-138">logged</span></span></p></td>
<td><p><span data-ttu-id="1ba54-139">若干</span><span class="sxs-lookup"><span data-stu-id="1ba54-139">bit</span></span></p></td>
<td><p><span data-ttu-id="1ba54-140">カテゴリの場合:</span><span class="sxs-lookup"><span data-stu-id="1ba54-140">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="1ba54-141">チャット履歴がオンの場合は True。</span><span class="sxs-lookup"><span data-stu-id="1ba54-141">True if chat history is on.</span></span></p></li>
<li><p><span data-ttu-id="1ba54-142">チャット履歴がオフの場合は False。</span><span class="sxs-lookup"><span data-stu-id="1ba54-142">False if chat history is off.</span></span></p></li>
</ul>
<p><span data-ttu-id="1ba54-143">ルームの場合:</span><span class="sxs-lookup"><span data-stu-id="1ba54-143">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="1ba54-144">Null。</span><span class="sxs-lookup"><span data-stu-id="1ba54-144">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ba54-145">filePost</span><span class="sxs-lookup"><span data-stu-id="1ba54-145">filePost</span></span></p></td>
<td><p><span data-ttu-id="1ba54-146">若干</span><span class="sxs-lookup"><span data-stu-id="1ba54-146">bit</span></span></p></td>
<td><p><span data-ttu-id="1ba54-147">カテゴリの場合:</span><span class="sxs-lookup"><span data-stu-id="1ba54-147">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="1ba54-148">ファイルのアップロードが許可されている場合は True。</span><span class="sxs-lookup"><span data-stu-id="1ba54-148">True if file uploads are allowed.</span></span></p></li>
<li><p><span data-ttu-id="1ba54-149">ファイルのアップロードが許可されていない場合は False。</span><span class="sxs-lookup"><span data-stu-id="1ba54-149">False if file uploads are disallowed.</span></span></p></li>
</ul>
<p><span data-ttu-id="1ba54-150">ルームの場合:</span><span class="sxs-lookup"><span data-stu-id="1ba54-150">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="1ba54-151">Null。</span><span class="sxs-lookup"><span data-stu-id="1ba54-151">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ba54-152">党</span><span class="sxs-lookup"><span data-stu-id="1ba54-152">disabled</span></span></p></td>
<td><p><span data-ttu-id="1ba54-153">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="1ba54-153">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="1ba54-154">チャットルームが無効になっている場合は True。</span><span class="sxs-lookup"><span data-stu-id="1ba54-154">True if the chat room is disabled.</span></span> <span data-ttu-id="1ba54-155">チャットルームにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="1ba54-155">Applies only to chat rooms.</span></span> <span data-ttu-id="1ba54-156">(カテゴリの場合は False)。</span><span class="sxs-lookup"><span data-stu-id="1ba54-156">(False for categories.)</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ba54-157">behavior</span><span class="sxs-lookup"><span data-stu-id="1ba54-157">behavior</span></span></p></td>
<td><p><span data-ttu-id="1ba54-158">NULL でない smallint</span><span class="sxs-lookup"><span data-stu-id="1ba54-158">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="1ba54-159">動作 (EnumValue テーブルで検索):</span><span class="sxs-lookup"><span data-stu-id="1ba54-159">Behavior (looked up in EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="1ba54-160">4: 標準 (通常のチャットルーム)。</span><span class="sxs-lookup"><span data-stu-id="1ba54-160">4: Normal (normal chat rooms).</span></span></p></li>
<li><p><span data-ttu-id="1ba54-161">5: 大会議室 (大会議室のチャットルーム、発表者のみが投稿可能)。</span><span class="sxs-lookup"><span data-stu-id="1ba54-161">5: Auditorium (auditorium chat rooms, only presenters can contribute).</span></span></p></li>
</ul>
<p><span data-ttu-id="1ba54-162">チャットルームにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="1ba54-162">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ba54-163">visibility</span><span class="sxs-lookup"><span data-stu-id="1ba54-163">visibility</span></span></p></td>
<td><p><span data-ttu-id="1ba54-164">NULL でない smallint</span><span class="sxs-lookup"><span data-stu-id="1ba54-164">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="1ba54-165">可視性 (EnumValue テーブルで検索):</span><span class="sxs-lookup"><span data-stu-id="1ba54-165">Visibility (looked up on EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="1ba54-166">2: Private</span><span class="sxs-lookup"><span data-stu-id="1ba54-166">2: Private</span></span></p></li>
<li><p><span data-ttu-id="1ba54-167">3: スコープ</span><span class="sxs-lookup"><span data-stu-id="1ba54-167">3: Scoped</span></span></p></li>
<li><p><span data-ttu-id="1ba54-168">6: 開く</span><span class="sxs-lookup"><span data-stu-id="1ba54-168">6: Open</span></span></p></li>
</ul>
<p><span data-ttu-id="1ba54-169">チャットルームにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="1ba54-169">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ba54-170">Tblsiopwhitelist.siopid</span><span class="sxs-lookup"><span data-stu-id="1ba54-170">siopID</span></span></p></td>
<td><p><span data-ttu-id="1ba54-171">GUID</span><span class="sxs-lookup"><span data-stu-id="1ba54-171">GUID</span></span></p></td>
<td><p><span data-ttu-id="1ba54-172">アドインがこのチャットルームに関連付けられている場合は Add-In GUID。</span><span class="sxs-lookup"><span data-stu-id="1ba54-172">Add-In GUID if an add-in is associated with this chat room.</span></span> <span data-ttu-id="1ba54-173">(カテゴリにはアドインはありません。)</span><span class="sxs-lookup"><span data-stu-id="1ba54-173">(Categories do not have add-ins.)</span></span></p>
<p><span data-ttu-id="1ba54-174">アドイン情報は、SiopWhiteList リストテーブルで検索されます。</span><span class="sxs-lookup"><span data-stu-id="1ba54-174">The add-in information is looked up in SiopWhiteList table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ba54-175">nodeAddedBy</span><span class="sxs-lookup"><span data-stu-id="1ba54-175">nodeAddedBy</span></span></p></td>
<td><p><span data-ttu-id="1ba54-176">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="1ba54-176">int, not null</span></span></p></td>
<td><p><span data-ttu-id="1ba54-177">このノードを作成したプリンシパルの ID。</span><span class="sxs-lookup"><span data-stu-id="1ba54-177">ID of the principal that created this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ba54-178">nodeAddedOn</span><span class="sxs-lookup"><span data-stu-id="1ba54-178">nodeAddedOn</span></span></p></td>
<td><p><span data-ttu-id="1ba54-179">NULL でない bigint</span><span class="sxs-lookup"><span data-stu-id="1ba54-179">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="1ba54-180">ノード作成のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="1ba54-180">Time stamp of the node creation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ba54-181">nodeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="1ba54-181">nodeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="1ba54-182">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="1ba54-182">int, not null</span></span></p></td>
<td><p><span data-ttu-id="1ba54-183">このノードの最新の更新を行ったプリンシパルの ID。</span><span class="sxs-lookup"><span data-stu-id="1ba54-183">ID of the principal that did the latest update of this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ba54-184">nodeUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="1ba54-184">nodeUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="1ba54-185">NULL でない bigint</span><span class="sxs-lookup"><span data-stu-id="1ba54-185">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="1ba54-186">このノードの最新の更新プログラムのタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="1ba54-186">Time stamp of the latest update of this node.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ba54-187">purgedOn</span><span class="sxs-lookup"><span data-stu-id="1ba54-187">purgedOn</span></span></p></td>
<td><p><span data-ttu-id="1ba54-188">日付型</span><span class="sxs-lookup"><span data-stu-id="1ba54-188">datetime</span></span></p></td>
<td><p><span data-ttu-id="1ba54-189">このノードに影響を与える最新の消去操作 (tblScopedPrincipal table およびに tblprincipalrole からの範囲の削除) の時間。</span><span class="sxs-lookup"><span data-stu-id="1ba54-189">Time of the latest purge operation (removal of scopes from tblScopedPrincipal table and roles from tblPrincipalRole table) that affected this node.</span></span> <span data-ttu-id="1ba54-190">これは、チャットサービスの内部キャッシュ更新メカニズムによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="1ba54-190">This is used by the Chat service’s internal cache update mechanism.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="1ba54-191">Keys</span><span class="sxs-lookup"><span data-stu-id="1ba54-191">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ba54-192">列</span><span class="sxs-lookup"><span data-stu-id="1ba54-192">Column</span></span></th>
<th><span data-ttu-id="1ba54-193">説明</span><span class="sxs-lookup"><span data-stu-id="1ba54-193">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ba54-194">nodeID</span><span class="sxs-lookup"><span data-stu-id="1ba54-194">nodeID</span></span></p></td>
<td><p><span data-ttu-id="1ba54-195">主キー。</span><span class="sxs-lookup"><span data-stu-id="1ba54-195">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ba54-196">behavior</span><span class="sxs-lookup"><span data-stu-id="1ba54-196">behavior</span></span></p></td>
<td><p><span data-ttu-id="1ba54-197">TblEnumValue テーブルに参照がある外部キー。</span><span class="sxs-lookup"><span data-stu-id="1ba54-197">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ba54-198">visibility</span><span class="sxs-lookup"><span data-stu-id="1ba54-198">visibility</span></span></p></td>
<td><p><span data-ttu-id="1ba54-199">TblEnumValue テーブルに参照がある外部キー。</span><span class="sxs-lookup"><span data-stu-id="1ba54-199">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ba54-200">parentID</span><span class="sxs-lookup"><span data-stu-id="1ba54-200">parentID</span></span></p></td>
<td><p><span data-ttu-id="1ba54-201">tblNode.nodeID テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="1ba54-201">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ba54-202">Tblsiopwhitelist.siopid</span><span class="sxs-lookup"><span data-stu-id="1ba54-202">siopID</span></span></p></td>
<td><p><span data-ttu-id="1ba54-203">TblSiopWhiteList テーブルに参照がある外部キー。</span><span class="sxs-lookup"><span data-stu-id="1ba54-203">Foreign key with lookup in tblSiopWhiteList.siopId table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

