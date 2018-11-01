---
title: 'Lync Server 2013: tblNode'
TOCTitle: tblNode
ms:assetid: a31d2961-aa83-4286-a12e-15d279c95f19
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg615024(v=OCS.15)
ms:contentKeyID: 48273047
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の tblNode

 

_**トピックの最終更新日:** 2015-03-09_

tblNode には、 Lync Server 2013 コントロール パネルおよび管理コマンドレットで管理されているオブジェクト ツリー (カテゴリ ノードまたはチャット ルーム ノードを持つ) が含まれています。

### 列

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
<td><p>NULL でない int</p></td>
<td><p>ノード ID (一意の番号)。</p></td>
</tr>
<tr class="even">
<td><p>nodeGuid</p></td>
<td><p>NULL でない GUID</p></td>
<td><p>ノード GUID。</p></td>
</tr>
<tr class="odd">
<td><p>parentID</p></td>
<td><p>int</p></td>
<td><p>親のノード ID。ルート ノード (ID 1) にもそれ自体が親として含まれます。</p></td>
</tr>
<tr class="even">
<td><p>nodeType</p></td>
<td><p>NULL でない bit</p></td>
<td><p>ノードがカテゴリの場合は、True。</p>
<p>ノードがチャット ルームの場合は、False。</p></td>
</tr>
<tr class="odd">
<td><p>nodeName</p></td>
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
<td><p>bit</p></td>
<td><p>カテゴリの場合:</p>
<ul>
<li><p>招待がオンの場合は、True。</p></li>
<li><p>招待がオフの場合は、False。</p></li>
</ul>
<p>ルームの場合:</p>
<ul>
<li><p>招待がオフの場合は、False (親カテゴリが上書きされます)。</p></li>
<li><p>招待の設定が親カテゴリから継承される場合は、NULL。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>logged</p></td>
<td><p>bit</p></td>
<td><p>カテゴリの場合:</p>
<ul>
<li><p>チャット履歴がオンの場合は、True。</p></li>
<li><p>チャット履歴がオフの場合は、False。</p></li>
</ul>
<p>ルームの場合:</p>
<ul>
<li><p>Null。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>filePost</p></td>
<td><p>bit</p></td>
<td><p>カテゴリの場合:</p>
<ul>
<li><p>ファイルのアップロードが許可される場合は、True。</p></li>
<li><p>ファイルのアップロードが許可されない場合は、False。</p></li>
</ul>
<p>ルームの場合:</p>
<ul>
<li><p>Null。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>disabled</p></td>
<td><p>NULL でない bit</p></td>
<td><p>チャット ルームが無効化されている場合は、True。チャット ルームにのみ適用されます。(カテゴリでは False)</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>behavior</p></td>
<td><p>NULL でない smallint</p></td>
<td><p>動作 (EnumValue テーブルで検索):</p>
<ul>
<li><p>4: 標準 (標準チャット ルーム)。</p></li>
<li><p>5: 大会議室 (大会議室のチャット ルーム、発表者のみが投稿可能)。</p></li>
</ul>
<p>チャット ルームにのみ適用されます。</p></td>
</tr>
<tr class="odd">
<td><p>visibility</p></td>
<td><p>NULL でない smallint</p></td>
<td><p>表示設定 (EnumValue テーブルで検索):</p>
<ul>
<li><p>2: プライベート</p></li>
<li><p>3: スコープ内</p></li>
<li><p>6: オープン</p></li>
</ul>
<p>チャット ルームにのみ適用されます。</p></td>
</tr>
<tr class="even">
<td><p>siopID</p></td>
<td><p>GUID</p></td>
<td><p>このチャット ルームにアドインが関連付けられている場合は、アドインの GUID (カテゴリはアドインを持たない)。</p>
<p>アドインの情報は SiopWhiteList テーブルで検索されます。</p></td>
</tr>
<tr class="odd">
<td><p>nodeAddedBy</p></td>
<td><p>NULL でない int</p></td>
<td><p>このノードを作成した プリンシパルの ID。</p></td>
</tr>
<tr class="even">
<td><p>nodeAddedOn</p></td>
<td><p>NULL でない bigint</p></td>
<td><p>ノード作成のタイム スタンプ。</p></td>
</tr>
<tr class="odd">
<td><p>nodeUpdatedBy</p></td>
<td><p>NULL でない int</p></td>
<td><p>このノードの最新更新を行ったプリンシパルの ID。</p></td>
</tr>
<tr class="even">
<td><p>nodeUpdatedOn</p></td>
<td><p>NULL でない bigint</p></td>
<td><p>このノードの最新更新のタイム スタンプ。</p></td>
</tr>
<tr class="odd">
<td><p>purgedOn</p></td>
<td><p>datetime</p></td>
<td><p>このノードに影響する最新のパージ操作 (スコープを tblScopedPrincipal テーブルから削除し、さらにロールを tblPrincipalRole テーブルから削除する) の時刻。これはチャット サービスの内部キャッシュ更新機構で使われます。</p></td>
</tr>
</tbody>
</table>


### キー

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
<td><p>tblEnumValue.valueID テーブルを参照する外部キー。</p></td>
</tr>
<tr class="odd">
<td><p>visibility</p></td>
<td><p>tblEnumValue.valueID テーブルを参照する外部キー。</p></td>
</tr>
<tr class="even">
<td><p>parentID</p></td>
<td><p>tblNode.nodeID テーブルを参照する外部キー。</p></td>
</tr>
<tr class="odd">
<td><p>siopID</p></td>
<td><p>tblSiopWhiteList.siopId テーブルを参照する外部キー。</p></td>
</tr>
</tbody>
</table>

