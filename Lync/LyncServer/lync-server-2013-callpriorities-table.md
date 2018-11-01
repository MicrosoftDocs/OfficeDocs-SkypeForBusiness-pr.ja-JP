---
title: 'Lync Server 2013: CallPriorities テーブル'
TOCTitle: CallPriorities テーブル
ms:assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398093(v=OCS.15)
ms:contentKeyID: 48271099
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の CallPriorities テーブル

 

_**トピックの最終更新日:** 2015-03-09_

CallPriorities テーブルは、使用できる通話の優先度 ("緊急"、"至急"、"通常" など) の一覧を格納する静的テーブルです。


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
<td><p><strong>PriorityId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>主/プライマリ</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Priority</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p></p></td>
<td><p>有効な値は次のとおりです。</p>
<ul>
<li><p>0 - 不明</p></li>
<li><p>1 - 非緊急</p></li>
<li><p>2 - 通常</p></li>
<li><p>3 - 至急</p></li>
<li><p>4 - 緊急</p></li>
</ul></td>
</tr>
</tbody>
</table>

