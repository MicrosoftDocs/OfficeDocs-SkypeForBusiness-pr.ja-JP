---
title: 'Lync Server 2013: Pools テーブル'
TOCTitle: Pools テーブル
ms:assetid: e0632b8d-e23a-4365-8a7a-6ca0957a46a9
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398991(v=OCS.15)
ms:contentKeyID: 48273829
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の Pools テーブル

 

_**トピックの最終更新日:** 2015-03-09_

Pools テーブルは、さまざまなプールについての情報を格納するサポート テーブルです。テーブルの各レコードが 1 つのプールを表します。


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
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>このプールを示す一意の番号です。</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolFQDN</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p> </p></td>
<td><p>プールの FQDN です。</p></td>
</tr>
</tbody>
</table>

