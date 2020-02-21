---
title: 'Lync Server 2013: サーバーパフォーマンスレポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server Performance Report
ms:assetid: 942bb39a-1790-498e-9d99-8f6ce2d155c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615018(v=OCS.15)
ms:contentKeyID: 48184879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff400c0384d6b9e6b51da09666629d1bb6b725ee
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200803"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-performance-report-in-lync-server-2013"></a>Lync Server 2013 のサーバーパフォーマンスレポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-01_

サーバーパフォーマンスレポートには、Microsoft Lync Server 2013 サーバーのうちで、低品質の通話のうち最大の割合を超えるサーバーが一覧表示されます。 このレポートは、サーバーの種類ごとに、次の種類について個別の統計情報を報告します。

  - 仲介サーバー

  - 音声ビデオ会議サーバー

  - 音声ビデオ エッジ サーバー

  - ゲートウェイ (仲介サーバー)

  - ゲートウェイ (仲介サーバーのバイパス)

  - ビデオ (音声ビデオ会議サーバーと音声ビデオエッジサーバーのビデオ指標を含む)

  - アプリケーション共有 (音声ビデオ会議サーバーと音声ビデオエッジサーバーのアプリケーション共有指標を含む)

このレポートに表示されるランク付けは、相対的なランク付けであることに注意してください。 たとえば、最もパフォーマンスの低いサーバーでは、1000に配置された通話の間に1つの低品質通話があるとします。 これは、許容可能なパーセンテージ (1%) です。 しかし、これが最もパフォーマンスの低いサーバーである場合 (つまり、他のすべてのサーバーの通話の割合が .1% よりも低い場合)、そのサーバーは引き続きサーバーパフォーマンスレポートに表示されます。

<div>

## <a name="accessing-the-server-performance-report"></a>サーバーパフォーマンスレポートへのアクセス

サーバーパフォーマンスレポートには、監視レポートのホームページからアクセスします。 次のいずれかの指標をクリックすると、 [Lync Server 2013 の通話リストレポート](lync-server-2013-call-list-report.md)にドリルダウンできます。

  - [通話ボリューム]

  - [低品質通話のパーセンテージ]

また、次の指標をクリックして、サーバーメディア品質傾向レポートにドリルダウンすることもできます。

  - Trend

</div>

<div>

## <a name="making-the-best-use-of-the-server-performance-report"></a>サーバーパフォーマンスレポートの活用

サーバーパフォーマンスレポートには、データをフィルター処理する方法がいくつか用意されています。たとえば、ネットワークの種類 (ワイヤード接続から発信された通話、およびワイヤレス接続からの通話の呼び出し)、アクセスの種類 (ファイアウォールの内側から発信された呼び出し、ファイアウォールの外側から発信された通話) のフィルター処理を行うことができます。 サーバーパフォーマンスレポートを表示してこれらのフィルターを使用することをお勧めします。 たとえば、通話の割合が低品質 (3.24%) の仲介サーバーがあるとします。 ワイヤレス呼び出しだけである場合は、同じサーバーに、20% に近づいている低品質通話のパーセンテージが設定されている可能性があります。 これは、サーバーが有線通話で問題が発生していないために、部分的に隠されている問題があることを意味します。

</div>

<div>

## <a name="filters"></a>フィルター

フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざま方法で表示したりする方法として利用できます。 たとえば、サーバーのパフォーマンスレポートを使用すると、返されるデータをサーバーの種類またはネットワークの種類 (有線またはワイヤレス) でフィルター処理することができます。 データをグループ化する方法も選択できます。 この場合、データは時間、日、週、または月によってグループ化されます。

次の表に、サーバーパフォーマンスレポートで使用できるフィルターを示します。

### <a name="server-performance-report-filters"></a>サーバーパフォーマンスレポートのフィルター

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
<td><p><strong>サーバーの種類</strong></p></td>
<td><p>パフォーマンスをレポートする必要があるサーバーの種類を示します。 次のいずれかを選択します。</p>
<ol>
<li><p>いずれ</p></li>
<li><p>仲介サーバー</p></li>
<li><p>音声ビデオ会議サーバー</p></li>
<li><p>音声ビデオ エッジ サーバー</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><strong>トップ N</strong></p></td>
<td><p>各カテゴリに表示されるサーバーの数 (低品質通話のパーセンテージに基づく) を示します。 たとえば、[ <strong>5</strong> ] を選択すると、5つの個サーバーが表示されます。 次のいずれかを選択します。</p>
<ol>
<li><p>いずれ</p></li>
<li><p>5</p></li>
<li><p>10 </p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p>[<strong>アクセスの種類</strong>]</p></td>
<td><p>クライアントが通話時に内部ネットワークにログオンしたか、外部ネットワークにログオンしたかを示します。次のいずれかを選択します。</p>
<ol>
<li><p>いずれ</p></li>
<li><p>内部</p></li>
<li><p>External</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p>[<strong>ネットワークの種類</strong>]</p></td>
<td><p>通話時にクライアントが接続したネットワークの種類を示します。次のいずれかを選択します。</p>
<ol>
<li><p>いずれ</p></li>
<li><p>有線</p></li>
<li><p>通信</p></li>
</ol></td>
</tr>
<tr class="odd">
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

次の表に、サーバーパフォーマンスレポートで提供される情報を示します。

### <a name="server-performance-report-metrics-audio-call-summary"></a>サーバーパフォーマンスレポートの指標: 音声通話の概要

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名前</th>
<th>並べ替え可能</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>サーバー</strong></p></td>
<td><p>いいえ</p></td>
<td><p>サーバーの名前または IP アドレス。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>通話ボリューム</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>発信された通話の合計数。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>低品質通話のパーセンテージ</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>低品質として分類される通話の総数。低品質通話とは、少なくとも 1 つの測定指標が許容値を超えている通話 (たとえば、過剰なジッターが発生した通話) のことです。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>往復 (ミリ秒)</strong>]</p></td>
<td><p>はい</p></td>
<td><p>リアルタイム転送プロトコル (RTP) パケットが別のエンドポイントとの間を往復するのに要する平均時間 (ミリ秒単位)。100 ミリ秒以下の往復時間が許容できる品質と見なされます。</p>
<p>この値が高い場合は、国際通話ルーティング、ルーティングの構成ミス、メディア サーバーの過負荷などの原因が考えられます。その結果、双方向のリアルタイムの音声会話が難しくなります。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>低下 (MOS)</strong>]</p></td>
<td><p>はい</p></td>
<td><p>通話時に発生した平均オピニオン値 (MOS) 低下の平均値。 低下の値範囲は、最低 0.0 から最高 5.0 までとなります。 0.5 以下の値は、許容される低下を表します。 従来、平均オピニオン値は、ユーザーが通話の品質を 1 から 5 の範囲で評価することによって計算されていました。 Lync Server では、監視サーバーは一連のアルゴリズムを使用して、ユーザーが通話を評価する方法を予測します。</p>
<p>この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーやエンドポイントの過負荷などの原因が考えられます。その結果、音声のひずみや欠落が生じます。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>パケット損失</strong>]</p></td>
<td><p>はい</p></td>
<td><p>リアルタイム転送プロトコル (RTP) パケット損失の平均レート。 (パケット損失は、RTP パケット、つまりインターネット経由で音声とビデオを送信するために使用されるプロトコルで、宛先に到達できなかった場合に発生します)。通常、高損失率は輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディアサーバーの過負荷などによって発生します。 パケット損失が発生すると、通常、音声のひずみや欠落が生じます。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>ジッター (ミリ秒)</strong>]</p></td>
<td><p>はい</p></td>
<td><p>RTP パケットの着信間に検出された平均ジッター (ジッターとは、通話の "揺れ" の測定値です)。 (ジッターは、通話の&quot;過&quot;の測定値です)。高ジッター値は、通常、混雑または過負荷のメディアサーバーによって発生し、その結果、音声がひずむか失われます。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>ヒーラー隠し比率</strong>]</p></td>
<td><p>はい</p></td>
<td><p>サンプルの合計数に対する隠しオーディオ サンプルの平均比率 (隠しオーディオ サンプルとは、突然遷移を取り除くために使用される手法です。突然遷移は、通常、ネットワーク パケットの削除が原因で発生します)。この値が高い場合は、パケット損失やジッターのために高いレベルで損失の隠蔽が適用されています。その結果、音声のひずみや欠落が生じます。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>ヒーラー引き伸ばし比率</strong>]</p></td>
<td><p>はい</p></td>
<td><p>サンプルの合計数に対する引き伸ばされたオーディオ サンプルの平均比率 (引き伸ばされたオーディオとは、ネットワーク パケットの削除が検出されたときに通話の品質を維持できるように拡張されたオーディオのことです)。この値が高い場合は、ジッターのために高いレベルでサンプルの引き伸ばしが行われています。その結果、音声が機械のように聞こえたりひずんで聞こえたりします。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>ヒーラー圧縮比率</strong>]</p></td>
<td><p>はい</p></td>
<td><p>サンプルの合計数に対する圧縮オーディオ サンプルの平均比率 (圧縮オーディオとは、ネットワーク パケットの削除が検出されたときに通話の品質を維持できるように圧縮されたオーディオのことです)。この値が高い場合は、ジッターのために高いレベルでサンプルの圧縮が行われています。その結果、音声が早送りされたように聞こえたりひずんで聞こえたりします。</p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-video-call-summary"></a>サーバーパフォーマンスレポートの指標: ビデオ通話の概要

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
<td><p>[<strong>通話の種類/エンドポイントの種類</strong>]</p></td>
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
<td><p>[<strong>通話ボリューム</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>通話の種類当たりの通話の総数。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>低品質通話のパーセンテージ</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>低品質として分類される通話の総数。低品質通話とは、少なくとも 1 つの測定指標が許容値を超えている通話 (たとえば、過剰なジッターが発生した通話) のことです。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>通話ボリューム (ワイヤレス通話)</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>ワイヤレス接続を使用した通話の総数。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>通話ボリューム (VPN 通話)</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>VPN 接続を使用した通話の総数。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>通話ボリューム (外部通話)</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>外部接続 (つまり、内部ネットワークの外側の接続) を使用した通話の数。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>Avg bit-rate (Kbits/s)</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>平均ビデオ ビット レート (1 秒あたりのキロビット)。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>Low bit-rate %</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>ビット レートが低い通話のパーセンテージ。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>Outbound packet loss</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>送信パケットのリアルタイム転送プロトコル (RTP) パケット損失。 (パケット損失は、RTP パケット、つまりインターネット経由で音声とビデオを送信するために使用されるプロトコルで、宛先に到達できなかった場合に発生します)。通常、高損失率は輻輳が原因で発生します。帯域幅の不足。ワイヤレスの輻輳または干渉。または、オーバーロードされたメディアサーバー。 パケット損失が発生すると、通常、音声のひずみや欠落が生じます。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>フリーズ フレーム %</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>"フリーズ" フレームのパーセンテージ。フリーズ フレームでは、通話の音声部分が続いていてもビデオの進行が停止します。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>Outbound avg frame rate</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>通話時の送信の平均フレーム レート。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>Inbound avg frame rate</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>通話時の受信の平均フレーム レート。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>Inbound low frame rate %</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>着信ビデオのビット レートが低い通話のパーセンテージ。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>Client health %</strong>]</p></td>
<td></td>
<td><p>通話時のクライアント デバイスの相対的な正常性を示します。</p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-application-sharing-call-summary"></a>サーバーパフォーマンスレポートの指標: アプリケーション共有の通話の概要

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
<td><p>[<strong>通話の種類/エンドポイントの種類</strong>]</p></td>
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
<td><p>[<strong>通話ボリューム</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>通話の種類当たりの通話の総数。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>低品質通話のパーセンテージ</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>低品質として分類される通話の総数。低品質通話とは、少なくとも 1 つの測定指標が許容値を超えている通話 (たとえば、過剰なジッターが発生した通話) のことです。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>通話ボリューム (ワイヤレス通話)</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>ワイヤレス接続を使用した通話の総数。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>通話ボリューム (VPN 通話)</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>VPN 接続を使用した通話の総数。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>通話ボリューム (外部通話)</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>外部接続 (つまり、内部ネットワークの外側の接続) を使用した通話の数。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>ジッター (ミリ秒)</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>RTP パケットの着信間に検出された平均ジッター (ジッターとは、通話の "揺れ" の測定値です)。 (ジッターは、通話の&quot;過&quot;の測定値です)。高ジッター値は、通常、混雑または過負荷のメディアサーバーによって発生し、その結果、音声がひずむか失われます。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>Relative one way delay burst density (ms)</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>2 つのメディア エンドポイント間の相対的な一方向の平均遅延。これは、1 ホップの遅延の測定です。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>RDP Tile processing latency burst density (ms)</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>表示セッション中の AS 会議サーバーでの RDP タイル処理の平均遅延。ネットワーク遅延はこの指標の対象外です。平均値が高いと、表示の際の遅延が大きくなります。過負荷の会議サーバーでは平均遅延が大きくなる場合があります。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>損失した合計タイル %</strong>]</p></td>
<td><p>いいえ</p></td>
<td><p>損失した RDP タイル数のパーセンテージ。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

