---
title: 'Lync Server 2013: tblPrincipalMemberDifference'
TOCTitle: tblPrincipalMemberDifference
ms:assetid: 0b94f555-6888-4fe0-a048-4660a2513276
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg558612(v=OCS.15)
ms:contentKeyID: 48271221
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の tblPrincipalMemberDifference

 

_**トピックの最終更新日:** 2015-03-09_

tblPrincipalMemberDifference には、Active Directory ドメイン サービス の同期の後続手順によってまだ処理されていないグループ メンバーシップの変更 (メンバーの追加と削除の両方) が格納されます。

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
<td><p>prinGuid</p></td>
<td><p>NULL でない GUID</p></td>
<td><p>変更されたグループのプリンシパル GUID。</p></td>
</tr>
<tr class="even">
<td><p>memberADPath</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>メンバーの識別名。</p></td>
</tr>
<tr class="odd">
<td><p>memberRemoved</p></td>
<td><p>NULL でない bit</p></td>
<td><p>メンバーが追加された場合は False。メンバーが削除された場合は True。</p></td>
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
<td><p>&lt;prinGuid、memberADPath&gt;</p></td>
<td><p>主キー。</p></td>
</tr>
</tbody>
</table>

