---
title: 'Lync Server 2013: サーバーパフォーマンスレポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server Performance Report
ms:assetid: 942bb39a-1790-498e-9d99-8f6ce2d155c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615018(v=OCS.15)
ms:contentKeyID: 48184879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c5a08104f33fc07d6a0ec1c3241a7f14fa1227a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822378"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-performance-report-in-lync-server-2013"></a><span data-ttu-id="a7373-102">Lync Server 2013 のサーバーパフォーマンスレポート</span><span class="sxs-lookup"><span data-stu-id="a7373-102">Server Performance Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7373-103">_**最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="a7373-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="a7373-104">サーバーパフォーマンスレポートには、高品質の通話が低割合で発生している Microsoft Lync Server 2013 サーバーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7373-104">The Server Performance Report provides a list of Microsoft Lync Server 2013 servers that have experienced the highest-percentage of poor calls.</span></span> <span data-ttu-id="a7373-105">このレポートでは、サーバーが種類ごとに分類され、以下の種類のサーバーの個別の統計情報が報告されます。</span><span class="sxs-lookup"><span data-stu-id="a7373-105">The report breaks down servers by server type, reporting separate statistics for the following types:</span></span>

  - <span data-ttu-id="a7373-106">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="a7373-106">Mediation Server</span></span>

  - <span data-ttu-id="a7373-107">音声ビデオ会議サーバー</span><span class="sxs-lookup"><span data-stu-id="a7373-107">A/V Conferencing Server</span></span>

  - <span data-ttu-id="a7373-108">音声ビデオ エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="a7373-108">A/V Edge Server</span></span>

  - <span data-ttu-id="a7373-109">ゲートウェイ (仲介サーバー)</span><span class="sxs-lookup"><span data-stu-id="a7373-109">Gateway (Mediation Server)</span></span>

  - <span data-ttu-id="a7373-110">ゲートウェイ (仲介サーバーのバイパス)</span><span class="sxs-lookup"><span data-stu-id="a7373-110">Gateway (Mediation Server bypass)</span></span>

  - <span data-ttu-id="a7373-111">ビデオ (音声ビデオ会議サーバーと音声ビデオ エッジ サーバーのビデオ指標を含む)</span><span class="sxs-lookup"><span data-stu-id="a7373-111">Video (including video metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

  - <span data-ttu-id="a7373-112">アプリケーション共有 (音声ビデオ会議サーバーと音声ビデオ エッジ サーバーのアプリケーション共有指標を含む)</span><span class="sxs-lookup"><span data-stu-id="a7373-112">Application Sharing (including application sharing metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

<span data-ttu-id="a7373-p102">このレポートに表示されるランク付けは相対的なランク付けであることに注意してください。たとえば、最もパフォーマンスの低いサーバーで発信された 1,000 件の通話のうち、低品質通話が 1 件あったとします。この場合、容認可能な低品質通話のパーセンテージは 0.1% です。しかし、それが最もパフォーマンスの低いサーバーである場合 (つまり、他のすべてのサーバーの低品質通話のパーセンテージが 0.1% 未満の場合)、そのサーバーは引き続きサーバー パフォーマンス レポートに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7373-p102">It’s important to note that the ranking shown in this report as relative rankings. For example, suppose your worst-performing server had one poor call among its 1,000 placed calls. That's a more-than-acceptable percentage of .1%. However, if that's the worst-performing server you have (that is, if all your other servers have a poor call percentage even lower than .1%), then that server will still appear on the Server Performance Report.</span></span>

<div>

## <a name="accessing-the-server-performance-report"></a><span data-ttu-id="a7373-117">サーバー パフォーマンス レポートへのアクセス</span><span class="sxs-lookup"><span data-stu-id="a7373-117">Accessing the Server Performance Report</span></span>

<span data-ttu-id="a7373-118">サーバー パフォーマンス レポートには、監視レポートのホーム ページからアクセスします。</span><span class="sxs-lookup"><span data-stu-id="a7373-118">The Server Performance Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="a7373-119">次の指標のいずれかをクリックして、 [Lync Server 2013 の通話リストレポート](lync-server-2013-call-list-report.md)にドリルダウンすることができます。</span><span class="sxs-lookup"><span data-stu-id="a7373-119">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="a7373-120">通話ボリューム</span><span class="sxs-lookup"><span data-stu-id="a7373-120">Call volume</span></span>

  - <span data-ttu-id="a7373-121">低品質通話のパーセンテージ</span><span class="sxs-lookup"><span data-stu-id="a7373-121">Poor call percentage</span></span>

<span data-ttu-id="a7373-122">また、次の指標をクリックして、サーバー メディア品質傾向レポートにドリルダウンすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a7373-122">In addition, you can drill down to the Server Media Quality Trend Report by clicking the following metric:</span></span>

  - <span data-ttu-id="a7373-123">傾向</span><span class="sxs-lookup"><span data-stu-id="a7373-123">Trend</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-server-performance-report"></a><span data-ttu-id="a7373-124">サーバーパフォーマンスレポートを最大限に活用する</span><span class="sxs-lookup"><span data-stu-id="a7373-124">Making the Best Use of the Server Performance Report</span></span>

<span data-ttu-id="a7373-p104">サーバー パフォーマンス レポートには、データをフィルター処理する方法が複数用意されています。たとえば、ネットワークの種類 (有線接続で行われた通話とワイヤレス接続で行われた通話) やアクセスの種類 (ファイヤウォールの内側から行われた通話とファイヤウォールの外側から行われた通話) でフィルター処理することができます。サーバー パフォーマンス レポートを表示するときは、これらのフィルターを利用することをお勧めします。たとえば、低品質通話のパーセンテージが 3.24% の仲介サーバーがあるとします。ワイヤレス通話だけを見ると、同じサーバーの低品質通話のパーセンテージは 20% 近くになっています。つまり、このサーバーのワイヤレス通話には問題がありますが、有線通話に関する問題はなかったため、問題の一部が不明瞭になっていたことがわかります。</span><span class="sxs-lookup"><span data-stu-id="a7373-p104">The Server Performance Report provides a number of ways to filter data; for example, you can filter on network type (calls made from a wired connection vs. calls made from a wireless connection) and access type (calls made from inside the firewall vs. calls made from outside the firewall). It's a good idea when viewing the server performance report to make use of these filters. For example, suppose you have a Mediation Server that has a poor call percentage of 3.24%. If you look solely at wireless calls, that same server might have a poor call percentage approaching 20%. That means that the server was having difficulty with wireless calls, a problem that is partially obscured because the server was not having problems with wired calls.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="a7373-130">フィルター</span><span class="sxs-lookup"><span data-stu-id="a7373-130">Filters</span></span>

<span data-ttu-id="a7373-p105">フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざまな方法で表示したりする方法として利用できます。たとえば、サーバー パフォーマンス レポートでは、返されたデータをサーバーの種類またはネットワークの種類 (有線またはワイヤレス) 別に表示することができます。また、データをグループ化する方法を選択することもできます。この場合は、データが時間、日、週、または月を基準にグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="a7373-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Server Performance Report enables you to do such things as filter the returned data by server type or by network type (that is, wired or wireless). You can also choose how data should be grouped. In this case, data is grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="a7373-135">次の表に、サーバー パフォーマンス レポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="a7373-135">The following table lists the filters that you can use with the Server Performance Report.</span></span>

### <a name="server-performance-report-filters"></a><span data-ttu-id="a7373-136">サーバー パフォーマンス レポートのフィルター</span><span class="sxs-lookup"><span data-stu-id="a7373-136">Server Performance Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a7373-137">名前</span><span class="sxs-lookup"><span data-stu-id="a7373-137">Name</span></span></th>
<th><span data-ttu-id="a7373-138">説明</span><span class="sxs-lookup"><span data-stu-id="a7373-138">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a7373-139"><strong>開始</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-139"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="a7373-p106">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="a7373-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="a7373-142">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="a7373-142">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="a7373-p107">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="a7373-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="a7373-145">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="a7373-145">7/7/2012</span></span></p>
<p><span data-ttu-id="a7373-146">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="a7373-146">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="a7373-147">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="a7373-147">7/3/2012</span></span></p>
<p><span data-ttu-id="a7373-148">一週間は、日曜日から始まり、土曜日で終わるものとします。</span><span class="sxs-lookup"><span data-stu-id="a7373-148">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7373-149"><strong>終了</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-149"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="a7373-p108">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="a7373-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="a7373-152">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="a7373-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="a7373-p109">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="a7373-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="a7373-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="a7373-155">7/7/2012</span></span></p>
<p><span data-ttu-id="a7373-156">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="a7373-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="a7373-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="a7373-157">7/3/2012</span></span></p>
<p><span data-ttu-id="a7373-158">一週間は、日曜日から始まり、土曜日で終わるものとします。</span><span class="sxs-lookup"><span data-stu-id="a7373-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7373-159"><strong>[サーバーの種類]</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-159"><strong>Server type</strong></span></span></p></td>
<td><p><span data-ttu-id="a7373-p110">どのサーバーのパフォーマンスを報告するのか、その対象となるサーバーの種類を示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="a7373-p110">Indicates the type of server whose performance should be reported. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="a7373-162">[すべて]</span><span class="sxs-lookup"><span data-stu-id="a7373-162">[All]</span></span></p></li>
<li><p><span data-ttu-id="a7373-163">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="a7373-163">Mediation Server</span></span></p></li>
<li><p><span data-ttu-id="a7373-164">音声ビデオ会議サーバー</span><span class="sxs-lookup"><span data-stu-id="a7373-164">A/V Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="a7373-165">音声ビデオ エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="a7373-165">A/V Edge Server</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7373-166"><strong>[トップ N]</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-166"><strong>Top N</strong></span></span></p></td>
<td><p><span data-ttu-id="a7373-p111">カテゴリごとに表示するサーバーの個数 (低品質通話のパーセンテージに基づく) を示します。たとえば、[<strong>5</strong>] を選択すると、特にパフォーマンスの低い 5 個のサーバーが表示されます。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="a7373-p111">Indicates the number of servers (based on their poor call percentage) to be displayed in each category. For example, if you select <strong>5</strong> then the five poorest-performing servers are displayed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="a7373-170">[すべて]</span><span class="sxs-lookup"><span data-stu-id="a7373-170">[All]</span></span></p></li>
<li><p><span data-ttu-id="a7373-171">5</span><span class="sxs-lookup"><span data-stu-id="a7373-171">5</span></span></p></li>
<li><p><span data-ttu-id="a7373-172">常用</span><span class="sxs-lookup"><span data-stu-id="a7373-172">10</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7373-173"><strong>[アクセスの種類]</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-173"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="a7373-p112">クライアントが通話時に内部ネットワークにログオンしたか、外部ネットワークにログオンしたかを示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="a7373-p112">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="a7373-176">[すべて]</span><span class="sxs-lookup"><span data-stu-id="a7373-176">[All]</span></span></p></li>
<li><p><span data-ttu-id="a7373-177">内部</span><span class="sxs-lookup"><span data-stu-id="a7373-177">Internal</span></span></p></li>
<li><p><span data-ttu-id="a7373-178">外部</span><span class="sxs-lookup"><span data-stu-id="a7373-178">External</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7373-179"><strong>[ネットワークの種類]</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-179"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="a7373-p113">通話時にクライアントが接続したネットワークの種類を示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="a7373-p113">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="a7373-182">[すべて]</span><span class="sxs-lookup"><span data-stu-id="a7373-182">[All]</span></span></p></li>
<li><p><span data-ttu-id="a7373-183">有線</span><span class="sxs-lookup"><span data-stu-id="a7373-183">Wired</span></span></p></li>
<li><p><span data-ttu-id="a7373-184">ワイヤレス</span><span class="sxs-lookup"><span data-stu-id="a7373-184">Wireless</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7373-185"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-185"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="a7373-p114">通話時に外部クライアントが仮想プライベート ネットワーク (VPN) 接続を使用したかどうかを示します。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="a7373-p114">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="a7373-188">[すべて]</span><span class="sxs-lookup"><span data-stu-id="a7373-188">[All]</span></span></p></li>
<li><p><span data-ttu-id="a7373-189">VPN</span><span class="sxs-lookup"><span data-stu-id="a7373-189">VPN</span></span></p></li>
<li><p><span data-ttu-id="a7373-190">非 VPN</span><span class="sxs-lookup"><span data-stu-id="a7373-190">Non-VPN</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="a7373-191">指標</span><span class="sxs-lookup"><span data-stu-id="a7373-191">Metrics</span></span>

<span data-ttu-id="a7373-192">次の表に、サーバー パフォーマンス レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="a7373-192">The following table lists the information provided in the Server Performance Report.</span></span>

### <a name="server-performance-report-metrics-audio-call-summary"></a><span data-ttu-id="a7373-193">サーバー パフォーマンス レポートの指標: 音声通話の概要</span><span class="sxs-lookup"><span data-stu-id="a7373-193">Server Performance Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a7373-194">名前</span><span class="sxs-lookup"><span data-stu-id="a7373-194">Name</span></span></th>
<th><span data-ttu-id="a7373-195">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="a7373-195">Can Sort On</span></span></th>
<th><span data-ttu-id="a7373-196">説明</span><span class="sxs-lookup"><span data-stu-id="a7373-196">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a7373-197"><strong>[サーバー]</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-197"><strong>Server</strong></span></span></p></td>
<td><p><span data-ttu-id="a7373-198">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7373-198">No</span></span></p></td>
<td><p><span data-ttu-id="a7373-199">サーバーの名前/IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="a7373-199">Name/IP address of the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7373-200"><strong>[通話ボリューム]</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-200"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="a7373-201">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7373-201">No</span></span></p></td>
<td><p><span data-ttu-id="a7373-202">通話の総数。</span><span class="sxs-lookup"><span data-stu-id="a7373-202">Total number of calls made.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7373-203"><strong>[低品質通話のパーセンテージ]</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-203"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="a7373-204">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7373-204">No</span></span></p></td>
<td><p><span data-ttu-id="a7373-p115">低品質として分類される通話の総数。低品質通話とは、少なくとも 1 つの測定指標が許容値を超えている通話 (たとえば、過剰なジッターが発生した通話) のことです。</span><span class="sxs-lookup"><span data-stu-id="a7373-p115">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7373-207"><strong>[往復 (ミリ秒)]</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-207"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="a7373-208">はい</span><span class="sxs-lookup"><span data-stu-id="a7373-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="a7373-p116">リアルタイム転送プロトコル (RTP) パケットが別のエンドポイントとの間を往復するのに要する平均時間 (ミリ秒単位)。100 ミリ秒以下の往復時間が許容できる品質と見なされます。</span><span class="sxs-lookup"><span data-stu-id="a7373-p116">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="a7373-p117">この値が高い場合は、国際通話ルーティング、ルーティングの構成ミス、メディア サーバーの過負荷などの原因が考えられます。その結果、双方向のリアルタイムの音声会話が難しくなります。</span><span class="sxs-lookup"><span data-stu-id="a7373-p117">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7373-213"><strong>[低下 (MOS)]</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-213"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="a7373-214">はい</span><span class="sxs-lookup"><span data-stu-id="a7373-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="a7373-215">通話時に発生した平均オピニオン値 (MOS) 低下の平均値。</span><span class="sxs-lookup"><span data-stu-id="a7373-215">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="a7373-216">低下の値範囲は、最低 0.0 から最高 5.0 までとなります。</span><span class="sxs-lookup"><span data-stu-id="a7373-216">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="a7373-217">0.5 以下の値は、許容される低下を表します。</span><span class="sxs-lookup"><span data-stu-id="a7373-217">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="a7373-218">従来、平均オピニオン値は、ユーザーが通話の品質を 1 から 5 の範囲で評価することによって計算されていました。</span><span class="sxs-lookup"><span data-stu-id="a7373-218">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="a7373-219">Lync Server では、監視サーバーは一連のアルゴリズムを使って、ユーザーがどのように通話を評価したかを予測します。</span><span class="sxs-lookup"><span data-stu-id="a7373-219">In Lync Server, the Monitoring Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="a7373-p119">この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーやエンドポイントの過負荷などの原因が考えられます。その結果、音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="a7373-p119">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7373-222"><strong>パケット損失</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-222"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="a7373-223">はい</span><span class="sxs-lookup"><span data-stu-id="a7373-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="a7373-p120">リアルタイム転送プロトコル (RTP) パケット損失の平均レート (パケット損失は、RTP パケット、つまりインターネット経由で音声とビデオを転送するために使われるプロトコルの一種で、パケットが宛先に到達できなかったときに発生します)。この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーの過負荷などの原因が考えられます。パケット損失が発生すると、通常、音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="a7373-p120">Average rate of real-time transport protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7373-227"><strong>[ジッター (ミリ秒)]</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-227"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="a7373-228">可</span><span class="sxs-lookup"><span data-stu-id="a7373-228">Yes</span></span></p></td>
<td><p><span data-ttu-id="a7373-229">RTP パケットの着信間に検出された平均ジッター (ジッターとは、通話の "揺れ" の測定値です)。</span><span class="sxs-lookup"><span data-stu-id="a7373-229">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="a7373-230">(ジッタは、通話の&quot;shakiness&quot;の尺度です)。通常、高ジッターの値は、輻輳または過負荷のメディアサーバーによって発生し、音声が歪むか、失われる原因となります。</span><span class="sxs-lookup"><span data-stu-id="a7373-230">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7373-231"><strong>ヒーラー隠し比率</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-231"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="a7373-232">はい</span><span class="sxs-lookup"><span data-stu-id="a7373-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="a7373-p122">サンプルの合計数に対する隠しオーディオ サンプルの平均比率 (隠しオーディオ サンプルとは、突然遷移を取り除くために使用される手法です。突然遷移は、通常、ネットワーク パケットの削除が原因で発生します)。この値が高い場合は、パケット損失やジッターのために高いレベルで損失の隠蔽が適用されています。その結果、音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="a7373-p122">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7373-235"><strong>ヒーラー引き伸ばし比率</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-235"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="a7373-236">はい</span><span class="sxs-lookup"><span data-stu-id="a7373-236">Yes</span></span></p></td>
<td><p><span data-ttu-id="a7373-p123">サンプルの合計数に対する引き伸ばされたオーディオ サンプルの平均比率 (引き伸ばされたオーディオとは、ネットワーク パケットの削除が検出されたときに通話の品質を維持できるように拡張されたオーディオのことです)。この値が高い場合は、ジッターのために高いレベルでサンプルの引き伸ばしが行われています。その結果、音声が機械のように聞こえたりひずんで聞こえたりします。</span><span class="sxs-lookup"><span data-stu-id="a7373-p123">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7373-239"><strong>ヒーラー圧縮比率</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-239"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="a7373-240">可</span><span class="sxs-lookup"><span data-stu-id="a7373-240">Yes</span></span></p></td>
<td><p><span data-ttu-id="a7373-p124">サンプルの合計数に対する圧縮オーディオ サンプルの平均比率 (圧縮オーディオとは、ネットワーク パケットの削除が検出されたときに通話の品質を維持できるように圧縮されたオーディオのことです)。この値が高い場合は、ジッターのために高いレベルでサンプルの圧縮が行われています。その結果、音声が早送りされたように聞こえたりひずんで聞こえたりします。</span><span class="sxs-lookup"><span data-stu-id="a7373-p124">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-video-call-summary"></a><span data-ttu-id="a7373-243">サーバー パフォーマンス レポートの指標: ビデオ通話の概要</span><span class="sxs-lookup"><span data-stu-id="a7373-243">Server Performance Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a7373-244">名前</span><span class="sxs-lookup"><span data-stu-id="a7373-244">Name</span></span></th>
<th><span data-ttu-id="a7373-245">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="a7373-245">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="a7373-246">説明</span><span class="sxs-lookup"><span data-stu-id="a7373-246">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a7373-247"><strong>[通話の種類/エンドポイントの種類]</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-247"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="a7373-248">不可</span><span class="sxs-lookup"><span data-stu-id="a7373-248">No</span></span></p></td>
<td><p><span data-ttu-id="a7373-p125">この項目をクリックすると、その種類に基づく通話の詳細情報がレポートに表示されます。通話の種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a7373-p125">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="a7373-251">UC ピアツーピア通話</span><span class="sxs-lookup"><span data-stu-id="a7373-251">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="a7373-252">UC 電話会議セッション</span><span class="sxs-lookup"><span data-stu-id="a7373-252">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="a7373-253">PSTN 電話会議セッション</span><span class="sxs-lookup"><span data-stu-id="a7373-253">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="a7373-254">PSTN 通話: メディアのバイパス</span><span class="sxs-lookup"><span data-stu-id="a7373-254">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="a7373-255">PSTN 通話 (非バイパス): UC レグ</span><span class="sxs-lookup"><span data-stu-id="a7373-255">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="a7373-256">PSTN 通話 (非バイパス): ゲートウェイ レグ</span><span class="sxs-lookup"><span data-stu-id="a7373-256">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="a7373-257">その他の通話の種類</span><span class="sxs-lookup"><span data-stu-id="a7373-257">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7373-258"><strong>[通話ボリューム]</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-258"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="a7373-259">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7373-259">No</span></span></p></td>
<td><p><span data-ttu-id="a7373-260">通話の種類あたりの通話の総数。</span><span class="sxs-lookup"><span data-stu-id="a7373-260">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7373-261"><strong>[低品質通話のパーセンテージ]</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-261"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="a7373-262">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7373-262">No</span></span></p></td>
<td><p><span data-ttu-id="a7373-p126">低品質として分類される通話の総数。低品質通話とは、少なくとも 1 つの測定指標が許容値を超えている通話 (たとえば、過剰なジッターが発生した通話) のことです。</span><span class="sxs-lookup"><span data-stu-id="a7373-p126">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7373-265"><strong>[通話ボリューム (ワイヤレス通話)]</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-265"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="a7373-266">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7373-266">No</span></span></p></td>
<td><p><span data-ttu-id="a7373-267">ワイヤレス接続を使用した通話の数。</span><span class="sxs-lookup"><span data-stu-id="a7373-267">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7373-268"><strong>[通話ボリューム (VPN 通話)]</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-268"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="a7373-269">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7373-269">No</span></span></p></td>
<td><p><span data-ttu-id="a7373-270">VPN 接続を使用した通話の数。</span><span class="sxs-lookup"><span data-stu-id="a7373-270">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7373-271"><strong>[通話ボリューム (外部通話)]</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-271"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="a7373-272">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7373-272">No</span></span></p></td>
<td><p><span data-ttu-id="a7373-273">外部接続 (つまり、内部ネットワークの外側の接続) を使用した通話の数。</span><span class="sxs-lookup"><span data-stu-id="a7373-273">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7373-274"><strong>[平均ビット レート (キロビット/秒)]</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-274"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="a7373-275">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7373-275">No</span></span></p></td>
<td><p><span data-ttu-id="a7373-276">平均ビデオ ビット レート (kbps)。</span><span class="sxs-lookup"><span data-stu-id="a7373-276">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7373-277"><strong>[低ビット レート (%)]</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-277"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="a7373-278">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7373-278">No</span></span></p></td>
<td><p><span data-ttu-id="a7373-279">ビット レートが低い通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="a7373-279">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7373-280"><strong>[送信パケット損失]</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-280"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="a7373-281">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7373-281">No</span></span></p></td>
<td><p><span data-ttu-id="a7373-p127">送信パケットのリアルタイム転送プロトコル (RTP) パケット損失 (パケット損失は、RTP パケット、つまりインターネット経由で音声とビデオを転送するために使われるプロトコルの一種で、パケットが宛先に到達できなかったときに発生します)。この値が高い場合は、輻輳、帯域幅の不足、ワイヤレスの輻輳または干渉、メディア サーバーの過負荷などの原因が考えられます。パケット損失が発生すると、通常、音声のひずみや欠落が生じます。</span><span class="sxs-lookup"><span data-stu-id="a7373-p127">Real-Time Transport Protocol (RTP) packet loss for outbound packets. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7373-285"><strong>[フリーズ フレーム %]</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-285"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="a7373-286">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7373-286">No</span></span></p></td>
<td><p><span data-ttu-id="a7373-p128">"フリーズ" フレームのパーセンテージ。フリーズ フレームでは、通話の音声部分が続いていてもビデオの進行が停止します。</span><span class="sxs-lookup"><span data-stu-id="a7373-p128">Percentage of “frozen” frames. In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7373-289"><strong>[送信フレーム率 (平均)]</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-289"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="a7373-290">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7373-290">No</span></span></p></td>
<td><p><span data-ttu-id="a7373-291">通話時の送信の平均フレーム レート。</span><span class="sxs-lookup"><span data-stu-id="a7373-291">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7373-292"><strong>[着信フレーム率 (平均)]</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-292"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="a7373-293">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7373-293">No</span></span></p></td>
<td><p><span data-ttu-id="a7373-294">通話時の受信の平均フレーム レート。</span><span class="sxs-lookup"><span data-stu-id="a7373-294">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7373-295"><strong>[着信フレーム率 (低) (%)]</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-295"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="a7373-296">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7373-296">No</span></span></p></td>
<td><p><span data-ttu-id="a7373-297">着信ビデオのビット レートが低い通話のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="a7373-297">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7373-298"><strong>[クライアントの正常性 (%)]</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-298"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a7373-299">通話時のクライアント デバイスの相対的な正常性を示します。</span><span class="sxs-lookup"><span data-stu-id="a7373-299">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="a7373-300">サーバー パフォーマンス レポートの指標: アプリケーション共有の通話の概要</span><span class="sxs-lookup"><span data-stu-id="a7373-300">Server Performance Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a7373-301">名前</span><span class="sxs-lookup"><span data-stu-id="a7373-301">Name</span></span></th>
<th><span data-ttu-id="a7373-302">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="a7373-302">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="a7373-303">説明</span><span class="sxs-lookup"><span data-stu-id="a7373-303">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a7373-304"><strong>[通話の種類/エンドポイントの種類]</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-304"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="a7373-305">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7373-305">No</span></span></p></td>
<td><p><span data-ttu-id="a7373-p129">この項目をクリックすると、その種類に基づく通話の詳細情報がレポートに表示されます。通話の種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a7373-p129">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="a7373-308">UC ピアツーピア通話</span><span class="sxs-lookup"><span data-stu-id="a7373-308">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="a7373-309">UC 電話会議セッション</span><span class="sxs-lookup"><span data-stu-id="a7373-309">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="a7373-310">PSTN 電話会議セッション</span><span class="sxs-lookup"><span data-stu-id="a7373-310">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="a7373-311">PSTN 通話: メディアのバイパス</span><span class="sxs-lookup"><span data-stu-id="a7373-311">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="a7373-312">PSTN 通話 (非バイパス): UC レグ</span><span class="sxs-lookup"><span data-stu-id="a7373-312">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="a7373-313">PSTN 通話 (非バイパス): ゲートウェイ レグ</span><span class="sxs-lookup"><span data-stu-id="a7373-313">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="a7373-314">その他の通話の種類</span><span class="sxs-lookup"><span data-stu-id="a7373-314">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7373-315"><strong>[通話ボリューム]</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-315"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="a7373-316">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7373-316">No</span></span></p></td>
<td><p><span data-ttu-id="a7373-317">通話の種類あたりの通話の総数。</span><span class="sxs-lookup"><span data-stu-id="a7373-317">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7373-318"><strong>[低品質通話のパーセンテージ]</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-318"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="a7373-319">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7373-319">No</span></span></p></td>
<td><p><span data-ttu-id="a7373-p130">低品質として分類される通話の総数。低品質通話とは、少なくとも 1 つの測定指標が許容値を超えている通話 (たとえば、過剰なジッターが発生した通話) のことです。</span><span class="sxs-lookup"><span data-stu-id="a7373-p130">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7373-322"><strong>[通話ボリューム (ワイヤレス通話)]</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-322"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="a7373-323">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7373-323">No</span></span></p></td>
<td><p><span data-ttu-id="a7373-324">ワイヤレス接続を使用した通話の数。</span><span class="sxs-lookup"><span data-stu-id="a7373-324">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7373-325"><strong>[通話ボリューム (VPN 通話)]</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-325"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="a7373-326">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7373-326">No</span></span></p></td>
<td><p><span data-ttu-id="a7373-327">VPN 接続を使用した通話の数。</span><span class="sxs-lookup"><span data-stu-id="a7373-327">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7373-328"><strong>[通話ボリューム (外部通話)]</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-328"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="a7373-329">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7373-329">No</span></span></p></td>
<td><p><span data-ttu-id="a7373-330">外部接続 (つまり、内部ネットワークの外側の接続) を使用した通話の数。</span><span class="sxs-lookup"><span data-stu-id="a7373-330">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7373-331"><strong>[ジッター (ミリ秒)]</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-331"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="a7373-332">不可</span><span class="sxs-lookup"><span data-stu-id="a7373-332">No</span></span></p></td>
<td><p><span data-ttu-id="a7373-333">RTP パケットの着信間に検出された平均ジッター (ジッターとは、通話の "揺れ" の測定値です)。</span><span class="sxs-lookup"><span data-stu-id="a7373-333">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="a7373-334">(ジッタは、通話の&quot;shakiness&quot;の尺度です)。通常、高ジッターの値は、輻輳または過負荷のメディアサーバーによって発生し、音声が歪むか、失われる原因となります。</span><span class="sxs-lookup"><span data-stu-id="a7373-334">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7373-335"><strong>[平均相対的一方向]</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-335"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="a7373-336">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7373-336">No</span></span></p></td>
<td><p><span data-ttu-id="a7373-p132">2 つのメディア エンドポイント間の相対的な一方向の平均遅延。これは 1 ホップの遅延の測定です。</span><span class="sxs-lookup"><span data-stu-id="a7373-p132">Average relative one-way delay between two media endpoints. This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7373-339"><strong>[RDP タイル処理の平均待機時間]</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-339"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="a7373-340">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7373-340">No</span></span></p></td>
<td><p><span data-ttu-id="a7373-p133">表示セッション中の AS 会議サーバーでの RDP タイル処理の平均待機時間。ネットワーク待機時間はこの指標の対象外です。平均値が高いと、表示の際の遅延が大きくなります。過負荷の会議サーバーでは平均遅延が大きくなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a7373-p133">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session. This metric does not cover network latency. A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7373-345"><strong>[損失した合計タイル %]</strong></span><span class="sxs-lookup"><span data-stu-id="a7373-345"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="a7373-346">不可</span><span class="sxs-lookup"><span data-stu-id="a7373-346">No</span></span></p></td>
<td><p><span data-ttu-id="a7373-347">損失した RDP タイルのパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="a7373-347">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

