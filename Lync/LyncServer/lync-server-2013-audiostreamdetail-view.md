---
title: 'Lync Server 2013: AudioStreamDetail ビュー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioStreamDetail view
ms:assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721859(v=OCS.15)
ms:contentKeyID: 49733792
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77cebcd47d735f1779396c0272877c0ec64a6189
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostreamdetail-view-in-lync-server-2013"></a>Lync Server 2013 の AudioStreamDetail ビュー

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-03_

AudioStreamDetail ビューには、データベース内の各オーディオストリームに関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。


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
<td><p>StreamId</p></td>
<td><p>int</p></td>
<td><p>メディアライン内の一意の ID。</p></td>
</tr>
<tr class="even">
<td><p>StartTime</p></td>
<td><p>datetime</p></td>
<td><p>セッションの開始時刻。</p></td>
</tr>
<tr class="odd">
<td><p>EndTime</p></td>
<td><p>datetime</p></td>
<td><p>セッションの終了時刻。</p></td>
</tr>
<tr class="even">
<td><p>このカテゴリ</p></td>
<td><p>bit</p></td>
<td><p>ダイアログカテゴリ: 0 は、仲介サーバー間の Lync サーバーです。1は PSTN ゲートウェイ区間の仲介サーバーです。</p></td>
</tr>
<tr class="odd">
<td><p>MediationServerBypassFlag</p></td>
<td><p>bit</p></td>
<td><p>通話がバイパスされたかどうかを示すフラグ。</p></td>
</tr>
<tr class="even">
<td><p>Mediabypasswarnings フラグ</p></td>
<td><p>int</p></td>
<td><p>存在する場合は、バイパス Id が一致した場合でも、通話がバイパスされなかった理由を示します。 1つの値のみが定義されます。</p>
<p>0x0001 –既定のネットワークアダプターの不明なバイパス ID。</p></td>
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
<td><p>発信者のユーザーエージェントのカテゴリ。 詳細については、「 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 の Useragentdef テーブル (QoE)</a> 」を参照してください。</p></td>
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
<td><p>呼び出し先のエンドポイントの CPU コアの数です。</p></td>
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
<td><p>CorrelationKey</p></td>
<td></td>
<td><p>相関関係キー。 <a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013 の Sessioncorrelation テーブル</a>から参照されます。</p></td>
</tr>
<tr class="odd">
<td><p>ConnectivityIce</p></td>
<td><p>tinyint</p></td>
<td><p>メディアパスについての情報 (ダイレクトまたは中継など) 詳細については、「 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>」を参照してください。</p></td>
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
<td><p>Transport</p></td>
<td><p>tinyint</p></td>
<td><p>トランスポートの種類: 0 は UDP、1は TCP です。</p></td>
</tr>
<tr class="odd">
<td><p>CallerIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>発信者の IP アドレス。 これは IPv4 または IPv6 アドレスのいずれかになります。</p></td>
</tr>
<tr class="even">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>発信者によって使用されるポート。</p></td>
</tr>
<tr class="odd">
<td><p>CallerInside</p></td>
<td><p>bit</p></td>
<td><p>発信者が間隔ネットワーク内にあるかどうかを示します。1は、発信者がエンタープライズネットワーク内にあることを意味します。0は、発信者がネットワークの外部にあることを意味します。</p></td>
</tr>
<tr class="even">
<td><p>CalleeIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>呼び出し先の IP アドレス。 これは IPv4 または IPv6 アドレスのいずれかになります。</p></td>
</tr>
<tr class="odd">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>呼び出し先によって使用されるポート。</p></td>
</tr>
<tr class="even">
<td><p>CalleeInside</p></td>
<td><p>bit</p></td>
<td><p>呼び出し先が間隔ネットワーク内にあるかどうかを示します。1は、呼び出し先がエンタープライズネットワーク内にあることを意味します。0は、呼び出し先がネットワークの外部にあることを意味します。</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserSite</p></td>
<td><p>nvarchar(128</p></td>
<td><p>発信者のサイトの名前。</p></td>
</tr>
<tr class="even">
<td><p>CallerRegion</p></td>
<td><p>nvarchar(128</p></td>
<td><p>発信者のサイトの国/地域の名前です。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserSite</p></td>
<td><p>nvarchar(128</p></td>
<td><p>呼び出し先のサイトの名前。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRegion</p></td>
<td><p>nvarchar(128</p></td>
<td><p>呼び出し先のサイトの国/地域の名前です。</p></td>
</tr>
<tr class="odd">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>発信者によって使用される A/V Edge サービスの IP アドレス。 詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayPort</p></td>
<td><p>int</p></td>
<td><p>発信者が使用する A/V Edge サービスで使用されるポート。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>呼び出し先によって使用される A/V エッジサービスの IP アドレスキー。 詳細については、「 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>呼び出し先によって使用される A/V Edge サービスで使用されるポート。</p></td>
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
<td><p>CallerRenderDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>発信者のレンダーデバイスドライバー名。</p></td>
</tr>
<tr class="odd">
<td><p>Calleecapdev</p></td>
<td><p>varchar (256)</p></td>
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
<td><p>CallerNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>発信者のネットワーク接続の種類: 0 は有線、1はワイヤレス。</p></td>
</tr>
<tr class="even">
<td><p>CallerVPN</p></td>
<td><p>bit</p></td>
<td><p>発信者が仮想プライベートネットワーク経由で接続しているかどうかを示します。1は仮想プライベートネットワーク (VPN)、0は VPN 以外。</p></td>
</tr>
<tr class="odd">
<td><p>CallerLinkSpeed</p></td>
<td><p>10進数 (18, 0)</p></td>
<td><p>発信者のエンドポイントのネットワークリンク速度 (bps)。</p></td>
</tr>
<tr class="even">
<td><p>CalleeNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>呼び出し先のネットワーク接続の種類: 0 は有線、1はワイヤレス。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVPN</p></td>
<td><p>bit</p></td>
<td><p>発信者が仮想プライベートネットワーク経由で接続しているかどうかを示します。1は仮想プライベートネットワーク (VPN)、0は VPN 以外。</p></td>
</tr>
<tr class="even">
<td><p>CalleeLinkSpeed</p></td>
<td><p>10進数 (18, 0)</p></td>
<td><p>転送先のエンドポイントのネットワークリンク速度 (bps)。</p></td>
</tr>
<tr class="odd">
<td><p>ConversationalMOS</p></td>
<td><p>10進数 (3, 2)</p></td>
<td><p>オーディオセッションの会話 MOS を Narrowband します (両方のオーディオストリームに基づく)。</p></td>
</tr>
<tr class="even">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>さまざまなポリシー設定 (TURN、API、SDP、ポリシーサーバーなど) が指定された send side ストリームに適用される実際の帯域幅。 これは、帯域幅の推定値に基づいて低帯域幅を使用できるため、有効帯域幅と混同しないようにする必要があります。 これは基本的に最大帯域幅であり、送信ストリームは、帯域幅の推定によって課された制限を受けることができません。</p></td>
</tr>
<tr class="odd">
<td><p>JitterInterArrival</p></td>
<td><p>int</p></td>
<td><p>リアルタイム制御プロトコル (RTCP) の統計情報からの平均ネットワークジッター。</p></td>
</tr>
<tr class="even">
<td><p>JitterInterArrivalMax</p></td>
<td><p>int</p></td>
<td><p>通話中の最大ネットワークジッター。</p></td>
</tr>
<tr class="odd">
<td><p>PacketLossRate</p></td>
<td><p>10進数 (5, 4)</p></td>
<td><p>通話中の平均パケット損失率。</p></td>
</tr>
<tr class="even">
<td><p>PacketLossRateMax</p></td>
<td><p>10進数 (5, 4)</p></td>
<td><p>通話中に発生したパケット損失の上限。</p></td>
</tr>
<tr class="odd">
<td><p>BurstDensity</p></td>
<td><p>10進数 (9, 4)</p></td>
<td><p>通話中に損失が発生した場合のパケット損失の平均密度。</p></td>
</tr>
<tr class="even">
<td><p>BurstDuration</p></td>
<td><p>int</p></td>
<td><p>通話中に損失が発生したときのパケット損失の平均時間。</p></td>
</tr>
<tr class="odd">
<td><p>BurstGapDensity</p></td>
<td><p>10進数 (9, 4)</p></td>
<td><p>パケット損失のバースト間のパケット損失の平均密度。</p></td>
</tr>
<tr class="even">
<td><p>BurstGapDuration</p></td>
<td><p>int</p></td>
<td><p>パケット損失のバーストの間の平均時間差。</p></td>
</tr>
<tr class="odd">
<td><p>PacketUtilization</p></td>
<td><p>int</p></td>
<td><p>オーディオストリームのパケット数。</p></td>
</tr>
<tr class="even">
<td><p>BandwidthEst</p></td>
<td><p>int</p></td>
<td><p>オーディオストリームの帯域幅の推定。</p></td>
</tr>
<tr class="odd">
<td><p>DegradationAvg</p></td>
<td><p>10進数 (3, 2)</p></td>
<td><p>電話全体のネットワーク MOS が低下します。 範囲は 0.0 ~ 5.0 です。 このメトリックは、ジッタとパケット損失によってネットワーク MOS が削減された量を示します。 許容可能な品質には、0.5 未満の値を指定する必要があります。</p></td>
</tr>
<tr class="even">
<td><p>DegradationMax</p></td>
<td><p>10進数 (3, 2)</p></td>
<td><p>通話中の最大ネットワーク MOS の品質低下。</p></td>
</tr>
<tr class="odd">
<td><p>DegradationJitterAvg</p></td>
<td><p>10進数 (3, 2)</p></td>
<td><p>ジッターによるネットワーク MOS の低下。</p></td>
</tr>
<tr class="even">
<td><p>DegradationPacketLossAvg</p></td>
<td><p>10進数 (3, 2)</p></td>
<td><p>パケット損失によるネットワーク MOS の低下。</p></td>
</tr>
<tr class="odd">
<td><p>PayloadDescription</p></td>
<td><p>int</p></td>
<td><p>通話に使用するオーディオコーデック。 <a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 の PayloadDescription テーブル</a>から参照されています。</p></td>
</tr>
<tr class="even">
<td><p>AudioSampleRate</p></td>
<td><p>int</p></td>
<td><p>オーディオストリームのサンプリングレート。</p></td>
</tr>
<tr class="odd">
<td><p>CallerSendSignalLevel</p></td>
<td><p>int</p></td>
<td><p>発信者が送信したオーディオのアナログゲインの制御オーディオ信号レベル。 このメトリックの単位は dBmo です。 許容可能な品質を求めるには、少なくとも30個の dBmo を指定する必要があります。 このメトリックは、A/V 会議サーバーまたは IP 携帯電話によって報告されることはありません。</p></td>
</tr>
<tr class="even">
<td><p>CallerRecvSignalLevel</p></td>
<td><p>int</p></td>
<td><p>発信者が受信した音声の音声信号レベル。 このメトリックの単位は dBmo です。 許容可能な品質を求めるには、少なくとも30個の dBmo を指定する必要があります。 このメトリックは、A/V 会議サーバーまたは IP 携帯電話によって報告されることはありません。</p></td>
</tr>
<tr class="odd">
<td><p>CallerSendNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>発信者が送信したオーディオのアナログゲインのオーディオノイズレベルを制御します。 このメトリックの単位は dBmo です。 許容される品質には、35 dBmo よりも小さい値を指定する必要があります。 このメトリックは、A/V 会議サーバーまたは IP 携帯電話によって報告されることはありません。</p></td>
</tr>
<tr class="even">
<td><p>CallerRecvNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>送信者が受信したオーディオのアナログゲインのオーディオノイズレベルを制御します。 このメトリックの単位は dBmo です。 許容される品質には、35 dBmo よりも小さい値を指定する必要があります。 このメトリックは、A/V 会議サーバーまたは IP 携帯電話によって報告されることはありません。</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoReturn</p></td>
<td><p>int</p></td>
<td><p>発信者に対する戻り値の損失の強調機能。 このメトリックの単位は dB です。 小さい値は、エコーが少なくなります。 このメトリックは、A/V 会議サーバーまたは IP 携帯電話によって報告されることはありません。</p></td>
</tr>
<tr class="even">
<td><p>CallerSpeakerGlitchRate</p></td>
<td><p>int</p></td>
<td><p>発信者のスピーカーレンダリングに対する5分あたりの平均エラー。 品質を向上させるには、5分未満でなければなりません。 A/V 会議サーバー、仲介サーバー、または IP 電話によって報告されていません。</p></td>
</tr>
<tr class="odd">
<td><p>CallerMicGlitchRate</p></td>
<td><p>int</p></td>
<td><p>発信者のマイクのキャプチャに対する5分あたりの平均エラー。 品質を向上させるには、5分未満の値を指定する必要があります。 A/V 会議サーバー、仲介サーバー、または IP 電話によって報告されていません。</p></td>
</tr>
<tr class="even">
<td><p>CallerTimestampDriftRateMic</p></td>
<td><p>10進数 (9, 2)</p></td>
<td><p>発信者のマイクデバイスクロックドリフトレート。 CPU クロックを基準としています。</p></td>
</tr>
<tr class="odd">
<td><p>CallerTimestampDriftRateSpk</p></td>
<td><p>10進数 (9, 2)</p></td>
<td><p>発信者のスピーカーデバイスクロックドリフトレート。 CPU クロックを基準としています。</p></td>
</tr>
<tr class="even">
<td><p>CallerTimestampErrorMicMs</p></td>
<td><p>10進数 (9, 2)</p></td>
<td><p>平均マイクキャプチャストリームタイムスタンプエラー (ミリ秒単位)、通話の最後の20秒。</p></td>
</tr>
<tr class="odd">
<td><p>CallerTimestampErrorSpkMs</p></td>
<td><p>10進数 (9, 2)</p></td>
<td><p>発信者のスピーカーレンダーストリームのタイムスタンプエラーの平均値 (ミリ秒) です。</p></td>
</tr>
<tr class="even">
<td><p>CallerVsEntryCauses 原因</p></td>
<td><p>smallint</p></td>
<td><p>音声スイッチは半二重モードで、中断機能が低減されます。 詳細については、「 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoEventCauses</p></td>
<td><p>tinyint</p></td>
<td><p>呼び出し元のエコーイベントの原因。 詳細については、「 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>CallerEchoPercentMicIn</p></td>
<td><p>10進数 (5, 2)</p></td>
<td><p>呼び出し元のマイクキャプチャストリームでエコーが検出された時間のパーセンテージ。 ヘッドセットを使用する場合は、値を低くする必要があります。</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoPercentSend</p></td>
<td><p>10進数 (5, 2)</p></td>
<td><p>呼び出し元の送信ストリームでエコーが検出された時間のパーセンテージ。 送信ストリームでのエコー率が高いと、エコーが発生したことを示します。</p></td>
</tr>
<tr class="even">
<td><p>CallerRxAGCSignalLevel</p></td>
<td><p>int</p></td>
<td><p>発信者のオーディオのためのゲートウェイからの仲介サーバー上のシグナルレベルを受信しました。これは、仲介サーバーにのみ適用されます。 このメトリックの単位は dBoV です。 品質を向上させるには、許容範囲は-30 ~-18 dBoV にする必要があります。</p></td>
</tr>
<tr class="odd">
<td><p>CallerRxAGCNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>発信者のオーディオのためのゲートウェイからの仲介サーバー上のシグナルレベルを受信しました。 これは、仲介サーバーにのみ適用されます。 このメトリックの単位は dBoV です。 品質を向上させるには、許容範囲として 50 dBoV 未満の値を指定する必要があります。</p></td>
</tr>
<tr class="even">
<td><p>CallerRxAGCGain</p></td>
<td><p>int</p></td>
<td><p>発信者の音声に適用された仲介サーバー側の自動ゲイン制御 (AGC)。</p></td>
</tr>
<tr class="odd">
<td><p>CallerInitialSignalLevelRMS</p></td>
<td><p>float</p></td>
<td><p>通話の最初の30秒間の着信シグナルの発信者への着信シグナルの平方根 (RMS)。</p></td>
</tr>
<tr class="even">
<td><p>CalleeSendSignalLevel</p></td>
<td><p>int</p></td>
<td><p>呼び出し元が送信したオーディオのアナログゲインコントロールオーディオ信号レベルを表します。 このメトリックの単位は dBmo です。 許容可能な品質を求めるには、少なくとも30個の dBmo を指定する必要があります。 このメトリックは、A/V 会議サーバーまたは IP 携帯電話によって報告されることはありません。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRecvSignalLevel</p></td>
<td><p>int</p></td>
<td><p>呼び出し側が受信したオーディオの音声信号レベル。 このメトリックの単位は dBmo です。 許容可能な品質を求めるには、少なくとも30個の dBmo を指定する必要があります。 このメトリックは、A/V 会議サーバーまたは IP 携帯電話によって報告されることはありません。</p></td>
</tr>
<tr class="even">
<td><p>CalleeSendNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>以降のアナログゲインは、呼び出し元が送信したオーディオに対してオーディオノイズレベルを制御します。 このメトリックの単位は dBmo です。 許容される品質には、35 dBmo よりも小さい値を指定する必要があります。 このメトリックは、A/V 会議サーバーまたは IP 携帯電話によって報告されることはありません。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRecvNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>後からのアナログゲインコントロール呼び出し側が受信したオーディオのオーディオノイズレベルを制御します。 このメトリックの単位は dBmo です。 許容される品質には、35 dBmo よりも小さい値を指定する必要があります。 このメトリックは、A/V 会議サーバーまたは IP 携帯電話によって報告されることはありません。</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoReturn</p></td>
<td><p>int</p></td>
<td><p>呼び出し先のエコーリターンロスの強化。 このメトリックの単位は dB です。 小さい値は、エコーが少なくなります。 このメトリックは、A/V 会議サーバーまたは IP 携帯電話によって報告されることはありません。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeSpeakerGlitchRate</p></td>
<td><p>int</p></td>
<td><p>呼び出し先のスピーカーレンダリングに対する5分あたりの平均エラー。 品質を向上させるには、5分未満でなければなりません。 A/V 会議サーバー、仲介サーバー、または IP 電話によって報告されていません。</p></td>
</tr>
<tr class="even">
<td><p>CalleeMicGlitchRate</p></td>
<td><p>int</p></td>
<td><p>呼び出し先のマイクのキャプチャに対する5分あたりの平均エラー。 品質を向上させるには、5分未満の値を指定する必要があります。 A/V 会議サーバー、仲介サーバー、または IP 電話によって報告されていません。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeTimestampDriftRateMic</p></td>
<td><p>10進数 (9, 2)</p></td>
<td><p>呼び出し先のマイクデバイスクロックドリフトレート。 CPU クロックを基準としています。</p></td>
</tr>
<tr class="even">
<td><p>CalleeTimestampDriftRateSpk</p></td>
<td><p>10進数 (9, 2)</p></td>
<td><p>呼び出し先のスピーカーデバイスクロックドリフト率。 CPU クロックを基準としています。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeTimestampErrorMicMs</p></td>
<td><p>10進数 (9, 2)</p></td>
<td><p>平均マイクキャプチャストリームタイムスタンプエラー (ミリ秒単位)、通話の最後の20秒。</p></td>
</tr>
<tr class="even">
<td><p>CalleeTimestampErrorSpkMs</p></td>
<td><p>10進数 (9, 2)</p></td>
<td><p>呼び出し側のスピーカーレンダーストリームのタイムスタンプエラーの平均 (ミリ秒) です。これは、通話の最後の20秒を示しています。</p></td>
</tr>
<tr class="odd">
<td><p>Calleevsenの原因</p></td>
<td><p>smallint</p></td>
<td><p>音声スイッチは半二重モードで、中断機能が低減されます。 詳細については、「 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoEventCauses</p></td>
<td><p>tinyint</p></td>
<td><p>呼び出し先のエコーイベントの原因。 詳細については、「 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeEchoPercentMicIn</p></td>
<td><p>10進数 (5, 2)</p></td>
<td><p>呼び出し先のマイクキャプチャストリームでエコーが検出された時間のパーセンテージ。 ヘッドセットを使用する場合は、値を低くする必要があります。</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoPercentSend</p></td>
<td><p>10進数 (5, 2)</p></td>
<td><p>呼び出し元の送信ストリームでエコーが検出された時間のパーセンテージ。 送信ストリームでのエコー率が高いと、エコーが発生したことを示します。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRxAGCSignalLevel</p></td>
<td><p>int</p></td>
<td><p>呼び出し元のオーディオのゲートウェイからの、仲介サーバー上の受信したシグナルレベル。これは、仲介サーバーにのみ適用されます。 このメトリックの単位は dBoV です。 品質を向上させるには、許容範囲は [-30 ~-18] の dBoV にする必要があります。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRxAGCNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>呼び出し元のオーディオのゲートウェイからの、仲介サーバー上の受信したシグナルレベル。 これは、仲介サーバーにのみ適用されます。 このメトリックの単位は dBoV です。 品質を向上させるには、許容範囲として 50 dBoV 未満の値を指定する必要があります。</p></td>
</tr>
<tr class="odd">
<td><p>お金の獲得</p></td>
<td><p>int</p></td>
<td><p>呼び出し先のオーディオに適用された仲介サーバー側の自動ゲイン制御 (AGC)。</p></td>
</tr>
<tr class="even">
<td><p>CalleeInitialSignalLevelRMS</p></td>
<td><p>float</p></td>
<td><p>呼び出しの最初の30秒間の呼び出し先への着信シグナルのルート平均平方根 (RMS)。</p></td>
</tr>
<tr class="odd">
<td><p>RatioConcealedSamplesAvg</p></td>
<td><p>10進数 (5, 2)</p></td>
<td><p>オーディオの修復によって発生した、一般的なサンプルの平均比率。</p></td>
</tr>
<tr class="even">
<td><p>RatioStretchedSamplesAvg</p></td>
<td><p>10進数 (5, 2)</p></td>
<td><p>オーディオ修復によって生成された、一般的なサンプルの平均比率。</p></td>
</tr>
<tr class="odd">
<td><p>RatioCompressedSamplesAvg</p></td>
<td><p>10進数 (5, 2)</p></td>
<td><p>オーディオの修復によって生成された、一般的なサンプルの圧縮サンプルの平均比率。</p></td>
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
<td><p>OverallAvgNetworkMOS</p></td>
<td><p>10進数 (3, 2)</p></td>
<td><p>通話の平均広帯域ネットワーク MOS。 このメトリックは、使用されているパケット損失、ジッタ、およびコーデックによって異なります。 範囲は 1.0 ~ 5.0 です。</p></td>
</tr>
<tr class="odd">
<td><p>OverallMinNetworkMOS</p></td>
<td><p>10進数 (3, 2)</p></td>
<td><p>通話の最小広帯域ネットワーク MOS。</p></td>
</tr>
<tr class="even">
<td><p>SendListenMOS</p></td>
<td><p>10進数 (3, 2)</p></td>
<td><p>平均予測広帯域は、音声のレベル、ノイズレベル、キャプチャデバイスの特性など、送信された音声の MOS スコアを聞き取ります。</p></td>
</tr>
<tr class="odd">
<td><p>SendListenMOSMin</p></td>
<td><p>10進数 (3, 2)</p></td>
<td><p>通話の最小 SendListenMOS。</p></td>
</tr>
<tr class="even">
<td><p>RecvListenMOS</p></td>
<td><p>10進数 (3, 2)</p></td>
<td><p>予測される平均広帯域は、ネットワークから受信した音声 (音声のレベル、ノイズレベル、コーデック、ネットワーク条件、キャプチャデバイスの特性など) を対象としています。</p></td>
</tr>
<tr class="odd">
<td><p>RecvListenMOSMin</p></td>
<td><p>10進数 (3, 2)</p></td>
<td><p>通話の最小 RecvListenMOS。</p></td>
</tr>
<tr class="even">
<td><p>AudioFECUsed</p></td>
<td><p>bit</p></td>
<td><p>通話にオーディオ FEC が使用されたかどうかを示します。</p></td>
</tr>
<tr class="odd">
<td><p>SenderIsCallerPAI</p></td>
<td><p>bit</p></td>
<td><p>P がアサートされた情報の方向を示します。1は、ストリームの方向を呼び出し元から呼び出し先に転送することを意味します。0は、ストリームの方向を呼び出し元から呼び出し元に転送します。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

