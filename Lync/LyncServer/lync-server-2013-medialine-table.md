---
title: 'Lync Server 2013: MediaLine テーブル'
TOCTitle: MediaLine テーブル
ms:assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg425920(v=OCS.15)
ms:contentKeyID: 48271878
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の MediaLine テーブル

 

_**トピックの最終更新日:** 2015-03-09_

1 つのレコードが 1 つのメディア ラインを表します (通常、1 つの音声セッションに 1 つの音声メディア ラインが含まれます。また、通常、1 つの音声ビデオ (A/V) セッションに 1 つの音声メディア ラインと 1 つのビデオ メディア ラインが含まれますが、会議デバイスまたはギャラリー ビューが使用される場合は、セッションに 2 つのビデオ メディア ラインが含まれることがあります)。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>列</strong></th>
<th><strong>データ型</strong></th>
<th><strong>キー/インデックス</strong></th>
<th><strong>詳細</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主/プライマリ</p></td>
<td><p><a href="lync-server-2013-session-table.md">Lync Server 2013 の Session テーブル</a> から参照されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p><a href="lync-server-2013-session-table.md">Lync Server 2013 の Session テーブル</a> から参照されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>主/プライマリ</p></td>
<td><p>0 はメイン音声、1 はメイン ビデオ、2 はパノラマ ビデオ、3 はアプリケーション共有/デスクトップ共有です。このラベルは、単一のセッションで一意である必要があります。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConnectivityIce</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>この列は存在しますが、Microsoft Lync Server 2013 では使用されていません。メディア ラインで使用される接続に関する情報は CallerConnectivityICE 列および CalleeConnectivityICE 列で取得します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerIceWarningFlags</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>このビット フラグに記述される Interactive Connectivity Establishment (ICE) プロセスに関する情報。詳細については、「サーバー プロトコル仕様の監視のエクスペリエンスの品質 (英語)」を参照してください。このドキュメントはダウンロードして入手できます。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeIceWarningFlags</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>CallerIceWarningFlags と同じですが、呼び出し先に関するものです。詳細については、「サーバー プロトコル仕様の監視のエクスペリエンスの品質 (英語)」を参照してください。このドキュメントはダウンロードして入手できます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Security</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>使用するセキュリティ プロファイル。0 は NONE、1 は SRTP、2 は V1 です。</p></td>
</tr>
<tr class="even">
<td><p><strong>Transport</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>0 は UDP、1 は TCP です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>発信者の IP アドレス。詳細については、「<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 での IPAddress テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>発信者が使用するポート。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerSubnet</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>発信者のサブネット。詳細については、「<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 での IPAddress テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerInside</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>1 は、発信者がエンタープライズ ネットワーク内に存在することを示し、0 は、発信者がネットワーク外に存在することを示します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerMacAddress</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>発信者の MAC アドレス。<a href="lync-server-2013-macaddress-table.md">Lync Server 2013 の MacAddress テーブル</a>から参照されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerRelayIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>発信者が使用する Lync Server 音声ビデオ エッジ サービスの IP アドレス。詳細については、「<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 での IPAddress テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRelayPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>発信者が使用する音声ビデオ エッジ サービスのポート。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerCaptureDev</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>発信者が使用するキャプチャ デバイス。<a href="lync-server-2013-device-table.md">Lync Server 2013 の Device テーブル</a> から参照されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRenderDev</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>発信者が使用するレンダー デバイス。<a href="lync-server-2013-device-table.md">Lync Server 2013 の Device テーブル</a> から参照されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerCaptureDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>発信者のキャプチャ デバイスのドライバー。<a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 の DeviceDriver テーブル</a> から参照されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRenderDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>発信者のレンダー デバイスのドライバー。<a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 の DeviceDriver テーブル</a> から参照されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerNetworkConnectionType</strong></p></td>
<td><p>tinyint</p></td>
<td><p>外部</p></td>
<td><p>発信者がどのようにネットワークに接続されているかを示します。値は <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 での NetworkConnectionDetail テーブル</a> から取得されます。通常の値の 0 は有線接続、1 は WiFi 接続、3 はイーサネット接続です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerBssid</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>ワイヤレスが使用されている場合、発信者の BSSID。<a href="lync-server-2013-macaddress-table.md">Lync Server 2013 の MacAddress テーブル</a>から参照されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerVPN</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>発信者のリンク。1 は仮想プライベート ネットワーク (VPN)、0 は非 VPN です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerLinkSpeed</strong></p></td>
<td><p>decimal(18.0)</p></td>
<td><p></p></td>
<td><p>発信者のエンドポイントのネットワーク リンクの速度 (単位 bps)。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話受信者の IP アドレス。詳細については、「<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 での IPAddress テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleePort</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>通話受信者が使用するポート。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeSubnet</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>呼び出し先のサブネット。詳細については、「<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 での IPAddress テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeInside</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>1 は、通話受信者がエンタープライズ ネットワーク内に存在することを示し、0 は、通話受信者がネットワーク外に存在することを示します。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeMacAddress</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>呼び出し先の MAC アドレス。<a href="lync-server-2013-macaddress-table.md">Lync Server 2013 の MacAddress テーブル</a>から参照されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeRelayIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話受信者が使用する音声ビデオ エッジ サービスの IP アドレス。詳細については、「<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 での IPAddress テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRelayPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>通話受信者が使用する音声ビデオ エッジ サービスのポート。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeCaptureDev</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話受信者が使用するキャプチャ デバイス。<a href="lync-server-2013-device-table.md">Lync Server 2013 の Device テーブル</a> から参照されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRenderDev</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話受信者が使用するレンダー デバイス。<a href="lync-server-2013-device-table.md">Lync Server 2013 の Device テーブル</a> から参照されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeCaptureDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話受信者のキャプチャ デバイスのドライバー。<a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 の DeviceDriver テーブル</a> から参照されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRenderDevDriver</strong></p></td>
<td><p>varchar(256)</p></td>
<td><p>外部</p></td>
<td><p>通話受信者のレンダー デバイスのドライバー。<a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 の DeviceDriver テーブル</a> から参照されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeNetworkConnectionType</strong></p></td>
<td><p>tinyint</p></td>
<td><p>外部</p></td>
<td><p>呼び出し先がどのようにネットワークに接続されているかを示します。値は <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 での NetworkConnectionDetail テーブル</a> から取得されます。通常の値の 0 は有線接続、1 は WiFi 接続、3 はイーサネット接続です。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeBssid</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>ワイヤレスが使用されている場合、呼び出し先の BSSID。<a href="lync-server-2013-macaddress-table.md">Lync Server 2013 の MacAddress テーブル</a>から参照されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeVPN</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>通話受信者のリンク。1 は仮想プライベート ネットワーク (VPN)、0 は非 VPN です。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeLinkSpeed</strong></p></td>
<td><p>decimal(18.0)</p></td>
<td><p> </p></td>
<td><p>通話受信者のエンドポイントのネットワーク リンクの速度 (単位 bps)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConversationalMOS</strong></p></td>
<td><p>decimal(3.2)</p></td>
<td><p> </p></td>
<td><p>音声セッションの Narrowband Conversational MOS (音声ストリームに基づく)。</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthLimit</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>これは、さまざまなポリシー設定 (TURN、API、SDP、ポリシー サーバーなど) が構成された特定の送信側ストリームに適用される実際の帯域幅です。この帯域幅を実効帯域幅と見なすことはできません。実効帯域幅は、帯域幅の評価に基づいて実際よりも低くなる可能性があります。これは基本的に、送信ストリームで利用できる最大帯域幅です (帯域幅の評価によって課せられる制限を除く)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppliedBandwidthSourceKey</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>これは、課せられる帯域幅の制限のソースです。帯域幅の制限のソースが記述されます (&quot;ポリシー サーバー&quot;、&quot;TURN サーバー&quot;、&quot;モダリティ&quot; など)。<a href="lync-server-2013-appliedbandwidthsource-table.md">Lync Server 2013 の AppliedBandwidthSource テーブル</a> から参照されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>Caller</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>発信者からの指標が受信されたかどうかを示します。1 は &quot;はい&quot;、null 値は &quot;いいえ&quot; です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Callee</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>通話受信者からの指標が受信されたかどうかを示します。1 は &quot;はい&quot;、null 値は &quot;いいえ&quot; です。</p></td>
</tr>
<tr class="even">
<td><p><strong>MidCallReport</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>レポートがセッションの一部を対象としているか、セッション全体を対象としているかを示します。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClassifiedPoorCall</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>呼び出しが低品質通話 (1) として分類されたか、良好な通話 (0) として分類されたかを示します。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerConnectivityICE</strong></p></td>
<td><p>tinyInt</p></td>
<td><p></p></td>
<td><p>発信者が ICE (Internet Connectivity Establishment) プロトコルを使用してネットワークに接続したかどうかを示します。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeConnectivityICE</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>発信者が ICE (Internet Connectivity Establishment) プロトコルを使用してネットワークに接続したかどうかを示します。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerReflexiveLocalIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話を発信したユーザーの再帰 IP アドレス。NAT (ネットワーク アドレス変換) を使用している組織では、再帰 IP アドレスはプロキシ サーバーの IP アドレスです。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerWiFiDriverDevicesDesc</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話を発信したユーザーによって使用されている WiFi ドライバーのデバイスの説明。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerWiFiDriverVersion</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話を発信したユーザーによって使用されている WiFi ドライバーのバージョン番号。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleReflexiveLocalIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話を受信したユーザーの再帰 IP アドレス。NAT (ネットワーク アドレス変換) を使用している組織では、再帰 IP アドレスはプロキシ サーバーの IP アドレスです。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeWiFiDriverDevicesDesc</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話を受信したユーザーによって使用されている WiFi ドライバーのデバイスの説明。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeWiFiDriverVersion</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話を受信したユーザーによって使用されている WiFi ドライバーのバージョン番号。</p>
<p>この列は、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
</tbody>
</table>

