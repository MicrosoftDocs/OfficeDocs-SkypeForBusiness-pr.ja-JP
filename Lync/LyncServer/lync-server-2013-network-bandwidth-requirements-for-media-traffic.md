---
title: メディアトラフィックの Lync Server 2013 ネットワーク帯域幅の要件
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
ms.openlocfilehash: 684f13a10c066e8902bed0024d7546017450ee9e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765928"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-bandwidth-requirements-for-media-traffic-in-lync-server-2013"></a>Lync Server 2013 でのメディアトラフィックのネットワーク帯域幅要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2015-09-24_

ネットワーク計画の重要な部分は、Lync Server によって生成されるメディアトラフィックをネットワークが処理できることを確認することです。 このセクションは、目的のメディア トラフィックを計画する場合に役立ちます。

<div>

## <a name="media-traffic-network-usage"></a>メディアトラフィックネットワークの使用状況

メディア トラフィックの帯域幅使用量の計算は、使用されるコーデック、解像度、アクティビティ レベルなど、変数の数が多いため、困難になる可能性があります。 帯域幅使用量は、使用されているコーデックとストリームのアクティビティ (どちらもシナリオによって異なります) の機能です。 次の表に、Lync Server 2013 シナリオで一般的に使われているオーディオコーデックの一覧を示します。

### <a name="audio-codec-bandwidth"></a>オーディオコーデックの帯域幅

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
<th>オーディオペイロードのビットレート (KBPS)</th>
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
<td><p>G.722 ステレオ</p></td>
<td><p>ピアツーピア、会議</p></td>
<td><p>128.0</p></td>
<td><p>144.0</p></td>
<td><p>159.6</p></td>
<td><p>223.6</p></td>
</tr>
<tr class="odd">
<td><p>G.711</p></td>
<td><p>PSTN、会議</p></td>
<td><p>64.0</p></td>
<td><p>80.0</p></td>
<td><p>92.0</p></td>
<td><p>156.0</p></td>
</tr>
<tr class="even">
<td><p>Siren</p></td>
<td><p>電話会議</p></td>
<td><p>16.0</p></td>
<td><p>32.0</p></td>
<td><p>47.6</p></td>
<td><p>63.6</p></td>
</tr>
</tbody>
</table>


前の表に記載されている帯域幅の数値は、20ms packetization (1 秒あたりの50パケット) と走るサイレンおよび G に基づいています。これには、会議シナリオからのセキュリティで保護されたリアルタイムトランスポートプロトコル (SRTP) のオーバーヘッドが含まれており、ストリームが100% アクティブであることを前提とします。 転送エラー訂正 (FEC) は、オーディオストリームの品質を維持するためにリンクでパケット損失が発生した場合に、動的に使用されます。

722コーデックのステレオバージョンは、Lync Room System に基づくシステムによって使用されます。これにより、ステレオマイクのキャプチャが可能になり、会議室の複数の talkers を区別しやすくなります。

ビデオの場合、既定のコーデックは、時間的なスケーラビリティを実現するスケーラブルなビデオコーディング拡張機能を備えた、高 264/MPEG-2 パート10の高度なビデオコーディング規格です。 Lync 2010 または Office Communicator 2007 R2 クライアントとの相互運用性を維持するために、Lync 2013 とレガシクライアント間のピアツーピア通話には RTVideo コーデックが使用されます。 Lync 2013 とレガシクライアントの両方が含まれる会議セッションでは、Lync 2013 エンドポイントは両方のビデオコーデックを使用してビデオをエンコードし、lync 2013 および RTVideo bitstream に bitstream を Lync 2010 または Office Communicator 2007 R2 クライアントに送信します。

必要な帯域幅は、解像度、品質、フレームレートによって異なります。 各解像度には2つの興味深いビットレートがあります。

  - **最大ペイロードのビット**   レートこの解像度でサポートされているフレームレートの最大値で、Lync 2013 のエンドポイントが使用するビットレートです。 この値は、最高品質とフレームレートのビデオを利用できるため、興味深いものです。

  - **最小ペイロードのビットレート**   これは、Lync 2013 のエンドポイントが次の低い解像度に切り替えるビットレートです。 特定の解像度を保証するために、利用可能なビデオペイロードのビットレートは、その解像度の最小ビットレート以下にする必要があります。 この値は、最大ビットレートが使用できないか、または実用的でない場合に可能な最小値を把握できるようにするために重要です。 一部のユーザーは、低ビットレートのビデオを使用できないと考えられる場合があるため、これらの最小ビデオペイロードのビットレートを検討する際には注意してください。 ユーザーがほとんどまたはまったく動かないビデオシーンの場合は、実際のビットレートが一時的に最小ビットレートよりも下になることがあります。

Lync 2013 では、より多くの解像度がサポートされています。 これにより、さまざまなネットワーク帯域幅やクライアントの受信機能に合わせて調整することができます。 さらに、Lync 2013 の既定の縦横比も16:9 に変更されました。 16:9 縦横比でのキャプチャが許可されていない web カメラでは、4:3 の縦横比は引き続きサポートされます。

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
<th>ビデオペイロードの最大ビットレート (Kbps)</th>
<th>ビデオペイロードの最小ビットレート (Kbps)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>H.264</p></td>
<td><p>320x180 (16:9)</p>
<p>212x160 (4:3)</p></td>
<td><p>250</p></td>
<td><p>マート</p></td>
</tr>
<tr class="even">
<td><p>H.264/RTVideo</p></td>
<td><p>424x240 (16:9)</p>
<p>320x240 (4:3)</p></td>
<td><p>350</p></td>
<td><p>100</p></td>
</tr>
<tr class="odd">
<td><p>H.264</p></td>
<td><p>480x270 (16:9)</p>
<p>424x320 (4:3)</p></td>
<td><p>450</p></td>
<td><p>200</p></td>
</tr>
<tr class="even">
<td><p>H.264/RTVideo</p></td>
<td><p>640x360 (16:9)</p>
<p>640x480 (4:3)</p></td>
<td><p>800</p></td>
<td><p>300</p></td>
</tr>
<tr class="odd">
<td><p>H.264</p></td>
<td><p>848x480 (16:9)</p></td>
<td><p>1500</p></td>
<td><p>400</p></td>
</tr>
<tr class="even">
<td><p>H.264</p></td>
<td><p>960x540 (16:9)</p></td>
<td><p>2000</p></td>
<td><p>500</p></td>
</tr>
<tr class="odd">
<td><p>H.264/RTVideo</p></td>
<td><p>1280x720 (16:9)</p></td>
<td><p>2500</p></td>
<td><p>700</p></td>
</tr>
<tr class="even">
<td><p>H.264</p></td>
<td><p>1920x1080 (16:9)</p></td>
<td><p>4000</p></td>
<td><p>1500</p></td>
</tr>
<tr class="odd">
<td><p>H.264/RTVideo</p></td>
<td><p>960x144 (20:3)</p></td>
<td><p>500</p></td>
<td><p>マート</p></td>
</tr>
<tr class="even">
<td><p>H.264</p></td>
<td><p>1280x192 (20:3)</p></td>
<td><p>1000</p></td>
<td><p>250</p></td>
</tr>
<tr class="odd">
<td><p>H.264</p></td>
<td><p>1920x288 (20:3)</p></td>
<td><p>2000</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


ビデオ FEC はビデオのペイロードビットレートに含まれているため、ビデオ FEC とビデオ FEC なしで別々の値を使用することはできません。

エンドポイントは、音声またはビデオ パケットを連続的にストリーミングするわけではありません。シナリオごとにさまざまなレベルのストリーム アクティビティがあり、このレベルからストリームに対するパケットの送信頻度が分かります。ストリーム アクティビティは、メディアとシナリオに左右されますが、使用されるコーデックの影響は受けません。ピアツーピア シナリオでは、次のようになります。

  - エンドポイントは、ユーザーが話しているときだけ、音声ストリームを送信します。

  - 両方の参加者が音声ストリームを受け取ります。

  - ビデオが使用されている場合は、両方のエンドポイントが通話中にビデオストリームを送受信します。

  - 移動がほとんどまたはまったく不要なビデオシーンの場合、ビデオコーデックでは、変更されずにビデオのエンコード領域がスキップされるため、実際のビットレートが一時的に少なくなることがあります。

電話会議シナリオでは、次のようになります。

  - エンドポイントは、ユーザーが話しているときだけ、音声ストリームを送信します。

  - すべての参加者が音声ストリームを受け取ります。

  - ビデオが使用されている場合、すべての参加者は最大 5 つの受信ビデオ ストリームと 1 つのパノラマ (たとえば、縦横比 20:3) ビデオ ストリームを受信できます。 既定では、5 つの受信ビデオ ストリームはアクティブな発表者履歴に基づきますが、ユーザーはビデオ ストリームを受信する参加者を手動で選択することもできます。

  - ユーザーの送信ビデオ ストリームを有効にしている各参加者は、1 つ以上のビデオ ストリームを送信します。 Lync 2013 は、最大5つのビデオストリームを送信して、すべての受信クライアントのビデオ品質を最適化する機能を追加します。 実際に送信されるビデオ ストリームの数は、CPU の能力、利用可能なアップリンク帯域幅、特定のビデオ ストリームを要求している受信クライアントの数に基づいて、送信側によって決定されます。 最も一般的なものは、レガシ クライアントが会議に参加している場合で、1 つの H.264 と 1 つの RTVideo ビデオ ストリームが送信されます。 もう 1 つのよくあるシナリオでは、受信側の異なる要求に対応するため、複数の H.264 ビデオ ストリームが (たとえば、異なるビデオ解像度で) 送信されます。

音声およびビデオ メディア用のリアルタイム転送プロトコル (RTP) トラフィックで必要な帯域幅以外に、リアルタイム転送制御プロトコル (RTCP) でも帯域幅が必要です。 RTCP は、RTP ストリームの統計情報の報告やアウトオブバンドの制御に使用されます。 計画の際には、RTCP トラフィックに関する次の表の帯域幅の数値を参照してください。 これらの値は、RTCP に使用される最大帯域幅を表します。コントロールデータの違いにより、オーディオストリームとビデオストリームは異なります。

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
<td><p>5</p></td>
</tr>
<tr class="even">
<td><p>ビデオ (H.264 または RTVideo の一方のみを送受信)</p></td>
<td><p>常用</p></td>
</tr>
<tr class="odd">
<td><p>ビデオ (H.264 と RTVideo の両方を送受信)</p></td>
<td><p>マート</p></td>
</tr>
</tbody>
</table>


容量の計画を立てるために、次の2つの帯域幅が使用されています。

  - **FEC のない最大帯域幅**   は、ストリームの一般的な動作、FEC を使わないシナリオで使用される一般的なコーデックなど、ストリームで消費される最大帯域幅を指定します。これは、ストリームのアクティビティが100% であり、FEC の使用をトリガーするパケット損失がない場合の帯域幅です。これは、特定のシナリオでコーデックを使用できるようにするために割り当てる必要がある帯域幅の量を計算する場合に便利です。 

  - **FEC の最大帯域幅**   は、ストリームの一般的な動作、および FEC でのシナリオで使用される一般的なコーデックなど、ストリームが消費する最大帯域幅を含みます。 これは、ストリームが100% のアクティビティであり、品質を向上させるために FEC の使用をトリガーしているときに、パケット損失が発生する場合の帯域幅です。 これは、特定のシナリオでコーデックを使用できるようにするために割り当てる必要がある帯域幅の量を計算するのに便利です。また、FEC を使用して、パケット損失条件の下で品質を維持することができます。 

次の表では、帯域幅の追加値、**一般的な帯域**幅の一覧も示します。 これは、ストリームの一般的なアクティビティやシナリオで使用される一般的なコーデックなど、ストリームが消費する平均帯域幅です。 この帯域幅は、どの時点でメディアトラフィックによって消費され、どの程度の帯域幅を使用するかを指定できますが、アクティビティレベルが平均よりも大きい場合は、個々の通話はこの値を超過します。 以下の表に示す一般的なビデオストリームの帯域幅は、測定された顧客データで見たさまざまなビデオ解像度の組み合わせに基づいています。 たとえば、ピアツーピアセッションでは、ほとんどのユーザーが既定のビデオレンダリングウィンドウを使用していますが、一部のユーザーは、高解像度のビデオ解像度を可能にするために Lync アプリケーションを拡大または最大化することができます。

次の表では、さまざまなシナリオについて、これら3つの帯域幅値を提供します。

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
<td><p>音声</p></td>
<td><p>RTAudio (狭帯域)</p></td>
<td><p>29.3</p></td>
<td><p>44.8</p></td>
<td><p>56.6</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2013 エンドポイントを呼び出すときのメインビデオ</p></td>
<td><p>H.264</p></td>
<td><p>460</p></td>
<td><p>4010 (最大解像度 1920x1080 の場合)</p></td>
<td><p>該当しない</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 または Office Communicator 2007 R2 エンドポイントを呼び出すときのメインビデオ</p></td>
<td><p>RTVideo</p></td>
<td><p>460</p></td>
<td><p>2510 (最大解像度 1280x720 の場合)</p></td>
<td><p>該当しない</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2013 エンドポイントを呼び出すときのパノラマビデオ</p></td>
<td><p>H.264</p></td>
<td><p>190</p></td>
<td><p>2010 (最大解像度 1920x288 の場合)</p></td>
<td><p>該当なし</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 または Office Communicator 2007 R2 エンドポイントを呼び出すときのパノラマビデオ</p></td>
<td><p>RTVideo</p></td>
<td><p>190</p></td>
<td><p>510 (最大解像度 960x144 の場合)</p></td>
<td><p>該当しない</p></td>
</tr>
</tbody>
</table>


### <a name="audiovideo-capacity-planning-for-conferences"></a>会議の音声/ビデオの容量計画

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
<td><p>音声</p></td>
<td><p>Siren</p></td>
<td><p>25.5</p></td>
<td><p>52.6</p></td>
<td><p>68.6</p></td>
</tr>
<tr class="odd">
<td><p>メイン ビデオ受信</p></td>
<td><p>.H および RTVideo</p></td>
<td><p>260</p></td>
<td><p>8015</p></td>
<td><p>該当しない</p></td>
</tr>
<tr class="even">
<td><p>メイン ビデオ送信</p></td>
<td><p>.H および RTVideo</p></td>
<td><p>270</p></td>
<td><p>8015</p></td>
<td><p>該当しない</p></td>
</tr>
<tr class="odd">
<td><p>パノラマ ビデオ受信</p></td>
<td><p>.H および RTVideo</p></td>
<td><p>190</p></td>
<td><p>2010 (最大解像度 1920x288 の場合)</p></td>
<td><p>該当なし</p></td>
</tr>
<tr class="even">
<td><p>パノラマ ビデオ送信</p></td>
<td><p>.H および RTVideo</p></td>
<td><p>190</p></td>
<td><p>2515 (複数の解像度/コーデックを使用して bitstreams を送信する場合)</p></td>
<td><p>該当しない</p></td>
</tr>
</tbody>
</table>


メインビデオの場合、一般的なストリーム帯域幅と最大ストリーム帯域幅は、受信したすべてのビデオストリームに対する合計帯域幅であり、すべての送信ビデオストリームについてはそれぞれ、 複数のビデオストリームを使っている場合でも、ビデオ通話の一般的な帯域幅はピアツーピアシナリオよりも小さくなっています。多くのビデオ会議では、ビデオのサイズが小さく、ビデオ解像度が低いため、コンテンツの共有が使用されています。 サポートされている集計ビデオペイロード帯域幅の最大値は 8000 Kbps です。たとえば、2つの着信1920x1080p ビデオストリームがある場合は、それらが使用されます。

パノラマビデオの標準的なストリーム帯域幅は、最大 96 0x144 パノラマビデオにのみストリーミングできる現在利用可能なデバイスに基づいています。 1920x288 パノラマビデオを搭載したデバイスが利用可能になると、一般的なストリーム帯域幅が増加することが予想されます。

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
<td><p>G. (会議の PSTN 参加者を含む)</p></td>
<td><p>64.8</p></td>
<td><p>97</p></td>
<td><p>161</p></td>
</tr>
<tr class="even">
<td><p>音声</p></td>
<td><p>RTAudio (狭帯域)</p></td>
<td><p>30.9</p></td>
<td><p>44.8</p></td>
<td><p>56.6</p></td>
</tr>
</tbody>
</table>


上記の各表のネットワーク帯域幅の数値は、単方向トラフィックのみを表しており、各ストリームの RTCP トラフィック オーバーヘッドを意味する 5 Kbps を含みます。 ビデオの場合、最大のビデオビットレートは、最大ストリームの計算に使用されます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

