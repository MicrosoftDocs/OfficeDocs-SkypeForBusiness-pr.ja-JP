---
title: 'Lync Server 2013: AudioStream テーブル'
description: 'Lync Server 2013: AudioStream テーブル。'
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
ms.openlocfilehash: 8af2e622e14c54fa4f9a6313e1b0dae8f2483132
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552343"
---
# <a name="audiostream-table-in-lync-server-2013"></a>Lync Server 2013 の AudioStream テーブル

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-02_

各レコードは、1つのオーディオストリームを表します。 通常、1つのオーディオメディアラインには2つのオーディオストリームが含まれています。


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
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013 の MediaLine テーブル</a>から参照されます。</p></td>
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
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>リアルタイム制御プロトコル (RTCP) 統計情報に基づく平均ネットワーク ジッター。</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>通話時の最大ネットワーク ジッター。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>10進数 (5, 4)</p></td>
<td><p> </p></td>
<td><p>通話時の平均パケット損失率。</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>10進数 (5, 4)</p></td>
<td><p> </p></td>
<td><p>通話時に観測された最大パケット損失。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BurstDensity</strong></p></td>
<td><p>10進数 (9、4)</p></td>
<td><p> </p></td>
<td><p>通話中のバースト損失中のパケット損失の平均密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>BurstDuration</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>通話時の損失のバーストで発生したパケット損失の平均期間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BurstGapDensity</strong></p></td>
<td><p>10進数 (9、4)</p></td>
<td><p> </p></td>
<td><p>パケット損失のバーストが発生して次のバーストが発生するまでの間に発生したパケット損失の平均密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>BurstGapDuration</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>パケット損失のバーストが発生して次のバーストが発生するまでの平均期間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>音声ストリームのパケット数。</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEst</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>音声ストリームの帯域幅の推定。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DegradationAvg</strong></p></td>
<td><p>10進数 (3、2)</p></td>
<td><p> </p></td>
<td><p>通話全体でのネットワーク MOS の低下。範囲は 0.0 ～ 5.0 です。この指標は、ジッターとパケット損失に起因する、ネットワーク MOS の低下量を示します。許容範囲に収まる程度の品質を維持するには、この値は 0.5 未満である必要があります。</p></td>
</tr>
<tr class="even">
<td><p><strong>DegradationMax</strong></p></td>
<td><p>10進数 (3、2)</p></td>
<td><p> </p></td>
<td><p>通話時のネットワーク MOS の最大低下。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DegradationJitterAvg</strong></p></td>
<td><p>10進数 (3、2)</p></td>
<td><p> </p></td>
<td><p>ジッターに起因するネットワーク MOS の低下。</p></td>
</tr>
<tr class="even">
<td><p><strong>DegradationPacketLossAvg</strong></p></td>
<td><p>10進数 (3、2)</p></td>
<td><p> </p></td>
<td><p>パケット損失に起因するネットワーク MOS の低下。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioPayloadDescription</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>呼び出しに使用されるオーディオコーデック (PayloadDescription テーブルから参照)。</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioSampleRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>音声ストリームのサンプリング レート。</p></td>
</tr>
<tr class="odd">
<td><p><strong>要し</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>RTCP 統計情報に基づく往復時間。 許容できる品質を得るには、これは100ミリ秒より小さくなければなりません。</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>音声ストリームの最大往復時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OverallAvgNetworkMOS</strong></p></td>
<td><p>10進数 (3、2)</p></td>
<td><p> </p></td>
<td><p>通話の広帯域ネットワーク MOS の平均値。 この指標は、パケット損失、ジッター、および使用されるコーデックによって異なります。 範囲は、[1.0 ~ 5.0] です。</p></td>
</tr>
<tr class="even">
<td><p><strong>OverallMinNetworkMOS</strong></p></td>
<td><p>10進数 (3、2)</p></td>
<td><p> </p></td>
<td><p>通話の広帯域ネットワーク MOS の最小値。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendListenMOS</strong></p></td>
<td><p>10進数 (3、2)</p></td>
<td><p> </p></td>
<td><p>音声レベル、ノイズレベル、キャプチャデバイス特性など、送信される音声の広帯域リスニング MOS スコアの平均予測値。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendListenMOSMin</strong></p></td>
<td><p>10進数 (3、2)</p></td>
<td><p> </p></td>
<td><p>通話の最小 SendListenMOS。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvListenMOS</strong></p></td>
<td><p>10進数 (3、2)</p></td>
<td><p> </p></td>
<td><p>音声レベル、ノイズレベル、コーデック、ネットワーク条件、キャプチャデバイス特性など、ネットワークから受信した音声の広帯域リスニング MOS スコアの平均予測値。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvListenMOSMin</strong></p></td>
<td><p>10進数 (3、2)</p></td>
<td><p> </p></td>
<td><p>通話の最小 RecvListenMOS。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioFECUsed</strong></p></td>
<td><p>若干</p></td>
<td></td>
<td><p>通話にオーディオ FEC が使用されたかどうかを示すフラグ。</p></td>
</tr>
<tr class="even">
<td><p><strong>RatioConcealedSamplesAvg</strong></p></td>
<td><p>10進数 (5、2)</p></td>
<td></td>
<td><p>標準サンプルへの音声復旧によって生成される隠しサンプルの平均比率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RatioStretchedSamplesAvg</strong></p></td>
<td><p>10進数 (5、2)</p></td>
<td></td>
<td><p>標準サンプルへの音声復旧によって生成される引き伸ばしサンプルの平均比率。</p></td>
</tr>
<tr class="even">
<td><p><strong>RatioCompressedSamplesAvg</strong></p></td>
<td><p>10進数 (5、2)</p></td>
<td></td>
<td><p>標準サンプルへの音声復旧によって生成される圧縮サンプルの平均比率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>受信</strong></p></td>
<td><p>若干</p></td>
<td><p> </p></td>
<td><p>受信側のストリームデータが受信されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>向き</strong></p></td>
<td><p>若干</p></td>
<td><p> </p></td>
<td><p>送信側のストリームデータが受信されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>若干</p></td>
<td><p> </p></td>
<td><p>1は、ストリームの方向が発信者から呼び出し先へ向かうことを意味します。</p>
<p>0 は、ストリームの方向が呼び出し先から発信者へ向かうことを意味します。</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalSD</strong></p></td>
<td><p>浮動小数点数</p></td>
<td></td>
<td><p>ジッタ到着時間の標準偏差。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConcealRatioMax</strong></p></td>
<td><p>浮動小数点数</p></td>
<td></td>
<td><p>ヒーラーによる隠しパケットの最大比率。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConcealRatioSD</strong></p></td>
<td><p>浮動小数点数</p></td>
<td></td>
<td><p>ヒーラーによって隠されたパケットの比率の標準偏差。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>HealerPacketDropRatio</strong></p></td>
<td><p>浮動小数点数</p></td>
<td></td>
<td><p>受信したパケットの合計数と比較して、ヒーラーによって削除されたパケットの比率。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>HealerFECPacketUsedRatio</strong></p></td>
<td><p>浮動小数点数</p></td>
<td></td>
<td><p>受信したパケットの合計数に対する、使用された転送エラー訂正パケットの比率。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MaxCompressedSamples</strong></p></td>
<td><p>浮動小数点数</p></td>
<td></td>
<td><p>ヒーラーによって圧縮されたオーディオパケットの最大数。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>LossCongestionPercent</strong></p></td>
<td><p>浮動小数点数</p></td>
<td></td>
<td><p>通話が切断された輻輳状態であった時間の割合を示します。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DelayCongestionPercent</strong></p></td>
<td><p>浮動小数点数</p></td>
<td></td>
<td><p>ネットワークパケットの遅延到着により輻輳が発生した通話の割合を示します。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentionDetectedPercent</strong></p></td>
<td><p>浮動小数点数</p></td>
<td></td>
<td><p>通話がネットワークリソースに対して競合していた時間の割合を示します。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstMin</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>呼び出し中に測定された最小帯域幅推定値。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>呼び出し中に測定された最大帯域幅推定値。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstStdDev</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>呼び出し中に測定された帯域幅推定の標準偏差。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstAvge</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>呼び出し中に測定された平均帯域幅推定値。</p>
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
<td><p>浮動小数点数</p></td>
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
<td><p><strong>DecodeStereoPercent</strong></p></td>
<td><p>浮動小数点数</p></td>
<td></td>
<td><p>ステレオとしてデコードされた通話のパーセンテージ。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AecRenderStereoPercent</strong></p></td>
<td><p>浮動小数点数</p></td>
<td></td>
<td><p>音響エコーキャンセラでステレオとしてレンダリングされた通話のパーセンテージ。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioPostFECPLR</strong></p></td>
<td><p>浮動小数点数</p></td>
<td></td>
<td><p>転送エラー訂正が適用された後のパケット損失率。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EncodeStereoPercent</strong></p></td>
<td><p>浮動小数点数</p></td>
<td></td>
<td><p>ステレオとしてエンコードされた通話のパーセンテージ。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
<tr class="even">
<td><p><strong>AecCaptureStereoPercent</strong></p></td>
<td><p>浮動小数点数</p></td>
<td></td>
<td><p>音響エコーキャンセラでステレオとしてキャプチャされた通話のパーセンテージ。</p>
<p>このコラムは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

