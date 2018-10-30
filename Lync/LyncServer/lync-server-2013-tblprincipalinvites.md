---
title: 'Lync Server 2013: tblPrincipalInvites'
TOCTitle: tblPrincipalInvites
ms:assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg558650(v=OCS.15)
ms:contentKeyID: 48272110
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の tblPrincipalInvites

 

_**トピックの最終更新日:** 2015-03-09_

tblPrincipalInvites には、自動招待が有効になっているすべてのノードのプロビジョニングされた全ユーザーの招待が含まれます。

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
<td><p>prinID</p></td>
<td><p>NULL でない int</p></td>
<td><p>プリンシパル ID。</p></td>
</tr>
<tr class="even">
<td><p>invID</p></td>
<td><p>NULL でない int</p></td>
<td><p>tblLastInviteId テーブルから生成された (プリンシパル ID ごとの) 一意のシーケンシャル番号。</p></td>
</tr>
<tr class="odd">
<td><p>nodeID</p></td>
<td><p>NULL でない int</p></td>
<td><p>ノード ID (チャット ルームのみ)。</p></td>
</tr>
<tr class="even">
<td><p>createdOn</p></td>
<td><p>NULL でない datetime</p></td>
<td><p>作成の時刻。</p></td>
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
<td><p>&lt;prinID, nodeID&gt;</p></td>
<td><p>主キー。</p></td>
</tr>
<tr class="even">
<td><p>prinID</p></td>
<td><p>tblPrincipal.prinID テーブルを参照する外部キー。</p></td>
</tr>
<tr class="odd">
<td><p>nodeID</p></td>
<td><p>tblNode.nodeID テーブルを参照する外部キー。</p></td>
</tr>
</tbody>
</table>

