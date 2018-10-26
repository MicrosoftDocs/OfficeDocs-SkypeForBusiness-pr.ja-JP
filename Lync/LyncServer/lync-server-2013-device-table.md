---
title: 'Lync Server 2013: Device テーブル'
TOCTitle: Device テーブル
ms:assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398930(v=OCS.15)
ms:contentKeyID: 48273700
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の Device テーブル

 

_**トピックの最終更新日:** 2015-03-09_

Device テーブルはサポート テーブルで、さまざまなキャプチャ デバイスまたはレンダー デバイスに関する情報が格納されます。テーブル内の各レコードは、1 つのデータベースを表します。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>列</strong></th>
<th><strong>データ型</strong></th>
<th><strong>キー/インデックス</strong></th>
<th><strong>詳細</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>DeviceKey</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>このデバイスを識別する一意の番号。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceName</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>DeviceName + DeviceType は一意</p></td>
<td><p>デバイス名。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceType</strong></p></td>
<td><p>bit</p></td>
<td><p>DeviceName + DeviceType は一意</p></td>
<td><p>デバイスの種類。1 はキャプチャ デバイスで、0 はレンダー デバイスです。</p></td>
</tr>
</tbody>
</table>

