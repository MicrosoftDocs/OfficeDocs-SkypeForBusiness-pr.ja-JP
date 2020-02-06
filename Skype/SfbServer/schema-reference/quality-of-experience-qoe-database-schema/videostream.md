---
title: VideoStream テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
description: 各レコードは1つのビデオストリームを表します。 1つのビデオメディアラインには通常、2つのビデオストリームが含まれています。
ms.openlocfilehash: 7eca8335ccf6905d3f80dd6ad8a5ccf00b749b39
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41804237"
---
# <a name="videostream-table"></a>VideoStream テーブル
 
各レコードは1つのビデオストリームを表します。 1つのビデオメディアラインには通常、2つのビデオストリームが含まれています。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |[MediaLine テーブル](medialine-0.md)から参照されます。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |R は[MediaLine テーブル](medialine-0.md)から参照されます。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |[MediaLine テーブル](medialine-0.md)から参照されます。  <br/> |
|**StreamID** <br/> |int  <br/> |Primary  <br/> |メディアライン内の一意の ID。  <br/> |
|**VideoPayloadDescription** <br/> |smallint  <br/> |外来、プライマリ  <br/> |ペイロードの説明。 詳細については、 [PayloadDescription の表](payloaddescription.md)を参照してください。 <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |リアルタイム制御プロトコル (RTCP) の統計情報からの平均ネットワークジッター。  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |ビデオセッション中の最大ネットワークジッター。  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |RTCP の統計情報からのラウンドトリップ時間。  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |ビデオストリームの最大ラウンドトリップ時間。  <br/> |
|**PacketLossRate** <br/> |10進数 (5, 4)  <br/> | <br/> |通話中の平均パケット損失率。  <br/> |
|**PacketLossRateMax** <br/> |10進数 (5, 4)  <br/> | <br/> |通話中に発生したパケット損失の上限。  <br/> |
|**PacketUtilization** <br/> |int  <br/> | <br/> |ビデオストリームのパケット数 (リアルタイムトランスポートプロトコル、RTP)。  <br/> |
|**BandwidthEst** <br/> |int  <br/> | <br/> |ビデオストリームの帯域幅推定。  <br/> |
|**VideoResolution** <br/> |char (9)  <br/> | <br/> |ピクセル幅にピクセルの高さを掛けたビデオの解像度。 文字列として報告されます。  <br/> |
|**VideoBitRateAvg** <br/> |int  <br/> | <br/> |ビデオストリームの平均ビットレート。  <br/> |
|**InboundVideoFrameRateAvg** <br/> |10進数 (9, 4)  <br/> | <br/> |ビデオフレームレートが適用されました。  <br/> |
|**OutboundVideoFrameRateAvg** <br/> |10進数 (9, 4)  <br/> | <br/> |送信されたビデオフレームレート。  <br/> |
|**VideoBitRateMax** <br/> |int  <br/> | <br/> |ビデオセッション中の最大ビデオビットレート。  <br/> |
|**VideoFrameLossRate** <br/> |10進数 (9, 4)  <br/> | <br/> |失われたビデオフレームの合計のパーセンテージ。  <br/> |
|**VideoFEC** <br/> |bit  <br/> | <br/> |使用できません。  <br/> |
|**ビデオ** <br/> |10進数 (9, 4)  <br/> ||失われたビデオフレームの合計のパーセンテージ。  <br/> |
|**CIFQualityRatio** <br/> |tinyint  <br/> ||共通インターチェンジ形式 (CIF) の解像度での通話の割合。  <br/> |
|**VGAQualityRatio** <br/> |tinyint  <br/> ||VGA 解像度での通話の割合。  <br/> |
|**HD720QualityRatio** <br/> |tinyint  <br/> ||HD720 の解像度での通話の割合。  <br/> |
|**NoneDropRatio** <br/> |tinyint  <br/> ||フレームドロップなしの通話時間の割合。  <br/> |
|**Bスペック** <br/> |tinyint  <br/> ||B フレームドロップでの通話時間の割合。  <br/> |
|**Bp・スペック** <br/> |tinyint  <br/> ||BP フレームドロップでの通話時間の割合。  <br/> |
|**Bpsp・ bp** <br/> |tinyint  <br/> ||BPSP フレームドロップでの通話時間の割合。  <br/> |
|**BPSPIDropRatio** <br/> |tinyint  <br/> ||BPSPI フレームドロップでの通話時間の割合。  <br/> |
|**トラフィック** <br/> |bit  <br/> | <br/> |受信側のストリームデータが受信されます。  <br/> |
|**発信** <br/> |bit  <br/> | <br/> |送信側のストリームデータが受信されます。  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1ストリームの方向は、呼び出し元から呼び出し先へとなります。  <br/> 0は、ストリームの方向を呼び出し元から呼び出し元に転送します。  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||通話が切断された輻輳状態であった時間の割合を示します。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||ネットワークパケットが遅延したために発生した、通話の割合を示します。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||通話がネットワークリソースに対して競合した時間の割合を示します。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||通話中の最小帯域幅推定値。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||通話中に測定された帯域幅推定の最大量。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||通話中に測定された帯域幅推定の標準偏差。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||通話中に計測された平均帯域幅推定量。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**LowBandwidthForMultiview** <br/> |float  <br/> ||エンドポイントが、ネットワーク接続が multiview ビデオをサポートしていないと判断した通話の割合。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||一方向の待機時間の合計。 相対的な一方向の待ち時間は、クライアントとサーバーの間の遅延を測定します。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||一方向の待ち時間の平均値。 相対的な一方向の待ち時間は、クライアントとサーバーの間の遅延を測定します。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||一方向の待機時間の上限。 相対的な一方向の待ち時間は、クライアントとサーバーの間の遅延を測定します。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||1方向のバースト発生の合計。 "Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。 このメトリックは、クライアントとサーバー間のデータフローを計測します。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayBurstDensity** <br/> |int  <br/> ||全体的な1方向バースト密度。 "Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。 このメトリックは、クライアントとサーバー間のデータフローを計測します。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||一方向のバースト期間の合計。 "Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。 このメトリックは、クライアントとサーバー間のデータフローを計測します。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||一方向のギャップ出現の合計。 "Bursty" 伝送とは、安定したストリームではなく、予期しないバーストでデータが流れる伝送です。ギャップは、このようなバーストの間の遅延を示します。 このメトリックは、クライアントとサーバー間のデータフローを計測します。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||一方向のギャップの密度の合計。 "Bursty" 伝送とは、安定したストリームではなく、予期しないバーストでデータが流れる伝送です。ギャップは、このようなバーストの間の遅延を示します。 このメトリックは、クライアントとサーバー間のデータフローを計測します。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||一方向のギャップ期間の合計。 "Bursty" 伝送とは、安定したストリームではなく、予期しないバーストでデータが流れる伝送です。ギャップは、このようなバーストの間の遅延を示します。 このメトリックは、クライアントとサーバー間のデータフローを計測します。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**パケット損失率** <br/> |10進数 (9, 4)  <br/> ||ビデオパケットが失われた速度。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**VideoAllocateBWAvg** <br/> |int  <br/> ||ビデオに割り当てられている平均帯域幅。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SendCodecTypes** <br/> |smallint  <br/> |外部  <br/> |送信者が使用するビデオコーデックの種類。 詳細については、 [CodecDescription の表](codecdescription.md)を参照してください。 <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**Send解像度の幅** <br/> |int  <br/> ||送信者が使用した解像度の幅。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**Sendの解像度の高さ** <br/> |int  <br/> ||送信者が使用する解像度の高さ。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SendFrameRateAverage** <br/> |float  <br/> ||送信者が使用した平均ビデオフレームレート送信。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SendBitRateMaximum** <br/> |int  <br/> ||送信者の最大ビットレート。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SendBitRateAverage** <br/> |int  <br/> ||送信者の平均ビットレート。  <br/> |
|**SendVideoStreamsMax** <br/> |int  <br/> ||送信者が使用したビデオストリームの最大数。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RecvCodecTypes** <br/> |smallint  <br/> |外部  <br/> |受信者が使用するビデオコード。 詳細については、 [CodecDescription の表](codecdescription.md)を参照してください。 <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RecvResolutionWidth** <br/> |int  <br/> ||レシーバーで使用される解像度の幅。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RecvResolutionHeight** <br/> |int  <br/> ||受信者が使用する解像度の高さ。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**受信フレームレート** <br/> |float  <br/> ||受信者が使用した平均ビデオフレームレート。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RecvBitRateMaximum** <br/> |int  <br/> ||受信者の最大ビットレート。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RecvBitRateAverage** <br/> |int  <br/> ||受信者の平均ビットレート。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RecvVideoStreamsMax** <br/> |int  <br/> ||受信者の最大ビデオストリーム。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RecvVideoStreamsMin** <br/> |int  <br/> ||受信者の最小ビデオストリーム。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RecvVideoStreamsMode** <br/> |int  <br/> ||受信者のビデオモード (たとえば、ギャラリーや単一ストリーム)。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**ビデオ plr** <br/> |float  <br/> ||転送後のエラー訂正が適用された後のパケット損失率。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**動的機能** <br/> |float  <br/> ||動的機能フラグがアクティブになった時間のパーセンテージ。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**解像度分** <br/> |char (9)  <br/> ||通話中に測定された最小解像度。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**LowBitRateCallPercent** <br/> |float  <br/> ||低ビットレートのしきい値 (70 kb/秒) 未満の通話のパーセンテージ。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**LowFrameRateCallPercent** <br/> |float  <br/> ||低フレームレートのしきい値を下回る通話の割合 (1 秒あたりの7.5 フレーム数)。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**低解像度** <br/> |float  <br/> ||最低の解像度で発生した通話の割合。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**DurationSeconds** <br/> |float  <br/> ||通話の長さ (秒単位)。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
|**IsAggregatedData** <br/> |bit  <br/> ||複数の通話からデータが集計されたかどうかを示します。  <br/> この列は Microsoft Lync Server 2013 で導入されました。  <br/> |
   

