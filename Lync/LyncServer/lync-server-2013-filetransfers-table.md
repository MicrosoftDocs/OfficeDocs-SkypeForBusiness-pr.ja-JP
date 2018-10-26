---
title: 'Lync Server 2013: FileTransfers テーブル'
TOCTitle: FileTransfers テーブル
ms:assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398353(v=OCS.15)
ms:contentKeyID: 48272108
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の FileTransfers テーブル

 

_**トピックの最終更新日:** 2015-03-09_

各レコードは、1 つのファイル転送セッションを表します。


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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主/プライマリ、外部</p></td>
<td><p>セッション要求の時間。<strong>SessionIdSeq</strong> と合わせて使用して、セッションを一意に識別します。詳細については、「<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 の Dialogs テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ、外部</p></td>
<td><p>セッションを識別するための ID 番号。セッションを一意に識別するために <strong>SessionIdTime</strong> と併用されます。詳細については、「<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 の Dialogs テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>File Name</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p></p></td>
<td><p>ファイルの名前。</p></td>
</tr>
<tr class="even">
<td><p><strong>FileIdentity</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p></p></td>
<td><p>同じファイル名が使用されているファイル送信を区別するための一意の識別子です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Cookie</strong></p></td>
<td><p>nvarchar (128)</p></td>
<td><p>主/プライマリ</p></td>
<td><p>すべてのフォローアップ メッセージをこれに関連付けられたものとして識別するために使用します。</p></td>
</tr>
<tr class="even">
<td><p><strong>Accept</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>TRUE または NULL。TRUE の場合は、Reject と Cancel が NULL になります。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Reject</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>TRUE または NULL。TRUE の場合は、Accept と Cancel が NULL になります。</p></td>
</tr>
<tr class="even">
<td><p><strong>Cancel</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>TRUE または NULL。TRUE の場合は、Accept と Reject が NULL になります。</p></td>
</tr>
</tbody>
</table>

