---
title: 'Lync Server 2013: ピアツーピア音声およびビデオレポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Voice and Video Report
ms:assetid: e17c36b5-5a2f-4673-9696-3b2d31c2bb2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615040(v=OCS.15)
ms:contentKeyID: 48185535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 974f403f65b494964affc4fbdc4880820ecb2db2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038659"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-voice-and-video-report-in-lync-server-2013"></a><span data-ttu-id="6dbb0-102">Lync Server 2013 のピアツーピア音声およびビデオレポート</span><span class="sxs-lookup"><span data-stu-id="6dbb0-102">Peer-to-Peer Voice and Video Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6dbb0-103">_**トピックの最終更新日:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="6dbb0-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="6dbb0-p101">ピアツーピア音声およびビデオ レポートは、指定した期間における音声通話やビデオ通話の配信に関する詳細を提供します (たとえば、1 時間あたりの通話回数または 1 日あたりの通話回数)。また、行われたすべての音声通話とビデオ通話を表示したり、正常な通話または失敗した通話のみを表示したりできます。レポートでは、次のグループに分割した通話情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6dbb0-p101">The Peer-to-Peer Voice and Video Report provides a detailed look at the distribution of voice and video calls over a specified period of time (for example, calls per hour or calls per day). The report also gives you the option of viewing all the voice and video calls that were made, or of viewing only the successful or failed calls. The reports shows call information broken down into the following groupings:</span></span>

  - <span data-ttu-id="6dbb0-107">プール別の通話</span><span class="sxs-lookup"><span data-stu-id="6dbb0-107">Calls per pool</span></span>

  - <span data-ttu-id="6dbb0-108">通話の種類ごとの通話 (たとえば、Lync から Lync への通話、および PSTN ネットワーク上の個人への Lync 通話)</span><span class="sxs-lookup"><span data-stu-id="6dbb0-108">Calls per call type (for example, a Lync to Lync call vs. a Lync call to a person on the PSTN network)</span></span>

  - <span data-ttu-id="6dbb0-109">アクセスの種類別の通話 (内部ネットワークにログオンしているユーザー、外部ネットワークにログオンしているユーザー)</span><span class="sxs-lookup"><span data-stu-id="6dbb0-109">Calls per access type (users logged on to the internal network vs. users logged on to the external network)</span></span>

  - <span data-ttu-id="6dbb0-110">仲介サーバーあたりの通話</span><span class="sxs-lookup"><span data-stu-id="6dbb0-110">Calls per Mediation Server</span></span>

<div>

## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="6dbb0-111">ピアツーピア音声およびビデオ レポートにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="6dbb0-111">To access the peer-to-peer voice and video report</span></span>

<span data-ttu-id="6dbb0-112">ピアツーピア アクティビティ概要レポートを開き、次のいずれかの指標をクリックすることによってのみ、ピアツーピア音声およびビデオ レポートにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6dbb0-112">You can access the Peer-to-Peer Voice and Video Report only by opening the Peer-to-Peer Activity Summary Report and then clicking any of the following metrics:</span></span>

  - <span data-ttu-id="6dbb0-113">ピアツーピア音声セッションの合計数</span><span class="sxs-lookup"><span data-stu-id="6dbb0-113">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="6dbb0-114">ピアツーピア音声セッションの合計時間</span><span class="sxs-lookup"><span data-stu-id="6dbb0-114">Total peer-to-peer audio minutes</span></span>

  - <span data-ttu-id="6dbb0-115">ピアツーピア ビデオ セッションの合計数</span><span class="sxs-lookup"><span data-stu-id="6dbb0-115">Total peer-to-peer video sessions</span></span>

  - <span data-ttu-id="6dbb0-116">ピアツーピア ビデオ セッションの合計時間</span><span class="sxs-lookup"><span data-stu-id="6dbb0-116">Total peer-to-peer video minutes</span></span>

</div>

<div>

## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="6dbb0-117">ピアツーピア音声およびビデオ レポートを最大限に活用するには</span><span class="sxs-lookup"><span data-stu-id="6dbb0-117">To make the best use of the peer-to-peer voice and video report</span></span>

<span data-ttu-id="6dbb0-p102">ピアツーピア音声およびビデオ レポートをフィルターするさまざまな方法があります。ただし、既定では、これらのフィルター オプションは非表示になっています。使用できるフィルター オプションを表示するには、[レポート] ウィンドウの右上隅にある [**パラメータの表示/非表示**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6dbb0-p102">There are a number of ways you can filter the Peer-to-Peer Voice and Video Report. However, those filtering options are hidden from view by default. To view the filtering options available to you, click **Show/Hide Parameters** button in the upper-right corner of the Report window.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="6dbb0-121">フィルター</span><span class="sxs-lookup"><span data-stu-id="6dbb0-121">Filters</span></span>

<span data-ttu-id="6dbb0-p103">フィルターは、細かく絞り込んだデータ セットを返したり、データをさまざま方法で表示したりする方法として利用できます。次の表に、ピアツーピア音声およびビデオ レポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="6dbb0-p103">Filters provide a way for you to return a more finely targeted set of data or to view the data in different ways. The following table lists the filters that you can use with the Peer-to-Peer Voice and Video Report.</span></span>

### <a name="peer-to-peer-voice-and-video-report-filters"></a><span data-ttu-id="6dbb0-124">ピアツーピア音声およびビデオ レポートのフィルター</span><span class="sxs-lookup"><span data-stu-id="6dbb0-124">Peer-to-peer voice and video report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6dbb0-125">名前</span><span class="sxs-lookup"><span data-stu-id="6dbb0-125">Name</span></span></th>
<th><span data-ttu-id="6dbb0-126">説明</span><span class="sxs-lookup"><span data-stu-id="6dbb0-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6dbb0-127"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="6dbb0-127"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="6dbb0-p104">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="6dbb0-p104">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="6dbb0-130">2012/7/7 13:00</span><span class="sxs-lookup"><span data-stu-id="6dbb0-130">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="6dbb0-p105">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="6dbb0-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="6dbb0-133">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="6dbb0-133">7/7/2012</span></span></p>
<p><span data-ttu-id="6dbb0-134">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="6dbb0-134">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="6dbb0-135">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="6dbb0-135">7/3/2012</span></span></p>
<p><span data-ttu-id="6dbb0-136">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="6dbb0-136">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6dbb0-137"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="6dbb0-137"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="6dbb0-p106">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="6dbb0-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="6dbb0-140">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="6dbb0-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="6dbb0-p107">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="6dbb0-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="6dbb0-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="6dbb0-143">7/7/2012</span></span></p>
<p><span data-ttu-id="6dbb0-144">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="6dbb0-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="6dbb0-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="6dbb0-145">7/3/2012</span></span></p>
<p><span data-ttu-id="6dbb0-146">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="6dbb0-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6dbb0-147"><strong>間隔</strong></span><span class="sxs-lookup"><span data-stu-id="6dbb0-147"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="6dbb0-p108">時間間隔です。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="6dbb0-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6dbb0-150">時間単位 (最大 25 時間の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="6dbb0-150">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="6dbb0-151">日単位 (最大 31 日の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="6dbb0-151">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="6dbb0-152">週単位 (最大 12 週の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="6dbb0-152">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="6dbb0-153">月単位 (最大 12 か月の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="6dbb0-153">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="6dbb0-p109">入力した開始日と終了日が選択した間隔で使用できる値の最大数を超える場合は、最大数の値 (開始日からカウント) のみが表示されます。たとえば、開始日と終了日をそれぞれ 7/7/2012 (2012 年 7 月 7 日)、2/28/2012 (2012 年 2 月 28 日) として毎日の間隔を選択しても、2012 年 8 月 7 日の午前 12:00 から 2012 年 9 月 7 日の午前 12:00 までの日付のデータ (つまり、合計 31 日分のデータのみ) が表示されることになります。</span><span class="sxs-lookup"><span data-stu-id="6dbb0-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6dbb0-156">[<strong>メディアの種類</strong>]</span><span class="sxs-lookup"><span data-stu-id="6dbb0-156"><strong>Media type</strong></span></span></p></td>
<td><p><span data-ttu-id="6dbb0-p110">セッションで使用されたメディアの種類を示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="6dbb0-p110">Indicates the type of media used in the session. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6dbb0-159">Both/フォーム/データシート</span><span class="sxs-lookup"><span data-stu-id="6dbb0-159">Both</span></span></p></li>
<li><p><span data-ttu-id="6dbb0-160">オーディオ</span><span class="sxs-lookup"><span data-stu-id="6dbb0-160">Audio</span></span></p></li>
<li><p><span data-ttu-id="6dbb0-161">ビデオ</span><span class="sxs-lookup"><span data-stu-id="6dbb0-161">Video</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6dbb0-162">[<strong>通話のディスポジション</strong>]</span><span class="sxs-lookup"><span data-stu-id="6dbb0-162"><strong>Call disposition</strong></span></span></p></td>
<td><p><span data-ttu-id="6dbb0-p111">セッションの成功または失敗を示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="6dbb0-p111">Indicates the success or failure of the session. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6dbb0-165">いずれ</span><span class="sxs-lookup"><span data-stu-id="6dbb0-165">[All]</span></span></p></li>
<li><p><span data-ttu-id="6dbb0-166">成功した通話</span><span class="sxs-lookup"><span data-stu-id="6dbb0-166">Success Calls</span></span></p></li>
<li><p><span data-ttu-id="6dbb0-167">失敗した通話</span><span class="sxs-lookup"><span data-stu-id="6dbb0-167">Failed Calls</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6dbb0-168">[<strong>報告元</strong>]</span><span class="sxs-lookup"><span data-stu-id="6dbb0-168"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="6dbb0-p112">レポートで使用する値を指定します。次の中から選択します。</span><span class="sxs-lookup"><span data-stu-id="6dbb0-p112">Indicates the values to be used in the report. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6dbb0-171">セッション数</span><span class="sxs-lookup"><span data-stu-id="6dbb0-171">Session count</span></span></p></li>
<li><p><span data-ttu-id="6dbb0-172">通話の分数</span><span class="sxs-lookup"><span data-stu-id="6dbb0-172">Call minutes</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="6dbb0-173">プール別のピアツーピア音声およびビデオ アクティビティの指標</span><span class="sxs-lookup"><span data-stu-id="6dbb0-173">Metrics for peer-to-peer voice and video activity by Pool</span></span>

<span data-ttu-id="6dbb0-174">次の表に、ピアツーピア音声およびビデオ レポートで各プールについて表示される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="6dbb0-174">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each pool.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="6dbb0-175">プール別のピアツーピア音声およびビデオ アクティビティの指標</span><span class="sxs-lookup"><span data-stu-id="6dbb0-175">Metrics for peer-to-peer voice and video activity by pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6dbb0-176">名前</span><span class="sxs-lookup"><span data-stu-id="6dbb0-176">Name</span></span></th>
<th><span data-ttu-id="6dbb0-177">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="6dbb0-177">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="6dbb0-178">説明</span><span class="sxs-lookup"><span data-stu-id="6dbb0-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6dbb0-179"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="6dbb0-179"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="6dbb0-180">いいえ</span><span class="sxs-lookup"><span data-stu-id="6dbb0-180">No</span></span></p></td>
<td><p><span data-ttu-id="6dbb0-181">呼び出しに使用されたレジストラープールまたはエッジサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="6dbb0-181">Name of the Registrar pool or Edge Server used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6dbb0-182"><strong>日付/時刻</strong></span><span class="sxs-lookup"><span data-stu-id="6dbb0-182"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="6dbb0-183">いいえ</span><span class="sxs-lookup"><span data-stu-id="6dbb0-183">No</span></span></p></td>
<td><p><span data-ttu-id="6dbb0-184">通話が行われた日付と時間。</span><span class="sxs-lookup"><span data-stu-id="6dbb0-184">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6dbb0-185"><strong>合計</strong></span><span class="sxs-lookup"><span data-stu-id="6dbb0-185"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="6dbb0-186">いいえ</span><span class="sxs-lookup"><span data-stu-id="6dbb0-186">No</span></span></p></td>
<td><p><span data-ttu-id="6dbb0-187">セッション数またはメッセージ数の合計。</span><span class="sxs-lookup"><span data-stu-id="6dbb0-187">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="6dbb0-188">通話の種類別のピアツーピア音声およびビデオ アクティビティの指標</span><span class="sxs-lookup"><span data-stu-id="6dbb0-188">Metrics for peer-to-peer voice and video activity by call type</span></span>

<span data-ttu-id="6dbb0-189">次の表に、ピアツーピア音声およびビデオ レポートで各種類の通話について表示される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="6dbb0-189">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each type of call that was made.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="6dbb0-190">通話の種類別のピアツーピア音声およびビデオ アクティビティの指標</span><span class="sxs-lookup"><span data-stu-id="6dbb0-190">Metrics for peer-to-peer voice and video activity by call type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6dbb0-191">名前</span><span class="sxs-lookup"><span data-stu-id="6dbb0-191">Name</span></span></th>
<th><span data-ttu-id="6dbb0-192">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="6dbb0-192">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="6dbb0-193">説明</span><span class="sxs-lookup"><span data-stu-id="6dbb0-193">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6dbb0-194">[<strong>通話の種類</strong>]</span><span class="sxs-lookup"><span data-stu-id="6dbb0-194"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="6dbb0-195">いいえ</span><span class="sxs-lookup"><span data-stu-id="6dbb0-195">No</span></span></p></td>
<td><p><span data-ttu-id="6dbb0-p113">行われた通話の種類を示します。値は次のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="6dbb0-p113">Indicates the type of call that was made. Values are one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6dbb0-198">Uc ツー UC</span><span class="sxs-lookup"><span data-stu-id="6dbb0-198">UC-to-UC</span></span></p></li>
<li><p><span data-ttu-id="6dbb0-199">UC ツー PSTN</span><span class="sxs-lookup"><span data-stu-id="6dbb0-199">UC-to-PSTN</span></span></p></li>
<li><p><span data-ttu-id="6dbb0-200">PSTN から UC</span><span class="sxs-lookup"><span data-stu-id="6dbb0-200">PSTN-to-UC</span></span></p></li>
<li><p><span data-ttu-id="6dbb0-201">PSTN ツー PSTN</span><span class="sxs-lookup"><span data-stu-id="6dbb0-201">PSTN-to-PSTN</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6dbb0-202"><strong>日付/時刻</strong></span><span class="sxs-lookup"><span data-stu-id="6dbb0-202"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="6dbb0-203">いいえ</span><span class="sxs-lookup"><span data-stu-id="6dbb0-203">No</span></span></p></td>
<td><p><span data-ttu-id="6dbb0-204">通話が行われた日付と時間。</span><span class="sxs-lookup"><span data-stu-id="6dbb0-204">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6dbb0-205"><strong>合計</strong></span><span class="sxs-lookup"><span data-stu-id="6dbb0-205"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="6dbb0-206">いいえ</span><span class="sxs-lookup"><span data-stu-id="6dbb0-206">No</span></span></p></td>
<td><p><span data-ttu-id="6dbb0-207">セッション数またはメッセージ数の合計。</span><span class="sxs-lookup"><span data-stu-id="6dbb0-207">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="6dbb0-208">アクセスの種類別のピアツーピア音声およびビデオ アクティビティの指標</span><span class="sxs-lookup"><span data-stu-id="6dbb0-208">Metrics for peer-to-peer voice and video activity by access type</span></span>

<span data-ttu-id="6dbb0-209">次の表に、ピアツーピア音声およびビデオ レポートで各種類のアクセスについて表示される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="6dbb0-209">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each network access type.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="6dbb0-210">アクセスの種類別のピアツーピア音声およびビデオ アクティビティの指標</span><span class="sxs-lookup"><span data-stu-id="6dbb0-210">Metrics for peer-to-peer voice and video activity by access type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6dbb0-211">名前</span><span class="sxs-lookup"><span data-stu-id="6dbb0-211">Name</span></span></th>
<th><span data-ttu-id="6dbb0-212">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="6dbb0-212">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="6dbb0-213">説明</span><span class="sxs-lookup"><span data-stu-id="6dbb0-213">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6dbb0-214">[<strong>動作状況の種類</strong>]</span><span class="sxs-lookup"><span data-stu-id="6dbb0-214"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="6dbb0-215">いいえ</span><span class="sxs-lookup"><span data-stu-id="6dbb0-215">No</span></span></p></td>
<td><p><span data-ttu-id="6dbb0-p114">クライアントが通話時に内部ネットワークにログオンしたか、外部ネットワークにログオンしたかを示します。通常は次のいずれかの値です。</span><span class="sxs-lookup"><span data-stu-id="6dbb0-p114">Indicates whether the clients were logged on to the internal network or the external network when the call was placed. Values are typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6dbb0-218">内部</span><span class="sxs-lookup"><span data-stu-id="6dbb0-218">Internal</span></span></p></li>
<li><p><span data-ttu-id="6dbb0-219">External</span><span class="sxs-lookup"><span data-stu-id="6dbb0-219">External</span></span></p></li>
<li><p><span data-ttu-id="6dbb0-220">混合</span><span class="sxs-lookup"><span data-stu-id="6dbb0-220">Mixed</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6dbb0-221"><strong>日付/時刻</strong></span><span class="sxs-lookup"><span data-stu-id="6dbb0-221"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="6dbb0-222">いいえ</span><span class="sxs-lookup"><span data-stu-id="6dbb0-222">No</span></span></p></td>
<td><p><span data-ttu-id="6dbb0-223">通話が行われた日付と時間。</span><span class="sxs-lookup"><span data-stu-id="6dbb0-223">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6dbb0-224"><strong>合計</strong></span><span class="sxs-lookup"><span data-stu-id="6dbb0-224"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="6dbb0-225">いいえ</span><span class="sxs-lookup"><span data-stu-id="6dbb0-225">No</span></span></p></td>
<td><p><span data-ttu-id="6dbb0-226">セッション数またはメッセージ数の合計。</span><span class="sxs-lookup"><span data-stu-id="6dbb0-226">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="6dbb0-227">仲介サーバー別のピアツーピア音声およびビデオ アクティビティの指標</span><span class="sxs-lookup"><span data-stu-id="6dbb0-227">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<span data-ttu-id="6dbb0-228">次の表に、ピアツーピア音声およびビデオレポートで仲介サーバーごとに提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="6dbb0-228">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each Mediation Server.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="6dbb0-229">仲介サーバー別のピアツーピア音声およびビデオ アクティビティの指標</span><span class="sxs-lookup"><span data-stu-id="6dbb0-229">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6dbb0-230">名前</span><span class="sxs-lookup"><span data-stu-id="6dbb0-230">Name</span></span></th>
<th><span data-ttu-id="6dbb0-231">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="6dbb0-231">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="6dbb0-232">説明</span><span class="sxs-lookup"><span data-stu-id="6dbb0-232">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6dbb0-233">[<strong>仲介サーバー</strong>]</span><span class="sxs-lookup"><span data-stu-id="6dbb0-233"><strong>Mediation Server</strong></span></span></p></td>
<td><p><span data-ttu-id="6dbb0-234">いいえ</span><span class="sxs-lookup"><span data-stu-id="6dbb0-234">No</span></span></p></td>
<td><p><span data-ttu-id="6dbb0-235">仲介サーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="6dbb0-235">Name of the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6dbb0-236"><strong>日付/時刻</strong></span><span class="sxs-lookup"><span data-stu-id="6dbb0-236"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="6dbb0-237">いいえ</span><span class="sxs-lookup"><span data-stu-id="6dbb0-237">No</span></span></p></td>
<td><p><span data-ttu-id="6dbb0-238">通話が行われた日付と時間。</span><span class="sxs-lookup"><span data-stu-id="6dbb0-238">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6dbb0-239"><strong>合計</strong></span><span class="sxs-lookup"><span data-stu-id="6dbb0-239"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="6dbb0-240">いいえ</span><span class="sxs-lookup"><span data-stu-id="6dbb0-240">No</span></span></p></td>
<td><p><span data-ttu-id="6dbb0-241">セッション数またはメッセージ数の合計。</span><span class="sxs-lookup"><span data-stu-id="6dbb0-241">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

