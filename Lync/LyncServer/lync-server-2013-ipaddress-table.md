---
title: Lync Server 2013 での IPAddress テーブル
TOCTitle: Lync Server 2013 での IPAddress テーブル
ms:assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205077(v=OCS.15)
ms:contentKeyID: 48272845
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での IPAddress テーブル

 

_**トピックの最終更新日:** 2015-03-09_

IPAddress テーブルは、IP アドレスを体感品質データベースの他の場所で使用される一意の IP アドレス識別子にマップします。このテーブルは、Microsoft Lync Server 2013 で導入されました。


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
<td><p><strong>IPAddressKey</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>指定した IP アドレスの一意の識別子。</p></td>
</tr>
<tr class="even">
<td><p><strong>IPAddress</strong></p></td>
<td><p>varchar(50)</p></td>
<td><p>一意</p></td>
<td><p>IpAddressKey にマップされる一意の IP アドレス (189.168.1.1 など)。これは IPv4 または IPv6 アドレスです。</p></td>
</tr>
</tbody>
</table>

