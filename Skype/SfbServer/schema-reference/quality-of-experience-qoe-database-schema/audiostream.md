---
title: AudioStream テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
description: 各レコードは、1 つのオーディオ ストリームを表します。 1 つのオーディオ メディア ラインには、通常、2 つのオーディオ ストリームが含まれる。
ms.openlocfilehash: e24a5c8611c3f6bf7b56edf342aa2595f6794a90
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831367"
---
# <a name="audiostream-table"></a>AudioStream テーブル
 
各レコードは、1 つのオーディオ ストリームを表します。 通常、1 つのオーディオ メディア ラインには 2 つのオーディオ ストリームが含まれる。
  
|Column|データ型|キー/インデックス|詳細|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |日付型  <br/> |Primary  <br/> |[MediaLine テーブルから参照されます](medialine-0.md)。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |[MediaLine テーブルから参照されます](medialine-0.md)。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |[MediaLine テーブルから参照されます](medialine-0.md)。  <br/> |
|**StreamID** <br/> |int  <br/> |Primary  <br/> |メディア ライン内の一意の ID。  <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |リアルタイム制御プロトコル (RTCP) 統計情報に基づく平均ネットワーク ジッター。  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |通話時の最大ネットワーク ジッター。  <br/> |
|**PacketLossRate** <br/> |decimal(5,4)  <br/> | <br/> |通話時の平均パケット損失率。  <br/> |
|**PacketLossRateMax** <br/> |decimal(5,4)  <br/> | <br/> |通話時に観測された最大パケット損失。  <br/> |
|**BurstDensity** <br/> |decimal(9,4)  <br/> | <br/> |通話中のバースト損失時のパケット損失の平均密度。  <br/> |
|**BurstDuration** <br/> |int  <br/> | <br/> |通話時の損失のバーストで発生したパケット損失の平均期間。  <br/> |
|**BurstGapDensity** <br/> |decimal(9,4)  <br/> | <br/> |パケット損失のバーストが発生して次のバーストが発生するまでの間に発生したパケット損失の平均密度。  <br/> |
|**BurstGapDuration** <br/> |int  <br/> | <br/> |パケット損失のバーストが発生して次のバーストが発生するまでの平均期間。  <br/> |
|**PacketUtilization** <br/> |Int  <br/> | <br/> |音声ストリームのパケット数。  <br/> |
|**BandwidthEst** <br/> |Int  <br/> | <br/> |音声ストリームの帯域幅の推定。  <br/> |
|**DegradationAvg** <br/> |decimal(3,2)  <br/> | <br/> |通話全体でのネットワーク MOS の低下。範囲は 0.0 ～ 5.0 です。この指標は、ジッターとパケット損失に起因する、ネットワーク MOS の低下量を示します。許容範囲に収まる程度の品質を維持するには、この値は 0.5 未満である必要があります。  <br/> |
|**DegradationMax** <br/> |decimal(3,2)  <br/> | <br/> |通話時のネットワーク MOS の最大低下。  <br/> |
|**DegradationJitterAvg** <br/> |decimal(3,2)  <br/> | <br/> |ジッターに起因するネットワーク MOS の低下。  <br/> |
|**DegradationPacketLossAvg** <br/> |decimal(3,2)  <br/> | <br/> |パケット損失に起因するネットワーク MOS の低下。  <br/> |
|**AudioPayloadDescription** <br/> |int  <br/> |外部  <br/> |PayloadDescription テーブルから参照される、呼び出しに使用されるオーディオ コーデック。  <br/> |
|**AudioSampleRate** <br/> |int  <br/> | <br/> |音声ストリームのサンプリング レート。  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |RTCP 統計情報に基づく往復時間。 許容できる品質のために、これは 100ms 未満である必要があります。  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |音声ストリームの最大往復時間。  <br/> |
|**OverallAvgNetworkMOS** <br/> |decimal(3,2)  <br/> | <br/> |通話の広帯域ネットワーク MOS の平均値。 この指標は、パケット損失、ジッター、および使用されるコーデックによって異なります。 範囲は [1.0 ~ 5.0] です。  <br/> |
|**OverallMinNetworkMOS** <br/> |decimal(3,2)  <br/> | <br/> |通話の最小広帯域ネットワーク MOS。  <br/> |
|**SendListenMOS** <br/> |decimal(3,2)  <br/> | <br/> |音声レベル、ノイズ レベル、キャプチャ デバイス特性など、送信される音声の広帯域リスニング MOS スコアの平均予測値。  <br/> |
|**SendListenMOSMin** <br/> |decimal(3,2)  <br/> | <br/> |呼び出しの最小 SendListenMOS。  <br/> |
|**RecvListenMOS** <br/> |decimal(3,2)  <br/> | <br/> |音声レベル、ノイズ レベル、コーデック、ネットワーク状態、キャプチャ デバイス特性など、ネットワークから受信した音声の、予測される広帯域リスニング MOS スコアの平均。  <br/> |
|**RecvListenMOSMin** <br/> |decimal(3,2)  <br/> | <br/> |呼び出しの最小 RecvListenMOS。  <br/> |
|**AudioFECUsed** <br/> |bit  <br/> ||通話に音声 FEC が使用されたかどうかを示すフラグ。  <br/> |
|**RatioConcealedSamplesAvg** <br/> |decimal(5,2)  <br/> ||標準サンプルへの音声復旧によって生成される隠しサンプルの平均比率。  <br/> |
|**RatioStretchedSamplesAvg** <br/> |decimal(5,2)  <br/> ||標準サンプルへの音声復旧によって生成される引き伸ばしサンプルの平均比率。  <br/> |
|**RatioCompressedSamplesAvg** <br/> |decimal(5,2)  <br/> ||標準サンプルへの音声復旧によって生成される圧縮サンプルの平均比率。  <br/> |
|**受信** <br/> |bit  <br/> | <br/> |受信側のストリーム データが受信されます。  <br/> |
|**送信** <br/> |bit  <br/> | <br/> |送信者側のストリーム データが受信されます。  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 は、ストリームの方向が呼び出し元から呼び出し先への方向を意味します。  <br/> 0 は、ストリームの方向が呼び出し先から発信者へ向かうことを意味します。  <br/> |
|**JitterInterArrivalSD** <br/> |浮動小数点数  <br/> ||ジッターの到着時間の標準偏差。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**ConcealRatioMax** <br/> |浮動小数点数  <br/> ||ヒーラーによって隠されるパケットの最大比率。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**ConcealRatioSD** <br/> |浮動小数点数  <br/> ||ヒーラーによって隠されるパケットの比率に対する標準偏差。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**HealerPacketDropRatio** <br/> |浮動小数点数  <br/> ||ヒーラーによって破棄されたパケットの比率と受信したパケットの総数との比較。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**HealerFECPacketUsedRatio** <br/> |浮動小数点数  <br/> ||受信したパケットの総数と比較した、前方エラー修正パケットの使用比率。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**MaxCompressedSamples** <br/> |浮動小数点数  <br/> ||ヒーラーによって圧縮されたオーディオ パケットの最大数。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**LossCongestionPercent** <br/> |浮動小数点数  <br/> ||通話が輻輳状態で失われる時間の割合を示します。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**DelayCongestionPercent** <br/> |浮動小数点数  <br/> ||ネットワーク パケットの遅延到着によって輻輳が発生した通話の割合を示します。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**ContentionDetectedPercent** <br/> |浮動小数点数  <br/> ||通話がネットワーク リソースと競合している時間の割合を示します。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||通話中に測定される最小帯域幅予測値。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||通話中に測定される最大帯域幅予測値。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||通話中に測定された帯域幅予測の標準偏差。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||通話中に測定された帯域幅予測の平均量。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayTotal** <br/> |浮動小数点数  <br/> ||一方向の遅延の合計時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayAverage** <br/> |浮動小数点数  <br/> ||一方向の遅延の平均時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayMax** <br/> |浮動小数点数  <br/> ||一方向の遅延の最大時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||一方向のバーストの合計発生数。 "バースト的な" 伝送とは、安定したストリームではなく、予測できないバーストでデータが流れ込む伝送です。 この指標では、クライアントとサーバーの間のデータ フローが測定されます。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayBurstDensity** <br/> |浮動小数点数  <br/> ||一方向のバーストの合計密度。 "バースト的な" 伝送とは、安定したストリームではなく、予測できないバーストでデータが流れ込む伝送です。 この指標では、クライアントとサーバーの間のデータ フローが測定されます。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayBurstDuration** <br/> |浮動小数点数  <br/> ||一方向のバーストの合計期間。 "バースト的な" 伝送とは、安定したストリームではなく、予測できないバーストでデータが流れ込む伝送です。 この指標では、クライアントとサーバーの間のデータ フローが測定されます。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||一方通行のギャップ発生回数の合計。 "バースト的な" 伝送とは、安定したストリームではなく、予測できないバーストでデータが流れ込む伝送です。ギャップは、これらのバースト間の遅延を示します。 この指標では、クライアントとサーバーの間のデータ フローが測定されます。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayGapDensity** <br/> |浮動小数点数  <br/> ||一方通行のギャップ密度の合計。 "バースト的な" 伝送とは、安定したストリームではなく、予測できないバーストでデータが流れ込む伝送です。ギャップは、これらのバースト間の遅延を示します。 この指標では、クライアントとサーバーの間のデータ フローが測定されます。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayGapDuration** <br/> |浮動小数点数  <br/> ||一方通行のギャップ期間の合計。 "バースト的な" 伝送とは、安定したストリームではなく、予測できないバーストでデータが流れ込む伝送です。ギャップは、これらのバースト間の遅延を示します。 この指標では、クライアントとサーバーの間のデータ フローが測定されます。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**DecodeStereoPercent** <br/> |浮動小数点数  <br/> ||ステレオとしてデコードされた通話のパーセンテージ。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**AecRenderStereoPercent** <br/> |浮動小数点数  <br/> ||アコースティック エコー キャンセルによってステレオとしてレンダリングされた通話の割合。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**AudioPostFECPLR** <br/> |浮動小数点数  <br/> ||前方エラー修正が適用された後のパケット損失率。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**EncodeStereoPercent** <br/> |浮動小数点数  <br/> ||ステレオとしてエンコードされた通話のパーセンテージ。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**AecCaptureStereoPercent** <br/> |浮動小数点数  <br/> ||アコースティック エコー キャンセルによってステレオとしてキャプチャされた通話のパーセンテージ。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
