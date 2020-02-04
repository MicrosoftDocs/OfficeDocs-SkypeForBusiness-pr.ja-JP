---
title: 'Lync Server 2013: メディア品質比較レポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Comparison Report
ms:assetid: c1d0b5a8-98ff-455a-b78b-a05a21cf066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205236(v=OCS.15)
ms:contentKeyID: 48185317
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bcec69db6154aa346fc4545dc3b50fcfe0f2d6f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758765"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-comparison-report-in-lync-server-2013"></a>Lync Server 2013 のメディア品質比較レポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-04-22_

メディア品質比較レポートを使用すると、さまざまな種類の音声通話の通話品質の値を比較できます (たとえば、ワイヤレス ネットワーク経由の通話と有線接続経由の通話の比較)。

<div>

## <a name="accessing-the-media-quality-comparison-report"></a>メディア品質比較レポートへのアクセス

メディア品質比較レポートは、[監視レポート] ホーム ページからアクセスします。

</div>

<div>

## <a name="filters"></a>フィルター

フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざまな方法で表示したりする方法として利用できます。次の表に、メディア品質比較レポートで使用できるフィルターを示します。

### <a name="media-quality-comparison-report-filters"></a>メディア品質比較レポートのフィルター

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>名前</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>開始</strong></p></td>
<td><p>時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</p>
<p>7/7/2012 1:00 PM</p>
<p>開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</p>
<p>7/7/2012</p>
<p>週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</p>
<p>7/3/2012</p>
<p>一週間は、日曜日から始まり、土曜日で終わるものとします。</p></td>
</tr>
<tr class="even">
<td><p><strong>終了</strong></p></td>
<td><p>時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</p>
<p>7/7/2012 1:00 PM</p>
<p>終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</p>
<p>7/7/2012</p>
<p>週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</p>
<p>7/3/2012</p>
<p>一週間は、日曜日から始まり、土曜日で終わるものとします。</p></td>
</tr>
<tr class="odd">
<td><p><strong>通話</strong></p></td>
<td><p>メインの比較項目として使用する通話の種類。有効な値は次のとおりです。</p>
<ul>
<li><p>[すべて]</p></li>
<li><p>外部</p></li>
<li><p>内部</p></li>
<li><p>VPN</p></li>
<li><p>非 VPN</p></li>
<li><p>有線</p></li>
<li><p>ワイヤレス</p></li>
<li><p>外部および有線</p></li>
<li><p>外部およびワイヤレス</p></li>
<li><p>外部および VPN</p></li>
<li><p>外部および非 VPN</p></li>
<li><p>内部および有線</p></li>
<li><p>内部およびワイヤレス</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>通話との比較</strong></p></td>
<td><p>2 番目の比較項目として使用する通話の種類。有効な値は次のとおりです。</p>
<ul>
<li><p>[すべて]</p></li>
<li><p>外部</p></li>
<li><p>内部</p></li>
<li><p>VPN</p></li>
<li><p>非 VPN</p></li>
<li><p>有線</p></li>
<li><p>ワイヤレス</p></li>
<li><p>外部および有線</p></li>
<li><p>外部およびワイヤレス</p></li>
<li><p>外部および VPN</p></li>
<li><p>外部および非 VPN</p></li>
<li><p>内部および有線</p></li>
<li><p>内部およびワイヤレス</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>間隔</strong></p></td>
<td><p>時間間隔です。次のいずれかを選択します。</p>
<ul>
<li><p>毎時 (最大 25 時間の表示が可能)</p></li>
<li><p>毎日 (最大 31 日の表示が可能)</p></li>
<li><p>毎週 (最大 12 週の表示が可能)</p></li>
</ul>
<p>入力した開始日と終了日が選択した間隔で使用できる値の最大数を超える場合は、最大数の値 (開始日からカウント) のみが表示されます。 たとえば、開始日が7/7/2012 で、終了日が2/28/2012 の [日] 間隔を選択した場合は、8/7/2012 12:00 AM から 9/7/2012 12:00 AM (つまり、31日分のデータ) のデータが表示されます。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>指標

次の表に、メディア品質比較レポートで提供される情報を示します。

### <a name="media-quality-comparison-report-metrics"></a>メディア品質比較レポートの指標

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
<td><p><strong>通話ボリューム</strong></p></td>
<td><p>いいえ</p></td>
<td><p>通話の合計数。</p></td>
</tr>
<tr class="even">
<td><p><strong>低下 (MOS)</strong></p></td>
<td><p>不可</p></td>
<td><p>通話中に発生した平均 MOS (平均意見得点) の低下。 値の劣化は、0.0 の低いものから5.0 までの範囲になります。値が0.5 以下の場合は、許容できる劣化率が示されます。 歴史的な意見は、ユーザーが1対5のスケールで通話の品質を評価することによって算出されたものです。 Lync Server は、一連のアルゴリズムを使って、ユーザーがどのように通話を評価したかを予測します。</p>
<p>この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーやエンドポイントの過負荷などの原因が考えられます。その結果、音声のひずみや欠落が生じます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>低品質通話のパーセンテージ</strong></p></td>
<td><p>いいえ</p></td>
<td><p>低品質として分類される通話の総数。低品質通話とは、少なくとも 1 つの測定指標が許容値を超えている通話 (たとえば、過剰なジッターが発生した通話) のことです。</p></td>
</tr>
<tr class="even">
<td><p><strong>往復 (ミリ秒)</strong></p></td>
<td><p>いいえ</p></td>
<td><p>リアルタイム転送プロトコル (RTP) パケットが別のエンドポイントとの間を往復するのに要する平均時間 (ミリ秒単位)。200 ミリ秒以下の往復時間が許容できる品質と見なされます。</p>
<p>この値が高い場合は、国際通話ルーティング、ルーティングの構成ミス、メディア サーバーの過負荷などの原因が考えられます。その結果、双方向のリアルタイムの音声会話が難しくなります。</p></td>
</tr>
<tr class="odd">
<td><p><strong>パケット損失</strong></p></td>
<td><p>いいえ</p></td>
<td><p>リアルタイム転送プロトコル (RTP) パケット損失の平均レート。(パケット損失は、RTP パケット、つまりインターネット経由で音声とビデオを転送するために使われるプロトコルの一種で、パケットが宛先に到達できなかったときに発生します)。この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーの過負荷などの原因が考えられます。パケット損失が発生すると、通常、音声のひずみや欠落が生じます。</p></td>
</tr>
<tr class="even">
<td><p><strong>[ジッター (ミリ秒)]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>RTP パケットの着信間に検出された平均ジッター (ジッターとは、通話の "揺れ" の測定値です)。 (ジッタは、通話の&quot;shakiness&quot;の尺度です)。通常、高ジッターの値は、輻輳または過負荷のメディアサーバーによって発生し、音声が歪むか、失われる原因となります。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ヒーラー隠し比率</strong></p></td>
<td><p>いいえ</p></td>
<td><p>サンプルの合計数に対する隠しオーディオ サンプルの平均比率 (隠しオーディオ サンプルとは、突然遷移を取り除くために使用される手法です。突然遷移は、通常、ネットワーク パケットの削除が原因で発生します)。この値が高い場合は、パケット損失やジッターのために高いレベルで損失の隠蔽が適用されています。その結果、音声のひずみや欠落が生じます。</p></td>
</tr>
<tr class="even">
<td><p><strong>ヒーラー引き伸ばし比率</strong></p></td>
<td><p>いいえ</p></td>
<td><p>サンプルの合計数に対する引き伸ばされたオーディオ サンプルの平均比率 (引き伸ばされたオーディオとは、ネットワーク パケットの削除が検出されたときに通話の品質を維持できるように拡張されたオーディオのことです)。この値が高い場合は、ジッターのために高いレベルでサンプルの引き伸ばしが行われています。その結果、音声が機械のように聞こえたりひずんで聞こえたりします。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ヒーラー圧縮比率</strong></p></td>
<td><p>不可</p></td>
<td><p>サンプルの合計数に対する圧縮オーディオ サンプルの平均比率 (圧縮オーディオとは、ネットワーク パケットの削除が検出されたときに通話の品質を維持できるように圧縮されたオーディオのことです)。この値が高い場合は、ジッターのために高いレベルでサンプルの圧縮が行われています。その結果、音声が早送りされたように聞こえたりひずんで聞こえたりします。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

