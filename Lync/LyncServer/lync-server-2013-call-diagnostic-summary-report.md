---
title: 'Lync Server 2013: 通話診断の概要レポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Diagnostic Summary Report
ms:assetid: 9091de56-13e6-440e-9353-f57c10c906fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615016(v=OCS.15)
ms:contentKeyID: 48184789
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c055a48684716ce64428615759b023242b9e4ff5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203443"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-diagnostic-summary-report-in-lync-server-2013"></a><span data-ttu-id="aada1-102">Lync Server 2013 の通話診断の概要レポート</span><span class="sxs-lookup"><span data-stu-id="aada1-102">Call Diagnostic Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aada1-103">_**トピックの最終更新日:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="aada1-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="aada1-p101">通話診断の概要レポートでは、失敗したピアツーピア セッションや会議セッションの概要を確認できます。このレポートでは、両方の種類のセッション全体のエラー率が表示され、エラー情報がセッション モダリティごとに分類されます。</span><span class="sxs-lookup"><span data-stu-id="aada1-p101">The Call Diagnostic Summary Report provides an overall look at failed peer-to-peer and conferencing sessions. The report shows the overall failure rate for both types of sessions, and further breaks the failure information down by session modality type:</span></span>

  - <span data-ttu-id="aada1-106">インスタント メッセージング</span><span class="sxs-lookup"><span data-stu-id="aada1-106">Instant messaging</span></span>

  - <span data-ttu-id="aada1-107">アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="aada1-107">Application sharing</span></span>

  - <span data-ttu-id="aada1-108">ファイル送信</span><span class="sxs-lookup"><span data-stu-id="aada1-108">File transfer</span></span>

  - <span data-ttu-id="aada1-109">オーディオ</span><span class="sxs-lookup"><span data-stu-id="aada1-109">Audio</span></span>

  - <span data-ttu-id="aada1-110">ビデオ</span><span class="sxs-lookup"><span data-stu-id="aada1-110">Video</span></span>

<div>

## <a name="accessing-the-call-diagnostic-summary-report"></a><span data-ttu-id="aada1-111">通話診断の概要レポートへのアクセス</span><span class="sxs-lookup"><span data-stu-id="aada1-111">Accessing the Call Diagnostic Summary Report</span></span>

<span data-ttu-id="aada1-112">通話診断の概要レポートには、監視レポートのホームページからアクセスします。</span><span class="sxs-lookup"><span data-stu-id="aada1-112">The Call Diagnostic Summary Report is accessed from the Monitoring Reports Home page.</span></span> <span data-ttu-id="aada1-113">通話診断の概要レポートでは、レポートの [ピアツーピアセッションの概要] セクションにある [エラー率] 指標をクリックすることによって、 [Lync Server 2013 のピアツーピアアクティビティ診断レポート](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="aada1-113">From the Call Diagnostic Summary Report you can access the [Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) by clicking the Failure rate metric under the Peer-to-Peer Session Summary section of the report.</span></span> <span data-ttu-id="aada1-114">また、次のいずれかの電話会議指標をクリックして、 [Lync Server 2013 の電話会議診断レポート](lync-server-2013-conference-diagnostic-report.md)にアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="aada1-114">You can also access the [Conference Diagnostic Report in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md) by clicking any of the following conference metrics:</span></span>

  - <span data-ttu-id="aada1-115">[全体的なセッション エラー率]</span><span class="sxs-lookup"><span data-stu-id="aada1-115">Overall session failure rate</span></span>

  - <span data-ttu-id="aada1-116">[フォーカス エラー率]</span><span class="sxs-lookup"><span data-stu-id="aada1-116">Focus failure rate</span></span>

  - <span data-ttu-id="aada1-117">[MCU エラー率]</span><span class="sxs-lookup"><span data-stu-id="aada1-117">MCU failure rate</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a><span data-ttu-id="aada1-118">通話診断の概要レポートの活用</span><span class="sxs-lookup"><span data-stu-id="aada1-118">Making the Best Use of the Call Diagnostic Summary Report</span></span>

<span data-ttu-id="aada1-119">通話診断の概要レポートには、Microsoft Lync Server 2013 で使用されるさまざまなモダリティのエラー率を比較するグラフが含まれています。</span><span class="sxs-lookup"><span data-stu-id="aada1-119">The Call Diagnostic Summary Report includes graphs that compare failure rates for the various modalities used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="aada1-120">これらのグラフの列は、実際にはホットリンクです。たとえば、ピアツーピアセッションの [インスタントメッセージング] 列をクリックすると、 [Lync Server 2013 のピアツーピアアクティビティ診断レポート](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)のインスタンスにドリルダウンします。このレポートでは、通話診断の概要レポートに含まれるすべてのインスタントメッセージングセッションに関する追加の詳細が提供されます。</span><span class="sxs-lookup"><span data-stu-id="aada1-120">The columns in these graphs are actually hotlinks; for example, if you click the Instant messaging column for peer-to-peer sessions, you'll drill down to an instance of the [Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md), a report that provides additional details about all the instant messaging sessions included in the Call Diagnostic Summary Report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="aada1-121">フィルター</span><span class="sxs-lookup"><span data-stu-id="aada1-121">Filters</span></span>

<span data-ttu-id="aada1-p104">フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざま方法で表示したりする方法として利用できます。たとえば、通話診断の概要レポートでは、セッションで使用されるレジストラー プールやエッジ プールのような要素をフィルターできます。また、データをグループ化する方法を選択することもできます。この場合は、通話が、時間、日、週、または月の単位でグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="aada1-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Call Diagnostic Summary Report enables you to filter on such things as the Registrar pool or Edge Server used in the session. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="aada1-126">次の表に、通話診断の概要レポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="aada1-126">The following table lists the filters that you can use with the Call Diagnostic Summary Report.</span></span>

### <a name="call-diagnostic-summary-report-filters"></a><span data-ttu-id="aada1-127">通話診断の概要レポートのフィルター</span><span class="sxs-lookup"><span data-stu-id="aada1-127">Call Diagnostic Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aada1-128">名前</span><span class="sxs-lookup"><span data-stu-id="aada1-128">Name</span></span></th>
<th><span data-ttu-id="aada1-129">説明</span><span class="sxs-lookup"><span data-stu-id="aada1-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aada1-130"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="aada1-130"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="aada1-p105">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="aada1-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="aada1-133">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="aada1-133">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="aada1-p106">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="aada1-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="aada1-136">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="aada1-136">7/7/2012</span></span></p>
<p><span data-ttu-id="aada1-137">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="aada1-137">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="aada1-138">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="aada1-138">7/3/2012</span></span></p>
<p><span data-ttu-id="aada1-139">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="aada1-139">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aada1-140"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="aada1-140"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="aada1-p107">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="aada1-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="aada1-143">7/7/2012 13:00</span><span class="sxs-lookup"><span data-stu-id="aada1-143">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="aada1-p108">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="aada1-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="aada1-146">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="aada1-146">7/7/2012</span></span></p>
<p><span data-ttu-id="aada1-147">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="aada1-147">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="aada1-148">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="aada1-148">7/3/2012</span></span></p>
<p><span data-ttu-id="aada1-149">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="aada1-149">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aada1-150"><strong>間隔</strong></span><span class="sxs-lookup"><span data-stu-id="aada1-150"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="aada1-p109">時間間隔です。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="aada1-p109">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="aada1-153">時間単位 (最大 25 時間の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="aada1-153">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="aada1-154">日単位 (最大 31 日の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="aada1-154">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="aada1-155">週単位 (最大 12 週の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="aada1-155">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="aada1-156">月単位 (最大 12 か月の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="aada1-156">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="aada1-p110">入力した開始日と終了日が選択した間隔で使用できる値の最大数を超える場合は、最大数の値 (開始日からカウント) のみが表示されます。たとえば、開始日と終了日をそれぞれ 7/7/2012 (2012 年 7 月 7 日)、2/28/2012 (2012 年 2 月 28 日) として毎日の間隔を選択しても、2012 年 8 月 7 日の午前 12:00 から 2012 年 9 月 7 日の午前 12:00 までの日付のデータ (つまり、合計 31 日分のデータのみ) が表示されることになります。</span><span class="sxs-lookup"><span data-stu-id="aada1-p110">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aada1-159"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="aada1-159"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="aada1-p111">レジストラー プールまたはエッジ サーバーの完全修飾ドメイン名 (FQDN)。個別のプールを選択するか、[<strong>すべて</strong>] をクリックしてすべてのプールのデータを表示できます。このドロップダウン リストは、データベース内のレコードに基づいて自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="aada1-p111">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="aada1-163">ピアツーピア セッションの指標</span><span class="sxs-lookup"><span data-stu-id="aada1-163">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="aada1-164">次の表に、ピアツーピア セッション (参加者が 2 人だけのセッション) の通話診断の概要レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="aada1-164">The following table lists the information provided in the Call Diagnostic Summary Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="aada1-165">ピアツーピア セッションの指標</span><span class="sxs-lookup"><span data-stu-id="aada1-165">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aada1-166">名前</span><span class="sxs-lookup"><span data-stu-id="aada1-166">Name</span></span></th>
<th><span data-ttu-id="aada1-167">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="aada1-167">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="aada1-168">説明</span><span class="sxs-lookup"><span data-stu-id="aada1-168">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aada1-169">[<strong>セッションの合計数</strong>]</span><span class="sxs-lookup"><span data-stu-id="aada1-169"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="aada1-170">いいえ</span><span class="sxs-lookup"><span data-stu-id="aada1-170">No</span></span></p></td>
<td><p><span data-ttu-id="aada1-171">実施されたピアツーピア セッションの総数です。</span><span class="sxs-lookup"><span data-stu-id="aada1-171">Total number of peer-to-peer sessions conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aada1-172"><strong>エラー率</strong></span><span class="sxs-lookup"><span data-stu-id="aada1-172"><strong>Failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="aada1-173">いいえ</span><span class="sxs-lookup"><span data-stu-id="aada1-173">No</span></span></p></td>
<td><p><span data-ttu-id="aada1-p112">エラーが発生したピアツーピア セッションの割合です。この項目をクリックすると、このレポートでは、エラーが発生したピアツーピア セッションに関する詳細情報を示すピアツーピア アクティビティ診断レポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="aada1-p112">Percentage of peer-to-peer sessions that failed. When you click this item, the report shows the Peer-to-Peer Activity Diagnostic report, which displays more detailed information about the failed peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="aada1-176">電話会議セッションの指標</span><span class="sxs-lookup"><span data-stu-id="aada1-176">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="aada1-177">次の表に、電話会議セッション (参加者が 3 人以上のセッション) の通話診断レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="aada1-177">The following table lists the information provided in the Call Diagnostic Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="aada1-178">電話会議セッションの指標</span><span class="sxs-lookup"><span data-stu-id="aada1-178">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aada1-179">名前</span><span class="sxs-lookup"><span data-stu-id="aada1-179">Name</span></span></th>
<th><span data-ttu-id="aada1-180">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="aada1-180">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="aada1-181">説明</span><span class="sxs-lookup"><span data-stu-id="aada1-181">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aada1-182">[<strong>電話会議の合計数</strong>]</span><span class="sxs-lookup"><span data-stu-id="aada1-182"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="aada1-183">いいえ</span><span class="sxs-lookup"><span data-stu-id="aada1-183">No</span></span></p></td>
<td><p><span data-ttu-id="aada1-184">実施された電話会議の総数です。</span><span class="sxs-lookup"><span data-stu-id="aada1-184">Total number of conferences conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aada1-185">[<strong>電話会議セッションの合計数</strong>]</span><span class="sxs-lookup"><span data-stu-id="aada1-185"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="aada1-186">いいえ</span><span class="sxs-lookup"><span data-stu-id="aada1-186">No</span></span></p></td>
<td><p><span data-ttu-id="aada1-187">実施された電話会議セッションの総数です。</span><span class="sxs-lookup"><span data-stu-id="aada1-187">Total number of conferencing sessions conducted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aada1-188">[<strong>全体的なセッション エラー率</strong>]</span><span class="sxs-lookup"><span data-stu-id="aada1-188"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="aada1-189">いいえ</span><span class="sxs-lookup"><span data-stu-id="aada1-189">No</span></span></p></td>
<td><p><span data-ttu-id="aada1-190">エラーが発生した電話会議セッション総数の割合です。</span><span class="sxs-lookup"><span data-stu-id="aada1-190">Percentage of the total conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aada1-191">[<strong>フォーカス セッション</strong>]</span><span class="sxs-lookup"><span data-stu-id="aada1-191"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="aada1-192">いいえ</span><span class="sxs-lookup"><span data-stu-id="aada1-192">No</span></span></p></td>
<td><p><span data-ttu-id="aada1-193">エラーが発生したフォーカス ベース電話会議セッションの総数です。</span><span class="sxs-lookup"><span data-stu-id="aada1-193">Total number of Focus-based conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aada1-194">[<strong>フォーカス エラー率</strong>]</span><span class="sxs-lookup"><span data-stu-id="aada1-194"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="aada1-195">いいえ</span><span class="sxs-lookup"><span data-stu-id="aada1-195">No</span></span></p></td>
<td><p><span data-ttu-id="aada1-196">エラーが発生したフォーカス ベース電話会議セッションの割合です。</span><span class="sxs-lookup"><span data-stu-id="aada1-196">Percentage of the Focus-based conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aada1-197">[<strong>MCU セッション</strong>]</span><span class="sxs-lookup"><span data-stu-id="aada1-197"><strong>MCU sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="aada1-198">いいえ</span><span class="sxs-lookup"><span data-stu-id="aada1-198">No</span></span></p></td>
<td><p><span data-ttu-id="aada1-199">エラーが発生した、会議サーバー (以前の Multipoint Control Unit (MCU)) ベースの電話会議の総数です。</span><span class="sxs-lookup"><span data-stu-id="aada1-199">Total number of conferencing server-based (formerly known as Multipoint Control Unit or MCU) conferences that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aada1-200">[<strong>MCU エラー率</strong>]</span><span class="sxs-lookup"><span data-stu-id="aada1-200"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="aada1-201">いいえ</span><span class="sxs-lookup"><span data-stu-id="aada1-201">No</span></span></p></td>
<td><p><span data-ttu-id="aada1-202">エラーが発生した、会議サーバー (以前の Multipoint Control Unit (MCU)) ベースの電話会議の割合です。</span><span class="sxs-lookup"><span data-stu-id="aada1-202">Percentage of the conferencing server-based (formerly known as Multipoint Control Unit or MCU) conferences that failed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

