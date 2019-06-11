---
title: 'Lync Server 2013: MediaLine テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: MediaLine table
ms:assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425920(v=OCS.15)
ms:contentKeyID: 48183956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4828f67614115eb4d6f46ab0a0a7c315e02d1924
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827439"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-table-in-lync-server-2013"></a>Lync Server 2013 の MediaLine テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-02-21_

各レコードは1つのメディアラインを表します。 (1 つのオーディオセッションには通常、1つのオーディオメディアラインが含まれています。 1つのオーディオとビデオ (A/V) セッションには通常、1つのオーディオメディアラインと1つのビデオメディアラインが含まれていますが、会議デバイスが使用されている場合や、[ギャラリー] ビューを使用している場合は、2つのビデオメディア線が表示されることがあります。


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
<td><p>Primary</p></td>
<td><p><a href="lync-server-2013-session-table.md">Lync Server 2013 のセッションテーブル</a>から参照されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p><a href="lync-server-2013-session-table.md">Lync Server 2013 のセッションテーブル</a>から参照されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p>0はメインオーディオ、1はメインビデオ、2はパノラマビデオ、3はアプリケーション/デスクトップ共有です。 このラベルは、1つのセッション内で一意である必要があります。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConnectivityIce</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>この列は存在しますが、Microsoft Lync Server 2013 では使用されません。 メディアラインに使用される接続に関する情報は、CallerConnectivityICE 列と CalleeConnectivityICE 列に記録されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerIceWarningFlags</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>「Bits フラグ」で説明されている対話型接続確立 (ICE) プロセスに関する情報。 詳細については、「ダウンロード可能な<em>エクスペリエンス監視サーバープロトコルの仕様</em>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeIceWarningFlags</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>CallerIceWarningFlags と同じですが、呼び出し先側でも同じです。 詳細については、「ダウンロード可能な<em>エクスペリエンス監視サーバープロトコルの仕様</em>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>セキュリティ</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>使用されているセキュリティプロファイル。 0は NONE、1は SRTP、2は V1 です。</p></td>
</tr>
<tr class="even">
<td><p><strong>Transport</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>0は UDP、1は TCP です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>発信者の IP アドレス。 詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>発信者によって使用されるポート。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerSubnet</strong></p></td>
<td><p>int</p></td>
<td><p> 外部</p></td>
<td><p>発信者のサブネット。 詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerInside</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>1: 発信者がエンタープライズネットワーク内にあることを示します。0は、呼び出し元がネットワークの外部にあることを意味します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerMacAddress</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>発信者の mac アドレス。 <a href="lync-server-2013-macaddress-table.md">Lync Server 2013 の MacAddress テーブル</a>から参照されています。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerRelayIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>発信者が使用した Lync Server A/V Edge サービスの IP アドレス。 詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRelayPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>発信者によって、A/V Edge サービスで使用されるポート。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerCaptureDev</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>発信者によって使用されるデバイスをキャプチャします。 <a href="lync-server-2013-device-table.md">Lync Server 2013 のデバイステーブル</a>から参照されている。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRenderDev</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>発信者によって使われるレンダリングデバイス。 <a href="lync-server-2013-device-table.md">Lync Server 2013 のデバイステーブル</a>から参照されている。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerCaptureDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>発信者のキャプチャデバイスのドライバー。 <a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 の Devicedriver テーブル</a>から参照されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRenderDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>発信者のレンダリングデバイスのドライバー。 <a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 の devicedriver テーブル</a>から参照されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerNetworkConnectionType</strong></p></td>
<td><p>tinyint</p></td>
<td><p>外部</p></td>
<td><p>発信者がネットワークに接続した方法を示します。 値は、 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 の Networkconnectiondetail テーブル</a>から取得されます。 一般的な値は、有線接続の場合は0、WiFi 接続の場合は0です。イーサネット接続の場合は3。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerBssid</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>ワイヤレスが使用されている場合は、発信者の BSSID。 <a href="lync-server-2013-macaddress-table.md">Lync Server 2013 の MacAddress テーブル</a>から参照されています。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerVPN</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>発信者のリンク。 1は仮想プライベートネットワーク (VPN)、0は非 VPN です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerLinkSpeed</strong></p></td>
<td><p>10進数 (18, 0)</p></td>
<td></td>
<td><p>発信者のエンドポイントのネットワークリンク速度 (bps)。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話受信者の IP アドレス。 詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleePort</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>通話レシーバーで使用されているポート。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeSubnet</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>呼び出し先のサブネット。 詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeInside</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>1: 通話受信者が企業ネットワーク内にあることを意味する0は、通話レシーバーがネットワークの外側にあることを意味します。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeMacAddress</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>呼び出し先 Mac アドレス。 <a href="lync-server-2013-macaddress-table.md">Lync Server 2013 の MacAddress テーブル</a>から参照されている。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeRelayIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話レシーバーによって使用される A/V エッジサービスの IP アドレス。 詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRelayPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>通話レシーバーによって、A/V Edge サービスで使用されるポート。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Calleecapdev</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話レシーバーによって使用されるデバイスをキャプチャします。 <a href="lync-server-2013-device-table.md">Lync Server 2013 のデバイステーブル</a>から参照されている。</p></td>
</tr>
<tr class="even">
<td><p><strong>Calle・ Enderdev</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話レシーバーによって使用されるレンダリングデバイス。 <a href="lync-server-2013-device-table.md">Lync Server 2013 のデバイステーブル</a>から参照されている。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Calleecapdevdriver</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話レシーバーのキャプチャデバイスのドライバー。 <a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 の Devicedriver テーブル</a>から参照されています。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRenderDevDriver</strong></p></td>
<td><p>varchar (256)</p></td>
<td><p>外部</p></td>
<td><p>通話レシーバーのレンダリングデバイスのドライバー。 <a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 の Devicedriver テーブル</a>から参照されています。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeNetworkConnectionType</strong></p></td>
<td><p>tinyint</p></td>
<td><p>外部</p></td>
<td><p>呼び出し先がネットワークに接続された方法を示します。 値は、 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 の Networkconnectiondetail テーブル</a>から取得されます。 一般的な値は、有線接続の場合は0、WiFi 接続の場合は0です。イーサネット接続の場合は3。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeBssid</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>ワイヤレスが使用されている場合は、呼び出し先の BSSID。 <a href="lync-server-2013-macaddress-table.md">Lync Server 2013 の MacAddress テーブル</a>から参照されています。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeVPN</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>通話レシーバーのリンク。1は仮想プライベートネットワーク (VPN)、0は非 VPN です。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeLinkSpeed</strong></p></td>
<td><p>10進数 (18, 0)</p></td>
<td><p> </p></td>
<td><p>通話受信側エンドポイントのネットワークリンク速度 (bps)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConversationalMOS</strong></p></td>
<td><p>10進数 (3, 2)</p></td>
<td><p> </p></td>
<td><p>オーディオセッションの会話 MOS を Narrowband します (両方のオーディオストリームに基づく)。</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthLimit</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>これは、さまざまなポリシー設定 (TURN、API、SDP、ポリシーサーバーなど) が指定された send side stream に適用される実際の帯域幅です。 これは、帯域幅の推定値に基づいて低帯域幅を使用できるため、有効帯域幅と混同しないようにする必要があります。 これは基本的に最大帯域幅であり、送信ストリームは、帯域幅の推定値によって課された制限を受けません。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppliedBandwidthSourceKey</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>これは、適用される帯域幅の上限のソースです。 帯域幅の制限の対象となる場所について説明します ("Policy Server"、"TURN Server"、"モダリティ" など)。 <a href="lync-server-2013-appliedbandwidthsource-table.md">Lync Server 2013 の AppliedBandwidthSource テーブル</a>から参照されている。</p></td>
</tr>
<tr class="even">
<td><p><strong>[発信者]</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>呼び出し元からのメトリックが受信されたかどうかを示します。1は yes で、null 値は no です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[呼び出し先]</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>通話レシーバーからのメトリックが受信されたかどうかを示します。1は yes で、null 値は no です。</p></td>
</tr>
<tr class="even">
<td><p><strong>MidCallReport</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>レポートがセッションの一部であるか、セッション全体であるかを示します。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClassifiedPoorCall</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>通話が低品質通話 (1) または良好コール (0) として分類されているかどうかを示します。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerConnectivityICE</strong></p></td>
<td><p>tinyInt</p></td>
<td></td>
<td><p>発信者が ICE プロトコル (インターネット接続の確立) を使ってネットワークに接続しているかどうかを示します。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeConnectivityICE</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>発信者が ICE プロトコル (インターネット接続の確立) を使ってネットワークに接続しているかどうかを示します。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerReflexiveLocalIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話を発信したユーザーの再帰 IP アドレス。 NAT (ネットワークアドレス変換) を使用している組織では、再帰 IP アドレスはプロキシサーバーの IP アドレスです。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerWiFiDriverDevicesDesc</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話を発信したユーザーによって採用された WiFi ドライバーのデバイスの説明。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerWiFiDriverVersion</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話を発信したユーザーによって採用された WiFi ドライバーのバージョン番号。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleReflexiveLocalIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話を受信したユーザーの再帰 IP アドレス。 NAT (ネットワークアドレス変換) を使用している組織では、再帰 IP アドレスはプロキシサーバーの IP アドレスです。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeWiFiDriverDevicesDesc</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話を受信したユーザーによって採用された WiFi ドライバーのデバイスの説明。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeWiFiDriverVersion</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話を受信したユーザーが使用する WiFi ドライバーのバージョン番号。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

