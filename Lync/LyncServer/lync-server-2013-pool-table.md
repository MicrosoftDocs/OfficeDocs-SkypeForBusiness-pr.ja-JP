---
title: 'Lync Server 2013: Pool テーブル'
TOCTitle: Pool テーブル
ms:assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398746(v=OCS.15)
ms:contentKeyID: 48272881
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の Pool テーブル

 

_**トピックの最終更新日:** 2015-03-09_

Pool テーブルは、さまざまなフロントエンド プールに関する情報を格納するサポート テーブルです。このテーブル内の各レコードは、1 つのプールを表しています。


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
<td><p><strong>PoolKey</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>このプールを示す一意の番号です。</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolName</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Unique </p></td>
<td><p>プールの FQDN です。</p></td>
</tr>
</tbody>
</table>

