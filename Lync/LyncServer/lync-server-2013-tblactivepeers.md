---
title: 'Lync Server 2013: tblActivePeers'
TOCTitle: tblActivePeers
ms:assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg615030(v=OCS.15)
ms:contentKeyID: 48273343
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の tblActivePeers

 

_**トピックの最終更新日:** 2015-03-09_

tblActivePeers には、チャット サービス間の現在のピアツーピア接続が含まれています。

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
<td><p>aplServerID</p></td>
<td><p>NULL でない int</p></td>
<td><p>エントリを投稿したサーバーの ID。</p></td>
</tr>
<tr class="even">
<td><p>aplPeerID</p></td>
<td><p>NULL でない int</p></td>
<td><p>投稿元サーバーが接続しているピアの ID。</p></td>
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
<td><p>&lt;aplServerID, aplPeerID&gt;</p></td>
<td><p>主キー。</p></td>
</tr>
<tr class="even">
<td><p>aplServerID</p></td>
<td><p>tblServerIdentity.serverID テーブルを参照する外部キー。</p></td>
</tr>
<tr class="odd">
<td><p>aplPeerID</p></td>
<td><p>tblServerIdentity.serverID テーブルを参照する外部キー。</p></td>
</tr>
</tbody>
</table>

