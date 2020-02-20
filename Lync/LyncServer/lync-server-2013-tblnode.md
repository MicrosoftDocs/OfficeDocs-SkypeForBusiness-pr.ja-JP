---
title: 'Lync Server 2013: tblNode'
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
ms.openlocfilehash: cee7c67421ae12d08e52bee1b013dfa6280472f3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142063"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblnode-in-lync-server-2013"></a><span data-ttu-id="83e15-102">Lync Server 2013 の tblNode</span><span class="sxs-lookup"><span data-stu-id="83e15-102">tblNode in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83e15-103">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="83e15-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="83e15-104">tblNode には、Lync Server 2013 コントロールパネルおよび管理コマンドレットで管理されるオブジェクトツリー (カテゴリまたはチャットルームノードを含む) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="83e15-104">tblNode contains the object tree (with category or chat room nodes) as managed in the Lync Server 2013 Control Panel and administrative cmdlets.</span></span>

### <a name="columns"></a><span data-ttu-id="83e15-105">Columns</span><span class="sxs-lookup"><span data-stu-id="83e15-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83e15-106">列</span><span class="sxs-lookup"><span data-stu-id="83e15-106">Column</span></span></th>
<th><span data-ttu-id="83e15-107">種類</span><span class="sxs-lookup"><span data-stu-id="83e15-107">Type</span></span></th>
<th><span data-ttu-id="83e15-108">説明</span><span class="sxs-lookup"><span data-stu-id="83e15-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83e15-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="83e15-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="83e15-110">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="83e15-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="83e15-111">ノード ID (一意の番号)。</span><span class="sxs-lookup"><span data-stu-id="83e15-111">Node ID (unique number).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83e15-112">Tblnode.nodeguid</span><span class="sxs-lookup"><span data-stu-id="83e15-112">nodeGuid</span></span></p></td>
<td><p><span data-ttu-id="83e15-113">NULL でない GUID</span><span class="sxs-lookup"><span data-stu-id="83e15-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="83e15-114">ノード GUID。</span><span class="sxs-lookup"><span data-stu-id="83e15-114">Node GUID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83e15-115">parentID</span><span class="sxs-lookup"><span data-stu-id="83e15-115">parentID</span></span></p></td>
<td><p><span data-ttu-id="83e15-116">int</span><span class="sxs-lookup"><span data-stu-id="83e15-116">int</span></span></p></td>
<td><p><span data-ttu-id="83e15-117">親のノード ID。</span><span class="sxs-lookup"><span data-stu-id="83e15-117">Node ID of parent.</span></span> <span data-ttu-id="83e15-118">ルートノード (ID 1 の) には、それ自体も親として含まれています。</span><span class="sxs-lookup"><span data-stu-id="83e15-118">The root node (with ID 1) includes itself as parent as well.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83e15-119">nodeType</span><span class="sxs-lookup"><span data-stu-id="83e15-119">nodeType</span></span></p></td>
<td><p><span data-ttu-id="83e15-120">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="83e15-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="83e15-121">ノードがカテゴリの場合は True。</span><span class="sxs-lookup"><span data-stu-id="83e15-121">True if the node is a category.</span></span></p>
<p><span data-ttu-id="83e15-122">False ノードがチャットルームの場合。</span><span class="sxs-lookup"><span data-stu-id="83e15-122">False if the node is a chat room.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83e15-123">ノード</span><span class="sxs-lookup"><span data-stu-id="83e15-123">nodeName</span></span></p></td>
<td><p><span data-ttu-id="83e15-124">NULL でない nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="83e15-124">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="83e15-125">ノード名。</span><span class="sxs-lookup"><span data-stu-id="83e15-125">Node name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83e15-126">nodeDesc</span><span class="sxs-lookup"><span data-stu-id="83e15-126">nodeDesc</span></span></p></td>
<td><p><span data-ttu-id="83e15-127">NULL でない nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="83e15-127">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="83e15-128">ノードの説明。</span><span class="sxs-lookup"><span data-stu-id="83e15-128">Node description.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83e15-129">invite</span><span class="sxs-lookup"><span data-stu-id="83e15-129">invite</span></span></p></td>
<td><p><span data-ttu-id="83e15-130">若干</span><span class="sxs-lookup"><span data-stu-id="83e15-130">bit</span></span></p></td>
<td><p><span data-ttu-id="83e15-131">カテゴリの場合:</span><span class="sxs-lookup"><span data-stu-id="83e15-131">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="83e15-132">招待がオンの場合は True。</span><span class="sxs-lookup"><span data-stu-id="83e15-132">True if invites are on.</span></span></p></li>
<li><p><span data-ttu-id="83e15-133">招待がオフの場合は False。</span><span class="sxs-lookup"><span data-stu-id="83e15-133">False if invites are off.</span></span></p></li>
</ul>
<p><span data-ttu-id="83e15-134">ルームの場合:</span><span class="sxs-lookup"><span data-stu-id="83e15-134">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="83e15-135">招待がオフの場合は False (親カテゴリは上書きされます)。</span><span class="sxs-lookup"><span data-stu-id="83e15-135">False if invites are off (overrides the parent category).</span></span></p></li>
<li><p><span data-ttu-id="83e15-136">招待の設定が親カテゴリから継承されている場合は Null。</span><span class="sxs-lookup"><span data-stu-id="83e15-136">Null if the invites setting is inherited from the parent category.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83e15-137">ログオン</span><span class="sxs-lookup"><span data-stu-id="83e15-137">logged</span></span></p></td>
<td><p><span data-ttu-id="83e15-138">若干</span><span class="sxs-lookup"><span data-stu-id="83e15-138">bit</span></span></p></td>
<td><p><span data-ttu-id="83e15-139">カテゴリの場合:</span><span class="sxs-lookup"><span data-stu-id="83e15-139">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="83e15-140">チャット履歴がオンの場合は True。</span><span class="sxs-lookup"><span data-stu-id="83e15-140">True if chat history is on.</span></span></p></li>
<li><p><span data-ttu-id="83e15-141">チャット履歴がオフの場合は False。</span><span class="sxs-lookup"><span data-stu-id="83e15-141">False if chat history is off.</span></span></p></li>
</ul>
<p><span data-ttu-id="83e15-142">ルームの場合:</span><span class="sxs-lookup"><span data-stu-id="83e15-142">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="83e15-143">Null。</span><span class="sxs-lookup"><span data-stu-id="83e15-143">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83e15-144">filePost</span><span class="sxs-lookup"><span data-stu-id="83e15-144">filePost</span></span></p></td>
<td><p><span data-ttu-id="83e15-145">若干</span><span class="sxs-lookup"><span data-stu-id="83e15-145">bit</span></span></p></td>
<td><p><span data-ttu-id="83e15-146">カテゴリの場合:</span><span class="sxs-lookup"><span data-stu-id="83e15-146">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="83e15-147">ファイルのアップロードが許可されている場合は True。</span><span class="sxs-lookup"><span data-stu-id="83e15-147">True if file uploads are allowed.</span></span></p></li>
<li><p><span data-ttu-id="83e15-148">ファイルのアップロードが許可されていない場合は False。</span><span class="sxs-lookup"><span data-stu-id="83e15-148">False if file uploads are disallowed.</span></span></p></li>
</ul>
<p><span data-ttu-id="83e15-149">ルームの場合:</span><span class="sxs-lookup"><span data-stu-id="83e15-149">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="83e15-150">Null。</span><span class="sxs-lookup"><span data-stu-id="83e15-150">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83e15-151">党</span><span class="sxs-lookup"><span data-stu-id="83e15-151">disabled</span></span></p></td>
<td><p><span data-ttu-id="83e15-152">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="83e15-152">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="83e15-153">チャットルームが無効になっている場合は True。</span><span class="sxs-lookup"><span data-stu-id="83e15-153">True if the chat room is disabled.</span></span> <span data-ttu-id="83e15-154">チャットルームにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="83e15-154">Applies only to chat rooms.</span></span> <span data-ttu-id="83e15-155">(カテゴリの場合は False)。</span><span class="sxs-lookup"><span data-stu-id="83e15-155">(False for categories.)</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83e15-156">behavior</span><span class="sxs-lookup"><span data-stu-id="83e15-156">behavior</span></span></p></td>
<td><p><span data-ttu-id="83e15-157">NULL でない smallint</span><span class="sxs-lookup"><span data-stu-id="83e15-157">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="83e15-158">動作 (EnumValue テーブルで検索):</span><span class="sxs-lookup"><span data-stu-id="83e15-158">Behavior (looked up in EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="83e15-159">4: 標準 (通常のチャットルーム)。</span><span class="sxs-lookup"><span data-stu-id="83e15-159">4: Normal (normal chat rooms).</span></span></p></li>
<li><p><span data-ttu-id="83e15-160">5: 大会議室 (大会議室のチャットルーム、発表者のみが投稿可能)。</span><span class="sxs-lookup"><span data-stu-id="83e15-160">5: Auditorium (auditorium chat rooms, only presenters can contribute).</span></span></p></li>
</ul>
<p><span data-ttu-id="83e15-161">チャットルームにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="83e15-161">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83e15-162">visibility</span><span class="sxs-lookup"><span data-stu-id="83e15-162">visibility</span></span></p></td>
<td><p><span data-ttu-id="83e15-163">NULL でない smallint</span><span class="sxs-lookup"><span data-stu-id="83e15-163">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="83e15-164">可視性 (EnumValue テーブルで検索):</span><span class="sxs-lookup"><span data-stu-id="83e15-164">Visibility (looked up on EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="83e15-165">2: Private</span><span class="sxs-lookup"><span data-stu-id="83e15-165">2: Private</span></span></p></li>
<li><p><span data-ttu-id="83e15-166">3: スコープ</span><span class="sxs-lookup"><span data-stu-id="83e15-166">3: Scoped</span></span></p></li>
<li><p><span data-ttu-id="83e15-167">6: 開く</span><span class="sxs-lookup"><span data-stu-id="83e15-167">6: Open</span></span></p></li>
</ul>
<p><span data-ttu-id="83e15-168">チャットルームにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="83e15-168">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83e15-169">Tblsiopwhitelist.siopid</span><span class="sxs-lookup"><span data-stu-id="83e15-169">siopID</span></span></p></td>
<td><p><span data-ttu-id="83e15-170">GUID</span><span class="sxs-lookup"><span data-stu-id="83e15-170">GUID</span></span></p></td>
<td><p><span data-ttu-id="83e15-171">アドインがこのチャットルームに関連付けられている場合は、アドインの GUID。</span><span class="sxs-lookup"><span data-stu-id="83e15-171">Add-In GUID if an add-in is associated with this chat room.</span></span> <span data-ttu-id="83e15-172">(カテゴリにはアドインはありません。)</span><span class="sxs-lookup"><span data-stu-id="83e15-172">(Categories do not have add-ins.)</span></span></p>
<p><span data-ttu-id="83e15-173">アドイン情報は、SiopWhiteList リストテーブルで検索されます。</span><span class="sxs-lookup"><span data-stu-id="83e15-173">The add-in information is looked up in SiopWhiteList table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83e15-174">nodeAddedBy</span><span class="sxs-lookup"><span data-stu-id="83e15-174">nodeAddedBy</span></span></p></td>
<td><p><span data-ttu-id="83e15-175">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="83e15-175">int, not null</span></span></p></td>
<td><p><span data-ttu-id="83e15-176">このノードを作成したプリンシパルの ID。</span><span class="sxs-lookup"><span data-stu-id="83e15-176">ID of the principal that created this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83e15-177">nodeAddedOn</span><span class="sxs-lookup"><span data-stu-id="83e15-177">nodeAddedOn</span></span></p></td>
<td><p><span data-ttu-id="83e15-178">NULL でない bigint</span><span class="sxs-lookup"><span data-stu-id="83e15-178">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="83e15-179">ノード作成のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="83e15-179">Time stamp of the node creation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83e15-180">nodeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="83e15-180">nodeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="83e15-181">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="83e15-181">int, not null</span></span></p></td>
<td><p><span data-ttu-id="83e15-182">このノードの最新の更新を行ったプリンシパルの ID。</span><span class="sxs-lookup"><span data-stu-id="83e15-182">ID of the principal that did the latest update of this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83e15-183">nodeUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="83e15-183">nodeUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="83e15-184">NULL でない bigint</span><span class="sxs-lookup"><span data-stu-id="83e15-184">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="83e15-185">このノードの最新の更新プログラムのタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="83e15-185">Time stamp of the latest update of this node.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83e15-186">purgedOn</span><span class="sxs-lookup"><span data-stu-id="83e15-186">purgedOn</span></span></p></td>
<td><p><span data-ttu-id="83e15-187">日付型</span><span class="sxs-lookup"><span data-stu-id="83e15-187">datetime</span></span></p></td>
<td><p><span data-ttu-id="83e15-188">このノードに影響を与える最新の消去操作 (tblScopedPrincipal table およびに tblprincipalrole からの範囲の削除) の時間。</span><span class="sxs-lookup"><span data-stu-id="83e15-188">Time of the latest purge operation (removal of scopes from tblScopedPrincipal table and roles from tblPrincipalRole table) that affected this node.</span></span> <span data-ttu-id="83e15-189">これは、チャットサービスの内部キャッシュ更新メカニズムによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="83e15-189">This is used by the Chat service’s internal cache update mechanism.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="83e15-190">Keys</span><span class="sxs-lookup"><span data-stu-id="83e15-190">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83e15-191">列</span><span class="sxs-lookup"><span data-stu-id="83e15-191">Column</span></span></th>
<th><span data-ttu-id="83e15-192">説明</span><span class="sxs-lookup"><span data-stu-id="83e15-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83e15-193">nodeID</span><span class="sxs-lookup"><span data-stu-id="83e15-193">nodeID</span></span></p></td>
<td><p><span data-ttu-id="83e15-194">主キー。</span><span class="sxs-lookup"><span data-stu-id="83e15-194">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83e15-195">behavior</span><span class="sxs-lookup"><span data-stu-id="83e15-195">behavior</span></span></p></td>
<td><p><span data-ttu-id="83e15-196">TblEnumValue テーブルに参照がある外部キー。</span><span class="sxs-lookup"><span data-stu-id="83e15-196">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83e15-197">visibility</span><span class="sxs-lookup"><span data-stu-id="83e15-197">visibility</span></span></p></td>
<td><p><span data-ttu-id="83e15-198">TblEnumValue テーブルに参照がある外部キー。</span><span class="sxs-lookup"><span data-stu-id="83e15-198">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83e15-199">parentID</span><span class="sxs-lookup"><span data-stu-id="83e15-199">parentID</span></span></p></td>
<td><p><span data-ttu-id="83e15-200">tblNode.nodeID テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="83e15-200">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83e15-201">Tblsiopwhitelist.siopid</span><span class="sxs-lookup"><span data-stu-id="83e15-201">siopID</span></span></p></td>
<td><p><span data-ttu-id="83e15-202">TblSiopWhiteList テーブルに参照がある外部キー。</span><span class="sxs-lookup"><span data-stu-id="83e15-202">Foreign key with lookup in tblSiopWhiteList.siopId table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

