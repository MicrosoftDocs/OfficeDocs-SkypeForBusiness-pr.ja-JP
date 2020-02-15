---
title: Lync Server 2013 メディアトラフィックのネットワーク帯域幅要件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network bandwidth requirements for media traffic
ms:assetid: 83e83b16-0f0e-4d87-901a-0faa4618cdc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688118(v=OCS.15)
ms:contentKeyID: 49733716
ms.date: 09/25/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f02f87e0cc7adc9cdfbd5e7ba1a9b7a4a6b736ee
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-bandwidth-requirements-for-media-traffic-in-lync-server-2013"></a>Lync Server 2013 でのメディアトラフィックのネットワーク帯域幅要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2015-09-24_

ネットワークの計画で重要な部分は、Lync Server によって生成されるメディア トラフィックをネットワークが処理できることを確認することです。このセクションは、目的のメディア トラフィックを計画する際に役立ちます。

<div>

## <a name="media-traffic-network-usage"></a>メディア トラフィック ネットワークの使用

メディア トラフィックの帯域幅使用量の計算は、使用されるコーデック、解像度、アクティビティ レベルなど、変数の数が多いため、困難になる可能性があります。 帯域幅使用量を決める要素に、使用されるコーデックとストリームのアクティビティがありますが、この 2 つの要素はシナリオごとに違いがあります。 次の表に、Lync Server 2013 のシナリオで一般的に使用されるオーディオコーデックの一覧を示します。

### <a name="audio-codec-bandwidth"></a>音声コーデックの帯域幅

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>音声コーデック</th>
<th>シナリオ</th>
<th>音声ペイロード ビットレート (KBPS)</th>
<th>帯域幅 - 音声ペイロードおよび IP ヘッダーのみ (Kbps)</th>
<th>帯域幅 - 音声ペイロード、IP ヘッダー、UDP、RTP、および SRTP (Kbps)</th>
<th>帯域幅 - 音声ペイロード、IP ヘッダー、UDP、RTP、SRTP および前方向エラー訂正 (Kbps)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTAudio (広帯域)</p></td>
<td><p>ピアツーピア</p></td>
<td><p>29.0</p></td>
<td><p>45.0</p></td>
<td><p>57.0</p></td>
<td><p>86.0</p></td>
</tr>
<tr class="even">
<td><p>RTAudio (狭帯域)</p></td>
<td><p>ピアツーピア、PSTN</p></td>
<td><p>11.8</p></td>
<td><p>27.8</p></td>
<td><p>39.8</p></td>
<td><p>51.6</p></td>
</tr>
<tr class="odd">
<td><p>G.722</p></td>
<td><p>会議</p></td>
<td><p>64.0</p></td>
<td><p>80.0</p></td>
<td><p>95.6</p></td>
<td><p>159.6</p></td>
</tr>
<tr class="even">
<td><p>G.722 Stereo</p></td>
<td><p>ピアツーピア、電話会議</p></td>
<td><p>128.0</p></td>
<td><p>144.0</p></td>
<td><p>159.6</p></td>
<td><p>223.6</p></td>
</tr>
<tr class="odd">
<td><p>G 711</p></td>
<td><p>PSTN、会議</p></td>
<td><p>64.0</p></td>
<td><p>80.0</p></td>
<td><p>92.0</p></td>
<td><p>156.0</p></td>
</tr>
<tr class="even">
<td><p>Siren</p></td>
<td><p>会議</p></td>
<td><p>16.0</p></td>
<td><p>32.0</p></td>
<td><p>47.6</p></td>
<td><p>63.6</p></td>
</tr>
</tbody>
</table>


この表の帯域幅数は、20ms パケット化 (50 パケット/秒) に基づいており Siren および G.722 では、電話会議シナリオからのセキュア リアルタイム転送プロトコル (SRTP) による追加オーバーヘッドが含まれ、ストリームが 100% アクティブであることが前提となっています。 前方向エラー訂正 (FEC) は、リンク上にパケット損失がある場合に、音声ストリームの品質確保を支えるために動的に使用されます。

G.722 コーデックのステレオバージョンは、Lync Room System に基づくシステムによって使用されます。これにより、ステレオマイクキャプチャが可能になり、会議室で複数の話者を識別しやすくなります。

ビデオの場合、既定のコーデックは、H.264/MPEG-4 Part 10 Advanced Video Coding 標準とその時間的スケーラビリティのためのスケーラブルなビデオ コーディング拡張機能です。 Lync 2010 または Office Communicator 2007 R2 クライアントとの相互運用性を維持するために、Lync 2013 とレガシクライアント間のピアツーピア通話には RTVideo コーデックが引き続き使用されます。 Lync 2013 と従来のクライアントの両方を使用する電話会議セッションでは、Lync 2013 エンドポイントは両方のビデオコーデックを使用してビデオをエンコードし、bitstream を Lync 2013 および RTVideo bitstream に Lync 2010 または Office Communicator 2007 R2 クライアントに送信します。

必要な帯域幅は、解像度、品質、およびフレーム レートによって決まります。 各解像度で、次の 2 つのビット レートが関与します。

  - **[最大ペイロードビットレート**   ] この解像度でサポートされている最大フレームレートでの Lync 2013 エンドポイントの解決に使用されるビットレートです。 品質とフレーム レートが最も高いビデオを可能にするため、この値が関与します。

  - **最小ペイロードビットレート**   これは、Lync 2013 エンドポイントが次の低解像度に切り替わるビットレートです。 特定の解像度を保証するために、使用可能なビデオペイロードビットレートがこの最小ビットレートを下回っている必要はありません。 この値はおもしろいので、最大ビットレートが使用できない、または現実的ではない場合に考えられる最小値を知ることができます。 一部のユーザーにとっては、低ビットレートのビデオが許容できないビデオの使用感を持つと考えられる場合があるため、これらの最小ビデオペイロードのビットレートを検討するときには注意してください。 ユーザーがほとんどまたはまったく動かないビデオの場合は、実際のビットレートが一時的に最小ビットレートよりも低くなることがあります。

Lync 2013 は、多くの解像度をサポートしています。 異なるネットワーク帯域幅に合わせて調整し、クライアントの機能を受け取ることができます。 さらに、Lync 2013 の既定の縦横比は16:9 に変更されました。 16:9 の縦横比でキャプチャできない Web カメラのために、4:3 の縦横比も引き続きサポートされています。

### <a name="video-resolution-bandwidth"></a>ビデオ解像度の帯域幅

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>ビデオ コーデック</th>
<th>解像度と縦横比</th>
<th>最大ビデオ ペイロード ビットレート (Kbps)</th>
<th>最小ビデオ ペイロード ビットレート (Kbps)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>.H</p></td>
<td><p>320x180 (16:9)</p>
<p>212x160 (4:3)</p></td>
<td><p>250</p></td>
<td><p>15 </p></td>
</tr>
<tr class="even">
<td><p>「264/RTVideo」</p></td>
<td><p>424x240 (16:9))</p>
<p>320 x 240 (4:3</p></td>
<td><p>350</p></td>
<td><p>100</p></td>
</tr>
<tr class="odd">
<td><p>.H</p></td>
<td><p>480x270 (16:9)</p>
<p>424x320 (4:3)</p></td>
<td><p>450</p></td>
<td><p>200</p></td>
</tr>
<tr class="even">
<td><p>「264/RTVideo」</p></td>
<td><p>640x360 (16:9)</p>
<p>640x480 (4:3)</p></td>
<td><p>800</p></td>
<td><p>300</p></td>
</tr>
<tr class="odd">
<td><p>.H</p></td>
<td><p>848x480 (16:9)</p></td>
<td><p>1500</p></td>
<td><p>400</p></td>
</tr>
<tr class="even">
<td><p>.H</p></td>
<td><p>960x540 (16:9)</p></td>
<td><p>2000</p></td>
<td><p>500</p></td>
</tr>
<tr class="odd">
<td><p>「264/RTVideo」</p></td>
<td><p>1280x720 (16:9)</p></td>
<td><p>2500</p></td>
<td><p>700</p></td>
</tr>
<tr class="even">
<td><p>.H</p></td>
<td><p>1920x1080 (16:9)</p></td>
<td><p>4000</p></td>
<td><p>1500</p></td>
</tr>
<tr class="odd">
<td><p>「264/RTVideo」</p></td>
<td><p>解像度 960x144 (20:3)</p></td>
<td><p>500</p></td>
<td><p>15 </p></td>
</tr>
<tr class="even">
<td><p>.H</p></td>
<td><p>1280x192 (20:3)</p></td>
<td><p>1000</p></td>
<td><p>250</p></td>
</tr>
<tr class="odd">
<td><p>.H</p></td>
<td><p>解像度 1920x288 (20:3)</p></td>
<td><p>2000</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


ビデオの FEC は、使用される場合ビデオ ペイロード ビットレートに含まれます。このため、ビデオ FEC を含む場合と含まない場合で別々の値はありません。

エンドポイントは、音声またはビデオ パケットを連続的にストリーミングするわけではありません。 シナリオごとにさまざまなレベルのストリーム アクティビティがあり、このレベルからストリームに対するパケットの送信頻度が分かります。 ストリーム アクティビティは、メディアとシナリオに左右されますが、使用されるコーデックの影響は受けません。 ピアツーピア シナリオでは、次のようになります。

  - エンドポイントは、ユーザーが話しているときだけ、音声ストリームを送信します。

  - 両方の参加者が音声ストリームを受け取ります。

  - ビデオが使用される場合、通話全体を通じて、両方のエンドポイントがビデオ ストリームを送受信します。

  - 動きがほとんど、またはまったくないビデオ シーンの場合、ビデオ コーデックは変更のないビデオの領域のエンコーディングをスキップするので、実際のビットレートが一時的に非常に低下することがあります。

電話会議シナリオでは、次のようになります。

  - エンドポイントは、ユーザーが話しているときだけ、音声ストリームを送信します。

  - すべての参加者が音声ストリームを受け取ります。

  - ビデオが使用されている場合、すべての参加者は最大 5 つの受信ビデオ ストリームと 1 つのパノラマ (たとえば、縦横比 20:3) ビデオ ストリームを受信できます。既定では、5 つの受信ビデオ ストリームはアクティブな発表者履歴に基づきますが、ユーザーはビデオ ストリームを受信する参加者を手動で選択することもできます。

  - ユーザーの送信ビデオ ストリームを有効にしている各参加者は、1 つ以上のビデオ ストリームを送信します。 Lync 2013 は、最大5つのビデオストリームを送信する機能を追加して、すべての受信側クライアントのビデオ品質を最適化します。 実際に送信されるビデオ ストリームの数は、CPU の能力、利用可能なアップリンク帯域幅、特定のビデオ ストリームを要求している受信クライアントの数に基づいて、送信側によって決定されます。 最も一般的なものは、レガシ クライアントが会議に参加している場合で、1 つの H.264 と 1 つの RTVideo ビデオ ストリームが送信されます。 もう 1 つのよくあるシナリオでは、受信側の異なる要求に対応するため、複数の H.264 ビデオ ストリームが (たとえば、異なるビデオ解像度で) 送信されます。

音声およびビデオ メディア用のリアルタイム転送プロトコル (RTP) トラフィックで必要な帯域幅以外に、リアルタイム転送制御プロトコル (RTCP) でも帯域幅が必要です。 RTCP は、RTP ストリームの統計情報の報告やアウトオブバンドの制御に使用されます。 計画の際には、RTCP トラフィックに関する次の表の帯域幅の数値を参照してください。 これらの値は、RTCP で使用される最大帯域幅を示し、制御データが違うため音声ストリームとビデオ ストリームとでは違いがあります。

### <a name="rtcp-bandwidth"></a>RTCP の帯域幅

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>メディア</th>
<th>RTCP の最大帯域幅 (Kbps)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>オーディオ</p></td>
<td><p>5 </p></td>
</tr>
<tr class="even">
<td><p>ビデオ (H.264 または RTVideo の一方のみを送受信)</p></td>
<td><p>10 </p></td>
</tr>
<tr class="odd">
<td><p>ビデオ (H.264 と RTVideo の両方を送受信)</p></td>
<td><p>15 </p></td>
</tr>
</tbody>
</table>


容量計画では、次の 2 つの帯域幅が関与します。

  - **[最大帯域幅 (FEC**   なし)] ストリームが消費する最大帯域幅。これには、ストリームの一般的な動作や、FEC なしでシナリオで使用される一般的なコーデックなどが含まれます。この値は、ストリームのアクティビティ レベルが 100% で、FEC の使用の原因になるパケット損失がない場合の帯域幅です。この値は、与えられたシナリオでコーデックの使用を可能にするために割り当てる必要のある帯域幅を計算する場合に関与します。 

  - **FEC の最大帯域幅**   は、ストリームの一般的な動作と、FEC を使用したシナリオで使用される一般的なコーデックを含む、ストリームが消費する最大帯域幅です。 この値は、ストリームのアクティビティ レベルが 100% で、品質向上のための FEC の使用の原因となるパケット損失がある場合の帯域幅です。 この値は、与えられたシナリオでのコーデックの使用とパケット損失状態での品質確保目的の FEC の使用を可能にするために割り当てる必要のある帯域幅を計算する場合に関与します。 

また、次の表に、帯域幅の**標準**値を示します。 これは、ストリームの一般的なアクティビティやシナリオで使用される一般的なコーデックなど、ストリームが消費する平均帯域幅です。 この帯域幅を使用して、メディアトラフィックで消費される帯域幅のおおよその程度を設定できますが、容量計画には使用しないことをお勧めします。これは、アクティビティレベルが平均より大きい場合に個々の呼び出しがこの値を超えるためです。 以下の表にある一般的なビデオストリームの帯域幅は、測定された顧客データで見られるように、さまざまなビデオ解像度の組み合わせに基づいています。 たとえば、ピアツーピアセッションでは、大多数のユーザーが既定のビデオレンダリングウィンドウを使用し、ユーザーのパーセンテージによっては、より多くのビデオ解像度を許可するように Lync アプリケーションを拡大または最大化します。

次の各表では、さまざまなシナリオを対象に、これら 3 つの帯域幅の値を示します。

### <a name="audiovideo-capacity-planning-for-peer-to-peer-sessions"></a>ピアツーピア セッションの音声/ビデオの容量計画

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>メディア</th>
<th>コーデック</th>
<th>標準的なストリーム帯域幅 (Kbps)</th>
<th>FEC を使用しない場合のストリームの最大帯域幅</th>
<th>FEC を使用する場合のストリームの最大帯域幅</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>オーディオ</p></td>
<td><p>RTAudio (広帯域)</p></td>
<td><p>39.8</p></td>
<td><p>62</p></td>
<td><p>91</p></td>
</tr>
<tr class="even">
<td><p>オーディオ</p></td>
<td><p>RTAudio (狭帯域)</p></td>
<td><p>29.3</p></td>
<td><p>44.8</p></td>
<td><p>56.6</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2013 エンドポイントを呼び出すときのメインビデオ</p></td>
<td><p>.H</p></td>
<td><p>460</p></td>
<td><p>4010 (最大解像度 1920x1080 の場合)</p></td>
<td><p>該当なし</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 または Office Communicator 2007 R2 エンドポイントを呼び出すときのメインビデオ</p></td>
<td><p>RTVideo</p></td>
<td><p>460</p></td>
<td><p>2510 (最大解像度 1280x720 の場合)</p></td>
<td><p>該当なし</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2013 エンドポイントを呼び出すときのパノラマビデオ</p></td>
<td><p>.H</p></td>
<td><p>190</p></td>
<td><p>2010 (最大解像度 1920x288 の場合)</p></td>
<td><p>該当なし</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 または Office Communicator 2007 R2 エンドポイントを呼び出すときのパノラマビデオ</p></td>
<td><p>RTVideo</p></td>
<td><p>190</p></td>
<td><p>510 (最大解像度 960x144 の場合)</p></td>
<td><p>該当なし</p></td>
</tr>
</tbody>
</table>


### <a name="audiovideo-capacity-planning-for-conferences"></a>会議の音声ビデオの容量計画

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>メディア</th>
<th>標準的なコーデック</th>
<th>標準的なストリーム帯域幅 (Kbps)</th>
<th>FEC を使用しない場合のストリームの最大帯域幅</th>
<th>FEC を使用する場合のストリームの最大帯域幅</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>オーディオ</p></td>
<td><p>G.722</p></td>
<td><p>46.1</p></td>
<td><p>100.6</p></td>
<td><p>164.6</p></td>
</tr>
<tr class="even">
<td><p>オーディオ</p></td>
<td><p>Siren</p></td>
<td><p>25.5</p></td>
<td><p>52.6</p></td>
<td><p>68.6</p></td>
</tr>
<tr class="odd">
<td><p>メイン ビデオ受信</p></td>
<td><p>H.264 および/または RTVideo</p></td>
<td><p>260</p></td>
<td><p>8015</p></td>
<td><p>該当なし</p></td>
</tr>
<tr class="even">
<td><p>メイン ビデオ送信</p></td>
<td><p>H.264 および/または RTVideo</p></td>
<td><p>270</p></td>
<td><p>8015</p></td>
<td><p>該当なし</p></td>
</tr>
<tr class="odd">
<td><p>パノラマ ビデオ受信</p></td>
<td><p>H.264 および/または RTVideo</p></td>
<td><p>190</p></td>
<td><p>2010 (最大解像度 1920x288 の場合)</p></td>
<td><p>該当なし</p></td>
</tr>
<tr class="even">
<td><p>パノラマ ビデオ送信</p></td>
<td><p>H.264 および/または RTVideo</p></td>
<td><p>190</p></td>
<td><p>2515 (複数の解像度/コーデックを使用するビットストリームを送信する場合)</p></td>
<td><p>該当なし</p></td>
</tr>
</tbody>
</table>


メイン ビデオの場合、標準および最大のストリーム帯域幅は、それぞれ、受信したすべてのビデオ ストリームの集計帯域幅と、送信したすべてのビデオ ストリームの集計帯域幅です。複数のビデオ ストリームであっても、標準的なビデオ帯域幅はピアツーピアのシナリオより小さくなります。これは、多くのビデオ会議ではコンテンツ共有が使用されるためにビデオ ウィンドウが小さくなり、したがってビデオ解像度が小さくなるためです。サポートされる最大の集計ビデオ ペイロード帯域幅は、たとえば 2 つの受信 1920x1080p ビデオ ストリームがある場合に使用される送信ストリームと受信ストリームの両方について、8000 Kbps です。

パノラマ ビデオの標準的なストリーム帯域幅は、最大で 960x144 パノラマ ビデオをストリーミングできる、現在利用可能なデバイスに基づきます。1920x288 パノラマ ビデオのデバイスが利用できるようになると、標準ストリーム帯域幅は大きくなると予想されます。

### <a name="audio-capacity-planning-for-pstn"></a>PSTN の音声容量計画

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>メディア</th>
<th>標準的なコーデック</th>
<th>標準的なストリーム帯域幅 (Kbps)</th>
<th>FEC を使用しない場合のストリームの最大帯域幅</th>
<th>FEC を使用する場合のストリームの最大帯域幅</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>オーディオ</p></td>
<td><p>711 (これには、電話会議の PSTN 参加者が含まれます)</p></td>
<td><p>64.8</p></td>
<td><p>97</p></td>
<td><p>161</p></td>
</tr>
<tr class="even">
<td><p>オーディオ</p></td>
<td><p>RTAudio (狭帯域)</p></td>
<td><p>30.9</p></td>
<td><p>44.8</p></td>
<td><p>56.6</p></td>
</tr>
</tbody>
</table>


上記の各表のネットワーク帯域幅の数値は、単方向トラフィックのみを表しており、各ストリームの RTCP トラフィック オーバーヘッドを意味する 5 Kbps を含みます。 ビデオの場合は、最大ストリームの計算に、最大ビデオ ビット レートが用いられています。

</div>

</div>

<span> </span>

</div>

</div>

</div>

