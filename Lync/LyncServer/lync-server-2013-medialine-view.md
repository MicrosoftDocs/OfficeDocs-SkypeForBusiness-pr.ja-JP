---
title: 'Lync Server 2013: MediaLine ビュー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaLine view
ms:assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687972(v=OCS.15)
ms:contentKeyID: 49733560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21fa89b5afe53937ee515dac45053dbd84ae12ef
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217599"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="medialine-view-in-lync-server-2013"></a>Lync Server 2013 の MediaLine ビュー

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-03_

メディア ライン ビューは、各メディア ラインに関する情報をデータベースに格納します。 通常、1 つの音声セッションに 1 つの音声メディア ラインが含まれます。 また、通常は 1 つの音声ビデオ (A/V) セッションに 1 つの音声メディア ラインと 1 つのビデオ メディア ラインが含まれますが、会議デバイスまたはギャラリー ビューが使用される場合は、セッションに 2 つのビデオ メディア ラインが含まれることがあります。 このビューは Microsoft Lync Server 2013 で導入されました。


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
<td><p>ConferenceDateTime</p></td>
<td><p>日付型</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</p></td>
</tr>
<tr class="even">
<td><p>SessionSeq</p></td>
<td><p>int</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</p></td>
</tr>
<tr class="odd">
<td><p>MediaLineLabel</p></td>
<td><p>tinyint</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</p></td>
</tr>
<tr class="even">
<td><p>CallerIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>発信者のビット フラグに記述される Interactive Connectivity Establishment (ICE) プロセスに関する情報。詳細については、「Quality of Experience Monitoring Server Protocol Specification」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>受信者についてビット フラグで記述される Interactive Connectivity Establishment (ICE) プロセスに関する情報。詳細については、「Quality of Experience Monitoring Server Protocol Specification」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>セキュリティ</p></td>
<td><p>tinyint</p></td>
<td><p>使用するセキュリティ プロファイル。0 は NONE、1 は SRTP、2 は V1 です。</p></td>
</tr>
<tr class="odd">
<td><p>Transport</p></td>
<td><p>tinyint</p></td>
<td><p>トランスポートの種類。0 は UDP、1 は TCP です。</p></td>
</tr>
<tr class="even">
<td><p>CallerIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>発信者の IP アドレス。IPv4 アドレスまたは IPv6 アドレスです。</p></td>
</tr>
<tr class="odd">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>発信者が使用するポート。</p></td>
</tr>
<tr class="even">
<td><p>CallerInside</p></td>
<td><p>若干</p></td>
<td><p>発信者が組織のネットワーク内に存在するかどうかを示します。1 は、発信者がエンタープライズ ネットワーク内に存在することを示します。0 は、発信者がネットワーク外に存在することを示します。</p></td>
</tr>
<tr class="odd">
<td><p>CallerMacAddress</p></td>
<td><p>varchar (256)</p></td>
<td><p>発信者が使用するネットワーク インターフェイスの MAC アドレス。</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>発信者が使用する音声ビデオ エッジ サービスの IPアドレス。 詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>発信者が使用する音声ビデオ エッジ サービスのポート。</p></td>
</tr>
<tr class="even">
<td><p>CallerReflexiveIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>音声ビデオ エッジ サービスからレポートされる発信者の IP アドレス。 クライアントが NAT の背後にある場合など、このアドレスが CallerIPAddr と異なることがあります。</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>発信者のキャプチャ デバイス名。</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>発信者のレンダー デバイス名。</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>発信者のキャプチャ デバイス ドライバー名。</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>発信者のレンダー デバイスのドライバー名。</p></td>
</tr>
<tr class="odd">
<td><p>CallerWifiDriverDeviceDesc</p></td>
<td><p>varchar (256</p></td>
<td><p>発信者の WiFi ドライバーの説明。</p></td>
</tr>
<tr class="even">
<td><p>CallerWifiDriverVersion</p></td>
<td><p>varchar (256)</p></td>
<td><p>発信者の WiFi ドライバーのバージョン。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionDetail</p></td>
<td><p>varchar (256)</p></td>
<td><p>発信者のネットワーク接続の詳細。 詳細については、「 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 の Networkconnectiondetail テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>CallerBssid</p></td>
<td><p>varchar (256)</p></td>
<td><p>発信者の WiFi 接続で使用する基本サービス セット識別子。</p></td>
</tr>
<tr class="odd">
<td><p>CallerVPN</p></td>
<td><p>若干</p></td>
<td><p>発信者が仮想プライベート ネットワーク経由で接続しているかどうかを示します。1 は仮想プライベート ネットワーク (VPN)、0 は非 VPN です。</p></td>
</tr>
<tr class="even">
<td><p>CalleeIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>通話受信者の IP アドレス。 IPv4 アドレスまたは IPv6 アドレスです。</p></td>
</tr>
<tr class="odd">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>呼び出し先が使用するポート。</p></td>
</tr>
<tr class="even">
<td><p>CalleeInside</p></td>
<td><p>若干</p></td>
<td><p>通話受信者がエンタープライズ ネットワーク内に存在するかどうかを示します。1 は、通話受信者がエンタープライズ ネットワーク内に存在することを示し、0 は、通話受信者がネットワーク外に存在することを示します。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeMacAddress</p></td>
<td><p>varchar (256)</p></td>
<td><p>通話受信者が使用するネットワーク インターフェイスの MAC アドレス。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>通話受信者が使用する音声ビデオ エッジ サービスの IP アドレス。 詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>通話受信者が使用する音声ビデオ エッジ サービスのポート。</p></td>
</tr>
<tr class="even">
<td><p>CalleeReflexiveIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>音声ビデオ エッジ サービスからレポートされる通話受信者の IP アドレス。 クライアントが NAT の背後にある場合など、このアドレスが CalleeIPAddr と異なることがあります。</p></td>
</tr>
<tr class="odd">
<td><p>Calleecapのアーキテクチャ開発</p></td>
<td><p>var (50)</p></td>
<td><p>通話受信者のキャプチャ デバイス名。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>呼び出し先のレンダー デバイス名。</p></td>
</tr>
<tr class="odd">
<td><p>Calleecapアーキテクチャ Devdriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>呼び出し先のキャプチャ デバイス ドライバー名。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>通話受信者のレンダー デバイスのドライバー名。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeWifiDriverDeviceDesc</p></td>
<td><p>varchar (256)</p></td>
<td><p>通話受信者の WiFi ドライバーの説明。</p></td>
</tr>
<tr class="even">
<td><p>CalleeWifiDriverVersion</p></td>
<td><p>varchar (256</p></td>
<td><p>通話受信者の WiFi ドライバーのバージョン。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionDetail</p></td>
<td><p>varchar (256)</p></td>
<td><p>通話受信者のネットワーク接続の詳細。 詳細については、「 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 の Networkconnectiondetail テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>CalleeBssid</p></td>
<td><p>varchar (256)</p></td>
<td><p>通話受信者の WiFi 接続で使用する基本サービス セット識別子。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVPN</p></td>
<td><p>若干</p></td>
<td><p>通話受信者が仮想プライベート ネットワーク経由で接続しているかどうかを示します。1 は仮想プライベート ネットワーク (VPN)、0 は非 VPN です。</p></td>
</tr>
<tr class="even">
<td><p>ConversationalMOS</p></td>
<td><p>10進数 (3、2)</p></td>
<td><p>音声セッションの Narrowband Conversational MOS (音声ストリームに基づく)。</p></td>
</tr>
<tr class="odd">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>これは、さまざまなポリシー設定 (TURN、API、SDP、ポリシー サーバーなど) が構成された特定の送信側ストリームに適用される実際の帯域幅です。この帯域幅を実効帯域幅と見なすことはできません。実効帯域幅は、帯域幅の評価に基づいて実際よりも低くなる可能性があります。これは基本的に、送信ストリームで利用できる最大帯域幅です (帯域幅の評価によって課せられる制限を除く)。</p></td>
</tr>
<tr class="even">
<td><p>AppliedBandwidthSource</p></td>
<td><p>varchar (256)</p></td>
<td><p>適用されている帯域幅制限のソースです。帯域幅制限の適用元を示します ("Policy Server"、"TURN Server"、"Modality" など)。</p></td>
</tr>
<tr class="odd">
<td><p>Caller</p></td>
<td><p>若干</p></td>
<td><p>発信者からの指標が受信されたかどうかを示します。1 は "はい"、0 は "いいえ" です。</p></td>
</tr>
<tr class="even">
<td><p>側</p></td>
<td><p>若干</p></td>
<td><p>通話受信者からの指標が受信されたかどうかを示します。1 は "はい"、0 は "いいえ" です。</p></td>
</tr>
<tr class="odd">
<td><p>MidCallReport</p></td>
<td><p>若干</p></td>
<td><p>レポートの対象が通話の一部か全部かを示します。</p></td>
</tr>
<tr class="even">
<td><p>ClassifiedPoorCall</p></td>
<td><p>若干</p></td>
<td><p>通話が低品質通話 (1) と高品質通話 (0) のどちらに分類されたかを示します。</p></td>
</tr>
<tr class="odd">
<td><p>CallerConnectivityICE</p></td>
<td><p>tinyint</p></td>
<td><p>発信者が ICE プロトコル (Internet Connectivity Establishment) を使用してネットワークに接続したかどうかを示します。</p></td>
</tr>
<tr class="even">
<td><p>CalleeConnectivityICE</p></td>
<td><p>tinyint</p></td>
<td><p>通話受信者が ICE プロトコル (Internet Connectivity Establishment) を使用してネットワークに接続したかどうかを示します。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

