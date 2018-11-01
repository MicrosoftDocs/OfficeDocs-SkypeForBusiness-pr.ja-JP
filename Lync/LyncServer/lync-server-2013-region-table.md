---
title: 'Lync Server 2013: Region テーブル'
TOCTitle: Region テーブル
ms:assetid: 1751a6aa-a6e8-4f16-8eb7-ae731c2e3ee3
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398235(v=OCS.15)
ms:contentKeyID: 48271393
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の Region テーブル

 

_**トピックの最終更新日:** 2015-03-09_

Region テーブルはサポート テーブルです。各レコードは、ネットワーク構成設定で定義されている 1 つの国/地域を表します。


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
<td><p><strong>RegionKey</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>国/地域を示す一意の番号です。</p></td>
</tr>
<tr class="even">
<td><p><strong>RegionName</strong></p></td>
<td><p>nvarchar (128)</p></td>
<td><p>一意</p></td>
<td><p>国/地域の名前です。</p></td>
</tr>
</tbody>
</table>

