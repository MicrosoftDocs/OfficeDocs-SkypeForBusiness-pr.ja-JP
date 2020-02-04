---
title: 'Lync Server 2013: ErrorReport テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorReport table
ms:assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412826(v=OCS.15)
ms:contentKeyID: 48185129
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8de4163f94d5848808c5b01c34b1676d3a0bbcff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735387"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-table-in-lync-server-2013"></a>Lync Server 2013 の ErrorReport テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-28_

ErrorReport テーブルには、発生したエラーに関する情報が格納されます。 各レコードはエラー発生の1つです。 このエラーは、フロントエンドサーバーで実行されている CDR エージェントまたはクライアントから送信された cd-r エージェントによってキャプチャされます。


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
<td><p>Primary</p></td>
<td><p>エラーが発生した日付と時刻。</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>エラーレポートを識別する ID 番号。 エラーレポートを一意に識別するための<strong>Errortime</strong>と組み合わせて使用されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ErrorId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>エラーの種類の一意の ID です。 詳細については、「 <a href="lync-server-2013-errordef-table.md">Lync Server 2013 の Errordef テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUserId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>エラーの原因となった要求を生成したユーザー。 詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザーテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUserId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>エラーの原因となった要求の送信先ユーザー。 詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザーテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>エラーに関連する会議の URI。 詳細については、「 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 の ConferenceUris テーブル</a>」を参照してください。 通常、ConferenceUriId が null でない場合は、FromUserId または ToUserId は null になります。</p></td>
</tr>
<tr class="odd">
<td><p><strong>セッション Id</strong></p></td>
<td><p>datetime</p></td>
<td><p>外部</p></td>
<td><p>セッションを一意に識別するために<strong>Sessionidseq</strong>と組み合わせて使用されます。 詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>セッションを識別する ID 番号。 セッションを一意に識別するために<strong>Sessionidtime</strong>と組み合わせて使用されます。 詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SourceId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>エラーレポートを送信したサーバー (レポートがサーバーコンポーネントから送信されている場合)。 詳細については、「 <a href="lync-server-2013-servers-table.md">Lync Server 2013 のサーバーの表</a>」を参照してください。</p>
<p>このフィールドは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>ApplicationId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>エラーレポートを送信したサーバー (レポートがサーバーコンポーネントから送信されている場合)。 詳細については、「 <a href="lync-server-2013-application-table.md">Lync Server 2013 のアプリケーションテーブル</a>」を参照してください。</p>
<p>このフィールドは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>画像</p></td>
<td><p> </p></td>
<td><p>エラーに関する詳細情報。</p>
<p>このデータは、次の構文を使用してテキスト形式に変換できます。</p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><strong>ClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>エラーレポートを送信するエンドポイントのクライアントバージョン。 詳細については、「 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の Clientversions の表</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsCapturedByServer</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>エラーレポートは、フロントエンドサーバーで実行されている CDR エージェントまたはクライアントによってキャプチャされます。</p></td>
</tr>
<tr class="even">
<td><p><strong>フラッグ</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>今後の使用のために予約されています。</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>長さ</p></td>
<td></td>
<td><p>電話会議に参加しているさまざまなコンポーネントについての、固有の識別子による結合時間情報の関連付け。</p>
<p>このフィールドは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime 時間</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>特定のコンポーネントが会議に参加するために必要な時間 (ミリ秒単位) です。</p>
<p>このフィールドは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>エラーレポートを生成したサーバーの完全修飾ドメイン名を表します。</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>エラーレポートが生成されたプールの完全修飾ドメイン名を表します。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

