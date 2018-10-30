---
title: 'Lync Server 2013: Roles テーブル'
TOCTitle: Roles テーブル
ms:assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg399043(v=OCS.15)
ms:contentKeyID: 48273909
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の Roles テーブル

 

_**トピックの最終更新日:** 2015-03-09_

Roles テーブルは、会議で使用可能な役割 (参加者、発表者など) のリストを格納する静的なテーブルです。


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
<td><p><strong>RoleId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>主/プライマリ</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Role</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p></p></td>
<td><p>有効な値は次のとおりです。</p>
<ul>
<li><p>0 - 不明</p></li>
<li><p>1 - 発表者</p></li>
<li><p>2 - 参加者</p></li>
</ul></td>
</tr>
</tbody>
</table>

