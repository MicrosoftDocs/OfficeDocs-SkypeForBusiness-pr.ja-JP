---
title: 'Lync Server 2013: AppSharingStream テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AppSharingStream table
ms:assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204808(v=OCS.15)
ms:contentKeyID: 48183852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c00a606981ab09d370d5aac390aa244a31063f24
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738417"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingstream-table-in-lync-server-2013"></a>Lync Server 2013 の AppSharingStream テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-02-21_

AppSharingStream テーブルには、アプリケーション共有に使用されるネットワークストリームのエクスペリエンスのメトリックの質が含まれています。 この表は、Microsoft Lync Server 2013 で導入されました。


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
<td><p>プライマリ、外部</p></td>
<td><p>セッションが開始された日付と時刻。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>プライマリ、外部</p></td>
<td><p>同じ日付と同時に開始したセッションを区別するために使用されるシーケンシャル識別子。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>プライマリ、外部</p></td>
<td><p>通話で使用されるビデオラインの種類を表します。 有効な値は次のとおりです。</p>
<ul>
<li><p>0–音声</p></li>
<li><p>1-ビデオ</p></li>
<li><p>2-パノラマビデオ</p></li>
<li><p>3-アプリケーション/デスクトップ共有</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>StreamID</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>アプリケーション共有ストリームの一意の識別子。</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>RTP パケットの着信間に検出された平均ジッター (ジッターとは、通話の "揺れ" の測定値です)。 (ジッタは、通話の&quot;shakiness&quot;の尺度です)。通常、高ジッターの値は、輻輳または過負荷のメディアサーバーによって発生し、音声が歪むか、失われる原因となります。</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>RTP パケット着信の間の最大ジッターが検出されました。 (ジッタは、通話の&quot;shakiness&quot;の尺度です)。通常、高ジッターの値は、輻輳または過負荷のメディアサーバーによって発生し、音声が歪むか、失われる原因となります。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RoundTrip</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>リアルタイム転送プロトコル (RTP) パケットが別のエンドポイントとの間を往復するのに要する平均時間 (ミリ秒単位)。200 ミリ秒以下の往復時間が許容できる品質と見なされます。</p>
<p>この値が高い場合は、国際通話ルーティング、ルーティングの構成ミス、メディア サーバーの過負荷などの原因が考えられます。その結果、双方向のリアルタイムの音声会話が難しくなります。</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>リアルタイムトランスポートプロトコルパケットが別のエンドポイントに移動してから戻るために必要な最大 (ミリ秒単位)。 200 ミリ秒以下の往復時間が許容できる品質と見なされます。</p>
<p>この値が高い場合は、国際通話ルーティング、ルーティングの構成ミス、メディア サーバーの過負荷などの原因が考えられます。その結果、双方向のリアルタイムの音声会話が難しくなります。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>リアルタイム転送プロトコル (RTP) パケット損失の平均レート。(パケット損失は、RTP パケット、つまりインターネット経由で音声とビデオを転送するために使われるプロトコルの一種で、パケットが宛先に到達できなかったときに発生します)。この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーの過負荷などの原因が考えられます。パケット損失が発生すると、通常、音声のひずみや欠落が生じます。</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>リアルタイムトランスポートプロトコル (RTP) パケット損失の最大速度。 (パケットの損失は、RTP パケット、インターネット上でのオーディオとビデオの伝送に使用されるプロトコル)、宛先への到達に失敗した場合に発生します。)通常、高損失率は輻輳が原因で発生します。帯域幅の不足。ワイヤレスの輻輳または妨害または、オーバーロードされたメディアサーバー。 パケット損失が発生すると、通常、音声のひずみや欠落が生じます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>送信されたパケットの数です。</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEst</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>セッションの終了時に提供される推定される一方向の帯域幅。 1秒あたりのビット数で報告されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppSharingPayloadDescription</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>アプリケーション共有ペイロードの説明。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>一方向の待機時間の合計。 相対的な一方向の待ち時間は、クライアントとサーバーの間の遅延を測定します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>一方向の待ち時間の平均値。 相対的な一方向の待ち時間は、クライアントとサーバーの間の遅延を測定します。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>一方向の待機時間の上限。 相対的な一方向の待ち時間は、クライアントとサーバーの間の遅延を測定します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>1方向のバースト発生の合計。 "Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。 このメトリックは、クライアントとサーバー間のデータフローを計測します。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>全体的な1方向バースト密度。 "Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。 このメトリックは、クライアントとサーバー間のデータフローを計測します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>一方向のバースト期間の合計。 "Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。 このメトリックは、クライアントとサーバー間のデータフローを計測します。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>一方向のギャップ出現の合計。 "Bursty" 伝送とは、安定したストリームではなく、予期しないバーストでデータが流れる伝送です。ギャップは、このようなバーストの間の遅延を示します。 このメトリックは、クライアントとサーバー間のデータフローを計測します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>一方向のギャップの密度の合計。 "Bursty" 伝送とは、安定したストリームではなく、予期しないバーストでデータが流れる伝送です。ギャップは、このようなバーストの間の遅延を示します。 このメトリックは、クライアントとサーバー間のデータフローを計測します。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>一方向のギャップ期間の合計。 "Bursty" 伝送とは、安定したストリームではなく、予期しないバーストでデータが流れる伝送です。ギャップは、このようなバーストの間の遅延を示します。 このメトリックは、クライアントとサーバー間のデータフローを計測します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ApplicationSharingType</strong></p></td>
<td><p>varChar (256)</p></td>
<td></td>
<td><p>アプリケーションロール (共有先またはビューアー) とコンテンツタイプ。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>リモートデスクトッププロトコル (RDP) タイルの合計処理時間。 表示環境では、合計の遅延が長くなります。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Rdp タイル処理</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>リモートデスクトッププロトコル (RDP) タイルの平均処理時間。 表示環境では、合計の遅延が長くなります。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>リモートデスクトッププロトコル (RDP) タイルの最大処理時間。 表示環境では、合計の遅延が長くなります。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>リモートデスクトッププロトコル (RDP) タイルの処理時間でのバースト発生。 "Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>リモートデスクトッププロトコル (RDP) タイルの処理時間のバースト密度。 "Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>リモートデスクトッププロトコル (RDP) タイルの処理時間のバースト時間。 "Bursty" 伝送とは、安定したストリームと比べて予期しないバーストでデータが流れる伝送です。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>リモートデスクトッププロトコル (RDP) タイルの処理時間のギャップの出現回数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>リモートデスクトッププロトコル (RDP) タイルの処理時間のギャップの密度。 隙間が小さいほど、表示エクスペリエンスが向上します。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>リモートデスクトッププロトコル (RDP) タイルの処理時間の間隔。 短い間隔の期間は、表示感が向上するようになります。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>キャプチャされたタイルの合計レート (1 秒あたりのタイル数)</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>キャプチャされたタイルの平均速度 (1 秒あたりのタイル数)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>キャプチャされたタイルの最大速度 (1 秒あたりのタイル数)</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateBurstOccurrences</strong></p></td>
<td><p>t</p></td>
<td></td>
<td><p>キャプチャされたタイルの速度 (1 秒あたりのタイル) でバーストが発生します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>キャプチャされたタイルの速度 (1 秒あたりのタイル数) のバースト密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>キャプチャされたタイルの割合でのバースト時間 (1 秒あたりのタイル数)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>キャプチャされたタイルの比率 (1 秒あたりのタイル数) でのギャップ出現回数。</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>キャプチャされたタイル (1 秒あたりのタイル数) の間隔の間隔。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>キャプチャされたタイルの割合の間隔 (1 秒あたりのタイル数)</p></td>
</tr>
<tr class="even">
<td><p><strong>損失タイル</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>閲覧者に届かなかったが、破棄され、最新のコンテンツによって上書きされたコンテンツの割合の合計。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>閲覧者に届かなかったが、新しいコンテンツによって破棄されて上書きされたコンテンツの平均割合。</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>閲覧者に届かなかったが、新しいコンテンツによって破棄されて上書きされたコンテンツの最大パーセンテージ。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>閲覧者に届かなかったが、新しいコンテンツによって破棄されて上書きされたコンテンツのバースト発生。</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>ビューアーに届かなかったが、新しいコンテンツによって破棄されて上書きされたコンテンツのバースト密度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>ビューアーに届かなかったが、新しいコンテンツによって破棄されて上書きされたコンテンツのバースト時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>閲覧者に届かなかったが、新しいコンテンツによって破棄されて上書きされたコンテンツの Gap オカレンス。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>ビューアーに届かなかったが、新しいコンテンツで破棄されて上書きされたコンテンツの Gap 濃度。</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>ビューアーに届かなかったが、新しいコンテンツによって破棄されて上書きされたコンテンツの間隔の期間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>グラフィックスソースから scraped フレームの合計数です。</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>グラフィックスソースから scraped フレームの平均数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>グラフィックスソースから scraped フレームの最大数。</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>グラフィックソースからフレームの scraped が発生します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>グラフィックスソースからのフレーム scraped のバースト密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>グラフィックスソースからのフレーム scraped のバースト時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>グラフィックソースから、フレーム内の Gap オカレンスが scraped ます。</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>グラフィックスソースから scraped フレームの間隔の濃度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>グラフィックスソースから scraped フレームの間隔を指定します。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>視聴者が受信したフレームの合計料金。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>視聴者が受信したフレームの平均速度。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>視聴者が受信した最大受信タイルレート。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>視聴者が受信したタイルレートでのバースト発生</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>視聴者が受信したタイルレートのバースト密度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>閲覧者が受信した受信タイルレートのバースト時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>閲覧者が受信したタイルレートのギャップが表示されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>閲覧者によって受信された、受信タイルレートのギャップの密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>視聴者が受信したタイルレートの間隔。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>視聴者が受信したフレームの合計料金。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>視聴者が受信したフレームの平均速度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>視聴者が受信した受信フレームレートの上限。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>視聴者が受信したフレームレートのバーストが発生します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>視聴者が受信したフレームレートのバースト密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>ビューアーで受信した受信フレームレートのバースト時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>閲覧者が受信したフレームレートのギャップが表示されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>視聴者が受信したフレームレートの間隔。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>視聴者が受信したフレームレートの間隔。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>送信者の合計送信タイルレート。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>送信者の平均送信タイルレート。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>送信者の最大送信タイルレート。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>送信者の送信タイルレートのバーストが発生します。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>送信者の送信タイルレートのバースト密度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>送信者の送信タイルレートのバースト時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>送信者に対して、送信タイルレートのギャップが発生します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>送信者の送信タイルレートの間隔。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>送信者の送信タイルレートの間隔。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>送信者の総送信フレームレート。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>送信者の平均送信フレームレート。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>送信者の最大送信フレームレート。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>送信者の送信フレームレートでのバースト発生。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>送信者の送信フレームレートのバースト密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>送信者の送信フレームレートのバースト時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>送信者に対して送信されるフレームレートのギャップ。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>送信者の発信フレームレートのギャップの密度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>送信者の発信フレームレートの間隔。</p></td>
</tr>
<tr class="even">
<td><p><strong>AverageRectangleHeight</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>平均ビデオ解像度の高さ (ピクセル単位)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AverageRectangleWidth</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>平均ビデオ解像度の幅 (ピクセル単位)。</p></td>
</tr>
<tr class="even">
<td><p><strong>トラフィック</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>受信伝送の平均フレームレート (1 秒あたりのフレーム数)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>発信</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>送信時の平均フレームレート (1 秒あたりのフレーム数)。</p></td>
</tr>
<tr class="even">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>1ストリームの方向は、呼び出し元から呼び出し先へとなります。</p>
<p>0は、ストリームの方向を呼び出し元から呼び出し元に転送します。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

