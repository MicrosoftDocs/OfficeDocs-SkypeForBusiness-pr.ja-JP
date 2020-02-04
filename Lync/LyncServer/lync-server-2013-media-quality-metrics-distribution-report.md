---
title: 'Lync Server 2013: メディア品質指標配布レポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Metrics Distribution Report
ms:assetid: d07996e6-b0a5-4ff8-9512-ab707762b4e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205262(v=OCS.15)
ms:contentKeyID: 48185409
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 085525063d13c60dc1702ebf169fed92707675e5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-media-quality-metrics-distribution-report-in-lync-server-2013"></a>Lync Server 2013 でのメディア品質指標の配布レポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-06-06_

メディア品質メトリック分布レポートでは、ジッターやパケット損失などの QoE (Quality of Experience) 指標の分布値を示すグラフを確認することができます。たとえば、ユーザーが合計で 10 回の通話を行い、この 10 回の通話から以下のようなラウンドトリップ時間が報告されたとします。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>通話番号</th>
<th>往復時間 (ミリ秒)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>両面</p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>6</p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>7</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>個</p></td>
<td><p>4550</p></td>
</tr>
<tr class="odd">
<td><p>ファイブ</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>常用</p></td>
<td><p>50</p></td>
</tr>
</tbody>
</table>


これらのラウンドトリップ時間の平均は500ミリ秒 (5000 は10で割る) です。 500ミリ秒は非常に大きなラウンドトリップ時間です。その結果、ネットワークの輻輳に対して重大な問題が発生したと判断される可能性があります。 (ラウンドトリップ時間が長い場合は、通常、ネットワークの過負荷が発生します)。

実際には、通話の90% は、非常に優れた往復時間でした。結果全体に対して1つの不正な通話があっただけです。 平均ラウンドトリップ時間のみを表示する場合は、問題が発生する可能性が高くなります。

メディア品質メトリック分布レポートでは、特定の指標 (ラウンドトリップ時間など) の分布をグラフィカルに表示することによって誤った結論に至るのを防ぎます。このようなグラフでは、9 回の通話はとても良好で、1 回の通話だけが良くなかったという事実がはっきりとわかります。当然ながら、その 1 回の通話についてはさらなる調査が必要ですが、10 回のうち 9 回がとても良好だったという結果は、少なくとも現時点では、ネットワークを大きく変更する理由はないことを示唆しています。

<div>

## <a name="filters"></a>フィルター

フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざまな方法で表示したりする方法として利用できます。次の表に、メディア品質メトリック分布レポートで使用できるフィルターを示します。

### <a name="media-quality-metrics-distribution-report-filters"></a>メディア品質メトリック分布レポートのフィルター

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
<td><p><strong>x 軸の最小値</strong></p></td>
<td><p>グラフの X 軸に表示される最小の値。</p></td>
</tr>
<tr class="even">
<td><p><strong>x 軸の最大値</strong></p></td>
<td><p>グラフの X 軸に表示される最大の値。</p></td>
</tr>
<tr class="odd">
<td><p><strong>アクセスの種類</strong></p></td>
<td><p>クライアントが通話時に内部ネットワークにログオンしたか、外部ネットワークにログオンしたかを示します。次のいずれかを選択します。</p>
<ul>
<li><p>[すべて]</p></li>
<li><p>内部</p></li>
<li><p>外部</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>通話時に外部クライアントが仮想プライベート ネットワーク (VPN) 接続を使用したかどうかを示します。次のいずれかを選択します。</p>
<ul>
<li><p>[すべて]</p></li>
<li><p>VPN</p></li>
<li><p>非 VPN</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>ネットワークの種類</strong></p></td>
<td><p>通話時にクライアントが接続したネットワークの種類を示します。次のいずれかを選択します。</p>
<ul>
<li><p>[すべて]</p></li>
<li><p>有線</p></li>
<li><p>ワイヤレス</p></li>
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

