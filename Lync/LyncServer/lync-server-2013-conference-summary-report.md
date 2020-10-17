---
title: 'Lync Server 2013: 電話会議の概要レポート'
description: 'Lync Server 2013: 電話会議の概要レポート。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Summary Report
ms:assetid: 62f54812-5700-45a3-8526-8f58b0f77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558656(v=OCS.15)
ms:contentKeyID: 48184299
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d9c0b8ad7280d2c7336282c14f46e6b5d6a1aec
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550713"
---
# <a name="conference-summary-report-in-lync-server-2013"></a><span data-ttu-id="b9231-103">Lync Server 2013 の電話会議の概要レポート</span><span class="sxs-lookup"><span data-stu-id="b9231-103">Conference Summary Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9231-104">_**トピックの最終更新日:** 2014-09-03_</span><span class="sxs-lookup"><span data-stu-id="b9231-104">_**Topic Last Modified:** 2014-09-03_</span></span>

<span data-ttu-id="b9231-105">電話会議の概要レポートは、オンライン電話会議セッションの全体像を示します。</span><span class="sxs-lookup"><span data-stu-id="b9231-105">The Conference Summary Report provides an overall view of your online conferencing sessions.</span></span> <span data-ttu-id="b9231-106">通常、会議には2人以上のユーザーが関与しており、Microsoft Lync Server 2013 の電話会議サービスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9231-106">A conference typically involves more than 2 users and requires the use of Microsoft Lync Server 2013 conferencing services.</span></span> <span data-ttu-id="b9231-107">それに対し、ピアツーピアセッションには通常は 2 名のユーザーのみが関与し、Lync Server の電話会議サービスを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b9231-107">By comparison, a peer-to-peer session typically involves just 2 users and does not require the use of Lync Server's conferencing services.</span></span> <span data-ttu-id="b9231-108">ピアツーピアアクティビティは、 [Lync Server 2013 のピアツーピアアクティビティ概要レポート](lync-server-2013-peer-to-peer-activity-summary-report.md)で報告されます。</span><span class="sxs-lookup"><span data-stu-id="b9231-108">Peer-to-peer activities are reported on the [Peer-to-Peer Activity Summary Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md).</span></span>

<span data-ttu-id="b9231-109">電話会議の概要レポートでは、特定の期間 (時間、日、週、月) に開催された電話会議の数だけでなく、会議に参加したユーザーの総数と、一意の電話会議の開催者の合計数も通知されます。</span><span class="sxs-lookup"><span data-stu-id="b9231-109">The Conference Summary Report not only tells you how many conferences were held during a given time period (hourly, daily, weekly, monthly) but also tells you the total number of people who took part in those conferences, and the total number of unique conference organizers.</span></span>

<span data-ttu-id="b9231-p102">"一意の" 開催者とは、少なくとも 1 件の会議を予定したユーザーです。たとえば、Pilar Ackerman が 1 件の会議を予定した場合、彼女は 1 名の一意の開催者としてカウントされます。Ken Myer が 148 件の会議を予定した場合、彼も 1 名の一意の開催者としてカウントされます。たとえば 次の表では 8 件の会議が予定されていますが、一意の開催者は 3 名だけです (Ken Myer、Pilar Ackerman、および David Ahs)。</span><span class="sxs-lookup"><span data-stu-id="b9231-p102">A "unique” organizer is anyone who schedules at least one conference. For example, if Pilar Ackerman schedules one conference she counts as one unique organizer. If Ken Myer schedules 148 conferences he, too counts as one unique organizer. For example, the table below shows 8 conferences scheduled, but just three unique organizers (Ken Myer, Pilar Ackerman, and David Ahs).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b9231-114">会議の開催者</span><span class="sxs-lookup"><span data-stu-id="b9231-114">Conference Organizer</span></span></th>
<th><span data-ttu-id="b9231-115">会議の開催日時</span><span class="sxs-lookup"><span data-stu-id="b9231-115">Conference Date</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b9231-116">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="b9231-116">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="b9231-117">7/7/2012 10:00</span><span class="sxs-lookup"><span data-stu-id="b9231-117">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9231-118">David Ahs</span><span class="sxs-lookup"><span data-stu-id="b9231-118">David Ahs</span></span></p></td>
<td><p><span data-ttu-id="b9231-119">7/7/2012 10:00</span><span class="sxs-lookup"><span data-stu-id="b9231-119">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9231-120">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="b9231-120">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="b9231-121">7/7/2012 11:00</span><span class="sxs-lookup"><span data-stu-id="b9231-121">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9231-122">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="b9231-122">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="b9231-123">7/7/2012 11:00</span><span class="sxs-lookup"><span data-stu-id="b9231-123">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9231-124">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="b9231-124">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="b9231-125">7/7/2012 13:00</span><span class="sxs-lookup"><span data-stu-id="b9231-125">7/7/2012 1:00 PM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9231-126">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="b9231-126">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="b9231-127">7/7/2012 14:00</span><span class="sxs-lookup"><span data-stu-id="b9231-127">7/7/2012 2:00 PM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9231-128">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="b9231-128">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="b9231-129">7/2/2012 10:00</span><span class="sxs-lookup"><span data-stu-id="b9231-129">7/2/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9231-130">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="b9231-130">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="b9231-131">7/2/2012 10:00</span><span class="sxs-lookup"><span data-stu-id="b9231-131">7/2/2012 10:00 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b9231-132">電話会議の概要レポートは、音声/ビデオを利用した会議の数も示します。</span><span class="sxs-lookup"><span data-stu-id="b9231-132">The Conference Summary Report also indicates how many conferences included audio and/or video.</span></span>

<div>

## <a name="accessing-the-conference-summary-report"></a><span data-ttu-id="b9231-133">電話会議の概要レポートへのアクセス方法</span><span class="sxs-lookup"><span data-stu-id="b9231-133">Accessing the Conference Summary Report</span></span>

<span data-ttu-id="b9231-p103">電話会議の概要レポートには、[監視レポート] ホーム ページからアクセスします。次の指標のどちらかをクリックすることで、電話会議動作状況レポートにドリルダウンできます。</span><span class="sxs-lookup"><span data-stu-id="b9231-p103">The Conference Summary Report is accessed from the Monitoring Reports home page. You can drill down to the Conference Activity report by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="b9231-136">電話会議の合計数</span><span class="sxs-lookup"><span data-stu-id="b9231-136">Total conferences</span></span>

  - <span data-ttu-id="b9231-137">参加者の合計数</span><span class="sxs-lookup"><span data-stu-id="b9231-137">Total participants</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-summary-report"></a><span data-ttu-id="b9231-138">電話会議の概要レポートを最大限に活用する</span><span class="sxs-lookup"><span data-stu-id="b9231-138">Making the Best Use of the Conference Summary Report</span></span>

<span data-ttu-id="b9231-p104">電話会議の概要レポートで使用される指標の大半の合計値は、レポートの下部で確認できます。指定した期間中に開催された会議の総数やこれらの会議の参加者の総数などの値を確認するには、下方向にスクロールします。レポートの下部に合計が示されない指標の 1 つに一意の電話会議開催者の総数があります。なぜでしょうか。1 つの理由を示します。1 か月分のデータを見ていると仮定します。1 日目の一意の会議の開催者の数は 34 名でした。2 日目の一意の会議の開催者の数は 27 でした。これは、この 2 日間の一意の会議の開催者は 61 名であるという意味になるでしょうか。必ずしもそうではありません。2 日目に会議を開催した 27 名は、1 日目に会議を開催した 34 名に含まれる可能性があります。たとえば、次の単純なレポートでは、Ken Myer と Pilar Ackerman が 7/7/2012 と 7/2/2012 の両日、会議を予定しています。</span><span class="sxs-lookup"><span data-stu-id="b9231-p104">Total values for most of the metrics used on the Conference Summary Report can be found at the bottom of the report; scroll down to see values such as the total number of conferences held during the specified time period, and the total number of people who participated in those conferences. One metric that is not totaled at the bottom of the report is Total unique conference organizers. Why not? Here’s one reason. Suppose you are looking at a month's worth of data. On day 1 you had 34 unique conference organizers; on day 2 you had 27 unique conference organizers. Does that mean you had 61 unique conference organizers for those two days? Not necessarily. After all, all 27 people who organized conferences on day 2 might be among the 34 people who organized conferences on day 1. For example, in this simple report, note that Ken Myer and Pilar Ackerman scheduled conferences both on 7/7/2012 and on 7/2/2012:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b9231-149">会議の開催者</span><span class="sxs-lookup"><span data-stu-id="b9231-149">Conference Organizer</span></span></th>
<th><span data-ttu-id="b9231-150">会議の開催日時</span><span class="sxs-lookup"><span data-stu-id="b9231-150">Conference Date</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b9231-151">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="b9231-151">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="b9231-152">7/7/2012 10:00</span><span class="sxs-lookup"><span data-stu-id="b9231-152">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9231-153">David Ahs</span><span class="sxs-lookup"><span data-stu-id="b9231-153">David Ahs</span></span></p></td>
<td><p><span data-ttu-id="b9231-154">7/7/2012 10:00</span><span class="sxs-lookup"><span data-stu-id="b9231-154">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9231-155">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="b9231-155">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="b9231-156">7/7/2012 11:00</span><span class="sxs-lookup"><span data-stu-id="b9231-156">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9231-157">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="b9231-157">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="b9231-158">7/7/2012 11:00</span><span class="sxs-lookup"><span data-stu-id="b9231-158">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9231-159">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="b9231-159">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="b9231-160">7/7/2012 13:00</span><span class="sxs-lookup"><span data-stu-id="b9231-160">7/7/2012 1:00 PM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9231-161">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="b9231-161">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="b9231-162">7/7/2012 14:00</span><span class="sxs-lookup"><span data-stu-id="b9231-162">7/7/2012 2:00 PM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9231-163">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="b9231-163">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="b9231-164">7/2/2012 10:00</span><span class="sxs-lookup"><span data-stu-id="b9231-164">7/2/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9231-165">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="b9231-165">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="b9231-166">7/2/2012 10:00</span><span class="sxs-lookup"><span data-stu-id="b9231-166">7/2/2012 10:00 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b9231-167">会議を開催した一意のユーザーの総数を把握するには、期間を変更します。たとえば、日単位ではなく月単位でデータを調べます。</span><span class="sxs-lookup"><span data-stu-id="b9231-167">To get a better idea of the total number of unique users who organized conferences, change your time interval; for example, look at the data by month instead of by day.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="b9231-168">フィルター</span><span class="sxs-lookup"><span data-stu-id="b9231-168">Filters</span></span>

<span data-ttu-id="b9231-p105">フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざま方法で表示したりする方法として利用できます。たとえば、電話会議の概要レポートでは、データをグループ化する方法を選択できます。その場合は、電話会議が時間、日、週、または月の単位でグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="b9231-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Conference Summary Report enables you to choose how data should be grouped. In this case, conferences grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="b9231-172">次の表に、電話会議の概要レポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="b9231-172">The following table lists the filters that you can use with the Conference Summary Report.</span></span>

### <a name="conference-summary-report-filters"></a><span data-ttu-id="b9231-173">電話会議の概要レポートのフィルター</span><span class="sxs-lookup"><span data-stu-id="b9231-173">Conference Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b9231-174">名前</span><span class="sxs-lookup"><span data-stu-id="b9231-174">Name</span></span></th>
<th><span data-ttu-id="b9231-175">説明</span><span class="sxs-lookup"><span data-stu-id="b9231-175">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b9231-176"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="b9231-176"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="b9231-p106">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="b9231-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="b9231-179">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="b9231-179">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="b9231-p107">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="b9231-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="b9231-182">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="b9231-182">7/7/2012</span></span></p>
<p><span data-ttu-id="b9231-183">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="b9231-183">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="b9231-184">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="b9231-184">7/3/2012</span></span></p>
<p><span data-ttu-id="b9231-185">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="b9231-185">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9231-186"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="b9231-186"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="b9231-p108">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="b9231-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="b9231-189">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="b9231-189">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="b9231-p109">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="b9231-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="b9231-192">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="b9231-192">7/7/2012</span></span></p>
<p><span data-ttu-id="b9231-193">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="b9231-193">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="b9231-194">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="b9231-194">7/3/2012</span></span></p>
<p><span data-ttu-id="b9231-195">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="b9231-195">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9231-196"><strong>間隔</strong></span><span class="sxs-lookup"><span data-stu-id="b9231-196"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="b9231-p110">時間間隔です。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="b9231-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b9231-199">時間単位 (最大 25 時間の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="b9231-199">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="b9231-200">日単位 (最大 31 日の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="b9231-200">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="b9231-201">週単位 (最大 12 週の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="b9231-201">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="b9231-202">月単位 (最大 12 か月の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="b9231-202">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="b9231-p111">開始日と終了日が、選択されている期間内で許容される値の最大数を超えると、(開始日から起算した) 値の最大数のみが表示されます。たとえば、期間として [毎日] を選択し、開始日に 2012 年 8 月 7 日、終了日に 2012 年 9 月 28 日を選択した場合、2012 年 8 月 7 日 12:00 AM から 2012 年 9 月 7 日 12:00 AM までの日数分のデータ (合計 31 日分のデータ) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b9231-p111">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) are displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="b9231-205">指標</span><span class="sxs-lookup"><span data-stu-id="b9231-205">Metrics</span></span>

<span data-ttu-id="b9231-206">次の表に、電話会議の概要レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="b9231-206">The following table the information provided by the Conferences Summary Report.</span></span>

### <a name="conference-summary-report-metrics"></a><span data-ttu-id="b9231-207">電話会議の概要レポートの指標</span><span class="sxs-lookup"><span data-stu-id="b9231-207">Conference Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b9231-208">名前</span><span class="sxs-lookup"><span data-stu-id="b9231-208">Name</span></span></th>
<th><span data-ttu-id="b9231-209">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="b9231-209">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="b9231-210">説明</span><span class="sxs-lookup"><span data-stu-id="b9231-210">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b9231-211"><strong>毎時</strong></span><span class="sxs-lookup"><span data-stu-id="b9231-211"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="b9231-212"><strong>毎日</strong></span><span class="sxs-lookup"><span data-stu-id="b9231-212"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="b9231-213"><strong>毎週</strong></span><span class="sxs-lookup"><span data-stu-id="b9231-213"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="b9231-214"><strong>毎月</strong></span><span class="sxs-lookup"><span data-stu-id="b9231-214"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="b9231-215">いいえ</span><span class="sxs-lookup"><span data-stu-id="b9231-215">No</span></span></p></td>
<td><p><span data-ttu-id="b9231-p112">フィルター ツール バーで選択した期間を示します。場合によっては、特定の期間をクリックして、その期間の詳細情報を表示することもできます。たとえば、期間として [毎日] を使用している場合に、「2011 年 7 月 7 日」をクリックすると、その日に行われたユーザー登録アクティビティが時間ごとに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b9231-p112">Indicates the time interval that you selected on the filter toolbar. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9231-219">[<strong>電話会議の合計数</strong>]</span><span class="sxs-lookup"><span data-stu-id="b9231-219"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="b9231-220">いいえ</span><span class="sxs-lookup"><span data-stu-id="b9231-220">No</span></span></p></td>
<td><p><span data-ttu-id="b9231-p113">実施された電話会議の総数です (会議の種類は区別されません)。この項目をクリックすると、選択した期間に対する電話会議動作状況レポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b9231-p113">Total number of conferences (regardless of conference type) that were held. When you click this item, the report shows you the Conference Activity Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9231-223">[<strong>参加者の合計数</strong>]</span><span class="sxs-lookup"><span data-stu-id="b9231-223"><strong>Total participants</strong></span></span></p></td>
<td><p><span data-ttu-id="b9231-224">いいえ</span><span class="sxs-lookup"><span data-stu-id="b9231-224">No</span></span></p></td>
<td><p><span data-ttu-id="b9231-p114">電話会議に参加したユーザーの総数です。この項目をクリックすると、選択した期間に対する電話会議動作状況レポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b9231-p114">Total number of people who took part in the conferences. When you click this item, the report shows you the Conference Activity Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9231-227">[<strong>電話会議 1 件あたりの平均参加者数</strong>]</span><span class="sxs-lookup"><span data-stu-id="b9231-227"><strong>Average participants per conference</strong></span></span></p></td>
<td><p><span data-ttu-id="b9231-228">いいえ</span><span class="sxs-lookup"><span data-stu-id="b9231-228">No</span></span></p></td>
<td><p><span data-ttu-id="b9231-p115">1 件の電話会議に参加した平均ユーザー数です。電話会議の合計数を参加者の合計数で割ることで求められます。</span><span class="sxs-lookup"><span data-stu-id="b9231-p115">Average number of people who took part in a given conference. Determined by dividing the total conferences by the total participants.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9231-231">[<strong>音声ビデオ会議の合計数</strong>]</span><span class="sxs-lookup"><span data-stu-id="b9231-231"><strong>Total A/V conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="b9231-232">いいえ</span><span class="sxs-lookup"><span data-stu-id="b9231-232">No</span></span></p></td>
<td><p><span data-ttu-id="b9231-233">音声またはビデオを利用した会議の総数です。</span><span class="sxs-lookup"><span data-stu-id="b9231-233">Total number of conferences that included audio or video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9231-234">[<strong>音声ビデオ会議の合計時間 (分)</strong>]</span><span class="sxs-lookup"><span data-stu-id="b9231-234"><strong>Total A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="b9231-235">いいえ</span><span class="sxs-lookup"><span data-stu-id="b9231-235">No</span></span></p></td>
<td><p><span data-ttu-id="b9231-236">音声ビデオ会議に費やされた合計時間を分単位で表したものです。</span><span class="sxs-lookup"><span data-stu-id="b9231-236">Total number of minutes devoted to audio/video conferencing.</span></span></p>
<p><span data-ttu-id="b9231-237">音声ビデオ会議の合計時間 (分単位) は、音声ビデオ会議の種類 (音声ビデオ会議など) を要約したものです。IM 会議、アプリ共有会議。データ会議。および PSTN 会議。</span><span class="sxs-lookup"><span data-stu-id="b9231-237">The Total A/V conference minutes metric summarizes all the audio/visual conference types, including: A/V conferences; IM conferences; app sharing conferences; data conferences; and PSTN conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9231-238">[<strong>音声ビデオ会議参加者の合計時間 (分)</strong>]</span><span class="sxs-lookup"><span data-stu-id="b9231-238"><strong>Total A/V conference participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="b9231-239">いいえ</span><span class="sxs-lookup"><span data-stu-id="b9231-239">No</span></span></p></td>
<td><p><span data-ttu-id="b9231-p116">参加者が音声ビデオ会議に費やした合計時間を分単位で表したものです。たとえば、あるユーザーが音声ビデオ会議に 5 分費やし、別のユーザーが同じ会議に 3 分費やしたとします。この場合、会議参加者の合計時間は 8 分 (= 5 分 + 3 分) となります。</span><span class="sxs-lookup"><span data-stu-id="b9231-p116">Total number of participant minutes devoted to audio/video conferencing. For example, suppose one user spends 5 minutes in an audio/video conference and a second user spends 3 minutes in that same conference. That makes a total of 8 participant minutes: 5 minutes plus 3 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9231-243">[<strong>音声ビデオ会議の平均時間 (分)</strong>]</span><span class="sxs-lookup"><span data-stu-id="b9231-243"><strong>Average A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="b9231-244">いいえ</span><span class="sxs-lookup"><span data-stu-id="b9231-244">No</span></span></p></td>
<td><p><span data-ttu-id="b9231-245">音声ビデオ会議 1 件あたりの平均時間を分単位で表したものです。</span><span class="sxs-lookup"><span data-stu-id="b9231-245">Average number of minutes per audio/video conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9231-246">[<strong>電話会議の一意な開催者の合計数</strong>]</span><span class="sxs-lookup"><span data-stu-id="b9231-246"><strong>Total number of unique organizers of conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="b9231-247">いいえ</span><span class="sxs-lookup"><span data-stu-id="b9231-247">No</span></span></p></td>
<td><p><span data-ttu-id="b9231-p117">少なくとも 1 件の電話会議を開催したユーザーの総数です。複数の電話会議を開催したユーザーも、電話会議を 1 件しか開催していないユーザーと同じように、一意の開催者 1 人分としてカウントされます。</span><span class="sxs-lookup"><span data-stu-id="b9231-p117">Total number of users who organized at least one conference. Users who organized more than one conference are counted as one unique organizer, just like users who only organized a single conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9231-250">[<strong>電話会議メッセージの合計数</strong>]</span><span class="sxs-lookup"><span data-stu-id="b9231-250"><strong>Total conference messages</strong></span></span></p></td>
<td><p><span data-ttu-id="b9231-251">いいえ</span><span class="sxs-lookup"><span data-stu-id="b9231-251">No</span></span></p></td>
<td><p><span data-ttu-id="b9231-252">電話会議中に送信されたインスタント メッセージの総数です。</span><span class="sxs-lookup"><span data-stu-id="b9231-252">Total number of instant messages sent during the conferences.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

