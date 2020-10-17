---
title: 'Lync Server 2013: 会議参加時間レポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Join Time Report
ms:assetid: e64dc89a-25e4-4cb8-bcb1-51712e69ba5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205344(v=OCS.15)
ms:contentKeyID: 48185686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fe20dd1e3e5387b4b31873ec0d3c6ae914c2cec
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526004"
---
# <a name="conference-join-time-report-in-lync-server-2013"></a><span data-ttu-id="ae444-102">Lync Server 2013 の会議参加時間レポート</span><span class="sxs-lookup"><span data-stu-id="ae444-102">Conference Join Time Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae444-103">_**トピックの最終更新日:** 2014-04-23_</span><span class="sxs-lookup"><span data-stu-id="ae444-103">_**Topic Last Modified:** 2014-04-23_</span></span>

<span data-ttu-id="ae444-p101">会議参加時間の概要を使用すると、ユーザーが会議に参加するのに要した時間を判定できます。このレポートは、平均参加時間 (ミリ秒) を表示します。また、2 秒以内に会議に参加できたユーザーの数や会議に参加するのに 2 ～ 5 秒かかったユーザーの数などが分かる詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="ae444-p101">The Conference Join Time Summary enables you to determine how long it takes your users to join a conference. The report shows the average join time (in milliseconds), and also provides a breakdown that lets you know how many users were able to join a conference in 2 seconds or less, how many users required between 2 and 5 seconds to join the conference, and so on.</span></span>

<div>

## <a name="accessing-the-conference-join-time-report"></a><span data-ttu-id="ae444-106">会議参加時間レポートにアクセスする</span><span class="sxs-lookup"><span data-stu-id="ae444-106">Accessing the Conference Join Time Report</span></span>

<span data-ttu-id="ae444-107">監視レポートのホーム ページから会議参加時間レポートにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ae444-107">The Conference Join Time Report is accessed from the Monitoring Reports home page.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="ae444-108">フィルター</span><span class="sxs-lookup"><span data-stu-id="ae444-108">Filters</span></span>

<span data-ttu-id="ae444-p102">フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざま方法で表示したりする方法として利用できます。次の表に、会議参加時間レポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="ae444-p102">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Join Time Report.</span></span>

### <a name="conference-join-time-report-filters"></a><span data-ttu-id="ae444-111">会議参加時間レポートのフィルター</span><span class="sxs-lookup"><span data-stu-id="ae444-111">Conference Join Time Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ae444-112">名前</span><span class="sxs-lookup"><span data-stu-id="ae444-112">Name</span></span></th>
<th><span data-ttu-id="ae444-113">説明</span><span class="sxs-lookup"><span data-stu-id="ae444-113">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ae444-114"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="ae444-114"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="ae444-p103">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="ae444-p103">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="ae444-117">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="ae444-117">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="ae444-p104">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="ae444-p104">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="ae444-120">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="ae444-120">7/7/2012</span></span></p>
<p><span data-ttu-id="ae444-121">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="ae444-121">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="ae444-122">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="ae444-122">7/3/2012</span></span></p>
<p><span data-ttu-id="ae444-123">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="ae444-123">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae444-124"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="ae444-124"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="ae444-p105">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="ae444-p105">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="ae444-127">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="ae444-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="ae444-p106">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="ae444-p106">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="ae444-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="ae444-130">7/7/2012</span></span></p>
<p><span data-ttu-id="ae444-131">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="ae444-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="ae444-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="ae444-132">7/3/2012</span></span></p>
<p><span data-ttu-id="ae444-133">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="ae444-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae444-134"><strong>間隔</strong></span><span class="sxs-lookup"><span data-stu-id="ae444-134"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="ae444-p107">時間間隔です。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="ae444-p107">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ae444-137">時間単位 (最大 25 時間の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="ae444-137">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="ae444-138">日単位 (最大 31 日の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="ae444-138">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="ae444-139">週単位 (最大 12 週の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="ae444-139">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="ae444-140">月単位 (最大 12 か月の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="ae444-140">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="ae444-p108">入力した開始日と終了日が選択した間隔で使用できる値の最大数を超える場合は、最大数の値 (開始日からカウント) のみが表示されます。たとえば、開始日と終了日をそれぞれ 7/7/2012 (2012 年 7 月 7 日)、2/28/2012 (2012 年 2 月 28 日) として毎日の間隔を選択しても、2012 年 8 月 7 日の午前 12:00 から 2012 年 9 月 7 日の午前 12:00 までの日付のデータ (つまり、合計 31 日分のデータのみ) が表示されることになります。</span><span class="sxs-lookup"><span data-stu-id="ae444-p108">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae444-143"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="ae444-143"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="ae444-p109">レジストラー プールまたはエッジ サーバーの完全修飾ドメイン名 (FQDN)。個別のプールを選択するか、[<strong>すべて</strong>] をクリックしてすべてのプールのデータを表示できます。このドロップダウン リストは、データベース内のレコードに基づいて自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="ae444-p109">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae444-147"><strong>会議セッション</strong></span><span class="sxs-lookup"><span data-stu-id="ae444-147"><strong>Conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="ae444-p110">セッションの種類。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ae444-p110">Type of session. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="ae444-150">[All]</span><span class="sxs-lookup"><span data-stu-id="ae444-150">[All]</span></span></p></li>
<li><p><span data-ttu-id="ae444-151">フォーカスセッション (フォーカスはオンライン会議の中心的なポリシーおよび状態マネージャーで、会議のすべての側面を調整します)</span><span class="sxs-lookup"><span data-stu-id="ae444-151">Focus sessions (the Focus is the central policy and state manager for online meetings and coordinates all aspects of A conference</span></span></p></li>
<li><p><span data-ttu-id="ae444-152">アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="ae444-152">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="ae444-153">音声ビデオ会議</span><span class="sxs-lookup"><span data-stu-id="ae444-153">A/V conferencing</span></span></p></li>
</ul>
<p><span data-ttu-id="ae444-p111">[すべて] を選択した場合は、会議参加時間の合計がレポートの上部に表示されます。これらの合計は、Microsoft Exchange または Microsoft Outlook を使用してスケジュールされた会議のみについての合計であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ae444-p111">If you select [All], the total conference join time will be displayed at the top of the report. Note that these totals are only for conferences which were scheduled by using Microsoft Exchange or Microsoft Outlook.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="ae444-156">指標</span><span class="sxs-lookup"><span data-stu-id="ae444-156">Metrics</span></span>

<span data-ttu-id="ae444-157">次の表に、会議参加時間レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="ae444-157">The following table lists the information provided in the Conference Join Time Report.</span></span>

### <a name="conference-join-time-report-metrics"></a><span data-ttu-id="ae444-158">会議参加時間レポートの指標</span><span class="sxs-lookup"><span data-stu-id="ae444-158">Conference Join Time Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ae444-159">名前</span><span class="sxs-lookup"><span data-stu-id="ae444-159">Name</span></span></th>
<th><span data-ttu-id="ae444-160">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="ae444-160">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="ae444-161">説明</span><span class="sxs-lookup"><span data-stu-id="ae444-161">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ae444-162"><strong>Date</strong></span><span class="sxs-lookup"><span data-stu-id="ae444-162"><strong>Date</strong></span></span></p>
<p><span data-ttu-id="ae444-163">この指標の実際の名前は、選択した間隔によって異なります。</span><span class="sxs-lookup"><span data-stu-id="ae444-163">The actual title for this metric will vary depending on the Interval that was selected.</span></span></p></td>
<td><p><span data-ttu-id="ae444-164">いいえ</span><span class="sxs-lookup"><span data-stu-id="ae444-164">No</span></span></p></td>
<td><p><span data-ttu-id="ae444-165">会議が開催された日時です。</span><span class="sxs-lookup"><span data-stu-id="ae444-165">Date and time that the conference took place.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae444-166"><strong>セッションの合計数</strong></span><span class="sxs-lookup"><span data-stu-id="ae444-166"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="ae444-167">いいえ</span><span class="sxs-lookup"><span data-stu-id="ae444-167">No</span></span></p></td>
<td><p><span data-ttu-id="ae444-168">セッションの総数です。成功したセッション、失敗したセッション (予期されるエラーと予期しないエラーの両方)、およびどちらにも分類されないセッションを含みます。</span><span class="sxs-lookup"><span data-stu-id="ae444-168">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae444-169"><strong>平均 (ミリ秒)</strong></span><span class="sxs-lookup"><span data-stu-id="ae444-169"><strong>Average (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="ae444-170">いいえ</span><span class="sxs-lookup"><span data-stu-id="ae444-170">No</span></span></p></td>
<td><p><span data-ttu-id="ae444-171">参加者が会議に参加するのに要した平均時間 (ミリ秒) です。</span><span class="sxs-lookup"><span data-stu-id="ae444-171">Average amount of time (in milliseconds) that it took participants to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae444-172"><strong>セッション &lt; 2 秒、ボリューム</strong></span><span class="sxs-lookup"><span data-stu-id="ae444-172"><strong>Sessions &lt; 2 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="ae444-173">いいえ</span><span class="sxs-lookup"><span data-stu-id="ae444-173">No</span></span></p></td>
<td><p><span data-ttu-id="ae444-174">2 秒未満で会議に参加できた参加者の数です。</span><span class="sxs-lookup"><span data-stu-id="ae444-174">Number of participants who were able to join the conference in less than 2 seconds.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae444-175"><strong>セッション &lt; 2 秒、パーセンテージ</strong></span><span class="sxs-lookup"><span data-stu-id="ae444-175"><strong>Sessions &lt; 2 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="ae444-176">いいえ</span><span class="sxs-lookup"><span data-stu-id="ae444-176">No</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae444-177"><strong>セッション 2 ～ 5 秒、数</strong></span><span class="sxs-lookup"><span data-stu-id="ae444-177"><strong>Sessions 2-5 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="ae444-178">いいえ</span><span class="sxs-lookup"><span data-stu-id="ae444-178">No</span></span></p></td>
<td><p><span data-ttu-id="ae444-179">2 ～ 5 秒で会議に参加できた参加者の数です。</span><span class="sxs-lookup"><span data-stu-id="ae444-179">Number of participants who took between 2 seconds and 5 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae444-180"><strong>セッション 2 ～ 5 秒、割合</strong></span><span class="sxs-lookup"><span data-stu-id="ae444-180"><strong>Sessions 2-5 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="ae444-181">いいえ</span><span class="sxs-lookup"><span data-stu-id="ae444-181">No</span></span></p></td>
<td><p><span data-ttu-id="ae444-182">2 ～ 5 秒で会議に参加できた参加者の合計の割合です。</span><span class="sxs-lookup"><span data-stu-id="ae444-182">Percentage of the total call participants who took between 2 seconds and 5 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae444-183"><strong>セッション 5 ～ 10 秒、数</strong></span><span class="sxs-lookup"><span data-stu-id="ae444-183"><strong>Sessions 5-10 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="ae444-184">いいえ</span><span class="sxs-lookup"><span data-stu-id="ae444-184">No</span></span></p></td>
<td><p><span data-ttu-id="ae444-185">5 ～ 10 秒で会議に参加できた参加者の数です。</span><span class="sxs-lookup"><span data-stu-id="ae444-185">Number of participants who took between 5 seconds and 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae444-186"><strong>セッション 5 ～ 10 秒、割合</strong></span><span class="sxs-lookup"><span data-stu-id="ae444-186"><strong>Sessions 5-10 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="ae444-187">いいえ</span><span class="sxs-lookup"><span data-stu-id="ae444-187">No</span></span></p></td>
<td><p><span data-ttu-id="ae444-188">5 ～ 10 秒で会議に参加できた参加者の合計の割合です。</span><span class="sxs-lookup"><span data-stu-id="ae444-188">Percentage of the total call participants who took between 5 seconds and 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae444-189"><strong>セッション &gt; 10 秒、ボリューム</strong></span><span class="sxs-lookup"><span data-stu-id="ae444-189"><strong>Sessions &gt; 10 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="ae444-190">いいえ</span><span class="sxs-lookup"><span data-stu-id="ae444-190">No</span></span></p></td>
<td><p><span data-ttu-id="ae444-191">会議に参加するのに 10 秒以上かかった参加者の数です。</span><span class="sxs-lookup"><span data-stu-id="ae444-191">Number of participants who required more than 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae444-192"><strong>セッション &gt; 10 秒、割合</strong></span><span class="sxs-lookup"><span data-stu-id="ae444-192"><strong>Sessions &gt; 10 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="ae444-193">いいえ</span><span class="sxs-lookup"><span data-stu-id="ae444-193">No</span></span></p></td>
<td><p><span data-ttu-id="ae444-194">会議に参加するのに 10 秒以上かかった参加者の合計の割合です。</span><span class="sxs-lookup"><span data-stu-id="ae444-194">Percentage of the total call participants who required more than 10 seconds to join the conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

