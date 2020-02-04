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
ms.openlocfilehash: 359c3fad7f41d990ffdba3aa533d0d5f10456665
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755307"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-im-report-in-lync-server-2013"></a><span data-ttu-id="390fe-102">Lync Server 2013 のピアツーピア IM レポート</span><span class="sxs-lookup"><span data-stu-id="390fe-102">Peer-to-Peer IM Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="390fe-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="390fe-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="390fe-p101">ピアツーピア IM レポートでは、ピアツーピア インスタント メッセージング (IM) セッションの傾向に関する情報が、プールおよび認証種類ごとに示されます。レポートでは、指定の時間内 (たとえば、日単位または時間単位) に行われたセッションの総数を表示したり、その時間内に送信されたインスタント メッセージの総数を表示したりできます。</span><span class="sxs-lookup"><span data-stu-id="390fe-p101">The Peer-to-Peer IM Report provides trend information about peer-to-peer instant messaging (IM) sessions, broken down by pool and by authentication type. The report can show either the total number of sessions held during the specified time period (for example, day-by-day or hour-by-hour), or it can show the total number of instant messages sent during that time period.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-im-report"></a><span data-ttu-id="390fe-106">ピアツーピア IM レポートへのアクセス</span><span class="sxs-lookup"><span data-stu-id="390fe-106">Accessing the Peer-to-Peer IM Report</span></span>

<span data-ttu-id="390fe-107">[ピアツーピアの IM] レポートにアクセスするには、 [Lync Server 2013 でピアツーピアアクティビティの概要レポート](lync-server-2013-peer-to-peer-activity-summary-report.md)を開いてから、次のいずれかの指標をクリックします。</span><span class="sxs-lookup"><span data-stu-id="390fe-107">You can access the Peer-to-Peer IM Report only by opening the [Peer-to-Peer Activity Summary Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md) and then clicking either of the following metrics:</span></span>

  - <span data-ttu-id="390fe-108">ピアツーピア IM セッションの合計数</span><span class="sxs-lookup"><span data-stu-id="390fe-108">Total peer-to-peer IM sessions</span></span>

  - <span data-ttu-id="390fe-109">ピアツーピア IM メッセージの合計数</span><span class="sxs-lookup"><span data-stu-id="390fe-109">Total peer-to-peer IM messages</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-im-report"></a><span data-ttu-id="390fe-110">ピアツーピア IM レポートの利用</span><span class="sxs-lookup"><span data-stu-id="390fe-110">Making the Best Use of the Peer-to-Peer IM Report</span></span>

<span data-ttu-id="390fe-p102">既定では、ピアツーピア IM レポートには、1 時間 (または、設定によっては 1 日) あたりのメッセージ数が示されます。ただし、1 日を時間単位のセッションで表示することもできます。この操作を行うには、[レポート] ウィンドウの右上隅にある [**パラメーターの表示/非表示**] をクリックし、[**報告元**] の一覧で [**セッション数**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="390fe-p102">By default, the Peer-to-Peer IM Report shows you the message count per-hour (or day, depending on your settings). However, you can also choose to view the day by sessions per hour. To do that, click **Hide/Show Parameters** in the upper-right corner of the Reports window, and then click **Session Count** from the **Report by** list.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="390fe-114">フィルター</span><span class="sxs-lookup"><span data-stu-id="390fe-114">Filters</span></span>

<span data-ttu-id="390fe-p103">フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざまな方法で表示したりする方法として利用できます。次の表に、ピアツーピア IM レポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="390fe-p103">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Peer-to-Peer IM Report.</span></span>

### <a name="peer-to-peer-im-report-filters"></a><span data-ttu-id="390fe-117">ピアツーピア IM レポートのフィルター</span><span class="sxs-lookup"><span data-stu-id="390fe-117">Peer-to-Peer IM Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="390fe-118">名前</span><span class="sxs-lookup"><span data-stu-id="390fe-118">Name</span></span></th>
<th><span data-ttu-id="390fe-119">説明</span><span class="sxs-lookup"><span data-stu-id="390fe-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="390fe-120"><strong>開始</strong></span><span class="sxs-lookup"><span data-stu-id="390fe-120"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="390fe-p104">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="390fe-p104">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="390fe-123">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="390fe-123">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="390fe-p105">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="390fe-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="390fe-126">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="390fe-126">7/7/2012</span></span></p>
<p><span data-ttu-id="390fe-127">週単位または月単位で表示するには、週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="390fe-127">To view by week or by month, enter a date that falls anywhere within the week or month (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="390fe-128">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="390fe-128">7/3/2012</span></span></p>
<p><span data-ttu-id="390fe-129">一週間は、日曜日から始まり、土曜日で終わるものとします。</span><span class="sxs-lookup"><span data-stu-id="390fe-129">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="390fe-130"><strong>終了</strong></span><span class="sxs-lookup"><span data-stu-id="390fe-130"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="390fe-p106">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="390fe-p106">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="390fe-133">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="390fe-133">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="390fe-p107">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="390fe-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="390fe-136">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="390fe-136">7/7/2012</span></span></p>
<p><span data-ttu-id="390fe-137">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="390fe-137">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="390fe-138">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="390fe-138">7/3/2012</span></span></p>
<p><span data-ttu-id="390fe-139">一週間は、日曜日から始まり、土曜日で終わるものとします。</span><span class="sxs-lookup"><span data-stu-id="390fe-139">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="390fe-140"><strong>[間隔]</strong></span><span class="sxs-lookup"><span data-stu-id="390fe-140"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="390fe-p108">時間間隔です。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="390fe-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="390fe-143">毎時 (最大 25 時間の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="390fe-143">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="390fe-144">毎日 (最大 31 日の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="390fe-144">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="390fe-145">毎週 (最大 12 週の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="390fe-145">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="390fe-146">毎月 (最大 12 か月の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="390fe-146">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="390fe-147">開始日と終了日が、選択されている期間内で許容される値の最大数を超えると、(開始日から起算した) 値の最大数のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="390fe-147">If the start and end dates exceed the maximum number of values allowed for the selected interval then only the maximum number of values (starting from the start date) are displayed.</span></span> <span data-ttu-id="390fe-148">たとえば、開始日が7/7/2012 で、終了日が2/28/2012 の [日] 間隔を選択した場合は、8/7/2012 12:00 AM から 9/7/2012 12:00 AM (つまり、31日分のデータ) のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="390fe-148">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="390fe-149"><strong>報告元</strong></span><span class="sxs-lookup"><span data-stu-id="390fe-149"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="390fe-p110">レポートで使用する値を指定します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="390fe-p110">Indicates the values to be used in the report. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="390fe-152">セッション数</span><span class="sxs-lookup"><span data-stu-id="390fe-152">Session count</span></span></p></li>
<li><p><span data-ttu-id="390fe-153">メッセージ数</span><span class="sxs-lookup"><span data-stu-id="390fe-153">Message count</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-pool"></a><span data-ttu-id="390fe-154">ピアツーピア IM セッション (プール別) の指標</span><span class="sxs-lookup"><span data-stu-id="390fe-154">Metrics for Peer-to-Peer IM Session by Pool</span></span>

<span data-ttu-id="390fe-155">次の表に、ピアツーピア IM レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="390fe-155">The following table lists the information provided in the Peer-to-Peer IM Report.</span></span>

### <a name="metrics-for-peer-to-peer-im-session-by-pool"></a><span data-ttu-id="390fe-156">ピアツーピア IM セッション (プール別) の指標</span><span class="sxs-lookup"><span data-stu-id="390fe-156">Metrics for Peer-to-Peer IM Session by Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="390fe-157">名前</span><span class="sxs-lookup"><span data-stu-id="390fe-157">Name</span></span></th>
<th><span data-ttu-id="390fe-158">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="390fe-158">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="390fe-159">説明</span><span class="sxs-lookup"><span data-stu-id="390fe-159">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="390fe-160"><strong>プール</strong></span><span class="sxs-lookup"><span data-stu-id="390fe-160"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="390fe-161">いいえ</span><span class="sxs-lookup"><span data-stu-id="390fe-161">No</span></span></p></td>
<td><p><span data-ttu-id="390fe-162">レジストラープールまたはエッジサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="390fe-162">Name of the Registrar pool or Edge Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="390fe-163"><strong>日付/時刻</strong></span><span class="sxs-lookup"><span data-stu-id="390fe-163"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="390fe-164">いいえ</span><span class="sxs-lookup"><span data-stu-id="390fe-164">No</span></span></p></td>
<td><p><span data-ttu-id="390fe-165">セッションの発生日時。</span><span class="sxs-lookup"><span data-stu-id="390fe-165">Date and time that the sessions took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="390fe-166"><strong>[合計]</strong></span><span class="sxs-lookup"><span data-stu-id="390fe-166"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="390fe-167">いいえ</span><span class="sxs-lookup"><span data-stu-id="390fe-167">No</span></span></p></td>
<td><p><span data-ttu-id="390fe-168">セッション数またはメッセージ数の合計。</span><span class="sxs-lookup"><span data-stu-id="390fe-168">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a><span data-ttu-id="390fe-169">ピアツーピア IM セッション (認証の種類別) の指標</span><span class="sxs-lookup"><span data-stu-id="390fe-169">Metrics for Peer-to-Peer IM Session by Authentication Type</span></span>

<span data-ttu-id="390fe-170">次の表に、ピアツーピア セッションにおいて参加者によって使用される各認証の種類に対してピアツーピア IM レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="390fe-170">The following table lists the information provided in the Peer-to-Peer IM Report for each type of authentication used by the participants in a peer-to-peer session.</span></span>

### <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a><span data-ttu-id="390fe-171">ピアツーピア IM セッション (認証の種類別) の指標</span><span class="sxs-lookup"><span data-stu-id="390fe-171">Metrics for Peer-to-Peer IM Session by Authentication Type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="390fe-172">名前</span><span class="sxs-lookup"><span data-stu-id="390fe-172">Name</span></span></th>
<th><span data-ttu-id="390fe-173">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="390fe-173">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="390fe-174">説明</span><span class="sxs-lookup"><span data-stu-id="390fe-174">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="390fe-175"><strong>[認証の種類]</strong></span><span class="sxs-lookup"><span data-stu-id="390fe-175"><strong>Authentication type</strong></span></span></p></td>
<td><p><span data-ttu-id="390fe-176">不可</span><span class="sxs-lookup"><span data-stu-id="390fe-176">No</span></span></p></td>
<td><p><span data-ttu-id="390fe-p111">セッション参加者によって使用される認証の種類。通常、値は次のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="390fe-p111">Type of authentication used by the session participants. Values are typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="390fe-179">Enterprise</span><span class="sxs-lookup"><span data-stu-id="390fe-179">Enterprise</span></span></p></li>
<li><p><span data-ttu-id="390fe-180">Federated</span><span class="sxs-lookup"><span data-stu-id="390fe-180">Federated</span></span></p></li>
<li><p><span data-ttu-id="390fe-181">PIC</span><span class="sxs-lookup"><span data-stu-id="390fe-181">PIC</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="390fe-182"><strong>[日付/時刻]</strong></span><span class="sxs-lookup"><span data-stu-id="390fe-182"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="390fe-183">いいえ</span><span class="sxs-lookup"><span data-stu-id="390fe-183">No</span></span></p></td>
<td><p><span data-ttu-id="390fe-184">セッションの発生日時。</span><span class="sxs-lookup"><span data-stu-id="390fe-184">Date and time that the sessions took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="390fe-185"><strong>[合計]</strong></span><span class="sxs-lookup"><span data-stu-id="390fe-185"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="390fe-186">いいえ</span><span class="sxs-lookup"><span data-stu-id="390fe-186">No</span></span></p></td>
<td><p><span data-ttu-id="390fe-187">セッション数またはメッセージ数の合計。</span><span class="sxs-lookup"><span data-stu-id="390fe-187">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

