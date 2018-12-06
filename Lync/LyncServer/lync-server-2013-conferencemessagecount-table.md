---
title: 'Lync Server 2013: ConferenceMessageCount テーブル'
TOCTitle: ConferenceMessageCount テーブル
ms:assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398590(v=OCS.15)
ms:contentKeyID: 48272578
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の ConferenceMessageCount テーブル

 

_**トピックの最終更新日:** 2015-03-09_

このテーブル内のそれぞれのレコードは、ある IM 会議での 1 人のユーザーを表し、そのユーザーが送信したメッセージの数を含みます。それぞれの会議は、このテーブル内の複数のレコードによって表されます。ユーザーごとに 1 つのレコードが使用されます。


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
<td><p>会議インスタンスの時間。<strong>SessionIdSeq</strong> と合わせて使用して、会議インスタンスを一意に識別します。詳細については、「<a href="lync-server-2013-conferences-table.md">Lync Server 2013 の Conferences テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ、外部</p></td>
<td><p>会議インスタンスを識別する ID 番号。<strong>SessionIdTime</strong> と合わせて使用して、会議インスタンスを一意に識別します。詳細については、「<a href="lync-server-2013-conferences-table.md">Lync Server 2013 の Conferences テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>このユーザーを示す一意の番号。<a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー テーブル</a>から参照されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>MessageCount</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>この会議中にこのユーザーが送信したメッセージの数です。</p></td>
</tr>
</tbody>
</table>

