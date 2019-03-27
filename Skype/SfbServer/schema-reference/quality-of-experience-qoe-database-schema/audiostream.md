---
title: AudioStream テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
description: 各レコードは、1 つのオーディオ ストリームを表します。 オーディオ メディアの 1 つの行には、通常 2 つのオーディオ ストリームが含まれています。
ms.openlocfilehash: 7c1e7ae70a04aabc7db704aaaad873bc5b2100c9
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894136"
---
# <a name="audiostream-table"></a>AudioStream テーブル
 
各レコードは、1 つのオーディオ ストリームを表します。 オーディオ メディアの 1 つの行には、通常 2 つのオーディオ ストリームが含まれています。
  
|列|データ型|キー/インデックス|詳細|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |[MediaLine テーブル](medialine-0.md)から参照されています。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |[MediaLine テーブル](medialine-0.md)から参照されています。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |[MediaLine テーブル](medialine-0.md)から参照されています。  <br/> |
|**StreamID** <br/> |int  <br/> |Primary  <br/> |メディア ライン内で一意の ID。  <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |リアルタイム制御プロトコル (RTCP) 統計情報のネットワークの平均ジッター。  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |呼び出し時に最大ネットワーク ジッター。  <br/> |
|**PacketLossRate** <br/> |decimal(5,4)  <br/> | <br/> |呼び出し時に平均パケット損失の割合です。  <br/> |
|**PacketLossRateMax** <br/> |decimal(5,4)  <br/> | <br/> |最大のパケット損失が呼び出し中に発生します。  <br/> |
|**BurstDensity** <br/> |decimal(9,4)  <br/> | <br/> |通話中のデータ損失のバースト時のパケット損失の平均密度は。  <br/> |
|**BurstDuration** <br/> |int  <br/> | <br/> |通話中のデータ損失のバースト時のパケット損失の平均時間です。  <br/> |
|**BurstGapDensity** <br/> |decimal(9,4)  <br/> | <br/> |バースト パケット ロスの間のギャップの中にパケット損失の平均密度は。  <br/> |
|**BurstGapDuration** <br/> |int  <br/> | <br/> |バースト パケット ロスの間のギャップの平均時間です。  <br/> |
|**PacketUtilization** <br/> |Int  <br/> | <br/> |オーディオ ストリームのパケット数です。  <br/> |
|**BandwidthEst** <br/> |Int  <br/> | <br/> |オーディオ ストリームの帯域幅を推定します。  <br/> |
|**DegradationAvg** <br/> |decimal(3,2)  <br/> | <br/> |全体のコールのネットワーク MOS の低下。 範囲は、0.0 に 5.0 です。 このメトリックでは、ネットワーク MOS 漢のジッターとパケット損失が発生したため、時間を表示します。 許容可能な品質にする必要があります 0.5 よりも小さい。  <br/> |
|**DegradationMax** <br/> |decimal(3,2)  <br/> | <br/> |呼び出し時に最大のネットワーク MOS の低下。  <br/> |
|**DegradationJitterAvg** <br/> |decimal(3,2)  <br/> | <br/> |ネットワーク MOS の低下がジッタが原因で発生します。  <br/> |
|**DegradationPacketLossAvg** <br/> |decimal(3,2)  <br/> | <br/> |ネットワーク MOS の低下がパケットの損失が原因で発生します。  <br/> |
|**AudioPayloadDescription** <br/> |int  <br/> |外部  <br/> |オーディオ コーデックは、PayloadDescription テーブルから参照される、呼び出しに使用されます。  <br/> |
|**AudioSampleRate** <br/> |int  <br/> | <br/> |ストリームのオーディオのサンプリング レートです。  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |RTCP の統計情報のラウンド トリップ時間です。 許容可能な品質を 100 ミリ秒未満であるはずです。  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |オーディオ ストリームの最大のラウンド トリップ時間です。  <br/> |
|**OverallAvgNetworkMOS** <br/> |decimal(3,2)  <br/> | <br/> |広帯域ネットワーク MOS を呼び出しの平均値です。 このメトリックは、パケット損失、ジッター、および使用するコーデックによって異なります。 範囲は、[1.0 5.0] です。  <br/> |
|**OverallMinNetworkMOS** <br/> |decimal(3,2)  <br/> | <br/> |最小広帯域ネットワーク MOS を呼び出しので。  <br/> |
|**SendListenMOS** <br/> |decimal(3,2)  <br/> | <br/> |予測平均の広帯域のリッスンしている MOS は、オーディオの送信、音声レベル、ノイズ レベルを含むスコアし、デバイスの特性をキャプチャします。  <br/> |
|**SendListenMOSMin** <br/> |decimal(3,2)  <br/> | <br/> |呼び出しの最小の SendListenMOS です。  <br/> |
|**RecvListenMOS** <br/> |decimal(3,2)  <br/> | <br/> |オーディオの平均の予測される広帯域の MOS をリッスンしているスコアは、音声レベル、ノイズ レベル、コーデック、ネットワークの状態のキャプチャ デバイスの特性を含むネットワークから受信します。  <br/> |
|**RecvListenMOSMin** <br/> |decimal(3,2)  <br/> | <br/> |呼び出しの最小の RecvListenMOS です。  <br/> |
|**AudioFECUsed** <br/> |bit  <br/> ||オーディオ FEC は、呼び出しに使用された場合を示すフラグを設定します。  <br/> |
|**RatioConcealedSamplesAvg** <br/> |decimal(5,2)  <br/> ||一般的なサンプルにオーディオの修復機能によって生成された非表示の文字列のサンプルの平均比率です。  <br/> |
|**RatioStretchedSamplesAvg** <br/> |decimal(5,2)  <br/> ||一般的なサンプルにオーディオの修復機能によって生成された、拡大されたサンプルの平均比率です。  <br/> |
|**RatioCompressedSamplesAvg** <br/> |decimal(5,2)  <br/> ||一般的なサンプルにオーディオの修復機能によって生成される圧縮のサンプルの平均比率です。  <br/> |
|**受信** <br/> |bit  <br/> | <br/> |受信機側でのデータのストリームを受信するとします。  <br/> |
|**発信** <br/> |bit  <br/> | <br/> |送信側のデータのストリームを受信するとします。  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 は、ストリームの方向は、呼び出し元から呼び出し先を意味します。  <br/> 0 では、ストリームの方向は、呼び出し先から呼び出し元を表します。  <br/> |
|**JitterInterArrivalSD** <br/> |float  <br/> ||ジッターの到着時間の標準偏差です。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**ConcealRatioMax** <br/> |float  <br/> ||治癒者によって非表示にするパケットの最大の比率です。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**ConcealRatioSD** <br/> |float  <br/> ||治癒者によって非表示にパケットの比率の標準偏差です。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**HealerPacketDropRatio** <br/> |float  <br/> ||受信パケットの合計数と比較して healer によって破棄されたパケットの率です。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**HealerFECPacketUsedRatio** <br/> |float  <br/> ||受信したパケットの合計数と比較して使用される前方エラー修正のパケットの率です。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**MaxCompressedSamples** <br/> |float  <br/> ||ヒーラーで圧縮されたオーディオ パケットの最大数。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||損失輻輳状態にしたときの時間の割合を示します。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||輻輳が原因でネットワーク パケットの遅延到着の呼び出しの割合を示します。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||ネットワーク リソースに対する呼び出しが競合する場合の時間の割合を示します。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||帯域幅の推定量の最小値は、呼び出し中に測定されます。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||最大帯域幅の推定量は、呼び出し中に測定されます。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||帯域幅の推定標準偏差は、呼び出し中に測定されます。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||平均帯域幅の推定量は、呼び出し中に測定されます。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||一方向の遅延時間の合計金額です。 相対的な一方向の遅延時間は、クライアントとサーバー間の遅延を測定します。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||一方向の遅延時間の平均量。 相対的な一方向の遅延時間は、クライアントとサーバー間の遅延を測定します。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||一方向の遅延時間の最大数。 相対的な一方向の遅延時間は、クライアントとサーバー間の遅延を測定します。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||合計の一方向のバースト発生数です。 「集中」の転送は、安定ではなく予期しない状態でのデータのフロー転送です。 このメトリックは、クライアントとサーバー間のデータ フローを測定します。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||合計の一方向のバースト密度。 「集中」の転送は、安定ではなく予期しない状態でのデータのフロー転送です。 このメトリックは、クライアントとサーバー間のデータ フローを測定します。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||合計の一方向のバーストの継続時間です。 「集中」の転送は、安定ではなく予期しない状態でのデータのフロー転送です。 このメトリックは、クライアントとサーバー間のデータ フローを測定します。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||合計の一方向のギャップの発生数です。 「集中」の転送では、転送、安定したストリームではなく予期しない状態でのデータのフローギャップは、これらのバーストの間の遅延を指定します。 このメトリックは、クライアントとサーバー間のデータ フローを測定します。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||合計の一方向のギャップ密度。 「集中」の転送では、転送、安定したストリームではなく予期しない状態でのデータのフローギャップは、これらのバーストの間の遅延を指定します。 このメトリックは、クライアントとサーバー間のデータ フローを測定します。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||合計の一方向のギャップの期間です。 「集中」の転送では、転送、安定したストリームではなく予期しない状態でのデータのフローギャップは、これらのバーストの間の遅延を指定します。 このメトリックは、クライアントとサーバー間のデータ フローを測定します。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**DecodeStereoPercent** <br/> |float  <br/> ||ステレオとしてデコードされた呼び出しの割合です。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**AecRenderStereoPercent** <br/> |float  <br/> ||音響エコー キャンセラをステレオとしてレンダリング呼び出しの割合です。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**AudioPostFECPLR** <br/> |float  <br/> ||パケット損失の割合が前方エラー修正を適用した後です。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**EncodeStereoPercent** <br/> |float  <br/> ||ステレオとしてエンコードされた呼び出しの割合です。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**AecCaptureStereoPercent** <br/> |float  <br/> ||音響エコー キャンセラをステレオとしてキャプチャされた呼び出しの割合です。  <br/> この列は、Microsoft Lync Server 2013 で導入されました。  <br/> |
