---
title: 'Lync Server 2013: tblComplianceParticipant'
TOCTitle: tblComplianceParticipant
ms:assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg558655(v=OCS.15)
ms:contentKeyID: 48272251
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 内の tblComplianceParticipant

 

_**トピックの最終更新日:** 2015-03-09_

tblComplianceParticipant には、現在の参加者がチャネルおよびサーバー別に格納されます。

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
<td><p>channelUri</p></td>
<td><p>NULL でない nvarchar (255)</p></td>
<td><p>チャネルの URI (Uniform Resource Identifier)。</p></td>
</tr>
<tr class="even">
<td><p>userId</p></td>
<td><p>NULL でない int</p></td>
<td><p>参加者のプリンシパル ID (tblPrincipal.prinID テーブルに対応)。</p></td>
</tr>
<tr class="odd">
<td><p>joinedAt</p></td>
<td><p>NULL でない bigint</p></td>
<td><p>参加イベントのタイム スタンプ。</p></td>
</tr>
<tr class="even">
<td><p>partedAt</p></td>
<td><p>bigint</p></td>
<td><p>参加者がまだ参加している場合は NULL。NULL でない場合は、チャネル退出イベントのタイム スタンプ。</p>
<p>これらのエントリは、すべてのトランスレーターがイベントを処理すると最終的に削除されます。</p></td>
</tr>
<tr class="odd">
<td><p>userUri</p></td>
<td><p>NULL でない nvarchar (255)</p></td>
<td><p>ユーザーの URI。</p></td>
</tr>
<tr class="even">
<td><p>serverID</p></td>
<td><p>int</p></td>
<td><p>サーバーの ID (tblServerIdentity.serverID テーブルなど)。</p></td>
</tr>
<tr class="odd">
<td><p>sessionId</p></td>
<td><p>bigint</p></td>
<td><p>サーバー セッション。チャット サービスが起動するたびに生成されるランダムな数値。孤立した参加者の識別を目的としたセッションの区別に使用されます。</p></td>
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
<td><p>&lt;channelUri, userId, joinedAt&gt;</p></td>
<td><p>主キー。</p></td>
</tr>
</tbody>
</table>

