---
title: 'Lync Server 2013: UriTypes テーブル'
TOCTitle: UriTypes テーブル
ms:assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398587(v=OCS.15)
ms:contentKeyID: 48272539
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の UriTypes テーブル

 

_**トピックの最終更新日:** 2015-06-16_

UriTypes テーブルには、Microsoft Lync Server 2013 において監視される URI (Uniform Resource Identifier) の種類が格納されています。


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
<td><p><strong>UriTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>主/プライマリ</p></td>
<td><p>URI の種類に割り当てられている一意の ID です。</p></td>
</tr>
<tr class="even">
<td><p><strong>UriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p></p></td>
<td><p>URI の種類の説明です。有効な値は次のとおりです。</p>
<ul>
<li><p>0 – Phone Uri</p></li>
<li><p>1 – User Uri</p></li>
</ul></td>
</tr>
</tbody>
</table>

