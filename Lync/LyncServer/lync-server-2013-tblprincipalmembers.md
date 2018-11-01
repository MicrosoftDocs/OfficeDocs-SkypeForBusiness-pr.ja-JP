---
title: 'Lync Server 2013: tblPrincipalMembers'
TOCTitle: tblPrincipalMembers
ms:assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg615022(v=OCS.15)
ms:contentKeyID: 48272993
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の tblPrincipalMembers

 

_**トピックの最終更新日:** 2015-03-09_

tblPrincipalMembers には、プリンシパル メンバーシップが含まれています。

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
<td><p>memberADPath</p></td>
<td><p>NULL でない nvarchar (384)</p></td>
<td><p>メンバーの識別名。メンバーは (tblPrincipal テーブル内の) プリンシパルでなくてもかまいません。</p></td>
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
<td><p>&lt;prinID, memberADPath&gt;</p></td>
<td><p>主キー。</p></td>
</tr>
<tr class="even">
<td><p>prinID</p></td>
<td><p>tblPrincipal.prinID の検索に使用する外部キー。</p></td>
</tr>
</tbody>
</table>

