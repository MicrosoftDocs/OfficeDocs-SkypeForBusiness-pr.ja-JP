---
title: 'Lync Server 2013: 場所レポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location Report
ms:assetid: cb2f1551-1e21-4f13-a39d-91f5f9010ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615035(v=OCS.15)
ms:contentKeyID: 48185641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45f7db796a4edab00918b0353e9b635f4615ba9a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046780"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-report-in-lync-server-2013"></a>Lync Server 2013 の場所レポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-01_

場所レポートは、通話品質指標に関する情報を、ネットワーク上の場所 (つまり、ネットワークサブネット) でグループ化して提供します。 ユーザーが呼び出しで問題が発生している場合は、このレポートを参考にして、問題が広範囲にあるか、または特定のネットワークセグメントに限定されているかを判断できます。

<div>

## <a name="accessing-the-location-report"></a>場所レポートへのアクセス

場所レポートには、監視レポートのホームページからアクセスします。 次のいずれかの指標クリックしてCall List Reportにドリルダウンできます。

  - [通話ボリューム]

  - [低品質通話のパーセンテージ]

</div>

<div>

## <a name="filters"></a>フィルター

フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざま方法で表示したりする方法として利用できます。 たとえば、場所レポートを使用すると、通話が発信された場所やワイヤレスまたは有線接続で通話が行われたかどうかなどのフィルター処理を行うことができます。 また、データをグループ化する方法を選択することもできます。 この場合は、通話が、時間、日、週、または月を基準にグループ化されています。

次の表に、場所レポートで使用できるフィルターを示します。

### <a name="location-report-filters"></a>場所レポートのフィルター

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
<td><p><strong>From</strong></p></td>
<td><p>時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</p>
<p>7/7/2012 1:00 PM</p>
<p>開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</p>
<p>7/7/2012</p>
<p>週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</p>
<p>7/3/2012</p>
<p>週は、常に日曜日から土曜日までです。</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</p>
<p>7/7/2012 13:00</p>
<p>終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</p>
<p>7/7/2012</p>
<p>週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</p>
<p>7/3/2012</p>
<p>週は、常に日曜日から土曜日までです。</p></td>
</tr>
<tr class="odd">
<td><p><strong>発信者の場所</strong></p></td>
<td><p>通話を発信したユーザーの IP サブネット。 <strong>[All]</strong>のみを選択して、すべてのサブネットを指定できます。</p></td>
</tr>
<tr class="even">
<td><p><strong>呼び出し先の場所</strong></p></td>
<td><p>通話を受信したユーザーの IP サブネット。 <strong>[All]</strong>のみを選択して、すべてのサブネットを指定できます。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>ネットワークの種類</strong>]</p></td>
<td><p>通話時にクライアントが接続したネットワークの種類を示します。次のいずれかを選択します。</p>
<ol>
<li><p>いずれ</p></li>
<li><p>有線</p></li>
<li><p>通信</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>通話時に外部クライアントが仮想プライベート ネットワーク (VPN) 接続を使用したかどうかを示します。次のいずれかを選択します。</p>
<ol>
<li><p>いずれ</p></li>
<li><p>VPN</p></li>
<li><p>非 VPN</p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>指標

次の表に、場所レポートで提供される情報を示します。

### <a name="location-report-metrics"></a>場所レポートの指標

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
<td><p><strong>発信者サブネット</strong></p></td>
<td><p>いいえ</p></td>
<td><p>通話を発信したユーザーの IP サブネット。</p></td>
</tr>
<tr class="even">
<td><p><strong>呼び出し先サブネット</strong></p></td>
<td><p>いいえ</p></td>
<td><p>通話を受信したユーザーの IP サブネット。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>通話ボリューム</strong>]</p></td>
<td><p>はい</p></td>
<td><p>発信された通話の合計数。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>低品質通話のパーセンテージ</strong>]</p></td>
<td><p>はい</p></td>
<td><p>低品質通話として分類された通話のパーセンテージ。 低品質通話とは、少なくとも 1 つの測定指標が許容値を超えている通話 (たとえば、過剰なジッターが発生した通話) のことです。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>往復 (ミリ秒)</strong>]</p></td>
<td><p>はい</p></td>
<td><p>リアルタイム転送プロトコル (RTP) パケットが別のエンドポイントとの間を往復するのに要する平均時間 (ミリ秒単位)。100 ミリ秒以下の往復時間が許容できる品質と見なされます。</p>
<p>この値が高い場合は、国際通話ルーティング、ルーティングの構成ミス、メディア サーバーの過負荷などの原因が考えられます。その結果、双方向のリアルタイムの音声会話が困難になります。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>低下 (MOS)</strong>]</p></td>
<td><p>はい</p></td>
<td><p>通話時に発生した平均オピニオン値 (MOS) 低下の平均値。 低下の値範囲は、最低 0.0 から最高 5.0 までとなります。 0.5 以下の値は、許容される低下を表します。 従来、平均オピニオン値は、ユーザーが通話の品質を 1 から 5 の範囲で評価することによって計算されていました。 Lync Server では、Lync Server は一連のアルゴリズムを使用して、ユーザーが通話を評価する方法を予測します。</p>
<p>この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーやエンドポイントの過負荷などの原因が考えられます。その結果、音声のひずみや欠落が生じます。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>パケット損失</strong>]</p></td>
<td><p>はい</p></td>
<td><p>RTP パケットの平均損失率 (パケット損失は、RTP パケット (音声およびビデオをインターネット上で転送する場合に使用されるプロトコル) が宛先に到達できなかった場合に発生します)。通常、この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーの過負荷などの原因が考えられます。その結果、一般に音声のひずみや欠落が生じます。</p></td>
</tr>
<tr class="even">
<td><p><strong>ずれ</strong></p></td>
<td><p>はい</p></td>
<td><p>RTP パケットの着信間に検出された平均ジッター (ジッターとは、通話の "揺れ" の測定値です)。 (ジッターは、通話の&quot;過&quot;の測定値です)。高ジッター値は、通常、混雑または過負荷のメディアサーバーによって発生し、その結果、音声がひずむか失われます。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>ヒーラー隠し比率</strong>]</p></td>
<td><p>はい</p></td>
<td><p>サンプルの合計数に対する隠しオーディオ サンプルの平均比率 (隠しオーディオ サンプルとは、突然遷移を取り除くために使用される手法です。突然遷移は、通常、ネットワーク パケットの削除が原因で発生します)。この値が高い場合は、パケット損失やジッターのために高いレベルで損失の隠蔽が適用されています。その結果、音声のひずみや欠落が生じます。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>ヒーラー引き伸ばし比率</strong>]</p></td>
<td><p>はい</p></td>
<td><p>サンプルの合計数に対する引き伸ばされたオーディオ サンプルの平均比率 (引き伸ばされたオーディオとは、ネットワーク パケットの削除が検出されたときに通話の品質を維持できるように拡張されたオーディオのことです)。この値が高い場合は、ジッターのために高いレベルでサンプルの引き伸ばしが行われています。その結果、音声が機械のように聞こえたりひずんで聞こえたりします。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>ヒーラー圧縮比率</strong>]</p></td>
<td><p>はい</p></td>
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

