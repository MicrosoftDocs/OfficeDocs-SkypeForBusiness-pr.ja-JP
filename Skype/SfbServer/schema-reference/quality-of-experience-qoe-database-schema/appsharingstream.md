---
title: AppSharingStream テーブル
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
ms.assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
description: AppSharingStream テーブルには、アプリケーション共有のストリームが使用するネットワークの QoE 測定値が含まれます。 この表は、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 675b4ef689b62577cbee1cef93a28865ca09abfe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809677"
---
# <a name="appsharingstream-table"></a>AppSharingStream テーブル
 
AppSharingStream テーブルには、アプリケーション共有のストリームが使用するネットワークの QoE 測定値が含まれます。 この表は、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |dateTime  <br/> |主/プライマリ、外部  <br/> |セッションが開始した日時。  <br/> |
|**SessionSeq** <br/> |int  <br/> |主/プライマリ、外部  <br/> |同じ日付に、同時に開始したセッションを区別する順次識別子。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |主/プライマリ、外部  <br/> | [「MediaLine テーブル」をご覧ください](https://docs.microsoft.com/skypeforbusiness/schema-reference/quality-of-experience-qoe-database-schema/medialine-0)。 <br/> |
|**StreamID** <br/> |int  <br/> |Primary  <br/> |アプリケーション共有ストリームの一意識別子。  <br/> |
|**JitterInterArrival** <br/> |int  <br/> ||RTP パケットの着信間に検出された平均ジッター (ジッターとは、通話の "揺れ" の測定値です)。通常、この値が高い場合は、輻輳やメディア サーバーの過負荷の原因が考えられます。その結果、音声のひずみや欠落が生じます。  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> ||RTP パケットの着信間に検出された最大ジッター (ジッターとは、通話の "揺れ" の測定値です)。通常、この値が高い場合は、輻輳やメディア サーバーの過負荷の原因が考えられます。その結果、音声のひずみや欠落が生じます。  <br/> |
|**RoundTrip** <br/> |int  <br/> ||リアルタイム転送プロトコル (RTP) パケットが別のエンドポイントとの間を往復するのに要する平均時間 (ミリ秒単位)。200 ミリ秒以下の往復時間が許容できる品質と見なされます。  <br/> この値が高い場合は、国際通話ルーティング、ルーティングの構成ミス、メディア サーバーの過負荷などの原因が考えられます。その結果、双方向のリアルタイムの音声会話が難しくなります。  <br/> |
|**RoundTripMax** <br/> |int  <br/> ||リアルタイム転送プロトコル (RTP) パケットが別のエンドポイントとの間を往復するのに要する最大時間 (ミリ秒単位)。200 ミリ秒以下の往復時間が許容できる品質と見なされます。  <br/> この値が高い場合は、国際通話ルーティング、ルーティングの構成ミス、メディア サーバーの過負荷などの原因が考えられます。その結果、双方向のリアルタイムの音声会話が難しくなります。  <br/> |
|**PacketLossRate** <br/> |浮動小数点数  <br/> ||リアルタイム転送プロトコル (RTP) パケット損失の平均レート。(パケット損失は、RTP パケット、つまりインターネット経由で音声とビデオを転送するために使われるプロトコルの一種で、パケットが宛先に到達できなかったときに発生します。) この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーの過負荷などの原因が考えられます。パケット損失が発生すると、通常、音声のひずみや欠落が生じます。  <br/> |
|**PacketLossRateMax** <br/> |浮動小数点数  <br/> ||リアルタイム転送プロトコル (RTP) パケット損失の最大レート。(パケット損失は、RTP パケット、つまりインターネット経由で音声とビデオを転送するために使われるプロトコルの一種で、パケットが宛先に到達できなかったときに発生します。) この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーの過負荷などの原因が考えられます。パケット損失が発生すると、通常、音声のひずみや欠落が生じます。  <br/> |
|**PacketUtilization** <br/> |int  <br/> ||送信されたパケット数。  <br/> |
|**BandwidthEst** <br/> |int  <br/> ||セッションの最後での、推定された一方向の帯域幅。ビット/秒で報告されます。  <br/> |
|**AppSharingPayloadDescription** <br/> |int  <br/> ||アプリケーション共有ペイロードの詳細。  <br/> |
|**RelativeOneWayTotal** <br/> |浮動小数点数  <br/> ||一方向の遅延の合計時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。  <br/> |
|**RelativeOneWayAverage** <br/> |浮動小数点数  <br/> ||一方向の遅延の平均時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。  <br/> |
|**RelativeOneWayMax** <br/> |浮動小数点数  <br/> ||一方向の遅延の最大時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||一方向のバーストの合計発生数。 "バースト的な" 伝送とは、安定したストリームではなく、予測できないバーストでデータが流れ込む伝送です。 この指標では、クライアントとサーバーの間のデータ フローが測定されます。  <br/> |
|**RelativeOneWayBurstDensity** <br/> |浮動小数点数  <br/> ||一方向のバーストの合計密度。 "バースト的な" 伝送とは、安定したストリームではなく、予測できないバーストでデータが流れ込む伝送です。 この指標では、クライアントとサーバーの間のデータ フローが測定されます。  <br/> |
|**RelativeOneWayBurstDuration** <br/> |浮動小数点数  <br/> ||一方向のバーストの合計期間。 "バースト的な" 伝送とは、安定したストリームではなく、予測できないバーストでデータが流れ込む伝送です。 この指標では、クライアントとサーバーの間のデータ フローが測定されます。  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||一方通行のギャップ発生回数の合計。 "バースト的な" 伝送とは、安定したストリームではなく、予測できないバーストでデータが流れ込む伝送です。ギャップは、これらのバースト間の遅延を示します。 この指標では、クライアントとサーバーの間のデータ フローが測定されます。  <br/> |
|**RelativeOneWayGapDensity** <br/> |浮動小数点数  <br/> ||一方通行のギャップ密度の合計。 "バースト的な" 伝送とは、安定したストリームではなく、予測できないバーストでデータが流れ込む伝送です。ギャップは、これらのバースト間の遅延を示します。 この指標では、クライアントとサーバーの間のデータ フローが測定されます。  <br/> |
|**RelativeOneWayGapDuration** <br/> |浮動小数点数  <br/> ||一方通行のギャップ期間の合計。 "バースト的な" 伝送とは、安定したストリームではなく、予測できないバーストでデータが流れ込む伝送です。ギャップは、これらのバースト間の遅延を示します。 この指標では、クライアントとサーバーの間のデータ フローが測定されます。  <br/> |
|**ApplicationSharingType** <br/> |varChar(256)  <br/> ||アプリケーション役割 (共有者または視聴者) とコンテンツ タイプ。  <br/> |
|**RDPTileProcessingLatencyTotal** <br/> |浮動小数点数  <br/> ||リモート デスクトップ プロトコル (RDP) タイルの合計の処理時間。この値が多いことは、表示に遅延が発生していることを示します。  <br/> |
|**RDPTileProcessingLatencyAverage** <br/> |浮動小数点数  <br/> ||リモート デスクトップ プロトコル (RDP) タイルの平均の処理時間。この値が多いことは、表示に遅延が発生していることを示します。  <br/> |
|**RDPTileProcessingLatencyMax** <br/> |浮動小数点数  <br/> ||リモート デスクトップ プロトコル (RDP) タイルの最大の処理時間。この値が多いことは、表示に遅延が発生していることを示します。  <br/> |
|**RDPTileProcessingLatencyBurstOccurrences** <br/> |int  <br/> ||リモート デスクトップ プロトコル (RDP) タイルの処理時間でのバースト発生数。 "バースト的な" 伝送とは、安定したストリームではなく、予測できないバーストでデータが流れ込む伝送です。  <br/> |
|**RDPTileProcessingLatencyBurstDensity** <br/> |浮動小数点数  <br/> ||リモート デスクトップ プロトコル (RDP) タイルの処理時間でのバースト密度。 "バースト的な" 伝送とは、安定したストリームではなく、予測できないバーストでデータが流れ込む伝送です。  <br/> |
|**RDPTileProcessingLatencyBurstDuration** <br/> |浮動小数点数  <br/> ||リモート デスクトップ プロトコル (RDP) タイルの処理時間でのバースト持続時間。 "バースト的な" 伝送とは、安定したストリームではなく、予測できないバーストでデータが流れ込む伝送です。  <br/> |
|**RDPTileProcessingLatencyGapOccurrences** <br/> |int  <br/> ||リモート デスクトップ プロトコル (RDP) タイルの処理時間でのギャップ発生数。  <br/> |
|**RDPTileProcessingLatencyGapDensity** <br/> |浮動小数点数  <br/> ||リモート デスクトップ プロトコル (RDP) タイルの処理時間でのギャップ密度。ギャップ密度が低いことは、表示エクスペリエンスが良いことを示します。  <br/> |
|**RDPTileProcessingLatencyGapDuration** <br/> |浮動小数点数  <br/> ||リモート デスクトップ プロトコル (RDP) タイルの処理時間でのギャップ持続時間。持続時間が短いことは、表示エクスペリエンスが良いことを示します。  <br/> |
|**CaptureTileRateTotal** <br/> |浮動小数点数  <br/> ||キャプチャされたタイルの合計のレート (タイル/秒)。  <br/> |
|**CaptureTileRateAverage** <br/> |浮動小数点数  <br/> ||キャプチャされたタイルの平均のレート (タイル/秒)。  <br/> |
|**CaptureTileRateMax** <br/> |浮動小数点数  <br/> ||キャプチャされたタイルの最大のレート (タイル/秒)。  <br/> |
|**CaptureTileRateBurstOccurrences** <br/> |in t  <br/> ||キャプチャされたタイルのレート (タイル/秒) でのバースト発生数。  <br/> |
|**CaptureTileRateBurstDensity** <br/> |浮動小数点数  <br/> ||キャプチャされたタイルのレート (タイル/秒) でのバースト密度。  <br/> |
|**CaptureTileRateBurstDuration** <br/> |浮動小数点数  <br/> ||キャプチャされたタイルのレート (タイル/秒) でのバースト持続時間。  <br/> |
|**CaptureTileRateGapOccurrences** <br/> |int  <br/> ||キャプチャされたタイルのレート (タイル/秒) でのギャップ発生数。  <br/> |
|**CaptureTileRateGapDensity** <br/> |浮動小数点数  <br/> ||キャプチャされたタイルのレート (タイル/秒) でのギャップ密度。  <br/> |
|**CaptureTileRateGapDuration** <br/> |浮動小数点数  <br/> ||キャプチャされたタイルのレート (タイル/秒) でのギャップ持続時間。  <br/> |
|**SpoiledTilePercentTotal** <br/> |浮動小数点数  <br/> ||視聴者に到達せず、新規のコンテンツによって破棄されて、上書きされたコンテンツの合計の割合。  <br/> |
|**SpoiledTilePercentAverage** <br/> |浮動小数点数  <br/> ||視聴者に到達せず、新規のコンテンツによって破棄されて、上書きされたコンテンツの平均の割合。  <br/> |
|**SpoiledTilePercentMax** <br/> |浮動小数点数  <br/> ||視聴者に到達せず、新規のコンテンツによって破棄されて、上書きされたコンテンツの最大の割合。  <br/> |
|**SpoiledTilePercentBurstOccurrences** <br/> |int  <br/> ||視聴者に到達せず、新規のコンテンツによって破棄されて、上書きされたコンテンツでのバースト発生数。  <br/> |
|**SpoiledTilePercentBurstDensity** <br/> |浮動小数点数  <br/> ||視聴者に到達せず、新規のコンテンツによって破棄されて、上書きされたコンテンツでのバースト密度。  <br/> |
|**SpoiledTilePercentBurstDuration** <br/> |浮動小数点数  <br/> ||視聴者に到達せず、新規のコンテンツによって破棄されて、上書きされたコンテンツでのバースト持続時間。  <br/> |
|**SpoiledTilePercentGapOccurrences** <br/> |int  <br/> ||視聴者に到達せず、新規のコンテンツによって破棄されて、上書きされたコンテンツでのギャップ発生数。  <br/> |
|**SpoiledTilePercentGapDensity** <br/> |浮動小数点数  <br/> ||視聴者に到達せず、新規のコンテンツによって破棄されて、上書きされたコンテンツでのギャップ密度。  <br/> |
|**SpoiledTilePercentGapDuration** <br/> |浮動小数点数  <br/> ||視聴者に到達せず、新規のコンテンツによって破棄されて、上書きされたコンテンツでのギャップ持続時間。  <br/> |
|**ScrapingFrameRateTotal** <br/> |浮動小数点数  <br/> ||グラフィックス ソースからスクレープされたフレームの合計数。  <br/> |
|**ScrapingFrameRateAverage** <br/> |浮動小数点数  <br/> ||グラフィックス ソースからスクレープされたフレームの平均数。  <br/> |
|**ScrapingFrameRateMax** <br/> |浮動小数点数  <br/> ||グラフィックス ソースからスクレープされたフレームの最大数。  <br/> |
|**ScrapingFrameRateBurstOccurrences** <br/> |int  <br/> ||グラフィックス ソースからスクレープされたフレームのバースト発生数。  <br/> |
|**ScrapingFrameRateBurstDensity** <br/> |浮動小数点数  <br/> ||グラフィックス ソースからスクレープされたフレームのバースト密度。  <br/> |
|**ScrapingFrameRateBurstDuration** <br/> |浮動小数点数  <br/> ||グラフィックス ソースからスクレープされたフレームのバースト持続時間。  <br/> |
|**ScrapingFrameRateGapOccurrences** <br/> |int  <br/> ||グラフィックス ソースからスクレープされたフレームのギャップ発生数。  <br/> |
|**ScrapingFrameRateGapDensity** <br/> |浮動小数点数  <br/> ||グラフィックス ソースからスクレープされたフレームのギャップ密度。  <br/> |
|**ScrapingFrameRateGapDuration** <br/> |浮動小数点数  <br/> ||グラフィックス ソースからスクレープされたフレームのギャップ持続時間。  <br/> |
|**IncomingTileRateTotal** <br/> |浮動小数点数  <br/> ||閲覧者が受信するときの合計受信フレーム レート。  <br/> |
|**IncomingTileRateAverage** <br/> |浮動小数点数  <br/> ||閲覧者が受信するときの平均受信フレーム レート。  <br/> |
|**IncomingTileRateMax** <br/> |浮動小数点数  <br/> ||閲覧者が受信するときの最大受信タイル レート。  <br/> |
|**IncomingTileRateBurstOccurrences** <br/> |int  <br/> ||閲覧者が受信する受信タイル レートでのバースト発生数。  <br/> |
|**IncomingTileRateBurstDensity** <br/> |浮動小数点数  <br/> ||閲覧者が受信する受信タイル レートでのバースト密度。  <br/> |
|**IncomingTileRateBurstDuration** <br/> |浮動小数点数  <br/> ||閲覧者が受信する受信タイル レートでのバースト持続時間。  <br/> |
|**IncomingTileRateGapOccurrences** <br/> |int  <br/> ||閲覧者が受信する受信タイル レートでのギャップ発生数。  <br/> |
|**IncomingTileRateGapDensity** <br/> |浮動小数点数  <br/> ||閲覧者が受信する受信タイル レートでのギャップ密度。  <br/> |
|**IncomingTileRateGapDuration** <br/> |浮動小数点数  <br/> ||閲覧者が受信する受信タイル レートでのギャップ持続時間。  <br/> |
|**IncomingFrameRateTotal** <br/> |浮動小数点数  <br/> ||閲覧者が受信するときの合計受信フレーム レート。  <br/> |
|**IncomingFrameRateAverage** <br/> |浮動小数点数  <br/> ||閲覧者が受信するときの平均受信フレーム レート。  <br/> |
|**IncomingFrameRateMax** <br/> |浮動小数点数  <br/> ||閲覧者が受信するときの最大受信フレーム レート。  <br/> |
|**IncomingFrameRateBurstOccurrences** <br/> |int  <br/> ||閲覧者が受信する受信フレーム レートでのバースト発生数。  <br/> |
|**IncomingFrameRateBurstDensity** <br/> |浮動小数点数  <br/> ||閲覧者が受信する受信フレーム レートでのバースト密度。  <br/> |
|**IncomingFrameRateBurstDuration** <br/> |浮動小数点数  <br/> ||閲覧者が受信する受信フレーム レートでのバースト持続時間。  <br/> |
|**IncomingFrameRateGapOccurrences** <br/> |int  <br/> ||閲覧者が受信する受信フレーム レートでのギャップ発生数。  <br/> |
|**IncomingFrameRateGapDensity** <br/> |浮動小数点数  <br/> ||閲覧者が受信する受信フレーム レートでのギャップ密度。  <br/> |
|**IncomingFrameRateDuration** <br/> |浮動小数点数  <br/> ||閲覧者が受信する受信フレーム レートでのギャップ持続時間。  <br/> |
|**OutgoingTileRateTotal** <br/> |浮動小数点数  <br/> ||送信者の合計の送信タイル レート。  <br/> |
|**OutgoingTileRateAverage** <br/> |浮動小数点数  <br/> ||送信者の平均の送信タイル レート。  <br/> |
|**OutgoingTileRateMax** <br/> |浮動小数点数  <br/> ||送信者の最大の送信タイル レート。  <br/> |
|**OutgoingTileRateBurstOccurrences** <br/> |int  <br/> ||送信者の送信タイル レートのバースト発生数。  <br/> |
|**OutgoingTileRateBurstDensity** <br/> |浮動小数点数  <br/> ||送信者の送信タイル レートのバースト密度。  <br/> |
|**OutgoingTileRateBurstDuration** <br/> |浮動小数点数  <br/> ||送信者の送信タイル レートのバースト持続時間。  <br/> |
|**OutgoingTileRateGapOccurrences** <br/> |int  <br/> ||送信者の送信タイル レートのギャップ発生数。  <br/> |
|**OutgoingTileRateGapDensity** <br/> |浮動小数点数  <br/> ||送信者の送信タイル レートのギャップ密度。  <br/> |
|**OutgoingTileRateGapDuration** <br/> |浮動小数点数  <br/> ||送信者の送信タイル レートのギャップ持続時間。  <br/> |
|**OutgoingFrameRateTotal** <br/> |浮動小数点数  <br/> ||送信者の合計の送信フレーム レート。  <br/> |
|**OutgoingFrameRateAverage** <br/> |浮動小数点数  <br/> ||送信者の平均の送信フレーム レート。  <br/> |
|**OutgoingFrameRateMax** <br/> |浮動小数点数  <br/> ||送信者の最大の送信フレーム レート。  <br/> |
|**OutgoingFrameRateBurstOccurrences** <br/> |int  <br/> ||送信者の送信フレーム レートのバースト発生数。  <br/> |
|**OutgoingFrameRateBurstDensity** <br/> |浮動小数点数  <br/> ||送信者の送信フレーム レートのバースト密度。  <br/> |
|**OutgoingFrameRateBurstDuration** <br/> |浮動小数点数  <br/> ||送信者の送信フレーム レートのバースト持続時間。  <br/> |
|**OutgoingFrameRateGapOccurrences** <br/> |int  <br/> ||送信者の送信フレーム レートのギャップ発生数。  <br/> |
|**OutgoingFrameRateGapDensity** <br/> |浮動小数点数  <br/> ||送信者の送信フレーム レートのギャップ密度。  <br/> |
|**OutgoingFrameRateGapDuration** <br/> |浮動小数点数  <br/> ||送信者の送信フレーム レートのギャップ持続時間。  <br/> |
|**AverageRectangleHeight** <br/> |int  <br/> ||平均のビデオ解像度の高さ (ピクセル)。  <br/> |
|**AverageRectangleWidth** <br/> |int  <br/> ||平均のビデオ解像度の幅 (ピクセル)。  <br/> |
|**受信** <br/> |bit  <br/> ||着信の平均フレーム レート (フレーム/秒)。  <br/> |
|**送信** <br/> |bit  <br/> ||発信の平均フレーム レート (フレーム/秒)。  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> ||1 は、ストリームの方向が発信者から呼び出し先へ向かうことを意味します。  <br/> 0 は、ストリームの方向が呼び出し先から発信者へ向かうことを意味します。  <br/> |
   

