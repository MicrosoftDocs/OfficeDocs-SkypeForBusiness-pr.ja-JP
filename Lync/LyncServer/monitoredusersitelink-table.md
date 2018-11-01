---
title: MonitoredUserSiteLink テーブル
TOCTitle: MonitoredUserSiteLink テーブル
ms:assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398233(v=OCS.15)
ms:contentKeyID: 48271387
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# MonitoredUserSiteLink テーブル

 

_**トピックの最終更新日:** 2015-03-09_

MonitoredUserSiteLink テーブルはサポート テーブルです。各レコードは、2 つのユーザー サイト間の 1 つのリンクを表します。


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
<td><p><strong>UserSite1Key</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ、外部</p></td>
<td><p><a href="lync-server-2013-usersite-table.md">Lync Server 2013 の UserSite テーブル</a> から参照されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserSite2Key</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ、外部</p></td>
<td><p><a href="lync-server-2013-usersite-table.md">Lync Server 2013 の UserSite テーブル</a> から参照されます。</p></td>
</tr>
</tbody>
</table>

