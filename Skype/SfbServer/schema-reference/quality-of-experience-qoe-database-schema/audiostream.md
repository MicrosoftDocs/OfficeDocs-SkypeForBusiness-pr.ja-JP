---
title: AudioStream テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
description: 各レコードは1つのオーディオストリームを表します。 通常、1つのオーディオメディアラインには2つのオーディオストリームが含まれています。
ms.openlocfilehash: 265125202de25da4c6e653ecd53bd465f9a5472b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810435"
---
# <a name="audiostream-table"></a>AudioStream テーブル
 
各レコードは1つのオーディオストリームを表します。 通常、1つのオーディオメディアラインには2つのオーディオストリームが含まれています。
  
|列|データ型|キー/インデックス|詳細|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |[MediaLine テーブル](medialine-0.md)から参照されます。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |[MediaLine テーブル](medialine-0.md)から参照されます。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |[MediaLine テーブル](medialine-0.md)から参照されます。  <br/> |
|**StreamID** <br/> |int  <br/> |Primary  <br/> |メディアライン内の一意の ID。  <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |リアルタイム制御プロトコル (RTCP) の統計情報からの平均ネットワークジッター。  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |通話中の最大ネットワークジッター。  <br/> |
|**PacketLossRate** <br/> |10進数 (5, 4)  <br/> | <br/> |通話中の平均パケット損失率。  <br/> |
|**PacketLossRateMax** <br/> |10進数 (5, 4)  <br/> | <br/> |通話中に発生したパケット損失の上限。  <br/> |
|**BurstDensity** <br/> |10進数 (9, 4)  <br/> | <br/> |通話中に損失が発生した場合のパケット損失の平均密度。  <br/> |
|**BurstDuration** <br/> |int  <br/> | <br/> |通話中に損失が発生したときのパケット損失の平均時間。  <br/> |
|**BurstGapDensity** <br/> |10進数 (9, 4)  <br/> | <br/> |パケット損失のバースト間のパケット損失の平均密度。  <br/> |
|**BurstGapDuration** <br/> |int  <br/> | <br/> |パケット損失のバーストの間の平均時間差。  <br/> |
|**PacketUtilization** <br/> |Int  <br/> | <br/> |オーディオストリームのパケット数。  <br/> |
|**BandwidthEst** <br/> |Int  <br/> | <br/> |オーディオストリームの帯域幅の推定。  <br/> |
|**DegradationAvg** <br/> |10進数 (3, 2)  <br/> | <br/> |電話全体のネットワーク MOS が低下します。 範囲は 0.0 ~ 5.0 です。 このメトリックは、ジッタとパケット損失によってネットワーク MOS が削減された量を示します。 許容可能な品質には、0.5 未満の値を指定する必要があります。  <br/> |
|**DegradationMax** <br/> |10進数 (3, 2)  <br/> | <br/> |通話中の最大ネットワーク MOS の品質低下。  <br/> |
|**DegradationJitterAvg** <br/> |10進数 (3, 2)  <br/> | <br/> |ジッターによるネットワーク MOS の低下。  <br/> |
|**DegradationPacketLossAvg** <br/> |10進数 (3, 2)  <br/> | <br/> |パケット損失によるネットワーク MOS の低下。  <br/> |
|**AudioPayloadDescription** <br/> |int  <br/> |外部  <br/> |PayloadDescription テーブルから参照される、通話に使われるオーディオコーデック。  <br/> |
|**AudioSampleRate** <br/> |int  <br/> | <br/> |オーディオストリームのサンプリングレート。  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |RTCP の統計情報からのラウンドトリップ時間。 許容可能な品質の場合は、100ms 未満にしてください。  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |オーディオストリームの最大ラウンドトリップ時間。  <br/> |
|**OverallAvgNetworkMOS** <br/> |10進数 (3, 2)  <br/> | <br/> |通話の平均広帯域ネットワーク MOS。 このメトリックは、使用されているパケット損失、ジッタ、およびコーデックによって異なります。 範囲は [1.0 から 5.0] になります。  <br/> |
|**OverallMinNetworkMOS** <br/> |10進数 (3, 2)  <br/> | <br/> |通話の最小広帯域ネットワーク MOS。  <br/> |
|**SendListenMOS** <br/> |10進数 (3, 2)  <br/> | <br/> |送信された音声の平均予測広帯域 MOS score (音声レベル、ノイズレベル、キャプチャデバイスの特性を含む)。  <br/> |
|**SendListenMOSMin** <br/> |10進数 (3, 2)  <br/> | <br/> |通話の最小 SendListenMOS。  <br/> |
|**RecvListenMOS** <br/> |10進数 (3, 2)  <br/> | <br/> |予測される平均広帯域は、ネットワークから受信した音声の MOS スコア (音声レベル、ノイズレベル、コーデック、ネットワーク条件、キャプチャデバイスの特性など) を対象としています。  <br/> |
|**RecvListenMOSMin** <br/> |10進数 (3, 2)  <br/> | <br/> |通話の最小 RecvListenMOS。  <br/> |
|**AudioFECUsed** <br/> |bit  <br/> ||通話にオーディオ FEC が使用されたかどうかを示すフラグ。  <br/> |
|**RatioConcealedSamplesAvg** <br/> |10進数 (5, 2)  <br/> ||オーディオの修復によって発生した、一般的なサンプルの平均比率。  <br/> |
|**RatioStretchedSamplesAvg** <br/> |10進数 (5, 2)  <br/> ||オーディオ修復によって生成された、一般的なサンプルの平均比率。  <br/> |
|**RatioCompressedSamplesAvg** <br/> |10進数 (5, 2)  <br/> ||オーディオの修復によって生成された、一般的なサンプルの圧縮サンプルの平均比率。  <br/> |
|**トラフィック** <br/> |bit  <br/> | <br/> |受信側のストリームデータが受信されます。  <br/> |
|**発信** <br/> |bit  <br/> | <br/> |送信側のストリームデータが受信されます。  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1は、ストリームの方向を呼び出し元から呼び出し先に転送することを意味します。  <br/> 0は、ストリームの方向を呼び出し元から呼び出し元に転送します。  <br/> |
|**JitterInterArrivalSD** <br/> |float  <br/> ||ジッタの到着時刻の標準偏差。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**ConcealRatioMax** <br/> |float  <br/> ||Healer によって隠されているパケットの最大比率。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**ConcealRatioSD** <br/> |float  <br/> ||Healer によって隠されているパケットの比率の標準偏差。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**HealerPacketDropRatio** <br/> |float  <br/> ||受信したパケットの合計数と比較して、healer によってドロップされたパケットの比率。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**HealerFECPacketUsedRatio** <br/> |float  <br/> ||受信したパケットの合計数と比較した、使用された転送エラー修正パケットの比率。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**MaxCompressedSamples** <br/> |float  <br/> ||Healer によって圧縮されたオーディオパケットの最大数。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||通話が切断された輻輳状態であった時間の割合を示します。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||ネットワークパケットが遅延したために発生した、通話の割合を示します。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||通話がネットワークリソースに対して競合した時間の割合を示します。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||通話中の最小帯域幅推定値。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||通話中に測定された帯域幅推定の最大量。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||通話中に測定された帯域幅推定の標準偏差。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||通話中に計測された平均帯域幅推定量。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||一方向の待機時間の合計。 相対的な一方向の待ち時間は、クライアントとサーバーの間の遅延を測定します。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||一方向の待ち時間の平均値。 相対的な一方向の待ち時間は、クライアントとサーバーの間の遅延を測定します。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||一方向の待機時間の上限。 相対的な一方向の待ち時間は、クライアントとサーバーの間の遅延を測定します。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||1方向のバースト発生の合計。 "Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。 このメトリックは、クライアントとサーバー間のデータフローを計測します。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||全体的な1方向バースト密度。 "Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。 このメトリックは、クライアントとサーバー間のデータフローを計測します。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||一方向のバースト期間の合計。 "Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。 このメトリックは、クライアントとサーバー間のデータフローを計測します。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||一方向のギャップ出現の合計。 "Bursty" 伝送とは、安定したストリームではなく、予期しないバーストでデータが流れる伝送です。ギャップは、このようなバーストの間の遅延を示します。 このメトリックは、クライアントとサーバー間のデータフローを計測します。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||一方向のギャップの密度の合計。 "Bursty" 伝送とは、安定したストリームではなく、予期しないバーストでデータが流れる伝送です。ギャップは、このようなバーストの間の遅延を示します。 このメトリックは、クライアントとサーバー間のデータフローを計測します。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||一方向のギャップ期間の合計。 "Bursty" 伝送とは、安定したストリームではなく、予期しないバーストでデータが流れる伝送です。ギャップは、このようなバーストの間の遅延を示します。 このメトリックは、クライアントとサーバー間のデータフローを計測します。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**DecodeStereoPercent** <br/> |float  <br/> ||ステレオとしてデコードされた通話のパーセンテージ。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**AecRenderStereoPercent** <br/> |float  <br/> ||アコースティックエコーキャンセラによってステレオとしてレンダリングされた通話の割合。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**AudioPostFECPLR** <br/> |float  <br/> ||転送後のエラー訂正が適用された後のパケット損失率。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**EncodeStereoPercent** <br/> |float  <br/> ||ステレオとしてエンコードされた通話の割合。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**AecCaptureStereoPercent** <br/> |float  <br/> ||アコースティックエコーキャンセラでステレオとしてキャプチャされた通話のパーセンテージ。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
