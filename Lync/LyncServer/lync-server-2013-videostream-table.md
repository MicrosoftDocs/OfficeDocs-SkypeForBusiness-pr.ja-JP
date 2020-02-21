---
title: 'Lync Server 2013: VideoStream テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoStream table
ms:assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425928(v=OCS.15)
ms:contentKeyID: 48184014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a313419ca4072fe4d1841ba66a9cb603671e6c56
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211649"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="videostream-table-in-lync-server-2013"></a>Lync Server 2013 の VideoStream テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-12-13_

各レコードは1つのビデオストリームを表します。 通常、1つのビデオメディアラインには2つのビデオストリームが含まれています。


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
<td><p>日付型</p></td>
<td><p>Primary</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">MediaLine テーブル (Lync Server 2013</a>) から参照される R。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>StreamID</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>メディア ライン内の一意の ID。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoPayloadDescription</strong></p></td>
<td><p>smallint</p></td>
<td><p>外部、プライマリ</p></td>
<td><p>ペイロードの説明。 詳細については、「 <a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 の PayloadDescription テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>リアルタイム制御プロトコル (RTCP) 統計情報に基づく平均ネットワーク ジッター。</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>ビデオセッション時の最大ネットワークジッター。</p></td>
</tr>
<tr class="even">
<td><p><strong>要し</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>RTCP 統計情報に基づく往復時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>ビデオストリームの最大往復時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>10進数 (5, 4)</p></td>
<td><p> </p></td>
<td><p>通話時の平均パケット損失率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>10進数 (5, 4)</p></td>
<td><p> </p></td>
<td><p>通話時に観測された最大パケット損失。</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>ビデオ ストリームのパケット数 (リアルタイム転送プロトコル、RTP)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEst</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>ビデオストリームの帯域幅の推定値。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoResolution</strong></p></td>
<td><p>文字 (9)</p></td>
<td><p> </p></td>
<td><p>幅×高さで示すビデオの解像度 (単位ピクセル)。文字列で報告されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoBitRateAvg</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>ビデオ ストリームの平均ビット レート。</p></td>
</tr>
<tr class="even">
<td><p><strong>InboundVideoFrameRateAvg</strong></p></td>
<td><p>10進数 (9、4)</p></td>
<td><p> </p></td>
<td><p>ビデオのフレームレートを受信しました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutboundVideoFrameRateAvg</strong></p></td>
<td><p>10進数 (9、4)</p></td>
<td><p> </p></td>
<td><p>ビデオのフレームレートが送信されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoBitRateMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>ビデオセッション時の最大ビデオビットレート。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoFrameLossRate</strong></p></td>
<td><p>10進数 (9、4)</p></td>
<td><p> </p></td>
<td><p>失われた合計ビデオフレーム数の割合。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoFEC</strong></p></td>
<td><p>若干</p></td>
<td><p> </p></td>
<td><p>注意事項なし。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoLocalFrameLossPercentageAvg</strong></p></td>
<td><p>10進数 (9、4)</p></td>
<td></td>
<td><p>失われた合計ビデオフレーム数の割合。</p></td>
</tr>
<tr class="even">
<td><p><strong>CIFQualityRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>共通交換形式 (CIF) の解決にかけられた通話のパーセンテージ。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VGAQualityRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>VGA 解像度で行われた通話のパーセンテージ。</p></td>
</tr>
<tr class="even">
<td><p><strong>HD720QualityRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>HD720 の解像度で行われた通話のパーセンテージ。</p></td>
</tr>
<tr class="odd">
<td><p><strong>NoneDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>フレームが欠落していない通話時間のパーセンテージ。</p></td>
</tr>
<tr class="even">
<td><p><strong>B' _ '</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>B フレームが欠落している通話時間のパーセンテージ。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Bp' bp'</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>BP フレームが欠落している通話時間のパーセンテージ。</p></td>
</tr>
<tr class="even">
<td><p><strong>Bpsp/Bpprた</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>BPSP フレームが欠落している通話時間のパーセンテージ。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BPSPIDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>BPSPI フレームが欠落している通話時間のパーセンテージ。</p></td>
</tr>
<tr class="even">
<td><p><strong>受信</strong></p></td>
<td><p>若干</p></td>
<td><p> </p></td>
<td><p>受信側のストリームデータが受信されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>送信</strong></p></td>
<td><p>若干</p></td>
<td><p> </p></td>
<td><p>送信側のストリームデータが受信されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>若干</p></td>
<td><p> </p></td>
<td><p>1 は、ストリームの方向が発信者から呼び出し先へ向かうことを意味します。</p>
<p>0 は、ストリームの方向が呼び出し先から発信者へ向かうことを意味します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>LossCongestionPercent</strong></p></td>
<td><p>浮動小数点数</p></td>
<td></td>
<td><p>通話が切断された輻輳状態であった時間の割合を示します。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>DelayCongestionPercent</strong></p></td>
<td><p>浮動小数点数</p></td>
<td></td>
<td><p>ネットワークパケットの遅延到着により輻輳が発生した通話の割合を示します。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ContentionDetectedPercent</strong></p></td>
<td><p>浮動小数点数</p></td>
<td></td>
<td><p>通話がネットワークリソースに対して競合していた時間の割合を示します。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstMin</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>呼び出し中に測定された最小帯域幅推定値。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>呼び出し中に測定された最大帯域幅推定値。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstStdDev</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>呼び出し中に測定された帯域幅推定の標準偏差。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstAvge</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>呼び出し中に測定された平均帯域幅推定値。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>LowBandwidthForMultiview</strong></p></td>
<td><p>浮動小数点数</p></td>
<td></td>
<td><p>エンドポイントが、ネットワーク接続がマルチビュービデオをサポートできなかったと判断した通話のパーセンテージ。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayTotal</strong></p></td>
<td><p>浮動小数点数</p></td>
<td></td>
<td><p>一方向の遅延の合計時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayAverage</strong></p></td>
<td><p>浮動小数点数</p></td>
<td></td>
<td><p>一方向の遅延の平均時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayMax</strong></p></td>
<td><p>浮動小数点数</p></td>
<td></td>
<td><p>一方向の遅延の最大時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>一方向のバーストの合計発生数。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDensity</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>一方向のバーストの合計密度。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDuration</strong></p></td>
<td><p>浮動小数点数</p></td>
<td></td>
<td><p>一方向のバーストの合計期間。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>一方向のギャップの合計発生数。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。ギャップは、これらのバースト間の遅延を示します。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapDensity</strong></p></td>
<td><p>浮動小数点数</p></td>
<td></td>
<td><p>一方向のギャップの合計密度。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。ギャップは、これらのバースト間の遅延を示します。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapDuration</strong></p></td>
<td><p>浮動小数点数</p></td>
<td></td>
<td><p>一方向のギャップの合計期間。"バースト的な" 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。ギャップは、これらのバースト間の遅延を示します。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoPacketLossRate</strong></p></td>
<td><p>10進数 (9、4)</p></td>
<td></td>
<td><p>失われたビデオ パケット数の割合。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoAllocateBWAvg</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>ビデオに割り当てられた帯域幅の平均。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendCodecTypes</strong></p></td>
<td><p>smallint</p></td>
<td><p>外部</p></td>
<td><p>送信者が使用するビデオコーデックの種類。 詳細については、「 <a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 の CodecDescription テーブル</a>」を参照してください。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Send解像度の幅</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>送信者が使用する解像度の幅。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>Send解像度の高さ</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>送信者が使用する解像度の高さ。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendFrameRateAverage</strong></p></td>
<td><p>浮動小数点数</p></td>
<td></td>
<td><p>送信者が使用する平均ビデオフレームレート伝送。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendBitRateMaximum</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>送信者の最大ビットレート。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendBitRateAverage</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>送信者の平均ビットレート。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendVideoStreamsMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>送信者が使用するビデオストリームの最大数。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvCodecTypes</strong></p></td>
<td><p>smallint</p></td>
<td><p>外部</p></td>
<td><p>受信者が使用するビデオコード。 詳細については、「 <a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 の CodecDescription テーブル</a>」を参照してください。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvResolutionWidth</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>受信者が使用する解像度の幅。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvResolutionHeight</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>受信者が使用する解像度の高さ。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvFrameRateAverage</strong></p></td>
<td><p>浮動小数点数</p></td>
<td></td>
<td><p>受信者が使用する平均ビデオフレームレート。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvBitRateMaximum</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>受信者の最大ビットレート。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvBitRateAverage</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>受信者の平均ビットレート。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvVideoStreamsMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>受信者の最大ビデオストリーム。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvVideoStreamsMin</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>受信者の最小ビデオストリーム。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvVideoStreamsMode</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>受信者のビデオモード (ギャラリー、単一ストリームなど)。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoPostFECPLR</strong></p></td>
<td><p>浮動小数点数</p></td>
<td></td>
<td><p>転送エラー訂正が適用された後のパケット損失率。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DynamicCapabilityPercent</strong></p></td>
<td><p>浮動小数点数</p></td>
<td></td>
<td><p>動的機能フラグがアクティブだった時間の割合。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>解像度 (分)</strong></p></td>
<td><p>文字 (9)</p></td>
<td></td>
<td><p>呼び出し中に測定された最小解像度。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowBitRateCallPercent</strong></p></td>
<td><p>浮動小数点数</p></td>
<td></td>
<td><p>低ビットレートのしきい値を下回る通話のパーセンテージ (70 キロビット/秒)。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>LowFrameRateCallPercent</strong></p></td>
<td><p>浮動小数点数</p></td>
<td></td>
<td><p>低フレームレートのしきい値を下回る通話のパーセンテージ (7.5 フレーム/秒、受信)。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Low解決呼び出しの割合</strong></p></td>
<td><p>浮動小数点数</p></td>
<td></td>
<td><p>最小解像度で発生した通話のパーセンテージ。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>DurationSeconds</strong></p></td>
<td><p>浮動小数点数</p></td>
<td></td>
<td><p>通話の長さ (秒単位)。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsAggregatedData</strong></p></td>
<td><p>若干</p></td>
<td></td>
<td><p>データが複数の呼び出しから集約されているかどうかを示します。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

