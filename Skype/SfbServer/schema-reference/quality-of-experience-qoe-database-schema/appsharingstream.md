---
title: AppSharingStream テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
description: AppSharingStream テーブルには、ネットワーク ストリームのアプリケーションを共有するために使用される高品質なエクスペリエンスの測定基準が含まれています。 このテーブルは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 4eeac3f7b082d4a798736bd9897b90668a1d44b2
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2018
ms.locfileid: "26294304"
---
# <a name="appsharingstream-table"></a>AppSharingStream テーブル
 
AppSharingStream テーブルには、ネットワーク ストリームのアプリケーションを共有するために使用される高品質なエクスペリエンスの測定基準が含まれています。 このテーブルは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |日付時刻  <br/> |プライマリ サーバーで、外部  <br/> |日付と時刻、セッションを開始します。  <br/> |
|**SessionSeq** <br/> |int  <br/> |プライマリ サーバーで、外部  <br/> |同時日付けと同時に開始されたセッションの間で区別するために使用される一連の識別子です。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |プライマリ サーバーで、外部  <br/> | [MediaLine テーブル](https://docs.microsoft.com/en-us/skypeforbusiness/schema-reference/quality-of-experience-qoe-database-schema/medialine-0)を参照してください。 <br/> |
|**StreamID** <br/> |int  <br/> |Primary  <br/> |ストリームを共有するアプリケーションの一意の識別子です。  <br/> |
|**JitterInterArrival** <br/> |int  <br/> ||RTP パケットの着信間に検出された平均ジッター (ジッターとは、通話の "揺れ" の測定値です)。通常、この値が高い場合は、輻輳やメディア サーバーの過負荷の原因が考えられます。その結果、音声のひずみや欠落が生じます。  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> ||最大変位は RTP パケットの到着の間に検出します。 (ジッタとは、呼び出しの「揺れ」の尺度のことです)。高ジッタ値は、通常負荷またはオーバー ロードされたメディア サーバーでは、によって発生し、オーディオがゆがんでいる、または失われると。  <br/> |
|**RoundTrip** <br/> |int  <br/> ||リアルタイム転送プロトコル (RTP) パケットが別のエンドポイントとの間を往復するのに要する平均時間 (ミリ秒単位)。200 ミリ秒以下の往復時間が許容できる品質と見なされます。  <br/> この値が高い場合は、国際通話ルーティング、ルーティングの構成ミス、メディア サーバーの過負荷などの原因が考えられます。その結果、双方向のリアルタイムの音声会話が難しくなります。  <br/> |
|**RoundTripMax** <br/> |int  <br/> ||最大量 (単位はミリ秒) のリアルタイム転送プロトコル パケットを別のエンドポイントに移動し、バックアップに必要な。 200 ミリ秒以下の往復時間が許容できる品質と見なされます。  <br/> この値が高い場合は、国際通話ルーティング、ルーティングの構成ミス、メディア サーバーの過負荷などの原因が考えられます。その結果、双方向のリアルタイムの音声会話が難しくなります。  <br/> |
|**PacketLossRate** <br/> |float  <br/> ||リアルタイム転送プロトコル (RTP) パケット損失の平均レート (パケット損失は、RTP パケット、つまりインターネット経由で音声とビデオを転送するために使われるプロトコルの一種で、パケットが宛先に到達できなかったときに発生します)。この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーの過負荷などの原因が考えられます。パケット損失が発生すると、通常、音声のひずみや欠落が生じます。  <br/> |
|**PacketLossRateMax** <br/> |float  <br/> ||リアルタイム転送プロトコル (RTP) パケット損失の最大速度です。 (パケット ・ ロスは、送信先に到達するのには、RTP パケットをインターネット経由でオーディオとビデオを送信するために使用されるプロトコルが失敗したとき発生します)。高損失率の原因として多い混雑します。帯域幅が不足しています。ワイヤレスの輻輳または干渉します。または、オーバー ロードされたメディア サーバーを選択します。 パケット損失が発生すると、通常、音声のひずみや欠落が生じます。  <br/> |
|**PacketUtilization** <br/> |int  <br/> ||送信されるパケットの数です。  <br/> |
|**BandwidthEst** <br/> |int  <br/> ||セッションの最後に使用可能な一方向の帯域幅を推定します。 1 秒あたりのビット数で報告されます。  <br/> |
|**AppSharingPayloadDescription** <br/> |int  <br/> ||ペイロードを共有するアプリケーションの説明です。  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||一方向の遅延時間の合計金額です。 相対的な一方向の遅延時間は、クライアントとサーバー間の遅延を測定します。  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||一方向の遅延時間の平均量。 相対的な一方向の遅延時間は、クライアントとサーバー間の遅延を測定します。  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||一方向の遅延時間の最大数。 相対的な一方向の遅延時間は、クライアントとサーバー間の遅延を測定します。  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||合計の一方向のバースト発生数です。 「集中」の転送は、安定ではなく予期しない状態でのデータのフロー転送です。 このメトリックは、クライアントとサーバー間のデータ フローを測定します。  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||合計の一方向のバースト密度。 「集中」の転送は、安定ではなく予期しない状態でのデータのフロー転送です。 このメトリックは、クライアントとサーバー間のデータ フローを測定します。  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||合計の一方向のバーストの継続時間です。 「集中」の転送は、安定ではなく予期しない状態でのデータのフロー転送です。 このメトリックは、クライアントとサーバー間のデータ フローを測定します。  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||合計の一方向のギャップの発生数です。 「集中」の転送では、転送、安定したストリームではなく予期しない状態でのデータのフローギャップは、これらのバーストの間の遅延を指定します。 このメトリックは、クライアントとサーバー間のデータ フローを測定します。  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||合計の一方向のギャップ密度。 「集中」の転送では、転送、安定したストリームではなく予期しない状態でのデータのフローギャップは、これらのバーストの間の遅延を指定します。 このメトリックは、クライアントとサーバー間のデータ フローを測定します。  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||合計の一方向のギャップの期間です。 「集中」の転送では、転送、安定したストリームではなく予期しない状態でのデータのフローギャップは、これらのバーストの間の遅延を指定します。 このメトリックは、クライアントとサーバー間のデータ フローを測定します。  <br/> |
|**ApplicationSharingType** <br/> |varChar(256)  <br/> ||(共有またはビューアー) に、アプリケーション ロールとコンテンツを入力します。  <br/> |
|**RDPTileProcessingLatencyTotal** <br/> |float  <br/> ||リモート デスクトップ プロトコル (RDP) タイルの処理時間の合計です。 表示エクスペリエンスで遅延が長く高い合計に相当します。  <br/> |
|**RDPTileProcessingLatencyAverage** <br/> |float  <br/> ||リモート デスクトップ プロトコル (RDP) タイルの処理時間の平均値します。 表示エクスペリエンスで遅延が長く高い合計に相当します。  <br/> |
|**RDPTileProcessingLatencyMax** <br/> |float  <br/> ||リモート デスクトップ プロトコル (RDP) の最大の処理時間を並べて表示します。 表示エクスペリエンスで遅延が長く高い合計に相当します。  <br/> |
|**RDPTileProcessingLatencyBurstOccurrences** <br/> |int  <br/> ||リモート デスクトップ プロトコル (RDP) タイルの処理時間の出現をバーストします。 「集中」の転送は、安定ではなく予期しない状態でのデータのフロー転送です。  <br/> |
|**RDPTileProcessingLatencyBurstDensity** <br/> |float  <br/> ||リモート デスクトップ プロトコル (RDP) タイルの処理時間の密度をバーストします。 「集中」の転送は、安定ではなく予期しない状態でのデータのフロー転送です。  <br/> |
|**RDPTileProcessingLatencyBurstDuration** <br/> |float  <br/> ||リモート デスクトップ プロトコル (RDP) タイルの処理時間の期間をバーストします。 「集中」の転送は、安定ではなく予期しない状態でのデータのフロー転送です。  <br/> |
|**RDPTileProcessingLatencyGapOccurrences** <br/> |int  <br/> ||リモート デスクトップ プロトコル (RDP) タイルの処理時間でのギャップ発生数です。  <br/> |
|**RDPTileProcessingLatencyGapDensity** <br/> |float  <br/> ||リモート デスクトップ プロトコル (RDP) タイルの処理時間でのギャップ密度。 ギャップの低密度より優れた表示エクスペリエンスに相当します。  <br/> |
|**RDPTileProcessingLatencyGapDuration** <br/> |float  <br/> ||リモート デスクトップ プロトコル (RDP) タイルの処理時間の間隔の期間です。 短い間隔の期間は、表示エクスペリエンスを向上させるに似ています。  <br/> |
|**CaptureTileRateTotal** <br/> |float  <br/> ||(1 秒あたりのタイル) でキャプチャされたタイルの合計の割合。  <br/> |
|**CaptureTileRateAverage** <br/> |float  <br/> ||(1 秒あたりのタイル) でキャプチャされたタイルの平均レート。  <br/> |
|**CaptureTileRateMax** <br/> |float  <br/> ||(1 秒あたりのタイル) でキャプチャされたタイルの最大数です。  <br/> |
|**CaptureTileRateBurstOccurrences** <br/> |t  <br/> ||(1 秒あたりのタイル) でキャプチャされたタイルのレートでの出現箇所をバーストします。  <br/> |
|**CaptureTileRateBurstDensity** <br/> |float  <br/> ||(1 秒あたりのタイル) でキャプチャされたタイルのレートの密度をバーストします。  <br/> |
|**CaptureTileRateBurstDuration** <br/> |float  <br/> ||(1 秒あたりのタイル) でキャプチャされたタイルのレートでは、期間をバーストします。  <br/> |
|**CaptureTileRateGapOccurrences** <br/> |int  <br/> ||(1 秒あたりのタイル) でキャプチャされたタイルのレートでのギャップ発生数です。  <br/> |
|**CaptureTileRateGapDensity** <br/> |float  <br/> ||(1 秒あたりのタイル) でキャプチャされたタイルのレートでのギャップ密度。  <br/> |
|**CaptureTileRateGapDuration** <br/> |float  <br/> ||ギャップ時間 (1 秒あたりのタイル) でキャプチャされたタイルのレートです。  <br/> |
|**SpoiledTilePercentTotal** <br/> |float  <br/> ||ビューアーが届きませんでしたが代わりには破棄され、新しいコンテンツで上書きされるコンテンツの合計の割合。  <br/> |
|**SpoiledTilePercentAverage** <br/> |float  <br/> ||ビューアーが届きませんでしたが代わりには破棄され、新しいコンテンツで上書きされるコンテンツの割合に関する平均。  <br/> |
|**SpoiledTilePercentMax** <br/> |float  <br/> ||ビューアーが届きませんでしたが代わりには破棄され、新しいコンテンツで上書きされるコンテンツの最大の割合です。  <br/> |
|**SpoiledTilePercentBurstOccurrences** <br/> |int  <br/> ||ビューアーが届きませんでしたが代わりには破棄され、新しいコンテンツで上書きされるコンテンツの出現箇所をバーストします。  <br/> |
|**SpoiledTilePercentBurstDensity** <br/> |float  <br/> ||ビューアーが届きませんでしたが代わりには破棄され、新しいコンテンツで上書きされるコンテンツの密度をバーストします。  <br/> |
|**SpoiledTilePercentBurstDuration** <br/> |float  <br/> ||ビューアーが届きませんでしたが代わりに破棄され、新しい内容で上書きされるコンテンツの存続期間をバーストします。  <br/> |
|**SpoiledTilePercentGapOccurrences** <br/> |int  <br/> ||ビューアーが届きませんでしたが代わりには破棄され、新しいコンテンツで上書きされるコンテンツのギャップの発生数です。  <br/> |
|**SpoiledTilePercentGapDensity** <br/> |float  <br/> ||ビューアーが届きませんでしたが代わりには破棄され、新しいコンテンツで上書きされるコンテンツのギャップ密度。  <br/> |
|**SpoiledTilePercentGapDuration** <br/> |float  <br/> ||ビューアーが届きませんでしたが代わりには破棄され、新しいコンテンツで上書きされるコンテンツのギャップの期間です。  <br/> |
|**ScrapingFrameRateTotal** <br/> |float  <br/> ||グラフィックス ソースから scraped フレームの合計数です。  <br/> |
|**ScrapingFrameRateAverage** <br/> |float  <br/> ||グラフィックス ソースから scraped のフレームの数の平均値です。  <br/> |
|**ScrapingFrameRateMax** <br/> |float  <br/> ||グラフィックス ソースから scraped のフレームの最大数。  <br/> |
|**ScrapingFrameRateBurstOccurrences** <br/> |int  <br/> ||グラフィックス ソースから scraped のフレームの発生をバーストします。  <br/> |
|**ScrapingFrameRateBurstDensity** <br/> |float  <br/> ||グラフィックス ソースから scraped のフレームには、密度をバーストします。  <br/> |
|**ScrapingFrameRateBurstDuration** <br/> |float  <br/> ||グラフィックス ソースから scraped のフレームのデュレーションをバーストします。  <br/> |
|**ScrapingFrameRateGapOccurrences** <br/> |int  <br/> ||グラフィックス ソースから scraped のフレームでのギャップ発生数です。  <br/> |
|**ScrapingFrameRateGapDensity** <br/> |float  <br/> ||グラフィックス ソースから scraped のフレームでのギャップ密度。  <br/> |
|**ScrapingFrameRateGapDuration** <br/> |float  <br/> ||グラフィックス ソースから scraped のフレーム間隔の期間です。  <br/> |
|**IncomingTileRateTotal** <br/> |float  <br/> ||視聴者が受信すると受信フレーム レートの合計です。  <br/> |
|**IncomingTileRateAverage** <br/> |float  <br/> ||視聴者が受信すると受信フレーム レートの平均値します。  <br/> |
|**IncomingTileRateMax** <br/> |float  <br/> ||最大の受信では、視聴者が受信すると、レートが並べて表示します。  <br/> |
|**IncomingTileRateBurstOccurrences** <br/> |int  <br/> ||視聴者が受信すると、受信タイル レートの出現をバーストします。  <br/> |
|**IncomingTileRateBurstDensity** <br/> |float  <br/> ||視聴者が受信すると、受信タイル レートの密度をバーストします。  <br/> |
|**IncomingTileRateBurstDuration** <br/> |float  <br/> ||視聴者が受信すると、受信タイル レートの期間をバーストします。  <br/> |
|**IncomingTileRateGapOccurrences** <br/> |int  <br/> ||として視聴者が受信した受信タイル レートでのギャップ発生数です。  <br/> |
|**IncomingTileRateGapDensity** <br/> |float  <br/> ||として視聴者が受信した受信タイル レートでのギャップ密度。  <br/> |
|**IncomingTileRateGapDuration** <br/> |float  <br/> ||ギャップの受信タイル レートの期間は、視聴者が受信するとします。  <br/> |
|**IncomingFrameRateTotal** <br/> |float  <br/> ||視聴者が受信すると受信フレーム レートの合計です。  <br/> |
|**IncomingFrameRateAverage** <br/> |float  <br/> ||視聴者が受信すると受信フレーム レートの平均値します。  <br/> |
|**IncomingFrameRateMax** <br/> |float  <br/> ||ビューアーによって受信と受信したフレーム レートを最大します。  <br/> |
|**IncomingFrameRateBurstOccurrences** <br/> |int  <br/> ||視聴者が受信すると、受信したフレーム レートで出現回数をバーストします。  <br/> |
|**IncomingFrameRateBurstDensity** <br/> |float  <br/> ||視聴者が受信すると、受信したフレーム レートの密度をバーストします。  <br/> |
|**IncomingFrameRateBurstDuration** <br/> |float  <br/> ||視聴者が受信すると、受信したフレーム レートで期間をバーストします。  <br/> |
|**IncomingFrameRateGapOccurrences** <br/> |int  <br/> ||として視聴者が受信した受信フレーム レートでのギャップ発生数です。  <br/> |
|**IncomingFrameRateGapDensity** <br/> |float  <br/> ||として視聴者が受信した受信フレーム レートでのギャップ密度。  <br/> |
|**IncomingFrameRateDuration** <br/> |float  <br/> ||ギャップの受信フレーム レートでの期間は、視聴者が受信するとします。  <br/> |
|**OutgoingTileRateTotal** <br/> |float  <br/> ||送信者の送信タイル レートを合計します。  <br/> |
|**OutgoingTileRateAverage** <br/> |float  <br/> ||送信者の送信タイル レートを平均します。  <br/> |
|**OutgoingTileRateMax** <br/> |float  <br/> ||送信者の送信タイル レートを最大します。  <br/> |
|**OutgoingTileRateBurstOccurrences** <br/> |int  <br/> ||送信者の送信タイル レートでの出現をバーストします。  <br/> |
|**OutgoingTileRateBurstDensity** <br/> |float  <br/> ||送信者の送信タイル レートの密度をバーストします。  <br/> |
|**OutgoingTileRateBurstDuration** <br/> |float  <br/> ||送信者の送信タイル レートの期間をバーストします。  <br/> |
|**OutgoingTileRateGapOccurrences** <br/> |int  <br/> ||送信者の送信タイル レートでの出現回数を間隔。  <br/> |
|**OutgoingTileRateGapDensity** <br/> |float  <br/> ||送信者の送信タイル レートでのギャップ密度。  <br/> |
|**OutgoingTileRateGapDuration** <br/> |float  <br/> ||送信者の送信タイル レートでのギャップの期間です。  <br/> |
|**OutgoingFrameRateTotal** <br/> |float  <br/> ||送信者の送信フレーム レートを合計します。  <br/> |
|**OutgoingFrameRateAverage** <br/> |float  <br/> ||送信者の送信フレーム レートを平均します。  <br/> |
|**OutgoingFrameRateMax** <br/> |float  <br/> ||送信者の送信フレーム レートを最大します。  <br/> |
|**OutgoingFrameRateBurstOccurrences** <br/> |int  <br/> ||送信者の送信フレーム レートでの出現をバーストします。  <br/> |
|**OutgoingFrameRateBurstDensity** <br/> |float  <br/> ||送信者の送信フレーム レートの密度をバーストします。  <br/> |
|**OutgoingFrameRateBurstDuration** <br/> |float  <br/> ||送信者の送信フレーム レートの期間をバーストします。  <br/> |
|**OutgoingFrameRateGapOccurrences** <br/> |int  <br/> ||送信者の送信フレーム レートでの出現回数を間隔。  <br/> |
|**OutgoingFrameRateGapDensity** <br/> |float  <br/> ||送信者の送信フレーム レートでのギャップ密度。  <br/> |
|**OutgoingFrameRateGapDuration** <br/> |float  <br/> ||送信者の送信フレーム レートのギャップの期間です。  <br/> |
|**AverageRectangleHeight** <br/> |int  <br/> ||平均のビデオ解像度の高さ (ピクセル単位)。  <br/> |
|**AverageRectangleWidth** <br/> |int  <br/> ||平均のビデオ解像度の幅 (ピクセル単位)。  <br/> |
|**受信** <br/> |bit  <br/> ||受信の場合 (1 秒あたりのフレーム数) の平均フレーム レートです。  <br/> |
|**発信** <br/> |bit  <br/> ||平均のフレーム レート (1 秒あたりのフレーム数) で送信に対して。  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> ||1 は、ストリームの方向は、呼び出し元から呼び出し先を意味します。  <br/> 0 では、ストリームの方向は、呼び出し先から呼び出し元を表します。  <br/> |
   

