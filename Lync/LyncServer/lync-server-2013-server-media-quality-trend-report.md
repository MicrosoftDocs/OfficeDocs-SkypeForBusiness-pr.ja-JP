---
title: 'Lync Server 2013: サーバーのメディア品質トレンドレポート'
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
ms.openlocfilehash: c4efb7e2f29c1da75a81f4df4ec586c396d77d3d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732437"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-media-quality-trend-report-in-lync-server-2013"></a><span data-ttu-id="44e1f-102">Lync Server 2013 のサーバーメディア品質トレンドレポート</span><span class="sxs-lookup"><span data-stu-id="44e1f-102">Server Media Quality Trend Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44e1f-103">_**最終更新日:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="44e1f-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="44e1f-104">サーバーメディア品質トレンドレポートを使用すると、通話音量、低品質の通話率、パケット損失、ジッタなど、さまざまな品質のエクスペリエンスについて、最大5台のサーバーを視覚的に比較することができます。</span><span class="sxs-lookup"><span data-stu-id="44e1f-104">The Server Media Quality Trend Report provides a way for you to graphically compare up to 5 servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter.</span></span> <span data-ttu-id="44e1f-105">このため、パフォーマンスが低下しているサーバー、過小使用されているサーバー、または過剰使用されているサーバーの特定などを簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="44e1f-105">This makes it easier to do such things as identify servers that are performing poorly, identify servers that are underutilized, or identify servers that are being overused.</span></span>

<div>

## <a name="accessing-the-server-media-quality-trend-report"></a><span data-ttu-id="44e1f-106">サーバー メディア品質傾向レポートへのアクセス</span><span class="sxs-lookup"><span data-stu-id="44e1f-106">Accessing the Server Media Quality Trend Report</span></span>

<span data-ttu-id="44e1f-107">サーバー メディア品質傾向レポートには、次のいずれかのレポートからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="44e1f-107">The Server Media Quality Trend Report can be accessed from either one of the following report:</span></span>

  - <span data-ttu-id="44e1f-108">[Lync server 2013 のサーバーパフォーマンスレポート](lync-server-2013-server-performance-report.md)(トレンド指標をクリック)</span><span class="sxs-lookup"><span data-stu-id="44e1f-108">[Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking the Trend metric)</span></span>

  - <span data-ttu-id="44e1f-109">[Lync server 2013](lync-server-2013-call-detail-report.md)の [通話の詳細] レポート ([A/V edge サーバーメトリック] をクリックします)。</span><span class="sxs-lookup"><span data-stu-id="44e1f-109">[Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) (by clicking the A/V edge server metric.</span></span> <span data-ttu-id="44e1f-110">発信者または呼び出し先がサーバーである場合は、エンドポイント名をクリックすることによってもサーバー メディア品質傾向レポートにアクセスできます)。</span><span class="sxs-lookup"><span data-stu-id="44e1f-110">If the caller or callee is a server, you can also reach the Server Quality Media Trend Report by clicking the endpoint name.)</span></span>

</div>

<div>

## <a name="making-the-best-use-of-server-media-quality-trend-report"></a><span data-ttu-id="44e1f-111">サーバー メディア品質傾向レポートを最大限に活用するには</span><span class="sxs-lookup"><span data-stu-id="44e1f-111">Making the Best Use of Server Media Quality Trend Report</span></span>

<span data-ttu-id="44e1f-112">特定のサーバーの[Lync server 2013 でサーバーパフォーマンスレポート](lync-server-2013-server-performance-report.md)のトレンド指標をクリックすると、サーバーのメディア品質のトレンドレポートが開きます。</span><span class="sxs-lookup"><span data-stu-id="44e1f-112">When you click the Trend metric on the [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) for a specific server, the Server Media Quality Trend Report will open.</span></span> <span data-ttu-id="44e1f-113">ただし、そのレポートの空のインスタンスのみが表示されます。サーバーパフォーマンスレポートで選択したサーバーは画面に表示されません。</span><span class="sxs-lookup"><span data-stu-id="44e1f-113">However, you will see only a blank instance of that report; the server you selected on the Server Performance Report will not be displayed onscreen.</span></span> <span data-ttu-id="44e1f-114">代わりに、[サーバー] ドロップダウンからそのサーバーを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="44e1f-114">Instead, you will need to select that server from the Servers dropdown.</span></span> <span data-ttu-id="44e1f-115">サーバーのドロップダウンに [すべて選択] オプションが含まれていることにも注目してください。</span><span class="sxs-lookup"><span data-stu-id="44e1f-115">Note, too that the Servers dropdown includes a Select All option.</span></span> <span data-ttu-id="44e1f-116">このオプションは、サーバーの数が5台を超える場合は使用できません。サーバーメディア品質トレンドレポートでは、一度に最大5つのサーバーのデータを表示できます。</span><span class="sxs-lookup"><span data-stu-id="44e1f-116">This option will not work if you have more than 5 servers; the Server Media Quality Trend Report can only display data for a maximum of 5 servers at a time.</span></span>

<span data-ttu-id="44e1f-117">サーバーのメディア品質トレンドレポートによって表示されたグラフには、[通話音量] と [低品質通話の割合] というラベルの付いたホットリンクがあります。グラフ上のポイントをクリックすると、 [Lync Server 2013 で通話リストレポート](lync-server-2013-call-list-report.md)のインスタンスが開き、指定された期間の合計通話 (または通話が悪くありました) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="44e1f-117">On the graphs displayed by the Server Media Quality Trend Report, the points labeled Call Volume and Poor Call Percentage are hotlinks; clicking a point on the graph will open an instance of the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) showing the total calls (or poor calls) for the specified time period.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="44e1f-118">フィルター</span><span class="sxs-lookup"><span data-stu-id="44e1f-118">Filters</span></span>

<span data-ttu-id="44e1f-p104">フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざまな方法で表示したりする方法として利用できます。次の表に、サーバー メディア品質傾向レポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="44e1f-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Server Media Quality Trend Report.</span></span>

### <a name="server-media-quality-trend-report-filters"></a><span data-ttu-id="44e1f-121">サーバー メディア品質傾向レポートのフィルター</span><span class="sxs-lookup"><span data-stu-id="44e1f-121">Server Media Quality Trend Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="44e1f-122">名前</span><span class="sxs-lookup"><span data-stu-id="44e1f-122">Name</span></span></th>
<th><span data-ttu-id="44e1f-123">説明</span><span class="sxs-lookup"><span data-stu-id="44e1f-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="44e1f-124"><strong>開始</strong></span><span class="sxs-lookup"><span data-stu-id="44e1f-124"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="44e1f-p105">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="44e1f-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="44e1f-127">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="44e1f-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="44e1f-p106">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="44e1f-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="44e1f-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="44e1f-130">7/7/2012</span></span></p>
<p><span data-ttu-id="44e1f-131">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="44e1f-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="44e1f-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="44e1f-132">7/3/2012</span></span></p>
<p><span data-ttu-id="44e1f-133">一週間は、日曜日から始まり、土曜日で終わるものとします。</span><span class="sxs-lookup"><span data-stu-id="44e1f-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e1f-134"><strong>終了</strong></span><span class="sxs-lookup"><span data-stu-id="44e1f-134"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="44e1f-p107">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="44e1f-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="44e1f-137">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="44e1f-137">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="44e1f-p108">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="44e1f-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="44e1f-140">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="44e1f-140">7/7/2012</span></span></p>
<p><span data-ttu-id="44e1f-141">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="44e1f-141">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="44e1f-142">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="44e1f-142">7/3/2012</span></span></p>
<p><span data-ttu-id="44e1f-143">一週間は、日曜日から始まり、土曜日で終わるものとします。</span><span class="sxs-lookup"><span data-stu-id="44e1f-143">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e1f-144"><strong>[間隔]</strong></span><span class="sxs-lookup"><span data-stu-id="44e1f-144"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="44e1f-p109">時間間隔です。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="44e1f-p109">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="44e1f-147">毎時 (最大 25 時間の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="44e1f-147">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="44e1f-148">毎日 (最大 31 日の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="44e1f-148">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="44e1f-149">毎週 (最大 12 週の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="44e1f-149">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="44e1f-150">入力した開始日と終了日が選択した間隔で使用できる値の最大数を超える場合は、最大数の値 (開始日からカウント) のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="44e1f-150">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="44e1f-151">たとえば、開始日が8/7/2012 で、終了日が9/28/2012 の [日] 間隔を選択した場合は、8/7/2012 12:00 AM から 9/7/2012 12:00 AM (つまり、31日分のデータ) のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="44e1f-151">For example, if you select the Daily interval with a start date of 8/7/2012 and an end date of 9/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e1f-152"><strong>[サーバーの種類]</strong></span><span class="sxs-lookup"><span data-stu-id="44e1f-152"><strong>Server type</strong></span></span></p></td>
<td><p><span data-ttu-id="44e1f-p111">通話に関係したサーバーの種類。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="44e1f-p111">Type of server involved in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="44e1f-155">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="44e1f-155">Mediation Server</span></span></p></li>
<li><p><span data-ttu-id="44e1f-156">音声ビデオ会議サーバー</span><span class="sxs-lookup"><span data-stu-id="44e1f-156">A/V Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="44e1f-157">音声ビデオ エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="44e1f-157">A/V Edge Server</span></span></p></li>
<li><p><span data-ttu-id="44e1f-158">ゲートウェイ (仲介サーバー)</span><span class="sxs-lookup"><span data-stu-id="44e1f-158">Gateway (Mediation Server)</span></span></p></li>
<li><p><span data-ttu-id="44e1f-159">ゲートウェイ (仲介サーバーのバイパス)</span><span class="sxs-lookup"><span data-stu-id="44e1f-159">Gateway (Mediation Server Bypass)</span></span></p></li>
<li><p><span data-ttu-id="44e1f-160">AS 会議サーバー</span><span class="sxs-lookup"><span data-stu-id="44e1f-160">AS Conferencing Server</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e1f-161"><strong>[サーバー]</strong></span><span class="sxs-lookup"><span data-stu-id="44e1f-161"><strong>Servers</strong></span></span></p></td>
<td><p><span data-ttu-id="44e1f-p112">セッションに関連するサーバーの名前。このドロップダウン リストは、サーバーの種類フィルターの値に基づいて自動的に入力されます。レポートのコンパイル時に最大 5 台のサーバーを選択できます。</span><span class="sxs-lookup"><span data-stu-id="44e1f-p112">Name of the server involved in the session; this dropdown list is automatically populated for you based on the value of the Server type filter. You can select up to 5 different servers when compiling a report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e1f-164"><strong>[アクセスの種類]</strong></span><span class="sxs-lookup"><span data-stu-id="44e1f-164"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="44e1f-p113">参加者が内部ネットワークにログオンしたか、外部ネットワークからログオンしたかを示します。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="44e1f-p113">Indicates whether the participant was logged on to the internal network or from the external network. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="44e1f-167">[すべて]</span><span class="sxs-lookup"><span data-stu-id="44e1f-167">[All]</span></span></p></li>
<li><p><span data-ttu-id="44e1f-168">内部</span><span class="sxs-lookup"><span data-stu-id="44e1f-168">Internal</span></span></p></li>
<li><p><span data-ttu-id="44e1f-169">外部</span><span class="sxs-lookup"><span data-stu-id="44e1f-169">External</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e1f-170"><strong>[ネットワークの種類]</strong></span><span class="sxs-lookup"><span data-stu-id="44e1f-170"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="44e1f-p114">通話時に参加者が接続したネットワークの種類を示します。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="44e1f-p114">Indicates the type of network the participant was connected to. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="44e1f-173">[すべて]</span><span class="sxs-lookup"><span data-stu-id="44e1f-173">[All]</span></span></p></li>
<li><p><span data-ttu-id="44e1f-174">有線</span><span class="sxs-lookup"><span data-stu-id="44e1f-174">Wired</span></span></p></li>
<li><p><span data-ttu-id="44e1f-175">ワイヤレス</span><span class="sxs-lookup"><span data-stu-id="44e1f-175">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e1f-176"><strong>[VPN]</strong></span><span class="sxs-lookup"><span data-stu-id="44e1f-176"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="44e1f-p115">通話中に外部参加者が仮想プライベート ネットワーク (VPN) 接続を使用したかどうかを示します。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="44e1f-p115">Indicates whether an external participant was using a virtual private network (VPN) connection during the session. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="44e1f-179">[すべて]</span><span class="sxs-lookup"><span data-stu-id="44e1f-179">[All]</span></span></p></li>
<li><p><span data-ttu-id="44e1f-180">VPN</span><span class="sxs-lookup"><span data-stu-id="44e1f-180">VPN</span></span></p></li>
<li><p><span data-ttu-id="44e1f-181">非 VPN</span><span class="sxs-lookup"><span data-stu-id="44e1f-181">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="44e1f-182">指標</span><span class="sxs-lookup"><span data-stu-id="44e1f-182">Metrics</span></span>

<span data-ttu-id="44e1f-183">次の表に、サーバー メディア品質傾向レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="44e1f-183">The following table lists the information provided in the Server Media Quality Trend Report.</span></span>

### <a name="server-media-quality-trend-report-metrics"></a><span data-ttu-id="44e1f-184">サーバー メディア品質傾向レポートの指標</span><span class="sxs-lookup"><span data-stu-id="44e1f-184">Server Media Quality Trend Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="44e1f-185">名前</span><span class="sxs-lookup"><span data-stu-id="44e1f-185">Name</span></span></th>
<th><span data-ttu-id="44e1f-186">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="44e1f-186">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="44e1f-187">説明</span><span class="sxs-lookup"><span data-stu-id="44e1f-187">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="44e1f-188"><strong>通話ボリューム</strong></span><span class="sxs-lookup"><span data-stu-id="44e1f-188"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="44e1f-189">いいえ</span><span class="sxs-lookup"><span data-stu-id="44e1f-189">No</span></span></p></td>
<td><p><span data-ttu-id="44e1f-190">通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="44e1f-190">Total number of calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e1f-191"><strong>低下 (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="44e1f-191"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="44e1f-192">不可</span><span class="sxs-lookup"><span data-stu-id="44e1f-192">No</span></span></p></td>
<td><p><span data-ttu-id="44e1f-193">通話中に発生した平均 MOS (平均オプションスコア) の低下。</span><span class="sxs-lookup"><span data-stu-id="44e1f-193">Average amount of MOS (mean option score) degradation experienced during a call.</span></span> <span data-ttu-id="44e1f-194">値の劣化は、0.0 の低いものから5.0 までの範囲になります。値が0.5 以下の場合は、許容できる劣化率が示されます。</span><span class="sxs-lookup"><span data-stu-id="44e1f-194">Degradation values can range from a low of 0.0 to a high of 5.0; a value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="44e1f-195">従来、平均オピニオン値は、ユーザーが通話の品質を 1 から 5 の範囲で評価することによって計算されていました。</span><span class="sxs-lookup"><span data-stu-id="44e1f-195">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="44e1f-196">Lync Server は、一連のアルゴリズムを使って、ユーザーがどのように通話を評価したかを予測します。</span><span class="sxs-lookup"><span data-stu-id="44e1f-196">Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="44e1f-p117">この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーやエンドポイントの過負荷などの原因が考えられます。その結果、音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="44e1f-p117">High degradation values can be caused by congestion; lack of bandwidth; wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e1f-199"><strong>低品質通話のパーセンテージ</strong></span><span class="sxs-lookup"><span data-stu-id="44e1f-199"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="44e1f-200">いいえ</span><span class="sxs-lookup"><span data-stu-id="44e1f-200">No</span></span></p></td>
<td><p><span data-ttu-id="44e1f-p118">低品質として分類される通話の総数。低品質通話とは、少なくとも 1 つの測定指標が許容値を超えている通話 (たとえば、過剰なジッターが発生した通話) のことです。</span><span class="sxs-lookup"><span data-stu-id="44e1f-p118">The total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e1f-203"><strong>往復 (ミリ秒)</strong></span><span class="sxs-lookup"><span data-stu-id="44e1f-203"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="44e1f-204">いいえ</span><span class="sxs-lookup"><span data-stu-id="44e1f-204">No</span></span></p></td>
<td><p><span data-ttu-id="44e1f-p119">リアルタイム転送プロトコル パケットが、あるエンドポイントとの間を往復するのに要する平均時間 (ミリ秒単位)。200 ミリ秒以下の往復時間が許容できる品質と見なされます。</span><span class="sxs-lookup"><span data-stu-id="44e1f-p119">Average amount of time (in milliseconds) required for a Real-Time Transport Protocol packet to travel to one endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="44e1f-p120">この値が高い場合は、国際通話ルーティング、ルーティングの構成ミス、メディア サーバーの過負荷などの原因が考えられます。その結果、双方向のリアルタイムの音声会話が難しくなります。</span><span class="sxs-lookup"><span data-stu-id="44e1f-p120">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e1f-209"><strong>パケット損失</strong></span><span class="sxs-lookup"><span data-stu-id="44e1f-209"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="44e1f-210">いいえ</span><span class="sxs-lookup"><span data-stu-id="44e1f-210">No</span></span></p></td>
<td><p><span data-ttu-id="44e1f-p121">リアルタイム転送プロトコル (RTP) パケット損失の平均レート。(パケット損失は、RTP パケット、つまりインターネット経由で音声とビデオを転送するために使われるプロトコルの一種で、パケットが宛先に到達できなかったときに発生します)。この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーの過負荷などの原因が考えられます。パケット損失が発生すると、通常、音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="44e1f-p121">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e1f-214"><strong>[ジッター (ミリ秒)]</strong></span><span class="sxs-lookup"><span data-stu-id="44e1f-214"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="44e1f-215">いいえ</span><span class="sxs-lookup"><span data-stu-id="44e1f-215">No</span></span></p></td>
<td><p><span data-ttu-id="44e1f-216">RTP パケットの着信間に検出された平均ジッター (ジッターとは、通話の "揺れ" の測定値です)。</span><span class="sxs-lookup"><span data-stu-id="44e1f-216">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="44e1f-217">(ジッタは、通話の&quot;shakiness&quot;の尺度です)。通常、高ジッターの値は、輻輳または過負荷のメディアサーバーによって発生し、音声が歪むか、失われる原因となります。</span><span class="sxs-lookup"><span data-stu-id="44e1f-217">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e1f-218"><strong>ヒーラー隠し比率</strong></span><span class="sxs-lookup"><span data-stu-id="44e1f-218"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="44e1f-219">いいえ</span><span class="sxs-lookup"><span data-stu-id="44e1f-219">No</span></span></p></td>
<td><p><span data-ttu-id="44e1f-p123">サンプルの合計数に対する隠しオーディオ サンプルの平均比率 (隠しオーディオ サンプルとは、突然遷移を取り除くために使用される手法です。突然遷移は、通常、ネットワーク パケットの削除が原因で発生します)。この値が高い場合は、パケット損失やジッターのために高いレベルで損失の隠蔽が適用されています。その結果、音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="44e1f-p123">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e1f-222"><strong>ヒーラー引き伸ばし比率</strong></span><span class="sxs-lookup"><span data-stu-id="44e1f-222"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="44e1f-223">いいえ</span><span class="sxs-lookup"><span data-stu-id="44e1f-223">No</span></span></p></td>
<td><p><span data-ttu-id="44e1f-p124">サンプルの合計数に対する引き伸ばされたオーディオ サンプルの平均比率 (引き伸ばされたオーディオとは、ネットワーク パケットの削除が検出されたときに通話の品質を維持できるように拡張されたオーディオのことです)。この値が高い場合は、ジッターのために高いレベルでサンプルの引き伸ばしが行われています。その結果、音声が機械のように聞こえたりひずんで聞こえたりします。</span><span class="sxs-lookup"><span data-stu-id="44e1f-p124">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e1f-226"><strong>ヒーラー圧縮比率</strong></span><span class="sxs-lookup"><span data-stu-id="44e1f-226"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="44e1f-227">不可</span><span class="sxs-lookup"><span data-stu-id="44e1f-227">No</span></span></p></td>
<td><p><span data-ttu-id="44e1f-p125">サンプルの合計数に対する圧縮オーディオ サンプルの平均比率 (圧縮オーディオとは、ネットワーク パケットの削除が検出されたときに通話の品質を維持できるように圧縮されたオーディオのことです)。この値が高い場合は、ジッターのために高いレベルでサンプルの圧縮が行われています。その結果、音声が早送りされたように聞こえたりひずんで聞こえたりします。</span><span class="sxs-lookup"><span data-stu-id="44e1f-p125">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

