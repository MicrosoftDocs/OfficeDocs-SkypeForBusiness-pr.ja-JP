---
title: ErrorReport ビュー
TOCTitle: ErrorReport ビュー
ms:assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ721887(v=OCS.15)
ms:contentKeyID: 49887148
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ErrorReport ビュー

 

_**トピックの最終更新日:** 2015-03-09_

ErrorReport ビューには報告されたエラーに関する情報が格納されます。個々のレコードが、発生した 1 つのエラーを表します。これらのエラーは、フロントエンド サーバー上で動作する CDR エージェントでキャプチャされたものか、クライアントから送られてきたものです。このビューは、Microsoft Lync Server 2013 で導入されました。


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
<td><p><strong>ErrorTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>エラーが発生した時刻。エラー を一意に識別するために ErrorReportSeq と併用されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>エラーを識別する ID 番号。エラーを一意に識別するために ErrorTime と併用されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p>エラー レポートの診断 ID。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>エラーを発生させたユーザーの URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>エラーを発生させたユーザーの URI の種類。詳細については、「<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>エラーを発生させたユーザーのテナント。詳細については、「<a href="lync-server-2013-tenants-table.md">Lync Server 2013 の Tenants テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>エラー レポートのターゲットであったユーザーの URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>エラー レポートのターゲットであったユーザーの URI の種類。詳細については、UriTypes テーブルを参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>エラー レポートのターゲットであったユーザーのテナント。詳細については、「<a href="lync-server-2013-tenants-table.md">Lync Server 2013 の Tenants テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>エラー レポートのターゲットであった会議の URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>エラー レポートのターゲットであった会議の URI の種類。詳細については、「<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>エラー レポートを発生させたセッション要求の時刻。セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。詳細については、<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 の Dialogs テーブル</a> を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>エラー レポートを発生させたセッション要求を識別する ID 番号。セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。詳細については、<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 の Dialogs テーブル</a> を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogId</strong></p></td>
<td><p>varstring(775)</p></td>
<td><p>エラーを発生させたセッションの SIP ダイアログ ID。形式は次のとおりです。</p>
<p>dialog;from-tag;to-tag</p>
<p>このデータは、次の構文を使用してテキスト形式に変換できます。</p>
<p>cast(cast(ExternalId as varbinary(max)) as varchar(max))</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVersion</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>エラーを発生させたユーザーが使用していたクライアントのバージョン。</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientType</strong></p></td>
<td><p>int</p></td>
<td><p>エラーを発生させたユーザーが使用していたクライアント。詳細については、「<a href="lync-server-2013-useragentdef-table.md">UserAgentDef テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientCategory</strong></p></td>
<td><p>nvarchar(64)</p></td>
<td><p>エラーを発生させたユーザーが使用していたクライアントのカテゴリの名前。</p></td>
</tr>
<tr class="even">
<td><p><strong>Source</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>エラーを発生させたサーバーの名前 (サーバー コンポーネントからレポートが送信された場合)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Application</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>エラーを発生させたアプリケーションの名前 (サーバー コンポーネントからレポートが送信された場合)。</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>エラー レポートを含む SIP メッセージのセッションに対する SIP 応答コード。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RequestType</strong></p></td>
<td><p>varchar(max)</p></td>
<td><p>エラーが発生した要求の種類。</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentType</strong></p></td>
<td><p>varchar(max)</p></td>
<td><p>エラーが発生した要求のコンテンツの種類。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>セッションの種類。詳細については、<a href="lync-server-2013-calltype-table.md">Lync Server 2013 の CallType テーブル</a> を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>会議に関するさまざまなコンポーネントの参加時間情報に関係する一意の識別子。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>int</p></td>
<td><p>特定のコンポーネントが会議に参加するのに必要な時間 (ミリ秒)。</p></td>
</tr>
<tr class="even">
<td><p><strong>IsCapturedByServer</strong></p></td>
<td><p>bit</p></td>
<td><p>フロントエンド サーバー上で動作する CDR エージェントでキャプチャされたエラーのレポートか、クライアントから送られてきたエラーのレポートかを示します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Flag</strong></p></td>
<td><p>smallint</p></td>
<td><p>今後の使用のために予約されています。</p></td>
</tr>
<tr class="even">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>varchar(max)</p></td>
<td><p>エラーに関する追加情報。</p></td>
</tr>
</tbody>
</table>

