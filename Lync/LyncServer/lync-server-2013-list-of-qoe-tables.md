---
title: 'Lync Server 2013: QoE テーブルの一覧'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: List of QoE tables
ms:assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398236(v=OCS.15)
ms:contentKeyID: 48183512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51c82c38a995fd9e847057fedbbce1422085332b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832944"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-qoe-tables-in-lync-server-2013"></a>Lync Server 2013 の QoE テーブルの一覧

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-02_

データベーススキーマは、次の表で構成されています。

**サポートテーブル**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>テーブル</strong></th>
<th><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-appsharingmetricsthreshold-table.md">Lync Server 2013 の AppSharingMetricsThreshold テーブル</a></p></td>
<td><p>アプリケーションの共有で使用されるエクスペリエンスメトリックの品質と受け入れ可能な値を保存します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 の CodecDescription テーブル</a></p></td>
<td><p>一意のコーデック識別子を対応するコーデックにマップします。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a></p></td>
<td><p>環境の品質データベースの別の場所で使用されている一意の IP アドレス識別子に IP アドレスをマッピングします。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 の NetworkConnectionDetail テーブル</a></p></td>
<td><p>ネットワーク接続の種類を、エクスペリエンスデータベースの他の場所で使用されていたネットワーク接続識別子にマップします。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-purgesettings-table-qoe.md">Lync Server 2013 の PurgeSettings テーブル (QoE)</a></p></td>
<td><p>古い品質エクスペリエンスレコードが QoE データベースから自動的に削除されるかどうかを指定する情報を格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-traceroute-table.md">Lync Server 2013 の TraceRoute テーブル</a></p></td>
<td><p>通話のルーティング情報を保存します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 の UserAgentDef テーブル (QoE)</a></p></td>
<td><p>ユーザーエージェント識別子をエージェントのわかりやすい名前にマップします。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videometricsthreshold-table.md">Lync Server 2013 の VideoMetricsThreshold テーブル</a></p></td>
<td><p>ビデオ通話で使用されるエクスペリエンスメトリックの品質を実現するのに最適な値を保存します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a></p></td>
<td><p>オーディオとビデオのセッションで使用されるセッション開始プロトコル (SIP) ユーザーエージェント (UA) 文字列と UA の種類が保存されます。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-user-table.md">Lync Server 2013 の User テーブル</a></p></td>
<td><p>オーディオとビデオのセッションで使用されるユーザー、会議、および電話の Uri を格納します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-endpoint-table.md">Lync Server 2013 の Endpoint テーブル</a></p></td>
<td><p>オーディオとビデオのセッションに参加しているエンドポイントの FQDN コンピューター名を格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-pool-table.md">Lync Server 2013 の Pool テーブル</a></p></td>
<td><p>メトリックデータが属するプールの名前が格納されます。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-device-table.md">Lync Server 2013 の Device テーブル</a></p></td>
<td><p>オーディオ/ビデオ通話で使用されるキャプチャデバイスとレンダリングデバイスを保存します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 の DeviceDriver テーブル</a></p></td>
<td><p>オーディオ/ビデオ通話で使用されるキャプチャデバイスとレンダリングデバイスのドライバーを保存します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conference-table.md">Lync Server 2013 の Conference テーブル</a></p></td>
<td><p>会議のシナリオの会議の Uri、または他のシナリオのために、電話会議の Uri を格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013 の SessionCorrelation テーブル</a></p></td>
<td><p>PSTN 通話の CorrelationID を保存します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 の PayloadDescription テーブル</a></p></td>
<td><p>音声/ビデオ通話で使用されるコーデックを保存します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-appliedbandwidthsource-table.md">Lync Server 2013 の AppliedBandwidthSource テーブル</a></p></td>
<td><p>音声/ビデオ通話で使用される帯域幅のソースを保存します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-macaddress-table.md">Lync Server 2013 の MacAddress テーブル</a></p></td>
<td><p>オーディオとビデオのセッションに参加しているエンドポイントの MAC アドレスが格納されます。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-dialog-table.md">Lync Server 2013 の Dialog テーブル</a></p></td>
<td><p>オーディオセッションとビデオセッションのダイアログ ID を保存します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-region-table.md">Lync Server 2013 の Region テーブル</a></p></td>
<td><p>NCS 設定で定義されたネットワーク領域を格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-usersite-table.md">Lync Server 2013 の UserSite テーブル</a></p></td>
<td><p>NCS 設定で定義されたネットワークサイトを保存します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-subnet-table.md">Lync Server 2013 の Subnet テーブル</a></p></td>
<td><p>NCS 設定で定義されているサブネットを格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-monitoredregionlink-table.md">Lync Server 2013 の MonitoredRegionLink テーブル</a></p></td>
<td><p>NCS 設定で定義されている地域リンクを格納します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="monitoredusersitelink-table.md">MonitoredUserSiteLink テーブル</a></p></td>
<td><p>NCS 設定で定義されたネットワークサイトリンクを格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-endpointsubnet-table.md">Lync Server 2013 の EndpointSubnet テーブル</a></p></td>
<td><p>オーディオおよびビデオセッションに参加しているエンドポイントのサブネットを格納します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-server-table.md">Lync Server 2013 のサーバー テーブル</a></p></td>
<td><p>メディアが移動するサーバーの FQDN または IP アドレスが格納されます。</p></td>
</tr>
</tbody>
</table>


**指標データのテーブル**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>テーブル</strong></th>
<th><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-appsharingstream-table.md">Lync Server 2013 の AppSharingStream テーブル</a></p></td>
<td><p>アプリケーション共有に使用されるネットワークストリームのエクスペリエンスメトリックの品質を保存します。 アプリケーション共有に使用されるネットワークストリームのエクスペリエンスのメトリックの評価。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-session-table.md">Lync Server 2013 の Session テーブル</a></p></td>
<td><p>オーディオまたはオーディオ/ビデオセッションに関する全体的な情報を保存します。 セッションは、2つのエンドポイント間のオーディオまたはビデオ SIP ダイアログとして定義されます。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a></p></td>
<td><p>セッション内の各メディアラインに関する情報を格納します。 メディアラインは、1つ以上のオーディオストリームとビデオストリームのコレクションです。 通常、1つのメディアラインには、オーディオまたはビデオの2つのストリームがあります。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-audiostream-table.md">Lync Server 2013 の AudioStream テーブル</a></p></td>
<td><p>メディアラインの各オーディオストリームのオーディオメディア品質指標を保存します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-audiosignal-table.md">Lync Server 2013 の AudioSignal テーブル</a></p></td>
<td><p>メディアラインにオーディオメディアの品質指標を保存します。 これには、アコースティックエコーキャンセル (AEC) と自動ゲイン制御 (AGC) メトリックが含まれます。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videostream-table.md">Lync Server 2013 の VideoStream テーブル</a></p></td>
<td><p>メディアラインの各オーディオストリームについて、ビデオメディアの品質指標を保存します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-audioclientevent-table.md">Lync Server 2013 の AudioClientEvent テーブル</a></p></td>
<td><p>クライアントイベントから収集されたオーディオメディア品質指標を格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videoclientevent-table.md">Lync Server 2013 の VideoClientEvent テーブル</a></p></td>
<td><p>クライアントイベントから収集されたビデオメディア品質指標を格納します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DiagnosticData テーブル</strong></p></td>
<td><p>内部でのみ使用する診断データを格納します。</p></td>
</tr>
</tbody>
</table>


**集計データのテーブル**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>テーブル</strong></th>
<th><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ServerSummary テーブル</strong></p></td>
<td><p>サーバーの概要データを保存します。これらのデータは、Quality of Experience (QoE) レポートのみに使用されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserSummary テーブル</strong></p></td>
<td><p>ユーザーの概要データが保存されます。これらのデータは QoE レポート専用に使用されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallTypeSummary テーブル</strong></p></td>
<td><p>このデータは、通話の種類の概要データを保存するために、QoE レポート専用に使用されます。</p></td>
</tr>
</tbody>
</table>


**監視サーバーによる内部使用のテーブル**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>テーブル</strong></th>
<th><strong>説明</strong></th>
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
<td><p><strong>フロントエンドテーブル</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="even">
<td><p><strong>タスクテーブル</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="odd">
<td><p><strong>概要 tabltabl</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="even">
<td><p><strong>DbErrorMessage</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MetricsThreshold</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="even">
<td><p><strong>DaylightSavingYears</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="odd">
<td><p><strong>TimeZoneConfiguration</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="even">
<td><p><strong>タイム</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallSummary の表</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceCallSumary のテーブル</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="odd">
<td><p><strong>テナントテーブル</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoCallSummaryTable</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ascall概要テーブル</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

