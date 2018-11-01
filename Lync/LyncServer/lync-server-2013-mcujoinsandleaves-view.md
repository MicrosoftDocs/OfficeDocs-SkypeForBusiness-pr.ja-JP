---
title: McuJoinsAndLeaves ビュー
TOCTitle: McuJoinsAndLeaves ビュー
ms:assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688088(v=OCS.15)
ms:contentKeyID: 49886994
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# McuJoinsAndLeaves ビュー

 

_**トピックの最終更新日:** 2015-03-09_

McuJoinsAndLeaves ビューには、1 つの会議サーバーのユーザーの参加および退出情報についての情報が格納されます。このビューの各レコードには、ユーザーの参加または退出と会議サーバーの 1 つの組み合わせに関する通話の詳細が含まれます。 このビューは、Microsoft Lync Server 2013 で導入されました。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>データ型</th>
<th>詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>会議インスタンスの時間。SessionIdSeq と合わせて使用して、会議インスタンスを一意に識別します。詳細については、「<a href="lync-server-2013-conferences-table.md">Lync Server 2013 の Conferences テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>会議インスタンスを識別する ID 番号。SessionIdTime と合わせて使用して、会議インスタンスを一意に識別します。詳細については、「<a href="lync-server-2013-conferences-table.md">Lync Server 2013 の Conferences テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuUri</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>ユーザーが接続した会議サーバーの URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>McuUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>ユーザーが接続した会議サーバーの URI。詳細については、「<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>会議サーバーの参加/退出情報がキャプチャされたユーザーの URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>会議サーバーの参加/退出情報がキャプチャされたユーザーの URI の種類。詳細については、「<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>会議サーバーの参加/退出情報がキャプチャされたユーザーのテナント。詳細については、「<a href="lync-server-2013-tenants-table.md">Lync Server 2013 の Tenants テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientVersion</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>会議サーバーの参加/退出情報がキャプチャされたユーザーが使用しているクライアントのバージョン。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientType</strong></p></td>
<td><p>int</p></td>
<td><p>会議サーバーの参加/退出情報がキャプチャされたユーザーが使用しているクライアント。詳細については、「<a href="lync-server-2013-useragentdef-table.md">UserAgentDef テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>会議サーバーの参加/退出情報がキャプチャされたユーザーが使用しているクライアントのカテゴリ名。</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuUserInstance</strong></p></td>
<td><p>int</p></td>
<td><p>複数のデバイスに同時にログオンしているユーザー用に、ユーザーとデバイスの組み合わせを一意に識別します。</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserFromPstn</strong></p></td>
<td><p>bit</p></td>
<td><p>ユーザーが内部ユーザーかどうかを示すビット。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>セッション要求の時間。SessionIdSeq と合わせて使用して、セッションを一意に識別します。詳細については、「<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 の Dialogs テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>セッションを識別するための ID 番号。セッションを一意に識別するために SessionIdTime と併用されます。詳細については、「<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 の Dialogs テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogId</strong></p></td>
<td><p>varchar(775)</p></td>
<td><p>セッションの SIP ダイアログ ID。形式は dialog;from-tag;to-tag です。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserJoinTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>ユーザーが会議サーバーに参加した時刻。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserLeaveTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>ユーザーが会議サーバーから退出した時刻。</p></td>
</tr>
</tbody>
</table>

