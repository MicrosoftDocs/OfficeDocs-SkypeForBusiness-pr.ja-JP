---
title: AppSharingStream テーブル
TOCTitle: AppSharingStream テーブル
ms:assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204808(v=OCS.15)
ms:contentKeyID: 48271788
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# AppSharingStream テーブル

 

_**トピックの最終更新日:** 2015-03-09_

AppSharingStream テーブルには、アプリケーション共有のストリームが使用するネットワークの QoE 測定値が含まれます。このテーブルは、Microsoft Lync Server 2013 で導入されました。


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
<td><p>dateTime</p></td>
<td><p>主/プライマリ、外部</p></td>
<td><p>セッションが開始した日時。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ、外部</p></td>
<td><p>同じ日付に、同時に開始したセッションを区別する順次識別子。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>主/プライマリ、外部</p></td>
<td><p>通話で使用されたビデオ回線の種類を表します。有効な値は次のとおりです。</p>
<ul>
<li><p>0 - 音声</p></li>
<li><p>1 - ビデオ</p></li>
<li><p>2 -- パノラマ ビデオ</p></li>
<li><p>3 – アプリケーション共有/デスクトップ共有</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>StreamID</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>アプリケーション共有ストリームの一意識別子。</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>RTP パケットの着信間に検出された平均ジッター (ジッターとは、通話の &quot;揺れ&quot; の測定値です)。通常、この値が高い場合は、輻輳やメディア サーバーの過負荷の原因が考えられます。その結果、音声のひずみや欠落が生じます。</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>RTP パケットの着信間に検出された最大ジッター (ジッターとは、通話の &quot;揺れ&quot; の測定値です)。通常、この値が高い場合は、輻輳やメディア サーバーの過負荷の原因が考えられます。その結果、音声のひずみや欠落が生じます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RoundTrip</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>リアルタイム転送プロトコル (RTP) パケットが別のエンドポイントとの間を往復するのに要する平均時間 (ミリ秒単位)。200 ミリ秒以下の往復時間が許容できる品質と見なされます。</p>
<p>この値が高い場合は、国際通話ルーティング、ルーティングの構成ミス、メディア サーバーの過負荷などの原因が考えられます。その結果、双方向のリアルタイムの音声会話が難しくなります。</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>リアルタイム転送プロトコル (RTP) パケットが別のエンドポイントとの間を往復するのに要する最大時間 (ミリ秒単位)。200 ミリ秒以下の往復時間が許容できる品質と見なされます。</p>
<p>この値が高い場合は、国際通話ルーティング、ルーティングの構成ミス、メディア サーバーの過負荷などの原因が考えられます。その結果、双方向のリアルタイムの音声会話が難しくなります。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>リアルタイム転送プロトコル (RTP) パケット損失の平均レート。(パケット損失は、RTP パケット、つまりインターネット経由で音声とビデオを転送するために使われるプロトコルの一種で、パケットが宛先に到達できなかったときに発生します。) この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーの過負荷などの原因が考えられます。パケット損失が発生すると、通常、音声のひずみや欠落が生じます。</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>リアルタイム転送プロトコル (RTP) パケット損失の最大レート。(パケット損失は、RTP パケット、つまりインターネット経由で音声とビデオを転送するために使われるプロトコルの一種で、パケットが宛先に到達できなかったときに発生します。) この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーの過負荷などの原因が考えられます。パケット損失が発生すると、通常、音声のひずみや欠落が生じます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>送信されたパケット数。</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEst</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>セッションの最後での、推定された一方向の帯域幅。ビット/秒で報告されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppSharingPayloadDescription</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>アプリケーション共有ペイロードの詳細。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayTotal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>一方向の遅延の合計時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayAverage</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>一方向の遅延の平均時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayMax</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>一方向の遅延の最大時間。相対的な一方向の遅延によって、クライアントとサーバーの間の遅延が測定されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>一方向のバーストの合計発生数。&quot;バースト的な&quot; 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>一方向のバーストの合計密度。&quot;バースト的な&quot; 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>一方向のバーストの合計期間。&quot;バースト的な&quot; 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>一方向のギャップの合計発生数。&quot;バースト的な&quot; 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。ギャップは、これらのバースト間の遅延を示します。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>一方向のギャップの合計密度。&quot;バースト的な&quot; 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。ギャップは、これらのバースト間の遅延を示します。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>一方向のギャップの合計期間。&quot;バースト的な&quot; 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。ギャップは、これらのバースト間の遅延を示します。この指標では、クライアントとサーバーの間のデータ フローが測定されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ApplicationSharingType</strong></p></td>
<td><p>varChar(256)</p></td>
<td><p></p></td>
<td><p>アプリケーション役割 (共有者または視聴者) とコンテンツ タイプ。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyTotal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>リモート デスクトップ プロトコル (RDP) タイルの合計の処理時間。この値が多いことは、表示に遅延が発生していることを示します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyAverage</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>リモート デスクトップ プロトコル (RDP) タイルの平均の処理時間。この値が多いことは、表示に遅延が発生していることを示します。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyMax</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>リモート デスクトップ プロトコル (RDP) タイルの最大の処理時間。この値が多いことは、表示に遅延が発生していることを示します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>リモート デスクトップ プロトコル (RDP) タイルの処理時間でのバースト発生数。&quot;バースト的な&quot; 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyBurstDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>リモート デスクトップ プロトコル (RDP) タイルの処理時間でのバースト密度。&quot;バースト的な&quot; 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>リモート デスクトップ プロトコル (RDP) タイルの処理時間でのバースト持続時間。&quot;バースト的な&quot; 伝送とは、安定的なストリームではなく、予測できないバーストでデータが流れている伝送のことです。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>リモート デスクトップ プロトコル (RDP) タイルの処理時間でのギャップ発生数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyGapDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>リモート デスクトップ プロトコル (RDP) タイルの処理時間でのギャップ密度。ギャップ密度が低いことは、表示エクスペリエンスが良いことを示します。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyGapDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>リモート デスクトップ プロトコル (RDP) タイルの処理時間でのギャップ持続時間。持続時間が短いことは、表示エクスペリエンスが良いことを示します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateTotal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>キャプチャされたタイルの合計のレート (タイル/秒)。</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateAverage</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>キャプチャされたタイルの平均のレート (タイル/秒)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateMax</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>キャプチャされたタイルの最大のレート (タイル/秒)。</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>キャプチャされたタイルのレート (タイル/秒) でのバースト発生数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>キャプチャされたタイルのレート (タイル/秒) でのバースト密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>キャプチャされたタイルのレート (タイル/秒) でのバースト持続時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>キャプチャされたタイルのレート (タイル/秒) でのギャップ発生数。</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>キャプチャされたタイルのレート (タイル/秒) でのギャップ密度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateGapDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>キャプチャされたタイルのレート (タイル/秒) でのギャップ持続時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentTotal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>視聴者に到達せず、新規のコンテンツによって破棄されて、上書きされたコンテンツの合計の割合。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentAverage</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>視聴者に到達せず、新規のコンテンツによって破棄されて、上書きされたコンテンツの平均の割合。</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentMax</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>視聴者に到達せず、新規のコンテンツによって破棄されて、上書きされたコンテンツの最大の割合。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>視聴者に到達せず、新規のコンテンツによって破棄されて、上書きされたコンテンツでのバースト発生数。</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentBurstDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>視聴者に到達せず、新規のコンテンツによって破棄されて、上書きされたコンテンツでのバースト密度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentBurstDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>視聴者に到達せず、新規のコンテンツによって破棄されて、上書きされたコンテンツでのバースト持続時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>視聴者に到達せず、新規のコンテンツによって破棄されて、上書きされたコンテンツでのギャップ発生数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentGapDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>視聴者に到達せず、新規のコンテンツによって破棄されて、上書きされたコンテンツでのギャップ密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentGapDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>視聴者に到達せず、新規のコンテンツによって破棄されて、上書きされたコンテンツでのギャップ持続時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateTotal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>グラフィックス ソースからスクレープされたフレームの合計数。</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateAverage</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>グラフィックス ソースからスクレープされたフレームの平均数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateMax</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>グラフィックス ソースからスクレープされたフレームの最大数。</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>グラフィックス ソースからスクレープされたフレームのバースト発生数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>グラフィックス ソースからスクレープされたフレームのバースト密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>グラフィックス ソースからスクレープされたフレームのバースト持続時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>グラフィックス ソースからスクレープされたフレームのギャップ発生数。</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>グラフィックス ソースからスクレープされたフレームのギャップ密度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateGapDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>グラフィックス ソースからスクレープされたフレームのギャップ持続時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateTotal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>閲覧者が受信するときの合計受信フレーム レート。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateAverage</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>閲覧者が受信するときの平均受信フレーム レート。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateMax</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>閲覧者が受信するときの最大受信タイル レート。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>閲覧者が受信する受信タイル レートでのバースト発生数。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>閲覧者が受信する受信タイル レートでのバースト密度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>閲覧者が受信する受信タイル レートでのバースト持続時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>閲覧者が受信する受信タイル レートでのギャップ発生数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>閲覧者が受信する受信タイル レートでのギャップ密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateGapDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>閲覧者が受信する受信タイル レートでのギャップ持続時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateTotal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>閲覧者が受信するときの合計受信フレーム レート。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateAverage</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>閲覧者が受信するときの平均受信フレーム レート。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateMax</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>閲覧者が受信するときの最大受信フレーム レート。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>閲覧者が受信する受信フレーム レートでのバースト発生数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>閲覧者が受信する受信フレーム レートでのバースト密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>閲覧者が受信する受信フレーム レートでのバースト持続時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>閲覧者が受信する受信フレーム レートでのギャップ発生数。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>閲覧者が受信する受信フレーム レートでのギャップ密度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>閲覧者が受信する受信フレーム レートでのギャップ持続時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateTotal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>送信者の合計の送信タイル レート。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateAverage</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>送信者の平均の送信タイル レート。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateMax</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>送信者の最大の送信タイル レート。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>送信者の送信タイル レートのバースト発生数。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>送信者の送信タイル レートのバースト密度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>送信者の送信タイル レートのバースト持続時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>送信者の送信タイル レートのギャップ発生数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>送信者の送信タイル レートのギャップ密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateGapDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>送信者の送信タイル レートのギャップ持続時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateTotal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>送信者の合計の送信フレーム レート。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateAverage</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>送信者の平均の送信フレーム レート。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateMax</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>送信者の最大の送信フレーム レート。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>送信者の送信フレーム レートのバースト発生数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>送信者の送信フレーム レートのバースト密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>送信者の送信フレーム レートのバースト持続時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>送信者の送信フレーム レートのギャップ発生数。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>送信者の送信フレーム レートのギャップ密度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateGapDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>送信者の送信フレーム レートのギャップ持続時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>AverageRectangleHeight</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>平均のビデオ解像度の高さ (ピクセル)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AverageRectangleWidth</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>平均のビデオ解像度の幅 (ピクセル)。</p></td>
</tr>
<tr class="even">
<td><p><strong>Inbound</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>着信の平均フレーム レート (フレーム/秒)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Outbound</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>発信の平均フレーム レート (フレーム/秒)。</p></td>
</tr>
<tr class="even">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>1 は、ストリームの方向が発信者から呼び出し先へ向かうことを意味します。</p>
<p>0 は、ストリームの方向が呼び出し先から発信者へ向かうことを意味します。</p></td>
</tr>
</tbody>
</table>

