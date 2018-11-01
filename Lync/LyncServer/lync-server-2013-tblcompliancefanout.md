---
title: 'Lync Server 2013: tblComplianceFanout'
TOCTitle: tblComplianceFanout
ms:assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg615050(v=OCS.15)
ms:contentKeyID: 48274140
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 内の tblComplianceFanout

 

_**トピックの最終更新日:** 2015-03-09_

tblComplianceFanout には、コンプライアンス イベントを処理したすべてのサーバーが格納されています。

### 列

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>型</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>fanoutEventID</p></td>
<td><p>int</p></td>
<td><p>イベント ID。</p></td>
</tr>
<tr class="even">
<td><p>fanoutServerID</p></td>
<td><p>int</p></td>
<td><p>サーバーの ID (tblServerIdentity.serverID テーブルに対応)。</p></td>
</tr>
</tbody>
</table>


### キー

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>fanoutEventID</p></td>
<td><p>tblComplianceData.cmplEventID テーブルを参照する外部キー。</p></td>
</tr>
</tbody>
</table>

