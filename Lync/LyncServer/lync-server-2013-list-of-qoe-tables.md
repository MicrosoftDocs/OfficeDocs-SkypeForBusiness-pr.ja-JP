---
title: 'Lync Server 2013: QoE テーブルの一覧'
TOCTitle: QoE テーブルの一覧
ms:assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398236(v=OCS.15)
ms:contentKeyID: 48271382
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の QoE テーブルの一覧

 

_**トピックの最終更新日:** 2015-03-09_

データベース スキーマは、次のテーブルで構成されます。

**サポート テーブル**


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
<td><p><a href="lync-server-2013-appsharingmetricsthreshold-table.md">AppSharingMetricsThreshold テーブル</a></p></td>
<td><p>アプリケーション共有で使用される QoE 指標の最適値および許容値を格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-codecdescription-table.md">CodecDescription テーブル</a></p></td>
<td><p>一意のコーデック識別子を対応するコーデックにマッピングします。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 での IPAddress テーブル</a></p></td>
<td><p>IP アドレスを、QoE データベース内の他の場所で使用される一意の IP アドレス識別子にマッピングします。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 での NetworkConnectionDetail テーブル</a></p></td>
<td><p>ネットワーク接続の種類を、QoE データベース内の他の場所で使用されるネットワーク接続識別子にマッピングします。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-purgesettings-table-qoe.md">PurgeSettings テーブル (QoE)</a></p></td>
<td><p>古くなった QoE レコードが QoE データベースから自動的に削除されるかどうか (およびそのタイミング) を指定する情報を格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-traceroute-table.md">TraceRoute テーブル</a></p></td>
<td><p>通話のルーティング情報を格納します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef テーブル (QoE)</a></p></td>
<td><p>ユーザー エージェント識別子をエージェントを表す名前にマッピングします。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videometricsthreshold-table.md">VideoMetricsThreshold テーブル</a></p></td>
<td><p>ビデオ通話で使用される QoE 指標の最適値および許容値を格納します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a></p></td>
<td><p>音声およびビデオ セッションで使用されるセッション開始プロトコル (SIP) ユーザー エージェント (UA) 文字列および UA の種類を格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-user-table.md">Lync Server 2013 の User テーブル</a></p></td>
<td><p>音声およびビデオ セッションで使用されるユーザー、会議、電話の URI を格納します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-endpoint-table.md">Lync Server 2013 の Endpoint テーブル</a></p></td>
<td><p>音声およびビデオ セッションに参加しているエンドポイントの FQDN コンピューター名を格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-pool-table.md">Lync Server 2013 の Pool テーブル</a></p></td>
<td><p>指標データが属するプールの名前を格納します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-device-table.md">Lync Server 2013 の Device テーブル</a></p></td>
<td><p>音声ビデオ通話で使用されるキャプチャ デバイスおよびレンダー デバイスを格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 の DeviceDriver テーブル</a></p></td>
<td><p>音声ビデオ通話で使用されるキャプチャ デバイスおよびレンダー デバイスのドライバーを格納します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conference-table.md">Lync Server 2013 の Conference テーブル</a></p></td>
<td><p>会議シナリオの会議 URI または他のシナリオの DialogID を格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013 の SessionCorrelation テーブル</a></p></td>
<td><p>PSTN 通話の CorrelationID を格納します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 の PayloadDescription テーブル</a></p></td>
<td><p>音声ビデオ通話で使用されるコーデックを格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-appliedbandwidthsource-table.md">Lync Server 2013 の AppliedBandwidthSource テーブル</a></p></td>
<td><p>音声ビデオ通話で使用される帯域幅ソースを格納します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-macaddress-table.md">Lync Server 2013 の MacAddress テーブル</a></p></td>
<td><p>音声およびビデオ セッションに参加しているエンドポイントの MAC アドレスを格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-dialog-table.md">Lync Server 2013 の Dialog テーブル</a></p></td>
<td><p>音声およびビデオ セッションのダイアログ ID を格納します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-region-table.md">Lync Server 2013 の Region テーブル</a></p></td>
<td><p>NCS 設定で定義されているネットワーク地域を格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-usersite-table.md">Lync Server 2013 の UserSite テーブル</a></p></td>
<td><p>NCS 設定で定義されているネットワーク サイトを格納します。</p></td>
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
<td><p>NCS 設定で定義されているネットワーク サイト リンクを格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-endpointsubnet-table.md">Lync Server 2013 の EndpointSubnet テーブル</a></p></td>
<td><p>音声およびビデオ セッションに参加しているエンドポイントのサブネットを格納します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-server-table.md">Lync Server 2013 のサーバー テーブル</a></p></td>
<td><p>メディアが通過するサーバーの FQDN または IP アドレスを格納します。</p></td>
</tr>
</tbody>
</table>


**指標データ用テーブル**


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
<td><p><a href="lync-server-2013-appsharingstream-table.md">AppSharingStream テーブル</a></p></td>
<td><p>アプリケーション共有で使用されるネットワーク ストリームの QoE 指標を格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-session-table.md">Lync Server 2013 の Session テーブル</a></p></td>
<td><p>音声セッションまたは音声ビデオ セッションに関する全体的な情報を格納します。セッションとは、2 つのエンドポイント間の音声またはビデオでの SIP ダイアログと定義されます。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a></p></td>
<td><p>セッションでの各メディア ラインについての情報を格納します。メディア ラインとは、1 つ以上の音声およびビデオ ストリームのコレクションです。通常、1 つのメディア ラインには音声またはビデオの 2 つのストリームが含まれます。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-audiostream-table.md">Lync Server 2013 の AudioStream テーブル</a></p></td>
<td><p>メディア ラインに含まれる各音声ストリームの音声メディア品質指標を格納します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-audiosignal-table.md">Lync Server 2013 の AudioSignal テーブル</a></p></td>
<td><p>メディア ラインの音声メディア品質指標を格納します。これには、アコーステック エコー キャンセレーション (AEC) 指標および自動ゲイン制御 (AGC) 指標が含まれます。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videostream-table.md">Lync Server 2013 の VideoStream テーブル</a></p></td>
<td><p>メディア ラインに含まれる各音声ストリームのビデオ メディア品質指標を格納します。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-audioclientevent-table.md">Lync Server 2013 の AudioClientEvent テーブル</a></p></td>
<td><p>クライアント イベントから収集された音声メディア品質指標を格納します。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videoclientevent-table.md">Lync Server 2013 の VideoClientEvent テーブル</a></p></td>
<td><p>クライアント イベントから収集されたビデオ メディア品質指標を格納します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DiagnosticData テーブル</strong></p></td>
<td><p>内部使用専用の診断データを格納します。</p></td>
</tr>
</tbody>
</table>


**概要データ用テーブル**


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
<td><p>サーバーの概要データを格納します。このデータは、QoE (Quality of Experience) レポートのみに使用されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserSummary テーブル</strong></p></td>
<td><p>ユーザーの概要データを格納します。このデータは、QoE レポートのみに使用されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallTypeSummary テーブル</strong></p></td>
<td><p>通話種類の概要データを格納します。このデータは、QoE レポートのみに使用されます。</p></td>
</tr>
</tbody>
</table>


**監視サーバーの内部用テーブル**


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
<td><p><strong>FrontEnd テーブル</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="even">
<td><p><strong>Task テーブル</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SummaryTableConfiguration</strong></p></td>
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
<td><p><strong>TimeZones</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallSummary テーブル</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceCallSumary テーブル</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tenant テーブル</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoCallSummary テーブル</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ASCallSummary テーブル</strong></p></td>
<td><p>内部使用のみ。</p></td>
</tr>
</tbody>
</table>

