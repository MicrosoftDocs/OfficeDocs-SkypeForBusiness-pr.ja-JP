---
title: 'Lync Server 2013: MediaLine view'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: MediaLine view
ms:assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687972(v=OCS.15)
ms:contentKeyID: 49733560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d930f3beeeddb5c5582f41c44f1c68ff7f21f18d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-view-in-lync-server-2013"></a>Lync Server 2013 での MediaLine の表示

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-03_

MediaLine ビューには、データベース内の各メディアラインに関する情報が格納されます。 1つのオーディオセッションには通常、1つのオーディオメディアラインが含まれています。 通常、1つのオーディオとビデオ (A/V) セッションには、1つのオーディオメディアラインと1つのビデオメディアラインが含まれます。ただし、会議デバイスが使用されている場合、または [ギャラリー] ビューを使用している場合は、2つのビデオメディアがセッションに含まれている可能性があります。 このビューは、Microsoft Lync Server 2013 で導入されました。


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
<td><p>ConferenceDateTime</p></td>
<td><p>datetime</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されている。</p></td>
</tr>
<tr class="even">
<td><p>SessionSeq</p></td>
<td><p>int</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されている。</p></td>
</tr>
<tr class="odd">
<td><p>MediaLineLabel</p></td>
<td><p>tinyint</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されている。</p></td>
</tr>
<tr class="even">
<td><p>CallerIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>発信者の bits フラグで説明されている対話型接続確立 (ICE) プロセスに関する情報。 詳細については、「エクスペリエンスの品質監視サーバープロトコルの仕様」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>対話式接続確立 (ICE) プロセスについて詳しくは、「呼び出し先のビットフラグ」で説明します。 詳細については、「エクスペリエンスの品質監視サーバープロトコルの仕様」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>セキュリティ</p></td>
<td><p>tinyint</p></td>
<td><p>セキュリティプロファイルが使用されています。 0は NONE、1は SRTP、2は V1 です。</p></td>
</tr>
<tr class="odd">
<td><p>Transport</p></td>
<td><p>tinyint</p></td>
<td><p>トランスポートの種類。 0は UDP、1は TCP です。</p></td>
</tr>
<tr class="even">
<td><p>CallerIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>発信者の IP アドレス。 これは IPv4 または IPv6 のアドレスにすることができます。</p></td>
</tr>
<tr class="odd">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>発信者によって使用されるポート。</p></td>
</tr>
<tr class="even">
<td><p>CallerInside</p></td>
<td><p>bit</p></td>
<td><p>発信者が組織のネットワーク内にあるかどうかを示します。 1発信者がエンタープライズネットワーク内にあることを意味します。 0は、発信者がネットワーク外であることを意味します。</p></td>
</tr>
<tr class="odd">
<td><p>CallerMacAddress</p></td>
<td><p>varchar (256)</p></td>
<td><p>発信者によって使用されるネットワークインターフェイスの MAC アドレスです。</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>発信者によって使用される A/V Edge サービスの IP アドレス。 詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>発信者が使用する A/V Edge サービスで使用されるポート。</p></td>
</tr>
<tr class="even">
<td><p>CallerReflexiveIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>A/V Edge サービスによって報告された発信者の IP アドレス。 このアドレスは、クライアントが NAT の背後にある場合など、CallerIPAddr と異なる場合があります。</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>発信者のキャプチャデバイス名。</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>発信者のレンダーデバイス名。</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>発信者のキャプチャデバイスドライバー名。</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>発信者のレンダーデバイスドライバー名。</p></td>
</tr>
<tr class="odd">
<td><p>CallerWifiDriverDeviceDesc</p></td>
<td><p>varchar (256</p></td>
<td><p>発信者の Wifi ドライバーの説明。</p></td>
</tr>
<tr class="even">
<td><p>CallerWifiDriverVersion</p></td>
<td><p>varchar (256)</p></td>
<td><p>発信者の Wifi ドライババージョン。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionDetail</p></td>
<td><p>varchar (256)</p></td>
<td><p>発信者のネットワーク接続の詳細。 詳細については、「 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 での Networkconnectiondetail の表</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>CallerBssid</p></td>
<td><p>varchar (256)</p></td>
<td><p>発信者の WiFi 接続で使用される基本サービスセット識別子。</p></td>
</tr>
<tr class="odd">
<td><p>CallerVPN</p></td>
<td><p>bit</p></td>
<td><p>発信者が仮想プライベートネットワーク経由で接続しているかどうかを示します。 1は仮想プライベートネットワーク (VPN)、0は非 VPN です。</p></td>
</tr>
<tr class="even">
<td><p>CalleeIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>呼び出し先の IP アドレス。 これは IPv4 または IPv6 のアドレスにすることができます。</p></td>
</tr>
<tr class="odd">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>呼び出し先によって使用されるポート。</p></td>
</tr>
<tr class="even">
<td><p>CalleeInside</p></td>
<td><p>bit</p></td>
<td><p>呼び出し先がエンタープライズネットワーク内にあるかどうかを示します。 1は、呼び出し先がエンタープライズネットワーク内にあることを意味します。0は、呼び出し先がネットワークの外部にあることを意味します。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeMacAddress</p></td>
<td><p>varchar (256)</p></td>
<td><p>呼び出し先によって使用されるネットワークインターフェイスの MAC アドレスです。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>呼び出し先によって使用される A/V エッジサービスの IP アドレス。 詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>呼び出し先によって使用される A/V Edge サービスで使用されるポート。</p></td>
</tr>
<tr class="even">
<td><p>CalleeReflexiveIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>A/V Edge サービスによって報告された呼び出し先の IP アドレス。 このアドレスは、クライアントが NAT の背後にある場合など、CalleeIPAddr と異なる場合があります。</p></td>
</tr>
<tr class="odd">
<td><p>Calleecapdev</p></td>
<td><p>var (50)</p></td>
<td><p>呼び出し先のキャプチャデバイス名。</p></td>
</tr>
<tr class="even">
<td><p>Calle・ Enderdev</p></td>
<td><p>varchar (256)</p></td>
<td><p>呼び出し先のレンダリングデバイス名。</p></td>
</tr>
<tr class="odd">
<td><p>Calleecapdevdriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>呼び出し先のキャプチャデバイスドライバー名。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>呼び出し先のレンダリングデバイスドライバー名。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeWifiDriverDeviceDesc</p></td>
<td><p>varchar (256)</p></td>
<td><p>呼び出し先の Wifi ドライバーの説明。</p></td>
</tr>
<tr class="even">
<td><p>CalleeWifiDriverVersion</p></td>
<td><p>varchar (256</p></td>
<td><p>呼び出し先の Wifi ドライバーバージョン。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionDetail</p></td>
<td><p>varchar (256)</p></td>
<td><p>呼び出し先のネットワーク接続の詳細。 詳細については、「 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 での Networkconnectiondetail の表</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>CalleeBssid</p></td>
<td><p>varchar (256)</p></td>
<td><p>呼び出し先の WiFi 接続で使用される基本サービスセット識別子。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVPN</p></td>
<td><p>bit</p></td>
<td><p>呼び出し先が仮想プライベートネットワーク経由で接続されているかどうかを示します。 1は仮想プライベートネットワーク (VPN)、0は非 VPN です。</p></td>
</tr>
<tr class="even">
<td><p>ConversationalMOS</p></td>
<td><p>10進数 (3, 2)</p></td>
<td><p>オーディオセッションの会話 MOS を Narrowband します (両方のオーディオストリームに基づく)。</p></td>
</tr>
<tr class="odd">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>これは、さまざまなポリシー設定 (TURN、API、SDP、ポリシーサーバーなど) によって指定された send side stream に適用される実際の帯域幅です。 これは、帯域幅の推定値に基づいて低帯域幅を使用できるため、有効帯域幅と混同しないようにしてください。 これは基本的に最大帯域幅であり、送信ストリームは、帯域幅の推定値によって課された制限を受けません。</p></td>
</tr>
<tr class="even">
<td><p>AppliedBandwidthSource</p></td>
<td><p>varchar (256)</p></td>
<td><p>適用される帯域幅キャップのソース。 帯域幅の制限の対象となる場所 (たとえば、"Policy Server"、"TURN Server"、"モダリティ" など) について説明します。</p></td>
</tr>
<tr class="odd">
<td><p>[発信者]</p></td>
<td><p>bit</p></td>
<td><p>呼び出し元からのメトリックが受信されたかどうかを示します。1は yes、0はいいえ。</p></td>
</tr>
<tr class="even">
<td><p>[呼び出し先]</p></td>
<td><p>bit</p></td>
<td><p>通話レシーバーからのメトリックが受信されたかどうかを示します。1は yes、0はいいえ。</p></td>
</tr>
<tr class="odd">
<td><p>MidCallReport</p></td>
<td><p>bit</p></td>
<td><p>レポートが通話の一部であるか、または完了しているかを示します。</p></td>
</tr>
<tr class="even">
<td><p>ClassifiedPoorCall</p></td>
<td><p>bit</p></td>
<td><p>通話が低品質通話 (1) として分類されたか、または良好な通話 (0) であるかを示します。</p></td>
</tr>
<tr class="odd">
<td><p>CallerConnectivityICE</p></td>
<td><p>tinyint</p></td>
<td><p>発信者が ICE プロトコル (インターネット接続の確立) を使ってネットワークに接続しているかどうかを示します。</p></td>
</tr>
<tr class="even">
<td><p>CalleeConnectivityICE</p></td>
<td><p>tinyint</p></td>
<td><p>ユーザーが ICE プロトコル (インターネット接続の確立) を使ってネットワークに接続しているかどうかを示します。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

