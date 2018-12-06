---
title: 'Lync Server 2013: McuJoinsAndLeaves テーブル'
TOCTitle: McuJoinsAndLeaves テーブル
ms:assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398316(v=OCS.15)
ms:contentKeyID: 48272039
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の McuJoinsAndLeaves テーブル

 

_**トピックの最終更新日:** 2015-03-09_

このテーブルの各レコードには、ユーザーの参加または退出と会議サーバーの 1 つの組み合わせに関する通話の詳細が含まれます。たとえば、Web 会議の要素と音声ビデオの要素を含む会議にユーザーが参加すると、そのユーザーの Web 会議参加に対応する 1 つのレコードが作成され、ユーザーの音声ビデオ会議参加に対応するもう 1 つのレコードが作成されます。


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
<td><p>主/プライマリ、外部</p></td>
<td><p>このユーザーを識別する一意の番号。詳細については、「<a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>McuUserInstance</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>ユーザーが複数のコンピューターまたはデバイスで同時にログオンしている場合、McuUserInstance はユーザーとデバイスの組み合わせを一意に識別します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsFromPstn</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>ユーザーが PSTN から参加しているかどうかを示します。</p></td>
</tr>
<tr class="even">
<td><p><strong>McuId</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ、外部</p></td>
<td><p>この会議サーバーを識別する一意の番号。詳細については、「<a href="lync-server-2013-mcus-table.md">Lync Server 2013 の Mcus テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>外部</p></td>
<td><p>セッション要求の時間。<strong>SessionIdSeq</strong> と合わせて使用して、セッションを一意に識別します。詳細については、「<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 の Dialogs テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>セッションを識別するための ID 番号。セッションを一意に識別するために <strong>SessionIdTime</strong> と併用されます。詳細については、「<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 の Dialogs テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserJoinTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>ユーザーがこの会議サーバーに参加した時刻。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserLeaveTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>ユーザーがこの会議サーバーから退出した時刻。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVerId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>会議で使用されるクライアント ソフトウェアのバージョン番号を指定する ID です。詳細については、「<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の ClientVersions テーブル</a>」を参照してください。</p>
<p>このフィールドは Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
</tbody>
</table>

