---
title: Skype for Business Server での監視ダッシュボードの使用
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e00e5783-116f-481f-ad17-3af847d6769a
description: '概要: Skype for Business Server の監視ダッシュボードについて学習します。'
ms.openlocfilehash: 98a96b8a513bad485a25aff76a69d787fb3079b0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827787"
---
# <a name="using-the-monitoring-dashboard-in-skype-for-business-server"></a><span data-ttu-id="48052-103">Skype for Business Server での監視ダッシュボードの使用</span><span class="sxs-lookup"><span data-stu-id="48052-103">Using the Monitoring Dashboard in Skype for Business Server</span></span>
 
<span data-ttu-id="48052-104">**概要:** Skype for Business Server の監視ダッシュボードについて学習します。</span><span class="sxs-lookup"><span data-stu-id="48052-104">**Summary:** Learn about the Monitoring Dashboard in Skype for Business Server.</span></span>
  
<span data-ttu-id="48052-105">監視ダッシュボードを使用すると、管理者は Skype for Business Server のシステム正常性とシステム使用状況の概要を簡単に確認できます。</span><span class="sxs-lookup"><span data-stu-id="48052-105">The Monitoring Dashboard provides administrators with a quick overview of their Skype for Business Server system health and system usage.</span></span> <span data-ttu-id="48052-106">ダッシュボードは、主要なシステム メトリックの集計ビューを表示し、次のいずれかを表示して表示するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="48052-106">The Dashboard is designed to show an aggregate view of key system metrics and to do so by displaying either:</span></span>
  
- <span data-ttu-id="48052-107">現在の日の合計。</span><span class="sxs-lookup"><span data-stu-id="48052-107">Totals for the current day.</span></span> <span data-ttu-id="48052-108">現在の日に表示される値は、(レポート サーバーの現地時刻に基づいて) 午前 0 時から現在の時刻まで記録されたデータを表します。</span><span class="sxs-lookup"><span data-stu-id="48052-108">Note that values shown for the current day represent data that has been recorded from midnight until the current time (based on the local time of the reporting server).</span></span> <span data-ttu-id="48052-109">つまり、通常は 24 時間ではなく、一部の日のデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="48052-109">That means that you will typically be viewing data for a partial day and not for a 24-hour period.</span></span> <span data-ttu-id="48052-110">たとえば、サーバーの現地時刻が午前 8 時の場合、午前 0 時から現在の午前 8 時の間に 8 時間あるため、8 時間分のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="48052-110">For example, if the local time of the server is 8:00 AM, you see eight hours' worth of data because there are eight hours between midnight and the current time of 8:00 AM.</span></span>
    
- <span data-ttu-id="48052-111">週の合計と過去 6 週間の傾向の合計。</span><span class="sxs-lookup"><span data-stu-id="48052-111">Totals for the week, and trend totals for the past six weeks.</span></span>
    
- <span data-ttu-id="48052-112">月の合計と過去 6 か月間の傾向の合計 (システム使用状況のみ)。</span><span class="sxs-lookup"><span data-stu-id="48052-112">Totals for the month, and trend totals for the past six months (for system usage only).</span></span>
    
<span data-ttu-id="48052-113">[Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csreportingconfiguration?view=skype-ps)コマンドレットを使用して、Skype for Business Server 監視レポートへのアクセスに使用する URL を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="48052-113">Note that you can use the [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) cmdlet to return the URL used for accessing Skype for Business Server Monitoring Reports:</span></span>
  
```PowerShell
Get-CsReportingConfiguration
```

<span data-ttu-id="48052-114">既定では、監視ダッシュボードには、現在の週の次の指標 (および過去 6 週間の傾向の合計) のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="48052-114">By default, the Monitoring Dashboard shows data for the following metrics for the current week (and trend totals for the previous six weeks):</span></span>
  
## <a name="system-usage-metrics"></a><span data-ttu-id="48052-115">システム使用状況の指標</span><span class="sxs-lookup"><span data-stu-id="48052-115">System Usage Metrics</span></span>

 <span data-ttu-id="48052-116">**Registration**</span><span class="sxs-lookup"><span data-stu-id="48052-116">**Registration**</span></span>
  
- <span data-ttu-id="48052-117">一意のユーザー ログオン</span><span class="sxs-lookup"><span data-stu-id="48052-117">Unique user logons</span></span>
    
  <span data-ttu-id="48052-118">**ピアツーピア**</span><span class="sxs-lookup"><span data-stu-id="48052-118">**Peer-to-peer**</span></span>
  
- <span data-ttu-id="48052-119">[セッションの合計数]</span><span class="sxs-lookup"><span data-stu-id="48052-119">Total sessions</span></span>
    
- <span data-ttu-id="48052-120">IM セッション</span><span class="sxs-lookup"><span data-stu-id="48052-120">IM sessions</span></span>
    
- <span data-ttu-id="48052-121">オーディオ セッション</span><span class="sxs-lookup"><span data-stu-id="48052-121">Audio sessions</span></span>
    
- <span data-ttu-id="48052-122">ビデオ セッション</span><span class="sxs-lookup"><span data-stu-id="48052-122">Video sessions</span></span>
    
- <span data-ttu-id="48052-123">アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="48052-123">Application sharing</span></span>
    
- <span data-ttu-id="48052-124">音声セッションの合計時間 (分)</span><span class="sxs-lookup"><span data-stu-id="48052-124">Total audio session minutes</span></span>
    
- <span data-ttu-id="48052-125">音声セッションの平均時間 (分)</span><span class="sxs-lookup"><span data-stu-id="48052-125">Avg. audio session minutes</span></span>
    
  <span data-ttu-id="48052-126">**Conference**</span><span class="sxs-lookup"><span data-stu-id="48052-126">**Conference**</span></span>
  
- <span data-ttu-id="48052-127">電話会議の合計数</span><span class="sxs-lookup"><span data-stu-id="48052-127">Total conferences</span></span>
    
- <span data-ttu-id="48052-128">IM 会議</span><span class="sxs-lookup"><span data-stu-id="48052-128">IM conferences</span></span>
    
- <span data-ttu-id="48052-129">A/V 会議</span><span class="sxs-lookup"><span data-stu-id="48052-129">A/V conferences</span></span>
    
- <span data-ttu-id="48052-130">アプリケーション共有会議</span><span class="sxs-lookup"><span data-stu-id="48052-130">Application sharing conferences</span></span>
    
- <span data-ttu-id="48052-131">Web 会議</span><span class="sxs-lookup"><span data-stu-id="48052-131">Web conferences</span></span>
    
- <span data-ttu-id="48052-132">開催者の総数</span><span class="sxs-lookup"><span data-stu-id="48052-132">Total organizers</span></span>
    
- <span data-ttu-id="48052-133">[音声ビデオ会議の合計時間 (分)]</span><span class="sxs-lookup"><span data-stu-id="48052-133">Total A/V conference minutes</span></span>
    
- <span data-ttu-id="48052-134">平均A/V 会議の時間 (分)</span><span class="sxs-lookup"><span data-stu-id="48052-134">Avg. A/V conference minutes</span></span>
    
- <span data-ttu-id="48052-135">[PSTN 電話会議の合計数]</span><span class="sxs-lookup"><span data-stu-id="48052-135">Total PSTN conferences</span></span>
    
- <span data-ttu-id="48052-136">[PSTN 参加者の合計数]</span><span class="sxs-lookup"><span data-stu-id="48052-136">Total PSTN participants</span></span>
    
- <span data-ttu-id="48052-137">[PSTN 参加者の合計時間 (分)]</span><span class="sxs-lookup"><span data-stu-id="48052-137">Total PSTN participant minutes</span></span>
    
<span data-ttu-id="48052-138">システム使用状況の指標に加えて、次の指標には、現在の日と過去 6 日間 ([週単位の表示] を選択した **場合)** の合計、または [月次ビュー] を選択した場合は現在の週と過去 6 週間の合計が表示 **されます。**</span><span class="sxs-lookup"><span data-stu-id="48052-138">In addition to the System Usage metrics, the following metrics displays total for the current day and the previous six days (if you select **Weekly View**) or for the current week and the past six weeks if you select **Monthly View**.</span></span>
  
## <a name="per-user-call-diagnostics"></a><span data-ttu-id="48052-139">Per-User通話診断</span><span class="sxs-lookup"><span data-stu-id="48052-139">Per-User Call Diagnostics</span></span>

 <span data-ttu-id="48052-140">**通話エラーが発生したユーザー**</span><span class="sxs-lookup"><span data-stu-id="48052-140">**Users with call failures**</span></span>
  
- <span data-ttu-id="48052-141">通話エラーが発生したユーザーの総数</span><span class="sxs-lookup"><span data-stu-id="48052-141">Total users with call failures</span></span>
    
- <span data-ttu-id="48052-142">通話エラーが発生した電話会議の開催者</span><span class="sxs-lookup"><span data-stu-id="48052-142">Conference organizers with call failures</span></span>
    
  <span data-ttu-id="48052-143">**低品質通話のユーザー**</span><span class="sxs-lookup"><span data-stu-id="48052-143">**Users with poor quality calls**</span></span>
  
- <span data-ttu-id="48052-144">低品質通話のユーザーの総数</span><span class="sxs-lookup"><span data-stu-id="48052-144">Total users with poor quality calls</span></span>
    
## <a name="call-diagnostics"></a><span data-ttu-id="48052-145">通話診断</span><span class="sxs-lookup"><span data-stu-id="48052-145">Call Diagnostics</span></span>

<span data-ttu-id="48052-146">ピアツーピア</span><span class="sxs-lookup"><span data-stu-id="48052-146">Peer-to-peer</span></span>
  
- <span data-ttu-id="48052-147">Total failures</span><span class="sxs-lookup"><span data-stu-id="48052-147">Total failures</span></span>
    
- <span data-ttu-id="48052-148">全体的なエラー率</span><span class="sxs-lookup"><span data-stu-id="48052-148">Overall failure rate</span></span>
    
- <span data-ttu-id="48052-149">IM エラー率</span><span class="sxs-lookup"><span data-stu-id="48052-149">IM failure rate</span></span>
    
- <span data-ttu-id="48052-150">オーディオエラー率</span><span class="sxs-lookup"><span data-stu-id="48052-150">Audio failure rate</span></span>
    
- <span data-ttu-id="48052-151">アプリケーション共有エラー率</span><span class="sxs-lookup"><span data-stu-id="48052-151">Application sharing failure rate</span></span>
    
<span data-ttu-id="48052-152">Conference</span><span class="sxs-lookup"><span data-stu-id="48052-152">Conference</span></span>
  
- <span data-ttu-id="48052-153">Total failures</span><span class="sxs-lookup"><span data-stu-id="48052-153">Total failures</span></span>
    
- <span data-ttu-id="48052-154">全体的なエラー率</span><span class="sxs-lookup"><span data-stu-id="48052-154">Overall failure rate</span></span>
    
- <span data-ttu-id="48052-155">IM エラー率</span><span class="sxs-lookup"><span data-stu-id="48052-155">IM failure rate</span></span>
    
- <span data-ttu-id="48052-156">A/V エラー率</span><span class="sxs-lookup"><span data-stu-id="48052-156">A/V failure rate</span></span>
    
- <span data-ttu-id="48052-157">アプリケーション共有エラー率</span><span class="sxs-lookup"><span data-stu-id="48052-157">Application sharing failure rate</span></span>
    
<span data-ttu-id="48052-158">失敗したセッション別の上位 5 サーバー</span><span class="sxs-lookup"><span data-stu-id="48052-158">Top five servers by failed sessions</span></span>
  
## <a name="media-quality-diagnostics"></a><span data-ttu-id="48052-159">メディア品質診断</span><span class="sxs-lookup"><span data-stu-id="48052-159">Media Quality Diagnostics</span></span>

<span data-ttu-id="48052-160">ピアツーピア</span><span class="sxs-lookup"><span data-stu-id="48052-160">Peer-to-peer</span></span>
  
- <span data-ttu-id="48052-161">低品質通話の合計</span><span class="sxs-lookup"><span data-stu-id="48052-161">Total poor quality calls</span></span>
    
- <span data-ttu-id="48052-162">低品質通話のパーセンテージ</span><span class="sxs-lookup"><span data-stu-id="48052-162">Poor quality call percentage</span></span>
    
- <span data-ttu-id="48052-163">低品質の PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="48052-163">PSTN calls with poor quality</span></span>
    
<span data-ttu-id="48052-164">Conference</span><span class="sxs-lookup"><span data-stu-id="48052-164">Conference</span></span>
  
- <span data-ttu-id="48052-165">低品質通話の合計</span><span class="sxs-lookup"><span data-stu-id="48052-165">Total poor quality calls</span></span>
    
- <span data-ttu-id="48052-166">低品質通話のパーセンテージ</span><span class="sxs-lookup"><span data-stu-id="48052-166">Poor quality call percentage</span></span>
    
- <span data-ttu-id="48052-167">低品質の PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="48052-167">PSTN calls with poor quality</span></span>
    
<span data-ttu-id="48052-168">低品質通話率の最も低いサーバー</span><span class="sxs-lookup"><span data-stu-id="48052-168">Top worst servers by poor quality call percentage</span></span>
  
## <a name="working-with-the-monitoring-dashboard"></a><span data-ttu-id="48052-169">監視ダッシュボードの操作</span><span class="sxs-lookup"><span data-stu-id="48052-169">Working with the Monitoring Dashboard</span></span>

<span data-ttu-id="48052-170">上記のように、既定では、現在の週の合計が表示され、過去 6 週間の傾向値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="48052-170">As noted, by default totals are shown for the current week and trend values are shown for the past six weeks.</span></span> <span data-ttu-id="48052-171">現在の月の合計 (および過去 6 か月間の傾向値) を表示する場合は、ダッシュボードの右上隅にある [月次ビュー] リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="48052-171">If you would prefer to see totals for the current month (as well as trend values for the past six months), click the **Monthly View** link in the upper right corner of the dashboard.</span></span> <span data-ttu-id="48052-172">If you decide to view monthly totals, the link text will change to **Weekly View**.</span><span class="sxs-lookup"><span data-stu-id="48052-172">If you decide to view monthly totals, the link text will change to **Weekly View**.</span></span> <span data-ttu-id="48052-173">そのリンクをクリックすると、週次表示に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="48052-173">You can switch back to the weekly view by clicking that link.</span></span>
  
> [!TIP]
> <span data-ttu-id="48052-174">監視ダッシュボードでは、現在の週 (または月) の合計と過去 6 週間 (または月) の傾向値の表示が制限されます。</span><span class="sxs-lookup"><span data-stu-id="48052-174">The Monitoring Dashboard restricts you to looking at totals for the current week (or month) and trend values for the past six weeks (or months).</span></span> <span data-ttu-id="48052-175">これらの日付と時刻は変更できません。</span><span class="sxs-lookup"><span data-stu-id="48052-175">You cannot change these dates and times.</span></span> <span data-ttu-id="48052-176">たとえば、ダッシュボードを使用して、9 か月前から始まる期間のレポートの合計を表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="48052-176">For example, you cannot use the Dashboard to view report totals for the time period beginning nine months ago.</span></span> 
  
<span data-ttu-id="48052-177">今週、今月、または **今日** の列に表示される値は、アイテムに関する詳細な情報にリンクしています。</span><span class="sxs-lookup"><span data-stu-id="48052-177">The values shown in the **This week**, **This month**, or **Today** columns link you to more detailed information about the item.</span></span> <span data-ttu-id="48052-178">多くの場合、列名と列に表示される値は、選択した指標や、週ビューと月次ビューの選択によって異なることがあります。</span><span class="sxs-lookup"><span data-stu-id="48052-178">Keep in mind that the column name and the values displayed in that column will often differ depending on the metric chosen and depending on whether you have selected weekly view or monthly view.</span></span> <span data-ttu-id="48052-179">たとえば、[一意のユーザー ログオン数] 指標に表示される合計をクリックすると、指定した期間のユーザー登録レポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="48052-179">For example, if you click the totals shown for the **Unique user logons** metric you will see the **User Registration Report** for the specified time period.</span></span> <span data-ttu-id="48052-180">[ダッシュボード] をクリックすると、いつでも監視ダッシュボードに戻 **ることができます**。</span><span class="sxs-lookup"><span data-stu-id="48052-180">You can return to the Monitoring Dashboard at any time by clicking **Dashboard**.</span></span>
  
> [!TIP]
> <span data-ttu-id="48052-181">ダッシュボードの右上隅にある [レポート] リンクをクリックして、監視サーバー レポートのホーム ページにアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="48052-181">You can also access the Monitoring Server Reports home page by clicking the **Reports** link in the upper right corner of the Dashboard.</span></span>
  
<span data-ttu-id="48052-182">[ **傾向** ] 列には、過去 6 週間の合計 (または、指標と時間間隔に応じて、過去 6 日間または過去 6 か月) を示す単純な線グラフが表示されます。</span><span class="sxs-lookup"><span data-stu-id="48052-182">The **Trend** column displays a simple line graph that shows totals for the past six weeks (or, depending on the metric and the time interval, the past six days or the past six months).</span></span> <span data-ttu-id="48052-183">これらの単純な線グラフには、期間ごとに 1 つのラベルのないデータ ポイントが表示されます (たとえば、過去 6 週間ごとに 1 つのラベルのないデータ ポイント)。</span><span class="sxs-lookup"><span data-stu-id="48052-183">These simple line graphs display one unlabeled data point for each time period (for example, one unlabeled data point for each of the past six weeks).</span></span> <span data-ttu-id="48052-184">ただし、マウス ポインターをグラフの上に置き、これらのグラフの実際の値を取得できます。</span><span class="sxs-lookup"><span data-stu-id="48052-184">However, you can retrieve actual values for these graphs by holding your mouse pointer over the graph.</span></span> <span data-ttu-id="48052-185">その場合、ツール ヒントにはグラフの最大値と最小値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="48052-185">In that case, a tool tip shows you the maximum and minimum values in the graph.</span></span>
  
## <a name="exporting-data-from-the-monitoring-dashboard"></a><span data-ttu-id="48052-186">監視ダッシュボードからのデータのエクスポート</span><span class="sxs-lookup"><span data-stu-id="48052-186">Exporting Data from the Monitoring Dashboard</span></span>

<span data-ttu-id="48052-187">監視ダッシュボードには、現在のダッシュボード ビューをエクスポートするさまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="48052-187">The Monitoring Dashboard provides a number of ways to export the current dashboard view.</span></span> <span data-ttu-id="48052-188">[ダッシュボード] ツール バーには、緑の矢印が付いているフロッピー ディスクのようなアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="48052-188">On the Dashboard toolbar, you'll see an icon that looks like a floppy disk with a green arrow attached to it.</span></span> <span data-ttu-id="48052-189">このアイコンをクリックすると、ドロップダウン リストが表示され、次のデータ エクスポート形式が表示されます。</span><span class="sxs-lookup"><span data-stu-id="48052-189">If you click this icon, a dropdown list will appear giving you the following data export formats:</span></span>
  
- <span data-ttu-id="48052-190">レポート データが含まれている XML ファイル</span><span class="sxs-lookup"><span data-stu-id="48052-190">XML file with report data</span></span>
    
- <span data-ttu-id="48052-191">CSV (コンマ区切り)</span><span class="sxs-lookup"><span data-stu-id="48052-191">CSV (comma delimited)</span></span>
    
- <span data-ttu-id="48052-192">PDF</span><span class="sxs-lookup"><span data-stu-id="48052-192">PDF</span></span>
    
- <span data-ttu-id="48052-193">MHTML (Web アーカイブ)</span><span class="sxs-lookup"><span data-stu-id="48052-193">MHTML (web archive)</span></span>
    
- <span data-ttu-id="48052-194">Excel</span><span class="sxs-lookup"><span data-stu-id="48052-194">Excel</span></span>
    
- <span data-ttu-id="48052-195">TIFF ファイル</span><span class="sxs-lookup"><span data-stu-id="48052-195">TIFF file</span></span>
    
- <span data-ttu-id="48052-196">Word</span><span class="sxs-lookup"><span data-stu-id="48052-196">Word</span></span>
    
<span data-ttu-id="48052-197">現在のダッシュボード ビュー (とその値) をエクスポートするには、目的のエクスポート オプションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="48052-197">To export the current dashboard view (and its values), click the desired export option.</span></span> <span data-ttu-id="48052-198">Skype for Business Server は、指定された形式でレポートを生成し、そのレポートを開く、または保存するオプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="48052-198">Skype for Business Server generates a report in the specified format and then give you the option of opening that report or saving it.</span></span> <span data-ttu-id="48052-199">既定では、Skype for Business Server はレポート監視ダッシュボードにタイトルを付け、ダウンロード フォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="48052-199">Note that, by default, Skype for Business Server titles the report **Monitoring Dashboard** and saves it to your Downloads folder.</span></span> <span data-ttu-id="48052-200">レポートに別の名前を付け、別のフォルダーに保存するには、[保存] ボタンの横にある矢印をクリックし、[名前を付けて保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="48052-200">To give the report a different name or to store it in a different folder, click the arrow next to the **Save** button and then click **Save As**.</span></span> <span data-ttu-id="48052-201">監視ダッシュボードという名前で、レポートを Downloads フォルダーに保存する場合は、[保存] ボタンを **クリック** します。</span><span class="sxs-lookup"><span data-stu-id="48052-201">If you are fine with name **Monitoring Dashboard** and with having the report saved in the Downloads folder you can just click the **Save** button.</span></span>
  
<span data-ttu-id="48052-202">ダッシュボード データをエクスポートしようとするときに、[セキュリティの警告] ダイアログボックスが "現在の設定では、このファイルのダウンロードを許可していない" というメッセージと共に表示される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="48052-202">It's possible that, when you try to export dashboard data, a **Security Alert** dialog box will appear along with the message "Your current settings do not allow this file to be downloaded."</span></span> <span data-ttu-id="48052-203">この場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="48052-203">If that occurs, do the following:</span></span>
  
- <span data-ttu-id="48052-204">In Internet Explorer, select **Internet Options**.</span><span class="sxs-lookup"><span data-stu-id="48052-204">In Internet Explorer, select **Internet Options**.</span></span>
    
- <span data-ttu-id="48052-205">[インターネット オプション]**ダイアログ** ボックスの [セキュリティ] タブで、[信頼済みサイト] をクリックし、[サイト] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="48052-205">In the **Internet Options** dialog box, on the **Security** tab, click **Trusted sites** and then click **Sites**.</span></span>
    
- <span data-ttu-id="48052-206">[信頼済 **み** サイト] ダイアログボックスで、[追加] をクリックして、Skype for Business Server レポートを実行している Skype for Business Server を信頼済み Web サイトのコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="48052-206">In the **Trusted sites** dialog box, click **Add** to add the Skype for Business Server that is running Skype for Business Server Reports to the collections of trusted websites.</span></span>
    
- <span data-ttu-id="48052-207">[閉 **じる] を** クリックし **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="48052-207">Click **Close** and then click **OK**.</span></span>
    
<span data-ttu-id="48052-208">変更を有効にする前に、監視ダッシュボードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="48052-208">You will then need to refresh the Monitoring Dashboard before the changes take effect.</span></span> <span data-ttu-id="48052-209">これを行うには、F5 キーを押すか、[ダッシュボード] ツールバーの **[最新** の情報に更新] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="48052-209">To do that, either press F5 or click the **Refresh** icon in the Dashboard toolbar.</span></span> <span data-ttu-id="48052-210">([ **最新の情報** に更新] アイコンは、緑色の矢印のペアが含む円です)。</span><span class="sxs-lookup"><span data-stu-id="48052-210">(The **Refresh** icon is a circle with a pair of green arrows in it.)</span></span>
  
<span data-ttu-id="48052-211">最新の監視ダッシュボード データへのリンクを含むライブ データ フィードを含む Excel スプレッドシートを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="48052-211">You can also create an Excel spreadsheet that includes live data feeds, which includes links to the latest Monitoring Dashboard data.</span></span> <span data-ttu-id="48052-212">ライブ データ フィード ファイルを作成するには、ツールバーのオレンジ色の [データ フィードにエクスポート] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="48052-212">To create a live data feed file, click the orange **Export to Data Feed** icon in the toolbar.</span></span>
  
<span data-ttu-id="48052-213">現在のダッシュボードを印刷する場合は、ツール バーのプリンター アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="48052-213">If you would prefer to print the current Dashboard then click the printer icon in the toolbar.</span></span>
  

