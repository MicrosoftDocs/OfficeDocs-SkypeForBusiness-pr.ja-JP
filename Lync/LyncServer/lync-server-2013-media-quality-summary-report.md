---
title: 'Lync Server 2013: メディア品質サマリーレポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Summary Report
ms:assetid: 8bd59ad6-3087-49c8-b692-5573fe2ffcd8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615012(v=OCS.15)
ms:contentKeyID: 48184776
ms.date: 06/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6980168a2d509bc32b9aa48f30167bca8721fef2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766088"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-summary-report-in-lync-server-2013"></a>Lync Server 2013 のメディア品質サマリーレポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2016-06-29_

メディア品質概要レポートは、組織での通話の品質を解析するのに最良の方法です。このレポートは、次のカテゴリに分類された詳細な QoE (Quality of Experience) 通話指標を提供します。

  - UC ピアツーピア通話 (Microsoft lync 2013 から Microsoft Lync 2013 通話)

  - UC 電話会議セッション

  - PSTN 電話会議セッション

  - PSTN 通話: メディアのバイパス

  - PSTN 通話 (非バイパス): UC レグ

  - PSTN 通話 (非バイパス): ゲートウェイ レグ

  - その他の通話の種類

レポートを初めて開いたとき、これらの各カテゴリの概要情報が表示されます。 レポートを離れることなく、各カテゴリを展開して、Office Communicator 2007 R2 から Lync 2013 への通話などのサブカテゴリを表示できます。 また、これらのサブカテゴリにドリルダウンして、そのサブカテゴリ内の発信された各通話の詳細を表示できます。

Microsoft Lync Server 2013 の [メディア品質の概要] レポートでは、データが、音声通話、ビデオ通話、アプリケーション共有通話の3種類に分割されます。 通話の各種類について、独自のセクションがレポート内に設けられ、通話指標の独自のカスタム セットが用意されています。

メディア品質概要レポートでは、有線通話とワイヤレス通話、内部通話と外部通話、VPN 通話と非 VPN 通話を比較できるフィルターも適用できます。

<div>

## <a name="accessing-the-media-quality-summary-report"></a>メディア品質概要レポートへのアクセス

メディア品質概要レポートには、監視レポートのホームページからアクセスできます。 次の指標のいずれかをクリックして、 [Lync Server 2013 の通話リストレポート](lync-server-2013-call-list-report.md)にドリルダウンすることができます。

  - 通話ボリューム

  - 低品質通話のパーセンテージ

また、次のいずれかの音声通話指標をクリックして、メディア品質メトリック分布レポートにアクセスできます。

  - 往復 (ミリ秒)

  - 低下 (MOS)

  - パケット損失

  - ジッター (ミリ秒)

  - ヒーラー隠し比率

  - ヒーラー引き伸ばし比率

  - ヒーラー圧縮比率

</div>

<div>

## <a name="filters"></a>フィルター

フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざまな方法で表示したりする方法として利用できます。たとえば、メディア品質概要レポートでは、返されたデータをアクセスの種類 (内部アクセス、外部アクセスなど) や有線/ワイヤレス ネットワーク接続でフィルターできます。また、データをグループ化する方法を選択することもできます。この場合は、通話が、時間、日、週、または月を基準にグループ化されています。

次の表に、メディア品質概要レポートで使用できるフィルターを示します。

### <a name="media-quality-summary-report-filters"></a>メディア品質概要レポートのフィルター

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
<td><p><strong>[アクセスの種類]</strong></p></td>
<td><p>クライアントが通話時に内部ネットワークにログオンしたか、外部ネットワークにログオンしたかを示します。次のいずれかを選択します。</p>
<ul>
<li><p>[すべて]</p></li>
<li><p>内部</p></li>
<li><p>外部</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>[ネットワークの種類]</strong></p></td>
<td><p>通話時にクライアントが接続したネットワークの種類を示します。次のいずれかを選択します。</p>
<ul>
<li><p>[すべて]</p></li>
<li><p>有線</p></li>
<li><p>ワイヤレス</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>VPN</strong></p></td>
<td><p>通話時に外部クライアントが仮想プライベート ネットワーク (VPN) 接続を使用したかどうかを示します。次のいずれかを選択します。</p>
<ul>
<li><p>[すべて]</p></li>
<li><p>VPN</p></li>
<li><p>非 VPN</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>指標

次の表に、メディア品質概要レポートで提供される情報を示します。

### <a name="media-quality-summary-report-metrics-audio-call-summary"></a>メディア品質概要レポートの指標: 音声通話の概要

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
<td><p><strong>[通話の種類/エンドポイントの種類]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>この項目をクリックすると、その種類に基づく通話の詳細情報がレポートに表示されます。通話の種類は次のとおりです。</p>
<ul>
<li><p>UC ピアツーピア通話</p></li>
<li><p>UC 電話会議セッション</p></li>
<li><p>PSTN 電話会議セッション</p></li>
<li><p>PSTN 通話: メディアのバイパス</p></li>
<li><p>PSTN 通話 (非バイパス): UC レグ</p></li>
<li><p>PSTN 通話 (非バイパス): ゲートウェイ レグ</p></li>
<li><p>その他の通話の種類</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>[通話ボリューム]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>通話の種類あたりの通話の総数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[低品質通話のパーセンテージ]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>低品質として分類される通話の総数。低品質通話とは、少なくとも 1 つの測定指標が許容値を超えている通話 (たとえば、過剰なジッターが発生した通話) のことです。</p></td>
</tr>
<tr class="even">
<td><p><strong>[通話ボリューム (ワイヤレス通話)]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>ワイヤレス接続を使用した通話の数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[通話ボリューム (VPN 通話)]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>VPN 接続を使用した通話の数。</p></td>
</tr>
<tr class="even">
<td><p><strong>[通話ボリューム (外部通話)]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>外部接続 (つまり、内部ネットワークの外側の接続) を使用した通話の数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[往復 (ミリ秒)]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>リアルタイム転送プロトコル (RTP) パケットが別のエンドポイントとの間を往復するのに要する平均時間 (ミリ秒単位)。100 ミリ秒以下の往復時間が許容できる品質と見なされます。</p>
<p>この値が高い場合は、国際通話ルーティング、ルーティングの構成ミス、メディア サーバーの過負荷などの原因が考えられます。その結果、双方向のリアルタイムの音声会話が難しくなります。</p></td>
</tr>
<tr class="even">
<td><p><strong>低下 (MOS)</strong></p></td>
<td><p>不可</p></td>
<td><p>通話時に発生した平均オピニオン値 (MOS) 低下の平均値。 低下の値範囲は、最低 0.0 から最高 5.0 までとなります。 0.5 以下の値は、許容される低下を表します。 従来、平均オピニオン値は、ユーザーが通話の品質を 1 から 5 の範囲で評価することによって計算されていました。 Lync server では、Lync Server で一連のアルゴリズムを使って、ユーザーが通話を評価した方法を予測します。</p>
<p>この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーやエンドポイントの過負荷などの原因が考えられます。その結果、音声のひずみや欠落が生じます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>パケット損失</strong></p></td>
<td><p>不可</p></td>
<td><p>RTP パケットの平均損失率 (パケット損失は、RTP パケット (音声およびビデオをインターネット上で転送する場合に使用されるプロトコル) が宛先に到達できなかった場合に発生します)。通常、この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーの過負荷などの原因が考えられます。その結果、一般に音声のひずみや欠落が生じます。</p></td>
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


### <a name="media-quality-summary-report-metrics-video-call-summary"></a>メディア品質概要レポートの指標: ビデオ通話の概要

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
<td><p><strong>[通話の種類/エンドポイントの種類]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>この項目をクリックすると、その種類に基づく通話の詳細情報がレポートに表示されます。通話の種類は次のとおりです。</p>
<ul>
<li><p>UC ピアツーピア通話</p></li>
<li><p>UC 電話会議セッション</p></li>
<li><p>PSTN 電話会議セッション</p></li>
<li><p>PSTN 通話: メディアのバイパス</p></li>
<li><p>PSTN 通話 (非バイパス): UC レグ</p></li>
<li><p>PSTN 通話 (非バイパス): ゲートウェイ レグ</p></li>
<li><p>その他の通話の種類</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>[通話ボリューム]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>通話の種類あたりの通話の総数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[低品質通話のパーセンテージ]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>低品質として分類される通話の総数。低品質通話とは、少なくとも 1 つの測定指標が許容値を超えている通話 (たとえば、過剰なジッターが発生した通話) のことです。</p></td>
</tr>
<tr class="even">
<td><p><strong>[通話ボリューム (ワイヤレス通話)]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>ワイヤレス接続を使用した通話の数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[通話ボリューム (VPN 通話)]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>VPN 接続を使用した通話の数。</p></td>
</tr>
<tr class="even">
<td><p><strong>[通話ボリューム (外部通話)]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>外部接続 (つまり、内部ネットワークの外側の接続) を使用した通話の数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[平均ビット レート (キロビット/秒)]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>平均ビデオ ビット レート (kbps)。</p></td>
</tr>
<tr class="even">
<td><p><strong>[低ビット レート (%)]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>ビット レートが低い通話のパーセンテージ。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[送信パケット損失]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>送信パケットのリアルタイム転送プロトコル (RTP) パケット損失 (パケット損失は、RTP パケット、つまりインターネット経由で音声とビデオを転送するために使われるプロトコルの一種で、パケットが宛先に到達できなかったときに発生します)。この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーの過負荷などの原因が考えられます。パケット損失が発生すると、通常、音声のひずみや欠落が生じます。</p></td>
</tr>
<tr class="even">
<td><p><strong>[フリーズ フレーム %]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>"フリーズ" フレームのパーセンテージ。フリーズ フレームでは、通話の音声部分が続いていてもビデオの進行が停止します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[送信フレーム率 (平均)]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>通話時の送信の平均フレーム レート。</p></td>
</tr>
<tr class="even">
<td><p><strong>[着信フレーム率 (平均)]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>通話時の受信の平均フレーム レート。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[着信フレーム率 (低) (%)]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>着信ビデオのビット レートが低い通話のパーセンテージ。</p></td>
</tr>
<tr class="even">
<td><p><strong>[クライアントの正常性 (%)]</strong></p></td>
<td></td>
<td><p>通話時のクライアント デバイスの相対的な正常性を示します。</p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-application-sharing-call-summary"></a>メディア品質概要レポートの指標: アプリケーション共有の通話の概要

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
<td><p><strong>[通話の種類/エンドポイントの種類]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>この項目をクリックすると、その種類に基づく通話の詳細情報がレポートに表示されます。通話の種類は次のとおりです。</p>
<ul>
<li><p>UC ピアツーピア通話</p></li>
<li><p>UC 電話会議セッション</p></li>
<li><p>PSTN 電話会議セッション</p></li>
<li><p>PSTN 通話: メディアのバイパス</p></li>
<li><p>PSTN 通話 (非バイパス): UC レグ</p></li>
<li><p>PSTN 通話 (非バイパス): ゲートウェイ レグ</p></li>
<li><p>その他の通話の種類</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>[通話ボリューム]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>通話の種類あたりの通話の総数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[低品質通話のパーセンテージ]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>低品質として分類される通話の総数。低品質通話とは、少なくとも 1 つの測定指標が許容値を超えている通話 (たとえば、過剰なジッターが発生した通話) のことです。</p></td>
</tr>
<tr class="even">
<td><p><strong>[通話ボリューム (ワイヤレス通話)]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>ワイヤレス接続を使用した通話の数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[通話ボリューム (VPN 通話)]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>VPN 接続を使用した通話の数。</p></td>
</tr>
<tr class="even">
<td><p><strong>[通話ボリューム (外部通話)]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>外部接続 (つまり、内部ネットワークの外側の接続) を使用した通話の数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[ジッター (ミリ秒)]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>RTP パケットの着信間に検出された平均ジッター (ジッターとは、通話の "揺れ" の測定値です)。 (ジッタは、通話の&quot;shakiness&quot;の尺度です)。通常、高ジッターの値は、輻輳または過負荷のメディアサーバーによって発生し、音声が歪むか、失われる原因となります。</p></td>
</tr>
<tr class="even">
<td><p><strong>[平均相対的一方向]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>2 つのメディア エンドポイント間の相対的な一方向の平均遅延。これは 1 ホップの遅延の測定です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[RDP タイル処理の平均待機時間]</strong></p></td>
<td><p>不可</p></td>
<td><p>表示セッション中の AS 会議サーバーでの RDP タイル処理の平均遅延。平均値が高いと、表示エクスペリエンスにおける遅延が大きくなり、ネットワーク遅延も生じます。会議サーバーが過負荷になると、平均遅延が大きくなる場合があります。</p></td>
</tr>
<tr class="even">
<td><p><strong>[損失した合計タイル %]</strong></p></td>
<td><p>いいえ</p></td>
<td><p>損失した RDP タイルのパーセンテージ。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

