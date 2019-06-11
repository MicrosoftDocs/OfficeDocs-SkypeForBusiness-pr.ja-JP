---
title: 'Lync Server 2013: 会議の診断レポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Diagnostic Report
ms:assetid: e9edc23c-8ce8-4ab8-8786-9d22e1e51e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615042(v=OCS.15)
ms:contentKeyID: 48185901
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 279d844a4c67d3b09b35fff92f6868cae8971059
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840500"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="cc2af-102">Lync Server 2013 での会議の診断レポート</span><span class="sxs-lookup"><span data-stu-id="cc2af-102">Conference Diagnostic Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc2af-103">_**最終更新日:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="cc2af-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="cc2af-104">電話会議診断レポートは、すべての電話会議セッションの成功とエラーに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="cc2af-104">The Conference Diagnostic Report provides information about the success and failure of all conferencing sessions.</span></span> <span data-ttu-id="cc2af-105">Microsoft Lync Server では、さまざまな種類のエラーを区別していることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="cc2af-105">Note that Microsoft Lync Server distinguishes between different kinds of failure:</span></span>

  - <span data-ttu-id="cc2af-p102">**予期されたエラー**。予期されたエラーは通常、単に技術的な意味においてのエラーです。たとえば、誰かが会議を始めたものの、1 人も参加しないうちに切断したとします。会議は開始されたのに完了しなかったので、技術的にはエラーです。しかし 1 人も参加しないうちに開催者が会議をキャンセルした場合に会議が完了しないのは当然なので、発生が予期されたエラーです。</span><span class="sxs-lookup"><span data-stu-id="cc2af-p102">**Expected failure**. An expected failure is typically a failure only in the most technical sense. For example, suppose someone starts a conference but hangs up before anyone can join. Technically that's a failure: the conference was initiated, but not completed. However, that's a failure that you would expect to happen: if the organizer cancels the conference before anyone can join then you would not expect that conference to be completed.</span></span>

  - <span data-ttu-id="cc2af-p103">**予期しないエラー**。予期しないエラーは名前が示すとおり、その状況下では発生が予期されないエラーです。たとえば、開催者の会議ポリシーが取得できないために会議が開催できないとします。どのような場合でもユーザーの会議ポリシーは常に取得できるはずなので、これは予期しないエラーです。</span><span class="sxs-lookup"><span data-stu-id="cc2af-p103">**Unexpected failure**. An unexpected error is exactly what the name implies: an error that, based on the circumstances, you would not expect to occur. For example, suppose a conference could not be held because the organizer's meeting policy could not be retrieved. That's an unexpected error: after all, you should always be able to retrieve a user's meeting policy.</span></span>

<span data-ttu-id="cc2af-p104">成功、予期されたエラー、および予期しないエラーの指標はセッションの合計数の指標に加算されない場合があることに注意してください。たとえば、レポートに次の値が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="cc2af-p104">Note that the Success, Expected failure, and Unexpected failure metrics might not add up to the Total sessions metric. For example, you might see the following values in the Report:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cc2af-117">成功</span><span class="sxs-lookup"><span data-stu-id="cc2af-117">Successes</span></span></th>
<th><span data-ttu-id="cc2af-118">予期されたエラー</span><span class="sxs-lookup"><span data-stu-id="cc2af-118">Expected failures</span></span></th>
<th><span data-ttu-id="cc2af-119">予期しないエラー</span><span class="sxs-lookup"><span data-stu-id="cc2af-119">Unexpected failures</span></span></th>
<th><span data-ttu-id="cc2af-120">セッションの合計数</span><span class="sxs-lookup"><span data-stu-id="cc2af-120">Total sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cc2af-121">2024</span><span class="sxs-lookup"><span data-stu-id="cc2af-121">2024</span></span></p></td>
<td><p><span data-ttu-id="cc2af-122">469</span><span class="sxs-lookup"><span data-stu-id="cc2af-122">469</span></span></p></td>
<td><p><span data-ttu-id="cc2af-123">16</span><span class="sxs-lookup"><span data-stu-id="cc2af-123">16</span></span></p></td>
<td><p><span data-ttu-id="cc2af-124">2521</span><span class="sxs-lookup"><span data-stu-id="cc2af-124">2521</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cc2af-125">2,024 + 469 + 16 は合計 2,509 セッションになりますが、[セッションの合計数] 列には合計 2,521 セッションと表示されています。</span><span class="sxs-lookup"><span data-stu-id="cc2af-125">If you add 2024 + 469 + 16 you get a total of 2,509 sessions and yet, the Total sessions column shows a total of 2,521 sessions.</span></span> <span data-ttu-id="cc2af-126">"不足分" の 12 セッションは、システムが成功または失敗に分類できなかったセッションです。</span><span class="sxs-lookup"><span data-stu-id="cc2af-126">The "missing" 12 sessions for are sessions that the system was unable to categorize as successful or unsuccessful.</span></span> <span data-ttu-id="cc2af-127">このような場合には、サードパーティ製の製品で、サーバーの監視に馴染みのない新しい診断コードが導入されていることがあります。</span><span class="sxs-lookup"><span data-stu-id="cc2af-127">That will sometimes be the case when a third-party product introduces a new diagnostic code that is unfamiliar to Monitoring Server.</span></span> <span data-ttu-id="cc2af-128">その場合、当該製品を使用した通話や当該診断コードのレポートは、成功、予期されたエラー、または予期しないエラーに分類できるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="cc2af-128">When that happens, calls made using that product, and reporting that diagnostic code, cannot always be categorized as being a Success, an Expected failure, or an Unexpected failure.</span></span>

<div>

## <a name="accessing-the-conference-diagnostic-report"></a><span data-ttu-id="cc2af-129">電話会議診断レポートへのアクセス</span><span class="sxs-lookup"><span data-stu-id="cc2af-129">Accessing the Conference Diagnostic Report</span></span>

<span data-ttu-id="cc2af-130">電話会議診断レポートは [監視レポート] ホーム ページからアクセスします。</span><span class="sxs-lookup"><span data-stu-id="cc2af-130">The Conference Diagnostic Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="cc2af-131">次の指標のいずれかをクリックして、 [Lync Server 2013 でエラー配布レポート](lync-server-2013-failure-distribution-report.md)にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="cc2af-131">You can access the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="cc2af-132">予期しないエラー ボリューム</span><span class="sxs-lookup"><span data-stu-id="cc2af-132">Unexpected failure volume</span></span>

  - <span data-ttu-id="cc2af-133">予期されるエラー ボリューム</span><span class="sxs-lookup"><span data-stu-id="cc2af-133">Expected failure volume</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-diagnostic-report"></a><span data-ttu-id="cc2af-134">電話会議診断レポートの活用</span><span class="sxs-lookup"><span data-stu-id="cc2af-134">Making the Best Use of the Conference Diagnostic Report</span></span>

<span data-ttu-id="cc2af-135">電話会議診断レポートには一連のグラフが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cc2af-135">The Conference Diagnostic Report includes a series of graphs.</span></span> <span data-ttu-id="cc2af-136">グラフの各列は実際にはハイパーリンクです。</span><span class="sxs-lookup"><span data-stu-id="cc2af-136">Each of the columns shown in the graph is actually a hyperlink.</span></span> <span data-ttu-id="cc2af-137">列をクリックすると、その期間[内の Lync Server 2013 のエラー配布レポート](lync-server-2013-failure-distribution-report.md)とその会議の種類が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cc2af-137">If you click a column, you'll drill down to the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) for that time period and that conference type.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="cc2af-138">フィルター</span><span class="sxs-lookup"><span data-stu-id="cc2af-138">Filters</span></span>

<span data-ttu-id="cc2af-p108">フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざまな方法で表示したりする方法として利用できます。たとえば、電話会議診断レポートでは、実行した電話会議の種類 (フォーカスベースの電話会議など) や、電話会議で使用したエッジ サーバーに基づくフィルターを行えます。また、データをグループ化する方法を選択することもできます。この場合は、時間、日、週、または月を基準に会議がグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="cc2af-p108">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Conference Diagnostic Report enables you to filter on such things as the type of conference being conducted (for example, a Focus-based conference) or by the Edge Server used in the conference. You can also choose how data should be grouped. In this case, conferences are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="cc2af-143">次の表に、電話会議診断レポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="cc2af-143">The following table lists the filters that you can use with the Conference Diagnostic Report.</span></span>

### <a name="conference-diagnostic-report-filters"></a><span data-ttu-id="cc2af-144">電話会議診断レポートのフィルター</span><span class="sxs-lookup"><span data-stu-id="cc2af-144">Conference Diagnostic Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cc2af-145">名前</span><span class="sxs-lookup"><span data-stu-id="cc2af-145">Name</span></span></th>
<th><span data-ttu-id="cc2af-146">説明</span><span class="sxs-lookup"><span data-stu-id="cc2af-146">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cc2af-147"><strong>開始</strong></span><span class="sxs-lookup"><span data-stu-id="cc2af-147"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="cc2af-p109">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="cc2af-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="cc2af-150">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="cc2af-150">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="cc2af-p110">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="cc2af-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="cc2af-153">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="cc2af-153">7/7/2012</span></span></p>
<p><span data-ttu-id="cc2af-154">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="cc2af-154">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="cc2af-155">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="cc2af-155">7/3/2012</span></span></p>
<p><span data-ttu-id="cc2af-156">一週間は、日曜日から始まり、土曜日で終わるものとします。</span><span class="sxs-lookup"><span data-stu-id="cc2af-156">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc2af-157"><strong>終了</strong></span><span class="sxs-lookup"><span data-stu-id="cc2af-157"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="cc2af-p111">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="cc2af-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="cc2af-160">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="cc2af-160">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="cc2af-p112">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="cc2af-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="cc2af-163">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="cc2af-163">7/7/2012</span></span></p>
<p><span data-ttu-id="cc2af-164">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="cc2af-164">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="cc2af-165">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="cc2af-165">7/3/2012</span></span></p>
<p><span data-ttu-id="cc2af-166">一週間は、日曜日から始まり、土曜日で終わるものとします。</span><span class="sxs-lookup"><span data-stu-id="cc2af-166">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc2af-167"><strong>[間隔]</strong></span><span class="sxs-lookup"><span data-stu-id="cc2af-167"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="cc2af-p113">時間間隔です。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="cc2af-p113">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="cc2af-170">毎時 (最大 25 時間の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="cc2af-170">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="cc2af-171">毎日 (最大 31 日の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="cc2af-171">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="cc2af-172">毎週 (最大 12 週の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="cc2af-172">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="cc2af-173">毎月 (最大 12 か月の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="cc2af-173">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="cc2af-174">入力した開始日と終了日が選択した間隔で使用できる値の最大数を超える場合は、最大数の値 (開始日からカウント) のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cc2af-174">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="cc2af-175">たとえば、開始日が7/7/2012 で、終了日が2/28/2012 の [日] 間隔を選択した場合は、8/7/2012 12:00 AM から 9/7/2012 12:00 AM (つまり、31日分のデータ) のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cc2af-175">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc2af-176"><strong>プール</strong></span><span class="sxs-lookup"><span data-stu-id="cc2af-176"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="cc2af-p115">レジストラー プールまたはエッジ サーバーの完全修飾ドメイン名 (FQDN)。個別のプールを選択するか、[<strong>すべて</strong>] をクリックしてすべてのプールのデータを表示できます。このドロップダウン リストは、データベース内のレコードに基づいて自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="cc2af-p115">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc2af-180"><strong>電話会議セッション</strong></span><span class="sxs-lookup"><span data-stu-id="cc2af-180"><strong>Conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="cc2af-p116">電話会議セッションの種類を示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="cc2af-p116">Indicates the type of conferencing session. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="cc2af-183">[すべて]</span><span class="sxs-lookup"><span data-stu-id="cc2af-183">[All]</span></span></p></li>
<li><p><span data-ttu-id="cc2af-184">フォーカス セッション</span><span class="sxs-lookup"><span data-stu-id="cc2af-184">Focus sessions</span></span></p></li>
<li><p><span data-ttu-id="cc2af-185">すべての MCU セッション</span><span class="sxs-lookup"><span data-stu-id="cc2af-185">All MCU sessions</span></span></p></li>
<li><p><span data-ttu-id="cc2af-186">IM 電話会議</span><span class="sxs-lookup"><span data-stu-id="cc2af-186">IM conferencing</span></span></p></li>
<li><p><span data-ttu-id="cc2af-187">アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="cc2af-187">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="cc2af-188">音声ビデオ会議</span><span class="sxs-lookup"><span data-stu-id="cc2af-188">A/V conferencing</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="cc2af-189">指標</span><span class="sxs-lookup"><span data-stu-id="cc2af-189">Metrics</span></span>

<span data-ttu-id="cc2af-190">次の表に、電話会議診断レポートでそれぞれの種類の電話会議セッションについて表示される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="cc2af-190">The following table lists the information provided in the Conference Diagnostic Report for each type of conferencing session.</span></span>

### <a name="conference-diagnostic-report-metrics"></a><span data-ttu-id="cc2af-191">電話会議診断レポートの指標</span><span class="sxs-lookup"><span data-stu-id="cc2af-191">Conference Diagnostic Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cc2af-192">名前</span><span class="sxs-lookup"><span data-stu-id="cc2af-192">Name</span></span></th>
<th><span data-ttu-id="cc2af-193">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="cc2af-193">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="cc2af-194">説明</span><span class="sxs-lookup"><span data-stu-id="cc2af-194">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cc2af-195"><strong>成功ボリューム</strong></span><span class="sxs-lookup"><span data-stu-id="cc2af-195"><strong>Success volume</strong></span></span></p></td>
<td><p><span data-ttu-id="cc2af-196">いいえ</span><span class="sxs-lookup"><span data-stu-id="cc2af-196">No</span></span></p></td>
<td><p><span data-ttu-id="cc2af-197">成功した電話会議の合計数。</span><span class="sxs-lookup"><span data-stu-id="cc2af-197">Total number of successful conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc2af-198"><strong>成功率</strong></span><span class="sxs-lookup"><span data-stu-id="cc2af-198"><strong>Success percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="cc2af-199">いいえ</span><span class="sxs-lookup"><span data-stu-id="cc2af-199">No</span></span></p></td>
<td><p><span data-ttu-id="cc2af-p117">大きな問題なく完了した電話会議の比率。成功ボリュームをセッションの合計数で割ることにより計算されます。</span><span class="sxs-lookup"><span data-stu-id="cc2af-p117">Percentage of conferences that completed with significant problems. Calculated by dividing the Success volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc2af-202"><strong>予期されるエラー ボリューム</strong></span><span class="sxs-lookup"><span data-stu-id="cc2af-202"><strong>Expected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="cc2af-203">いいえ</span><span class="sxs-lookup"><span data-stu-id="cc2af-203">No</span></span></p></td>
<td><p><span data-ttu-id="cc2af-204">&quot;予期しないエラー&quot;が発生した会議の合計数です。</span><span class="sxs-lookup"><span data-stu-id="cc2af-204">Total number of conferences where an &quot;expected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="cc2af-p118">予期されるエラーとは、発生が予想されるエラーです。たとえば、ステータスを "応答不可" に設定しているユーザーへの通話は、すべてエラーになることが予想されます。</span><span class="sxs-lookup"><span data-stu-id="cc2af-p118">An expected failure is a failure that is expected to happen. For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc2af-207"><strong>予期されるエラー率</strong></span><span class="sxs-lookup"><span data-stu-id="cc2af-207"><strong>Expected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="cc2af-208">いいえ</span><span class="sxs-lookup"><span data-stu-id="cc2af-208">No</span></span></p></td>
<td><p><span data-ttu-id="cc2af-p119">予期されるエラーが発生した電話会議の比率。予期されるエラー ボリュームをセッションの合計数で割ることにより計算されます。</span><span class="sxs-lookup"><span data-stu-id="cc2af-p119">Percentage of conferences that experienced an expected error. Calculated by dividing the Expected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc2af-211"><strong>予期しないエラー ボリューム</strong></span><span class="sxs-lookup"><span data-stu-id="cc2af-211"><strong>Unexpected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="cc2af-212">いいえ</span><span class="sxs-lookup"><span data-stu-id="cc2af-212">No</span></span></p></td>
<td><p><span data-ttu-id="cc2af-213">&quot;予期しないエラー&quot;が発生した電話会議の合計数です。</span><span class="sxs-lookup"><span data-stu-id="cc2af-213">Total number of conferences where an &quot;unexpected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="cc2af-p120">予期しないエラーとは、一見すると正常と思われるシステムで発生するエラーです。たとえば、呼び出し元が保留中になっている通話は終了してはなりません。この操作を行うと、予期しないエラーとしてフラグが設定されます。</span><span class="sxs-lookup"><span data-stu-id="cc2af-p120">An unexpected failure is a failure that occurs in what would appear to be an otherwise healthy system. For example, a call should not be terminated if the caller is placed on hold. If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc2af-217"><strong>予期しないエラー率</strong></span><span class="sxs-lookup"><span data-stu-id="cc2af-217"><strong>Unexpected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="cc2af-218">いいえ</span><span class="sxs-lookup"><span data-stu-id="cc2af-218">No</span></span></p></td>
<td><p><span data-ttu-id="cc2af-p121">予期しないエラーが発生した電話会議の比率。予期しないエラー ボリュームをセッションの合計数で割ることにより計算されます。</span><span class="sxs-lookup"><span data-stu-id="cc2af-p121">Percentage of conferences that experienced an unexpected error. Calculated by dividing the Unexpected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc2af-221"><strong>セッションの合計数</strong></span><span class="sxs-lookup"><span data-stu-id="cc2af-221"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="cc2af-222">不可</span><span class="sxs-lookup"><span data-stu-id="cc2af-222">No</span></span></p></td>
<td><p><span data-ttu-id="cc2af-223">電話会議の合計数。成功した電話会議、エラーが発生した電話会議 (予期されるエラーと予期しないエラーの両方)、および未分類の電話会議を含みます。</span><span class="sxs-lookup"><span data-stu-id="cc2af-223">Total number of conferences, including successful conferences, failed conferences (both expected failures and unexpected failures), and uncategorized conferences.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

