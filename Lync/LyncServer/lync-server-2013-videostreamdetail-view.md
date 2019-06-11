---
title: 'Lync Server 2013: VideoStreamDetail ビュー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VideoStreamDetail view
ms:assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721928(v=OCS.15)
ms:contentKeyID: 49733863
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95cc003a0e136a4a4c123355548b95c9566b4b31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostreamdetail-view-in-lync-server-2013"></a>Lync Server 2013 の VideoStreamDetail ビュー

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-03_

VideoStreamDetail ビューには、データベース内の各ビデオストリームに関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。


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
<td><p>セッション時間</p></td>
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
<td><p>StreamId</p></td>
<td><p>int</p></td>
<td><p>メディアライン内の一意の ID。</p></td>
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
<td><p>通話の優先度。</p></td>
</tr>
<tr class="even">
<td><p>CallerPool</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>発信者番号プールの FQDN。</p></td>
</tr>
<tr class="odd">
<td><p>CalleePool</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>呼び出し元プールの FQDN。</p></td>
</tr>
<tr class="even">
<td><p>[発信者]</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>発信者の URI。</p></td>
</tr>
<tr class="odd">
<td><p>[呼び出し先]</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>呼び出し先の URI。</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>呼び出し元のユーザーエージェント文字列。</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>呼び出し元のユーザーエージェントの種類。 詳細については、「 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>呼び出し元のユーザーエージェントのカテゴリ。 詳細については、「 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 の Useragentdef テーブル (QoE)</a> 」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>呼び出し先のユーザーエージェント文字列。</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>呼び出し先のユーザーエージェントの種類。 詳細については、「 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>呼び出し先のユーザーエージェントのカテゴリ。 詳細については、「 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 の Useragentdef テーブル (QoE)</a> 」を参照してください。</p></td>
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
<td><p>nvarchar(128</p></td>
<td><p>発信者のエンドポイントのオペレーティングシステム (OS)。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeOS</p></td>
<td><p>nvarchar(128</p></td>
<td><p>呼び出し先のエンドポイントのオペレーティングシステム (OS)。</p></td>
</tr>
<tr class="even">
<td><p>Caller</p></td>
<td><p>nvarchar(128</p></td>
<td><p>呼び出し元のエンドポイントの CPU 名。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUName</p></td>
<td><p>nvarchar(128</p></td>
<td><p>呼び出し先のエンドポイントの CPU 名。</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUNumberOfCores</p></td>
<td><p>smallint</p></td>
<td><p>呼び出し元のエンドポイントの CPU コアの数。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUNumberOfCores</p></td>
<td><p>smallint</p></td>
<td><p>呼び出し先のエンドポイントの CPU コアの数。</p></td>
</tr>
<tr class="even">
<td><p>Callerプロセッサーの速度</p></td>
<td><p>int</p></td>
<td><p>発信者のエンドポイントの CPU プロセッサ速度。</p></td>
</tr>
<tr class="odd">
<td><p>Calleecpuプロセッサー速度</p></td>
<td><p>int</p></td>
<td><p>呼び出し先のエンドポイントの CPU プロセッサ速度。</p></td>
</tr>
<tr class="even">
<td><p>CallerVirtualizationFlag</p></td>
<td><p>tinyint</p></td>
<td><p>呼び出し元のシステムが仮想環境で実行されているかどうかを示します。 詳細については、「 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 のエンドポイントテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVirtualizationFlag</p></td>
<td><p>tinyint</p></td>
<td><p>呼び出し先のシステムが仮想環境で実行されているかどうかを示します。 詳細については、「 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 のエンドポイントテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>ConnectivityIce</p></td>
<td><p>tinyint</p></td>
<td><p>メディアパスについての情報 (ダイレクトまたは中継など) 詳細については、「 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p>CallerIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>発信者の bits フラグで説明されている対話型接続確立 (ICE) プロセスに関する情報。 詳細については、「エクスペリエンスの品質監視サーバープロトコルの仕様」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>対話式接続確立 (ICE) プロセスについて詳しくは、「呼び出し先のビットフラグ」で説明します。 詳細については、「エクスペリエンスの品質監視サーバープロトコルの仕様」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p>Transport</p></td>
<td><p>int</p></td>
<td><p>トランスポートの種類: 0 は UDP、1は TCP です。</p></td>
</tr>
<tr class="even">
<td><p>CallerIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>発信者の IP アドレス。 これは IPv4 または IPv6 アドレスのいずれかになります。</p></td>
</tr>
<tr class="odd">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>発信者によって使用されるポート。</p></td>
</tr>
<tr class="even">
<td><p>CallerInside</p></td>
<td><p>bit</p></td>
<td><p>発信者が組織のネットワーク内にあるかどうかを示します。 1: 発信者がエンタープライズネットワーク内にあることを示します。0は、呼び出し元がネットワークの外部にあることを意味します。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>呼び出し先の IP アドレス。 これは IPv4 または IPv6 アドレスのいずれかになります。</p></td>
</tr>
<tr class="even">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>呼び出し先によって使用されるポート。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeInside</p></td>
<td><p>bit</p></td>
<td><p>発信者が組織のネットワーク内にあるかどうかを示します。1は、呼び出し元がエンタープライズネットワーク内にあることを意味します。0は、呼び出し先がネットワークの外部にあることを意味します。</p></td>
</tr>
<tr class="even">
<td><p>CallerUserSite</p></td>
<td><p>nvarchar(128</p></td>
<td><p>発信者のサイトの名前。</p></td>
</tr>
<tr class="odd">
<td><p>CallerRegion</p></td>
<td><p>nvarchar(128</p></td>
<td><p>発信者のサイトの国/地域の名前です。</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserSite</p></td>
<td><p>nvarchar(128</p></td>
<td><p>呼び出し先のサイトの名前。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRegion</p></td>
<td><p>nvarchar(128</p></td>
<td><p>呼び出し先のサイトの国/地域の名前です。</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>発信者によって使用される A/V Edge サービスの IP アドレス。 詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p>CallerRelayPort</p></td>
<td><p>int</p></td>
<td><p>発信者によって使用される A/V Edge サービス上のポート。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>呼び出し先によって使用される A/V エッジサービスの IP アドレスキー。 詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>呼び出し先によって使用される A/V エッジサービスのポート。</p></td>
</tr>
<tr class="even">
<td><p>CallerCaptureDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>発信者のキャプチャデバイス名。</p></td>
</tr>
<tr class="odd">
<td><p>CallerRenderDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>発信者のレンダーデバイス名。</p></td>
</tr>
<tr class="even">
<td><p>CallerCaptureDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>発信者のキャプチャデバイスドライバー名。</p></td>
</tr>
<tr class="odd">
<td><p>CallerRenderDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>発信者のレンダーデバイスドライバー名。</p></td>
</tr>
<tr class="even">
<td><p>Calleecapdev</p></td>
<td><p>varchar (256)</p></td>
<td><p>呼び出し先のキャプチャデバイス名。</p></td>
</tr>
<tr class="odd">
<td><p>Calle・ Enderdev</p></td>
<td><p>varchar (256)</p></td>
<td><p>呼び出し先のレンダリングデバイス名。</p></td>
</tr>
<tr class="even">
<td><p>Callecap・ Devdriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>呼び出し先のキャプチャデバイスドライバー名。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRenderDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>呼び出し先のレンダリングデバイスドライバー名。</p></td>
</tr>
<tr class="even">
<td><p>CallerNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>発信者のネットワーク接続の種類: 0 は有線、1はワイヤレス。</p></td>
</tr>
<tr class="odd">
<td><p>CallerVPN</p></td>
<td><p>bit</p></td>
<td><p>発信者が仮想プライベートネットワーク経由で接続しているかどうかを示します。 1は仮想プライベートネットワーク (VPN)、0は非 VPN です。</p></td>
</tr>
<tr class="even">
<td><p>CallerLinkSpeed</p></td>
<td><p>10進数 (18,)</p></td>
<td><p>発信者のエンドポイントのネットワークリンク速度 (bps)。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>呼び出し先のネットワーク接続の種類: 0 は有線、1はワイヤレス。</p></td>
</tr>
<tr class="even">
<td><p>CalleeVPN</p></td>
<td><p>bit</p></td>
<td><p>呼び出し先が仮想プライベートネットワーク経由で接続されているかどうかを示します。 1は仮想プライベートネットワーク (VPN)、0は非 VPN です。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeLinkSpeed</p></td>
<td><p>10進数 (18, 0)</p></td>
<td><p>転送先のエンドポイントのネットワークリンク速度 (bps)。</p></td>
</tr>
<tr class="even">
<td><p>ConversationalMOS</p></td>
<td><p>10進数 (3, 2)</p></td>
<td><p>オーディオセッションの会話 MOS を Narrowband します (両方のオーディオストリームに基づく)。</p></td>
</tr>
<tr class="odd">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>さまざまなポリシー設定 (TURN、API、SDP、ポリシーサーバーなど) が指定された send side ストリームに適用される実際の帯域幅。 これは、帯域幅の推定値に基づいて低帯域幅を使用できるため、有効帯域幅と混同しないようにする必要があります。 これは基本的に最大帯域幅であり、送信ストリームは、帯域幅の推定値によって課された制限を受けません。</p></td>
</tr>
<tr class="even">
<td><p>JitterInterArrival</p></td>
<td><p>int</p></td>
<td><p>リアルタイム制御プロトコル (RTCP) の統計情報からの平均ネットワークジッター。</p></td>
</tr>
<tr class="odd">
<td><p>JitterInterArrivalMax</p></td>
<td><p>int</p></td>
<td><p>通話中の最大ネットワークジッター。</p></td>
</tr>
<tr class="even">
<td><p>RoundTrip</p></td>
<td><p>int</p></td>
<td><p>RTCP の統計情報からのラウンドトリップ時間。</p></td>
</tr>
<tr class="odd">
<td><p>RoundTripMax</p></td>
<td><p>int</p></td>
<td><p>オーディオストリームの最大ラウンドトリップ時間。</p></td>
</tr>
<tr class="even">
<td><p>PacketLossRate</p></td>
<td><p>10進数 (5, 4)</p></td>
<td><p>通話中の平均パケット損失率。</p></td>
</tr>
<tr class="odd">
<td><p>PacketLossRateMax</p></td>
<td><p>10進数 (5, 4)</p></td>
<td><p>通話中に発生したパケット損失の上限。</p></td>
</tr>
<tr class="even">
<td><p>PacketUtilization</p></td>
<td><p>int</p></td>
<td><p>ビデオストリームのパケット数 (リアルタイムトランスポートプロトコル、RTP)。</p></td>
</tr>
<tr class="odd">
<td><p>BandwidthEst</p></td>
<td><p>int</p></td>
<td><p>オーディオストリームの帯域幅の推定。</p></td>
</tr>
<tr class="even">
<td><p>PayloadDescription</p></td>
<td><p>int</p></td>
<td><p>通話に使用されるオーディオコーデック。 <a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 の PayloadDescription テーブル</a>から参照されています。</p></td>
</tr>
<tr class="odd">
<td><p>VideoResolution</p></td>
<td><p>char (9)</p></td>
<td><p>ピクセル幅にピクセルの高さを掛けたビデオの解像度。 文字列として報告されます。</p></td>
</tr>
<tr class="even">
<td><p>VideoBitRateAvg</p></td>
<td><p>int</p></td>
<td><p>ビデオストリームの平均ビットレート。</p></td>
</tr>
<tr class="odd">
<td><p>InboundVideoFrameRateAvg</p></td>
<td><p>10進数 (9, 4)</p></td>
<td><p>受信したビデオのフレームレート。</p></td>
</tr>
<tr class="even">
<td><p>OutboundVideoFrameRateAvg</p></td>
<td><p>10進数 (9, 4)</p></td>
<td><p>送信されたビデオのフレームレート。</p></td>
</tr>
<tr class="odd">
<td><p>ViideoBitRateMax</p></td>
<td><p>int</p></td>
<td><p>ビデオセッション中の最大ビデオビットレート。</p></td>
</tr>
<tr class="even">
<td><p>パケット損失率</p></td>
<td><p>10進数 (9, 4)</p></td>
<td><p>ビデオパケットが失われた速度。</p></td>
</tr>
<tr class="odd">
<td><p>VideoFrameLossRate</p></td>
<td><p>10進数 (9.4)</p></td>
<td><p>失われたビデオフレームの合計のパーセンテージ。</p></td>
</tr>
<tr class="even">
<td><p>VideoFEC</p></td>
<td><p>bit</p></td>
<td><p>使用されません。</p></td>
</tr>
<tr class="odd">
<td><p>VideoAllocateBWAvg</p></td>
<td><p>int</p></td>
<td><p>ビデオに割り当てられている平均帯域幅。</p></td>
</tr>
<tr class="even">
<td><p>ビデオ</p></td>
<td><p>10進数 (9.4)</p></td>
<td><p>紛失したビデオフレームの合計の割合。</p></td>
</tr>
<tr class="odd">
<td><p>SenderIsCallerPAI</p></td>
<td><p>bit</p></td>
<td><p>P がアサートした id 情報のストリームの方向。 1は、ストリームの方向を呼び出し元から呼び出し先に転送することを意味します。0は、ストリームの方向を呼び出し元から呼び出し元に転送します。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

