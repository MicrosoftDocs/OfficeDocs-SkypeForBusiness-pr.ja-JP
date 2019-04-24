---
title: VideoStream テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
description: 各レコードは、1 つのビデオ ストリームを表します。 通常、1 つのビデオ メディア ラインには、2 つのビデオ ストリームが含まれています。
ms.openlocfilehash: d6eeeb96acc766859d6b57594bd11a5538593da3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212019"
---
# <a name="videostream-table"></a>VideoStream テーブル
 
各レコードは、1 つのビデオ ストリームを表します。 通常、1 つのビデオ メディア ラインには、2 つのビデオ ストリームが含まれています。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |[MediaLine テーブル](medialine-0.md)から参照されています。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |R は、 [MediaLine テーブル](medialine-0.md)から参照されています。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |[MediaLine テーブル](medialine-0.md)から参照されています。  <br/> |
|**StreamID** <br/> |int  <br/> |Primary  <br/> |メディア ライン内で一意の ID。  <br/> |
|**VideoPayloadDescription** <br/> |smallint  <br/> |外部、主  <br/> |ペイロードの説明です。 詳細については、 [PayloadDescription テーブル](payloaddescription.md)を参照してください。 <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |リアルタイム制御プロトコル (RTCP) 統計情報のネットワークの平均ジッター。  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |ビデオ ・ セッション中に最大ネットワーク ジッター。  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |RTCP の統計情報のラウンド トリップ時間です。  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |ビデオ ストリームの最大のラウンド トリップ時間です。  <br/> |
|**PacketLossRate** <br/> |decimal(5,4)  <br/> | <br/> |呼び出し時に平均パケット損失の割合です。  <br/> |
|**PacketLossRateMax** <br/> |decimal(5,4)  <br/> | <br/> |最大のパケット損失が呼び出し中に発生します。  <br/> |
|**PacketUtilization** <br/> |int  <br/> | <br/> |(リアルタイム トランスポート プロトコル、RTP) は、ビデオ ストリームのパケット数です。  <br/> |
|**BandwidthEst** <br/> |int  <br/> | <br/> |ビデオ ストリームの帯域幅を推定します。  <br/> |
|**VideoResolution** <br/> |char (9)  <br/> | <br/> |ピクセルの幅をピクセル単位の高さを掛けた値でビデオの解像度です。 文字列として報告されます。  <br/> |
|**VideoBitRateAvg** <br/> |int  <br/> | <br/> |ビデオ ストリームの平均ビット レートです。  <br/> |
|**InboundVideoFrameRateAvg** <br/> |decimal(9,4)  <br/> | <br/> |ビデオのフレーム レートを受信します。  <br/> |
|**OutboundVideoFrameRateAvg** <br/> |decimal(9,4)  <br/> | <br/> |ビデオのフレーム レートを送信します。  <br/> |
|**VideoBitRateMax** <br/> |int  <br/> | <br/> |ビデオ ・ セッション中に最大のビデオ ビット レートです。  <br/> |
|**VideoFrameLossRate** <br/> |decimal(9,4)  <br/> | <br/> |失われたビデオ フレームの合計の割合。  <br/> |
|**VideoFEC** <br/> |bit  <br/> | <br/> |利用できません。  <br/> |
|**VideoLocalFrameLossPercentageAvg** <br/> |decimal(9,4)  <br/> ||失われたビデオ フレームの合計の割合。  <br/> |
|**CIFQualityRatio** <br/> |tinyint  <br/> ||一般的なインターチェンジ形式 (CIF) の解像度では、呼び出しの割合です。  <br/> |
|**VGAQualityRatio** <br/> |tinyint  <br/> ||VGA 解像度では、呼び出しの割合です。  <br/> |
|**HD720QualityRatio** <br/> |tinyint  <br/> ||HD720 の解像度では、呼び出しの割合です。  <br/> |
|**NoneDropRatio** <br/> |tinyint  <br/> ||フレーム ドロップとの通話時間の割合です。  <br/> |
|**BDropRatio** <br/> |tinyint  <br/> ||B フレームのドロップでの通話時間の割合です。  <br/> |
|**BPDropRatio** <br/> |tinyint  <br/> ||BP フレームのドロップでの通話時間の割合です。  <br/> |
|**BPSPDropRatio** <br/> |tinyint  <br/> ||BPSP フレームのドロップでの通話時間の割合です。  <br/> |
|**BPSPIDropRatio** <br/> |tinyint  <br/> ||BPSPI フレームのドロップでの通話時間の割合です。  <br/> |
|**受信** <br/> |bit  <br/> | <br/> |受信機側でのデータのストリームを受信するとします。  <br/> |
|**発信** <br/> |bit  <br/> | <br/> |送信側のデータのストリームを受信するとします。  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 は、ストリームの方向は、呼び出し元から呼び出し先を意味します。  <br/> 0 では、ストリームの方向は、呼び出し先から呼び出し元を表します。  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||損失輻輳状態にしたときの時間の割合を示します。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||輻輳が原因でネットワーク パケットの遅延到着の呼び出しの割合を示します。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||ネットワーク リソースに対する呼び出しが競合する場合の時間の割合を示します。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||帯域幅の推定量の最小値は、呼び出し中に測定されます。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||最大帯域幅の推定量は、呼び出し中に測定されます。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||帯域幅の推定標準偏差は、呼び出し中に測定されます。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||平均帯域幅の推定量は、呼び出し中に測定されます。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**LowBandwidthForMultiview** <br/> |float  <br/> ||エンドポイントがネットワーク接続がマルチビュー ビデオをサポートしていないことを確認する呼び出しの割合です。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||一方向の遅延時間の合計金額です。 相対的な一方向の遅延時間は、クライアントとサーバー間の遅延を測定します。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||一方向の遅延時間の平均量。 相対的な一方向の遅延時間は、クライアントとサーバー間の遅延を測定します。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||一方向の遅延時間の最大数。 相対的な一方向の遅延時間は、クライアントとサーバー間の遅延を測定します。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||合計の一方向のバースト発生数です。 「集中」の転送は、安定ではなく予期しない状態でのデータのフロー転送です。 このメトリックは、クライアントとサーバー間のデータ フローを測定します。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayBurstDensity** <br/> |int  <br/> ||合計の一方向のバースト密度。 「集中」の転送は、安定ではなく予期しない状態でのデータのフロー転送です。 このメトリックは、クライアントとサーバー間のデータ フローを測定します。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||合計の一方向のバーストの継続時間です。 「集中」の転送は、安定ではなく予期しない状態でのデータのフロー転送です。 このメトリックは、クライアントとサーバー間のデータ フローを測定します。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||合計の一方向のギャップの発生数です。 「集中」の転送では、転送、安定したストリームではなく予期しない状態でのデータのフローギャップは、これらのバーストの間の遅延を指定します。 このメトリックは、クライアントとサーバー間のデータ フローを測定します。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||合計の一方向のギャップ密度。 「集中」の転送では、転送、安定したストリームではなく予期しない状態でのデータのフローギャップは、これらのバーストの間の遅延を指定します。 このメトリックは、クライアントとサーバー間のデータ フローを測定します。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||合計の一方向のギャップの期間です。 「集中」の転送では、転送、安定したストリームではなく予期しない状態でのデータのフローギャップは、これらのバーストの間の遅延を指定します。 このメトリックは、クライアントとサーバー間のデータ フローを測定します。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**VideoPacketLossRate** <br/> |decimal(9,4)  <br/> ||レートが、ビデオのパケットが失われました。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**VideoAllocateBWAvg** <br/> |int  <br/> ||ビデオに割り当てられた帯域幅の平均量。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SendCodecTypes** <br/> |smallint  <br/> |外部  <br/> |送信者によって使用されるビデオのコーデックの種類です。 詳細については、 [CodecDescription テーブル](codecdescription.md)を参照してください。 <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SendResolutionWidth** <br/> |int  <br/> ||解像度の幅が、送信者によって使用されます。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SendResolutionHeight** <br/> |int  <br/> ||送信者によって使用される解像度の高さです。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SendFrameRateAverage** <br/> |float  <br/> ||送信者によって使用されるビデオのフレーム レートの伝送を平均します。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SendBitRateMaximum** <br/> |int  <br/> ||送信者の最大ビット レートです。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SendBitRateAverage** <br/> |int  <br/> ||センダーの平均ビット レートです。  <br/> |
|**SendVideoStreamsMax** <br/> |int  <br/> ||送信者によって使用されるビデオのストリームの最大数。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RecvCodecTypes** <br/> |smallint  <br/> |外部  <br/> |受信機で使用されるビデオのコード。 詳細については、 [CodecDescription テーブル](codecdescription.md)を参照してください。 <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RecvResolutionWidth** <br/> |int  <br/> ||受信機で使用されている解像度の幅です。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RecvResolutionHeight** <br/> |int  <br/> ||受信機で使用されている解像度の高さです。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RecvFrameRateAverage** <br/> |float  <br/> ||平均のビデオのフレーム レートが受信側で使用します。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RecvBitRateMaximum** <br/> |int  <br/> ||受信機の最大ビット レートです。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RecvBitRateAverage** <br/> |int  <br/> ||受信機の平均ビット レートです。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RecvVideoStreamsMax** <br/> |int  <br/> ||受信機のビデオ ストリームの最大です。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RecvVideoStreamsMin** <br/> |int  <br/> ||受信機のビデオ ストリームの最小値です。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RecvVideoStreamsMode** <br/> |int  <br/> ||ビデオ モード (ギャラリーなど、1 つのストリーム) の受信機です。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**VideoPostFECPLR** <br/> |float  <br/> ||パケット損失の割合が前方エラー修正を適用した後です。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**DynamicCapabilityPercent** <br/> |float  <br/> ||動的な機能フラグがアクティブだった時間の割合。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**ResolutionMin** <br/> |char (9)  <br/> ||最小解像度は、呼び出し中に測定されます。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**LowBitRateCallPercent** <br/> |float  <br/> ||低ビット レートのしきい値 (70 キロ ビット/秒) 以下の呼び出しの割合です。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**LowFrameRateCallPercent** <br/> |float  <br/> ||低フレーム レートのしきい値以下の呼び出しの割合 (7.5 秒あたりのフレームを受信)。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**LowResolutionCallPercent** <br/> |float  <br/> ||最低の解像度で発生した呼び出しの割合です。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**DurationSeconds** <br/> |float  <br/> ||秒単位での長さです。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**IsAggregatedData** <br/> |bit  <br/> ||複数の呼び出しからのデータが集計されたかどうかを示します。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
   

