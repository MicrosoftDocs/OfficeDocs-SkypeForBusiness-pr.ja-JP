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
ms.openlocfilehash: 459b5393f255ade4e510f17c11beccf2f38f7cfc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214552"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblnode-in-lync-server-2013"></a><span data-ttu-id="942f5-102">Lync Server 2013 の tblNode</span><span class="sxs-lookup"><span data-stu-id="942f5-102">tblNode in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="942f5-103">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="942f5-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="942f5-104">tblNode には、Lync Server 2013 コントロールパネルおよび管理コマンドレットで管理されるオブジェクトツリー (カテゴリまたはチャットルームノードを含む) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="942f5-104">tblNode contains the object tree (with category or chat room nodes) as managed in the Lync Server 2013 Control Panel and administrative cmdlets.</span></span>

### <a name="columns"></a><span data-ttu-id="942f5-105">Columns</span><span class="sxs-lookup"><span data-stu-id="942f5-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="942f5-106">列</span><span class="sxs-lookup"><span data-stu-id="942f5-106">Column</span></span></th>
<th><span data-ttu-id="942f5-107">種類</span><span class="sxs-lookup"><span data-stu-id="942f5-107">Type</span></span></th>
<th><span data-ttu-id="942f5-108">説明</span><span class="sxs-lookup"><span data-stu-id="942f5-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="942f5-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="942f5-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="942f5-110">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="942f5-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="942f5-111">ノード ID (一意の番号)。</span><span class="sxs-lookup"><span data-stu-id="942f5-111">Node ID (unique number).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="942f5-112">Tblnode.nodeguid</span><span class="sxs-lookup"><span data-stu-id="942f5-112">nodeGuid</span></span></p></td>
<td><p><span data-ttu-id="942f5-113">NULL でない GUID</span><span class="sxs-lookup"><span data-stu-id="942f5-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="942f5-114">ノード GUID。</span><span class="sxs-lookup"><span data-stu-id="942f5-114">Node GUID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="942f5-115">parentID</span><span class="sxs-lookup"><span data-stu-id="942f5-115">parentID</span></span></p></td>
<td><p><span data-ttu-id="942f5-116">int</span><span class="sxs-lookup"><span data-stu-id="942f5-116">int</span></span></p></td>
<td><p><span data-ttu-id="942f5-117">親のノード ID。</span><span class="sxs-lookup"><span data-stu-id="942f5-117">Node ID of parent.</span></span> <span data-ttu-id="942f5-118">ルートノード (ID 1 の) には、それ自体も親として含まれています。</span><span class="sxs-lookup"><span data-stu-id="942f5-118">The root node (with ID 1) includes itself as parent as well.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="942f5-119">nodeType</span><span class="sxs-lookup"><span data-stu-id="942f5-119">nodeType</span></span></p></td>
<td><p><span data-ttu-id="942f5-120">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="942f5-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="942f5-121">ノードがカテゴリの場合は True。</span><span class="sxs-lookup"><span data-stu-id="942f5-121">True if the node is a category.</span></span></p>
<p><span data-ttu-id="942f5-122">False ノードがチャットルームの場合。</span><span class="sxs-lookup"><span data-stu-id="942f5-122">False if the node is a chat room.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="942f5-123">ノード</span><span class="sxs-lookup"><span data-stu-id="942f5-123">nodeName</span></span></p></td>
<td><p><span data-ttu-id="942f5-124">NULL でない nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="942f5-124">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="942f5-125">ノード名。</span><span class="sxs-lookup"><span data-stu-id="942f5-125">Node name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="942f5-126">nodeDesc</span><span class="sxs-lookup"><span data-stu-id="942f5-126">nodeDesc</span></span></p></td>
<td><p><span data-ttu-id="942f5-127">NULL でない nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="942f5-127">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="942f5-128">ノードの説明。</span><span class="sxs-lookup"><span data-stu-id="942f5-128">Node description.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="942f5-129">invite</span><span class="sxs-lookup"><span data-stu-id="942f5-129">invite</span></span></p></td>
<td><p><span data-ttu-id="942f5-130">若干</span><span class="sxs-lookup"><span data-stu-id="942f5-130">bit</span></span></p></td>
<td><p><span data-ttu-id="942f5-131">カテゴリの場合:</span><span class="sxs-lookup"><span data-stu-id="942f5-131">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="942f5-132">招待がオンの場合は True。</span><span class="sxs-lookup"><span data-stu-id="942f5-132">True if invites are on.</span></span></p></li>
<li><p><span data-ttu-id="942f5-133">招待がオフの場合は False。</span><span class="sxs-lookup"><span data-stu-id="942f5-133">False if invites are off.</span></span></p></li>
</ul>
<p><span data-ttu-id="942f5-134">ルームの場合:</span><span class="sxs-lookup"><span data-stu-id="942f5-134">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="942f5-135">招待がオフの場合は False (親カテゴリは上書きされます)。</span><span class="sxs-lookup"><span data-stu-id="942f5-135">False if invites are off (overrides the parent category).</span></span></p></li>
<li><p><span data-ttu-id="942f5-136">招待の設定が親カテゴリから継承されている場合は Null。</span><span class="sxs-lookup"><span data-stu-id="942f5-136">Null if the invites setting is inherited from the parent category.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="942f5-137">ログオン</span><span class="sxs-lookup"><span data-stu-id="942f5-137">logged</span></span></p></td>
<td><p><span data-ttu-id="942f5-138">若干</span><span class="sxs-lookup"><span data-stu-id="942f5-138">bit</span></span></p></td>
<td><p><span data-ttu-id="942f5-139">カテゴリの場合:</span><span class="sxs-lookup"><span data-stu-id="942f5-139">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="942f5-140">チャット履歴がオンの場合は True。</span><span class="sxs-lookup"><span data-stu-id="942f5-140">True if chat history is on.</span></span></p></li>
<li><p><span data-ttu-id="942f5-141">チャット履歴がオフの場合は False。</span><span class="sxs-lookup"><span data-stu-id="942f5-141">False if chat history is off.</span></span></p></li>
</ul>
<p><span data-ttu-id="942f5-142">ルームの場合:</span><span class="sxs-lookup"><span data-stu-id="942f5-142">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="942f5-143">Null。</span><span class="sxs-lookup"><span data-stu-id="942f5-143">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="942f5-144">filePost</span><span class="sxs-lookup"><span data-stu-id="942f5-144">filePost</span></span></p></td>
<td><p><span data-ttu-id="942f5-145">若干</span><span class="sxs-lookup"><span data-stu-id="942f5-145">bit</span></span></p></td>
<td><p><span data-ttu-id="942f5-146">カテゴリの場合:</span><span class="sxs-lookup"><span data-stu-id="942f5-146">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="942f5-147">ファイルのアップロードが許可されている場合は True。</span><span class="sxs-lookup"><span data-stu-id="942f5-147">True if file uploads are allowed.</span></span></p></li>
<li><p><span data-ttu-id="942f5-148">ファイルのアップロードが許可されていない場合は False。</span><span class="sxs-lookup"><span data-stu-id="942f5-148">False if file uploads are disallowed.</span></span></p></li>
</ul>
<p><span data-ttu-id="942f5-149">ルームの場合:</span><span class="sxs-lookup"><span data-stu-id="942f5-149">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="942f5-150">Null。</span><span class="sxs-lookup"><span data-stu-id="942f5-150">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="942f5-151">党</span><span class="sxs-lookup"><span data-stu-id="942f5-151">disabled</span></span></p></td>
<td><p><span data-ttu-id="942f5-152">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="942f5-152">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="942f5-153">チャットルームが無効になっている場合は True。</span><span class="sxs-lookup"><span data-stu-id="942f5-153">True if the chat room is disabled.</span></span> <span data-ttu-id="942f5-154">チャットルームにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="942f5-154">Applies only to chat rooms.</span></span> <span data-ttu-id="942f5-155">(カテゴリの場合は False)。</span><span class="sxs-lookup"><span data-stu-id="942f5-155">(False for categories.)</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="942f5-156">behavior</span><span class="sxs-lookup"><span data-stu-id="942f5-156">behavior</span></span></p></td>
<td><p><span data-ttu-id="942f5-157">NULL でない smallint</span><span class="sxs-lookup"><span data-stu-id="942f5-157">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="942f5-158">動作 (EnumValue テーブルで検索):</span><span class="sxs-lookup"><span data-stu-id="942f5-158">Behavior (looked up in EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="942f5-159">4: 標準 (通常のチャットルーム)。</span><span class="sxs-lookup"><span data-stu-id="942f5-159">4: Normal (normal chat rooms).</span></span></p></li>
<li><p><span data-ttu-id="942f5-160">5: 大会議室 (大会議室のチャットルーム、発表者のみが投稿可能)。</span><span class="sxs-lookup"><span data-stu-id="942f5-160">5: Auditorium (auditorium chat rooms, only presenters can contribute).</span></span></p></li>
</ul>
<p><span data-ttu-id="942f5-161">チャットルームにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="942f5-161">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="942f5-162">visibility</span><span class="sxs-lookup"><span data-stu-id="942f5-162">visibility</span></span></p></td>
<td><p><span data-ttu-id="942f5-163">NULL でない smallint</span><span class="sxs-lookup"><span data-stu-id="942f5-163">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="942f5-164">可視性 (EnumValue テーブルで検索):</span><span class="sxs-lookup"><span data-stu-id="942f5-164">Visibility (looked up on EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="942f5-165">2: Private</span><span class="sxs-lookup"><span data-stu-id="942f5-165">2: Private</span></span></p></li>
<li><p><span data-ttu-id="942f5-166">3: スコープ</span><span class="sxs-lookup"><span data-stu-id="942f5-166">3: Scoped</span></span></p></li>
<li><p><span data-ttu-id="942f5-167">6: 開く</span><span class="sxs-lookup"><span data-stu-id="942f5-167">6: Open</span></span></p></li>
</ul>
<p><span data-ttu-id="942f5-168">チャットルームにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="942f5-168">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="942f5-169">Tblsiopwhitelist.siopid</span><span class="sxs-lookup"><span data-stu-id="942f5-169">siopID</span></span></p></td>
<td><p><span data-ttu-id="942f5-170">GUID</span><span class="sxs-lookup"><span data-stu-id="942f5-170">GUID</span></span></p></td>
<td><p><span data-ttu-id="942f5-171">アドインがこのチャットルームに関連付けられている場合は、アドインの GUID。</span><span class="sxs-lookup"><span data-stu-id="942f5-171">Add-In GUID if an add-in is associated with this chat room.</span></span> <span data-ttu-id="942f5-172">(カテゴリにはアドインはありません。)</span><span class="sxs-lookup"><span data-stu-id="942f5-172">(Categories do not have add-ins.)</span></span></p>
<p><span data-ttu-id="942f5-173">アドイン情報は、SiopWhiteList リストテーブルで検索されます。</span><span class="sxs-lookup"><span data-stu-id="942f5-173">The add-in information is looked up in SiopWhiteList table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="942f5-174">nodeAddedBy</span><span class="sxs-lookup"><span data-stu-id="942f5-174">nodeAddedBy</span></span></p></td>
<td><p><span data-ttu-id="942f5-175">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="942f5-175">int, not null</span></span></p></td>
<td><p><span data-ttu-id="942f5-176">このノードを作成したプリンシパルの ID。</span><span class="sxs-lookup"><span data-stu-id="942f5-176">ID of the principal that created this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="942f5-177">nodeAddedOn</span><span class="sxs-lookup"><span data-stu-id="942f5-177">nodeAddedOn</span></span></p></td>
<td><p><span data-ttu-id="942f5-178">NULL でない bigint</span><span class="sxs-lookup"><span data-stu-id="942f5-178">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="942f5-179">ノード作成のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="942f5-179">Time stamp of the node creation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="942f5-180">nodeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="942f5-180">nodeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="942f5-181">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="942f5-181">int, not null</span></span></p></td>
<td><p><span data-ttu-id="942f5-182">このノードの最新の更新を行ったプリンシパルの ID。</span><span class="sxs-lookup"><span data-stu-id="942f5-182">ID of the principal that did the latest update of this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="942f5-183">nodeUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="942f5-183">nodeUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="942f5-184">NULL でない bigint</span><span class="sxs-lookup"><span data-stu-id="942f5-184">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="942f5-185">このノードの最新の更新プログラムのタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="942f5-185">Time stamp of the latest update of this node.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="942f5-186">purgedOn</span><span class="sxs-lookup"><span data-stu-id="942f5-186">purgedOn</span></span></p></td>
<td><p><span data-ttu-id="942f5-187">日付型</span><span class="sxs-lookup"><span data-stu-id="942f5-187">datetime</span></span></p></td>
<td><p><span data-ttu-id="942f5-188">このノードに影響を与える最新の消去操作 (tblScopedPrincipal table およびに tblprincipalrole からの範囲の削除) の時間。</span><span class="sxs-lookup"><span data-stu-id="942f5-188">Time of the latest purge operation (removal of scopes from tblScopedPrincipal table and roles from tblPrincipalRole table) that affected this node.</span></span> <span data-ttu-id="942f5-189">これは、チャットサービスの内部キャッシュ更新メカニズムによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="942f5-189">This is used by the Chat service’s internal cache update mechanism.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="942f5-190">Keys</span><span class="sxs-lookup"><span data-stu-id="942f5-190">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="942f5-191">列</span><span class="sxs-lookup"><span data-stu-id="942f5-191">Column</span></span></th>
<th><span data-ttu-id="942f5-192">説明</span><span class="sxs-lookup"><span data-stu-id="942f5-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="942f5-193">nodeID</span><span class="sxs-lookup"><span data-stu-id="942f5-193">nodeID</span></span></p></td>
<td><p><span data-ttu-id="942f5-194">主キー。</span><span class="sxs-lookup"><span data-stu-id="942f5-194">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="942f5-195">behavior</span><span class="sxs-lookup"><span data-stu-id="942f5-195">behavior</span></span></p></td>
<td><p><span data-ttu-id="942f5-196">TblEnumValue テーブルに参照がある外部キー。</span><span class="sxs-lookup"><span data-stu-id="942f5-196">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="942f5-197">visibility</span><span class="sxs-lookup"><span data-stu-id="942f5-197">visibility</span></span></p></td>
<td><p><span data-ttu-id="942f5-198">TblEnumValue テーブルに参照がある外部キー。</span><span class="sxs-lookup"><span data-stu-id="942f5-198">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="942f5-199">parentID</span><span class="sxs-lookup"><span data-stu-id="942f5-199">parentID</span></span></p></td>
<td><p><span data-ttu-id="942f5-200">tblNode.nodeID テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="942f5-200">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="942f5-201">Tblsiopwhitelist.siopid</span><span class="sxs-lookup"><span data-stu-id="942f5-201">siopID</span></span></p></td>
<td><p><span data-ttu-id="942f5-202">TblSiopWhiteList テーブルに参照がある外部キー。</span><span class="sxs-lookup"><span data-stu-id="942f5-202">Foreign key with lookup in tblSiopWhiteList.siopId table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

