---
title: 'Lync Server 2013: MacAddress テーブル'
TOCTitle: MacAddress テーブル
ms:assetid: a32e68c5-3f95-4217-aff4-cb3d1cc70505
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412761(v=OCS.15)
ms:contentKeyID: 48273048
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の MacAddress テーブル

 

_**トピックの最終更新日:** 2015-03-09_

MacAddress テーブルは補助的なテーブルです。個々のレコードが 1 つのソースを表します。


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
<td><p><strong>MacAddressKey</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>MAC アドレスを識別する一意の番号。</p></td>
</tr>
<tr class="even">
<td><p><strong>MacAddress</strong></p></td>
<td><p>varchar(256)</p></td>
<td><p>一意</p></td>
<td><p>MAC アドレス文字列。</p></td>
</tr>
</tbody>
</table>

