---
title: 'Lync Server 2013: tblPrincipalAffiliations'
TOCTitle: tblPrincipalAffiliations
ms:assetid: 45fd8484-5837-44d2-85bb-45c83546607c
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg558642(v=OCS.15)
ms:contentKeyID: 48271945
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の tblPrincipalAffiliations

 

_**トピックの最終更新日:** 2015-03-09_

tblPrincipalAffiliations には、 Active Directory ドメイン サービス セキュリティ グループ、Active Directory コンテナー、ドメインなどの場所においてのメンバーシップを定義するプリンシパルの所属が含まれます。

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
<td><p>principalID</p></td>
<td><p>NULL でない int</p></td>
<td><p>所属プリンシパルの ID。</p></td>
</tr>
<tr class="even">
<td><p>affiliationID</p></td>
<td><p>NULL でない int</p></td>
<td><p>所属を表すプリンシパルの ID。各プリンシパル (system-user-types 除く) には自己所属も含まれます。</p></td>
</tr>
<tr class="odd">
<td><p>インデックス</p></td>
<td><p>NULL でない int</p></td>
<td><p>インデックス。自己所属の値は -1、それ以外の所属の値は、&lt;principalID, affiliationId&gt; バケット内で 1 から順に増加します。</p></td>
</tr>
<tr class="even">
<td><p>updatedBy</p></td>
<td><p>NULL でない int</p></td>
<td><p>最新の更新を実行したプリンシパル。通常は、Active Directory の同期を意味する 1 です。</p></td>
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
<td><p>&lt;principalID, index, affiliationID&gt;</p></td>
<td><p>主キー。</p></td>
</tr>
<tr class="even">
<td><p>principalID</p></td>
<td><p>tblPrincipal.prinID テーブルを参照する外部キー。</p></td>
</tr>
<tr class="odd">
<td><p>affiliationID</p></td>
<td><p>tblPrincipal.prinID テーブルを参照する外部キー。</p></td>
</tr>
</tbody>
</table>

