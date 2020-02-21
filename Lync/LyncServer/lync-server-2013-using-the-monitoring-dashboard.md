---
title: 'Lync Server 2013: 監視ダッシュボードの使用'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Monitoring Dashboard
ms:assetid: e00e5783-116f-481f-ad17-3af847d6769a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721905(v=OCS.15)
ms:contentKeyID: 49733839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 697023ef7c93191cbe13aa0abf4c175240e70ae9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212563"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-the-monitoring-dashboard-in-lync-server-2013"></a><span data-ttu-id="f8481-102">Lync Server 2013 での監視ダッシュボードの使用</span><span class="sxs-lookup"><span data-stu-id="f8481-102">Using the Monitoring Dashboard in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8481-103">_**トピックの最終更新日:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="f8481-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="f8481-104">監視ダッシュボードでは、管理者が Microsoft Lync Server 2013 のシステム正常性およびシステム使用状況の概要をすばやく表示できます。</span><span class="sxs-lookup"><span data-stu-id="f8481-104">The Monitoring Dashboard provides administrators with a quick overview of their Microsoft Lync Server 2013 system health and system usage.</span></span> <span data-ttu-id="f8481-105">このダッシュボードは、主要なシステム指標の集計ビューを表示するように設計されており、次のいずれかを表示することによって行います。</span><span class="sxs-lookup"><span data-stu-id="f8481-105">The Dashboard is designed to show an aggregate view of key system metrics and to do so by displaying either:</span></span>

  - <span data-ttu-id="f8481-106">現在の日付の合計。</span><span class="sxs-lookup"><span data-stu-id="f8481-106">Totals for the current day.</span></span> <span data-ttu-id="f8481-107">現在の日付に表示されている値は、現在の時刻 (レポートサーバーのローカル時刻に基づいて) まで深夜から録音されたデータを表していることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f8481-107">Note that values shown for the current day represent data that has been recorded from midnight until the current time (based on the local time of the reporting server).</span></span> <span data-ttu-id="f8481-108">これは、通常、24時間の期間ではなく、日付の一部のデータを表示することを意味します。</span><span class="sxs-lookup"><span data-stu-id="f8481-108">That means that you will typically be viewing data for a partial day and not for a 24-hour period.</span></span> <span data-ttu-id="f8481-109">たとえば、サーバーのローカル時刻が 8:00 AM の場合は、午前0時と現在の時刻 8:00 AM の間に8時間あるため、8時間のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8481-109">For example, if the local time of the server is 8:00 AM, you see eight hours’ worth of data because there are eight hours between midnight and the current time of 8:00 AM.</span></span>

  - <span data-ttu-id="f8481-110">週の合計と過去6週間の傾向の合計。</span><span class="sxs-lookup"><span data-stu-id="f8481-110">Totals for the week, and trend totals for the past six weeks.</span></span>

  - <span data-ttu-id="f8481-111">月の合計と過去6か月の傾向の合計 (システム使用状況のみ)。</span><span class="sxs-lookup"><span data-stu-id="f8481-111">Totals for the month, and trend totals for the past six months (for system usage only).</span></span>

<span data-ttu-id="f8481-112">このコマンドレットを使用すると、Lync Server 2013 の監視レポートへのアクセスに使用する URL[を取得でき](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration)ます。</span><span class="sxs-lookup"><span data-stu-id="f8481-112">Note that you can use the [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) cmdlet to return the URL used for accessing Lync Server 2013 Monitoring Reports:</span></span>

    Get-CsReportingConfiguration

<span data-ttu-id="f8481-113">既定では、監視ダッシュボードは現在の週の次の指標 (および過去6週間の傾向の合計) のデータを示しています。</span><span class="sxs-lookup"><span data-stu-id="f8481-113">By default, the Monitoring Dashboard shows data for the following metrics for the current week (and trend totals for the previous six weeks):</span></span>

<div>

## <a name="system-usage-metrics"></a><span data-ttu-id="f8481-114">システム使用状況の指標</span><span class="sxs-lookup"><span data-stu-id="f8481-114">System Usage Metrics</span></span>

<span data-ttu-id="f8481-115">**レジスタ**</span><span class="sxs-lookup"><span data-stu-id="f8481-115">**Registration**</span></span>

  - <span data-ttu-id="f8481-116">一意のユーザーログオン</span><span class="sxs-lookup"><span data-stu-id="f8481-116">Unique user logons</span></span>

<span data-ttu-id="f8481-117">**ピアツーピア**</span><span class="sxs-lookup"><span data-stu-id="f8481-117">**Peer-to-peer**</span></span>

  - <span data-ttu-id="f8481-118">[セッションの合計数]</span><span class="sxs-lookup"><span data-stu-id="f8481-118">Total sessions</span></span>

  - <span data-ttu-id="f8481-119">IM セッション</span><span class="sxs-lookup"><span data-stu-id="f8481-119">IM sessions</span></span>

  - <span data-ttu-id="f8481-120">オーディオセッション</span><span class="sxs-lookup"><span data-stu-id="f8481-120">Audio sessions</span></span>

  - <span data-ttu-id="f8481-121">ビデオセッション</span><span class="sxs-lookup"><span data-stu-id="f8481-121">Video sessions</span></span>

  - <span data-ttu-id="f8481-122">アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="f8481-122">Application sharing</span></span>

  - <span data-ttu-id="f8481-123">オーディオセッションの合計時間 (分)</span><span class="sxs-lookup"><span data-stu-id="f8481-123">Total audio session minutes</span></span>

  - <span data-ttu-id="f8481-124">オーディオセッションの平均時間 (分)</span><span class="sxs-lookup"><span data-stu-id="f8481-124">Avg. audio session minutes</span></span>

<span data-ttu-id="f8481-125">**室**</span><span class="sxs-lookup"><span data-stu-id="f8481-125">**Conference**</span></span>

  - <span data-ttu-id="f8481-126">電話会議の合計数</span><span class="sxs-lookup"><span data-stu-id="f8481-126">Total conferences</span></span>

  - <span data-ttu-id="f8481-127">IM 会議</span><span class="sxs-lookup"><span data-stu-id="f8481-127">IM conferences</span></span>

  - <span data-ttu-id="f8481-128">音声ビデオ会議</span><span class="sxs-lookup"><span data-stu-id="f8481-128">A/V conferences</span></span>

  - <span data-ttu-id="f8481-129">アプリケーション共有会議</span><span class="sxs-lookup"><span data-stu-id="f8481-129">Application sharing conferences</span></span>

  - <span data-ttu-id="f8481-130">Web 会議</span><span class="sxs-lookup"><span data-stu-id="f8481-130">Web conferences</span></span>

  - <span data-ttu-id="f8481-131">開催者の合計数</span><span class="sxs-lookup"><span data-stu-id="f8481-131">Total organizers</span></span>

  - <span data-ttu-id="f8481-132">[音声ビデオ会議の合計時間 (分)]</span><span class="sxs-lookup"><span data-stu-id="f8481-132">Total A/V conference minutes</span></span>

  - <span data-ttu-id="f8481-133">平均.音声ビデオ会議の時間 (分)</span><span class="sxs-lookup"><span data-stu-id="f8481-133">Avg. A/V conference minutes</span></span>

  - <span data-ttu-id="f8481-134">[PSTN 電話会議の合計数]</span><span class="sxs-lookup"><span data-stu-id="f8481-134">Total PSTN conferences</span></span>

  - <span data-ttu-id="f8481-135">[PSTN 参加者の合計数]</span><span class="sxs-lookup"><span data-stu-id="f8481-135">Total PSTN participants</span></span>

  - <span data-ttu-id="f8481-136">[PSTN 参加者の合計時間 (分)]</span><span class="sxs-lookup"><span data-stu-id="f8481-136">Total PSTN participant minutes</span></span>

<span data-ttu-id="f8481-137">システムの使用状況の指標に加えて、次の指標では、現在の日付と過去6日間の合計 ([**週ビュー**] を選択した場合)、または現在の週と過去6週間以内に [**月ビュー**] を選択した場合の合計が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8481-137">In addition to the System Usage metrics, the following metrics displays total for the current day and the previous six days (if you select **Weekly View**) or for the current week and the past six weeks if you select **Monthly View**.</span></span>

</div>

<div>

## <a name="per-user-call-diagnostics"></a><span data-ttu-id="f8481-138">ユーザーごとの通話診断</span><span class="sxs-lookup"><span data-stu-id="f8481-138">Per-User Call Diagnostics</span></span>

<span data-ttu-id="f8481-139">**通話エラーが発生したユーザー**</span><span class="sxs-lookup"><span data-stu-id="f8481-139">**Users with call failures**</span></span>

  - <span data-ttu-id="f8481-140">通話エラーが発生したユーザーの合計数</span><span class="sxs-lookup"><span data-stu-id="f8481-140">Total users with call failures</span></span>

  - <span data-ttu-id="f8481-141">通話エラーが発生した会議開催者</span><span class="sxs-lookup"><span data-stu-id="f8481-141">Conference organizers with call failures</span></span>

<span data-ttu-id="f8481-142">**低品質通話のユーザー**</span><span class="sxs-lookup"><span data-stu-id="f8481-142">**Users with poor quality calls**</span></span>

  - <span data-ttu-id="f8481-143">低品質通話のユーザー総数</span><span class="sxs-lookup"><span data-stu-id="f8481-143">Total users with poor quality calls</span></span>

</div>

<div>

## <a name="call-diagnostics"></a><span data-ttu-id="f8481-144">通話診断</span><span class="sxs-lookup"><span data-stu-id="f8481-144">Call Diagnostics</span></span>

<span data-ttu-id="f8481-145">ピアツーピア</span><span class="sxs-lookup"><span data-stu-id="f8481-145">Peer-to-peer</span></span>

  - <span data-ttu-id="f8481-146">失敗の合計数</span><span class="sxs-lookup"><span data-stu-id="f8481-146">Total failures</span></span>

  - <span data-ttu-id="f8481-147">全体的なエラー率</span><span class="sxs-lookup"><span data-stu-id="f8481-147">Overall failure rate</span></span>

  - <span data-ttu-id="f8481-148">IM エラー率</span><span class="sxs-lookup"><span data-stu-id="f8481-148">IM failure rate</span></span>

  - <span data-ttu-id="f8481-149">音声エラー率</span><span class="sxs-lookup"><span data-stu-id="f8481-149">Audio failure rate</span></span>

  - <span data-ttu-id="f8481-150">アプリケーション共有エラー率</span><span class="sxs-lookup"><span data-stu-id="f8481-150">Application sharing failure rate</span></span>

<span data-ttu-id="f8481-151">室</span><span class="sxs-lookup"><span data-stu-id="f8481-151">Conference</span></span>

  - <span data-ttu-id="f8481-152">失敗の合計数</span><span class="sxs-lookup"><span data-stu-id="f8481-152">Total failures</span></span>

  - <span data-ttu-id="f8481-153">全体的なエラー率</span><span class="sxs-lookup"><span data-stu-id="f8481-153">Overall failure rate</span></span>

  - <span data-ttu-id="f8481-154">IM エラー率</span><span class="sxs-lookup"><span data-stu-id="f8481-154">IM failure rate</span></span>

  - <span data-ttu-id="f8481-155">音声ビデオエラー率</span><span class="sxs-lookup"><span data-stu-id="f8481-155">A/V failure rate</span></span>

  - <span data-ttu-id="f8481-156">アプリケーション共有エラー率</span><span class="sxs-lookup"><span data-stu-id="f8481-156">Application sharing failure rate</span></span>

<span data-ttu-id="f8481-157">セッションが失敗した上位5台のサーバー</span><span class="sxs-lookup"><span data-stu-id="f8481-157">Top five servers by failed sessions</span></span>

</div>

<div>

## <a name="media-quality-diagnostics"></a><span data-ttu-id="f8481-158">メディア品質診断</span><span class="sxs-lookup"><span data-stu-id="f8481-158">Media Quality Diagnostics</span></span>

<span data-ttu-id="f8481-159">ピアツーピア</span><span class="sxs-lookup"><span data-stu-id="f8481-159">Peer-to-peer</span></span>

  - <span data-ttu-id="f8481-160">低品質通話の合計数</span><span class="sxs-lookup"><span data-stu-id="f8481-160">Total poor quality calls</span></span>

  - <span data-ttu-id="f8481-161">低品質通話のパーセンテージ</span><span class="sxs-lookup"><span data-stu-id="f8481-161">Poor quality call percentage</span></span>

  - <span data-ttu-id="f8481-162">低品質の PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="f8481-162">PSTN calls with poor quality</span></span>

<span data-ttu-id="f8481-163">室</span><span class="sxs-lookup"><span data-stu-id="f8481-163">Conference</span></span>

  - <span data-ttu-id="f8481-164">低品質通話の合計数</span><span class="sxs-lookup"><span data-stu-id="f8481-164">Total poor quality calls</span></span>

  - <span data-ttu-id="f8481-165">低品質通話のパーセンテージ</span><span class="sxs-lookup"><span data-stu-id="f8481-165">Poor quality call percentage</span></span>

  - <span data-ttu-id="f8481-166">低品質の PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="f8481-166">PSTN calls with poor quality</span></span>

<span data-ttu-id="f8481-167">低品質通話のパーセンテージによる上位最低サーバー</span><span class="sxs-lookup"><span data-stu-id="f8481-167">Top worst servers by poor quality call percentage</span></span>

</div>

<div>

## <a name="working-with-the-monitoring-dashboard"></a><span data-ttu-id="f8481-168">監視ダッシュボードを使用する</span><span class="sxs-lookup"><span data-stu-id="f8481-168">Working with the Monitoring Dashboard</span></span>

<span data-ttu-id="f8481-169">前述したように、既定では、現在の週の合計が表示され、過去6週間の傾向値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8481-169">As noted, by default totals are shown for the current week and trend values are shown for the past six weeks.</span></span> <span data-ttu-id="f8481-170">現在の月の合計 (および過去6か月の傾向値) を表示する場合は、ダッシュボードの右上隅にある [**月間表示**] リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8481-170">If you would prefer to see totals for the current month (as well as trend values for the past six months), click the **Monthly View** link in the upper right corner of the dashboard.</span></span> <span data-ttu-id="f8481-171">月単位の合計を表示するように設定すると、リンクテキストは [**週] ビュー**に変わります。</span><span class="sxs-lookup"><span data-stu-id="f8481-171">If you decide to view monthly totals, the link text will change to **Weekly View**.</span></span> <span data-ttu-id="f8481-172">そのリンクをクリックすると、[週] ビューに戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="f8481-172">You can switch back to the weekly view by clicking that link.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="f8481-173">監視ダッシュボードでは、現在の週 (または月) の合計と過去6週間 (または数か月) の傾向値を見ることができます。</span><span class="sxs-lookup"><span data-stu-id="f8481-173">The Monitoring Dashboard restricts you to looking at totals for the current week (or month) and trend values for the past six weeks (or months).</span></span> <span data-ttu-id="f8481-174">これらの日付と時刻は変更できません。</span><span class="sxs-lookup"><span data-stu-id="f8481-174">You cannot change these dates and times.</span></span> <span data-ttu-id="f8481-175">たとえば、ダッシュボードを使用して、9か月前に開始された期間のレポートの合計を表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="f8481-175">For example, you cannot use the Dashboard to view report totals for the time period beginning nine months ago.</span></span>



</div>

<span data-ttu-id="f8481-176">**今週**、**今月**、または**今日**の列に表示されている値は、アイテムに関する詳細情報にリンクしています。</span><span class="sxs-lookup"><span data-stu-id="f8481-176">The values shown in the **This week**, **This month**, or **Today** columns link you to more detailed information about the item.</span></span> <span data-ttu-id="f8481-177">列名と列に表示される値は、多くの場合、選択された指標と、[週ビュー] または [月] ビューのどちらを選択したかによって異なることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f8481-177">Keep in mind that the column name and the values displayed in that column will often differ depending on the metric chosen and depending on whether you have selected weekly view or monthly view.</span></span> <span data-ttu-id="f8481-178">たとえば、**一意のユーザーログオン**指標に表示されている合計をクリックすると、指定した期間の**ユーザー登録レポート**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8481-178">For example, if you click the totals shown for the **Unique user logons** metric you will see the **User Registration Report** for the specified time period.</span></span> <span data-ttu-id="f8481-179">[**ダッシュボード**] をクリックすると、いつでも監視ダッシュボードに戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="f8481-179">You can return to the Monitoring Dashboard at any time by clicking **Dashboard**.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="f8481-180">ダッシュボードの右上隅にある [<STRONG>レポート</STRONG>] リンクをクリックして、監視サーバーレポートのホームページにアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f8481-180">You can also access the Monitoring Server Reports home page by clicking the <STRONG>Reports</STRONG> link in the upper right corner of the Dashboard.</span></span>



</div>

<span data-ttu-id="f8481-181">[**傾向**] 列には、過去6週間 (または、指標と時間間隔、過去6日間または過去6か月に応じて) の合計を示す単純な折れ線グラフが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8481-181">The **Trend** column displays a simple line graph that shows totals for the past six weeks (or, depending on the metric and the time interval, the past six days or the past six months).</span></span> <span data-ttu-id="f8481-182">これらの単純な線グラフでは、各期間に1つのラベルのないデータポイントが表示されます (たとえば、過去6週間ごとに1つのラベルのないデータポイントが表示されます)。</span><span class="sxs-lookup"><span data-stu-id="f8481-182">These simple line graphs display one unlabeled data point for each time period (for example, one unlabeled data point for each of the past six weeks).</span></span> <span data-ttu-id="f8481-183">ただし、グラフの上にマウスポインターを置くと、これらのグラフの実績値を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="f8481-183">However, you can retrieve actual values for these graphs by holding your mouse pointer over the graph.</span></span> <span data-ttu-id="f8481-184">その場合は、グラフの最大値と最小値がヒントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8481-184">In that case, a tooltip shows you the maximum and minimum values in the graph.</span></span>

</div>

<div>

## <a name="exporting-data-from-the-monitoring-dashboard"></a><span data-ttu-id="f8481-185">監視ダッシュボードからのデータのエクスポート</span><span class="sxs-lookup"><span data-stu-id="f8481-185">Exporting Data from the Monitoring Dashboard</span></span>

<span data-ttu-id="f8481-186">監視ダッシュボードには、現在のダッシュボードビューをエクスポートする方法がいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="f8481-186">The Monitoring Dashboard provides a number of ways to export the current dashboard view.</span></span> <span data-ttu-id="f8481-187">ダッシュボードのツールバーには、緑色の矢印が付いたフロッピーディスクのように見えるアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8481-187">On the Dashboard toolbar, you'll see an icon that looks like a floppy disk with a green arrow attached to it.</span></span> <span data-ttu-id="f8481-188">このアイコンをクリックすると、次のデータエクスポート形式を提供するドロップダウンリストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8481-188">If you click this icon, a dropdown list will appear giving you the following data export formats:</span></span>

  - <span data-ttu-id="f8481-189">レポート データが含まれている XML ファイル</span><span class="sxs-lookup"><span data-stu-id="f8481-189">XML file with report data</span></span>

  - <span data-ttu-id="f8481-190">CSV (コンマ区切り)</span><span class="sxs-lookup"><span data-stu-id="f8481-190">CSV (comma delimited)</span></span>

  - <span data-ttu-id="f8481-191">PDF</span><span class="sxs-lookup"><span data-stu-id="f8481-191">PDF</span></span>

  - <span data-ttu-id="f8481-192">MHTML (Web アーカイブ)</span><span class="sxs-lookup"><span data-stu-id="f8481-192">MHTML (web archive)</span></span>

  - <span data-ttu-id="f8481-193">Excel</span><span class="sxs-lookup"><span data-stu-id="f8481-193">Excel</span></span>

  - <span data-ttu-id="f8481-194">TIFF ファイル</span><span class="sxs-lookup"><span data-stu-id="f8481-194">TIFF file</span></span>

  - <span data-ttu-id="f8481-195">Word</span><span class="sxs-lookup"><span data-stu-id="f8481-195">Word</span></span>

<span data-ttu-id="f8481-196">現在のダッシュボードビュー (およびその値) をエクスポートするには、目的のエクスポートオプションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8481-196">To export the current dashboard view (and its values), click the desired export option.</span></span> <span data-ttu-id="f8481-197">Lync Server 2013 は、指定された形式でレポートを生成し、レポートを開いたり保存したりするためのオプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="f8481-197">Lync Server 2013 generates a report in the specified format and then give you the option of opening that report or saving it.</span></span> <span data-ttu-id="f8481-198">既定では、Lync Server はレポート**監視ダッシュボード**のタイトルを作成し、それを [ダウンロード] フォルダーに保存することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f8481-198">Note that, by default, Lync Server titles the report **Monitoring Dashboard** and saves it to your Downloads folder.</span></span> <span data-ttu-id="f8481-199">レポートに別の名前を付けるか、または別のフォルダーに保存するには、[**保存**] ボタンの横にある矢印をクリックし、[名前を付け**て保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8481-199">To give the report a different name or to store it in a different folder, click the arrow next to the **Save** button and then click **Save As**.</span></span> <span data-ttu-id="f8481-200">名前**監視ダッシュボード**を使用していて、レポートが [ダウンロード] フォルダーに保存されている場合は、[**保存**] ボタンをクリックするだけで構いません。</span><span class="sxs-lookup"><span data-stu-id="f8481-200">If you are fine with name **Monitoring Dashboard** and with having the report saved in the Downloads folder you can just click the **Save** button.</span></span>

<span data-ttu-id="f8481-201">ダッシュボードデータをエクスポートしようとすると、[**セキュリティの警告**] ダイアログボックスが "現在の設定ではこのファイルをダウンロードできません" というメッセージと共に表示される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f8481-201">It's possible that, when you try to export dashboard data, a **Security Alert** dialog box will appear along with the message "Your current settings do not allow this file to be downloaded."</span></span> <span data-ttu-id="f8481-202">その場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f8481-202">If that occurs, do the following:</span></span>

  - <span data-ttu-id="f8481-203">Internet Explorer で、[**インターネットオプション**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f8481-203">In Internet Explorer, select **Internet Options**.</span></span>

  - <span data-ttu-id="f8481-204">[**インターネットオプション**] ダイアログボックスの [**セキュリティ**] タブで、[**信頼済みサイト**] をクリックし、[**サイト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8481-204">In the **Internet Options** dialog box, on the **Security** tab, click **Trusted sites** and then click **Sites**.</span></span>

  - <span data-ttu-id="f8481-205">[**信頼済みサイト**] ダイアログボックスで、[**追加**] をクリックして、lync server 2013 レポートを実行している lync server 2013 を信頼済み web サイトのコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="f8481-205">In the **Trusted sites** dialog box, click **Add** to add the Lync Server 2013 that is running Lync Server 2013 Reports to the collections of trusted websites.</span></span>

  - <span data-ttu-id="f8481-206">[**閉じる**] をクリックし、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8481-206">Click **Close** and then click **OK**.</span></span>

<span data-ttu-id="f8481-207">変更を有効にするには、監視ダッシュボードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8481-207">You will then need to refresh the Monitoring Dashboard before the changes take effect.</span></span> <span data-ttu-id="f8481-208">これを行うには、F5 キーを押すか、ダッシュボードツールバーの [**更新**] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8481-208">To do that, either press F5 or click the **Refresh** icon in the Dashboard toolbar.</span></span> <span data-ttu-id="f8481-209">(**更新**アイコンは、緑色の矢印のペアがある円です。)</span><span class="sxs-lookup"><span data-stu-id="f8481-209">(The **Refresh** icon is a circle with a pair of green arrows in it.)</span></span>

<span data-ttu-id="f8481-210">また、最新の監視ダッシュボードデータへのリンクを含む、ライブデータフィードを含む Excel スプレッドシートを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="f8481-210">You can also create an Excel spreadsheet that includes live data feeds, which includes links to the latest Monitoring Dashboard data.</span></span> <span data-ttu-id="f8481-211">ライブデータフィードファイルを作成するには、ツールバーの [オレンジ色の**データフィードへのエクスポート**] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8481-211">To create a live data feed file, click the orange **Export to Data Feed** icon in the toolbar.</span></span>

<span data-ttu-id="f8481-212">現在のダッシュボードを印刷したい場合は、ツールバーの [プリンター] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8481-212">If you would prefer to print the current Dashboard then click the printer icon in the toolbar.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

