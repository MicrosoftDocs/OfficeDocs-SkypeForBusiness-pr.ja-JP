---
title: 'Lync Server 2013: tblNode'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblNode
ms:assetid: a31d2961-aa83-4286-a12e-15d279c95f19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615024(v=OCS.15)
ms:contentKeyID: 48184960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84bf7cf57f9890093a56deb2e0769b82e92aa0ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblnode-in-lync-server-2013"></a>Lync Server 2013 の tblNode

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-12_

tblNode には、Lync Server 2013 コントロールパネルと管理コマンドレットで管理されるオブジェクトツリー (カテゴリまたはチャットルームノードを含む) が含まれています。

### <a name="columns"></a>行

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>型</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>nodeID</p></td>
<td><p>int (null ではない)</p></td>
<td><p>ノード ID (一意の番号)。</p></td>
</tr>
<tr class="even">
<td><p>nodeGuid</p></td>
<td><p>GUID、null ではない</p></td>
<td><p>ノード GUID。</p></td>
</tr>
<tr class="odd">
<td><p>parentID</p></td>
<td><p>int</p></td>
<td><p>親のノード ID。 ルートノード (ID 1 の) には、それ自体も親として含まれています。</p></td>
</tr>
<tr class="even">
<td><p>nodeType</p></td>
<td><p>ビット、null ではない</p></td>
<td><p>ノードがカテゴリの場合は True です。</p>
<p>ノードがチャットルームの場合は False です。</p></td>
</tr>
<tr class="odd">
<td><p>nodeName</p></td>
<td><p>nvarchar (256)、null ではない</p></td>
<td><p>ノード名。</p></td>
</tr>
<tr class="even">
<td><p>nodeDesc</p></td>
<td><p>nvarchar (256)、null ではない</p></td>
<td><p>ノードの説明。</p></td>
</tr>
<tr class="odd">
<td><p>召集</p></td>
<td><p>bit</p></td>
<td><p>カテゴリの場合:</p>
<ul>
<li><p>招待がオンの場合は True です。</p></li>
<li><p>招待がオフの場合は False です。</p></li>
</ul>
<p>会議室の場合:</p>
<ul>
<li><p>[招待] がオフの場合は False です (親カテゴリを上書きします)。</p></li>
<li><p>招待設定が親カテゴリから継承されている場合は Null です。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>ログ</p></td>
<td><p>bit</p></td>
<td><p>カテゴリの場合:</p>
<ul>
<li><p>チャット履歴がオンの場合は True です。</p></li>
<li><p>チャット履歴がオフの場合は False です。</p></li>
</ul>
<p>会議室の場合:</p>
<ul>
<li><p>空.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>filePost</p></td>
<td><p>bit</p></td>
<td><p>カテゴリの場合:</p>
<ul>
<li><p>ファイルのアップロードが許可されている場合は True です。</p></li>
<li><p>ファイルのアップロードが許可されていない場合は False です。</p></li>
</ul>
<p>会議室の場合:</p>
<ul>
<li><p>空.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>無効に</p></td>
<td><p>ビット、null ではない</p></td>
<td><p>チャットルームが無効になっている場合は True です。 チャットルームにのみ適用されます。 (カテゴリの場合は False)。</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>状況</p></td>
<td><p>smallint (null ではない)</p></td>
<td><p>動作 (EnumValue テーブルでの検索):</p>
<ul>
<li><p>4: 標準 (通常のチャットルーム)。</p></li>
<li><p>5: 聴衆 (聴衆チャットルーム、発表者のみが投稿できます)。</p></li>
</ul>
<p>チャットルームにのみ適用されます。</p></td>
</tr>
<tr class="odd">
<td><p>明確化</p></td>
<td><p>smallint (null ではない)</p></td>
<td><p>Visibility (EnumValue テーブル上で検索される):</p>
<ul>
<li><p>2: プライベート</p></li>
<li><p>3: 範囲</p></li>
<li><p>6: 開く</p></li>
</ul>
<p>チャットルームにのみ適用されます。</p></td>
</tr>
<tr class="even">
<td><p>siopID</p></td>
<td><p>GUID</p></td>
<td><p>アドインがこのチャットルームに関連付けられている場合は、アドインの GUID。 (カテゴリにはアドインがありません。)</p>
<p>アドイン情報は、SiopWhiteList リスト表で検索されます。</p></td>
</tr>
<tr class="odd">
<td><p>nodeAddedBy</p></td>
<td><p>int (null ではない)</p></td>
<td><p>このノードを作成したプリンシパルの ID です。</p></td>
</tr>
<tr class="even">
<td><p>nodeAddedOn</p></td>
<td><p>bigint (null ではない)</p></td>
<td><p>ノードの作成のタイムスタンプ。</p></td>
</tr>
<tr class="odd">
<td><p>nodeUpdatedBy</p></td>
<td><p>int (null ではない)</p></td>
<td><p>このノードの最新の更新を実行したプリンシパルの ID です。</p></td>
</tr>
<tr class="even">
<td><p>nodeUpdatedOn</p></td>
<td><p>bigint (null ではない)</p></td>
<td><p>このノードの最新の更新プログラムのタイムスタンプです。</p></td>
</tr>
<tr class="odd">
<td><p>purgedOn</p></td>
<td><p>datetime</p></td>
<td><p>このノードに影響を与える最新の消去操作 (tblScopedPrincipal テーブルと tblPrincipalRole テーブルからのスコープの削除) の時間。 これは、チャットサービスの内部キャッシュ更新メカニズムによって使用されます。</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>機能

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
<td><p>状況</p></td>
<td><p>TblEnumValue Id テーブルで参照される外部キー。</p></td>
</tr>
<tr class="odd">
<td><p>明確化</p></td>
<td><p>TblEnumValue Id テーブルで参照される外部キー。</p></td>
</tr>
<tr class="even">
<td><p>parentID</p></td>
<td><p>TblNode テーブルで参照される外部キー。</p></td>
</tr>
<tr class="odd">
<td><p>siopID</p></td>
<td><p>TblSiopWhiteList テーブルで参照する外部キー。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

