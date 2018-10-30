---
title: 'Lync Server 2013: Manufacturers テーブル'
TOCTitle: Manufacturers テーブル
ms:assetid: 734608b3-5a3a-4b61-87dc-9a8551401d06
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398549(v=OCS.15)
ms:contentKeyID: 48272455
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の Manufacturers テーブル

 

_**トピックの最終更新日:** 2015-03-09_

Manufacturers テーブルは、サポート テーブルです。それぞれのレコードには、1 つのデバイス (卓上電話) 製造元に関する情報が格納されます。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>データ型</th>
<th>キー/インデックス</th>
<th>詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ManufacturerId</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>この製造元を示す一意の番号です。</p></td>
</tr>
<tr class="even">
<td><p><strong>Manufacturer</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p> </p></td>
<td><p>製造元の名前です。</p></td>
</tr>
</tbody>
</table>

