---
title: 'Lync Server 2013: サーバーパフォーマンスレポート'
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
ms.openlocfilehash: 05c1e366c797eb0c626d00744ef6f0088d28e465
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143985"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-performance-report-in-lync-server-2013"></a><span data-ttu-id="affc6-102">Lync Server 2013 のサーバーパフォーマンスレポート</span><span class="sxs-lookup"><span data-stu-id="affc6-102">Server Performance Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="affc6-103">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="affc6-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="affc6-104">サーバーパフォーマンスレポートには、Microsoft Lync Server 2013 サーバーのうちで、低品質の通話のうち最大の割合を超えるサーバーが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="affc6-104">The Server Performance Report provides a list of Microsoft Lync Server 2013 servers that have experienced the highest-percentage of poor calls.</span></span> <span data-ttu-id="affc6-105">このレポートは、サーバーの種類ごとに、次の種類について個別の統計情報を報告します。</span><span class="sxs-lookup"><span data-stu-id="affc6-105">The report breaks down servers by server type, reporting separate statistics for the following types:</span></span>

  - <span data-ttu-id="affc6-106">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="affc6-106">Mediation Server</span></span>

  - <span data-ttu-id="affc6-107">音声ビデオ会議サーバー</span><span class="sxs-lookup"><span data-stu-id="affc6-107">A/V Conferencing Server</span></span>

  - <span data-ttu-id="affc6-108">音声ビデオ エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="affc6-108">A/V Edge Server</span></span>

  - <span data-ttu-id="affc6-109">ゲートウェイ (仲介サーバー)</span><span class="sxs-lookup"><span data-stu-id="affc6-109">Gateway (Mediation Server)</span></span>

  - <span data-ttu-id="affc6-110">ゲートウェイ (仲介サーバーのバイパス)</span><span class="sxs-lookup"><span data-stu-id="affc6-110">Gateway (Mediation Server bypass)</span></span>

  - <span data-ttu-id="affc6-111">ビデオ (音声ビデオ会議サーバーと音声ビデオエッジサーバーのビデオ指標を含む)</span><span class="sxs-lookup"><span data-stu-id="affc6-111">Video (including video metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

  - <span data-ttu-id="affc6-112">アプリケーション共有 (音声ビデオ会議サーバーと音声ビデオエッジサーバーのアプリケーション共有指標を含む)</span><span class="sxs-lookup"><span data-stu-id="affc6-112">Application Sharing (including application sharing metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

<span data-ttu-id="affc6-113">このレポートに表示されるランク付けは、相対的なランク付けであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="affc6-113">It’s important to note that the ranking shown in this report as relative rankings.</span></span> <span data-ttu-id="affc6-114">たとえば、最もパフォーマンスの低いサーバーでは、1000に配置された通話の間に1つの低品質通話があるとします。</span><span class="sxs-lookup"><span data-stu-id="affc6-114">For example, suppose your worst-performing server had one poor call among its 1,000 placed calls.</span></span> <span data-ttu-id="affc6-115">これは、許容可能なパーセンテージ (1%) です。</span><span class="sxs-lookup"><span data-stu-id="affc6-115">That's a more-than-acceptable percentage of .1%.</span></span> <span data-ttu-id="affc6-116">しかし、これが最もパフォーマンスの低いサーバーである場合 (つまり、他のすべてのサーバーの通話の割合が .1% よりも低い場合)、そのサーバーは引き続きサーバーパフォーマンスレポートに表示されます。</span><span class="sxs-lookup"><span data-stu-id="affc6-116">However, if that's the worst-performing server you have (that is, if all your other servers have a poor call percentage even lower than .1%), then that server will still appear on the Server Performance Report.</span></span>

<div>

## <a name="accessing-the-server-performance-report"></a><span data-ttu-id="affc6-117">サーバーパフォーマンスレポートへのアクセス</span><span class="sxs-lookup"><span data-stu-id="affc6-117">Accessing the Server Performance Report</span></span>

<span data-ttu-id="affc6-118">サーバーパフォーマンスレポートには、監視レポートのホームページからアクセスします。</span><span class="sxs-lookup"><span data-stu-id="affc6-118">The Server Performance Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="affc6-119">次のいずれかの指標をクリックすると、 [Lync Server 2013 の通話リストレポート](lync-server-2013-call-list-report.md)にドリルダウンできます。</span><span class="sxs-lookup"><span data-stu-id="affc6-119">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="affc6-120">[通話ボリューム]</span><span class="sxs-lookup"><span data-stu-id="affc6-120">Call volume</span></span>

  - <span data-ttu-id="affc6-121">[低品質通話のパーセンテージ]</span><span class="sxs-lookup"><span data-stu-id="affc6-121">Poor call percentage</span></span>

<span data-ttu-id="affc6-122">また、次の指標をクリックして、サーバーメディア品質傾向レポートにドリルダウンすることもできます。</span><span class="sxs-lookup"><span data-stu-id="affc6-122">In addition, you can drill down to the Server Media Quality Trend Report by clicking the following metric:</span></span>

  - <span data-ttu-id="affc6-123">Trend</span><span class="sxs-lookup"><span data-stu-id="affc6-123">Trend</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-server-performance-report"></a><span data-ttu-id="affc6-124">サーバーパフォーマンスレポートの活用</span><span class="sxs-lookup"><span data-stu-id="affc6-124">Making the Best Use of the Server Performance Report</span></span>

<span data-ttu-id="affc6-125">サーバーパフォーマンスレポートには、データをフィルター処理する方法がいくつか用意されています。たとえば、ネットワークの種類 (ワイヤード接続から発信された通話、およびワイヤレス接続からの通話の呼び出し)、アクセスの種類 (ファイアウォールの内側から発信された呼び出し、ファイアウォールの外側から発信された通話) のフィルター処理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="affc6-125">The Server Performance Report provides a number of ways to filter data; for example, you can filter on network type (calls made from a wired connection vs. calls made from a wireless connection) and access type (calls made from inside the firewall vs. calls made from outside the firewall).</span></span> <span data-ttu-id="affc6-126">サーバーパフォーマンスレポートを表示してこれらのフィルターを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="affc6-126">It's a good idea when viewing the server performance report to make use of these filters.</span></span> <span data-ttu-id="affc6-127">たとえば、通話の割合が低品質 (3.24%) の仲介サーバーがあるとします。</span><span class="sxs-lookup"><span data-stu-id="affc6-127">For example, suppose you have a Mediation Server that has a poor call percentage of 3.24%.</span></span> <span data-ttu-id="affc6-128">ワイヤレス呼び出しだけである場合は、同じサーバーに、20% に近づいている低品質通話のパーセンテージが設定されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="affc6-128">If you look solely at wireless calls, that same server might have a poor call percentage approaching 20%.</span></span> <span data-ttu-id="affc6-129">これは、サーバーが有線通話で問題が発生していないために、部分的に隠されている問題があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="affc6-129">That means that the server was having difficulty with wireless calls, a problem that is partially obscured because the server was not having problems with wired calls.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="affc6-130">フィルター</span><span class="sxs-lookup"><span data-stu-id="affc6-130">Filters</span></span>

<span data-ttu-id="affc6-131">フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざま方法で表示したりする方法として利用できます。</span><span class="sxs-lookup"><span data-stu-id="affc6-131">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="affc6-132">たとえば、サーバーのパフォーマンスレポートを使用すると、返されるデータをサーバーの種類またはネットワークの種類 (有線またはワイヤレス) でフィルター処理することができます。</span><span class="sxs-lookup"><span data-stu-id="affc6-132">For example, the Server Performance Report enables you to do such things as filter the returned data by server type or by network type (that is, wired or wireless).</span></span> <span data-ttu-id="affc6-133">データをグループ化する方法も選択できます。</span><span class="sxs-lookup"><span data-stu-id="affc6-133">You can also choose how data should be grouped.</span></span> <span data-ttu-id="affc6-134">この場合、データは時間、日、週、または月によってグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="affc6-134">In this case, data is grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="affc6-135">次の表に、サーバーパフォーマンスレポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="affc6-135">The following table lists the filters that you can use with the Server Performance Report.</span></span>

### <a name="server-performance-report-filters"></a><span data-ttu-id="affc6-136">サーバーパフォーマンスレポートのフィルター</span><span class="sxs-lookup"><span data-stu-id="affc6-136">Server Performance Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="affc6-137">名前</span><span class="sxs-lookup"><span data-stu-id="affc6-137">Name</span></span></th>
<th><span data-ttu-id="affc6-138">説明</span><span class="sxs-lookup"><span data-stu-id="affc6-138">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="affc6-139"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="affc6-139"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="affc6-p106">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="affc6-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="affc6-142">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="affc6-142">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="affc6-p107">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="affc6-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="affc6-145">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="affc6-145">7/7/2012</span></span></p>
<p><span data-ttu-id="affc6-146">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="affc6-146">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="affc6-147">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="affc6-147">7/3/2012</span></span></p>
<p><span data-ttu-id="affc6-148">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="affc6-148">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="affc6-149"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="affc6-149"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="affc6-p108">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="affc6-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="affc6-152">7/7/2012 13:00</span><span class="sxs-lookup"><span data-stu-id="affc6-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="affc6-p109">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="affc6-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="affc6-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="affc6-155">7/7/2012</span></span></p>
<p><span data-ttu-id="affc6-156">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="affc6-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="affc6-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="affc6-157">7/3/2012</span></span></p>
<p><span data-ttu-id="affc6-158">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="affc6-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="affc6-159"><strong>サーバーの種類</strong></span><span class="sxs-lookup"><span data-stu-id="affc6-159"><strong>Server type</strong></span></span></p></td>
<td><p><span data-ttu-id="affc6-160">パフォーマンスをレポートする必要があるサーバーの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="affc6-160">Indicates the type of server whose performance should be reported.</span></span> <span data-ttu-id="affc6-161">次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="affc6-161">Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="affc6-162">いずれ</span><span class="sxs-lookup"><span data-stu-id="affc6-162">[All]</span></span></p></li>
<li><p><span data-ttu-id="affc6-163">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="affc6-163">Mediation Server</span></span></p></li>
<li><p><span data-ttu-id="affc6-164">音声ビデオ会議サーバー</span><span class="sxs-lookup"><span data-stu-id="affc6-164">A/V Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="affc6-165">音声ビデオ エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="affc6-165">A/V Edge Server</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="affc6-166"><strong>トップ N</strong></span><span class="sxs-lookup"><span data-stu-id="affc6-166"><strong>Top N</strong></span></span></p></td>
<td><p><span data-ttu-id="affc6-167">各カテゴリに表示されるサーバーの数 (低品質通話のパーセンテージに基づく) を示します。</span><span class="sxs-lookup"><span data-stu-id="affc6-167">Indicates the number of servers (based on their poor call percentage) to be displayed in each category.</span></span> <span data-ttu-id="affc6-168">たとえば、[ <strong>5</strong> ] を選択すると、5つの個サーバーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="affc6-168">For example, if you select <strong>5</strong> then the five poorest-performing servers are displayed.</span></span> <span data-ttu-id="affc6-169">次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="affc6-169">Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="affc6-170">いずれ</span><span class="sxs-lookup"><span data-stu-id="affc6-170">[All]</span></span></p></li>
<li><p><span data-ttu-id="affc6-171">5</span><span class="sxs-lookup"><span data-stu-id="affc6-171">5</span></span></p></li>
<li><p><span data-ttu-id="affc6-172">10 </span><span class="sxs-lookup"><span data-stu-id="affc6-172">10</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="affc6-173">[<strong>アクセスの種類</strong>]</span><span class="sxs-lookup"><span data-stu-id="affc6-173"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="affc6-p112">クライアントが通話時に内部ネットワークにログオンしたか、外部ネットワークにログオンしたかを示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="affc6-p112">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="affc6-176">いずれ</span><span class="sxs-lookup"><span data-stu-id="affc6-176">[All]</span></span></p></li>
<li><p><span data-ttu-id="affc6-177">内部</span><span class="sxs-lookup"><span data-stu-id="affc6-177">Internal</span></span></p></li>
<li><p><span data-ttu-id="affc6-178">External</span><span class="sxs-lookup"><span data-stu-id="affc6-178">External</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="affc6-179">[<strong>ネットワークの種類</strong>]</span><span class="sxs-lookup"><span data-stu-id="affc6-179"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="affc6-p113">通話時にクライアントが接続したネットワークの種類を示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="affc6-p113">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="affc6-182">いずれ</span><span class="sxs-lookup"><span data-stu-id="affc6-182">[All]</span></span></p></li>
<li><p><span data-ttu-id="affc6-183">有線</span><span class="sxs-lookup"><span data-stu-id="affc6-183">Wired</span></span></p></li>
<li><p><span data-ttu-id="affc6-184">通信</span><span class="sxs-lookup"><span data-stu-id="affc6-184">Wireless</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="affc6-185"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="affc6-185"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="affc6-p114">通話時に外部クライアントが仮想プライベート ネットワーク (VPN) 接続を使用したかどうかを示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="affc6-p114">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="affc6-188">いずれ</span><span class="sxs-lookup"><span data-stu-id="affc6-188">[All]</span></span></p></li>
<li><p><span data-ttu-id="affc6-189">VPN</span><span class="sxs-lookup"><span data-stu-id="affc6-189">VPN</span></span></p></li>
<li><p><span data-ttu-id="affc6-190">非 VPN</span><span class="sxs-lookup"><span data-stu-id="affc6-190">Non-VPN</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="affc6-191">指標</span><span class="sxs-lookup"><span data-stu-id="affc6-191">Metrics</span></span>

<span data-ttu-id="affc6-192">次の表に、サーバーパフォーマンスレポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="affc6-192">The following table lists the information provided in the Server Performance Report.</span></span>

### <a name="server-performance-report-metrics-audio-call-summary"></a><span data-ttu-id="affc6-193">サーバーパフォーマンスレポートの指標: 音声通話の概要</span><span class="sxs-lookup"><span data-stu-id="affc6-193">Server Performance Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="affc6-194">名前</span><span class="sxs-lookup"><span data-stu-id="affc6-194">Name</span></span></th>
<th><span data-ttu-id="affc6-195">並べ替え可能</span><span class="sxs-lookup"><span data-stu-id="affc6-195">Can Sort On</span></span></th>
<th><span data-ttu-id="affc6-196">説明</span><span class="sxs-lookup"><span data-stu-id="affc6-196">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="affc6-197"><strong>サーバー</strong></span><span class="sxs-lookup"><span data-stu-id="affc6-197"><strong>Server</strong></span></span></p></td>
<td><p><span data-ttu-id="affc6-198">いいえ</span><span class="sxs-lookup"><span data-stu-id="affc6-198">No</span></span></p></td>
<td><p><span data-ttu-id="affc6-199">サーバーの名前または IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="affc6-199">Name/IP address of the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="affc6-200">[<strong>通話ボリューム</strong>]</span><span class="sxs-lookup"><span data-stu-id="affc6-200"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="affc6-201">いいえ</span><span class="sxs-lookup"><span data-stu-id="affc6-201">No</span></span></p></td>
<td><p><span data-ttu-id="affc6-202">発信された通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="affc6-202">Total number of calls made.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="affc6-203">[<strong>低品質通話のパーセンテージ</strong>]</span><span class="sxs-lookup"><span data-stu-id="affc6-203"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="affc6-204">いいえ</span><span class="sxs-lookup"><span data-stu-id="affc6-204">No</span></span></p></td>
<td><p><span data-ttu-id="affc6-p115">低品質として分類される通話の総数。低品質通話とは、少なくとも 1 つの測定指標が許容値を超えている通話 (たとえば、過剰なジッターが発生した通話) のことです。</span><span class="sxs-lookup"><span data-stu-id="affc6-p115">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="affc6-207">[<strong>往復 (ミリ秒)</strong>]</span><span class="sxs-lookup"><span data-stu-id="affc6-207"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="affc6-208">はい</span><span class="sxs-lookup"><span data-stu-id="affc6-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="affc6-p116">リアルタイム転送プロトコル (RTP) パケットが別のエンドポイントとの間を往復するのに要する平均時間 (ミリ秒単位)。100 ミリ秒以下の往復時間が許容できる品質と見なされます。</span><span class="sxs-lookup"><span data-stu-id="affc6-p116">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="affc6-p117">この値が高い場合は、国際通話ルーティング、ルーティングの構成ミス、メディア サーバーの過負荷などの原因が考えられます。その結果、双方向のリアルタイムの音声会話が難しくなります。</span><span class="sxs-lookup"><span data-stu-id="affc6-p117">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="affc6-213">[<strong>低下 (MOS)</strong>]</span><span class="sxs-lookup"><span data-stu-id="affc6-213"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="affc6-214">はい</span><span class="sxs-lookup"><span data-stu-id="affc6-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="affc6-215">通話時に発生した平均オピニオン値 (MOS) 低下の平均値。</span><span class="sxs-lookup"><span data-stu-id="affc6-215">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="affc6-216">低下の値範囲は、最低 0.0 から最高 5.0 までとなります。</span><span class="sxs-lookup"><span data-stu-id="affc6-216">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="affc6-217">0.5 以下の値は、許容される低下を表します。</span><span class="sxs-lookup"><span data-stu-id="affc6-217">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="affc6-218">従来、平均オピニオン値は、ユーザーが通話の品質を 1 から 5 の範囲で評価することによって計算されていました。</span><span class="sxs-lookup"><span data-stu-id="affc6-218">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="affc6-219">Lync Server では、監視サーバーは一連のアルゴリズムを使用して、ユーザーが通話を評価する方法を予測します。</span><span class="sxs-lookup"><span data-stu-id="affc6-219">In Lync Server, the Monitoring Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="affc6-p119">この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーやエンドポイントの過負荷などの原因が考えられます。その結果、音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="affc6-p119">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="affc6-222">[<strong>パケット損失</strong>]</span><span class="sxs-lookup"><span data-stu-id="affc6-222"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="affc6-223">はい</span><span class="sxs-lookup"><span data-stu-id="affc6-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="affc6-224">リアルタイム転送プロトコル (RTP) パケット損失の平均レート。</span><span class="sxs-lookup"><span data-stu-id="affc6-224">Average rate of real-time transport protocol (RTP) packet loss.</span></span> <span data-ttu-id="affc6-225">(パケット損失は、RTP パケット、つまりインターネット経由で音声とビデオを送信するために使用されるプロトコルで、宛先に到達できなかった場合に発生します)。通常、高損失率は輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディアサーバーの過負荷などによって発生します。</span><span class="sxs-lookup"><span data-stu-id="affc6-225">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server.</span></span> <span data-ttu-id="affc6-226">パケット損失が発生すると、通常、音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="affc6-226">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="affc6-227">[<strong>ジッター (ミリ秒)</strong>]</span><span class="sxs-lookup"><span data-stu-id="affc6-227"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="affc6-228">はい</span><span class="sxs-lookup"><span data-stu-id="affc6-228">Yes</span></span></p></td>
<td><p><span data-ttu-id="affc6-229">RTP パケットの着信間に検出された平均ジッター (ジッターとは、通話の "揺れ" の測定値です)。</span><span class="sxs-lookup"><span data-stu-id="affc6-229">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="affc6-230">(ジッターは、通話の&quot;過&quot;の測定値です)。高ジッター値は、通常、混雑または過負荷のメディアサーバーによって発生し、その結果、音声がひずむか失われます。</span><span class="sxs-lookup"><span data-stu-id="affc6-230">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="affc6-231">[<strong>ヒーラー隠し比率</strong>]</span><span class="sxs-lookup"><span data-stu-id="affc6-231"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="affc6-232">はい</span><span class="sxs-lookup"><span data-stu-id="affc6-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="affc6-p122">サンプルの合計数に対する隠しオーディオ サンプルの平均比率 (隠しオーディオ サンプルとは、突然遷移を取り除くために使用される手法です。突然遷移は、通常、ネットワーク パケットの削除が原因で発生します)。この値が高い場合は、パケット損失やジッターのために高いレベルで損失の隠蔽が適用されています。その結果、音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="affc6-p122">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="affc6-235">[<strong>ヒーラー引き伸ばし比率</strong>]</span><span class="sxs-lookup"><span data-stu-id="affc6-235"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="affc6-236">はい</span><span class="sxs-lookup"><span data-stu-id="affc6-236">Yes</span></span></p></td>
<td><p><span data-ttu-id="affc6-p123">サンプルの合計数に対する引き伸ばされたオーディオ サンプルの平均比率 (引き伸ばされたオーディオとは、ネットワーク パケットの削除が検出されたときに通話の品質を維持できるように拡張されたオーディオのことです)。この値が高い場合は、ジッターのために高いレベルでサンプルの引き伸ばしが行われています。その結果、音声が機械のように聞こえたりひずんで聞こえたりします。</span><span class="sxs-lookup"><span data-stu-id="affc6-p123">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="affc6-239">[<strong>ヒーラー圧縮比率</strong>]</span><span class="sxs-lookup"><span data-stu-id="affc6-239"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="affc6-240">はい</span><span class="sxs-lookup"><span data-stu-id="affc6-240">Yes</span></span></p></td>
<td><p><span data-ttu-id="affc6-p124">サンプルの合計数に対する圧縮オーディオ サンプルの平均比率 (圧縮オーディオとは、ネットワーク パケットの削除が検出されたときに通話の品質を維持できるように圧縮されたオーディオのことです)。この値が高い場合は、ジッターのために高いレベルでサンプルの圧縮が行われています。その結果、音声が早送りされたように聞こえたりひずんで聞こえたりします。</span><span class="sxs-lookup"><span data-stu-id="affc6-p124">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-video-call-summary"></a><span data-ttu-id="affc6-243">サーバーパフォーマンスレポートの指標: ビデオ通話の概要</span><span class="sxs-lookup"><span data-stu-id="affc6-243">Server Performance Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="affc6-244">名前</span><span class="sxs-lookup"><span data-stu-id="affc6-244">Name</span></span></th>
<th><span data-ttu-id="affc6-245">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="affc6-245">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="affc6-246">説明</span><span class="sxs-lookup"><span data-stu-id="affc6-246">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="affc6-247">[<strong>通話の種類/エンドポイントの種類</strong>]</span><span class="sxs-lookup"><span data-stu-id="affc6-247"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="affc6-248">いいえ</span><span class="sxs-lookup"><span data-stu-id="affc6-248">No</span></span></p></td>
<td><p><span data-ttu-id="affc6-p125">この項目をクリックすると、その種類に基づく通話の詳細情報がレポートに表示されます。通話の種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="affc6-p125">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="affc6-251">UC ピアツーピア通話</span><span class="sxs-lookup"><span data-stu-id="affc6-251">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="affc6-252">UC 電話会議セッション</span><span class="sxs-lookup"><span data-stu-id="affc6-252">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="affc6-253">PSTN 電話会議セッション</span><span class="sxs-lookup"><span data-stu-id="affc6-253">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="affc6-254">PSTN 通話: メディアのバイパス</span><span class="sxs-lookup"><span data-stu-id="affc6-254">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="affc6-255">PSTN 通話 (非バイパス): UC レグ</span><span class="sxs-lookup"><span data-stu-id="affc6-255">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="affc6-256">PSTN 通話 (非バイパス): ゲートウェイ レグ</span><span class="sxs-lookup"><span data-stu-id="affc6-256">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="affc6-257">その他の通話の種類</span><span class="sxs-lookup"><span data-stu-id="affc6-257">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="affc6-258">[<strong>通話ボリューム</strong>]</span><span class="sxs-lookup"><span data-stu-id="affc6-258"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="affc6-259">いいえ</span><span class="sxs-lookup"><span data-stu-id="affc6-259">No</span></span></p></td>
<td><p><span data-ttu-id="affc6-260">通話の種類当たりの通話の総数。</span><span class="sxs-lookup"><span data-stu-id="affc6-260">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="affc6-261">[<strong>低品質通話のパーセンテージ</strong>]</span><span class="sxs-lookup"><span data-stu-id="affc6-261"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="affc6-262">いいえ</span><span class="sxs-lookup"><span data-stu-id="affc6-262">No</span></span></p></td>
<td><p><span data-ttu-id="affc6-p126">低品質として分類される通話の総数。低品質通話とは、少なくとも 1 つの測定指標が許容値を超えている通話 (たとえば、過剰なジッターが発生した通話) のことです。</span><span class="sxs-lookup"><span data-stu-id="affc6-p126">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="affc6-265">[<strong>通話ボリューム (ワイヤレス通話)</strong>]</span><span class="sxs-lookup"><span data-stu-id="affc6-265"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="affc6-266">いいえ</span><span class="sxs-lookup"><span data-stu-id="affc6-266">No</span></span></p></td>
<td><p><span data-ttu-id="affc6-267">ワイヤレス接続を使用した通話の総数。</span><span class="sxs-lookup"><span data-stu-id="affc6-267">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="affc6-268">[<strong>通話ボリューム (VPN 通話)</strong>]</span><span class="sxs-lookup"><span data-stu-id="affc6-268"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="affc6-269">いいえ</span><span class="sxs-lookup"><span data-stu-id="affc6-269">No</span></span></p></td>
<td><p><span data-ttu-id="affc6-270">VPN 接続を使用した通話の総数。</span><span class="sxs-lookup"><span data-stu-id="affc6-270">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="affc6-271">[<strong>通話ボリューム (外部通話)</strong>]</span><span class="sxs-lookup"><span data-stu-id="affc6-271"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="affc6-272">いいえ</span><span class="sxs-lookup"><span data-stu-id="affc6-272">No</span></span></p></td>
<td><p><span data-ttu-id="affc6-273">外部接続 (つまり、内部ネットワークの外側の接続) を使用した通話の数。</span><span class="sxs-lookup"><span data-stu-id="affc6-273">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="affc6-274">[<strong>Avg bit-rate (Kbits/s)</strong>]</span><span class="sxs-lookup"><span data-stu-id="affc6-274"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="affc6-275">いいえ</span><span class="sxs-lookup"><span data-stu-id="affc6-275">No</span></span></p></td>
<td><p><span data-ttu-id="affc6-276">平均ビデオ ビット レート (1 秒あたりのキロビット)。</span><span class="sxs-lookup"><span data-stu-id="affc6-276">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="affc6-277">[<strong>Low bit-rate %</strong>]</span><span class="sxs-lookup"><span data-stu-id="affc6-277"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="affc6-278">いいえ</span><span class="sxs-lookup"><span data-stu-id="affc6-278">No</span></span></p></td>
<td><p><span data-ttu-id="affc6-279">ビット レートが低い通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="affc6-279">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="affc6-280">[<strong>Outbound packet loss</strong>]</span><span class="sxs-lookup"><span data-stu-id="affc6-280"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="affc6-281">いいえ</span><span class="sxs-lookup"><span data-stu-id="affc6-281">No</span></span></p></td>
<td><p><span data-ttu-id="affc6-282">送信パケットのリアルタイム転送プロトコル (RTP) パケット損失。</span><span class="sxs-lookup"><span data-stu-id="affc6-282">Real-Time Transport Protocol (RTP) packet loss for outbound packets.</span></span> <span data-ttu-id="affc6-283">(パケット損失は、RTP パケット、つまりインターネット経由で音声とビデオを送信するために使用されるプロトコルで、宛先に到達できなかった場合に発生します)。通常、高損失率は輻輳が原因で発生します。帯域幅の不足。ワイヤレスの輻輳または干渉。または、オーバーロードされたメディアサーバー。</span><span class="sxs-lookup"><span data-stu-id="affc6-283">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="affc6-284">パケット損失が発生すると、通常、音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="affc6-284">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="affc6-285">[<strong>フリーズ フレーム %</strong>]</span><span class="sxs-lookup"><span data-stu-id="affc6-285"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="affc6-286">いいえ</span><span class="sxs-lookup"><span data-stu-id="affc6-286">No</span></span></p></td>
<td><p><span data-ttu-id="affc6-p128">"フリーズ" フレームのパーセンテージ。フリーズ フレームでは、通話の音声部分が続いていてもビデオの進行が停止します。</span><span class="sxs-lookup"><span data-stu-id="affc6-p128">Percentage of “frozen” frames. In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="affc6-289">[<strong>Outbound avg frame rate</strong>]</span><span class="sxs-lookup"><span data-stu-id="affc6-289"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="affc6-290">いいえ</span><span class="sxs-lookup"><span data-stu-id="affc6-290">No</span></span></p></td>
<td><p><span data-ttu-id="affc6-291">通話時の送信の平均フレーム レート。</span><span class="sxs-lookup"><span data-stu-id="affc6-291">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="affc6-292">[<strong>Inbound avg frame rate</strong>]</span><span class="sxs-lookup"><span data-stu-id="affc6-292"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="affc6-293">いいえ</span><span class="sxs-lookup"><span data-stu-id="affc6-293">No</span></span></p></td>
<td><p><span data-ttu-id="affc6-294">通話時の受信の平均フレーム レート。</span><span class="sxs-lookup"><span data-stu-id="affc6-294">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="affc6-295">[<strong>Inbound low frame rate %</strong>]</span><span class="sxs-lookup"><span data-stu-id="affc6-295"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="affc6-296">いいえ</span><span class="sxs-lookup"><span data-stu-id="affc6-296">No</span></span></p></td>
<td><p><span data-ttu-id="affc6-297">着信ビデオのビット レートが低い通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="affc6-297">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="affc6-298">[<strong>Client health %</strong>]</span><span class="sxs-lookup"><span data-stu-id="affc6-298"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="affc6-299">通話時のクライアント デバイスの相対的な正常性を示します。</span><span class="sxs-lookup"><span data-stu-id="affc6-299">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="affc6-300">サーバーパフォーマンスレポートの指標: アプリケーション共有の通話の概要</span><span class="sxs-lookup"><span data-stu-id="affc6-300">Server Performance Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="affc6-301">名前</span><span class="sxs-lookup"><span data-stu-id="affc6-301">Name</span></span></th>
<th><span data-ttu-id="affc6-302">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="affc6-302">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="affc6-303">説明</span><span class="sxs-lookup"><span data-stu-id="affc6-303">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="affc6-304">[<strong>通話の種類/エンドポイントの種類</strong>]</span><span class="sxs-lookup"><span data-stu-id="affc6-304"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="affc6-305">いいえ</span><span class="sxs-lookup"><span data-stu-id="affc6-305">No</span></span></p></td>
<td><p><span data-ttu-id="affc6-p129">この項目をクリックすると、その種類に基づく通話の詳細情報がレポートに表示されます。通話の種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="affc6-p129">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="affc6-308">UC ピアツーピア通話</span><span class="sxs-lookup"><span data-stu-id="affc6-308">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="affc6-309">UC 電話会議セッション</span><span class="sxs-lookup"><span data-stu-id="affc6-309">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="affc6-310">PSTN 電話会議セッション</span><span class="sxs-lookup"><span data-stu-id="affc6-310">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="affc6-311">PSTN 通話: メディアのバイパス</span><span class="sxs-lookup"><span data-stu-id="affc6-311">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="affc6-312">PSTN 通話 (非バイパス): UC レグ</span><span class="sxs-lookup"><span data-stu-id="affc6-312">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="affc6-313">PSTN 通話 (非バイパス): ゲートウェイ レグ</span><span class="sxs-lookup"><span data-stu-id="affc6-313">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="affc6-314">その他の通話の種類</span><span class="sxs-lookup"><span data-stu-id="affc6-314">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="affc6-315">[<strong>通話ボリューム</strong>]</span><span class="sxs-lookup"><span data-stu-id="affc6-315"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="affc6-316">いいえ</span><span class="sxs-lookup"><span data-stu-id="affc6-316">No</span></span></p></td>
<td><p><span data-ttu-id="affc6-317">通話の種類当たりの通話の総数。</span><span class="sxs-lookup"><span data-stu-id="affc6-317">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="affc6-318">[<strong>低品質通話のパーセンテージ</strong>]</span><span class="sxs-lookup"><span data-stu-id="affc6-318"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="affc6-319">いいえ</span><span class="sxs-lookup"><span data-stu-id="affc6-319">No</span></span></p></td>
<td><p><span data-ttu-id="affc6-p130">低品質として分類される通話の総数。低品質通話とは、少なくとも 1 つの測定指標が許容値を超えている通話 (たとえば、過剰なジッターが発生した通話) のことです。</span><span class="sxs-lookup"><span data-stu-id="affc6-p130">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="affc6-322">[<strong>通話ボリューム (ワイヤレス通話)</strong>]</span><span class="sxs-lookup"><span data-stu-id="affc6-322"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="affc6-323">いいえ</span><span class="sxs-lookup"><span data-stu-id="affc6-323">No</span></span></p></td>
<td><p><span data-ttu-id="affc6-324">ワイヤレス接続を使用した通話の総数。</span><span class="sxs-lookup"><span data-stu-id="affc6-324">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="affc6-325">[<strong>通話ボリューム (VPN 通話)</strong>]</span><span class="sxs-lookup"><span data-stu-id="affc6-325"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="affc6-326">いいえ</span><span class="sxs-lookup"><span data-stu-id="affc6-326">No</span></span></p></td>
<td><p><span data-ttu-id="affc6-327">VPN 接続を使用した通話の総数。</span><span class="sxs-lookup"><span data-stu-id="affc6-327">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="affc6-328">[<strong>通話ボリューム (外部通話)</strong>]</span><span class="sxs-lookup"><span data-stu-id="affc6-328"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="affc6-329">いいえ</span><span class="sxs-lookup"><span data-stu-id="affc6-329">No</span></span></p></td>
<td><p><span data-ttu-id="affc6-330">外部接続 (つまり、内部ネットワークの外側の接続) を使用した通話の数。</span><span class="sxs-lookup"><span data-stu-id="affc6-330">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="affc6-331">[<strong>ジッター (ミリ秒)</strong>]</span><span class="sxs-lookup"><span data-stu-id="affc6-331"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="affc6-332">いいえ</span><span class="sxs-lookup"><span data-stu-id="affc6-332">No</span></span></p></td>
<td><p><span data-ttu-id="affc6-333">RTP パケットの着信間に検出された平均ジッター (ジッターとは、通話の "揺れ" の測定値です)。</span><span class="sxs-lookup"><span data-stu-id="affc6-333">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="affc6-334">(ジッターは、通話の&quot;過&quot;の測定値です)。高ジッター値は、通常、混雑または過負荷のメディアサーバーによって発生し、その結果、音声がひずむか失われます。</span><span class="sxs-lookup"><span data-stu-id="affc6-334">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="affc6-335">[<strong>Relative one way delay burst density (ms)</strong>]</span><span class="sxs-lookup"><span data-stu-id="affc6-335"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="affc6-336">いいえ</span><span class="sxs-lookup"><span data-stu-id="affc6-336">No</span></span></p></td>
<td><p><span data-ttu-id="affc6-p132">2 つのメディア エンドポイント間の相対的な一方向の平均遅延。これは、1 ホップの遅延の測定です。</span><span class="sxs-lookup"><span data-stu-id="affc6-p132">Average relative one-way delay between two media endpoints. This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="affc6-339">[<strong>RDP Tile processing latency burst density (ms)</strong>]</span><span class="sxs-lookup"><span data-stu-id="affc6-339"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="affc6-340">いいえ</span><span class="sxs-lookup"><span data-stu-id="affc6-340">No</span></span></p></td>
<td><p><span data-ttu-id="affc6-p133">表示セッション中の AS 会議サーバーでの RDP タイル処理の平均遅延。ネットワーク遅延はこの指標の対象外です。平均値が高いと、表示の際の遅延が大きくなります。過負荷の会議サーバーでは平均遅延が大きくなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="affc6-p133">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session. This metric does not cover network latency. A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="affc6-345">[<strong>損失した合計タイル %</strong>]</span><span class="sxs-lookup"><span data-stu-id="affc6-345"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="affc6-346">いいえ</span><span class="sxs-lookup"><span data-stu-id="affc6-346">No</span></span></p></td>
<td><p><span data-ttu-id="affc6-347">損失した RDP タイル数のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="affc6-347">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

