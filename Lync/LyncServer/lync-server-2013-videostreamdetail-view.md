---
title: VideoStreamDetail ビュー
TOCTitle: VideoStreamDetail ビュー
ms:assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ721928(v=OCS.15)
ms:contentKeyID: 49887202
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# VideoStreamDetail ビュー

 

_**トピックの最終更新日:** 2015-03-09_

VideoStreamDetail ビューには、データベース内の各ビデオ ストリームに関する情報が格納されています。このビューは、Microsoft Lync Server 2013 で導入されました。


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
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SessionTime</p></td>
<td><p>datetime</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a> から参照されます。</p></td>
</tr>
<tr class="even">
<td><p>SessionSeq</p></td>
<td><p>int</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a> から参照されます。</p></td>
</tr>
<tr class="odd">
<td><p>MediaLineLabel</p></td>
<td><p>tinyint</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a> から参照されます。</p></td>
</tr>
<tr class="even">
<td><p>StreamId</p></td>
<td><p>int</p></td>
<td><p>メディア ライン内の一意の ID。</p></td>
</tr>
<tr class="odd">
<td><p>StartTime</p></td>
<td><p>datetime</p></td>
<td><p>セッションの開始時刻。</p></td>
</tr>
<tr class="even">
<td><p>EndTime</p></td>
<td><p>datetime</p></td>
<td><p>セッションの終了時刻。</p></td>
</tr>
<tr class="odd">
<td><p>CallPriority</p></td>
<td><p>int</p></td>
<td><p>通話の優先順位。</p></td>
</tr>
<tr class="even">
<td><p>CallerPool</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>発信者プールの FQDN。</p></td>
</tr>
<tr class="odd">
<td><p>CalleePool</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>呼び出し先プールの FQDN。</p></td>
</tr>
<tr class="even">
<td><p>Caller</p></td>
<td><p>nvarchar(450)</p></td>
<td><p>発信者の URI。</p></td>
</tr>
<tr class="odd">
<td><p>Callee</p></td>
<td><p>nvarchar(450)</p></td>
<td><p>呼び出し先の URI。</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>発信者のユーザー エージェント文字列。</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>発信者のユーザー エージェントの種類。詳細については、「<a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgentCategory</p></td>
<td><p>nvarchar(64)</p></td>
<td><p>発信者のユーザー エージェントのカテゴリ。詳細については、「<a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef テーブル (QoE)</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>呼び出し先のユーザー エージェント文字列。</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>呼び出し先のユーザー エージェントの種類。詳細については、「<a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgentCategory</p></td>
<td><p>nvarchar(64)</p></td>
<td><p>呼び出し先のユーザー エージェントのカテゴリ。詳細については、「<a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef テーブル (QoE)</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>CallerEndpoint</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>発信者のエンドポイント名。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeEndpoint</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>呼び出し先のエンドポイント名。</p></td>
</tr>
<tr class="even">
<td><p>CallerOS</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>発信者のエンドポイントのオペレーティング システム (OS)。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeOS</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>呼び出し先のエンドポイントのオペレーティング システム (OS)。</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUName</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>発信者のエンドポイントの CPU 名。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUName</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>呼び出し先のエンドポイントの CPU 名。</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUNumberOfCores</p></td>
<td><p>smallint</p></td>
<td><p>発信者のエンドポイントの CPU コアの数。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUNumberOfCores</p></td>
<td><p>smallint</p></td>
<td><p>呼び出し先のエンドポイントの CPU コアの数。</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUProcessorSpeed</p></td>
<td><p>int</p></td>
<td><p>発信者のエンドポイントの CPU プロセッサ速度。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUProcessorSpeed</p></td>
<td><p>int</p></td>
<td><p>呼び出し先のエンドポイントの CPU プロセッサ速度。</p></td>
</tr>
<tr class="even">
<td><p>CallerVirtualizationFlag</p></td>
<td><p>tinyint</p></td>
<td><p>発信者のシステムが仮想環境で実行されているかどうかを示します。詳細については、「<a href="lync-server-2013-endpoint-table.md">Lync Server 2013 の Endpoint テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVirtualizationFlag</p></td>
<td><p>tinyint</p></td>
<td><p>呼び出し先のシステムが仮想環境で実行されているかどうかを示します。詳細については、「<a href="lync-server-2013-endpoint-table.md">Lync Server 2013 の Endpoint テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>ConnectivityIce</p></td>
<td><p>tinyint</p></td>
<td><p>メディア パスに関する情報 (直接、リレーなど)。詳細については、「<a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p>CallerIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>発信者のビット フラグに記述される Interactive Connectivity Establishment (ICE) プロセスに関する情報。詳細については、「Quality of Experience Monitoring Server Protocol Specification」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>呼び出し先のビット フラグに記述される Interactive Connectivity Establishment (ICE) プロセスに関する情報。詳細については、「Quality of Experience Monitoring Server Protocol Specification」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p>Transport</p></td>
<td><p>int</p></td>
<td><p>トランスポートの種類。0 は UDP、1 は TCP です。</p></td>
</tr>
<tr class="even">
<td><p>CallerIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>発信者の IP アドレス。IPv4 または IPv6 のアドレスです。</p></td>
</tr>
<tr class="odd">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>発信者が使用するポート。</p></td>
</tr>
<tr class="even">
<td><p>CallerInside</p></td>
<td><p>bit</p></td>
<td><p>発信者が組織ネットワーク内にいるかどうかを示します。1 は、発信者がエンタープライズ ネットワーク内に存在することを示し、0 は、発信者がネットワーク外に存在することを示します。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>呼び出し先の IP アドレス。IPv4 または IPv6 のアドレスです。</p></td>
</tr>
<tr class="even">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>呼び出し先が使用するポート。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeInside</p></td>
<td><p>bit</p></td>
<td><p>呼び出し先が組織ネットワーク内にいるかどうかを示します。1 は、呼び出し先がエンタープライズ ネットワーク内に存在することを示し、0 は、呼び出し先がネットワーク外に存在することを示します。</p></td>
</tr>
<tr class="even">
<td><p>CallerUserSite</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>発信者のサイトの名前。</p></td>
</tr>
<tr class="odd">
<td><p>CallerRegion</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>発信者のサイトの国/地域の名前。</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserSite</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>呼び出し先のサイトの名前。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRegion</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>呼び出し先のサイトの国/地域の名前。</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>発信者が使用する音声ビデオ エッジ サービスの IPアドレス。詳細については、「<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 での IPAddress テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p>CallerRelayPort</p></td>
<td><p>int</p></td>
<td><p>発信者が使用する音声ビデオ エッジ サービスのポート。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var(50)</p>
<p></p></td>
<td><p>呼び出し先が使用する音声ビデオ エッジ サービスの IPアドレス キー。詳細については、「<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 での IPAddress テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>呼び出し先が使用する音声ビデオ エッジ サービスのポート。</p></td>
</tr>
<tr class="even">
<td><p>CallerCaptureDev</p></td>
<td><p>varchar(256)</p></td>
<td><p>発信者のキャプチャ デバイス名。</p></td>
</tr>
<tr class="odd">
<td><p>CallerRenderDev</p></td>
<td><p>varchar(256)</p></td>
<td><p>発信者のレンダー デバイス名。</p></td>
</tr>
<tr class="even">
<td><p>CallerCaptureDevDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>発信者のキャプチャ デバイス ドライバー名。</p></td>
</tr>
<tr class="odd">
<td><p>CallerRenderDevDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>発信者のレンダー デバイス ドライバー名。</p></td>
</tr>
<tr class="even">
<td><p>CalleeCaptureDev</p></td>
<td><p>varchar(256)</p></td>
<td><p>呼び出し先のキャプチャ デバイス名。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRenderDev</p></td>
<td><p>varchar(256)</p></td>
<td><p>呼び出し先のレンダー デバイス名。</p></td>
</tr>
<tr class="even">
<td><p>CalleCaptureDevDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>呼び出し先のキャプチャ デバイス ドライバー名。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRenderDevDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>呼び出し先のレンダー デバイス ドライバー名。</p></td>
</tr>
<tr class="even">
<td><p>CallerNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>発信者のネットワーク接続の種類。0 は有線、1 はワイヤレスです。</p></td>
</tr>
<tr class="odd">
<td><p>CallerVPN</p></td>
<td><p>bit</p></td>
<td><p>発信者が仮想プライベート ネットワークで接続しているかどうかを示します。1 は仮想プライベート ネットワーク (VPN)、0 は非 VPN です。</p></td>
</tr>
<tr class="even">
<td><p>CallerLinkSpeed</p></td>
<td><p>decimal(18,)</p></td>
<td><p>発信者のエンドポイントのネットワーク リンクの速度 (単位 bps)。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>呼び出し先のネットワーク接続の種類。0 は有線、1 はワイヤレスです。</p></td>
</tr>
<tr class="even">
<td><p>CalleeVPN</p></td>
<td><p>bit</p></td>
<td><p>呼び出し先が仮想プライベート ネットワークで接続しているかどうかを示します。1 は仮想プライベート ネットワーク (VPN)、0 は非 VPN です。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeLinkSpeed</p></td>
<td><p>decimal(18,0)</p></td>
<td><p>呼び出し先のエンドポイントのネットワーク リンクの速度 (単位 bps)。</p></td>
</tr>
<tr class="even">
<td><p>ConversationalMOS</p></td>
<td><p>decimal(3,2)</p></td>
<td><p>音声セッションの Narrowband Conversational MOS (音声ストリームに基づく)。</p></td>
</tr>
<tr class="odd">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>さまざまなポリシー設定 (TURN、API、SDP、ポリシー サーバーなど) が構成された特定の送信側ストリームに適用される実際の帯域幅。この帯域幅を実効帯域幅と見なすことはできません。実効帯域幅は、帯域幅の評価に基づいて実際よりも低くなる可能性があります。これは基本的に、送信ストリームで利用できる最大帯域幅です (帯域幅の評価によって課せられる制限を除く)。</p></td>
</tr>
<tr class="even">
<td><p>JitterInterArrival</p></td>
<td><p>int</p></td>
<td><p>リアルタイム制御プロトコル (RTCP) 統計情報に基づく平均ネットワーク ジッター。</p></td>
</tr>
<tr class="odd">
<td><p>JitterInterArrivalMax</p></td>
<td><p>int</p></td>
<td><p>通話時の最大ネットワーク ジッター。</p></td>
</tr>
<tr class="even">
<td><p>RoundTrip</p></td>
<td><p>int</p></td>
<td><p>RTCP 統計情報に基づく往復時間。</p></td>
</tr>
<tr class="odd">
<td><p>RoundTripMax</p></td>
<td><p>int</p></td>
<td><p>音声ストリームの最大往復時間。</p></td>
</tr>
<tr class="even">
<td><p>PacketLossRate</p></td>
<td><p>decimal(5,4)</p></td>
<td><p>通話時の平均パケット損失率。</p></td>
</tr>
<tr class="odd">
<td><p>PacketLossRateMax</p></td>
<td><p>decimal(5,4)</p></td>
<td><p>通話時に観測された最大パケット損失。</p></td>
</tr>
<tr class="even">
<td><p>PacketUtilization</p></td>
<td><p>int</p></td>
<td><p>ビデオ ストリームのパケット数 (リアルタイム転送プロトコル、RTP)。</p></td>
</tr>
<tr class="odd">
<td><p>BandwidthEst</p></td>
<td><p>int</p></td>
<td><p>音声ストリームの帯域幅の推定。</p></td>
</tr>
<tr class="even">
<td><p>PayloadDescription</p></td>
<td><p>int</p></td>
<td><p>通話に使用されるオーディオ コーデック。<a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 の PayloadDescription テーブル</a> テーブルから参照されます。</p></td>
</tr>
<tr class="odd">
<td><p>VideoResolution</p></td>
<td><p>char(9)</p></td>
<td><p>幅×高さで示すビデオの解像度 (単位ピクセル)。文字列で報告されます。</p></td>
</tr>
<tr class="even">
<td><p>VideoBitRateAvg</p></td>
<td><p>int</p></td>
<td><p>ビデオ ストリームの平均ビット レート。</p></td>
</tr>
<tr class="odd">
<td><p>InboundVideoFrameRateAvg</p></td>
<td><p>decimal(9,4)</p></td>
<td><p>ビデオの受信フレーム レート。</p></td>
</tr>
<tr class="even">
<td><p>OutboundVideoFrameRateAvg</p></td>
<td><p>decimal(9,4)</p></td>
<td><p>ビデオの送信フレーム レート。</p></td>
</tr>
<tr class="odd">
<td><p>ViideoBitRateMax</p></td>
<td><p>int</p></td>
<td><p>ビデオ セッション時の最大ビデオ ビット レート。</p></td>
</tr>
<tr class="even">
<td><p>VideoPacketLossRate</p></td>
<td><p>decimal(9,4)</p></td>
<td><p>失われたビデオ パケット数の割合。</p></td>
</tr>
<tr class="odd">
<td><p>VideoFrameLossRate</p></td>
<td><p>decimal(9.4)</p></td>
<td><p>失われた合計ビデオ フレーム数の割合。</p></td>
</tr>
<tr class="even">
<td><p>VideoFEC</p></td>
<td><p>bit</p></td>
<td><p>不使用。</p></td>
</tr>
<tr class="odd">
<td><p>VideoAllocateBWAvg</p></td>
<td><p>int</p></td>
<td><p>ビデオに割り当てられた帯域幅の平均。</p></td>
</tr>
<tr class="even">
<td><p>VideoLocalFrameLossPercentageAvg</p></td>
<td><p>decimal(9.4)</p></td>
<td><p>失われた合計ビデオ フレーム数の割合。</p></td>
</tr>
<tr class="odd">
<td><p>SenderIsCallerPAI</p></td>
<td><p>bit</p></td>
<td><p>P-Asserted Identity 情報のストリームの方向。1 は、ストリームの方向が発信者から呼び出し先へ向かうことを意味します。0 は、ストリームの方向が呼び出し先から発信者へ向かうことを意味します。</p></td>
</tr>
</tbody>
</table>

