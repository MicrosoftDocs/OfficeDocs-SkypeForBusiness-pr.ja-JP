---
title: 'Lync Server 2013: メディア品質メトリック分布レポート'
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
ms.openlocfilehash: 38adc41aaffcccbb27d4c9105f0fecabcae3c21c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045119"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-media-quality-metrics-distribution-report-in-lync-server-2013"></a>Lync Server 2013 のメディア品質メトリック分布レポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-06-06_

メディア品質メトリック分布レポートを使用すると、ジッターやパケット損失などの qoe (Quality of Experience) 指標の分布値を示すグラフを表示できます。 たとえば、ユーザーが合計10件の通話を行うとします。これらの10の呼び出しでは、次のラウンドトリップ時間が報告されます。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>呼び出し番号</th>
<th>往復時間 (ミリ秒)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1 </p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>2 </p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>3 </p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>4 </p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>5 </p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>6 </p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>7 </p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>8 </p></td>
<td><p>4550</p></td>
</tr>
<tr class="odd">
<td><p>9 </p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>10 </p></td>
<td><p>50</p></td>
</tr>
</tbody>
</table>


これらのラウンドトリップ時間の平均は500ミリ秒 (5000 は10で割る) です。 500ミリ秒は、非常に大きな往復時間です。そのため、ネットワークの輻輳に重大な問題があると思われるかもしれません。 (通常、長いラウンドトリップ時間は、ネットワークの過負荷の結果です。)

実際には、通話の90% は、優れた往復時間でした。結果全体に悪影響を与える1つの呼び出しがあっただけの場合があります。 平均往復時間を確認するだけの場合は、非常に不正確な結論にジャンプする可能性があります。

メディア品質メトリック分布レポートは、指定された指標 (ラウンドトリップ時間など) のグラフィカルな配布を表示することにより、誤った結果にジャンプしないようにします。 これらのグラフは、9個の優れた通話と、非常に悪い呼び出しがあることを明確にするのに役立ちます。 確かに、1回の呼び出しをさらに調査する必要がある場合もあります。ただし、この時点では少なくとも、ネットワークに大幅な変更を加える理由がないことを推奨するのは、10件の通話が9つの場合ということです。

<div>

## <a name="filters"></a>フィルター

フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざま方法で表示したりする方法として利用できます。 次の表に、メディア品質メトリック分布レポートで使用できるフィルターを示します。

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
<td><p><strong>X 軸の最小値</strong></p></td>
<td><p>グラフの X 軸に表示される最小の値。</p></td>
</tr>
<tr class="even">
<td><p><strong>X 軸の最大値</strong></p></td>
<td><p>グラフの X 軸に表示される最大値。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>アクセスの種類</strong>]</p></td>
<td><p>クライアントが通話時に内部ネットワークにログオンしたか、外部ネットワークにログオンしたかを示します。次のいずれかを選択します。</p>
<ul>
<li><p>いずれ</p></li>
<li><p>内部</p></li>
<li><p>External</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>通話時に外部クライアントが仮想プライベート ネットワーク (VPN) 接続を使用したかどうかを示します。次のいずれかを選択します。</p>
<ul>
<li><p>いずれ</p></li>
<li><p>VPN</p></li>
<li><p>非 VPN</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>[<strong>ネットワークの種類</strong>]</p></td>
<td><p>通話時にクライアントが接続したネットワークの種類を示します。次のいずれかを選択します。</p>
<ul>
<li><p>いずれ</p></li>
<li><p>有線</p></li>
<li><p>通信</p></li>
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

