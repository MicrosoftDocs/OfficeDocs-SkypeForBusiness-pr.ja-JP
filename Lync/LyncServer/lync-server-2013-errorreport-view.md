---
title: 'Lync Server 2013: ErrorReport ビュー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorReport view
ms:assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721887(v=OCS.15)
ms:contentKeyID: 49733821
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8792154c88c74049a785ddfb9ebbca55a52bc26
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514454"
---
# <a name="errorreport-view-in-lync-server-2013"></a>Lync Server 2013 の ErrorReport ビュー

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-01-22_

ErrorReport ビューは、報告されたエラーに関する情報を格納します。 各レコードは、エラー発生の1つです。 エラーは、フロントエンドサーバーで実行されている CDR エージェント、またはクライアントから送信されます。 このビューは Microsoft Lync Server 2013 で導入されました。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Column</th>
<th>データ型</th>
<th>詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ErrorTime</strong></p></td>
<td><p>日付型</p></td>
<td><p>エラーが発生した時刻。エラー を一意に識別するために ErrorReportSeq と併用されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>Errorreportseq、</strong></p></td>
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
<td><p>nvarchar (450)</p></td>
<td><p>エラーを発生させたユーザーの URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Fromuritoff</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>エラーを発生させたユーザーの URI の種類。 詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a> 」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>エラーを発生させたユーザーのテナント。 詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの表</a> 」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>エラーレポートのターゲットであったユーザーの URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>エラーレポートの対象となるユーザーの URI の種類です。 詳細については、「UriTypes Table」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>すべての Ant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>エラーレポートを対象とするユーザーのテナント。 詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの表</a> 」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>エラーレポートのターゲットであった会議の URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>エラーレポートのターゲットであった会議の URI の種類。 詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a> 」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>日付型</p></td>
<td><p>エラーレポートを生成したセッション要求の時刻。 セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。 詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessionidseq と</strong></p></td>
<td><p>int</p></td>
<td><p>エラーレポートを生成したセッション要求を識別する ID 番号。 セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。 詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogId</strong></p></td>
<td><p>varstring (775)</p></td>
<td><p>エラーを発生させたセッションの SIP ダイアログ ID。 形式は次のとおりです。</p>
<p>dialog、from タグ、およびタグ</p>
<p>このデータは、次の構文を使用してテキスト形式に変換できます。</p>
<p>cast (varbinary (varbinary (max) としての ExternalId) as varchar (max))</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVersion</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>エラーを発生させたユーザーが使用しているクライアントのバージョン。</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientType</strong></p></td>
<td><p>int</p></td>
<td><p>エラーを発生させたユーザーが使用しているクライアント。 詳細については、「 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の Useragentdef テーブル</a> 」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>エラーを発生させたユーザーが使用しているクライアントのカテゴリの名前。</p></td>
</tr>
<tr class="even">
<td><p><strong>Source</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>エラーを発生させたサーバーの名前 (サーバー コンポーネントからレポートが送信された場合)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Application</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>エラーを発生させたアプリケーションの名前 (サーバー コンポーネントからレポートが送信された場合)。</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>エラーレポートを含む SIP メッセージのセッションに対する SIP 応答コード。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RequestType</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>失敗した要求の種類。</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentType</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>失敗した要求のコンテンツの種類。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>セッションの種類。 詳細については、「 <a href="lync-server-2013-calltype-table.md">Lync Server 2013 の CallType テーブル</a> 」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>識別子</p></td>
<td><p>会議に関するさまざまなコンポーネントの参加時間情報に関係する一意の識別子。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SetupTime タイム</strong></p></td>
<td><p>int</p></td>
<td><p>特定のコンポーネントが会議に参加するのに必要な時間 (ミリ秒)。</p></td>
</tr>
<tr class="even">
<td><p><strong>IsCapturedByServer</strong></p></td>
<td><p>若干</p></td>
<td><p>エラー報告がフロントエンドサーバーで実行されている CDR エージェントによってキャプチャされたか、クライアントによって送信されたかを示します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Flag</strong></p></td>
<td><p>smallint</p></td>
<td><p>将来使用するために予約されています。</p></td>
</tr>
<tr class="even">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>エラーに関する追加情報。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FrontEnd</strong></p></td>
<td><p>nvarchar</p></td>
<td><p>レポートを送信したフロントエンドサーバーの完全修飾ドメイン名。</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>nvarchar</p></td>
<td><p>レポートを送信したフロントエンドサーバーが含まれているプールの完全修飾ドメイン名。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

