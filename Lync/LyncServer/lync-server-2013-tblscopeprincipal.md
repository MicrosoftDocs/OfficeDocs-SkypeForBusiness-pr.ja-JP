---
title: 'Lync Server 2013: tblScopePrincipal'
TOCTitle: tblScopePrincipal
ms:assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg558639(v=OCS.15)
ms:contentKeyID: 48271906
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の tblScopePrincipal

 

_**トピックの最終更新日:** 2015-03-09_

tblScopePrincipal には、ノードに割り当てられるスコープが含まれます。

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
<td><p>scopeNodeID</p></td>
<td><p>NULL でない int</p></td>
<td><p>範囲の適用先ノード ID。</p></td>
</tr>
<tr class="even">
<td><p>scopePrinID</p></td>
<td><p>NULL でない int</p></td>
<td><p>プリンシパル ID。</p></td>
</tr>
<tr class="odd">
<td><p>scopeIsDenied</p></td>
<td><p>NULL でない bit</p></td>
<td><p>スコープの種類が [拒否] の場合は True、[許可] の場合は False。</p></td>
</tr>
<tr class="even">
<td><p>scopeUpdatedBy</p></td>
<td><p>NULL でない int</p></td>
<td><p>このエントリを最後に更新したプリンシパルの ID。</p></td>
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
<td><p>&lt;scopeNodeID, scopePrinID&gt;</p></td>
<td><p>主キー。</p></td>
</tr>
<tr class="even">
<td><p>scopeNodeID</p></td>
<td><p>tblNode.nodeID テーブルを参照する外部キー。</p></td>
</tr>
<tr class="odd">
<td><p>scopePrinID</p></td>
<td><p>tblPrincipal.prinID テーブルを参照する外部キー。</p></td>
</tr>
</tbody>
</table>

