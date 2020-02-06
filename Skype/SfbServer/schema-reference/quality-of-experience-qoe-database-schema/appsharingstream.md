---
title: AppSharingStream テーブル
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
ms.assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
description: AppSharingStream テーブルには、アプリケーション共有に使用されるネットワークストリームのエクスペリエンスのメトリックの質が含まれています。 この表は、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 1ebcfe16fe5863bcb3046e88ba5cdc2079f22a9c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41811105"
---
# <a name="appsharingstream-table"></a>AppSharingStream テーブル
 
AppSharingStream テーブルには、アプリケーション共有に使用されるネットワークストリームのエクスペリエンスのメトリックの質が含まれています。 この表は、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |dateTime  <br/> |プライマリ、外部  <br/> |セッションが開始された日付と時刻。  <br/> |
|**SessionSeq** <br/> |int  <br/> |プライマリ、外部  <br/> |同じ日付と同時に開始したセッションを区別するために使用されるシーケンシャル識別子。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |プライマリ、外部  <br/> | 「 [MediaLine テーブル](https://docs.microsoft.com/skypeforbusiness/schema-reference/quality-of-experience-qoe-database-schema/medialine-0)」を参照してください。 <br/> |
|**StreamID** <br/> |int  <br/> |Primary  <br/> |アプリケーション共有ストリームの一意の識別子。  <br/> |
|**JitterInterArrival** <br/> |int  <br/> ||RTP パケットの着信間に検出された平均ジッター (ジッターとは、通話の "揺れ" の測定値です)。通常、この値が高い場合は、輻輳やメディア サーバーの過負荷の原因が考えられます。その結果、音声のひずみや欠落が生じます。  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> ||RTP パケット着信の間の最大ジッターが検出されました。 (ジッターは、通話の "shakiness" の測定値です)。通常、高ジッターの値は、輻輳または過負荷のメディアサーバーによって発生し、音声が歪むか、失われる原因となります。  <br/> |
|**RoundTrip** <br/> |int  <br/> ||リアルタイム転送プロトコル (RTP) パケットが別のエンドポイントとの間を往復するのに要する平均時間 (ミリ秒単位)。200 ミリ秒以下の往復時間が許容できる品質と見なされます。  <br/> この値が高い場合は、国際通話ルーティング、ルーティングの構成ミス、メディア サーバーの過負荷などの原因が考えられます。その結果、双方向のリアルタイムの音声会話が難しくなります。  <br/> |
|**RoundTripMax** <br/> |int  <br/> ||リアルタイムトランスポートプロトコルパケットが別のエンドポイントに移動してから戻るために必要な最大 (ミリ秒単位)。 200 ミリ秒以下の往復時間が許容できる品質と見なされます。  <br/> この値が高い場合は、国際通話ルーティング、ルーティングの構成ミス、メディア サーバーの過負荷などの原因が考えられます。その結果、双方向のリアルタイムの音声会話が難しくなります。  <br/> |
|**PacketLossRate** <br/> |float  <br/> ||リアルタイム転送プロトコル (RTP) パケット損失の平均レート。(パケット損失は、RTP パケット、つまりインターネット経由で音声とビデオを転送するために使われるプロトコルの一種で、パケットが宛先に到達できなかったときに発生します)。この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーの過負荷などの原因が考えられます。パケット損失が発生すると、通常、音声のひずみや欠落が生じます。  <br/> |
|**PacketLossRateMax** <br/> |float  <br/> ||リアルタイムトランスポートプロトコル (RTP) パケット損失の最大速度。 (パケットの損失は、RTP パケット、インターネット上でのオーディオとビデオの伝送に使用されるプロトコル)、宛先への到達に失敗した場合に発生します。)通常、高損失率は輻輳が原因で発生します。帯域幅の不足。ワイヤレスの輻輳または妨害または、オーバーロードされたメディアサーバー。 パケット損失が発生すると、通常、音声のひずみや欠落が生じます。  <br/> |
|**PacketUtilization** <br/> |int  <br/> ||送信されたパケットの数です。  <br/> |
|**BandwidthEst** <br/> |int  <br/> ||セッションの終了時に提供される推定される一方向の帯域幅。 1秒あたりのビット数で報告されます。  <br/> |
|**AppSharingPayloadDescription** <br/> |int  <br/> ||アプリケーション共有ペイロードの説明。  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||一方向の待機時間の合計。 相対的な一方向の待ち時間は、クライアントとサーバーの間の遅延を測定します。  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||一方向の待ち時間の平均値。 相対的な一方向の待ち時間は、クライアントとサーバーの間の遅延を測定します。  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||一方向の待機時間の上限。 相対的な一方向の待ち時間は、クライアントとサーバーの間の遅延を測定します。  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||1方向のバースト発生の合計。 "Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。 このメトリックは、クライアントとサーバー間のデータフローを計測します。  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||全体的な1方向バースト密度。 "Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。 このメトリックは、クライアントとサーバー間のデータフローを計測します。  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||一方向のバースト期間の合計。 "Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。 このメトリックは、クライアントとサーバー間のデータフローを計測します。  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||一方向のギャップ出現の合計。 "Bursty" 伝送とは、安定したストリームではなく、予期しないバーストでデータが流れる伝送です。ギャップは、このようなバーストの間の遅延を示します。 このメトリックは、クライアントとサーバー間のデータフローを計測します。  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||一方向のギャップの密度の合計。 "Bursty" 伝送とは、安定したストリームではなく、予期しないバーストでデータが流れる伝送です。ギャップは、このようなバーストの間の遅延を示します。 このメトリックは、クライアントとサーバー間のデータフローを計測します。  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||一方向のギャップ期間の合計。 "Bursty" 伝送とは、安定したストリームではなく、予期しないバーストでデータが流れる伝送です。ギャップは、このようなバーストの間の遅延を示します。 このメトリックは、クライアントとサーバー間のデータフローを計測します。  <br/> |
|**ApplicationSharingType** <br/> |varChar (256)  <br/> ||アプリケーションロール (共有先またはビューアー) とコンテンツタイプ。  <br/> |
|**RDPTileProcessingLatencyTotal** <br/> |float  <br/> ||リモートデスクトッププロトコル (RDP) タイルの合計処理時間。 表示環境では、合計の遅延が長くなります。  <br/> |
|**Rdp タイル処理** <br/> |float  <br/> ||リモートデスクトッププロトコル (RDP) タイルの平均処理時間。 表示環境では、合計の遅延が長くなります。  <br/> |
|**RDPTileProcessingLatencyMax** <br/> |float  <br/> ||リモートデスクトッププロトコル (RDP) タイルの最大処理時間。 表示環境では、合計の遅延が長くなります。  <br/> |
|**RDPTileProcessingLatencyBurstOccurrences** <br/> |int  <br/> ||リモートデスクトッププロトコル (RDP) タイルの処理時間でのバースト発生。 "Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。  <br/> |
|**RDPTileProcessingLatencyBurstDensity** <br/> |float  <br/> ||リモートデスクトッププロトコル (RDP) タイルの処理時間のバースト密度。 "Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。  <br/> |
|**RDPTileProcessingLatencyBurstDuration** <br/> |float  <br/> ||リモートデスクトッププロトコル (RDP) タイルの処理時間のバースト時間。 "Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。  <br/> |
|**RDPTileProcessingLatencyGapOccurrences** <br/> |int  <br/> ||リモートデスクトッププロトコル (RDP) タイルの処理時間のギャップの出現回数。  <br/> |
|**RDPTileProcessingLatencyGapDensity** <br/> |float  <br/> ||リモートデスクトッププロトコル (RDP) タイルの処理時間のギャップの密度。 隙間が小さいほど、表示エクスペリエンスが向上します。  <br/> |
|**RDPTileProcessingLatencyGapDuration** <br/> |float  <br/> ||リモートデスクトッププロトコル (RDP) タイルの処理時間の間隔。 短い間隔の期間は、表示感が向上するようになります。  <br/> |
|**CaptureTileRateTotal** <br/> |float  <br/> ||キャプチャされたタイルの合計レート (1 秒あたりのタイル数)  <br/> |
|**CaptureTileRateAverage** <br/> |float  <br/> ||キャプチャされたタイルの平均速度 (1 秒あたりのタイル数)。  <br/> |
|**CaptureTileRateMax** <br/> |float  <br/> ||キャプチャされたタイルの最大速度 (1 秒あたりのタイル数)  <br/> |
|**CaptureTileRateBurstOccurrences** <br/> |t  <br/> ||キャプチャされたタイルの速度 (1 秒あたりのタイル) でバーストが発生します。  <br/> |
|**CaptureTileRateBurstDensity** <br/> |float  <br/> ||キャプチャされたタイルの速度 (1 秒あたりのタイル数) のバースト密度。  <br/> |
|**CaptureTileRateBurstDuration** <br/> |float  <br/> ||キャプチャされたタイルの割合でのバースト時間 (1 秒あたりのタイル数)。  <br/> |
|**CaptureTileRateGapOccurrences** <br/> |int  <br/> ||キャプチャされたタイルの比率 (1 秒あたりのタイル数) でのギャップ出現回数。  <br/> |
|**CaptureTileRateGapDensity** <br/> |float  <br/> ||キャプチャされたタイル (1 秒あたりのタイル数) の間隔の間隔。  <br/> |
|**CaptureTileRateGapDuration** <br/> |float  <br/> ||キャプチャされたタイルの割合の間隔 (1 秒あたりのタイル数)  <br/> |
|**損失タイル** <br/> |float  <br/> ||閲覧者に届かなかったが、破棄され、最新のコンテンツによって上書きされたコンテンツの割合の合計。  <br/> |
|**SpoiledTilePercentAverage** <br/> |float  <br/> ||閲覧者に届かなかったが、新しいコンテンツによって破棄されて上書きされたコンテンツの平均割合。  <br/> |
|**SpoiledTilePercentMax** <br/> |float  <br/> ||閲覧者に届かなかったが、新しいコンテンツによって破棄されて上書きされたコンテンツの最大パーセンテージ。  <br/> |
|**SpoiledTilePercentBurstOccurrences** <br/> |int  <br/> ||閲覧者に届かなかったが、新しいコンテンツによって破棄されて上書きされたコンテンツのバースト発生。  <br/> |
|**SpoiledTilePercentBurstDensity** <br/> |float  <br/> ||ビューアーに届かなかったが、新しいコンテンツによって破棄されて上書きされたコンテンツのバースト密度。  <br/> |
|**SpoiledTilePercentBurstDuration** <br/> |float  <br/> ||ビューアーに届かなかったが、新しいコンテンツによって破棄されて上書きされたコンテンツのバースト時間。  <br/> |
|**SpoiledTilePercentGapOccurrences** <br/> |int  <br/> ||閲覧者に届かなかったが、新しいコンテンツによって破棄されて上書きされたコンテンツの Gap オカレンス。  <br/> |
|**SpoiledTilePercentGapDensity** <br/> |float  <br/> ||ビューアーに届かなかったが、新しいコンテンツで破棄されて上書きされたコンテンツの Gap 濃度。  <br/> |
|**SpoiledTilePercentGapDuration** <br/> |float  <br/> ||ビューアーに届かなかったが、新しいコンテンツによって破棄されて上書きされたコンテンツの間隔の期間。  <br/> |
|**ScrapingFrameRateTotal** <br/> |float  <br/> ||グラフィックスソースから scraped フレームの合計数です。  <br/> |
|**ScrapingFrameRateAverage** <br/> |float  <br/> ||グラフィックスソースから scraped フレームの平均数。  <br/> |
|**ScrapingFrameRateMax** <br/> |float  <br/> ||グラフィックスソースから scraped フレームの最大数。  <br/> |
|**ScrapingFrameRateBurstOccurrences** <br/> |int  <br/> ||グラフィックソースからフレームの scraped が発生します。  <br/> |
|**ScrapingFrameRateBurstDensity** <br/> |float  <br/> ||グラフィックスソースからのフレーム scraped のバースト密度。  <br/> |
|**ScrapingFrameRateBurstDuration** <br/> |float  <br/> ||グラフィックスソースからのフレーム scraped のバースト時間。  <br/> |
|**ScrapingFrameRateGapOccurrences** <br/> |int  <br/> ||グラフィックソースから、フレーム内の Gap オカレンスが scraped ます。  <br/> |
|**ScrapingFrameRateGapDensity** <br/> |float  <br/> ||グラフィックスソースから scraped フレームの間隔の濃度。  <br/> |
|**ScrapingFrameRateGapDuration** <br/> |float  <br/> ||グラフィックスソースから scraped フレームの間隔を指定します。  <br/> |
|**IncomingTileRateTotal** <br/> |float  <br/> ||視聴者が受信したフレームの合計料金。  <br/> |
|**IncomingTileRateAverage** <br/> |float  <br/> ||視聴者が受信したフレームの平均速度。  <br/> |
|**IncomingTileRateMax** <br/> |float  <br/> ||視聴者が受信した最大受信タイルレート。  <br/> |
|**IncomingTileRateBurstOccurrences** <br/> |int  <br/> ||視聴者が受信したタイルレートでのバースト発生  <br/> |
|**IncomingTileRateBurstDensity** <br/> |float  <br/> ||視聴者が受信したタイルレートのバースト密度。  <br/> |
|**IncomingTileRateBurstDuration** <br/> |float  <br/> ||閲覧者が受信した受信タイルレートのバースト時間。  <br/> |
|**IncomingTileRateGapOccurrences** <br/> |int  <br/> ||閲覧者が受信したタイルレートのギャップが表示されます。  <br/> |
|**IncomingTileRateGapDensity** <br/> |float  <br/> ||閲覧者によって受信された、受信タイルレートのギャップの密度。  <br/> |
|**IncomingTileRateGapDuration** <br/> |float  <br/> ||視聴者が受信したタイルレートの間隔。  <br/> |
|**IncomingFrameRateTotal** <br/> |float  <br/> ||視聴者が受信したフレームの合計料金。  <br/> |
|**IncomingFrameRateAverage** <br/> |float  <br/> ||視聴者が受信したフレームの平均速度。  <br/> |
|**IncomingFrameRateMax** <br/> |float  <br/> ||視聴者が受信した受信フレームレートの上限。  <br/> |
|**IncomingFrameRateBurstOccurrences** <br/> |int  <br/> ||視聴者が受信したフレームレートのバーストが発生します。  <br/> |
|**IncomingFrameRateBurstDensity** <br/> |float  <br/> ||視聴者が受信したフレームレートのバースト密度。  <br/> |
|**IncomingFrameRateBurstDuration** <br/> |float  <br/> ||ビューアーで受信した受信フレームレートのバースト時間。  <br/> |
|**IncomingFrameRateGapOccurrences** <br/> |int  <br/> ||閲覧者が受信したフレームレートのギャップが表示されます。  <br/> |
|**IncomingFrameRateGapDensity** <br/> |float  <br/> ||視聴者が受信したフレームレートの間隔。  <br/> |
|**IncomingFrameRateDuration** <br/> |float  <br/> ||視聴者が受信したフレームレートの間隔。  <br/> |
|**OutgoingTileRateTotal** <br/> |float  <br/> ||送信者の合計送信タイルレート。  <br/> |
|**OutgoingTileRateAverage** <br/> |float  <br/> ||送信者の平均送信タイルレート。  <br/> |
|**OutgoingTileRateMax** <br/> |float  <br/> ||送信者の最大送信タイルレート。  <br/> |
|**OutgoingTileRateBurstOccurrences** <br/> |int  <br/> ||送信者の送信タイルレートのバーストが発生します。  <br/> |
|**OutgoingTileRateBurstDensity** <br/> |float  <br/> ||送信者の送信タイルレートのバースト密度。  <br/> |
|**OutgoingTileRateBurstDuration** <br/> |float  <br/> ||送信者の送信タイルレートのバースト時間。  <br/> |
|**OutgoingTileRateGapOccurrences** <br/> |int  <br/> ||送信者に対して、送信タイルレートのギャップが発生します。  <br/> |
|**OutgoingTileRateGapDensity** <br/> |float  <br/> ||送信者の送信タイルレートの間隔。  <br/> |
|**OutgoingTileRateGapDuration** <br/> |float  <br/> ||送信者の送信タイルレートの間隔。  <br/> |
|**OutgoingFrameRateTotal** <br/> |float  <br/> ||送信者の総送信フレームレート。  <br/> |
|**OutgoingFrameRateAverage** <br/> |float  <br/> ||送信者の平均送信フレームレート。  <br/> |
|**OutgoingFrameRateMax** <br/> |float  <br/> ||送信者の最大送信フレームレート。  <br/> |
|**OutgoingFrameRateBurstOccurrences** <br/> |int  <br/> ||送信者の送信フレームレートでのバースト発生。  <br/> |
|**OutgoingFrameRateBurstDensity** <br/> |float  <br/> ||送信者の送信フレームレートのバースト密度。  <br/> |
|**OutgoingFrameRateBurstDuration** <br/> |float  <br/> ||送信者の送信フレームレートのバースト時間。  <br/> |
|**OutgoingFrameRateGapOccurrences** <br/> |int  <br/> ||送信者に対して送信されるフレームレートのギャップ。  <br/> |
|**OutgoingFrameRateGapDensity** <br/> |float  <br/> ||送信者の発信フレームレートのギャップの密度。  <br/> |
|**OutgoingFrameRateGapDuration** <br/> |float  <br/> ||送信者の発信フレームレートの間隔。  <br/> |
|**AverageRectangleHeight** <br/> |int  <br/> ||平均ビデオ解像度の高さ (ピクセル単位)。  <br/> |
|**AverageRectangleWidth** <br/> |int  <br/> ||平均ビデオ解像度の幅 (ピクセル単位)。  <br/> |
|**トラフィック** <br/> |bit  <br/> ||受信伝送の平均フレームレート (1 秒あたりのフレーム数)。  <br/> |
|**発信** <br/> |bit  <br/> ||送信時の平均フレームレート (1 秒あたりのフレーム数)。  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> ||1ストリームの方向は、呼び出し元から呼び出し先へとなります。  <br/> 0は、ストリームの方向を呼び出し元から呼び出し元に転送します。  <br/> |
   

