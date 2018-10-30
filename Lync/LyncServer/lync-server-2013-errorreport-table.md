---
title: 'Lync Server 2013: ErrorReport テーブル'
TOCTitle: ErrorReport テーブル
ms:assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412826(v=OCS.15)
ms:contentKeyID: 48273260
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の ErrorReport テーブル

 

_**トピックの最終更新日:** 2015-06-22_

ErrorReport テーブルには、発生したエラーに関する情報が格納されます。個々のレコードが、発生した 1 つのエラーを表します。これらのエラーは、フロントエンド サーバー上で動作する CDR エージェントでキャプチャされたものか、クライアントから送られてきたものです。


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
<td><p><strong>ErrorTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主/プライマリ</p></td>
<td><p>エラーが発生した日時。</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>エラー レポートを識別する ID 番号。エラー レポートを一意に識別するために <strong>ErrorTime</strong> と併用されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ErrorId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>エラーの種類の一意 ID。詳細については、「<a href="lync-server-2013-errordef-table.md">Lync Server 2013 ErrorDef テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUserId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>エラーを起こした要求を出したユーザー。詳細については、「<a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUserId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>エラーを起こした要求の通話先ユーザー。詳細については、「<a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>エラーに関連する会議 URI。詳細については、「<a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 の ConferenceUris テーブル</a>」を参照してください。通常、ConferenceUriId が NULL でなければ、FromUserId または ToUserId が NULL になります。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>外部</p></td>
<td><p>セッションを一意に識別するために <strong>SessionIdSeq</strong> と併用されます。詳細については、「<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 の Dialogs テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>セッションを識別するための ID 番号。セッションを一意に識別するために <strong>SessionIdTime</strong> と併用されます。詳細については、「<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 の Dialogs テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SourceId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>エラー報告を送信したサーバー (報告がサーバー コンポーネントから送信されている場合)。詳細については、「<a href="lync-server-2013-servers-table.md">Lync Server 2013 の Servers テーブル</a>」を参照してください。</p>
<p>このフィールドは Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>ApplicationId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>エラー報告を送信したサーバー (報告がサーバー コンポーネントから送信されている場合)。詳細については、「<a href="lync-server-2013-application-table.md">Lync Server 2013 の Application テーブル</a>」を参照してください。</p>
<p>このフィールドは Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>画像</p></td>
<td><p> </p></td>
<td><p>エラーに関するその他の情報。</p>
<p>このデータは、次の構文を使用してテキスト形式に変換できます。</p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><strong>ClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>エラー レポートを送信するエンドポイントのクライアント バージョン。詳細については、「<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の ClientVersions テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsCapturedByServer</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>フロントエンド サーバー上で動作する CDR エージェントでキャプチャされたエラーのレポートか、クライアントから送られてきたエラーのレポートかを示します。</p></td>
</tr>
<tr class="even">
<td><p><strong>Flag</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>今後の使用のために予約されています。</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td><p></p></td>
<td><p>会議に関するさまざまなコンポーネントの参加時間情報に関係する一意の識別子。</p>
<p>このフィールドは Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>特定のコンポーネントが会議に参加するのに必要な時間 (ミリ秒)。</p>
<p>このフィールドは Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>エラー報告を生成したサーバーの完全修飾ドメイン名を表します。</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>エラー報告が生成されたプールの完全修飾ドメイン名を表します。</p></td>
</tr>
</tbody>
</table>

