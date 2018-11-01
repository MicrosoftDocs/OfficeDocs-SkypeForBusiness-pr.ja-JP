---
title: 'Lync Server 2013: EdgeServers テーブル'
TOCTitle: EdgeServers テーブル
ms:assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412833(v=OCS.15)
ms:contentKeyID: 48273267
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の EdgeServers テーブル

 

_**トピックの最終更新日:** 2015-03-09_

EdgeServers テーブルは補助的なテーブルです。この個々のレコードには、データベースに記録が残された通話に関係する特定のエッジ サーバーの情報が格納されています。


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
<td><p><strong>EdgeServerId</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>このエッジ サーバーを識別する一意の番号。</p></td>
</tr>
<tr class="even">
<td><p><strong>EdgeServer</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p> </p></td>
<td><p>エッジ サーバーの名前。</p></td>
</tr>
</tbody>
</table>

