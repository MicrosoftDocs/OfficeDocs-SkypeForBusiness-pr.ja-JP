---
title: 'Lync Server 2013: サーバーメディア品質傾向レポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server Media Quality Trend Report
ms:assetid: 8a51fd13-1487-4632-b5ec-f7ae2abe8ed4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205071(v=OCS.15)
ms:contentKeyID: 48184760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88c7a9f1fbadb69f00982f52dfae264d6a4ce60d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143995"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-media-quality-trend-report-in-lync-server-2013"></a><span data-ttu-id="ea77c-102">Lync Server 2013 のサーバーメディア品質傾向レポート</span><span class="sxs-lookup"><span data-stu-id="ea77c-102">Server Media Quality Trend Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea77c-103">_**トピックの最終更新日:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="ea77c-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="ea77c-p101">サーバー メディア品質傾向レポートを使用すると、通話件数、低品質通話のパーセンテージ、パケット損失、ジッターなどの QoE (Quality of Experience) 指標について、最大 5 台のサーバーを視覚的に比較できます。これにより、パフォーマンスが低下しているサーバー、過小使用されているサーバー、または過剰使用されているサーバーの特定などを簡単に行えます。</span><span class="sxs-lookup"><span data-stu-id="ea77c-p101">The Server Media Quality Trend Report provides a way for you to graphically compare up to 5 servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter. This makes it easier to do such things as identify servers that are performing poorly, identify servers that are underutilized, or identify servers that are being overused.</span></span>

<div>

## <a name="accessing-the-server-media-quality-trend-report"></a><span data-ttu-id="ea77c-106">サーバー メディア品質傾向レポートへのアクセス</span><span class="sxs-lookup"><span data-stu-id="ea77c-106">Accessing the Server Media Quality Trend Report</span></span>

<span data-ttu-id="ea77c-107">サーバー メディア品質傾向レポートには、次のいずれかのレポートからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ea77c-107">The Server Media Quality Trend Report can be accessed from either one of the following report:</span></span>

  - <span data-ttu-id="ea77c-108">[Lync server 2013 のサーバーパフォーマンスレポート](lync-server-2013-server-performance-report.md)(傾向指標をクリック)</span><span class="sxs-lookup"><span data-stu-id="ea77c-108">[Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking the Trend metric)</span></span>

  - <span data-ttu-id="ea77c-109">[Lync server 2013 の通話の詳細レポート](lync-server-2013-call-detail-report.md)(音声ビデオエッジサーバーの指標をクリックします)。</span><span class="sxs-lookup"><span data-stu-id="ea77c-109">[Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) (by clicking the A/V edge server metric.</span></span> <span data-ttu-id="ea77c-110">呼び出し元または呼び出し先がサーバーの場合は、エンドポイント名をクリックして、サーバー品質のメディア傾向レポートにアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="ea77c-110">If the caller or callee is a server, you can also reach the Server Quality Media Trend Report by clicking the endpoint name.)</span></span>

</div>

<div>

## <a name="making-the-best-use-of-server-media-quality-trend-report"></a><span data-ttu-id="ea77c-111">サーバー メディア品質傾向レポートを最大限に活用するには</span><span class="sxs-lookup"><span data-stu-id="ea77c-111">Making the Best Use of Server Media Quality Trend Report</span></span>

<span data-ttu-id="ea77c-112">特定のサーバーについて[Lync server 2013 のサーバーパフォーマンスレポート](lync-server-2013-server-performance-report.md)の傾向指標をクリックすると、サーバーメディア品質傾向レポートが開きます。</span><span class="sxs-lookup"><span data-stu-id="ea77c-112">When you click the Trend metric on the [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) for a specific server, the Server Media Quality Trend Report will open.</span></span> <span data-ttu-id="ea77c-113">ただし、そのレポートの空のインスタンスだけが表示されます。サーバーパフォーマンスレポートで選択したサーバーは、画面上に表示されません。</span><span class="sxs-lookup"><span data-stu-id="ea77c-113">However, you will see only a blank instance of that report; the server you selected on the Server Performance Report will not be displayed onscreen.</span></span> <span data-ttu-id="ea77c-114">代わりに、[サーバー] ドロップダウンからそのサーバーを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea77c-114">Instead, you will need to select that server from the Servers dropdown.</span></span> <span data-ttu-id="ea77c-115">また、サーバーのドロップダウンに [すべて選択] オプションが含まれていることにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="ea77c-115">Note, too that the Servers dropdown includes a Select All option.</span></span> <span data-ttu-id="ea77c-116">このオプションは、5台以上のサーバーがある場合は機能しません。サーバーメディア品質傾向レポートでは、一度に最大5台のサーバーのデータしか表示できません。</span><span class="sxs-lookup"><span data-stu-id="ea77c-116">This option will not work if you have more than 5 servers; the Server Media Quality Trend Report can only display data for a maximum of 5 servers at a time.</span></span>

<span data-ttu-id="ea77c-117">サーバーメディア品質傾向レポートで表示されるグラフでは、[通話ボリューム] と [低品質通話のパーセンテージ] というラベルが付いたポイントはホットリンクです。グラフ上のポイントをクリックすると、指定された期間の通話リストレポートのインスタンスが[Lync Server 2013 に](lync-server-2013-call-list-report.md)表示され、通話の合計 (または低品質) が示されます。</span><span class="sxs-lookup"><span data-stu-id="ea77c-117">On the graphs displayed by the Server Media Quality Trend Report, the points labeled Call Volume and Poor Call Percentage are hotlinks; clicking a point on the graph will open an instance of the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) showing the total calls (or poor calls) for the specified time period.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="ea77c-118">フィルター</span><span class="sxs-lookup"><span data-stu-id="ea77c-118">Filters</span></span>

<span data-ttu-id="ea77c-p104">フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざま方法で表示したりする方法として利用できます。次の表に、サーバー メディア品質傾向レポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="ea77c-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Server Media Quality Trend Report.</span></span>

### <a name="server-media-quality-trend-report-filters"></a><span data-ttu-id="ea77c-121">サーバー メディア品質傾向レポートのフィルター</span><span class="sxs-lookup"><span data-stu-id="ea77c-121">Server Media Quality Trend Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ea77c-122">名前</span><span class="sxs-lookup"><span data-stu-id="ea77c-122">Name</span></span></th>
<th><span data-ttu-id="ea77c-123">説明</span><span class="sxs-lookup"><span data-stu-id="ea77c-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea77c-124"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="ea77c-124"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="ea77c-p105">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="ea77c-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="ea77c-127">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="ea77c-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="ea77c-p106">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="ea77c-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="ea77c-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="ea77c-130">7/7/2012</span></span></p>
<p><span data-ttu-id="ea77c-131">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="ea77c-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="ea77c-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="ea77c-132">7/3/2012</span></span></p>
<p><span data-ttu-id="ea77c-133">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="ea77c-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea77c-134"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="ea77c-134"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="ea77c-p107">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="ea77c-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="ea77c-137">7/7/2012 13:00</span><span class="sxs-lookup"><span data-stu-id="ea77c-137">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="ea77c-p108">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="ea77c-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="ea77c-140">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="ea77c-140">7/7/2012</span></span></p>
<p><span data-ttu-id="ea77c-141">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="ea77c-141">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="ea77c-142">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="ea77c-142">7/3/2012</span></span></p>
<p><span data-ttu-id="ea77c-143">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="ea77c-143">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea77c-144"><strong>間隔</strong></span><span class="sxs-lookup"><span data-stu-id="ea77c-144"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="ea77c-p109">時間間隔です。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="ea77c-p109">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ea77c-147">時間単位 (最大 25 時間の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="ea77c-147">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="ea77c-148">日単位 (最大 31 日の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="ea77c-148">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="ea77c-149">週単位 (最大 12 週の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="ea77c-149">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="ea77c-p110">入力した開始日と終了日が選択した間隔で使用できる値の最大数を超える場合は、最大数の値 (開始日からカウント) のみが表示されます。たとえば、開始日と終了日をそれぞれ 8/7/2012 (2012 年 8 月 7 日)、9/28/2012 (2012 年 9 月 28 日) として毎日の間隔を選択しても、2012 年 8 月 7 日の午前 12:00 から 2012 年 9 月 7 日の午前 12:00 までの日付のデータ (つまり、合計 31 日分のデータのみ) が表示されることになります。</span><span class="sxs-lookup"><span data-stu-id="ea77c-p110">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 8/7/2012 and an end date of 9/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea77c-152">[<strong>サーバーの種類</strong>]</span><span class="sxs-lookup"><span data-stu-id="ea77c-152"><strong>Server type</strong></span></span></p></td>
<td><p><span data-ttu-id="ea77c-p111">通話に関係したサーバーの種類。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ea77c-p111">Type of server involved in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="ea77c-155">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="ea77c-155">Mediation Server</span></span></p></li>
<li><p><span data-ttu-id="ea77c-156">音声ビデオ会議サーバー</span><span class="sxs-lookup"><span data-stu-id="ea77c-156">A/V Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="ea77c-157">音声ビデオ エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="ea77c-157">A/V Edge Server</span></span></p></li>
<li><p><span data-ttu-id="ea77c-158">ゲートウェイ (仲介サーバー)</span><span class="sxs-lookup"><span data-stu-id="ea77c-158">Gateway (Mediation Server)</span></span></p></li>
<li><p><span data-ttu-id="ea77c-159">ゲートウェイ (仲介サーバーのバイパス)</span><span class="sxs-lookup"><span data-stu-id="ea77c-159">Gateway (Mediation Server Bypass)</span></span></p></li>
<li><p><span data-ttu-id="ea77c-160">AS 会議サーバー</span><span class="sxs-lookup"><span data-stu-id="ea77c-160">AS Conferencing Server</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea77c-161"><strong>サーバー</strong></span><span class="sxs-lookup"><span data-stu-id="ea77c-161"><strong>Servers</strong></span></span></p></td>
<td><p><span data-ttu-id="ea77c-p112">セッションに関連するサーバーの名前。このドロップダウン リストは、サーバーの種類フィルターの値に基づいて自動的に入力されます。レポートのコンパイル時に最大 5 台のサーバーを選択できます。</span><span class="sxs-lookup"><span data-stu-id="ea77c-p112">Name of the server involved in the session; this dropdown list is automatically populated for you based on the value of the Server type filter. You can select up to 5 different servers when compiling a report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea77c-164">[<strong>アクセスの種類</strong>]</span><span class="sxs-lookup"><span data-stu-id="ea77c-164"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="ea77c-p113">参加者が内部ネットワークにログオンしたか、外部ネットワークからログオンしたかを示します。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ea77c-p113">Indicates whether the participant was logged on to the internal network or from the external network. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="ea77c-167">いずれ</span><span class="sxs-lookup"><span data-stu-id="ea77c-167">[All]</span></span></p></li>
<li><p><span data-ttu-id="ea77c-168">内部</span><span class="sxs-lookup"><span data-stu-id="ea77c-168">Internal</span></span></p></li>
<li><p><span data-ttu-id="ea77c-169">External</span><span class="sxs-lookup"><span data-stu-id="ea77c-169">External</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea77c-170">[<strong>ネットワークの種類</strong>]</span><span class="sxs-lookup"><span data-stu-id="ea77c-170"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="ea77c-p114">通話時に参加者が接続したネットワークの種類を示します。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ea77c-p114">Indicates the type of network the participant was connected to. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="ea77c-173">いずれ</span><span class="sxs-lookup"><span data-stu-id="ea77c-173">[All]</span></span></p></li>
<li><p><span data-ttu-id="ea77c-174">有線</span><span class="sxs-lookup"><span data-stu-id="ea77c-174">Wired</span></span></p></li>
<li><p><span data-ttu-id="ea77c-175">通信</span><span class="sxs-lookup"><span data-stu-id="ea77c-175">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea77c-176"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="ea77c-176"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="ea77c-p115">通話中に外部参加者が仮想プライベート ネットワーク (VPN) 接続を使用したかどうかを示します。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ea77c-p115">Indicates whether an external participant was using a virtual private network (VPN) connection during the session. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="ea77c-179">いずれ</span><span class="sxs-lookup"><span data-stu-id="ea77c-179">[All]</span></span></p></li>
<li><p><span data-ttu-id="ea77c-180">VPN</span><span class="sxs-lookup"><span data-stu-id="ea77c-180">VPN</span></span></p></li>
<li><p><span data-ttu-id="ea77c-181">非 VPN</span><span class="sxs-lookup"><span data-stu-id="ea77c-181">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="ea77c-182">指標</span><span class="sxs-lookup"><span data-stu-id="ea77c-182">Metrics</span></span>

<span data-ttu-id="ea77c-183">次の表に、サーバー メディア品質傾向レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="ea77c-183">The following table lists the information provided in the Server Media Quality Trend Report.</span></span>

### <a name="server-media-quality-trend-report-metrics"></a><span data-ttu-id="ea77c-184">サーバー メディア品質傾向レポートの指標</span><span class="sxs-lookup"><span data-stu-id="ea77c-184">Server Media Quality Trend Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ea77c-185">名前</span><span class="sxs-lookup"><span data-stu-id="ea77c-185">Name</span></span></th>
<th><span data-ttu-id="ea77c-186">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="ea77c-186">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="ea77c-187">説明</span><span class="sxs-lookup"><span data-stu-id="ea77c-187">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea77c-188">[<strong>通話ボリューム</strong>]</span><span class="sxs-lookup"><span data-stu-id="ea77c-188"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="ea77c-189">いいえ</span><span class="sxs-lookup"><span data-stu-id="ea77c-189">No</span></span></p></td>
<td><p><span data-ttu-id="ea77c-190">通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="ea77c-190">Total number of calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea77c-191">[<strong>低下 (MOS)</strong>]</span><span class="sxs-lookup"><span data-stu-id="ea77c-191"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="ea77c-192">いいえ</span><span class="sxs-lookup"><span data-stu-id="ea77c-192">No</span></span></p></td>
<td><p><span data-ttu-id="ea77c-193">通話中に発生した MOS (平均オプションスコア) 低下の平均量。</span><span class="sxs-lookup"><span data-stu-id="ea77c-193">Average amount of MOS (mean option score) degradation experienced during a call.</span></span> <span data-ttu-id="ea77c-194">低下値は、0.0 の中から5.0 までの範囲で指定できます。値が0.5 以下の場合は、許容できる低下を表します。</span><span class="sxs-lookup"><span data-stu-id="ea77c-194">Degradation values can range from a low of 0.0 to a high of 5.0; a value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="ea77c-195">従来、平均オピニオン値は、ユーザーが通話の品質を 1 から 5 の範囲で評価することによって計算されていました。</span><span class="sxs-lookup"><span data-stu-id="ea77c-195">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="ea77c-196">Lync Server は、一連のアルゴリズムを使用して、ユーザーが通話を評価する方法を予測します。</span><span class="sxs-lookup"><span data-stu-id="ea77c-196">Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="ea77c-p117">この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーやエンドポイントの過負荷などの原因が考えられます。その結果、音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="ea77c-p117">High degradation values can be caused by congestion; lack of bandwidth; wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea77c-199">[<strong>低品質通話のパーセンテージ</strong>]</span><span class="sxs-lookup"><span data-stu-id="ea77c-199"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="ea77c-200">いいえ</span><span class="sxs-lookup"><span data-stu-id="ea77c-200">No</span></span></p></td>
<td><p><span data-ttu-id="ea77c-p118">低品質として分類される通話の総数。低品質通話とは、少なくとも 1 つの測定指標が許容値を超えている通話 (たとえば、過剰なジッターが発生した通話) のことです。</span><span class="sxs-lookup"><span data-stu-id="ea77c-p118">The total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea77c-203">[<strong>往復 (ミリ秒)</strong>]</span><span class="sxs-lookup"><span data-stu-id="ea77c-203"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="ea77c-204">いいえ</span><span class="sxs-lookup"><span data-stu-id="ea77c-204">No</span></span></p></td>
<td><p><span data-ttu-id="ea77c-p119">リアルタイム転送プロトコル パケットが、あるエンドポイントとの間を往復するのに要する平均時間 (ミリ秒単位)。200 ミリ秒以下の往復時間が許容できる品質と見なされます。</span><span class="sxs-lookup"><span data-stu-id="ea77c-p119">Average amount of time (in milliseconds) required for a Real-Time Transport Protocol packet to travel to one endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="ea77c-p120">この値が高い場合は、国際通話ルーティング、ルーティングの構成ミス、メディア サーバーの過負荷などの原因が考えられます。その結果、双方向のリアルタイムの音声会話が難しくなります。</span><span class="sxs-lookup"><span data-stu-id="ea77c-p120">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea77c-209">[<strong>パケット損失</strong>]</span><span class="sxs-lookup"><span data-stu-id="ea77c-209"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="ea77c-210">いいえ</span><span class="sxs-lookup"><span data-stu-id="ea77c-210">No</span></span></p></td>
<td><p><span data-ttu-id="ea77c-p121">リアルタイム転送プロトコル (RTP) パケット損失の平均レート (パケット損失は、RTP パケット、つまりインターネット経由で音声とビデオを転送するために使われるプロトコルの一種で、パケットが宛先に到達できなかったときに発生します)。この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーの過負荷などの原因が考えられます。パケット損失が発生すると、通常、音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="ea77c-p121">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea77c-214">[<strong>ジッター (ミリ秒)</strong>]</span><span class="sxs-lookup"><span data-stu-id="ea77c-214"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="ea77c-215">いいえ</span><span class="sxs-lookup"><span data-stu-id="ea77c-215">No</span></span></p></td>
<td><p><span data-ttu-id="ea77c-216">RTP パケットの着信間に検出された平均ジッター (ジッターとは、通話の "揺れ" の測定値です)。</span><span class="sxs-lookup"><span data-stu-id="ea77c-216">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="ea77c-217">(ジッターは、通話の&quot;過&quot;の測定値です)。高ジッター値は、通常、混雑または過負荷のメディアサーバーによって発生し、その結果、音声がひずむか失われます。</span><span class="sxs-lookup"><span data-stu-id="ea77c-217">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea77c-218">[<strong>ヒーラー隠し比率</strong>]</span><span class="sxs-lookup"><span data-stu-id="ea77c-218"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="ea77c-219">いいえ</span><span class="sxs-lookup"><span data-stu-id="ea77c-219">No</span></span></p></td>
<td><p><span data-ttu-id="ea77c-p123">サンプルの合計数に対する隠しオーディオ サンプルの平均比率 (隠しオーディオ サンプルとは、突然遷移を取り除くために使用される手法です。突然遷移は、通常、ネットワーク パケットの削除が原因で発生します)。この値が高い場合は、パケット損失やジッターのために高いレベルで損失の隠蔽が適用されています。その結果、音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="ea77c-p123">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea77c-222">[<strong>ヒーラー引き伸ばし比率</strong>]</span><span class="sxs-lookup"><span data-stu-id="ea77c-222"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="ea77c-223">いいえ</span><span class="sxs-lookup"><span data-stu-id="ea77c-223">No</span></span></p></td>
<td><p><span data-ttu-id="ea77c-p124">サンプルの合計数に対する引き伸ばされたオーディオ サンプルの平均比率 (引き伸ばされたオーディオとは、ネットワーク パケットの削除が検出されたときに通話の品質を維持できるように拡張されたオーディオのことです)。この値が高い場合は、ジッターのために高いレベルでサンプルの引き伸ばしが行われています。その結果、音声が機械のように聞こえたりひずんで聞こえたりします。</span><span class="sxs-lookup"><span data-stu-id="ea77c-p124">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea77c-226">[<strong>ヒーラー圧縮比率</strong>]</span><span class="sxs-lookup"><span data-stu-id="ea77c-226"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="ea77c-227">いいえ</span><span class="sxs-lookup"><span data-stu-id="ea77c-227">No</span></span></p></td>
<td><p><span data-ttu-id="ea77c-p125">サンプルの合計数に対する圧縮オーディオ サンプルの平均比率 (圧縮オーディオとは、ネットワーク パケットの削除が検出されたときに通話の品質を維持できるように圧縮されたオーディオのことです)。この値が高い場合は、ジッターのために高いレベルでサンプルの圧縮が行われています。その結果、音声が早送りされたように聞こえたりひずんで聞こえたりします。</span><span class="sxs-lookup"><span data-stu-id="ea77c-p125">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

