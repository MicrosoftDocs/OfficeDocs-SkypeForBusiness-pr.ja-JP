---
title: 'Lync Server 2013: tblPrincipalMeta'
TOCTitle: tblPrincipalMeta
ms:assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg615009(v=OCS.15)
ms:contentKeyID: 48272677
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の tblPrincipalMeta

 

_**トピックの最終更新日:** 2015-03-09_

tblPrincipalMeta には、 Active Directory ドメイン サービス から最新の情報に更新する必要があるプリンシパルが格納されます。

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
<td><p>prinAffiliationsDirty</p></td>
<td><p>NULL でない bit</p></td>
<td><p>プリンシパルの所属を最新の情報に更新する必要がある場合は True。</p></td>
</tr>
<tr class="odd">
<td><p>prinAttributesDirty</p></td>
<td><p>NULL でない bit</p></td>
<td><p>プリンシパル属性を最新の情報に更新する必要がある場合は True。</p></td>
</tr>
<tr class="even">
<td><p>prinDeleted</p></td>
<td><p>NULL でない bit</p></td>
<td><p>プリンシパルが削除されている場合は True。</p></td>
</tr>
<tr class="odd">
<td><p>tryCount</p></td>
<td><p>int</p></td>
<td><p>それまでに行われた AD DS からプリンシパルを更新する試行の数。</p></td>
</tr>
<tr class="even">
<td><p>lastTry</p></td>
<td><p>datetime</p></td>
<td><p>プリンシパルを最新の情報に更新する最新の試行からのタイム スタンプ。最新の情報への更新をまだ試みていない場合は NULL になります。</p></td>
</tr>
<tr class="odd">
<td><p>nextTry</p></td>
<td><p>datetime</p></td>
<td><p>次にスケジュールされている最新の情報への更新のタイム スタンプ。最新の情報への更新がスケジュールされていない場合は NULL になります。</p></td>
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
<td><p>prinID</p></td>
<td><p>主キー。</p></td>
</tr>
<tr class="even">
<td><p>prinID</p></td>
<td><p>tblPrincipal.prinID テーブルを参照する外部キー。</p></td>
</tr>
</tbody>
</table>

