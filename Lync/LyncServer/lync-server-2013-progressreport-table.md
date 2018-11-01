---
title: 'Lync Server 2013: ProgressReport テーブル'
TOCTitle: ProgressReport テーブル
ms:assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg425864(v=OCS.15)
ms:contentKeyID: 48271781
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の ProgressReport テーブル

 

_**トピックの最終更新日:** 2015-03-09_

進行状況レポートは、通話またはセッションの完了後にクライアントによってデータベースにアップロードされたデータに基づきます。進行状況レポートは、Lync Server 2013 による診断時に役立ちそうな通話とセッションのみを対象として書き込まれます。

ErrorTime、ErrorReportSeq、および ProgressReportSeq フィールドは、必ずしもエラーを参照するのではなく、通話またはメッセージの状態を示すメッセージを参照します。


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
<td><p>主/プライマリ、外部</p></td>
<td><p>この進行状況レポートを含む進行状況エラー レポートの日時。詳細については、「<a href="lync-server-2013-errorreport-table.md">Lync Server 2013 の ErrorReport テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorId</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ、外部</p></td>
<td><p>進行状況レポートを一意に識別するための ID 番号。ErrorTime と ProgressReportSeq と併用されます。詳細については、「<a href="lync-server-2013-errorreport-table.md">Lync Server 2013 の ErrorReport テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ、外部</p></td>
<td><p>エラー レポートを識別する ID 番号。ErrorReporSeq は、一意的にエラー レポートを識別する目的で ErrorTime と共に使用されます。詳細については、「<a href="lync-server-2013-errorreport-table.md">Lync Server 2013 の ErrorReport テーブル</a>」を参照してください。</p>
<p>このフィールドは Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>ProgressReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>進行状況レポートを識別するための ID 番号。進行状況レポートを一意に識別するために ErrorTime と ErrorReportSeq と併用されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>進行状況レポートの診断 ID。</p>
<p>このフィールドは Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>SourceId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>(レポートがサーバー コンポーネントから送信された場合) エラー レポートを送信したサーバー。詳細は「<a href="lync-server-2013-servers-table.md">Lync Server 2013 の Servers テーブル</a>」を参照してください。このフィールドは Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ApplicationId</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>レポートの対象となる Lync Server プロセス。詳細については、「アプリケーション テーブル」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>詳細</strong></p></td>
<td><p>画像</p></td>
<td><p></p></td>
<td><p>進行状況レポートの詳細。記憶域を節約するできるようにバイナリ形式で格納されます。このデータは、次のコードを使用してテキスト形式に変換できます。</p>
<p>cast(cast(Detail as varbinary(max)) as varchar(max))</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td><p></p></td>
<td><p>電話会議に関係するさまざまなコンポーネントの参加時間情報を関連付ける一意識別子。</p>
<p>このフィールドは Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>特定のコンポーネントが電話会議に参加する時間 (単位はミリ秒)。</p>
<p>このフィールドは Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
</tbody>
</table>

