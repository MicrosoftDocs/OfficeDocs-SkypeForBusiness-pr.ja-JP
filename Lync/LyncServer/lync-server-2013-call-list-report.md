---
title: 'Lync Server 2013: 通話リストレポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call List Report
ms:assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615020(v=OCS.15)
ms:contentKeyID: 48184921
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faf330a776f64534c02833a0472cfefea7f0998e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840706"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-list-report-in-lync-server-2013"></a>Lync Server 2013 の通話リストレポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-01_

通話リストレポートでは、組織内で発信および受信した個々の通話の品質 (QoE) メトリックが提供されます。 実際に報告される指標は、通話リストレポートへのアクセス方法によって異なります。 たとえば、 [Lync Server 2013 のデバイスレポート](lync-server-2013-device-report.md)からレポートを開くと、次のようなメトリックが表示されます。これは、デバイスレポートにも報告されます。

  - 発信者のマイク

  - 発信者のスピーカー

  - 呼び出し先マイク

  - 呼び出し先スピーカー

  - 音声切り替え時間の比率

ただし、 [Lync Server 2013 の場所レポート](lync-server-2013-location-report.md)から通話リストレポートを開くと、これらのメトリックは表示されません。代わりに、次のようなメトリックが表示できます。

  - 往復 (ミリ秒)

  - 低下 (MOS)

  - パケット損失

  - ジッター (ミリ秒)

これらは場所レポートで報告される指標です。ただし、通話リスト レポートでは、[詳細] 指標をいつでもクリックして、任意の通話のすべての QoE 情報を提供することができます。

<div>

## <a name="accessing-the-call-list-report"></a>通話リスト レポートへのアクセス

通話リスト レポートには、次のいずれかのレポートからアクセスできます。

  - [Lync Server 2013 の場所レポート](lync-server-2013-location-report.md)(通話ボリュームまたは低通話のパーセンテージメトリックをクリック)

  - [Lync Server 2013 のデバイスレポート](lync-server-2013-device-report.md)(通話ボリュームまたは低通話パーセンテージメトリックをクリック)

  - [Lync Server 2013 のメディア品質の概要レポート](lync-server-2013-media-quality-summary-report.md)(通話ボリュームまたは低品質の通話率のメトリックをクリック)

  - [Lync server 2013 のサーバーパフォーマンスレポート](lync-server-2013-server-performance-report.md)(通話ボリュームまたは低通話パーセンテージメトリックをクリック)

通話リストレポート内から、詳細なメトリックをクリックして、 [Lync Server 2013 の通話詳細レポート](lync-server-2013-call-detail-report.md)にアクセスできます。

</div>

<div>

## <a name="making-the-best-use-of-the-call-list-report"></a>通話リスト レポートの活用

通話リスト レポートの一部の指標 ([音声切り替え時間の比率] など) で実際に何を測定するのかがわからない場合は、指標ラベルの上にマウス ポインターを置いてください。指標の簡単な説明を示すツール ヒントが表示されます。

</div>

<div>

## <a name="filters"></a>フィルター

なし。通話リスト レポートにフィルターを適用することはできません。

</div>

<div>

## <a name="metrics"></a>指標

次の表に、通話リスト レポートで提供される通話ごとの情報を示します。

### <a name="call-list-report-metrics"></a>通話リスト レポートの指標

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名前</th>
<th>この項目での並べ替え</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>[詳細]</strong></p></td>
<td><p>不可</p></td>
<td><p>この項目をクリックすると、その通話に関する補足的な情報が表示されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>[発信者]</strong></p></td>
<td><p>はい</p></td>
<td><p>通話の発信者の SIP アドレス。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[呼び出し先]</strong></p></td>
<td><p>はい</p></td>
<td><p>通話の着信者の SIP アドレス。</p></td>
</tr>
<tr class="even">
<td><p><strong>[開始時刻]</strong></p></td>
<td><p>はい</p></td>
<td><p>通話が開始された日時。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[終了時刻]</strong></p></td>
<td><p>はい</p></td>
<td><p>通話が終了した日時。</p></td>
</tr>
<tr class="even">
<td><p><strong>[発信者ユーザー エージェント]</strong></p></td>
<td><p>はい</p></td>
<td><p>通話の発信者のエンドポイントで使われているソフトウェア。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[呼び出し先ユーザー エージェント]</strong></p></td>
<td><p>はい</p></td>
<td><p>通話の着信者のエンドポイントで使われているソフトウェア。</p></td>
</tr>
<tr class="even">
<td><p><strong>[往復 (ミリ秒)]</strong></p></td>
<td><p>はい</p></td>
<td><p>リアルタイム転送プロトコル (RTP) パケットが別のエンドポイントとの間を往復するのに要する平均時間 (ミリ秒単位)。100 ミリ秒以下の往復時間が許容できる品質と見なされます。</p>
<p>この値が高い場合は、国際通話ルーティング、ルーティングの構成ミス、メディア サーバーの過負荷などの原因が考えられます。その結果、双方向のリアルタイムの音声会話が難しくなります。</p></td>
</tr>
<tr class="odd">
<td><p><strong>低下 (MOS)</strong></p></td>
<td><p>はい</p></td>
<td><p>通話時に発生した平均オピニオン値 (MOS) 低下の平均値。 低下の値範囲は、最低 0.0 から最高 5.0 までとなります。 0.5 以下の値は、許容される低下を表します。 従来、平均オピニオン値は、ユーザーが通話の品質を 1 から 5 の範囲で評価することによって計算されていました。 Lync server では、Lync Server で一連のアルゴリズムを使って、ユーザーが通話を評価した方法を予測します。</p>
<p>この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーやエンドポイントの過負荷などの原因が考えられます。その結果、音声のひずみや欠落が生じます。</p></td>
</tr>
<tr class="even">
<td><p><strong>パケット損失</strong></p></td>
<td><p>はい</p></td>
<td><p>RTP パケットの平均損失率 (パケット損失は、RTP パケット (音声およびビデオをインターネット上で転送する場合に使用されるプロトコル) が宛先に到達できなかった場合に発生します)。通常、この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーの過負荷などの原因が考えられます。その結果、一般に音声のひずみや欠落が生じます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ジッター</strong></p></td>
<td><p>はい</p></td>
<td><p>RTP パケットの着信間に検出された平均ジッター (ジッターとは、通話の "揺れ" の測定値です)。 (ジッタは、通話の&quot;shakiness&quot;の尺度です)。通常、高ジッターの値は、輻輳または過負荷のメディアサーバーによって発生し、音声が歪むか、失われる原因となります。</p></td>
</tr>
<tr class="even">
<td><p><strong>ヒーラー隠し比率</strong></p></td>
<td><p>はい</p></td>
<td><p>サンプルの合計数に対する隠しオーディオ サンプルの平均比率 (隠しオーディオ サンプルとは、突然遷移を取り除くために使用される手法です。突然遷移は、通常、ネットワーク パケットの削除が原因で発生します)。この値が高い場合は、パケット損失やジッターのために高いレベルで損失の隠蔽が適用されています。その結果、音声のひずみや欠落が生じます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ヒーラー引き伸ばし比率</strong></p></td>
<td><p>はい</p></td>
<td><p>サンプルの合計数に対する引き伸ばされたオーディオ サンプルの平均比率 (引き伸ばされたオーディオとは、ネットワーク パケットの削除が検出されたときに通話の品質を維持できるように拡張されたオーディオのことです)。この値が高い場合は、ジッターのために高いレベルでサンプルの引き伸ばしが行われています。その結果、音声が機械のように聞こえたりひずんで聞こえたりします。</p></td>
</tr>
<tr class="even">
<td><p><strong>ヒーラー圧縮比率</strong></p></td>
<td><p>はい</p></td>
<td><p>サンプルの合計数に対する圧縮オーディオ サンプルの平均比率 (圧縮オーディオとは、ネットワーク パケットの削除が検出されたときに通話の品質を維持できるように圧縮されたオーディオのことです)。この値が高い場合は、ジッターのために高いレベルでサンプルの圧縮が行われています。その結果、音声が早送りされたように聞こえたりひずんで聞こえたりします。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[接続]</strong></p></td>
<td><p>可</p></td>
<td><p>ワイヤレス通信リンクの種類。通常、これは次のいずれかです。</p>
<ul>
<li><p>リレー</p></li>
<li><p>直接</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

