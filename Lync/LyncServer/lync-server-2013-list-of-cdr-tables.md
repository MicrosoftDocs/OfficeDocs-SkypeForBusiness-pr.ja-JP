---
title: 'Lync Server 2013: CDR テーブルの一覧'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: List of CDR tables
ms:assetid: 031843fd-c7ff-4534-9b02-8847aad70807
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398084(v=OCS.15)
ms:contentKeyID: 48183254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1ac043d144e73d8e1b40ca717e278619e053fdc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832949"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-tables-in-lync-server-2013"></a>Lync Server 2013 の CDR テーブルの一覧

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-18_

通話の詳細記録 (CDR) データベーススキーマは、次の表で構成されています。

<div>

## <a name="static-tables"></a>静的なテーブル


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>テーブル</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-callpriorities-table.md">Lync Server 2013 の CallPriorities テーブル</a></p></td>
<td><p>緊急、緊急、標準、不急など、可能な通話の優先順位のリストを保存します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencejointimethresholds-table.md">Lync Server 2013 の ConferenceJoinTimeThresholds テーブル</a></p></td>
<td><p>会議参加時間のサマリーレポートで使用される分類境界を格納します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-deregistertype-table.md">Lync Server 2013 の DeRegisterType テーブル</a></p></td>
<td><p>&quot;クライアントによって開始された、&quot; &quot;登録の期限切れ&quot; &quot;、クライアントのクラッシュ&quot;など、可能なユーザー登録解除の理由のリストを保存します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-medialist-table.md">Lync Server 2013 の MediaList テーブル</a></p></td>
<td><p>データベースにエントリを生成できるメディアの種類の一覧を保存します (たとえば、IM、音声、ビデオ、ファイル転送など)。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-purgesettings-table.md">Lync Server 2013 の PurgeSettings テーブル</a></p></td>
<td><p>古い通話の詳細レコードが CDR データベースから自動的に削除されるかどうかを指定する情報を格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-roles-table.md">Lync Server 2013 の Roles テーブル</a></p></td>
<td><p>可能な電話会議の役割のリスト ([出席者] と [発表者] など) を保存します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-sipresponsemetadata-table.md">Lync Server 2013 の SIPResponseMetaData テーブル</a></p></td>
<td><p>SIP 応答コードの一覧と、各コードの分類と定義を保存します。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supporting-tables"></a>サポートテーブル


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>テーブル</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の ClientVersions テーブル</a></p></td>
<td><p>このデータベースにキャプチャされた情報を使って、通話に関係する各クライアントのクライアント (クライアントの種類とバージョン番号の両方) を保存します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 の ConferenceUris テーブル</a></p></td>
<td><p>会議関連の通話で使用される ConferenceURIs のリストを保存します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 の ContentTypes テーブル</a></p></td>
<td><p>ピアツーピア通話と電話会議の両方で使用されるセッション開始プロトコル (SIP) コンテンツタイプのリストを保存します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-devices-table.md">Lync Server 2013 の Devices テーブル</a></p></td>
<td><p>製造元、ハードウェアのバージョン、MAC アドレスなど、デバイスの一覧を保存します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-dialogs-table.md">Lync Server 2013 の Dialogs テーブル</a></p></td>
<td><p>データベース内の各セッションのダイアログ ID に関する情報を格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 の EdgeServers テーブル</a></p></td>
<td><p>外部通話に使用されるエッジサーバーの一覧を保存します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-gateways-table.md">Lync Server 2013 のゲートウェイ テーブル</a></p></td>
<td><p>VoIP (Voice over Internet Protocol) 通話に使用されるゲートウェイの一覧を保存します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 の HardwareVersions テーブル</a></p></td>
<td><p>ハードウェアバージョンのデバイス (卓上電話) の一覧を保存します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 の Manufacturers テーブル</a></p></td>
<td><p>デバイスの製造元の一覧を保存します (卓上電話)。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcus-table.md">Lync Server 2013 の Mcus テーブル</a></p></td>
<td><p>さまざまな A/V 会議サーバーとその Uri に関する情報を保存します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 の MediationServers テーブル</a></p></td>
<td><p>VoIP 通話に使用される仲介サーバーのリストを保存します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-phones-table.md">Lync Server 2013 の Phones テーブル</a></p></td>
<td><p>アーカイブされた、または通話の詳細が記録された VoIP 通話で使用されたすべての電話番号が格納されます。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-pools-table.md">Lync Server 2013 の Pools テーブル</a></p></td>
<td><p>IM メッセージがキャプチャされるプールの名前を格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-servers-table.md">Lync Server 2013 の Servers テーブル</a></p></td>
<td><p>通話に関連するサーバーの名前が格納されます。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tenants-table.md">Lync Server 2013 の Tenants テーブル</a></p></td>
<td><p>現在の展開でサポートされているテナントを格納します。 エンタープライズユーザー、フェデレーションユーザー、パブリック IM 接続ユーザー、匿名ユーザー向けの一部のビルドのテナントがあります。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の UserAgentDef テーブル</a></p></td>
<td><p>ユーザーエージェント識別子をエージェントのわかりやすい名前にマップします。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー テーブル</a></p></td>
<td><p>このデータベースに記録またはアーカイブされたセッションに参加しているユーザーの Uri を格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-userstatistics-table.md">Lync Server 2013 の UserStatistics テーブル</a></p></td>
<td><p>個々のユーザーによるシステムの使用状況に関する情報が格納されます。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a>会議 CDR レコードに固有のテーブル


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>テーブル</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-conferences-table.md">Lync Server 2013 の Conferences テーブル</a></p></td>
<td><p>ConferenceURI、開始時刻、終了時刻など、アーカイブされた、または情報が記録されたすべての会議に関する情報を保存します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencesessiondetails-table.md">Lync Server 2013 の ConferenceSessionDetails テーブル</a></p></td>
<td><p>各セッションの開始時刻、終了時刻、ユーザー ID、応答コード、診断 ID など、SIP ベースのすべての会議セッションに関する情報が格納されます。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-focusjoinsandleaves-table.md">Lync Server 2013 の FocusJoinsAndLeaves テーブル</a></p></td>
<td><p>ユーザーの役割やクライアントのバージョンなど、会議の参加と退席に関する情報を保存します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcujoinsandleaves-table.md">Lync Server 2013 の McuJoinsAndLeaves テーブル</a></p></td>
<td><p>会議に参加している、またはユーザーが参加して休暇している A/V 会議サーバーに関する情報を保存します。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a>IM 会議のメッセージのテーブル


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>テーブル</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-conferencemessagecount-table.md">Lync Server 2013 の ConferenceMessageCount テーブル</a></p></td>
<td><p>IM 会議ごとに、各ユーザーが送信したメッセージの数が保存されます。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-imreportsummary-table.md">Lync Server 2013 の IMReportSummary テーブル</a></p></td>
<td><p>組織内で開催されたインスタントメッセージセッションに関する全体的なレポートを提供します。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-peer-to-peer-sessions"></a>ピアツーピアセッションのテーブル


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>テーブル</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 の SessionDetails テーブル</a></p></td>
<td><p>各ユーザーの開始時刻、終了時刻、ユーザー ID、応答コード、メッセージ数など、すべてのピアツーピアセッションに関する情報を保存します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-filetransfers-table.md">Lync Server 2013 の FileTransfers テーブル</a></p></td>
<td><p>ファイル名や結果 (承諾、拒否、またはキャンセル) などのファイル転送セッションに関する情報を保存します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-media-table.md">Lync Server 2013 の Media テーブル</a></p></td>
<td><p>ピアツーピアセッションに関連するさまざまなメディアの種類に関する情報が格納されます。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a>VoIP 通話の詳細の表


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>テーブル</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-voipdetails-table.md">Lync Server 2013 の VoipDetails テーブル</a></p></td>
<td><p>各 [voip/PSTN 通話] には、VoIP 電話の電話 ID、使用されているゲートウェイ、切断されているパーティなど、通話に関する情報が格納されます。 電話の開始/終了時刻と応答コードのための<a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 の Sessiondetails テーブル</a>を指します。</p>
<div>

> [!NOTE]  
> 通話中に1人の当事者が VoIP ユーザーの場合、または仲介サーバーが通話に参加していた場合は、次の表でレコードが作成されます。 公衆交換電話網 (PSTN) 電話を含まない VoIP/VoIP 通話に関する情報は、 <A href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 の Sessiondetails の表</A>に記載されています。


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a>E9 の表 (1 ~ 1 の通話監査)


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>テーブル</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-locations-table.md">Lync Server 2013 の Locations テーブル</a></p></td>
<td><p>拡張 9-1-1 (E9) 通話などの各緊急通話では、通話に関する位置情報が保存されます。 電話の開始/終了時刻と応答コードのための<a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 の Sessiondetails テーブル</a>を指します。</p>
<div>

> [!NOTE]  
> このテーブルには、E9 通話の位置 blob のみが含まれています。 通話に関するその他の詳細情報については、SessionDetails テーブルを参照してください。


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a>トラブルシューティングのための表


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>テーブル</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-application-table.md">Lync Server 2013 の Application テーブル</a></p></td>
<td><p>ルーティングと接続に関連する、Lync Server 2013 内のさまざまなプロセスに関する情報を保存します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-calltype-table.md">Lync Server 2013 の CallType テーブル</a></p></td>
<td><p>[オーディオ]、[インスタントメッセージング]、[音声とビデオ]、[アプリケーションの共有] など、通話の種類に関する情報を保存します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-errorcategory-table.md">Lync Server 2013 の ErrorCategory テーブル</a></p></td>
<td><p>各 Microsoft Lync Server 2013 診断分類のフレンドリ名を格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-errordef-table.md">Lync Server 2013 ErrorDef テーブル</a></p></td>
<td><p>エラーの種類とその定義に関する情報を格納します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-errorreport-table.md">Lync Server 2013 の ErrorReport テーブル</a></p></td>
<td><p>発生したエラーに関する情報を格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-progressreport-table.md">Lync Server 2013 の ProgressReport テーブル</a></p></td>
<td><p>Lync Server 2013 プロセスに関連するさまざまな手順の進捗レポートに関する情報を格納します。</p></td>
</tr>
</tbody>
</table>


次の一覧の表は、Lync Server によって内部的に使用されます。 このドキュメントには、詳細が記載されていません。

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a>Lync Server で内部的に使用するテーブル


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>テーブル</th>
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
<td><p><strong>フロントエンドテーブル</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MSMQProcessing テーブル</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="even">
<td><p><strong>概要 tabltabl</strong></p></td>
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
<td><p><strong>タスクテーブル</strong></p></td>
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
<td><p><strong>タイム</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="even">
<td><p><strong>FailureSummary_UQ</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FailureSummary 概要</strong></p></td>
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

