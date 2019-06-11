---
title: 'Lync Server 2013: ErrorReport view'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ErrorReport view
ms:assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721887(v=OCS.15)
ms:contentKeyID: 49733821
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b50a2615fe83ed481d9642ac6895120f20b9fd0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833209"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-view-in-lync-server-2013"></a>Lync Server 2013 での ErrorReport の表示

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-01-22_

ErrorReport ビューには、報告されたエラーに関する情報が格納されます。 各レコードはエラー発生の1つです。 このエラーは、フロントエンドサーバーで実行されている CDR エージェントまたはクライアントから送信された cd-r エージェントによってキャプチャされます。 このビューは、Microsoft Lync Server 2013 で導入されました。


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
<td><p>エラーが発生した時刻。 エラーを一意に識別するには、ErrorReportSeq と組み合わせて使います。</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>エラーを識別する ID 番号。 エラーを一意に識別するための ErrorTime と共に使用されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p>エラーレポートの診断 ID。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>エラーを発生させたユーザーの URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>エラーを発生させたユーザーの URI の種類。 詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>エラーを発生させたユーザーのテナント。 詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの一覧</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>エラーレポートのターゲットであるユーザーの URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>エラーレポートの対象となるユーザーの URI の種類。 詳細については、UriTypes の表を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>すべての Ant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>エラーレポートの対象ユーザーのテナント。 詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの一覧</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>エラーレポートのターゲットとなった会議の URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>エラーレポートのターゲットとなった会議の URI の種類。 詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>セッション Id</strong></p></td>
<td><p>datetime</p></td>
<td><p>エラーレポートを生成したセッション要求の時刻。 セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。 詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>エラーレポートを生成したセッション要求を識別する ID 番号。 セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。 詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>この Id</strong></p></td>
<td><p>varstring (775)</p></td>
<td><p>エラーを発生させたセッションの SIP ダイアログ ID。 形式は次のとおりです。</p>
<p>ダイアログ; 開始タグからタグへ</p>
<p>このデータは、次の構文を使用してテキスト形式に変換できます。</p>
<p>キャスト (cast (ExternalId as varbinary (max)) (varchar (max)))</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVersion</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>エラーの発生元のユーザーによって使用されたクライアントのバージョン。</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientType</strong></p></td>
<td><p>int</p></td>
<td><p>エラーの発生元のユーザーによって使用されたクライアント。 詳細については、「 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の Useragentdef テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>エラーの発生元のユーザーによって使用されたクライアントのカテゴリの名前です。</p></td>
</tr>
<tr class="even">
<td><p><strong>ソース</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>エラーが発生したサーバーの名前 (サーバーコンポーネントからレポートが送信された場合)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Application</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>エラーの発生元のアプリケーションの名前 (サーバーコンポーネントからレポートが送信された場合)。</p></td>
</tr>
<tr class="even">
<td><p><strong>返信</strong></p></td>
<td><p>int</p></td>
<td><p>エラーレポートが含まれる SIP メッセージのセッションへの SIP 応答コード。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RequestType</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>失敗した要求の種類。</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentType</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>失敗した要求のコンテンツタイプ。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>セッションの種類。 詳細については、「 <a href="lync-server-2013-calltype-table.md">Lync Server 2013 の CallType テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>長さ</p></td>
<td><p>電話会議に参加しているさまざまなコンポーネントについての、固有の識別子による結合時間情報の関連付け。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SetupTime 時間</strong></p></td>
<td><p>int</p></td>
<td><p>特定のコンポーネントが会議に参加するために必要な時間 (ミリ秒単位) です。</p></td>
</tr>
<tr class="even">
<td><p><strong>IsCapturedByServer</strong></p></td>
<td><p>bit</p></td>
<td><p>エラーレポートが、フロントエンドサーバーで実行されている CDR エージェントまたはクライアントによってキャプチャされたかどうかを示します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>フラッグ</strong></p></td>
<td><p>smallint</p></td>
<td><p>今後の使用のために予約されています。</p></td>
</tr>
<tr class="even">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>エラーに関する追加情報。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FrontEnd</strong></p></td>
<td><p>nvarchar</p></td>
<td><p>レポートを提出したフロントエンドサーバーの完全修飾ドメイン名。</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>nvarchar</p></td>
<td><p>レポートを提出したフロントエンドサーバーを含むプールの完全修飾ドメイン名。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

