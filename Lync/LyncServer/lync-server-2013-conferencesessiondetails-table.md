---
title: 'Lync Server 2013: ConferenceSessionDetails テーブル'
TOCTitle: ConferenceSessionDetails テーブル
ms:assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412741(v=OCS.15)
ms:contentKeyID: 48273044
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の ConferenceSessionDetails テーブル

 

_**トピックの最終更新日:** 2015-03-09_

各レコードは 1 つの電話会議セッションを表します。それはフォーカスがあるセッションの場合もあれば、特定の会議サーバーでのセッションの場合もあります。


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
<td><p>Datetime</p></td>
<td><p>主/プライマリ、外部</p></td>
<td><p>セッション要求の時刻。電話会議セッションを一意に識別するために <strong>SessionIdSeq</strong> と併用されます。詳細については、「<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 の Dialogs テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ、外部</p></td>
<td><p>セッションを識別するための ID 番号。電話会議セッションを一意に識別するために <strong>SessionIdTime</strong> と併用されます。詳細については、「<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 の Dialogs テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>このセッションに関連するフォーカス会議 URI。詳細については、「<a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 の ConferenceUris テーブル</a>」を参照してください。この URI はフォーカスに基づく会議 URI です。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td><p></p></td>
<td><p>定期的な電話会議のインスタンスを区別する識別子。定期的な電話会議の各インスタンスは、ConferenceURI は同じですが、ConfInstance 値が異なります。</p>
<p>このフィールドは Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>このセッションに関連する会議サーバー会議 URI。詳細については、「<a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 の ConferenceUris テーブル</a>」を参照してください。この URI は会議サーバーに基づく会議 URI です。フォーカス会議セッションでは、この列は NULL になります。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>電話会議セッションのいずれかのユーザーの ID。詳細については、「<a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p></p></td>
<td><p>エンドポイントのインスタンスを識別するための GUID。たとえば、あるユーザーが同じアカウントを使用して異なるコンピューターにログオンする場合、それぞれのコンピューターに異なるエンドポイント ID が与えられます。</p></td>
</tr>
<tr class="even">
<td><p><strong>OnBehalfOfId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>発信者が代理を務めているユーザーの ID を示します。詳細については、「<a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredById</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話の参照元であるユーザーの ID。詳細については、「<a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>会議ユーザーが使用しているクライアント バージョン。詳細については、「<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の ClientVersions テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConfClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>会議サーバーが使用しているクライアント バージョン。詳細については、「<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の ClientVersions テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>ReplaceDialogIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>外部</p></td>
<td><p>現在のセッションで置き換えられる前のダイアログを識別する ID 番号。詳細については、「<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 の Dialogs テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplaceDialogIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>セッションを識別するための ID 番号。このセッションで置き換えられたセッションを一意に識別するために <strong>ReplacesDialogIdTime</strong> と併用されます。詳細については、「<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 の Dialogs テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>IsStartedByConfServer</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>会議サーバーによって開始されたセッションであるかどうかを示します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsEndedByConfServer</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>会議サーバーによって終了されたセッションであるかどうかを示します。</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserInternal</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>社内からログオンしたユーザーであるかどうかを示します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>セッションへの招待に対するセッション開始プロトコル (SIP) 応答コード。通常は、セッションの最初の INVITE メッセージから生成されたデータが設定されます。INVITE メッセージがない場合は、関連する最初の SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>SIP ヘッダーから取得された診断 ID。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>このセッションで使用されるフロントエンド サーバーの ID。詳細については、「<a href="lync-server-2013-servers-table.md">Lync Server 2013 の Servers テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>セッションが取得されたプールの ID。詳細については、「<a href="lync-server-2013-pools-table.md">Lync Server 2013 の Pools テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話で使われている仲介サーバー。詳細については、「<a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 の MediationServers テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>GatewayId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話で使われているゲートウェイ。詳細については、「<a href="lync-server-2013-gateways-table.md">Lync Server 2013 のゲートウェイ テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServerId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話で使われているエッジ サーバー。詳細については、「<a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 の EdgeServers テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>セッションで使用されるコンテンツの種類。詳細については、「<a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 の ContentTypes テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>InviteTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>最初の INVITE 要求の時刻。通常は、セッションの最初の INVITE メッセージから生成されたデータが設定されます。INVITE メッセージがない場合は、関連する最初の SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>最初の SIP RESPONSE の時刻。通常は、セッションの最初の INVITE メッセージから生成されたデータが設定されます。INVITE メッセージがない場合は、関連する最初の SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionEndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>セッションが終了した時刻。</p></td>
</tr>
<tr class="even">
<td><p><strong>UriTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>外部</p></td>
<td><p><a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>の MCU の URI の種類の値が含まれます。クエリのパフォーマンスを向上させるために使用されます。</p>
<p>このフィールドは Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>ユーザーの属性を示すビット セット。以下の属性が定義されています。</p>
<ul>
<li><p>デスクトップ電話と統合 - 1</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>CallFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>通話の属性を示すビット セット。以下の属性が定義されています。</p>
<ul>
<li><p>再試行されたセッション - 1</p></li>
</ul></td>
</tr>
</tbody>
</table>


\* ほとんどのセッションでは、SessionIdSeq の値は 1 になります。まったく同時に複数のセッションが開始した場合、あるセッションの SessionIdSeq は 1、別のセッションは 2、などとなります。

