---
title: 'Lync Server 2013: tblEnumValue'
TOCTitle: tblEnumValue
ms:assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg615025(v=OCS.15)
ms:contentKeyID: 48273049
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の tblEnumValue

 

_**トピックの最終更新日:** 2015-03-09_

tblEnumValue は、ノード テーブルで使われる属性の Visibility (表示設定) 値と Behavior (動作) 値を含む、ハードコードされたテーブルです。

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
<td><p>valueID</p></td>
<td><p>NULL でない smallint</p></td>
<td><p>値の ID。</p></td>
</tr>
<tr class="even">
<td><p>attributeID</p></td>
<td><p>NULL でない smallint</p></td>
<td><p>属性の ID。</p></td>
</tr>
<tr class="odd">
<td><p>attributeValue</p></td>
<td><p>NULL でない nvarchar (256)</p></td>
<td><p>値の名前。</p></td>
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
<td><p>valueID</p></td>
<td><p>主キー。</p></td>
</tr>
<tr class="even">
<td><p>attributeID</p></td>
<td><p>tblEnumAttribute.attributeID テーブルを参照する外部キー。</p></td>
</tr>
</tbody>
</table>


### テーブル値

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>valueID</th>
<th>attributeID</th>
<th>attributeValue</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>1</p></td>
<td><p>private</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>1</p></td>
<td><p>scope</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>2</p></td>
<td><p>normal</p></td>
</tr>
<tr class="even">
<td><p>5</p></td>
<td><p>2</p></td>
<td><p>auditorium</p></td>
</tr>
<tr class="odd">
<td><p>6</p></td>
<td><p>1</p></td>
<td><p>open</p></td>
</tr>
</tbody>
</table>


## 関連項目

#### 概念

[Lync Server 2013 の tblNode](lync-server-2013-tblnode.md)

