---
title: 'Lync Server 2013: MonitoredRegionLink テーブル'
TOCTitle: MonitoredRegionLink テーブル
ms:assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398874(v=OCS.15)
ms:contentKeyID: 48273674
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の MonitoredRegionLink テーブル

 

_**トピックの最終更新日:** 2015-03-09_

MonitoredRegionLink テーブルは、サポート テーブルです。各レコードは、2 つの国/地域の間の 1 つのリンクを表します。


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
<td><p><strong>Region1Key</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ、外部</p></td>
<td><p><a href="lync-server-2013-region-table.md">Lync Server 2013 の Region テーブル</a> から参照されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>Region2Key</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ、外部</p></td>
<td><p><a href="lync-server-2013-region-table.md">Lync Server 2013 の Region テーブル</a> から参照されます。</p></td>
</tr>
</tbody>
</table>

