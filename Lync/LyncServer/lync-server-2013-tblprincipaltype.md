---
title: 'Lync Server 2013: tblPrincipalType'
TOCTitle: tblPrincipalType
ms:assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg558633(v=OCS.15)
ms:contentKeyID: 48271686
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の tblPrincipalType

 

_**トピックの最終更新日:** 2015-03-09_

tblPrincipal テーブルには、tblPrincipal テーブルの内容を分類するプリンシパル型が含まれます。

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
<td><p>ptypeID</p></td>
<td><p>NULL でない smallint</p></td>
<td><p>プリンシパル型 ID。</p></td>
</tr>
<tr class="even">
<td><p>ptypeDesc</p></td>
<td><p>NULL でない nvarchar (256)</p></td>
<td><p>型の説明。</p></td>
</tr>
<tr class="odd">
<td><p>ptypeIsSystemUser</p></td>
<td><p>NULL でない bit</p></td>
<td><p>型が内部の用途で使用されるプリンシパルに対応する場合、True。</p></td>
</tr>
<tr class="even">
<td><p>ptypeIsUser</p></td>
<td><p>NULL でない bit</p></td>
<td><p>型がユーザー型の場合、True。</p></td>
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
<td><p>ptypeID</p></td>
<td><p>主キー。</p></td>
</tr>
</tbody>
</table>


### プリンシパル値

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>ID</th>
<th>[役割]</th>
<th>説明</th>
<th>ユーザー</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>任意</p></td>
<td><p>既知の型を持たない汎用的なプリンシパル。tblPrincipal テーブルでは使用されません。</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>AnyUser</p></td>
<td><p>ユーザー型の汎用的なプリンシパル。tblPrincipal テーブルでは使用されません。</p></td>
<td><p>○</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>AnyGroup</p></td>
<td><p>グループ セマンティックを持つ汎用的なプリンシパル。tblPrincipal テーブルでは使用されません。</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>SystemUser</p></td>
<td><p>常設チャット サーバーによって内部で使用されるプリンシパル。</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>ユーザー</p></td>
<td><p>標準のユーザー</p></td>
<td><p>○</p></td>
</tr>
<tr class="even">
<td><p>8</p></td>
<td><p>DC</p></td>
<td><p>Active Directory ドメイン サービス ドメイン コントローラー。</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>9</p></td>
<td><p>グループ</p></td>
<td><p>Active Directory セキュリティ グループ。</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>10</p></td>
<td><p>Folder</p></td>
<td><p>Active Directory コンテナーまたは組織単位。</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## 関連項目

#### 概念

[Lync Server 2013 の tblPrincipal](lync-server-2013-tblprincipal.md)

