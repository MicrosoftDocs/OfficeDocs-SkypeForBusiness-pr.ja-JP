---
title: 'Lync Server 2013: ピアツーピアアクティビティ診断レポート'
description: 'Lync Server 2013: ピアツーピアアクティビティ診断レポート。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Activity Diagnostic Report
ms:assetid: 025e8ab4-2e64-4a6b-8f52-caf756a5cac3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558602(v=OCS.15)
ms:contentKeyID: 48183242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80172c5e0f8b23bf05fad6ec300f0d1ffefb3327
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557353"
---
# <a name="peer-to-peer-activity-diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="42d23-103">Lync Server 2013 のピアツーピアアクティビティ診断レポート</span><span class="sxs-lookup"><span data-stu-id="42d23-103">Peer-to-Peer Activity Diagnostic Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42d23-104">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="42d23-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="42d23-105">ピアツーピア アクティビティ診断レポートは、ピアツーピア通信セッションの成功およびエラーに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="42d23-105">The Peer-to-Peer Activity Diagnostic Report provides information about the success and failure of your peer-to-peer communication sessions.</span></span> <span data-ttu-id="42d23-106">Microsoft Lync Server 2013 では、さまざまな種類の障害について区別されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="42d23-106">Note that Microsoft Lync Server 2013 distinguishes between different kinds of failure:</span></span>

  - <span data-ttu-id="42d23-107">**予期されたエラー**。</span><span class="sxs-lookup"><span data-stu-id="42d23-107">**Expected failure**.</span></span> <span data-ttu-id="42d23-108">予期されたエラーは通常、単に技術的な意味においてのエラーです。</span><span class="sxs-lookup"><span data-stu-id="42d23-108">An expected failure is typically a failure only in the most technical sense.</span></span> <span data-ttu-id="42d23-109">たとえば、だれかを呼び出すと、自分がオフィスの外にいて、電話に応答できないとします。</span><span class="sxs-lookup"><span data-stu-id="42d23-109">For example, suppose you call someone, but he or she is away from the office and is unable to answer the phone.</span></span> <span data-ttu-id="42d23-110">呼び出しが応答されなかったため、この呼び出しは技術的に失敗したと見なされます。</span><span class="sxs-lookup"><span data-stu-id="42d23-110">Because the call was not answered, the call is technically considered a failure.</span></span> <span data-ttu-id="42d23-111">一方、これは予期されたエラーです。電話に応答できない場合、Microsoft Lync Server 2013 は電話に応答することを期待していません。</span><span class="sxs-lookup"><span data-stu-id="42d23-111">On the other hand, this was an expected failure: Microsoft Lync Server 2013 does not expect you to answer the phone if you're not available to answer the phone.</span></span> <span data-ttu-id="42d23-112">同様に、オフラインのユーザーにインスタントメッセージを送信しようとした場合や、インスタントメッセージングをサポートしていない電話にのみログオンしている場合は、予期されるエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="42d23-112">Likewise, an expected failure will occur if you attempt to send an instant message to a user who is offline, or is logged on only to a phone that does not support instant messaging.</span></span>

  - <span data-ttu-id="42d23-113">**予期しないエラー**。</span><span class="sxs-lookup"><span data-stu-id="42d23-113">**Unexpected failure**.</span></span> <span data-ttu-id="42d23-114">予期しないエラーは名前が示すとおり、その状況下では発生が予期されないエラーです。</span><span class="sxs-lookup"><span data-stu-id="42d23-114">An unexpected error is exactly what the name implies: an error that, based on the circumstances, you would not expect to occur.</span></span> <span data-ttu-id="42d23-115">たとえば、ある人を呼び出すと、その人物が通話に応答できるとします。ただし、Lync Server 2013 が通話をボイスメールにルーティングしようとすると、Exchange ユニファイドメッセージングへの接続が失われたため、呼び出しが失敗します。</span><span class="sxs-lookup"><span data-stu-id="42d23-115">For example, suppose you call someone and that person is available to answer the call; however, when Lync Server 2013 tries to route your call to voicemail the call fails because connectivity to Exchange Unified Messaging has been lost.</span></span> <span data-ttu-id="42d23-116">これは予期しないエラーです。呼び出しは常にボイスメールにルーティングされる可能性があると考えられます。</span><span class="sxs-lookup"><span data-stu-id="42d23-116">That's an unexpected error: you would expect that calls could always be routed to voicemail.</span></span> <span data-ttu-id="42d23-117">一般的なルールとして、予期しないエラーが発生する場合があります。これは、ユーザー教育や同様の手段では解決できない問題です。</span><span class="sxs-lookup"><span data-stu-id="42d23-117">As a general rule, unexpected failures are true failures: they are problems that likely cannot be remedied through user education or similar measures.</span></span>

<span data-ttu-id="42d23-p104">成功、予期されたエラー、予期しないエラーの各指標の値を合計してもセッションの合計数の指標値に等しくならない場合があります。たとえば、先ほど説明した例では、次のような値が得られました。</span><span class="sxs-lookup"><span data-stu-id="42d23-p104">Note that the Success, Expected failure, and Unexpected failure metrics might not add up to the Total sessions metric. For example, in the preceding illustration, we have the following values:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="42d23-120">成功</span><span class="sxs-lookup"><span data-stu-id="42d23-120">Successes</span></span></th>
<th><span data-ttu-id="42d23-121">[Expected failures] (予期されたエラー数)</span><span class="sxs-lookup"><span data-stu-id="42d23-121">Expected failures</span></span></th>
<th><span data-ttu-id="42d23-122">[Unexpected failures] (予期しないエラー数)</span><span class="sxs-lookup"><span data-stu-id="42d23-122">Unexpected failures</span></span></th>
<th><span data-ttu-id="42d23-123">[セッションの合計数]</span><span class="sxs-lookup"><span data-stu-id="42d23-123">Total sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="42d23-124">2024</span><span class="sxs-lookup"><span data-stu-id="42d23-124">2024</span></span></p></td>
<td><p><span data-ttu-id="42d23-125">469</span><span class="sxs-lookup"><span data-stu-id="42d23-125">469</span></span></p></td>
<td><p><span data-ttu-id="42d23-126">16 </span><span class="sxs-lookup"><span data-stu-id="42d23-126">16</span></span></p></td>
<td><p><span data-ttu-id="42d23-127">2521</span><span class="sxs-lookup"><span data-stu-id="42d23-127">2521</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="42d23-128">2,024 + 469 + 16 を計算すると合計は 2,509 セッションになりますが、セッションの合計数の列には合計 2,521 セッションと示されています。</span><span class="sxs-lookup"><span data-stu-id="42d23-128">If you add 2024 + 469 + 16 you get a total of 2,509 sessions, yet the Total sessions column shows a total of 2,521 sessions.</span></span> <span data-ttu-id="42d23-129">"不足している" 12 セッションは、システムが成功にもエラーにも分類できなかったセッションです。</span><span class="sxs-lookup"><span data-stu-id="42d23-129">The "missing" 12 sessions are sessions that the system was unable to categorize as successful or unsuccessful.</span></span> <span data-ttu-id="42d23-130">サードパーティ製品が、Lync Server に不慣れな新しい診断コードを導入している場合は、このような場合があります。</span><span class="sxs-lookup"><span data-stu-id="42d23-130">That will sometimes be the case when a third-party product introduces a new diagnostic code that is unfamiliar to Lync Server.</span></span> <span data-ttu-id="42d23-131">この場合、その製品を使用して行われ、該当する診断コードを通知する通話は、必ずしも成功、予期されたエラー、または予期しないエラーのいずれかに分類されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="42d23-131">When that happens, calls made using that product, and reporting that diagnostic code, cannot always be categorized as being a Success, an Expected failure, or an Unexpected failure.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-activity-diagnostic-report"></a><span data-ttu-id="42d23-132">ピアツーピア アクティビティ診断レポートへのアクセス</span><span class="sxs-lookup"><span data-stu-id="42d23-132">Accessing the Peer-to-Peer Activity Diagnostic Report</span></span>

<span data-ttu-id="42d23-133">ピアツーピア診断レポートには、監視レポートのホーム ページからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="42d23-133">The Peer-to-Peer Diagnostic Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="42d23-134">次のいずれかの指標をクリックすると、 [Lync Server 2013 のエラー分布レポート](lync-server-2013-failure-distribution-report.md) にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="42d23-134">You can access the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="42d23-135">[予期しないエラー ボリューム]</span><span class="sxs-lookup"><span data-stu-id="42d23-135">Unexpected failure volume</span></span>

  - <span data-ttu-id="42d23-136">[予期されるエラー ボリューム]</span><span class="sxs-lookup"><span data-stu-id="42d23-136">Expected failure volume</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-diagnostic-report"></a><span data-ttu-id="42d23-137">ピアツーピア アクティビティ診断レポートの活用</span><span class="sxs-lookup"><span data-stu-id="42d23-137">Making the Best Use of the Peer-to-Peer Activity Diagnostic Report</span></span>

<span data-ttu-id="42d23-p107">ピアツーピア アクティビティ診断レポートをフィルターできる方法はいくつかありますが、既定ではそうしたフィルター処理オプションがビューに表示されません。フィルター処理オプションの表示を有効にするには、レポート ウィンドウの右上隅にある [パラメーターの表示/非表示] ボタンをクリックします。この操作により、フィルター処理オプションを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="42d23-p107">There are a number of ways you can filter the Peer-to-Peer Activity Diagnostic Report but, by default, those filtering options are hidden from view. To view the filtering options available to you, click the Show/Hide Parameters button in the upper right-hand corner of the report window. Once you do that the filtering options will be available for use.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="42d23-141">フィルター</span><span class="sxs-lookup"><span data-stu-id="42d23-141">Filters</span></span>

<span data-ttu-id="42d23-p108">フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざま方法で表示したりする方法として利用できます。たとえば、ピアツーピア アクティビティ診断レポートを使用すると、セッション モダリティ (インスタント メッセージング、ファイル送信、アプリケーション共有など) のようなものでフィルターできます。また、データをグループ化する方法を選択することもできます。この場合は、通話が、時間、日、週、または月を基準にグループ化されています。</span><span class="sxs-lookup"><span data-stu-id="42d23-p108">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Peer-to-Peer Activity Diagnostic Report enables you to filter on such things as the session modality (for example, instant messaging, file transfer, or application sharing). You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="42d23-146">次の表に、ピアツーピア アクティビティ診断レポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="42d23-146">The following table lists the filters that you can use with the Peer-to-Peer Activity Diagnostic Report.</span></span>

### <a name="peer-to-peer-activity-diagnostic-report-filters"></a><span data-ttu-id="42d23-147">ピアツーピア アクティビティ診断レポートのフィルター</span><span class="sxs-lookup"><span data-stu-id="42d23-147">Peer-to-Peer Activity Diagnostic Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="42d23-148">名前</span><span class="sxs-lookup"><span data-stu-id="42d23-148">Name</span></span></th>
<th><span data-ttu-id="42d23-149">説明</span><span class="sxs-lookup"><span data-stu-id="42d23-149">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="42d23-150"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="42d23-150"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="42d23-p109">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="42d23-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="42d23-153">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="42d23-153">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="42d23-p110">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="42d23-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="42d23-156">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="42d23-156">7/7/2012</span></span></p>
<p><span data-ttu-id="42d23-157">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="42d23-157">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="42d23-158">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="42d23-158">7/3/2012</span></span></p>
<p><span data-ttu-id="42d23-159">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="42d23-159">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42d23-160"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="42d23-160"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="42d23-p111">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="42d23-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="42d23-163">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="42d23-163">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="42d23-p112">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="42d23-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="42d23-166">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="42d23-166">7/7/2012</span></span></p>
<p><span data-ttu-id="42d23-167">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="42d23-167">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="42d23-168">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="42d23-168">7/3/2012</span></span></p>
<p><span data-ttu-id="42d23-169">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="42d23-169">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42d23-170"><strong>間隔</strong></span><span class="sxs-lookup"><span data-stu-id="42d23-170"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="42d23-p113">時間間隔です。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="42d23-p113">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="42d23-173">時間単位 (最大 25 時間の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="42d23-173">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="42d23-174">日単位 (最大 31 日の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="42d23-174">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="42d23-175">週単位 (最大 12 週の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="42d23-175">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="42d23-176">月単位 (最大 12 か月の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="42d23-176">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="42d23-p114">入力した開始日と終了日が選択した間隔で使用できる値の最大数を超える場合は、最大数の値 (開始日からカウント) のみが表示されます。たとえば、開始日と終了日をそれぞれ 7/7/2012 (2012 年 7 月 7 日)、2/28/2012 (2012 年 2 月 28 日) として毎日の間隔を選択しても、2012 年 8 月 7 日の午前 12:00 から 2012 年 9 月 7 日の午前 12:00 までの日付のデータ (つまり、合計 31 日分のデータのみ) が表示されることになります。</span><span class="sxs-lookup"><span data-stu-id="42d23-p114">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42d23-179"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="42d23-179"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="42d23-p115">レジストラー プールまたはエッジ サーバーの完全修飾ドメイン名 (FQDN)。個別のプールを選択するか、[<strong>すべて</strong>] をクリックしてすべてのプールのデータを表示できます。このドロップダウン リストは、データベース内のレコードに基づいて自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="42d23-p115">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42d23-183"><strong>モダリティ</strong></span><span class="sxs-lookup"><span data-stu-id="42d23-183"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="42d23-p116">お発生した通信アクティビティの種類を示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="42d23-p116">Indicates the type of communication activity that took place. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="42d23-186">[All]</span><span class="sxs-lookup"><span data-stu-id="42d23-186">[All]</span></span></p></li>
<li><p><span data-ttu-id="42d23-187">インスタント メッセージング</span><span class="sxs-lookup"><span data-stu-id="42d23-187">Instant messaging</span></span></p></li>
<li><p><span data-ttu-id="42d23-188">ファイル送信</span><span class="sxs-lookup"><span data-stu-id="42d23-188">File transfer</span></span></p></li>
<li><p><span data-ttu-id="42d23-189">アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="42d23-189">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="42d23-190">オーディオ</span><span class="sxs-lookup"><span data-stu-id="42d23-190">Audio</span></span></p></li>
<li><p><span data-ttu-id="42d23-191">ビデオ</span><span class="sxs-lookup"><span data-stu-id="42d23-191">Video</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-per-modality"></a><span data-ttu-id="42d23-192">指標 (モダリティ別)</span><span class="sxs-lookup"><span data-stu-id="42d23-192">Metrics (per modality)</span></span>

<span data-ttu-id="42d23-193">次の表に、各モダリティに対してピアツーピア アクティビティ診断レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="42d23-193">The following table lists the information provided in the Peer-to-Peer Activity Diagnostic Report for each modality.</span></span>

### <a name="metrics-per-modality"></a><span data-ttu-id="42d23-194">指標 (モダリティ別)</span><span class="sxs-lookup"><span data-stu-id="42d23-194">Metrics (per modality)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="42d23-195">名前</span><span class="sxs-lookup"><span data-stu-id="42d23-195">Name</span></span></th>
<th><span data-ttu-id="42d23-196">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="42d23-196">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="42d23-197">説明</span><span class="sxs-lookup"><span data-stu-id="42d23-197">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="42d23-198">[<strong>成功ボリューム</strong>]</span><span class="sxs-lookup"><span data-stu-id="42d23-198"><strong>Success volume</strong></span></span></p></td>
<td><p><span data-ttu-id="42d23-199">いいえ</span><span class="sxs-lookup"><span data-stu-id="42d23-199">No</span></span></p></td>
<td><p><span data-ttu-id="42d23-200">成功したピアツーピア セッションの総数です。</span><span class="sxs-lookup"><span data-stu-id="42d23-200">Total number of successful peer-to-peer sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42d23-201">[<strong>成功率</strong>]</span><span class="sxs-lookup"><span data-stu-id="42d23-201"><strong>Success percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="42d23-202">いいえ</span><span class="sxs-lookup"><span data-stu-id="42d23-202">No</span></span></p></td>
<td><p><span data-ttu-id="42d23-p117">重大な問題が発生して終了したピアツーピア セッションの割合です。[成功ボリューム] を [セッションの合計数] で割ることによって求められます。</span><span class="sxs-lookup"><span data-stu-id="42d23-p117">Percentage of peer-to-peer sessions that completed with significant problems. Calculated by dividing the Success volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42d23-205">[<strong>予期されるエラー ボリューム</strong>]</span><span class="sxs-lookup"><span data-stu-id="42d23-205"><strong>Expected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="42d23-206">いいえ</span><span class="sxs-lookup"><span data-stu-id="42d23-206">No</span></span></p></td>
<td><p><span data-ttu-id="42d23-207">&quot;予期されたエラーが発生したセッションの合計数 &quot; です。</span><span class="sxs-lookup"><span data-stu-id="42d23-207">Total number of sessions where an &quot;expected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="42d23-p118">予期されるエラーとは、発生が予想されるエラーです。たとえば、ステータスを "応答不可" に設定しているユーザーへの通話は、すべてエラーになることが予想されます。</span><span class="sxs-lookup"><span data-stu-id="42d23-p118">An expected failure is a failure that is expected to happen. For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42d23-210">[<strong>予期されるエラー率</strong>]</span><span class="sxs-lookup"><span data-stu-id="42d23-210"><strong>Expected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="42d23-211">いいえ</span><span class="sxs-lookup"><span data-stu-id="42d23-211">No</span></span></p></td>
<td><p><span data-ttu-id="42d23-p119">予期されるエラーが発生したピアツーピア セッションの割合です。[予期されるエラー ボリューム] を [セッションの合計数] で割ることによって求められます。</span><span class="sxs-lookup"><span data-stu-id="42d23-p119">Percentage of peer-to-peer sessions that experienced an expected error. Calculated by dividing the Expected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42d23-214">[<strong>予期しないエラー ボリューム</strong>]</span><span class="sxs-lookup"><span data-stu-id="42d23-214"><strong>Unexpected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="42d23-215">いいえ</span><span class="sxs-lookup"><span data-stu-id="42d23-215">No</span></span></p></td>
<td><p><span data-ttu-id="42d23-216">&quot;予期しないエラーが発生したセッションの合計数 &quot; です。</span><span class="sxs-lookup"><span data-stu-id="42d23-216">Total number of sessions where an &quot;unexpected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="42d23-p120">予期しないエラーとは、一見すると正常と思われるシステムで発生するエラーです。たとえば、呼び出し元が保留中になっている通話は終了してはなりません。この操作を行うと、予期しないエラーとしてフラグが設定されます。</span><span class="sxs-lookup"><span data-stu-id="42d23-p120">An unexpected failure is a failure that occurs in what would appear to be an otherwise healthy system. For example, a call should not be terminated if the caller is placed on hold. If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42d23-220">[<strong>予期しないエラー率</strong>]</span><span class="sxs-lookup"><span data-stu-id="42d23-220"><strong>Unexpected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="42d23-221">いいえ</span><span class="sxs-lookup"><span data-stu-id="42d23-221">No</span></span></p></td>
<td><p><span data-ttu-id="42d23-p121">予期しないエラーが発生したピアツーピア セッションの割合です。[予期しないエラー ボリューム] を [セッションの合計数] で割ることによって求められます。</span><span class="sxs-lookup"><span data-stu-id="42d23-p121">Percentage of peer-to-peer sessions that experienced an unexpected error. Calculated by dividing the Unexpected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42d23-224">[<strong>セッションの合計数</strong>]</span><span class="sxs-lookup"><span data-stu-id="42d23-224"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="42d23-225">いいえ</span><span class="sxs-lookup"><span data-stu-id="42d23-225">No</span></span></p></td>
<td><p><span data-ttu-id="42d23-226">セッションの総数です。成功したセッション、失敗したセッション (予期されるエラーと予期しないエラーの両方)、およびどちらにも分類されないセッションを含みます。</span><span class="sxs-lookup"><span data-stu-id="42d23-226">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

