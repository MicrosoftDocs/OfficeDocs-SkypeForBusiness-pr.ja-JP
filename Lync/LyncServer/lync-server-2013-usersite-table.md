---
title: 'Lync Server 2013: UserSite テーブル'
TOCTitle: UserSite テーブル
ms:assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398256(v=OCS.15)
ms:contentKeyID: 48271433
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の UserSite テーブル

 

_**トピックの最終更新日:** 2015-03-09_

UserSite テーブルはサポート テーブルです。各レコードは、ネットワーク構成の設定で定義されている 1 つのユーザー サイトを表します。


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
<td><p><strong>UserSiteKey</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>ユーザー サイトを示す一意の番号です。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserSiteName</strong></p></td>
<td><p>nvarchar (128)</p></td>
<td><p>一意</p></td>
<td><p>ユーザー サイトの名前です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RegionKey</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p><a href="lync-server-2013-region-table.md">Lync Server 2013 の Region テーブル</a>から参照されます。</p></td>
</tr>
</tbody>
</table>

