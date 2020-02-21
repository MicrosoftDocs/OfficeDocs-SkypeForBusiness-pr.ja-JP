---
title: 'Lync Server 2013: ピアツーピア IM レポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer IM Report
ms:assetid: 19ec0145-2398-437b-8989-f780c179b798
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558620(v=OCS.15)
ms:contentKeyID: 48183533
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ddfd9bc59a42a8ab8cad77fa0c434adc1da02c27
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215743"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-im-report-in-lync-server-2013"></a><span data-ttu-id="172b7-102">Lync Server 2013 のピアツーピア IM レポート</span><span class="sxs-lookup"><span data-stu-id="172b7-102">Peer-to-Peer IM Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="172b7-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="172b7-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="172b7-p101">ピアツーピア IM レポートでは、ピアツーピア インスタント メッセージング (IM) セッションの傾向に関する情報が、プールおよび認証種類ごとに示されます。レポートでは、指定の時間内 (たとえば、日単位または時間単位) に行われたセッションの総数を表示したり、その時間内に送信されたインスタント メッセージの総数を表示したりできます。</span><span class="sxs-lookup"><span data-stu-id="172b7-p101">The Peer-to-Peer IM Report provides trend information about peer-to-peer instant messaging (IM) sessions, broken down by pool and by authentication type. The report can show either the total number of sessions held during the specified time period (for example, day-by-day or hour-by-hour), or it can show the total number of instant messages sent during that time period.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-im-report"></a><span data-ttu-id="172b7-106">ピアツーピア IM レポートへのアクセス</span><span class="sxs-lookup"><span data-stu-id="172b7-106">Accessing the Peer-to-Peer IM Report</span></span>

<span data-ttu-id="172b7-107">ピアツーピア IM レポートにアクセスするには、 [Lync Server 2013 でピアツーピアアクティビティ概要レポート](lync-server-2013-peer-to-peer-activity-summary-report.md)を開き、次のいずれかの指標をクリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="172b7-107">You can access the Peer-to-Peer IM Report only by opening the [Peer-to-Peer Activity Summary Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md) and then clicking either of the following metrics:</span></span>

  - <span data-ttu-id="172b7-108">ピアツーピア IM セッションの合計数</span><span class="sxs-lookup"><span data-stu-id="172b7-108">Total peer-to-peer IM sessions</span></span>

  - <span data-ttu-id="172b7-109">ピアツーピア IM メッセージの合計数</span><span class="sxs-lookup"><span data-stu-id="172b7-109">Total peer-to-peer IM messages</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-im-report"></a><span data-ttu-id="172b7-110">ピアツーピア IM レポートの利用</span><span class="sxs-lookup"><span data-stu-id="172b7-110">Making the Best Use of the Peer-to-Peer IM Report</span></span>

<span data-ttu-id="172b7-p102">既定では、ピアツーピア IM レポートには、1 時間 (または、設定によっては 1 日) あたりのメッセージ数が示されます。しかし、1 日を 1 時間当たりのセッション単位で表示することもできます。これを行うには、[レポート] ウィンドウの右上隅にある [**パラメーターの表示/非表示**] をクリックし、[**報告元**] の一覧で [**セッション数**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="172b7-p102">By default, the Peer-to-Peer IM Report shows you the message count per-hour (or day, depending on your settings). However, you can also choose to view the day by sessions per hour. To do that, click **Hide/Show Parameters** in the upper-right corner of the Reports window, and then click **Session Count** from the **Report by** list.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="172b7-114">フィルター</span><span class="sxs-lookup"><span data-stu-id="172b7-114">Filters</span></span>

<span data-ttu-id="172b7-p103">フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざま方法で表示したりする方法として利用できます。次の表に、ピアツーピア IM レポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="172b7-p103">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Peer-to-Peer IM Report.</span></span>

### <a name="peer-to-peer-im-report-filters"></a><span data-ttu-id="172b7-117">ピアツーピア IM レポートのフィルター</span><span class="sxs-lookup"><span data-stu-id="172b7-117">Peer-to-Peer IM Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="172b7-118">名前</span><span class="sxs-lookup"><span data-stu-id="172b7-118">Name</span></span></th>
<th><span data-ttu-id="172b7-119">説明</span><span class="sxs-lookup"><span data-stu-id="172b7-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="172b7-120"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="172b7-120"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="172b7-p104">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="172b7-p104">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="172b7-123">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="172b7-123">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="172b7-p105">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="172b7-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="172b7-126">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="172b7-126">7/7/2012</span></span></p>
<p><span data-ttu-id="172b7-127">週単位または月単位で表示するには、週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="172b7-127">To view by week or by month, enter a date that falls anywhere within the week or month (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="172b7-128">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="172b7-128">7/3/2012</span></span></p>
<p><span data-ttu-id="172b7-129">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="172b7-129">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="172b7-130"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="172b7-130"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="172b7-p106">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="172b7-p106">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="172b7-133">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="172b7-133">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="172b7-p107">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="172b7-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="172b7-136">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="172b7-136">7/7/2012</span></span></p>
<p><span data-ttu-id="172b7-137">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="172b7-137">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="172b7-138">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="172b7-138">7/3/2012</span></span></p>
<p><span data-ttu-id="172b7-139">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="172b7-139">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="172b7-140"><strong>間隔</strong></span><span class="sxs-lookup"><span data-stu-id="172b7-140"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="172b7-p108">時間間隔です。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="172b7-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="172b7-143">時間単位 (最大 25 時間の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="172b7-143">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="172b7-144">日単位 (最大 31 日の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="172b7-144">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="172b7-145">週単位 (最大 12 週の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="172b7-145">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="172b7-146">月単位 (最大 12 か月の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="172b7-146">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="172b7-p109">開始日と終了日が、選択されている期間内で許容される値の最大数を超えると、(開始日から起算した) 値の最大数のみが表示されます。たとえば、期間として [毎日] を選択し、開始日に 2012 年 7 月 7 日、終了日に 2012 年 2 月 28 日を選択した場合、2012 年 8 月 7 日 12:00 AM から 2012 年 9 月 7 日 12:00 AM までの日数分のデータ (合計 31 日分のデータ) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="172b7-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval then only the maximum number of values (starting from the start date) are displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="172b7-149">[<strong>報告元</strong>]</span><span class="sxs-lookup"><span data-stu-id="172b7-149"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="172b7-p110">レポートで使用する値を指定します。次の中から選択します。</span><span class="sxs-lookup"><span data-stu-id="172b7-p110">Indicates the values to be used in the report. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="172b7-152">セッション数</span><span class="sxs-lookup"><span data-stu-id="172b7-152">Session count</span></span></p></li>
<li><p><span data-ttu-id="172b7-153">メッセージ数</span><span class="sxs-lookup"><span data-stu-id="172b7-153">Message count</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-pool"></a><span data-ttu-id="172b7-154">ピアツーピア IM セッション (プール別) の指標</span><span class="sxs-lookup"><span data-stu-id="172b7-154">Metrics for Peer-to-Peer IM Session by Pool</span></span>

<span data-ttu-id="172b7-155">次の表に、ピアツーピア IM レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="172b7-155">The following table lists the information provided in the Peer-to-Peer IM Report.</span></span>

### <a name="metrics-for-peer-to-peer-im-session-by-pool"></a><span data-ttu-id="172b7-156">ピアツーピア IM セッション (プール別) の指標</span><span class="sxs-lookup"><span data-stu-id="172b7-156">Metrics for Peer-to-Peer IM Session by Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="172b7-157">名前</span><span class="sxs-lookup"><span data-stu-id="172b7-157">Name</span></span></th>
<th><span data-ttu-id="172b7-158">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="172b7-158">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="172b7-159">説明</span><span class="sxs-lookup"><span data-stu-id="172b7-159">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="172b7-160"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="172b7-160"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="172b7-161">いいえ</span><span class="sxs-lookup"><span data-stu-id="172b7-161">No</span></span></p></td>
<td><p><span data-ttu-id="172b7-162">レジストラープールまたはエッジサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="172b7-162">Name of the Registrar pool or Edge Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="172b7-163"><strong>日付/時刻</strong></span><span class="sxs-lookup"><span data-stu-id="172b7-163"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="172b7-164">いいえ</span><span class="sxs-lookup"><span data-stu-id="172b7-164">No</span></span></p></td>
<td><p><span data-ttu-id="172b7-165">セッションの発生日時。</span><span class="sxs-lookup"><span data-stu-id="172b7-165">Date and time that the sessions took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="172b7-166"><strong>合計</strong></span><span class="sxs-lookup"><span data-stu-id="172b7-166"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="172b7-167">いいえ</span><span class="sxs-lookup"><span data-stu-id="172b7-167">No</span></span></p></td>
<td><p><span data-ttu-id="172b7-168">セッション数またはメッセージ数の合計。</span><span class="sxs-lookup"><span data-stu-id="172b7-168">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a><span data-ttu-id="172b7-169">ピアツーピア IM セッション (認証の種類別) の指標</span><span class="sxs-lookup"><span data-stu-id="172b7-169">Metrics for Peer-to-Peer IM Session by Authentication Type</span></span>

<span data-ttu-id="172b7-170">次の表に、ピアツーピア セッションにおいて参加者によって使用される各認証の種類に対してピアツーピア IM レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="172b7-170">The following table lists the information provided in the Peer-to-Peer IM Report for each type of authentication used by the participants in a peer-to-peer session.</span></span>

### <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a><span data-ttu-id="172b7-171">ピアツーピア IM セッション (認証の種類別) の指標</span><span class="sxs-lookup"><span data-stu-id="172b7-171">Metrics for Peer-to-Peer IM Session by Authentication Type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="172b7-172">名前</span><span class="sxs-lookup"><span data-stu-id="172b7-172">Name</span></span></th>
<th><span data-ttu-id="172b7-173">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="172b7-173">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="172b7-174">説明</span><span class="sxs-lookup"><span data-stu-id="172b7-174">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="172b7-175">[<strong>認証の種類</strong>]</span><span class="sxs-lookup"><span data-stu-id="172b7-175"><strong>Authentication type</strong></span></span></p></td>
<td><p><span data-ttu-id="172b7-176">いいえ</span><span class="sxs-lookup"><span data-stu-id="172b7-176">No</span></span></p></td>
<td><p><span data-ttu-id="172b7-p111">セッション参加者によって使用される認証の種類。通常、値は次のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="172b7-p111">Type of authentication used by the session participants. Values are typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="172b7-179">大企業</span><span class="sxs-lookup"><span data-stu-id="172b7-179">Enterprise</span></span></p></li>
<li><p><span data-ttu-id="172b7-180">分散</span><span class="sxs-lookup"><span data-stu-id="172b7-180">Federated</span></span></p></li>
<li><p><span data-ttu-id="172b7-181">PIC</span><span class="sxs-lookup"><span data-stu-id="172b7-181">PIC</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="172b7-182"><strong>日付/時刻</strong></span><span class="sxs-lookup"><span data-stu-id="172b7-182"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="172b7-183">いいえ</span><span class="sxs-lookup"><span data-stu-id="172b7-183">No</span></span></p></td>
<td><p><span data-ttu-id="172b7-184">セッションの発生日時。</span><span class="sxs-lookup"><span data-stu-id="172b7-184">Date and time that the sessions took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="172b7-185"><strong>合計</strong></span><span class="sxs-lookup"><span data-stu-id="172b7-185"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="172b7-186">いいえ</span><span class="sxs-lookup"><span data-stu-id="172b7-186">No</span></span></p></td>
<td><p><span data-ttu-id="172b7-187">セッション数またはメッセージ数の合計。</span><span class="sxs-lookup"><span data-stu-id="172b7-187">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

