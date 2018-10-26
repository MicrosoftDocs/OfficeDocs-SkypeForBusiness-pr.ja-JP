---
title: 'Lync Server 2013: tblEnumAttribute'
TOCTitle: tblEnumAttribute
ms:assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg558617(v=OCS.15)
ms:contentKeyID: 48271398
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の tblEnumAttribute

 

_**トピックの最終更新日:** 2015-03-09_

tblEnumAttribute は、Node テーブルで使用される表示および動作属性を含むハードコードされたテーブルです。

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
<td><p>attributeID</p></td>
<td><p>NULL でない smallint</p></td>
<td><p>属性の ID。</p></td>
</tr>
<tr class="even">
<td><p>attributeName</p></td>
<td><p>NULL でない nvarchar (256)</p></td>
<td><p>属性の名前。</p></td>
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
<td><p>attributeID</p></td>
<td><p>主キー。</p></td>
</tr>
</tbody>
</table>


### テーブル値

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>attributeID</th>
<th>attributeName</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>Visibility</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>Behavior</p></td>
</tr>
</tbody>
</table>


## 関連項目

#### 概念

[Lync Server 2013 の tblNode](lync-server-2013-tblnode.md)

