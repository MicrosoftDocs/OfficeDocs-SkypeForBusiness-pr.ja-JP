---
title: 'Lync Server 2013: CDR テーブルのリスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of CDR tables
ms:assetid: 031843fd-c7ff-4534-9b02-8847aad70807
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398084(v=OCS.15)
ms:contentKeyID: 48183254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbcd509d0abd05c12bd3443fe35fdd8c3f8a8885
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513974"
---
# <a name="list-of-cdr-tables-in-lync-server-2013"></a>Lync Server 2013 の CDR テーブルの一覧

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-18_

通話詳細記録 (CDR) データベース スキーマは、次のテーブルで構成されています。

<div>

## <a name="static-tables"></a>静的テーブル


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-callpriorities-table.md">Lync Server 2013 の CallPriorities テーブル</a></p></td>
<td><p>可能な通話優先順位の一覧を格納します (緊急、至急、通常、非至急など)。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencejointimethresholds-table.md">Lync Server 2013 の ConferenceJoinTimeThresholds テーブル</a></p></td>
<td><p>電話会議参加時間の概要レポートで使用される分類の境界を格納します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-deregistertype-table.md">Lync Server 2013 の DeRegisterType テーブル</a></p></td>
<td><p>ユーザーが開始した &quot; 、 &quot; &quot; 登録期限切れ、クライアントクラッシュなど、ユーザーに対して発生する可能性のある登録解除の理由の一覧を格納 &quot; &quot; &quot; します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-medialist-table.md">Lync Server 2013 の MediaList テーブル</a></p></td>
<td><p>データベースのエントリを生成できるメディアの種類の一覧を格納します (IM、音声、ビデオ、ファイル送信など)。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-purgesettings-table.md">Lync Server 2013 の PurgeSettings テーブル</a></p></td>
<td><p>通話詳細記録を CDR データベースから自動的に削除するかどうか (削除する場合はそのタイミング) を指定する情報を格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-roles-table.md">Lync Server 2013 の Roles テーブル</a></p></td>
<td><p>可能な電話会議の役割の一覧を格納します (参加者、発表者など)。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-sipresponsemetadata-table.md">Lync Server 2013 の SIPResponseMetaData テーブル</a></p></td>
<td><p>SIP 応答コードの一覧と、それらの各コードの分類および定義を格納します。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supporting-tables"></a>サポート テーブル


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の ClientVersions テーブル</a></p></td>
<td><p>通話に関わった各クライアントのクライアント情報 (クライアントの種類とバージョン番号の両方) およびこのデータベースでキャプチャされた情報を格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 の ConferenceUris テーブル</a></p></td>
<td><p>電話会議関連の通話で使用された ConferenceURI の一覧を格納します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 の ContentTypes テーブル</a></p></td>
<td><p>ピアツーピア通話と電話会議の両方で使用されるセッション開始プロトコル (SIP) のコンテンツの種類の一覧を格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-devices-table.md">Lync Server 2013 の Devices テーブル</a></p></td>
<td><p>デバイスの一覧を格納します。製造元、ハードウェアのバージョン、MAC アドレスが含まれます。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a></p></td>
<td><p>データベースでの各セッションのダイアログ ID に関する情報を格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 の EdgeServers テーブル</a></p></td>
<td><p>外線発信に使用されるエッジ サーバーの一覧を格納します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-gateways-table.md">Lync Server 2013 のゲートウェイテーブル</a></p></td>
<td><p>ボイス オーバー インターネット プロトコル (VoIP) 通話に使用されるゲートウェイの一覧を格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 の [ハードウェアバージョン表の一覧</a></p></td>
<td><p>デバイス (電話) のハードウェア バージョンの一覧を格納します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 の [製造元の表」</a></p></td>
<td><p>デバイス (電話) の製造元の一覧を格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcus-table.md">Lync Server 2013 の mcu テーブル</a></p></td>
<td><p>さまざまな音声ビデオ会議サーバーとその URI に関する情報を格納します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 の MediationServers テーブル</a></p></td>
<td><p>VoIP 通話に使用される仲介サーバーの一覧を格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-phones-table.md">Lync Server 2013 の電話表</a></p></td>
<td><p>アーカイブされた VoIP 通話または通話の詳細が記録された VoIP 通話において使用されたすべての電話番号を格納します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-pools-table.md">Lync Server 2013 のプールテーブル</a></p></td>
<td><p>IM メッセージがキャプチャされたプールの名前を格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-servers-table.md">Lync Server 2013 のサーバーテーブル</a></p></td>
<td><p>通話に関係したサーバーの名前を格納します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントテーブル</a></p></td>
<td><p>現在の展開でサポートされるテナントを格納します。 エンタープライズ ユーザー用、フェデレーション ユーザー用、パブリック IM 接続ユーザー用、および匿名ユーザー用に、複数の組み込みテナントがあります。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の UserAgentDef テーブル</a></p></td>
<td><p>ユーザー エージェント識別子をエージェントを表す名前にマッピングします。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザーテーブル</a></p></td>
<td><p>このデータベースに記録またはアーカイブされたセッションに参加していたユーザーのユーザー URI を格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-userstatistics-table.md">Lync Server 2013 の UserStatistics テーブル</a></p></td>
<td><p>個別のユーザーによるシステムの使用状況に関する情報を格納します。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a>電話会議 CDR レコードに固有のテーブル


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-conferences-table.md">Lync Server 2013 の会議テーブル</a></p></td>
<td><p>アーカイブされた、または詳細が記録されたすべての電話会議に関する情報を格納します (ConferenceURI、開始時刻、終了時刻など)。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencesessiondetails-table.md">Lync Server 2013 の ConferenceSessionDetails テーブル</a></p></td>
<td><p>すべての SIP ベースの電話会議セッションに関する情報を格納します (各セッションの開始時刻と終了時刻、ユーザー ID、応答コード、診断 ID など)。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-focusjoinsandleaves-table.md">Lync Server 2013 の FocusJoinsAndLeaves テーブル</a></p></td>
<td><p>電話会議の参加および退出に関する情報を格納します (ユーザーの役割、クライアントのバージョンなど)。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcujoinsandleaves-table.md">Lync Server 2013 の McuJoinsAndLeaves テーブル</a></p></td>
<td><p>電話会議に関係する音声ビデオ会議サーバーおよびユーザーの参加と退出の時刻に関する情報を格納します。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a>IM 会議でのメッセージ関するテーブル


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-conferencemessagecount-table.md">Lync Server 2013 の ConferenceMessageCount テーブル</a></p></td>
<td><p>IM 会議ごとに、各ユーザーが送信したメッセージの数を格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-imreportsummary-table.md">Lync Server 2013 の IMReportSummary テーブル</a></p></td>
<td><p>組織で行われたインスタント メッセージング セッションに関する概要レポートを提供します。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-peer-to-peer-sessions"></a>ピアツーピア セッションに関するテーブル


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 の SessionDetails テーブル</a></p></td>
<td><p>すべてのピアツーピア セッションに関する情報を格納します (各ユーザーの開始時刻と終了時刻、ユーザー ID、応答コード、メッセージ数など)。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-filetransfers-table.md">Lync Server 2013 の FileTransfers テーブル</a></p></td>
<td><p>ファイル転送セッションに関する情報を格納します (ファイル名、結果 (許可、禁止、取り消し) など)。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-media-table.md">Lync Server 2013 のメディアテーブル</a></p></td>
<td><p>ピアツーピア セッションに関係するメディアの種類に関する情報を格納します。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a>VoIP 通話の詳細に関するテーブル


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-voipdetails-table.md">Lync Server 2013 の VoipDetails テーブル</a></p></td>
<td><p>各 2 パーティ VoIP/PSTN 通話について、通話に関する情報を格納します (VoIP 電話の電話 ID、使用されたゲートウェイ、切断したパーティなど)。 通話の開始/終了時刻と応答コードのための <a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 の Sessiondetails テーブル</a> を参照します。</p>
<div>

> [!NOTE]  
> 通話の 1 つのパーティが VoIP ユーザーの場合、または仲介サーバーが通話に関係していた場合、このテーブルにレコードが作成されます。 公衆交換電話網 (PSTN) 電話を含まない VoIP/VoIP 通話に関する情報は、 <A href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 の Sessiondetails テーブル</A>に記録されます。


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a>E9-1-1 通話監査に関するテーブル


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-locations-table.md">Lync Server 2013 の場所テーブル</a></p></td>
<td><p>Enhanced 9-1-1 (E9-1-1) 呼び出しなどの緊急呼び出しごとに、通話に関する場所情報を格納します。 通話の開始/終了時刻と応答コードのための <a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 の Sessiondetails テーブル</a> を参照します。</p>
<div>

> [!NOTE]  
> このテーブルには、E9-1-1 呼び出しの場所の BLOB だけが格納されます。通話に関する他の詳細情報については、SessionDetails テーブルを参照してください。


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a>トラブルシューティングに関するテーブル


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-application-table.md">Lync Server 2013 のアプリケーションテーブル</a></p></td>
<td><p>ルーティングと接続に関係する Lync Server 2013 内のさまざまなプロセスに関する情報を格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-calltype-table.md">Lync Server 2013 の CallType テーブル</a></p></td>
<td><p>通話の種類に関する情報を格納します ("音声"、"インスタント メッセージング"、Instant Messaging"、"音声とビデオ"、アプリケーション共有" など)。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-errorcategory-table.md">Lync Server 2013 の ErrorCategory テーブル</a></p></td>
<td><p>各 Microsoft Lync Server 2013 診断分類のフレンドリ名を格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-errordef-table.md">Lync Server 2013 の ErrorDef テーブル</a></p></td>
<td><p>エラーの種類およびその定義に関する情報を格納します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-errorreport-table.md">Lync Server 2013 の ErrorReport テーブル</a></p></td>
<td><p>発生したエラーに関する情報を格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-progressreport-table.md">Lync Server 2013 の進捗レポートの表</a></p></td>
<td><p>Lync Server 2013 プロセスに関係するさまざまな手順の進捗レポートに関する情報を格納します。</p></td>
</tr>
</tbody>
</table>


次の表は、Lync Server によって内部的に使用されます。 これらのテーブルの詳細については、このドキュメントでは説明しません。

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a>Lync Server の内部用テーブル


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>DbConfigDateTime</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="even">
<td><p><strong>DbConfigInt</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DbErrorMessage</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="even">
<td><p><strong>FrontEnd テーブル</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MSMQProcessing テーブル</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="even">
<td><p><strong>概要 (Tabl)</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Syndicators テーブル</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="even">
<td><p><strong>SyndicatorsTenantMap テーブル</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Task テーブル</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserStatistics</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UsageSummary_UQ</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="even">
<td><p><strong>UsageSummary</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DaylightSavingYears</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="even">
<td><p><strong>TimeZoneConfiguration</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="odd">
<td><p><strong>TimeZones</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="even">
<td><p><strong>FailureSummary_UQ</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FailureSummary</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="even">
<td><p><strong>ServerSummary</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagMetaData</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

