---
title: 'Lync Server 2013: AudioStream テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioStream table
ms:assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425961(v=OCS.15)
ms:contentKeyID: 48184077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97a8015bce118991b21b541faf588dd4d76ac784
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostream-table-in-lync-server-2013"></a>Lync Server 2013 の AudioStream テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-02_

各レコードは1つのオーディオストリームを表します。 通常、1つのオーディオメディアラインには2つのオーディオストリームが含まれています。


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
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されている。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されている。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されている。</p></td>
</tr>
<tr class="even">
<td><p><strong>StreamID</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>メディアライン内の一意の ID。</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>リアルタイム制御プロトコル (RTCP) の統計情報からの平均ネットワークジッター。</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>通話中の最大ネットワークジッター。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>10進数 (5, 4)</p></td>
<td><p> </p></td>
<td><p>通話中の平均パケット損失率。</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>10進数 (5, 4)</p></td>
<td><p> </p></td>
<td><p>通話中に発生したパケット損失の上限。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BurstDensity</strong></p></td>
<td><p>10進数 (9, 4)</p></td>
<td><p> </p></td>
<td><p>通話中に損失が発生した場合のパケット損失の平均密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>BurstDuration</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>通話中に損失が発生したときのパケット損失の平均時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BurstGapDensity</strong></p></td>
<td><p>10進数 (9, 4)</p></td>
<td><p> </p></td>
<td><p>パケット損失のバースト間のパケット損失の平均密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>BurstGapDuration</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>パケット損失のバーストの間の平均時間差。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>オーディオストリームのパケット数。</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEst</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>オーディオストリームの帯域幅の推定。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DegradationAvg</strong></p></td>
<td><p>10進数 (3, 2)</p></td>
<td><p> </p></td>
<td><p>電話全体のネットワーク MOS が低下します。 範囲は 0.0 ~ 5.0 です。 このメトリックは、ジッタとパケット損失によってネットワーク MOS が削減された量を示します。 許容可能な品質には、0.5 未満の値を指定する必要があります。</p></td>
</tr>
<tr class="even">
<td><p><strong>DegradationMax</strong></p></td>
<td><p>10進数 (3, 2)</p></td>
<td><p> </p></td>
<td><p>通話中の最大ネットワーク MOS の品質低下。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DegradationJitterAvg</strong></p></td>
<td><p>10進数 (3, 2)</p></td>
<td><p> </p></td>
<td><p>ジッターによるネットワーク MOS の低下。</p></td>
</tr>
<tr class="even">
<td><p><strong>DegradationPacketLossAvg</strong></p></td>
<td><p>10進数 (3, 2)</p></td>
<td><p> </p></td>
<td><p>パケット損失によるネットワーク MOS の低下。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioPayloadDescription</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>PayloadDescription テーブルから参照される、通話に使われるオーディオコーデック。</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioSampleRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>オーディオストリームのサンプリングレート。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RoundTrip</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>RTCP の統計情報からのラウンドトリップ時間。 許容可能な品質の場合は、100ms 未満にしてください。</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>オーディオストリームの最大ラウンドトリップ時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OverallAvgNetworkMOS</strong></p></td>
<td><p>10進数 (3, 2)</p></td>
<td><p> </p></td>
<td><p>通話の平均広帯域ネットワーク MOS。 このメトリックは、使用されているパケット損失、ジッタ、およびコーデックによって異なります。 範囲は [1.0 から 5.0] になります。</p></td>
</tr>
<tr class="even">
<td><p><strong>OverallMinNetworkMOS</strong></p></td>
<td><p>10進数 (3, 2)</p></td>
<td><p> </p></td>
<td><p>通話の最小広帯域ネットワーク MOS。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendListenMOS</strong></p></td>
<td><p>10進数 (3, 2)</p></td>
<td><p> </p></td>
<td><p>送信された音声の平均予測広帯域 MOS score (音声レベル、ノイズレベル、キャプチャデバイスの特性を含む)。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendListenMOSMin</strong></p></td>
<td><p>10進数 (3, 2)</p></td>
<td><p> </p></td>
<td><p>通話の最小 SendListenMOS。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvListenMOS</strong></p></td>
<td><p>10進数 (3, 2)</p></td>
<td><p> </p></td>
<td><p>予測される平均広帯域は、ネットワークから受信した音声の MOS スコア (音声レベル、ノイズレベル、コーデック、ネットワーク条件、キャプチャデバイスの特性など) を対象としています。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvListenMOSMin</strong></p></td>
<td><p>10進数 (3, 2)</p></td>
<td><p> </p></td>
<td><p>通話の最小 RecvListenMOS。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioFECUsed</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>通話にオーディオ FEC が使用されたかどうかを示すフラグ。</p></td>
</tr>
<tr class="even">
<td><p><strong>RatioConcealedSamplesAvg</strong></p></td>
<td><p>10進数 (5, 2)</p></td>
<td></td>
<td><p>オーディオの修復によって発生した、一般的なサンプルの平均比率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RatioStretchedSamplesAvg</strong></p></td>
<td><p>10進数 (5, 2)</p></td>
<td></td>
<td><p>オーディオ修復によって生成された、一般的なサンプルの平均比率。</p></td>
</tr>
<tr class="even">
<td><p><strong>RatioCompressedSamplesAvg</strong></p></td>
<td><p>10進数 (5, 2)</p></td>
<td></td>
<td><p>オーディオの修復によって生成された、一般的なサンプルの圧縮サンプルの平均比率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>トラフィック</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>受信側のストリームデータが受信されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>発信</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>送信側のストリームデータが受信されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>1は、ストリームの方向を呼び出し元から呼び出し先に転送することを意味します。</p>
<p>0は、ストリームの方向を呼び出し元から呼び出し元に転送します。</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalSD</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>ジッタの到着時刻の標準偏差。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConcealRatioMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Healer によって隠されているパケットの最大比率。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConcealRatioSD</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Healer によって隠されているパケットの比率の標準偏差。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>HealerPacketDropRatio</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>受信したパケットの合計数と比較して、healer によってドロップされたパケットの比率。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>HealerFECPacketUsedRatio</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>受信したパケットの合計数と比較した、使用された転送エラー修正パケットの比率。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MaxCompressedSamples</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Healer によって圧縮されたオーディオパケットの最大数。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>LossCongestionPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>通話が切断された輻輳状態であった時間の割合を示します。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DelayCongestionPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>ネットワークパケットが遅延したために発生した、通話の割合を示します。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentionDetectedPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>通話がネットワークリソースに対して競合した時間の割合を示します。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstMin</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>通話中の最小帯域幅推定値。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>通話中に測定された帯域幅推定の最大量。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstStdDev</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>通話中に測定された帯域幅推定の標準偏差。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstAvge</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>通話中に計測された平均帯域幅推定量。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>一方向の待機時間の合計。 相対的な一方向の待ち時間は、クライアントとサーバーの間の遅延を測定します。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>一方向の待ち時間の平均値。 相対的な一方向の待ち時間は、クライアントとサーバーの間の遅延を測定します。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>一方向の待機時間の上限。 相対的な一方向の待ち時間は、クライアントとサーバーの間の遅延を測定します。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>1方向のバースト発生の合計。 "Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。 このメトリックは、クライアントとサーバー間のデータフローを計測します。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>全体的な1方向バースト密度。 "Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。 このメトリックは、クライアントとサーバー間のデータフローを計測します。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>一方向のバースト期間の合計。 "Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。 このメトリックは、クライアントとサーバー間のデータフローを計測します。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>一方向のギャップ出現の合計。 "Bursty" 伝送とは、安定したストリームではなく、予期しないバーストでデータが流れる伝送です。ギャップは、このようなバーストの間の遅延を示します。 このメトリックは、クライアントとサーバー間のデータフローを計測します。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>一方向のギャップの密度の合計。 "Bursty" 伝送とは、安定したストリームではなく、予期しないバーストでデータが流れる伝送です。ギャップは、このようなバーストの間の遅延を示します。 このメトリックは、クライアントとサーバー間のデータフローを計測します。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>一方向のギャップ期間の合計。 "Bursty" 伝送とは、安定したストリームではなく、予期しないバーストでデータが流れる伝送です。ギャップは、このようなバーストの間の遅延を示します。 このメトリックは、クライアントとサーバー間のデータフローを計測します。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>DecodeStereoPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>ステレオとしてデコードされた通話のパーセンテージ。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AecRenderStereoPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>アコースティックエコーキャンセラによってステレオとしてレンダリングされた通話の割合。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioPostFECPLR</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>転送後のエラー訂正が適用された後のパケット損失率。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EncodeStereoPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>ステレオとしてエンコードされた通話の割合。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>AecCaptureStereoPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>アコースティックエコーキャンセラでステレオとしてキャプチャされた通話のパーセンテージ。</p>
<p>この列は Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

