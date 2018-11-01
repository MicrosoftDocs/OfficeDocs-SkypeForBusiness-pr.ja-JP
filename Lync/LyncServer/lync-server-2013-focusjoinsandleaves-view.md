---
title: FocusJoinsAndLeaves ビュー
TOCTitle: FocusJoinsAndLeaves ビュー
ms:assetid: 226460ef-766f-4d61-80cb-f332b65a210d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ687992(v=OCS.15)
ms:contentKeyID: 49886874
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# FocusJoinsAndLeaves ビュー

 

_**トピックの最終更新日:** 2015-03-09_

FocusJoinsAndLeaves ビューには、1 つの会議における参加と退出についての情報が格納されます。各会議は、ユーザーが会議に参加して会議を退出するたびに書き込まれるレコードによってこのビューで表されます。このビューは Microsoft Lync Server 2013 で導入されました。


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
<td><p>会議インスタンスの時刻。会議インスタンスを一意に識別するために SessionIdSeq と併用されます。詳細については、「<a href="lync-server-2013-conferences-table.md">Lync Server 2013 の Conferences テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>会議インスタンスを識別する ID 番号。会議インスタンスを一意に識別するために SessionIdTime と併用されます。詳細については、「<a href="lync-server-2013-conferences-table.md">Lync Server 2013 の Conferences テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>会議の参加/退出情報が取得されたユーザーの URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>会議の参加/退出情報が取得されたユーザーの URI の種類。詳細については、「<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>会議の参加/退出情報が取得されたユーザーのテナント。詳細については、「<a href="lync-server-2013-tenants-table.md">Lync Server 2013 の Tenants テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>会議の参加/退出情報が取得されたユーザーの一意の識別子。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientVersion</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>会議の参加/退出情報が取得されたユーザーが使用したクライアントのバージョン。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientType</strong></p></td>
<td><p>int</p></td>
<td><p>会議の参加/退出情報が取得されたユーザーが使用したクライアント。詳細については、「<a href="lync-server-2013-useragentdef-table.md">UserAgentDef テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>会議の参加/退出情報が取得されたユーザーが使用したクライアントのカテゴリ名。</p></td>
</tr>
<tr class="even">
<td><p><strong>FocusUserInstance</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>IsuserInternal</strong></p></td>
<td><p>bit</p></td>
<td><p>ユーザーが内部ユーザーか否かを表すビット。</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>セッション要求の時刻。セッションを一意に識別するために SessionIdSeq と併用されます。詳細については、「<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 の Dialogs テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>ユーザーが複数のコンピューターまたはデバイスから同時にログオンしている場合は、UserInstance を使用してユーザーとデバイスの組み合わせを一意に識別します。</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogId</strong></p></td>
<td><p>varchar(775)</p></td>
<td><p>セッションの SIP ダイアログ ID。書式は dialog;from-tag;to-tag となります。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserJoinTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>ユーザーが会議に参加した時刻。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserLeaveTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>ユーザーが会議を退出した時刻。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserRole</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>会議でのユーザーの役割 (発表者、参加者など)。</p></td>
</tr>
</tbody>
</table>

