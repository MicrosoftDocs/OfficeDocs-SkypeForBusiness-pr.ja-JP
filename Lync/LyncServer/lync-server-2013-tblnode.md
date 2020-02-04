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
ms.openlocfilehash: 24ba45d9ba650a9de4359d64e3281fb488b6a279
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731487"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblnode-in-lync-server-2013"></a><span data-ttu-id="9f694-102">Lync Server 2013 の tblNode</span><span class="sxs-lookup"><span data-stu-id="9f694-102">tblNode in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f694-103">_**最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="9f694-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="9f694-104">tblNode には、Lync Server 2013 コントロールパネルと管理コマンドレットで管理されるオブジェクトツリー (カテゴリまたはチャットルームノードを含む) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9f694-104">tblNode contains the object tree (with category or chat room nodes) as managed in the Lync Server 2013 Control Panel and administrative cmdlets.</span></span>

### <a name="columns"></a><span data-ttu-id="9f694-105">行</span><span class="sxs-lookup"><span data-stu-id="9f694-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9f694-106">列</span><span class="sxs-lookup"><span data-stu-id="9f694-106">Column</span></span></th>
<th><span data-ttu-id="9f694-107">型</span><span class="sxs-lookup"><span data-stu-id="9f694-107">Type</span></span></th>
<th><span data-ttu-id="9f694-108">説明</span><span class="sxs-lookup"><span data-stu-id="9f694-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f694-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="9f694-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="9f694-110">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="9f694-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9f694-111">ノード ID (一意の番号)。</span><span class="sxs-lookup"><span data-stu-id="9f694-111">Node ID (unique number).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f694-112">nodeGuid</span><span class="sxs-lookup"><span data-stu-id="9f694-112">nodeGuid</span></span></p></td>
<td><p><span data-ttu-id="9f694-113">GUID、null ではない</span><span class="sxs-lookup"><span data-stu-id="9f694-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="9f694-114">ノード GUID。</span><span class="sxs-lookup"><span data-stu-id="9f694-114">Node GUID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f694-115">parentID</span><span class="sxs-lookup"><span data-stu-id="9f694-115">parentID</span></span></p></td>
<td><p><span data-ttu-id="9f694-116">int</span><span class="sxs-lookup"><span data-stu-id="9f694-116">int</span></span></p></td>
<td><p><span data-ttu-id="9f694-117">親のノード ID。</span><span class="sxs-lookup"><span data-stu-id="9f694-117">Node ID of parent.</span></span> <span data-ttu-id="9f694-118">ルートノード (ID 1 の) には、それ自体も親として含まれています。</span><span class="sxs-lookup"><span data-stu-id="9f694-118">The root node (with ID 1) includes itself as parent as well.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f694-119">nodeType</span><span class="sxs-lookup"><span data-stu-id="9f694-119">nodeType</span></span></p></td>
<td><p><span data-ttu-id="9f694-120">ビット、null ではない</span><span class="sxs-lookup"><span data-stu-id="9f694-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="9f694-121">ノードがカテゴリの場合は True です。</span><span class="sxs-lookup"><span data-stu-id="9f694-121">True if the node is a category.</span></span></p>
<p><span data-ttu-id="9f694-122">ノードがチャットルームの場合は False です。</span><span class="sxs-lookup"><span data-stu-id="9f694-122">False if the node is a chat room.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f694-123">nodeName</span><span class="sxs-lookup"><span data-stu-id="9f694-123">nodeName</span></span></p></td>
<td><p><span data-ttu-id="9f694-124">nvarchar (256)、null ではない</span><span class="sxs-lookup"><span data-stu-id="9f694-124">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="9f694-125">ノード名。</span><span class="sxs-lookup"><span data-stu-id="9f694-125">Node name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f694-126">nodeDesc</span><span class="sxs-lookup"><span data-stu-id="9f694-126">nodeDesc</span></span></p></td>
<td><p><span data-ttu-id="9f694-127">nvarchar (256)、null ではない</span><span class="sxs-lookup"><span data-stu-id="9f694-127">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="9f694-128">ノードの説明。</span><span class="sxs-lookup"><span data-stu-id="9f694-128">Node description.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f694-129">召集</span><span class="sxs-lookup"><span data-stu-id="9f694-129">invite</span></span></p></td>
<td><p><span data-ttu-id="9f694-130">bit</span><span class="sxs-lookup"><span data-stu-id="9f694-130">bit</span></span></p></td>
<td><p><span data-ttu-id="9f694-131">カテゴリの場合:</span><span class="sxs-lookup"><span data-stu-id="9f694-131">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="9f694-132">招待がオンの場合は True です。</span><span class="sxs-lookup"><span data-stu-id="9f694-132">True if invites are on.</span></span></p></li>
<li><p><span data-ttu-id="9f694-133">招待がオフの場合は False です。</span><span class="sxs-lookup"><span data-stu-id="9f694-133">False if invites are off.</span></span></p></li>
</ul>
<p><span data-ttu-id="9f694-134">会議室の場合:</span><span class="sxs-lookup"><span data-stu-id="9f694-134">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="9f694-135">[招待] がオフの場合は False です (親カテゴリを上書きします)。</span><span class="sxs-lookup"><span data-stu-id="9f694-135">False if invites are off (overrides the parent category).</span></span></p></li>
<li><p><span data-ttu-id="9f694-136">招待設定が親カテゴリから継承されている場合は Null です。</span><span class="sxs-lookup"><span data-stu-id="9f694-136">Null if the invites setting is inherited from the parent category.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f694-137">ログ</span><span class="sxs-lookup"><span data-stu-id="9f694-137">logged</span></span></p></td>
<td><p><span data-ttu-id="9f694-138">bit</span><span class="sxs-lookup"><span data-stu-id="9f694-138">bit</span></span></p></td>
<td><p><span data-ttu-id="9f694-139">カテゴリの場合:</span><span class="sxs-lookup"><span data-stu-id="9f694-139">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="9f694-140">チャット履歴がオンの場合は True です。</span><span class="sxs-lookup"><span data-stu-id="9f694-140">True if chat history is on.</span></span></p></li>
<li><p><span data-ttu-id="9f694-141">チャット履歴がオフの場合は False です。</span><span class="sxs-lookup"><span data-stu-id="9f694-141">False if chat history is off.</span></span></p></li>
</ul>
<p><span data-ttu-id="9f694-142">会議室の場合:</span><span class="sxs-lookup"><span data-stu-id="9f694-142">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="9f694-143">空.</span><span class="sxs-lookup"><span data-stu-id="9f694-143">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f694-144">filePost</span><span class="sxs-lookup"><span data-stu-id="9f694-144">filePost</span></span></p></td>
<td><p><span data-ttu-id="9f694-145">bit</span><span class="sxs-lookup"><span data-stu-id="9f694-145">bit</span></span></p></td>
<td><p><span data-ttu-id="9f694-146">カテゴリの場合:</span><span class="sxs-lookup"><span data-stu-id="9f694-146">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="9f694-147">ファイルのアップロードが許可されている場合は True です。</span><span class="sxs-lookup"><span data-stu-id="9f694-147">True if file uploads are allowed.</span></span></p></li>
<li><p><span data-ttu-id="9f694-148">ファイルのアップロードが許可されていない場合は False です。</span><span class="sxs-lookup"><span data-stu-id="9f694-148">False if file uploads are disallowed.</span></span></p></li>
</ul>
<p><span data-ttu-id="9f694-149">会議室の場合:</span><span class="sxs-lookup"><span data-stu-id="9f694-149">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="9f694-150">空.</span><span class="sxs-lookup"><span data-stu-id="9f694-150">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f694-151">無効に</span><span class="sxs-lookup"><span data-stu-id="9f694-151">disabled</span></span></p></td>
<td><p><span data-ttu-id="9f694-152">ビット、null ではない</span><span class="sxs-lookup"><span data-stu-id="9f694-152">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="9f694-153">チャットルームが無効になっている場合は True です。</span><span class="sxs-lookup"><span data-stu-id="9f694-153">True if the chat room is disabled.</span></span> <span data-ttu-id="9f694-154">チャットルームにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="9f694-154">Applies only to chat rooms.</span></span> <span data-ttu-id="9f694-155">(カテゴリの場合は False)。</span><span class="sxs-lookup"><span data-stu-id="9f694-155">(False for categories.)</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f694-156">状況</span><span class="sxs-lookup"><span data-stu-id="9f694-156">behavior</span></span></p></td>
<td><p><span data-ttu-id="9f694-157">smallint (null ではない)</span><span class="sxs-lookup"><span data-stu-id="9f694-157">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="9f694-158">動作 (EnumValue テーブルでの検索):</span><span class="sxs-lookup"><span data-stu-id="9f694-158">Behavior (looked up in EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="9f694-159">4: 標準 (通常のチャットルーム)。</span><span class="sxs-lookup"><span data-stu-id="9f694-159">4: Normal (normal chat rooms).</span></span></p></li>
<li><p><span data-ttu-id="9f694-160">5: 聴衆 (聴衆チャットルーム、発表者のみが投稿できます)。</span><span class="sxs-lookup"><span data-stu-id="9f694-160">5: Auditorium (auditorium chat rooms, only presenters can contribute).</span></span></p></li>
</ul>
<p><span data-ttu-id="9f694-161">チャットルームにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="9f694-161">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f694-162">明確化</span><span class="sxs-lookup"><span data-stu-id="9f694-162">visibility</span></span></p></td>
<td><p><span data-ttu-id="9f694-163">smallint (null ではない)</span><span class="sxs-lookup"><span data-stu-id="9f694-163">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="9f694-164">Visibility (EnumValue テーブル上で検索される):</span><span class="sxs-lookup"><span data-stu-id="9f694-164">Visibility (looked up on EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="9f694-165">2: プライベート</span><span class="sxs-lookup"><span data-stu-id="9f694-165">2: Private</span></span></p></li>
<li><p><span data-ttu-id="9f694-166">3: 範囲</span><span class="sxs-lookup"><span data-stu-id="9f694-166">3: Scoped</span></span></p></li>
<li><p><span data-ttu-id="9f694-167">6: 開く</span><span class="sxs-lookup"><span data-stu-id="9f694-167">6: Open</span></span></p></li>
</ul>
<p><span data-ttu-id="9f694-168">チャットルームにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="9f694-168">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f694-169">siopID</span><span class="sxs-lookup"><span data-stu-id="9f694-169">siopID</span></span></p></td>
<td><p><span data-ttu-id="9f694-170">GUID</span><span class="sxs-lookup"><span data-stu-id="9f694-170">GUID</span></span></p></td>
<td><p><span data-ttu-id="9f694-171">アドインがこのチャットルームに関連付けられている場合は、アドインの GUID。</span><span class="sxs-lookup"><span data-stu-id="9f694-171">Add-In GUID if an add-in is associated with this chat room.</span></span> <span data-ttu-id="9f694-172">(カテゴリにはアドインがありません。)</span><span class="sxs-lookup"><span data-stu-id="9f694-172">(Categories do not have add-ins.)</span></span></p>
<p><span data-ttu-id="9f694-173">アドイン情報は、SiopWhiteList リスト表で検索されます。</span><span class="sxs-lookup"><span data-stu-id="9f694-173">The add-in information is looked up in SiopWhiteList table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f694-174">nodeAddedBy</span><span class="sxs-lookup"><span data-stu-id="9f694-174">nodeAddedBy</span></span></p></td>
<td><p><span data-ttu-id="9f694-175">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="9f694-175">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9f694-176">このノードを作成したプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="9f694-176">ID of the principal that created this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f694-177">nodeAddedOn</span><span class="sxs-lookup"><span data-stu-id="9f694-177">nodeAddedOn</span></span></p></td>
<td><p><span data-ttu-id="9f694-178">bigint (null ではない)</span><span class="sxs-lookup"><span data-stu-id="9f694-178">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="9f694-179">ノードの作成のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="9f694-179">Time stamp of the node creation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f694-180">nodeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="9f694-180">nodeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="9f694-181">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="9f694-181">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9f694-182">このノードの最新の更新を実行したプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="9f694-182">ID of the principal that did the latest update of this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f694-183">nodeUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="9f694-183">nodeUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="9f694-184">bigint (null ではない)</span><span class="sxs-lookup"><span data-stu-id="9f694-184">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="9f694-185">このノードの最新の更新プログラムのタイムスタンプです。</span><span class="sxs-lookup"><span data-stu-id="9f694-185">Time stamp of the latest update of this node.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f694-186">purgedOn</span><span class="sxs-lookup"><span data-stu-id="9f694-186">purgedOn</span></span></p></td>
<td><p><span data-ttu-id="9f694-187">datetime</span><span class="sxs-lookup"><span data-stu-id="9f694-187">datetime</span></span></p></td>
<td><p><span data-ttu-id="9f694-188">このノードに影響を与える最新の消去操作 (tblScopedPrincipal テーブルと tblPrincipalRole テーブルからのスコープの削除) の時間。</span><span class="sxs-lookup"><span data-stu-id="9f694-188">Time of the latest purge operation (removal of scopes from tblScopedPrincipal table and roles from tblPrincipalRole table) that affected this node.</span></span> <span data-ttu-id="9f694-189">これは、チャットサービスの内部キャッシュ更新メカニズムによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="9f694-189">This is used by the Chat service’s internal cache update mechanism.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="9f694-190">機能</span><span class="sxs-lookup"><span data-stu-id="9f694-190">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9f694-191">列</span><span class="sxs-lookup"><span data-stu-id="9f694-191">Column</span></span></th>
<th><span data-ttu-id="9f694-192">説明</span><span class="sxs-lookup"><span data-stu-id="9f694-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f694-193">nodeID</span><span class="sxs-lookup"><span data-stu-id="9f694-193">nodeID</span></span></p></td>
<td><p><span data-ttu-id="9f694-194">主キー。</span><span class="sxs-lookup"><span data-stu-id="9f694-194">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f694-195">状況</span><span class="sxs-lookup"><span data-stu-id="9f694-195">behavior</span></span></p></td>
<td><p><span data-ttu-id="9f694-196">TblEnumValue Id テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="9f694-196">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f694-197">明確化</span><span class="sxs-lookup"><span data-stu-id="9f694-197">visibility</span></span></p></td>
<td><p><span data-ttu-id="9f694-198">TblEnumValue Id テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="9f694-198">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f694-199">parentID</span><span class="sxs-lookup"><span data-stu-id="9f694-199">parentID</span></span></p></td>
<td><p><span data-ttu-id="9f694-200">TblNode テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="9f694-200">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f694-201">siopID</span><span class="sxs-lookup"><span data-stu-id="9f694-201">siopID</span></span></p></td>
<td><p><span data-ttu-id="9f694-202">TblSiopWhiteList テーブルで参照する外部キー。</span><span class="sxs-lookup"><span data-stu-id="9f694-202">Foreign key with lookup in tblSiopWhiteList.siopId table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

