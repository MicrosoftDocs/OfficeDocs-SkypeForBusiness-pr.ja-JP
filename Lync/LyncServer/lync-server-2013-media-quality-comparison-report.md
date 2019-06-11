---
title: 'Lync Server 2013: メディア品質比較レポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media Quality Comparison Report
ms:assetid: c1d0b5a8-98ff-455a-b78b-a05a21cf066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205236(v=OCS.15)
ms:contentKeyID: 48185317
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6697e02d7b821ebd3dc3cabc3a95c8d00960a08
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-comparison-report-in-lync-server-2013"></a><span data-ttu-id="466ee-102">Lync Server 2013 のメディア品質比較レポート</span><span class="sxs-lookup"><span data-stu-id="466ee-102">Media Quality Comparison Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="466ee-103">_**最終更新日:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="466ee-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="466ee-104">メディア品質比較レポートを使用すると、さまざまな種類の音声通話の通話品質の値を比較できます (たとえば、ワイヤレス ネットワーク経由の通話と有線接続経由の通話の比較)。</span><span class="sxs-lookup"><span data-stu-id="466ee-104">The Media Quality Comparison Report enables you to compare call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>

<div>

## <a name="accessing-the-media-quality-comparison-report"></a><span data-ttu-id="466ee-105">メディア品質比較レポートへのアクセス</span><span class="sxs-lookup"><span data-stu-id="466ee-105">Accessing the Media Quality Comparison Report</span></span>

<span data-ttu-id="466ee-106">メディア品質比較レポートは、[監視レポート] ホーム ページからアクセスします。</span><span class="sxs-lookup"><span data-stu-id="466ee-106">The Media Quality Comparison Report is accessed from the Monitoring Reports home page.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="466ee-107">フィルター</span><span class="sxs-lookup"><span data-stu-id="466ee-107">Filters</span></span>

<span data-ttu-id="466ee-p101">フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざまな方法で表示したりする方法として利用できます。次の表に、メディア品質比較レポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="466ee-p101">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Media Quality Comparison Report.</span></span>

### <a name="media-quality-comparison-report-filters"></a><span data-ttu-id="466ee-110">メディア品質比較レポートのフィルター</span><span class="sxs-lookup"><span data-stu-id="466ee-110">Media Quality Comparison Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="466ee-111">名前</span><span class="sxs-lookup"><span data-stu-id="466ee-111">Name</span></span></th>
<th><span data-ttu-id="466ee-112">説明</span><span class="sxs-lookup"><span data-stu-id="466ee-112">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="466ee-113"><strong>開始</strong></span><span class="sxs-lookup"><span data-stu-id="466ee-113"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="466ee-p102">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="466ee-p102">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="466ee-116">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="466ee-116">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="466ee-p103">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="466ee-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="466ee-119">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="466ee-119">7/7/2012</span></span></p>
<p><span data-ttu-id="466ee-120">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="466ee-120">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="466ee-121">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="466ee-121">7/3/2012</span></span></p>
<p><span data-ttu-id="466ee-122">一週間は、日曜日から始まり、土曜日で終わるものとします。</span><span class="sxs-lookup"><span data-stu-id="466ee-122">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="466ee-123"><strong>終了</strong></span><span class="sxs-lookup"><span data-stu-id="466ee-123"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="466ee-p104">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="466ee-p104">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="466ee-126">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="466ee-126">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="466ee-p105">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="466ee-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="466ee-129">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="466ee-129">7/7/2012</span></span></p>
<p><span data-ttu-id="466ee-130">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="466ee-130">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="466ee-131">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="466ee-131">7/3/2012</span></span></p>
<p><span data-ttu-id="466ee-132">一週間は、日曜日から始まり、土曜日で終わるものとします。</span><span class="sxs-lookup"><span data-stu-id="466ee-132">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="466ee-133"><strong>通話</strong></span><span class="sxs-lookup"><span data-stu-id="466ee-133"><strong>Calls</strong></span></span></p></td>
<td><p><span data-ttu-id="466ee-p106">メインの比較項目として使用する通話の種類。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="466ee-p106">Type of call to be used as the main comparison item. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="466ee-136">[すべて]</span><span class="sxs-lookup"><span data-stu-id="466ee-136">[All]</span></span></p></li>
<li><p><span data-ttu-id="466ee-137">外部</span><span class="sxs-lookup"><span data-stu-id="466ee-137">External</span></span></p></li>
<li><p><span data-ttu-id="466ee-138">内部</span><span class="sxs-lookup"><span data-stu-id="466ee-138">Internal</span></span></p></li>
<li><p><span data-ttu-id="466ee-139">VPN</span><span class="sxs-lookup"><span data-stu-id="466ee-139">VPN</span></span></p></li>
<li><p><span data-ttu-id="466ee-140">非 VPN</span><span class="sxs-lookup"><span data-stu-id="466ee-140">Non-VPN</span></span></p></li>
<li><p><span data-ttu-id="466ee-141">有線</span><span class="sxs-lookup"><span data-stu-id="466ee-141">Wired</span></span></p></li>
<li><p><span data-ttu-id="466ee-142">ワイヤレス</span><span class="sxs-lookup"><span data-stu-id="466ee-142">Wireless</span></span></p></li>
<li><p><span data-ttu-id="466ee-143">外部および有線</span><span class="sxs-lookup"><span data-stu-id="466ee-143">External and wired</span></span></p></li>
<li><p><span data-ttu-id="466ee-144">外部およびワイヤレス</span><span class="sxs-lookup"><span data-stu-id="466ee-144">External and wireless</span></span></p></li>
<li><p><span data-ttu-id="466ee-145">外部および VPN</span><span class="sxs-lookup"><span data-stu-id="466ee-145">External and VPN</span></span></p></li>
<li><p><span data-ttu-id="466ee-146">外部および非 VPN</span><span class="sxs-lookup"><span data-stu-id="466ee-146">External and non-VPN</span></span></p></li>
<li><p><span data-ttu-id="466ee-147">内部および有線</span><span class="sxs-lookup"><span data-stu-id="466ee-147">Internal and wired</span></span></p></li>
<li><p><span data-ttu-id="466ee-148">内部およびワイヤレス</span><span class="sxs-lookup"><span data-stu-id="466ee-148">Internal and wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="466ee-149"><strong>通話との比較</strong></span><span class="sxs-lookup"><span data-stu-id="466ee-149"><strong>Compare with calls</strong></span></span></p></td>
<td><p><span data-ttu-id="466ee-p107">2 番目の比較項目として使用する通話の種類。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="466ee-p107">Type of call to be used as the secondary comparison item. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="466ee-152">[すべて]</span><span class="sxs-lookup"><span data-stu-id="466ee-152">[All]</span></span></p></li>
<li><p><span data-ttu-id="466ee-153">外部</span><span class="sxs-lookup"><span data-stu-id="466ee-153">External</span></span></p></li>
<li><p><span data-ttu-id="466ee-154">内部</span><span class="sxs-lookup"><span data-stu-id="466ee-154">Internal</span></span></p></li>
<li><p><span data-ttu-id="466ee-155">VPN</span><span class="sxs-lookup"><span data-stu-id="466ee-155">VPN</span></span></p></li>
<li><p><span data-ttu-id="466ee-156">非 VPN</span><span class="sxs-lookup"><span data-stu-id="466ee-156">Non-VPN</span></span></p></li>
<li><p><span data-ttu-id="466ee-157">有線</span><span class="sxs-lookup"><span data-stu-id="466ee-157">Wired</span></span></p></li>
<li><p><span data-ttu-id="466ee-158">ワイヤレス</span><span class="sxs-lookup"><span data-stu-id="466ee-158">Wireless</span></span></p></li>
<li><p><span data-ttu-id="466ee-159">外部および有線</span><span class="sxs-lookup"><span data-stu-id="466ee-159">External and wired</span></span></p></li>
<li><p><span data-ttu-id="466ee-160">外部およびワイヤレス</span><span class="sxs-lookup"><span data-stu-id="466ee-160">External and wireless</span></span></p></li>
<li><p><span data-ttu-id="466ee-161">外部および VPN</span><span class="sxs-lookup"><span data-stu-id="466ee-161">External and VPN</span></span></p></li>
<li><p><span data-ttu-id="466ee-162">外部および非 VPN</span><span class="sxs-lookup"><span data-stu-id="466ee-162">External and non-VPN</span></span></p></li>
<li><p><span data-ttu-id="466ee-163">内部および有線</span><span class="sxs-lookup"><span data-stu-id="466ee-163">Internal and wired</span></span></p></li>
<li><p><span data-ttu-id="466ee-164">内部およびワイヤレス</span><span class="sxs-lookup"><span data-stu-id="466ee-164">Internal and wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="466ee-165"><strong>間隔</strong></span><span class="sxs-lookup"><span data-stu-id="466ee-165"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="466ee-p108">時間間隔です。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="466ee-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="466ee-168">毎時 (最大 25 時間の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="466ee-168">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="466ee-169">毎日 (最大 31 日の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="466ee-169">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="466ee-170">毎週 (最大 12 週の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="466ee-170">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="466ee-171">入力した開始日と終了日が選択した間隔で使用できる値の最大数を超える場合は、最大数の値 (開始日からカウント) のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="466ee-171">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="466ee-172">たとえば、開始日が7/7/2012 で、終了日が2/28/2012 の [日] 間隔を選択した場合は、8/7/2012 12:00 AM から 9/7/2012 12:00 AM (つまり、31日分のデータ) のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="466ee-172">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="466ee-173">指標</span><span class="sxs-lookup"><span data-stu-id="466ee-173">Metrics</span></span>

<span data-ttu-id="466ee-174">次の表に、メディア品質比較レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="466ee-174">The following table lists the information provided in the Media Quality Comparison Report.</span></span>

### <a name="media-quality-comparison-report-metrics"></a><span data-ttu-id="466ee-175">メディア品質比較レポートの指標</span><span class="sxs-lookup"><span data-stu-id="466ee-175">Media Quality Comparison Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="466ee-176">名前</span><span class="sxs-lookup"><span data-stu-id="466ee-176">Name</span></span></th>
<th><span data-ttu-id="466ee-177">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="466ee-177">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="466ee-178">説明</span><span class="sxs-lookup"><span data-stu-id="466ee-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="466ee-179"><strong>通話ボリューム</strong></span><span class="sxs-lookup"><span data-stu-id="466ee-179"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="466ee-180">いいえ</span><span class="sxs-lookup"><span data-stu-id="466ee-180">No</span></span></p></td>
<td><p><span data-ttu-id="466ee-181">通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="466ee-181">Total number of calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="466ee-182"><strong>低下 (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="466ee-182"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="466ee-183">不可</span><span class="sxs-lookup"><span data-stu-id="466ee-183">No</span></span></p></td>
<td><p><span data-ttu-id="466ee-184">通話中に発生した平均 MOS (平均意見得点) の低下。</span><span class="sxs-lookup"><span data-stu-id="466ee-184">Average amount of MOS (mean opinion score) degradation experienced during a call.</span></span> <span data-ttu-id="466ee-185">値の劣化は、0.0 の低いものから5.0 までの範囲になります。値が0.5 以下の場合は、許容できる劣化率が示されます。</span><span class="sxs-lookup"><span data-stu-id="466ee-185">Degradation values can range from a low of 0.0 to a high of 5.0; a value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="466ee-186">歴史的な意見は、ユーザーが1対5のスケールで通話の品質を評価することによって算出されたものです。</span><span class="sxs-lookup"><span data-stu-id="466ee-186">Historically, mean opinion scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="466ee-187">Lync Server は、一連のアルゴリズムを使って、ユーザーがどのように通話を評価したかを予測します。</span><span class="sxs-lookup"><span data-stu-id="466ee-187">Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="466ee-p111">この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーやエンドポイントの過負荷などの原因が考えられます。その結果、音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="466ee-p111">High degradation values can be caused by congestion; lack of bandwidth; wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="466ee-190"><strong>低品質通話のパーセンテージ</strong></span><span class="sxs-lookup"><span data-stu-id="466ee-190"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="466ee-191">いいえ</span><span class="sxs-lookup"><span data-stu-id="466ee-191">No</span></span></p></td>
<td><p><span data-ttu-id="466ee-p112">低品質として分類される通話の総数。低品質通話とは、少なくとも 1 つの測定指標が許容値を超えている通話 (たとえば、過剰なジッターが発生した通話) のことです。</span><span class="sxs-lookup"><span data-stu-id="466ee-p112">The total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="466ee-194"><strong>往復 (ミリ秒)</strong></span><span class="sxs-lookup"><span data-stu-id="466ee-194"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="466ee-195">いいえ</span><span class="sxs-lookup"><span data-stu-id="466ee-195">No</span></span></p></td>
<td><p><span data-ttu-id="466ee-p113">リアルタイム転送プロトコル (RTP) パケットが別のエンドポイントとの間を往復するのに要する平均時間 (ミリ秒単位)。200 ミリ秒以下の往復時間が許容できる品質と見なされます。</span><span class="sxs-lookup"><span data-stu-id="466ee-p113">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="466ee-p114">この値が高い場合は、国際通話ルーティング、ルーティングの構成ミス、メディア サーバーの過負荷などの原因が考えられます。その結果、双方向のリアルタイムの音声会話が難しくなります。</span><span class="sxs-lookup"><span data-stu-id="466ee-p114">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="466ee-200"><strong>パケット損失</strong></span><span class="sxs-lookup"><span data-stu-id="466ee-200"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="466ee-201">いいえ</span><span class="sxs-lookup"><span data-stu-id="466ee-201">No</span></span></p></td>
<td><p><span data-ttu-id="466ee-p115">リアルタイム転送プロトコル (RTP) パケット損失の平均レート。(パケット損失は、RTP パケット、つまりインターネット経由で音声とビデオを転送するために使われるプロトコルの一種で、パケットが宛先に到達できなかったときに発生します)。この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーの過負荷などの原因が考えられます。パケット損失が発生すると、通常、音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="466ee-p115">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="466ee-205"><strong>[ジッター (ミリ秒)]</strong></span><span class="sxs-lookup"><span data-stu-id="466ee-205"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="466ee-206">いいえ</span><span class="sxs-lookup"><span data-stu-id="466ee-206">No</span></span></p></td>
<td><p><span data-ttu-id="466ee-207">RTP パケットの着信間に検出された平均ジッター (ジッターとは、通話の "揺れ" の測定値です)。</span><span class="sxs-lookup"><span data-stu-id="466ee-207">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="466ee-208">(ジッタは、通話の&quot;shakiness&quot;の尺度です)。通常、高ジッターの値は、輻輳または過負荷のメディアサーバーによって発生し、音声が歪むか、失われる原因となります。</span><span class="sxs-lookup"><span data-stu-id="466ee-208">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="466ee-209"><strong>ヒーラー隠し比率</strong></span><span class="sxs-lookup"><span data-stu-id="466ee-209"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="466ee-210">いいえ</span><span class="sxs-lookup"><span data-stu-id="466ee-210">No</span></span></p></td>
<td><p><span data-ttu-id="466ee-p117">サンプルの合計数に対する隠しオーディオ サンプルの平均比率 (隠しオーディオ サンプルとは、突然遷移を取り除くために使用される手法です。突然遷移は、通常、ネットワーク パケットの削除が原因で発生します)。この値が高い場合は、パケット損失やジッターのために高いレベルで損失の隠蔽が適用されています。その結果、音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="466ee-p117">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="466ee-213"><strong>ヒーラー引き伸ばし比率</strong></span><span class="sxs-lookup"><span data-stu-id="466ee-213"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="466ee-214">いいえ</span><span class="sxs-lookup"><span data-stu-id="466ee-214">No</span></span></p></td>
<td><p><span data-ttu-id="466ee-p118">サンプルの合計数に対する引き伸ばされたオーディオ サンプルの平均比率 (引き伸ばされたオーディオとは、ネットワーク パケットの削除が検出されたときに通話の品質を維持できるように拡張されたオーディオのことです)。この値が高い場合は、ジッターのために高いレベルでサンプルの引き伸ばしが行われています。その結果、音声が機械のように聞こえたりひずんで聞こえたりします。</span><span class="sxs-lookup"><span data-stu-id="466ee-p118">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="466ee-217"><strong>ヒーラー圧縮比率</strong></span><span class="sxs-lookup"><span data-stu-id="466ee-217"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="466ee-218">不可</span><span class="sxs-lookup"><span data-stu-id="466ee-218">No</span></span></p></td>
<td><p><span data-ttu-id="466ee-p119">サンプルの合計数に対する圧縮オーディオ サンプルの平均比率 (圧縮オーディオとは、ネットワーク パケットの削除が検出されたときに通話の品質を維持できるように圧縮されたオーディオのことです)。この値が高い場合は、ジッターのために高いレベルでサンプルの圧縮が行われています。その結果、音声が早送りされたように聞こえたりひずんで聞こえたりします。</span><span class="sxs-lookup"><span data-stu-id="466ee-p119">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

