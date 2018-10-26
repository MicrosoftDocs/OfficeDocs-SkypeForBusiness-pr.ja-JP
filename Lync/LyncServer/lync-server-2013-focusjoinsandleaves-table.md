---
title: 'Lync Server 2013: FocusJoinsAndLeaves テーブル'
TOCTitle: FocusJoinsAndLeaves テーブル
ms:assetid: e6f0212c-67e9-4061-8720-d0296e855991
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg399026(v=OCS.15)
ms:contentKeyID: 48274004
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の FocusJoinsAndLeaves テーブル

 

_**トピックの最終更新日:** 2015-03-09_

このテーブルの各レコードには、1 人のユーザーが 1 つの会議で行った参加および退席についての CDR 情報が格納されています。ユーザーが会議で行ったそれぞれの参加および退席について、このテーブルで各会議が 1 つのレコードで表されます。


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
<td><p>会議インスタンスの時間。 <strong>SessionIdSeq</strong> と合わせて使用して、会議インスタンスを一意に識別します。詳細については、「<a href="lync-server-2013-conferences-table.md">Lync Server 2013 の Conferences テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ、外部</p></td>
<td><p>会議インスタンスを識別する ID 番号。 <strong>SessionIdTime</strong> と合わせて使用して、会議インスタンスを一意に識別します。詳細については、「<a href="lync-server-2013-conferences-table.md">Lync Server 2013 の Conferences テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主/プライマリ、外部</p></td>
<td><p>セッション要求の時間。 <strong>SessionIdSeq</strong> と合わせて使用して、セッションを一意に識別します。詳細については、「<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 の Dialogs テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ、外部</p></td>
<td><p>セッションを識別する ID 番号。 <strong>SessionIdTime</strong> と合わせて使用して、セッションを一意に識別します。詳細については、「<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 の Dialogs テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>このユーザーを示す一意の番号。 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー テーブル</a>から参照されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>FocusUserInstance</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>ユーザーが複数のコンピューターまたはデバイスから同時にログオンしている場合、 <strong>UserInstance</strong> を使用して、ユーザーとデバイスの組み合わせを一意に識別します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsUserInternal</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>ユーザーが内部からログオンしているかどうか。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserRole</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>会議でのこのユーザーの役割 (発表者、参加者など)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserJoinTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>このユーザーが会議に参加した時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserLeaveTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>このユーザーが会議から退席した時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVerId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>ユーザーのクライアント ソフトウェアのバージョン。 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の ClientVersions テーブル</a>への参照です。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td><p></p></td>
<td><p>会議で使用されるエンドポイントのグローバル一意識別子 (GUID) です。</p>
<p>このフィールドは Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
</tbody>
</table>

