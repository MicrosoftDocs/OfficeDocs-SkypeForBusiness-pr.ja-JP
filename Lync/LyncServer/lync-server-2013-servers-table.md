---
title: 'Lync Server 2013: Servers テーブル'
TOCTitle: Servers テーブル
ms:assetid: 1535e676-a647-4606-bc56-e8bfde5ca823
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398223(v=OCS.15)
ms:contentKeyID: 48271361
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の Servers テーブル

 

_**トピックの最終更新日:** 2015-03-09_

Servers テーブルは、さまざまなサーバーについての情報を格納するサポート テーブルです。テーブルの各レコードは 1 つのサーバーを表します。


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
<td><p><strong>ServerId</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>このサーバーを示す一意の番号です。</p></td>
</tr>
<tr class="even">
<td><p><strong>ServerFQDN</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p> </p></td>
<td><p>サーバーの FQDN です。</p></td>
</tr>
</tbody>
</table>

