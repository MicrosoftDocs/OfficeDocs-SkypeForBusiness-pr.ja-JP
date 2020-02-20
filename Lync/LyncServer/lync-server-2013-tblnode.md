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

# <a name="tblnode-in-lync-server-2013"></a>Lync Server 2013 の tblNode

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-12_

tblNode には、Lync Server 2013 コントロールパネルおよび管理コマンドレットで管理されるオブジェクトツリー (カテゴリまたはチャットルームノードを含む) が含まれています。

### <a name="columns"></a>Columns

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>種類</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>nodeID</p></td>
<td><p>NULL でない int</p></td>
<td><p>ノード ID (一意の番号)。</p></td>
</tr>
<tr class="even">
<td><p>Tblnode.nodeguid</p></td>
<td><p>NULL でない GUID</p></td>
<td><p>ノード GUID。</p></td>
</tr>
<tr class="odd">
<td><p>parentID</p></td>
<td><p>int</p></td>
<td><p>親のノード ID。 ルートノード (ID 1 の) には、それ自体も親として含まれています。</p></td>
</tr>
<tr class="even">
<td><p>nodeType</p></td>
<td><p>NULL でない bit</p></td>
<td><p>ノードがカテゴリの場合は True。</p>
<p>False ノードがチャットルームの場合。</p></td>
</tr>
<tr class="odd">
<td><p>ノード</p></td>
<td><p>NULL でない nvarchar (256)</p></td>
<td><p>ノード名。</p></td>
</tr>
<tr class="even">
<td><p>nodeDesc</p></td>
<td><p>NULL でない nvarchar (256)</p></td>
<td><p>ノードの説明。</p></td>
</tr>
<tr class="odd">
<td><p>invite</p></td>
<td><p>若干</p></td>
<td><p>カテゴリの場合:</p>
<ul>
<li><p>招待がオンの場合は True。</p></li>
<li><p>招待がオフの場合は False。</p></li>
</ul>
<p>ルームの場合:</p>
<ul>
<li><p>招待がオフの場合は False (親カテゴリは上書きされます)。</p></li>
<li><p>招待の設定が親カテゴリから継承されている場合は Null。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>ログオン</p></td>
<td><p>若干</p></td>
<td><p>カテゴリの場合:</p>
<ul>
<li><p>チャット履歴がオンの場合は True。</p></li>
<li><p>チャット履歴がオフの場合は False。</p></li>
</ul>
<p>ルームの場合:</p>
<ul>
<li><p>Null。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>filePost</p></td>
<td><p>若干</p></td>
<td><p>カテゴリの場合:</p>
<ul>
<li><p>ファイルのアップロードが許可されている場合は True。</p></li>
<li><p>ファイルのアップロードが許可されていない場合は False。</p></li>
</ul>
<p>ルームの場合:</p>
<ul>
<li><p>Null。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>党</p></td>
<td><p>NULL でない bit</p></td>
<td><p>チャットルームが無効になっている場合は True。 チャットルームにのみ適用されます。 (カテゴリの場合は False)。</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>behavior</p></td>
<td><p>NULL でない smallint</p></td>
<td><p>動作 (EnumValue テーブルで検索):</p>
<ul>
<li><p>4: 標準 (通常のチャットルーム)。</p></li>
<li><p>5: 大会議室 (大会議室のチャットルーム、発表者のみが投稿可能)。</p></li>
</ul>
<p>チャットルームにのみ適用されます。</p></td>
</tr>
<tr class="odd">
<td><p>visibility</p></td>
<td><p>NULL でない smallint</p></td>
<td><p>可視性 (EnumValue テーブルで検索):</p>
<ul>
<li><p>2: Private</p></li>
<li><p>3: スコープ</p></li>
<li><p>6: 開く</p></li>
</ul>
<p>チャットルームにのみ適用されます。</p></td>
</tr>
<tr class="even">
<td><p>Tblsiopwhitelist.siopid</p></td>
<td><p>GUID</p></td>
<td><p>アドインがこのチャットルームに関連付けられている場合は、アドインの GUID。 (カテゴリにはアドインはありません。)</p>
<p>アドイン情報は、SiopWhiteList リストテーブルで検索されます。</p></td>
</tr>
<tr class="odd">
<td><p>nodeAddedBy</p></td>
<td><p>NULL でない int</p></td>
<td><p>このノードを作成したプリンシパルの ID。</p></td>
</tr>
<tr class="even">
<td><p>nodeAddedOn</p></td>
<td><p>NULL でない bigint</p></td>
<td><p>ノード作成のタイムスタンプ。</p></td>
</tr>
<tr class="odd">
<td><p>nodeUpdatedBy</p></td>
<td><p>NULL でない int</p></td>
<td><p>このノードの最新の更新を行ったプリンシパルの ID。</p></td>
</tr>
<tr class="even">
<td><p>nodeUpdatedOn</p></td>
<td><p>NULL でない bigint</p></td>
<td><p>このノードの最新の更新プログラムのタイムスタンプ。</p></td>
</tr>
<tr class="odd">
<td><p>purgedOn</p></td>
<td><p>日付型</p></td>
<td><p>このノードに影響を与える最新の消去操作 (tblScopedPrincipal table およびに tblprincipalrole からの範囲の削除) の時間。 これは、チャットサービスの内部キャッシュ更新メカニズムによって使用されます。</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>Keys

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>nodeID</p></td>
<td><p>主キー。</p></td>
</tr>
<tr class="even">
<td><p>behavior</p></td>
<td><p>TblEnumValue テーブルに参照がある外部キー。</p></td>
</tr>
<tr class="odd">
<td><p>visibility</p></td>
<td><p>TblEnumValue テーブルに参照がある外部キー。</p></td>
</tr>
<tr class="even">
<td><p>parentID</p></td>
<td><p>tblNode.nodeID テーブル内の参照による外部キー。</p></td>
</tr>
<tr class="odd">
<td><p>Tblsiopwhitelist.siopid</p></td>
<td><p>TblSiopWhiteList テーブルに参照がある外部キー。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

