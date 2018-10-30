---
title: 'Lync Server 2013: tblServerIdentity'
TOCTitle: tblServerIdentity
ms:assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg558648(v=OCS.15)
ms:contentKeyID: 48272102
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の tblServerIdentity

 

_**トピックの最終更新日:** 2015-03-09_

tblServerIdentity には、 常設チャット サーバー プール内のアクティブなチャット サーバーが含まれます。

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
<td><p>serverID</p></td>
<td><p>NULL でない int</p></td>
<td><p>サーバー ID。 中央管理ストアのインスタンス ID に対応します。</p></td>
</tr>
<tr class="even">
<td><p>serverAddress</p></td>
<td><p>NULL でない nvarchar (256)</p></td>
<td><p>Windows Communication Foundation アドレスを使用したサーバー アドレス。</p></td>
</tr>
<tr class="odd">
<td><p>serverLastPingTime</p></td>
<td><p>datetime</p></td>
<td><p>チャネル サーバーが、実行中であることを示すためにこの行を更新した最新時刻。</p></td>
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
<td><p>serverID</p></td>
<td><p>主キー。</p></td>
</tr>
</tbody>
</table>

