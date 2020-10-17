---
title: 'Lync Server 2013: サーバーパフォーマンスレポート'
description: 'Lync Server 2013: サーバーパフォーマンスレポート。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server Performance Report
ms:assetid: 942bb39a-1790-498e-9d99-8f6ce2d155c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615018(v=OCS.15)
ms:contentKeyID: 48184879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aed9b3b9eeec4487dce4d401df0d70ffba89677b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543343"
---
# <a name="server-performance-report-in-lync-server-2013"></a><span data-ttu-id="6c040-103">Lync Server 2013 のサーバーパフォーマンスレポート</span><span class="sxs-lookup"><span data-stu-id="6c040-103">Server Performance Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c040-104">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="6c040-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="6c040-105">サーバーパフォーマンスレポートには、Microsoft Lync Server 2013 サーバーのうちで、低品質の通話のうち最大の割合を超えるサーバーが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c040-105">The Server Performance Report provides a list of Microsoft Lync Server 2013 servers that have experienced the highest-percentage of poor calls.</span></span> <span data-ttu-id="6c040-106">このレポートは、サーバーの種類ごとに、次の種類について個別の統計情報を報告します。</span><span class="sxs-lookup"><span data-stu-id="6c040-106">The report breaks down servers by server type, reporting separate statistics for the following types:</span></span>

  - <span data-ttu-id="6c040-107">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="6c040-107">Mediation Server</span></span>

  - <span data-ttu-id="6c040-108">音声ビデオ会議サーバー</span><span class="sxs-lookup"><span data-stu-id="6c040-108">A/V Conferencing Server</span></span>

  - <span data-ttu-id="6c040-109">音声ビデオ エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="6c040-109">A/V Edge Server</span></span>

  - <span data-ttu-id="6c040-110">ゲートウェイ (仲介サーバー)</span><span class="sxs-lookup"><span data-stu-id="6c040-110">Gateway (Mediation Server)</span></span>

  - <span data-ttu-id="6c040-111">ゲートウェイ (仲介サーバーのバイパス)</span><span class="sxs-lookup"><span data-stu-id="6c040-111">Gateway (Mediation Server bypass)</span></span>

  - <span data-ttu-id="6c040-112">ビデオ (音声ビデオ会議サーバーと音声ビデオエッジサーバーのビデオ指標を含む)</span><span class="sxs-lookup"><span data-stu-id="6c040-112">Video (including video metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

  - <span data-ttu-id="6c040-113">アプリケーション共有 (音声ビデオ会議サーバーと音声ビデオエッジサーバーのアプリケーション共有指標を含む)</span><span class="sxs-lookup"><span data-stu-id="6c040-113">Application Sharing (including application sharing metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

<span data-ttu-id="6c040-114">このレポートに表示されるランク付けは、相対的なランク付けであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6c040-114">It’s important to note that the ranking shown in this report as relative rankings.</span></span> <span data-ttu-id="6c040-115">たとえば、最もパフォーマンスの低いサーバーでは、1000に配置された通話の間に1つの低品質通話があるとします。</span><span class="sxs-lookup"><span data-stu-id="6c040-115">For example, suppose your worst-performing server had one poor call among its 1,000 placed calls.</span></span> <span data-ttu-id="6c040-116">これは、許容可能なパーセンテージ (1%) です。</span><span class="sxs-lookup"><span data-stu-id="6c040-116">That's a more-than-acceptable percentage of .1%.</span></span> <span data-ttu-id="6c040-117">しかし、これが最もパフォーマンスの低いサーバーである場合 (つまり、他のすべてのサーバーの通話の割合が .1% よりも低い場合)、そのサーバーは引き続きサーバーパフォーマンスレポートに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c040-117">However, if that's the worst-performing server you have (that is, if all your other servers have a poor call percentage even lower than .1%), then that server will still appear on the Server Performance Report.</span></span>

<div>

## <a name="accessing-the-server-performance-report"></a><span data-ttu-id="6c040-118">サーバーパフォーマンスレポートへのアクセス</span><span class="sxs-lookup"><span data-stu-id="6c040-118">Accessing the Server Performance Report</span></span>

<span data-ttu-id="6c040-119">サーバーパフォーマンスレポートには、監視レポートのホームページからアクセスします。</span><span class="sxs-lookup"><span data-stu-id="6c040-119">The Server Performance Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="6c040-120">次のいずれかの指標をクリックすると、 [Lync Server 2013 の通話リストレポート](lync-server-2013-call-list-report.md) にドリルダウンできます。</span><span class="sxs-lookup"><span data-stu-id="6c040-120">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="6c040-121">[通話ボリューム]</span><span class="sxs-lookup"><span data-stu-id="6c040-121">Call volume</span></span>

  - <span data-ttu-id="6c040-122">[低品質通話のパーセンテージ]</span><span class="sxs-lookup"><span data-stu-id="6c040-122">Poor call percentage</span></span>

<span data-ttu-id="6c040-123">また、次の指標をクリックして、サーバーメディア品質傾向レポートにドリルダウンすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6c040-123">In addition, you can drill down to the Server Media Quality Trend Report by clicking the following metric:</span></span>

  - <span data-ttu-id="6c040-124">Trend</span><span class="sxs-lookup"><span data-stu-id="6c040-124">Trend</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-server-performance-report"></a><span data-ttu-id="6c040-125">サーバーパフォーマンスレポートの活用</span><span class="sxs-lookup"><span data-stu-id="6c040-125">Making the Best Use of the Server Performance Report</span></span>

<span data-ttu-id="6c040-126">サーバーパフォーマンスレポートには、データをフィルター処理する方法がいくつか用意されています。たとえば、ネットワークの種類 (ワイヤード接続から発信された通話、およびワイヤレス接続からの通話の呼び出し)、アクセスの種類 (ファイアウォールの内側から発信された呼び出し、ファイアウォールの外側から発信された通話) のフィルター処理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6c040-126">The Server Performance Report provides a number of ways to filter data; for example, you can filter on network type (calls made from a wired connection vs. calls made from a wireless connection) and access type (calls made from inside the firewall vs. calls made from outside the firewall).</span></span> <span data-ttu-id="6c040-127">サーバーパフォーマンスレポートを表示してこれらのフィルターを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6c040-127">It's a good idea when viewing the server performance report to make use of these filters.</span></span> <span data-ttu-id="6c040-128">たとえば、通話の割合が低品質 (3.24%) の仲介サーバーがあるとします。</span><span class="sxs-lookup"><span data-stu-id="6c040-128">For example, suppose you have a Mediation Server that has a poor call percentage of 3.24%.</span></span> <span data-ttu-id="6c040-129">ワイヤレス呼び出しだけである場合は、同じサーバーに、20% に近づいている低品質通話のパーセンテージが設定されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6c040-129">If you look solely at wireless calls, that same server might have a poor call percentage approaching 20%.</span></span> <span data-ttu-id="6c040-130">これは、サーバーが有線通話で問題が発生していないために、部分的に隠されている問題があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="6c040-130">That means that the server was having difficulty with wireless calls, a problem that is partially obscured because the server was not having problems with wired calls.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="6c040-131">フィルター</span><span class="sxs-lookup"><span data-stu-id="6c040-131">Filters</span></span>

<span data-ttu-id="6c040-132">フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざま方法で表示したりする方法として利用できます。</span><span class="sxs-lookup"><span data-stu-id="6c040-132">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="6c040-133">たとえば、サーバーのパフォーマンスレポートを使用すると、返されるデータをサーバーの種類またはネットワークの種類 (有線またはワイヤレス) でフィルター処理することができます。</span><span class="sxs-lookup"><span data-stu-id="6c040-133">For example, the Server Performance Report enables you to do such things as filter the returned data by server type or by network type (that is, wired or wireless).</span></span> <span data-ttu-id="6c040-134">データをグループ化する方法も選択できます。</span><span class="sxs-lookup"><span data-stu-id="6c040-134">You can also choose how data should be grouped.</span></span> <span data-ttu-id="6c040-135">この場合、データは時間、日、週、または月によってグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="6c040-135">In this case, data is grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="6c040-136">次の表に、サーバーパフォーマンスレポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="6c040-136">The following table lists the filters that you can use with the Server Performance Report.</span></span>

### <a name="server-performance-report-filters"></a><span data-ttu-id="6c040-137">サーバーパフォーマンスレポートのフィルター</span><span class="sxs-lookup"><span data-stu-id="6c040-137">Server Performance Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6c040-138">名前</span><span class="sxs-lookup"><span data-stu-id="6c040-138">Name</span></span></th>
<th><span data-ttu-id="6c040-139">説明</span><span class="sxs-lookup"><span data-stu-id="6c040-139">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6c040-140"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="6c040-140"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="6c040-p106">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="6c040-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="6c040-143">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="6c040-143">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="6c040-p107">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="6c040-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="6c040-146">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="6c040-146">7/7/2012</span></span></p>
<p><span data-ttu-id="6c040-147">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="6c040-147">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="6c040-148">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="6c040-148">7/3/2012</span></span></p>
<p><span data-ttu-id="6c040-149">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="6c040-149">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c040-150"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="6c040-150"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="6c040-p108">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="6c040-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="6c040-153">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="6c040-153">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="6c040-p109">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="6c040-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="6c040-156">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="6c040-156">7/7/2012</span></span></p>
<p><span data-ttu-id="6c040-157">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="6c040-157">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="6c040-158">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="6c040-158">7/3/2012</span></span></p>
<p><span data-ttu-id="6c040-159">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="6c040-159">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c040-160"><strong>サーバーの種類</strong></span><span class="sxs-lookup"><span data-stu-id="6c040-160"><strong>Server type</strong></span></span></p></td>
<td><p><span data-ttu-id="6c040-161">パフォーマンスをレポートする必要があるサーバーの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="6c040-161">Indicates the type of server whose performance should be reported.</span></span> <span data-ttu-id="6c040-162">次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="6c040-162">Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="6c040-163">[All]</span><span class="sxs-lookup"><span data-stu-id="6c040-163">[All]</span></span></p></li>
<li><p><span data-ttu-id="6c040-164">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="6c040-164">Mediation Server</span></span></p></li>
<li><p><span data-ttu-id="6c040-165">音声ビデオ会議サーバー</span><span class="sxs-lookup"><span data-stu-id="6c040-165">A/V Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="6c040-166">音声ビデオ エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="6c040-166">A/V Edge Server</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c040-167"><strong>トップ N</strong></span><span class="sxs-lookup"><span data-stu-id="6c040-167"><strong>Top N</strong></span></span></p></td>
<td><p><span data-ttu-id="6c040-168">各カテゴリに表示されるサーバーの数 (低品質通話のパーセンテージに基づく) を示します。</span><span class="sxs-lookup"><span data-stu-id="6c040-168">Indicates the number of servers (based on their poor call percentage) to be displayed in each category.</span></span> <span data-ttu-id="6c040-169">たとえば、[ <strong>5</strong> ] を選択すると、5つの個サーバーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c040-169">For example, if you select <strong>5</strong> then the five poorest-performing servers are displayed.</span></span> <span data-ttu-id="6c040-170">次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="6c040-170">Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="6c040-171">[All]</span><span class="sxs-lookup"><span data-stu-id="6c040-171">[All]</span></span></p></li>
<li><p><span data-ttu-id="6c040-172">5 </span><span class="sxs-lookup"><span data-stu-id="6c040-172">5</span></span></p></li>
<li><p><span data-ttu-id="6c040-173">10  </span><span class="sxs-lookup"><span data-stu-id="6c040-173">10</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c040-174">[<strong>アクセスの種類</strong>]</span><span class="sxs-lookup"><span data-stu-id="6c040-174"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="6c040-p112">クライアントが通話時に内部ネットワークにログオンしたか、外部ネットワークにログオンしたかを示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="6c040-p112">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="6c040-177">[All]</span><span class="sxs-lookup"><span data-stu-id="6c040-177">[All]</span></span></p></li>
<li><p><span data-ttu-id="6c040-178">内部</span><span class="sxs-lookup"><span data-stu-id="6c040-178">Internal</span></span></p></li>
<li><p><span data-ttu-id="6c040-179">外部</span><span class="sxs-lookup"><span data-stu-id="6c040-179">External</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c040-180">[<strong>ネットワークの種類</strong>]</span><span class="sxs-lookup"><span data-stu-id="6c040-180"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="6c040-p113">通話時にクライアントが接続したネットワークの種類を示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="6c040-p113">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="6c040-183">[All]</span><span class="sxs-lookup"><span data-stu-id="6c040-183">[All]</span></span></p></li>
<li><p><span data-ttu-id="6c040-184">有線</span><span class="sxs-lookup"><span data-stu-id="6c040-184">Wired</span></span></p></li>
<li><p><span data-ttu-id="6c040-185">通信</span><span class="sxs-lookup"><span data-stu-id="6c040-185">Wireless</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c040-186"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="6c040-186"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="6c040-p114">通話時に外部クライアントが仮想プライベート ネットワーク (VPN) 接続を使用したかどうかを示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="6c040-p114">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="6c040-189">[All]</span><span class="sxs-lookup"><span data-stu-id="6c040-189">[All]</span></span></p></li>
<li><p><span data-ttu-id="6c040-190">VPN</span><span class="sxs-lookup"><span data-stu-id="6c040-190">VPN</span></span></p></li>
<li><p><span data-ttu-id="6c040-191">非 VPN</span><span class="sxs-lookup"><span data-stu-id="6c040-191">Non-VPN</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="6c040-192">指標</span><span class="sxs-lookup"><span data-stu-id="6c040-192">Metrics</span></span>

<span data-ttu-id="6c040-193">次の表に、サーバーパフォーマンスレポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="6c040-193">The following table lists the information provided in the Server Performance Report.</span></span>

### <a name="server-performance-report-metrics-audio-call-summary"></a><span data-ttu-id="6c040-194">サーバーパフォーマンスレポートの指標: 音声通話の概要</span><span class="sxs-lookup"><span data-stu-id="6c040-194">Server Performance Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6c040-195">名前</span><span class="sxs-lookup"><span data-stu-id="6c040-195">Name</span></span></th>
<th><span data-ttu-id="6c040-196">並べ替え可能</span><span class="sxs-lookup"><span data-stu-id="6c040-196">Can Sort On</span></span></th>
<th><span data-ttu-id="6c040-197">説明</span><span class="sxs-lookup"><span data-stu-id="6c040-197">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6c040-198"><strong>Server</strong></span><span class="sxs-lookup"><span data-stu-id="6c040-198"><strong>Server</strong></span></span></p></td>
<td><p><span data-ttu-id="6c040-199">いいえ</span><span class="sxs-lookup"><span data-stu-id="6c040-199">No</span></span></p></td>
<td><p><span data-ttu-id="6c040-200">サーバーの名前または IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="6c040-200">Name/IP address of the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c040-201">[<strong>通話ボリューム</strong>]</span><span class="sxs-lookup"><span data-stu-id="6c040-201"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="6c040-202">いいえ</span><span class="sxs-lookup"><span data-stu-id="6c040-202">No</span></span></p></td>
<td><p><span data-ttu-id="6c040-203">発信された通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="6c040-203">Total number of calls made.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c040-204">[<strong>低品質通話のパーセンテージ</strong>]</span><span class="sxs-lookup"><span data-stu-id="6c040-204"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="6c040-205">いいえ</span><span class="sxs-lookup"><span data-stu-id="6c040-205">No</span></span></p></td>
<td><p><span data-ttu-id="6c040-p115">低品質として分類される通話の総数。低品質通話とは、少なくとも 1 つの測定指標が許容値を超えている通話 (たとえば、過剰なジッターが発生した通話) のことです。</span><span class="sxs-lookup"><span data-stu-id="6c040-p115">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c040-208">[<strong>往復 (ミリ秒)</strong>]</span><span class="sxs-lookup"><span data-stu-id="6c040-208"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="6c040-209">必要</span><span class="sxs-lookup"><span data-stu-id="6c040-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="6c040-p116">リアルタイム転送プロトコル (RTP) パケットが別のエンドポイントとの間を往復するのに要する平均時間 (ミリ秒単位)。100 ミリ秒以下の往復時間が許容できる品質と見なされます。</span><span class="sxs-lookup"><span data-stu-id="6c040-p116">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="6c040-p117">この値が高い場合は、国際通話ルーティング、ルーティングの構成ミス、メディア サーバーの過負荷などの原因が考えられます。その結果、双方向のリアルタイムの音声会話が難しくなります。</span><span class="sxs-lookup"><span data-stu-id="6c040-p117">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c040-214">[<strong>低下 (MOS)</strong>]</span><span class="sxs-lookup"><span data-stu-id="6c040-214"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="6c040-215">必要</span><span class="sxs-lookup"><span data-stu-id="6c040-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="6c040-216">通話時に発生した平均オピニオン値 (MOS) 低下の平均値。</span><span class="sxs-lookup"><span data-stu-id="6c040-216">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="6c040-217">低下の値範囲は、最低 0.0 から最高 5.0 までとなります。</span><span class="sxs-lookup"><span data-stu-id="6c040-217">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="6c040-218">0.5 以下の値は、許容される低下を表します。</span><span class="sxs-lookup"><span data-stu-id="6c040-218">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="6c040-219">従来、平均オピニオン値は、ユーザーが通話の品質を 1 から 5 の範囲で評価することによって計算されていました。</span><span class="sxs-lookup"><span data-stu-id="6c040-219">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="6c040-220">Lync Server では、監視サーバーは一連のアルゴリズムを使用して、ユーザーが通話を評価する方法を予測します。</span><span class="sxs-lookup"><span data-stu-id="6c040-220">In Lync Server, the Monitoring Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="6c040-p119">この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーやエンドポイントの過負荷などの原因が考えられます。その結果、音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="6c040-p119">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c040-223">[<strong>パケット損失</strong>]</span><span class="sxs-lookup"><span data-stu-id="6c040-223"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="6c040-224">必要</span><span class="sxs-lookup"><span data-stu-id="6c040-224">Yes</span></span></p></td>
<td><p><span data-ttu-id="6c040-225">リアルタイム転送プロトコル (RTP) パケット損失の平均レート。</span><span class="sxs-lookup"><span data-stu-id="6c040-225">Average rate of real-time transport protocol (RTP) packet loss.</span></span> <span data-ttu-id="6c040-226">(パケット損失は、RTP パケット、つまりインターネット経由で音声とビデオを送信するために使用されるプロトコルで、宛先に到達できなかった場合に発生します)。通常、高損失率は輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディアサーバーの過負荷などによって発生します。</span><span class="sxs-lookup"><span data-stu-id="6c040-226">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server.</span></span> <span data-ttu-id="6c040-227">パケット損失が発生すると、通常、音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="6c040-227">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c040-228">[<strong>ジッター (ミリ秒)</strong>]</span><span class="sxs-lookup"><span data-stu-id="6c040-228"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="6c040-229">必要</span><span class="sxs-lookup"><span data-stu-id="6c040-229">Yes</span></span></p></td>
<td><p><span data-ttu-id="6c040-230">RTP パケットの着信間に検出された平均ジッター (ジッターとは、通話の "揺れ" の測定値です)。</span><span class="sxs-lookup"><span data-stu-id="6c040-230">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="6c040-231">(ジッターは、通話の過の測定値です &quot; &quot; )。高ジッター値は、通常、混雑または過負荷のメディアサーバーによって発生し、その結果、音声がひずむか失われます。</span><span class="sxs-lookup"><span data-stu-id="6c040-231">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c040-232">[<strong>ヒーラー隠し比率</strong>]</span><span class="sxs-lookup"><span data-stu-id="6c040-232"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="6c040-233">必要</span><span class="sxs-lookup"><span data-stu-id="6c040-233">Yes</span></span></p></td>
<td><p><span data-ttu-id="6c040-p122">サンプルの合計数に対する隠しオーディオ サンプルの平均比率 (隠しオーディオ サンプルとは、突然遷移を取り除くために使用される手法です。突然遷移は、通常、ネットワーク パケットの削除が原因で発生します)。この値が高い場合は、パケット損失やジッターのために高いレベルで損失の隠蔽が適用されています。その結果、音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="6c040-p122">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c040-236">[<strong>ヒーラー引き伸ばし比率</strong>]</span><span class="sxs-lookup"><span data-stu-id="6c040-236"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="6c040-237">必要</span><span class="sxs-lookup"><span data-stu-id="6c040-237">Yes</span></span></p></td>
<td><p><span data-ttu-id="6c040-p123">サンプルの合計数に対する引き伸ばされたオーディオ サンプルの平均比率 (引き伸ばされたオーディオとは、ネットワーク パケットの削除が検出されたときに通話の品質を維持できるように拡張されたオーディオのことです)。この値が高い場合は、ジッターのために高いレベルでサンプルの引き伸ばしが行われています。その結果、音声が機械のように聞こえたりひずんで聞こえたりします。</span><span class="sxs-lookup"><span data-stu-id="6c040-p123">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c040-240">[<strong>ヒーラー圧縮比率</strong>]</span><span class="sxs-lookup"><span data-stu-id="6c040-240"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="6c040-241">必要</span><span class="sxs-lookup"><span data-stu-id="6c040-241">Yes</span></span></p></td>
<td><p><span data-ttu-id="6c040-p124">サンプルの合計数に対する圧縮オーディオ サンプルの平均比率 (圧縮オーディオとは、ネットワーク パケットの削除が検出されたときに通話の品質を維持できるように圧縮されたオーディオのことです)。この値が高い場合は、ジッターのために高いレベルでサンプルの圧縮が行われています。その結果、音声が早送りされたように聞こえたりひずんで聞こえたりします。</span><span class="sxs-lookup"><span data-stu-id="6c040-p124">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-video-call-summary"></a><span data-ttu-id="6c040-244">サーバーパフォーマンスレポートの指標: ビデオ通話の概要</span><span class="sxs-lookup"><span data-stu-id="6c040-244">Server Performance Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6c040-245">名前</span><span class="sxs-lookup"><span data-stu-id="6c040-245">Name</span></span></th>
<th><span data-ttu-id="6c040-246">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="6c040-246">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="6c040-247">説明</span><span class="sxs-lookup"><span data-stu-id="6c040-247">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6c040-248">[<strong>通話の種類/エンドポイントの種類</strong>]</span><span class="sxs-lookup"><span data-stu-id="6c040-248"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="6c040-249">いいえ</span><span class="sxs-lookup"><span data-stu-id="6c040-249">No</span></span></p></td>
<td><p><span data-ttu-id="6c040-p125">この項目をクリックすると、その種類に基づく通話の詳細情報がレポートに表示されます。通話の種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6c040-p125">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="6c040-252">UC ピアツーピア通話</span><span class="sxs-lookup"><span data-stu-id="6c040-252">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="6c040-253">UC 電話会議セッション</span><span class="sxs-lookup"><span data-stu-id="6c040-253">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="6c040-254">PSTN 電話会議セッション</span><span class="sxs-lookup"><span data-stu-id="6c040-254">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="6c040-255">PSTN 通話: メディアのバイパス</span><span class="sxs-lookup"><span data-stu-id="6c040-255">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="6c040-256">PSTN 通話 (非バイパス): UC レグ</span><span class="sxs-lookup"><span data-stu-id="6c040-256">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="6c040-257">PSTN 通話 (非バイパス): ゲートウェイ レグ</span><span class="sxs-lookup"><span data-stu-id="6c040-257">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="6c040-258">その他の通話の種類</span><span class="sxs-lookup"><span data-stu-id="6c040-258">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c040-259">[<strong>通話ボリューム</strong>]</span><span class="sxs-lookup"><span data-stu-id="6c040-259"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="6c040-260">いいえ</span><span class="sxs-lookup"><span data-stu-id="6c040-260">No</span></span></p></td>
<td><p><span data-ttu-id="6c040-261">通話の種類当たりの通話の総数。</span><span class="sxs-lookup"><span data-stu-id="6c040-261">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c040-262">[<strong>低品質通話のパーセンテージ</strong>]</span><span class="sxs-lookup"><span data-stu-id="6c040-262"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="6c040-263">いいえ</span><span class="sxs-lookup"><span data-stu-id="6c040-263">No</span></span></p></td>
<td><p><span data-ttu-id="6c040-p126">低品質として分類される通話の総数。低品質通話とは、少なくとも 1 つの測定指標が許容値を超えている通話 (たとえば、過剰なジッターが発生した通話) のことです。</span><span class="sxs-lookup"><span data-stu-id="6c040-p126">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c040-266">[<strong>通話ボリューム (ワイヤレス通話)</strong>]</span><span class="sxs-lookup"><span data-stu-id="6c040-266"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="6c040-267">いいえ</span><span class="sxs-lookup"><span data-stu-id="6c040-267">No</span></span></p></td>
<td><p><span data-ttu-id="6c040-268">ワイヤレス接続を使用した通話の総数。</span><span class="sxs-lookup"><span data-stu-id="6c040-268">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c040-269">[<strong>通話ボリューム (VPN 通話)</strong>]</span><span class="sxs-lookup"><span data-stu-id="6c040-269"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="6c040-270">いいえ</span><span class="sxs-lookup"><span data-stu-id="6c040-270">No</span></span></p></td>
<td><p><span data-ttu-id="6c040-271">VPN 接続を使用した通話の総数。</span><span class="sxs-lookup"><span data-stu-id="6c040-271">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c040-272">[<strong>通話ボリューム (外部通話)</strong>]</span><span class="sxs-lookup"><span data-stu-id="6c040-272"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="6c040-273">いいえ</span><span class="sxs-lookup"><span data-stu-id="6c040-273">No</span></span></p></td>
<td><p><span data-ttu-id="6c040-274">外部接続 (つまり、内部ネットワークの外側の接続) を使用した通話の数。</span><span class="sxs-lookup"><span data-stu-id="6c040-274">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c040-275">[<strong>Avg bit-rate (Kbits/s)</strong>]</span><span class="sxs-lookup"><span data-stu-id="6c040-275"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="6c040-276">いいえ</span><span class="sxs-lookup"><span data-stu-id="6c040-276">No</span></span></p></td>
<td><p><span data-ttu-id="6c040-277">平均ビデオ ビット レート (1 秒あたりのキロビット)。</span><span class="sxs-lookup"><span data-stu-id="6c040-277">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c040-278">[<strong>Low bit-rate %</strong>]</span><span class="sxs-lookup"><span data-stu-id="6c040-278"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="6c040-279">いいえ</span><span class="sxs-lookup"><span data-stu-id="6c040-279">No</span></span></p></td>
<td><p><span data-ttu-id="6c040-280">ビット レートが低い通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="6c040-280">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c040-281">[<strong>Outbound packet loss</strong>]</span><span class="sxs-lookup"><span data-stu-id="6c040-281"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="6c040-282">いいえ</span><span class="sxs-lookup"><span data-stu-id="6c040-282">No</span></span></p></td>
<td><p><span data-ttu-id="6c040-283">送信パケットの Real-Time トランスポートプロトコル (RTP) パケット損失。</span><span class="sxs-lookup"><span data-stu-id="6c040-283">Real-Time Transport Protocol (RTP) packet loss for outbound packets.</span></span> <span data-ttu-id="6c040-284">(パケット損失は、RTP パケット、つまりインターネット経由で音声とビデオを送信するために使用されるプロトコルで、宛先に到達できなかった場合に発生します)。通常、高損失率は輻輳が原因で発生します。帯域幅の不足。ワイヤレスの輻輳または干渉。または、オーバーロードされたメディアサーバー。</span><span class="sxs-lookup"><span data-stu-id="6c040-284">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="6c040-285">パケット損失が発生すると、通常、音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="6c040-285">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c040-286">[<strong>フリーズ フレーム %</strong>]</span><span class="sxs-lookup"><span data-stu-id="6c040-286"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="6c040-287">いいえ</span><span class="sxs-lookup"><span data-stu-id="6c040-287">No</span></span></p></td>
<td><p><span data-ttu-id="6c040-p128">"フリーズ" フレームのパーセンテージ。フリーズ フレームでは、通話の音声部分が続いていてもビデオの進行が停止します。</span><span class="sxs-lookup"><span data-stu-id="6c040-p128">Percentage of “frozen” frames. In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c040-290">[<strong>Outbound avg frame rate</strong>]</span><span class="sxs-lookup"><span data-stu-id="6c040-290"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="6c040-291">いいえ</span><span class="sxs-lookup"><span data-stu-id="6c040-291">No</span></span></p></td>
<td><p><span data-ttu-id="6c040-292">通話時の送信の平均フレーム レート。</span><span class="sxs-lookup"><span data-stu-id="6c040-292">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c040-293">[<strong>Inbound avg frame rate</strong>]</span><span class="sxs-lookup"><span data-stu-id="6c040-293"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="6c040-294">いいえ</span><span class="sxs-lookup"><span data-stu-id="6c040-294">No</span></span></p></td>
<td><p><span data-ttu-id="6c040-295">通話時の受信の平均フレーム レート。</span><span class="sxs-lookup"><span data-stu-id="6c040-295">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c040-296">[<strong>Inbound low frame rate %</strong>]</span><span class="sxs-lookup"><span data-stu-id="6c040-296"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="6c040-297">いいえ</span><span class="sxs-lookup"><span data-stu-id="6c040-297">No</span></span></p></td>
<td><p><span data-ttu-id="6c040-298">着信ビデオのビット レートが低い通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="6c040-298">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c040-299">[<strong>Client health %</strong>]</span><span class="sxs-lookup"><span data-stu-id="6c040-299"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6c040-300">通話時のクライアント デバイスの相対的な正常性を示します。</span><span class="sxs-lookup"><span data-stu-id="6c040-300">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="6c040-301">サーバーパフォーマンスレポートの指標: アプリケーション共有の通話の概要</span><span class="sxs-lookup"><span data-stu-id="6c040-301">Server Performance Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6c040-302">名前</span><span class="sxs-lookup"><span data-stu-id="6c040-302">Name</span></span></th>
<th><span data-ttu-id="6c040-303">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="6c040-303">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="6c040-304">説明</span><span class="sxs-lookup"><span data-stu-id="6c040-304">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6c040-305">[<strong>通話の種類/エンドポイントの種類</strong>]</span><span class="sxs-lookup"><span data-stu-id="6c040-305"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="6c040-306">いいえ</span><span class="sxs-lookup"><span data-stu-id="6c040-306">No</span></span></p></td>
<td><p><span data-ttu-id="6c040-p129">この項目をクリックすると、その種類に基づく通話の詳細情報がレポートに表示されます。通話の種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6c040-p129">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="6c040-309">UC ピアツーピア通話</span><span class="sxs-lookup"><span data-stu-id="6c040-309">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="6c040-310">UC 電話会議セッション</span><span class="sxs-lookup"><span data-stu-id="6c040-310">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="6c040-311">PSTN 電話会議セッション</span><span class="sxs-lookup"><span data-stu-id="6c040-311">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="6c040-312">PSTN 通話: メディアのバイパス</span><span class="sxs-lookup"><span data-stu-id="6c040-312">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="6c040-313">PSTN 通話 (非バイパス): UC レグ</span><span class="sxs-lookup"><span data-stu-id="6c040-313">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="6c040-314">PSTN 通話 (非バイパス): ゲートウェイ レグ</span><span class="sxs-lookup"><span data-stu-id="6c040-314">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="6c040-315">その他の通話の種類</span><span class="sxs-lookup"><span data-stu-id="6c040-315">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c040-316">[<strong>通話ボリューム</strong>]</span><span class="sxs-lookup"><span data-stu-id="6c040-316"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="6c040-317">いいえ</span><span class="sxs-lookup"><span data-stu-id="6c040-317">No</span></span></p></td>
<td><p><span data-ttu-id="6c040-318">通話の種類当たりの通話の総数。</span><span class="sxs-lookup"><span data-stu-id="6c040-318">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c040-319">[<strong>低品質通話のパーセンテージ</strong>]</span><span class="sxs-lookup"><span data-stu-id="6c040-319"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="6c040-320">いいえ</span><span class="sxs-lookup"><span data-stu-id="6c040-320">No</span></span></p></td>
<td><p><span data-ttu-id="6c040-p130">低品質として分類される通話の総数。低品質通話とは、少なくとも 1 つの測定指標が許容値を超えている通話 (たとえば、過剰なジッターが発生した通話) のことです。</span><span class="sxs-lookup"><span data-stu-id="6c040-p130">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c040-323">[<strong>通話ボリューム (ワイヤレス通話)</strong>]</span><span class="sxs-lookup"><span data-stu-id="6c040-323"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="6c040-324">いいえ</span><span class="sxs-lookup"><span data-stu-id="6c040-324">No</span></span></p></td>
<td><p><span data-ttu-id="6c040-325">ワイヤレス接続を使用した通話の総数。</span><span class="sxs-lookup"><span data-stu-id="6c040-325">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c040-326">[<strong>通話ボリューム (VPN 通話)</strong>]</span><span class="sxs-lookup"><span data-stu-id="6c040-326"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="6c040-327">いいえ</span><span class="sxs-lookup"><span data-stu-id="6c040-327">No</span></span></p></td>
<td><p><span data-ttu-id="6c040-328">VPN 接続を使用した通話の総数。</span><span class="sxs-lookup"><span data-stu-id="6c040-328">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c040-329">[<strong>通話ボリューム (外部通話)</strong>]</span><span class="sxs-lookup"><span data-stu-id="6c040-329"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="6c040-330">いいえ</span><span class="sxs-lookup"><span data-stu-id="6c040-330">No</span></span></p></td>
<td><p><span data-ttu-id="6c040-331">外部接続 (つまり、内部ネットワークの外側の接続) を使用した通話の数。</span><span class="sxs-lookup"><span data-stu-id="6c040-331">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c040-332">[<strong>ジッター (ミリ秒)</strong>]</span><span class="sxs-lookup"><span data-stu-id="6c040-332"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="6c040-333">いいえ</span><span class="sxs-lookup"><span data-stu-id="6c040-333">No</span></span></p></td>
<td><p><span data-ttu-id="6c040-334">RTP パケットの着信間に検出された平均ジッター (ジッターとは、通話の "揺れ" の測定値です)。</span><span class="sxs-lookup"><span data-stu-id="6c040-334">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="6c040-335">(ジッターは、通話の過の測定値です &quot; &quot; )。高ジッター値は、通常、混雑または過負荷のメディアサーバーによって発生し、その結果、音声がひずむか失われます。</span><span class="sxs-lookup"><span data-stu-id="6c040-335">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c040-336">[<strong>Relative one way delay burst density (ms)</strong>]</span><span class="sxs-lookup"><span data-stu-id="6c040-336"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="6c040-337">いいえ</span><span class="sxs-lookup"><span data-stu-id="6c040-337">No</span></span></p></td>
<td><p><span data-ttu-id="6c040-p132">2 つのメディア エンドポイント間の相対的な一方向の平均遅延。これは、1 ホップの遅延の測定です。</span><span class="sxs-lookup"><span data-stu-id="6c040-p132">Average relative one-way delay between two media endpoints. This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c040-340">[<strong>RDP Tile processing latency burst density (ms)</strong>]</span><span class="sxs-lookup"><span data-stu-id="6c040-340"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="6c040-341">いいえ</span><span class="sxs-lookup"><span data-stu-id="6c040-341">No</span></span></p></td>
<td><p><span data-ttu-id="6c040-p133">表示セッション中の AS 会議サーバーでの RDP タイル処理の平均遅延。ネットワーク遅延はこの指標の対象外です。平均値が高いと、表示の際の遅延が大きくなります。過負荷の会議サーバーでは平均遅延が大きくなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6c040-p133">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session. This metric does not cover network latency. A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c040-346">[<strong>損失した合計タイル %</strong>]</span><span class="sxs-lookup"><span data-stu-id="6c040-346"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="6c040-347">いいえ</span><span class="sxs-lookup"><span data-stu-id="6c040-347">No</span></span></p></td>
<td><p><span data-ttu-id="6c040-348">損失した RDP タイル数のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="6c040-348">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

