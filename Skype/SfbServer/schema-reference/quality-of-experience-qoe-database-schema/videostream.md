---
title: VideoStream テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
description: 各レコードは、1 つのビデオ ストリームを表します。 通常、1 つのビデオ メディア ラインには 2 つのビデオ ストリームが含まれる。
ms.openlocfilehash: e506f022dbfa4ef0a1a8578dc6caf7c0f3984fa6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821327"
---
# <a name="videostream-table"></a>VideoStream テーブル
 
各レコードは、1 つのビデオ ストリームを表します。 通常、1 つのビデオ メディア ラインには 2 つのビデオ ストリームが含まれる。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |日付型  <br/> |Primary  <br/> |[MediaLine テーブルから参照されます](medialine-0.md)。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |R [MediaLine テーブルから参照されます](medialine-0.md)。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |[MediaLine テーブルから参照されます](medialine-0.md)。  <br/> |
|**StreamID** <br/> |int  <br/> |Primary  <br/> |メディア ライン内の一意の ID。  <br/> |
|**VideoPayloadDescription** <br/> |smallint  <br/> |外部、プライマリ  <br/> |ペイロードの説明。 詳細については [、PayloadDescription の表](payloaddescription.md) を参照してください。 <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |リアルタイム制御プロトコル (RTCP) 統計情報に基づく平均ネットワーク ジッター。  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |ビデオ セッション中の最大ネットワーク ジッター。  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |RTCP 統計情報に基づく往復時間。  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |ビデオ ストリームの最大ラウンド トリップ時間。  <br/> |
|**PacketLossRate** <br/> |decimal(5,4)  <br/> | <br/> |通話時の平均パケット損失率。  <br/> |
|**PacketLossRateMax** <br/> |decimal(5,4)  <br/> | <br/> |通話時に観測された最大パケット損失。  <br/> |
|**PacketUtilization** <br/> |int  <br/> | <br/> |ビデオ ストリームのパケット数 (リアルタイム転送プロトコル、RTP)。  <br/> |
|**BandwidthEst** <br/> |int  <br/> | <br/> |ビデオ ストリームの帯域幅の推定値。  <br/> |
|**VideoResolution** <br/> |char(9)  <br/> | <br/> |幅×高さで示すビデオの解像度 (単位ピクセル)。文字列で報告されます。  <br/> |
|**VideoBitRateAvg** <br/> |int  <br/> | <br/> |ビデオ ストリームの平均ビット レート。  <br/> |
|**InboundVideoFrameRateAvg** <br/> |decimal(9,4)  <br/> | <br/> |受信したビデオ フレーム レート。  <br/> |
|**OutboundVideoFrameRateAvg** <br/> |decimal(9,4)  <br/> | <br/> |送信されるビデオ フレーム レート。  <br/> |
|**VideoBitRateMax** <br/> |int  <br/> | <br/> |ビデオ セッション中の最大ビデオ ビット レート。  <br/> |
|**VideoFrameLossRate** <br/> |decimal(9,4)  <br/> | <br/> |失われたビデオ フレームの合計の割合。  <br/> |
|**VideoFEC** <br/> |bit  <br/> | <br/> |注意事項なし。  <br/> |
|**VideoLocalFrameLossPercentageAvg** <br/> |decimal(9,4)  <br/> ||失われたビデオ フレームの合計の割合。  <br/> |
|**CIFQualityRatio** <br/> |tinyint  <br/> ||共通交換形式 (CIF) 解決での通話の割合。  <br/> |
|**VGAQualityRatio** <br/> |tinyint  <br/> ||VGA 解決時の通話の割合。  <br/> |
|**HD720QualityRatio** <br/> |tinyint  <br/> ||HD720 解像度での通話の割合。  <br/> |
|**NoneDropRatio** <br/> |tinyint  <br/> ||フレーム ドロップがない通話時間の割合。  <br/> |
|**BDropRatio** <br/> |tinyint  <br/> ||B フレーム ドロップでの通話時間の割合。  <br/> |
|**BPDropRatio** <br/> |tinyint  <br/> ||BP フレーム ドロップでの通話時間の割合。  <br/> |
|**BPSPDropRatio** <br/> |tinyint  <br/> ||BPSP フレーム ドロップでの通話時間の割合。  <br/> |
|**BPSPIDropRatio** <br/> |tinyint  <br/> ||BPSPI フレーム ドロップでの通話時間の割合。  <br/> |
|**受信** <br/> |bit  <br/> | <br/> |受信側のストリーム データが受信されます。  <br/> |
|**送信** <br/> |bit  <br/> | <br/> |送信者側のストリーム データが受信されます。  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 は、ストリームの方向が発信者から呼び出し先へ向かうことを意味します。  <br/> 0 は、ストリームの方向が呼び出し先から発信者へ向かうことを意味します。  <br/> |
|**LossCongestionPercent** <br/> |浮動小数点数  <br/> ||通話が輻輳状態で失われる時間の割合を示します。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**DelayCongestionPercent** <br/> |浮動小数点数  <br/> ||ネットワーク パケットの遅延到着によって輻輳が発生した通話の割合を示します。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**ContentionDetectedPercent** <br/> |浮動小数点数  <br/> ||通話がネットワーク リソースと競合している時間の割合を示します。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||通話中に測定される最小帯域幅予測値。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||通話中に測定される最大帯域幅予測値。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||通話中に測定された帯域幅予測の標準偏差。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||通話中に測定された帯域幅予測の平均量。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**LowBandwidthForMultiview** <br/> |浮動小数点数  <br/> ||エンドポイントがネットワーク接続がマルチビュー ビデオをサポートできないと判断した通話のパーセンテージ。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayTotal** <br/> |浮動小数点数  <br/> ||一方向の遅延の合計時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayAverage** <br/> |浮動小数点数  <br/> ||一方向の遅延の平均時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayMax** <br/> |浮動小数点数  <br/> ||一方向の遅延の最大時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||一方向のバーストの合計発生数。 "バースト的な" 伝送とは、安定したストリームではなく、予測できないバーストでデータが流れ込む伝送です。 この指標では、クライアントとサーバーの間のデータ フローが測定されます。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayBurstDensity** <br/> |int  <br/> ||一方向のバーストの合計密度。 "バースト的な" 伝送とは、安定したストリームではなく、予測できないバーストでデータが流れ込む伝送です。 この指標では、クライアントとサーバーの間のデータ フローが測定されます。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayBurstDuration** <br/> |浮動小数点数  <br/> ||一方向のバーストの合計期間。 "バースト的な" 伝送とは、安定したストリームではなく、予測できないバーストでデータが流れ込む伝送です。 この指標では、クライアントとサーバーの間のデータ フローが測定されます。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||一方通行のギャップ発生回数の合計。 "バースト的な" 伝送とは、安定したストリームではなく、予測できないバーストでデータが流れ込む伝送です。ギャップは、これらのバースト間の遅延を示します。 この指標では、クライアントとサーバーの間のデータ フローが測定されます。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayGapDensity** <br/> |浮動小数点数  <br/> ||一方通行のギャップ密度の合計。 "バースト的な" 伝送とは、安定したストリームではなく、予測できないバーストでデータが流れ込む伝送です。ギャップは、これらのバースト間の遅延を示します。 この指標では、クライアントとサーバーの間のデータ フローが測定されます。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayGapDuration** <br/> |浮動小数点数  <br/> ||一方通行のギャップ期間の合計。 "バースト的な" 伝送とは、安定したストリームではなく、予測できないバーストでデータが流れ込む伝送です。ギャップは、これらのバースト間の遅延を示します。 この指標では、クライアントとサーバーの間のデータ フローが測定されます。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**VideoPacketLossRate** <br/> |decimal(9,4)  <br/> ||失われたビデオ パケット数の割合。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**VideoAllocateBWAvg** <br/> |int  <br/> ||ビデオに割り当てられた帯域幅の平均。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SendCodecTypes** <br/> |smallint  <br/> |外部  <br/> |送信者が使用するビデオ コーデックの種類。 詳しくは [、CodecDescription の表](codecdescription.md) をご覧ください。 <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SendResolutionWidth** <br/> |int  <br/> ||送信者が使用する解像度の幅。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SendResolutionHeight** <br/> |int  <br/> ||送信者が使用する解像度の高さ。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SendFrameRateAverage** <br/> |浮動小数点数  <br/> ||送信者が使用する平均ビデオ フレーム レート転送。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SendBitRateMaximum** <br/> |int  <br/> ||送信者の最大ビット レート。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SendBitRateAverage** <br/> |int  <br/> ||送信者の平均ビット レート。  <br/> |
|**SendVideoStreamsMax** <br/> |int  <br/> ||送信者が使用するビデオ ストリームの最大数。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RecvCodecTypes** <br/> |smallint  <br/> |外部  <br/> |レシーバーによって使用されるビデオ コード。 詳しくは [、CodecDescription の表](codecdescription.md) をご覧ください。 <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RecvResolutionWidth** <br/> |int  <br/> ||レシーバーで使用される解像度の幅。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RecvResolutionHeight** <br/> |int  <br/> ||レシーバーで使用される解像度の高さ。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RecvFrameRateAverage** <br/> |浮動小数点数  <br/> ||レシーバーが使用する平均ビデオ フレーム レート。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RecvBitRateMaximum** <br/> |int  <br/> ||レシーバーの最大ビット レート。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RecvBitRateAverage** <br/> |int  <br/> ||レシーバの平均ビット レート。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RecvVideoStreamsMax** <br/> |int  <br/> ||レシーバーの最大ビデオ ストリーム。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RecvVideoStreamsMin** <br/> |int  <br/> ||レシーバーの最小ビデオ ストリーム。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RecvVideoStreamsMode** <br/> |int  <br/> ||レシーバーのビデオ モード (ギャラリーや単一ストリームなど)。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**VideoPostFECPLR** <br/> |浮動小数点数  <br/> ||前方エラー修正が適用された後のパケット損失率。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**DynamicCapabilityPercent** <br/> |浮動小数点数  <br/> ||動的機能フラグがアクティブだった時間の割合。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**ResolutionMin** <br/> |char(9)  <br/> ||通話中に測定される最小解像度。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**LowBitRateCallPercent** <br/> |浮動小数点数  <br/> ||低ビット レートしきい値 (70 キロビット/秒) を下回る通話のパーセンテージ。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**LowFrameRateCallPercent** <br/> |浮動小数点数  <br/> ||低フレーム レートしきい値 (1 秒あたり 7.5 フレーム、受信) を下回る通話のパーセンテージ。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**LowResolutionCallPercent** <br/> |浮動小数点数  <br/> ||最も低い解像度で発生した通話のパーセンテージ。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**DurationSeconds** <br/> |浮動小数点数  <br/> ||呼び出しの長さ (秒)。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**IsAggregatedData** <br/> |bit  <br/> ||データが複数の呼び出しから集計されたかどうかを示します。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
   

