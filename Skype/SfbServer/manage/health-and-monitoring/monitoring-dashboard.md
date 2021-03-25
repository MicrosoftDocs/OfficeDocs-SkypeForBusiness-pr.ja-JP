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
ms.openlocfilehash: 83a04a60e63deb39666ee4d042f74973b7d16d0b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118606"
---
# <a name="using-the-monitoring-dashboard-in-skype-for-business-server"></a><span data-ttu-id="bedd8-103">Skype for Business Server での監視ダッシュボードの使用</span><span class="sxs-lookup"><span data-stu-id="bedd8-103">Using the Monitoring Dashboard in Skype for Business Server</span></span>
 
<span data-ttu-id="bedd8-104">**概要:** Skype for Business Server の監視ダッシュボードについて学習します。</span><span class="sxs-lookup"><span data-stu-id="bedd8-104">**Summary:** Learn about the Monitoring Dashboard in Skype for Business Server.</span></span>
  
<span data-ttu-id="bedd8-105">監視ダッシュボードを使用すると、管理者は Skype for Business Server システムの正常性とシステム使用状況の概要を簡単に確認できます。</span><span class="sxs-lookup"><span data-stu-id="bedd8-105">The Monitoring Dashboard provides administrators with a quick overview of their Skype for Business Server system health and system usage.</span></span> <span data-ttu-id="bedd8-106">ダッシュボードは、主要なシステム メトリックの集計ビューを表示し、次のいずれかを表示するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="bedd8-106">The Dashboard is designed to show an aggregate view of key system metrics and to do so by displaying either:</span></span>
  
- <span data-ttu-id="bedd8-107">現在の日の合計。</span><span class="sxs-lookup"><span data-stu-id="bedd8-107">Totals for the current day.</span></span> <span data-ttu-id="bedd8-108">現在の日に表示される値は、午前 0 時から現在の時刻 (レポート サーバーの現地時間に基づく) まで記録されたデータを表します。</span><span class="sxs-lookup"><span data-stu-id="bedd8-108">Note that values shown for the current day represent data that has been recorded from midnight until the current time (based on the local time of the reporting server).</span></span> <span data-ttu-id="bedd8-109">つまり、通常は一部の日のデータを表示し、24 時間表示は表示しないという意味です。</span><span class="sxs-lookup"><span data-stu-id="bedd8-109">That means that you will typically be viewing data for a partial day and not for a 24-hour period.</span></span> <span data-ttu-id="bedd8-110">たとえば、サーバーの現地時間が午前 8:00 の場合、午前 0 時から現在の午前 8 時の間に 8 時間あるため、8 時間分のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bedd8-110">For example, if the local time of the server is 8:00 AM, you see eight hours' worth of data because there are eight hours between midnight and the current time of 8:00 AM.</span></span>
    
- <span data-ttu-id="bedd8-111">週の合計と過去 6 週間の傾向の合計。</span><span class="sxs-lookup"><span data-stu-id="bedd8-111">Totals for the week, and trend totals for the past six weeks.</span></span>
    
- <span data-ttu-id="bedd8-112">月の合計と過去 6 か月間の傾向の合計 (システムの使用状況のみ)。</span><span class="sxs-lookup"><span data-stu-id="bedd8-112">Totals for the month, and trend totals for the past six months (for system usage only).</span></span>
    
<span data-ttu-id="bedd8-113">[Get-CsReportingConfiguration](/powershell/module/skype/get-csreportingconfiguration?view=skype-ps)コマンドレットを使用して、Skype for Business Server 監視レポートへのアクセスに使用される URL を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="bedd8-113">Note that you can use the [Get-CsReportingConfiguration](/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) cmdlet to return the URL used for accessing Skype for Business Server Monitoring Reports:</span></span>
  
```PowerShell
Get-CsReportingConfiguration
```

<span data-ttu-id="bedd8-114">既定では、監視ダッシュボードには、現在の週の次の指標 (および過去 6 週間の傾向の合計) のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bedd8-114">By default, the Monitoring Dashboard shows data for the following metrics for the current week (and trend totals for the previous six weeks):</span></span>
  
## <a name="system-usage-metrics"></a><span data-ttu-id="bedd8-115">システム使用状況の指標</span><span class="sxs-lookup"><span data-stu-id="bedd8-115">System Usage Metrics</span></span>

 <span data-ttu-id="bedd8-116">**Registration**</span><span class="sxs-lookup"><span data-stu-id="bedd8-116">**Registration**</span></span>
  
- <span data-ttu-id="bedd8-117">一意のユーザー ログオン</span><span class="sxs-lookup"><span data-stu-id="bedd8-117">Unique user logons</span></span>
    
  <span data-ttu-id="bedd8-118">**ピアツーピア**</span><span class="sxs-lookup"><span data-stu-id="bedd8-118">**Peer-to-peer**</span></span>
  
- <span data-ttu-id="bedd8-119">[セッションの合計数]</span><span class="sxs-lookup"><span data-stu-id="bedd8-119">Total sessions</span></span>
    
- <span data-ttu-id="bedd8-120">IM セッション</span><span class="sxs-lookup"><span data-stu-id="bedd8-120">IM sessions</span></span>
    
- <span data-ttu-id="bedd8-121">オーディオ セッション</span><span class="sxs-lookup"><span data-stu-id="bedd8-121">Audio sessions</span></span>
    
- <span data-ttu-id="bedd8-122">ビデオ セッション</span><span class="sxs-lookup"><span data-stu-id="bedd8-122">Video sessions</span></span>
    
- <span data-ttu-id="bedd8-123">アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="bedd8-123">Application sharing</span></span>
    
- <span data-ttu-id="bedd8-124">オーディオ セッションの合計時間 (分)</span><span class="sxs-lookup"><span data-stu-id="bedd8-124">Total audio session minutes</span></span>
    
- <span data-ttu-id="bedd8-125">Avg. オーディオ セッションの分数</span><span class="sxs-lookup"><span data-stu-id="bedd8-125">Avg. audio session minutes</span></span>
    
  <span data-ttu-id="bedd8-126">**Conference**</span><span class="sxs-lookup"><span data-stu-id="bedd8-126">**Conference**</span></span>
  
- <span data-ttu-id="bedd8-127">電話会議の合計数</span><span class="sxs-lookup"><span data-stu-id="bedd8-127">Total conferences</span></span>
    
- <span data-ttu-id="bedd8-128">IM 会議</span><span class="sxs-lookup"><span data-stu-id="bedd8-128">IM conferences</span></span>
    
- <span data-ttu-id="bedd8-129">A/V 会議</span><span class="sxs-lookup"><span data-stu-id="bedd8-129">A/V conferences</span></span>
    
- <span data-ttu-id="bedd8-130">アプリケーション共有会議</span><span class="sxs-lookup"><span data-stu-id="bedd8-130">Application sharing conferences</span></span>
    
- <span data-ttu-id="bedd8-131">Web 会議</span><span class="sxs-lookup"><span data-stu-id="bedd8-131">Web conferences</span></span>
    
- <span data-ttu-id="bedd8-132">オーガナイザーの総数</span><span class="sxs-lookup"><span data-stu-id="bedd8-132">Total organizers</span></span>
    
- <span data-ttu-id="bedd8-133">[音声ビデオ会議の合計時間 (分)]</span><span class="sxs-lookup"><span data-stu-id="bedd8-133">Total A/V conference minutes</span></span>
    
- <span data-ttu-id="bedd8-134">Avg。A/V 会議の分数</span><span class="sxs-lookup"><span data-stu-id="bedd8-134">Avg. A/V conference minutes</span></span>
    
- <span data-ttu-id="bedd8-135">[PSTN 電話会議の合計数]</span><span class="sxs-lookup"><span data-stu-id="bedd8-135">Total PSTN conferences</span></span>
    
- <span data-ttu-id="bedd8-136">[PSTN 参加者の合計数]</span><span class="sxs-lookup"><span data-stu-id="bedd8-136">Total PSTN participants</span></span>
    
- <span data-ttu-id="bedd8-137">[PSTN 参加者の合計時間 (分)]</span><span class="sxs-lookup"><span data-stu-id="bedd8-137">Total PSTN participant minutes</span></span>
    
<span data-ttu-id="bedd8-138">[システム使用状況] の指標に加えて、現在の日と過去 6 日間 ([週単位の表示] を選択した **場合)** または [月次ビュー]を選択した場合は、現在の週と過去 6 週間の合計が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bedd8-138">In addition to the System Usage metrics, the following metrics displays total for the current day and the previous six days (if you select **Weekly View**) or for the current week and the past six weeks if you select **Monthly View**.</span></span>
  
## <a name="per-user-call-diagnostics"></a><span data-ttu-id="bedd8-139">Per-User呼び出し診断</span><span class="sxs-lookup"><span data-stu-id="bedd8-139">Per-User Call Diagnostics</span></span>

 <span data-ttu-id="bedd8-140">**呼び出しの失敗を持つユーザー**</span><span class="sxs-lookup"><span data-stu-id="bedd8-140">**Users with call failures**</span></span>
  
- <span data-ttu-id="bedd8-141">通話エラーが発生したユーザーの総数</span><span class="sxs-lookup"><span data-stu-id="bedd8-141">Total users with call failures</span></span>
    
- <span data-ttu-id="bedd8-142">通話の失敗がある会議の開催者</span><span class="sxs-lookup"><span data-stu-id="bedd8-142">Conference organizers with call failures</span></span>
    
  <span data-ttu-id="bedd8-143">**品質の低い通話を使用するユーザー**</span><span class="sxs-lookup"><span data-stu-id="bedd8-143">**Users with poor quality calls**</span></span>
  
- <span data-ttu-id="bedd8-144">品質の低い通話を持つユーザーの総数</span><span class="sxs-lookup"><span data-stu-id="bedd8-144">Total users with poor quality calls</span></span>
    
## <a name="call-diagnostics"></a><span data-ttu-id="bedd8-145">通話診断</span><span class="sxs-lookup"><span data-stu-id="bedd8-145">Call Diagnostics</span></span>

<span data-ttu-id="bedd8-146">ピアツーピア</span><span class="sxs-lookup"><span data-stu-id="bedd8-146">Peer-to-peer</span></span>
  
- <span data-ttu-id="bedd8-147">エラーの合計</span><span class="sxs-lookup"><span data-stu-id="bedd8-147">Total failures</span></span>
    
- <span data-ttu-id="bedd8-148">全体的なエラー率</span><span class="sxs-lookup"><span data-stu-id="bedd8-148">Overall failure rate</span></span>
    
- <span data-ttu-id="bedd8-149">IM エラー率</span><span class="sxs-lookup"><span data-stu-id="bedd8-149">IM failure rate</span></span>
    
- <span data-ttu-id="bedd8-150">オーディオエラー率</span><span class="sxs-lookup"><span data-stu-id="bedd8-150">Audio failure rate</span></span>
    
- <span data-ttu-id="bedd8-151">アプリケーション共有の失敗率</span><span class="sxs-lookup"><span data-stu-id="bedd8-151">Application sharing failure rate</span></span>
    
<span data-ttu-id="bedd8-152">会議</span><span class="sxs-lookup"><span data-stu-id="bedd8-152">Conference</span></span>
  
- <span data-ttu-id="bedd8-153">エラーの合計</span><span class="sxs-lookup"><span data-stu-id="bedd8-153">Total failures</span></span>
    
- <span data-ttu-id="bedd8-154">全体的なエラー率</span><span class="sxs-lookup"><span data-stu-id="bedd8-154">Overall failure rate</span></span>
    
- <span data-ttu-id="bedd8-155">IM エラー率</span><span class="sxs-lookup"><span data-stu-id="bedd8-155">IM failure rate</span></span>
    
- <span data-ttu-id="bedd8-156">A/V エラー 率</span><span class="sxs-lookup"><span data-stu-id="bedd8-156">A/V failure rate</span></span>
    
- <span data-ttu-id="bedd8-157">アプリケーション共有の失敗率</span><span class="sxs-lookup"><span data-stu-id="bedd8-157">Application sharing failure rate</span></span>
    
<span data-ttu-id="bedd8-158">失敗したセッション別の上位 5 つのサーバー</span><span class="sxs-lookup"><span data-stu-id="bedd8-158">Top five servers by failed sessions</span></span>
  
## <a name="media-quality-diagnostics"></a><span data-ttu-id="bedd8-159">メディア品質診断</span><span class="sxs-lookup"><span data-stu-id="bedd8-159">Media Quality Diagnostics</span></span>

<span data-ttu-id="bedd8-160">ピアツーピア</span><span class="sxs-lookup"><span data-stu-id="bedd8-160">Peer-to-peer</span></span>
  
- <span data-ttu-id="bedd8-161">品質の低い通話の合計</span><span class="sxs-lookup"><span data-stu-id="bedd8-161">Total poor quality calls</span></span>
    
- <span data-ttu-id="bedd8-162">低品質の通話率</span><span class="sxs-lookup"><span data-stu-id="bedd8-162">Poor quality call percentage</span></span>
    
- <span data-ttu-id="bedd8-163">品質の低い PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="bedd8-163">PSTN calls with poor quality</span></span>
    
<span data-ttu-id="bedd8-164">会議</span><span class="sxs-lookup"><span data-stu-id="bedd8-164">Conference</span></span>
  
- <span data-ttu-id="bedd8-165">品質の低い通話の合計</span><span class="sxs-lookup"><span data-stu-id="bedd8-165">Total poor quality calls</span></span>
    
- <span data-ttu-id="bedd8-166">低品質の通話率</span><span class="sxs-lookup"><span data-stu-id="bedd8-166">Poor quality call percentage</span></span>
    
- <span data-ttu-id="bedd8-167">品質の低い PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="bedd8-167">PSTN calls with poor quality</span></span>
    
<span data-ttu-id="bedd8-168">品質の低い通話率による上位の最悪のサーバー</span><span class="sxs-lookup"><span data-stu-id="bedd8-168">Top worst servers by poor quality call percentage</span></span>
  
## <a name="working-with-the-monitoring-dashboard"></a><span data-ttu-id="bedd8-169">監視ダッシュボードの操作</span><span class="sxs-lookup"><span data-stu-id="bedd8-169">Working with the Monitoring Dashboard</span></span>

<span data-ttu-id="bedd8-170">上記のように、既定では現在の週の合計が表示され、過去 6 週間の傾向値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bedd8-170">As noted, by default totals are shown for the current week and trend values are shown for the past six weeks.</span></span> <span data-ttu-id="bedd8-171">現在の月の合計 (および過去 6 か月間の傾向値) を表示する場合は、ダッシュボードの右上隅にある [月次ビュー] リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bedd8-171">If you would prefer to see totals for the current month (as well as trend values for the past six months), click the **Monthly View** link in the upper right corner of the dashboard.</span></span> <span data-ttu-id="bedd8-172">月ごとの合計を表示する場合、リンク テキストは [週次表示] **に変更されます**。</span><span class="sxs-lookup"><span data-stu-id="bedd8-172">If you decide to view monthly totals, the link text will change to **Weekly View**.</span></span> <span data-ttu-id="bedd8-173">そのリンクをクリックすると、週単位の表示に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="bedd8-173">You can switch back to the weekly view by clicking that link.</span></span>
  
> [!TIP]
> <span data-ttu-id="bedd8-174">監視ダッシュボードでは、現在の週 (または月) の合計と、過去 6 週間 (または月) の傾向値を確認できます。</span><span class="sxs-lookup"><span data-stu-id="bedd8-174">The Monitoring Dashboard restricts you to looking at totals for the current week (or month) and trend values for the past six weeks (or months).</span></span> <span data-ttu-id="bedd8-175">これらの日付と時刻は変更できません。</span><span class="sxs-lookup"><span data-stu-id="bedd8-175">You cannot change these dates and times.</span></span> <span data-ttu-id="bedd8-176">たとえば、ダッシュボードを使用して、9 か月前から始まる期間のレポートの合計を表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="bedd8-176">For example, you cannot use the Dashboard to view report totals for the time period beginning nine months ago.</span></span> 
  
<span data-ttu-id="bedd8-177">[今週]、[**今月**]、または [今日] 列に表示される **値は、** アイテムに関する詳細情報にリンクします。</span><span class="sxs-lookup"><span data-stu-id="bedd8-177">The values shown in the **This week**, **This month**, or **Today** columns link you to more detailed information about the item.</span></span> <span data-ttu-id="bedd8-178">列名と列に表示される値は、多くの場合、選択した指標や、週単位ビューまたは月次ビューを選択したかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="bedd8-178">Keep in mind that the column name and the values displayed in that column will often differ depending on the metric chosen and depending on whether you have selected weekly view or monthly view.</span></span> <span data-ttu-id="bedd8-179">たとえば、[一意のユーザー ログオン] メトリックに表示される合計をクリックすると、指定した期間の **ユーザー登録レポート** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bedd8-179">For example, if you click the totals shown for the **Unique user logons** metric you will see the **User Registration Report** for the specified time period.</span></span> <span data-ttu-id="bedd8-180">[ダッシュボード] をクリックすると、いつでも監視ダッシュボードに戻 **ることができます**。</span><span class="sxs-lookup"><span data-stu-id="bedd8-180">You can return to the Monitoring Dashboard at any time by clicking **Dashboard**.</span></span>
  
> [!TIP]
> <span data-ttu-id="bedd8-181">[監視サーバー レポート] ホーム ページには、ダッシュボードの右上隅にある [レポート] リンクをクリックしてアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="bedd8-181">You can also access the Monitoring Server Reports home page by clicking the **Reports** link in the upper right corner of the Dashboard.</span></span>
  
<span data-ttu-id="bedd8-182">[ **傾向]** 列には、過去 6 週間の合計を示す単純な線グラフが表示されます (または、指標と時間間隔に応じて、過去 6 日間または過去 6 か月)。</span><span class="sxs-lookup"><span data-stu-id="bedd8-182">The **Trend** column displays a simple line graph that shows totals for the past six weeks (or, depending on the metric and the time interval, the past six days or the past six months).</span></span> <span data-ttu-id="bedd8-183">これらの単純な線グラフには、期間ごとにラベルが付いていないデータ ポイントが 1 つ表示されます (たとえば、過去 6 週間のラベルなしデータ ポイントが 1 つ)。</span><span class="sxs-lookup"><span data-stu-id="bedd8-183">These simple line graphs display one unlabeled data point for each time period (for example, one unlabeled data point for each of the past six weeks).</span></span> <span data-ttu-id="bedd8-184">ただし、グラフの上にマウス ポインターを置き、これらのグラフの実際の値を取得できます。</span><span class="sxs-lookup"><span data-stu-id="bedd8-184">However, you can retrieve actual values for these graphs by holding your mouse pointer over the graph.</span></span> <span data-ttu-id="bedd8-185">その場合、ツール ヒントにはグラフの最大値と最小値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bedd8-185">In that case, a tool tip shows you the maximum and minimum values in the graph.</span></span>
  
## <a name="exporting-data-from-the-monitoring-dashboard"></a><span data-ttu-id="bedd8-186">監視ダッシュボードからのデータのエクスポート</span><span class="sxs-lookup"><span data-stu-id="bedd8-186">Exporting Data from the Monitoring Dashboard</span></span>

<span data-ttu-id="bedd8-187">監視ダッシュボードには、現在のダッシュボード ビューをエクスポートするさまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="bedd8-187">The Monitoring Dashboard provides a number of ways to export the current dashboard view.</span></span> <span data-ttu-id="bedd8-188">[ダッシュボード] ツールバーには、緑の矢印が付いているフロッピー ディスクのように見えるアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bedd8-188">On the Dashboard toolbar, you'll see an icon that looks like a floppy disk with a green arrow attached to it.</span></span> <span data-ttu-id="bedd8-189">このアイコンをクリックすると、ドロップダウン リストが表示され、次のデータエクスポート形式が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bedd8-189">If you click this icon, a dropdown list will appear giving you the following data export formats:</span></span>
  
- <span data-ttu-id="bedd8-190">レポート データが含まれている XML ファイル</span><span class="sxs-lookup"><span data-stu-id="bedd8-190">XML file with report data</span></span>
    
- <span data-ttu-id="bedd8-191">CSV (コンマ区切り)</span><span class="sxs-lookup"><span data-stu-id="bedd8-191">CSV (comma delimited)</span></span>
    
- <span data-ttu-id="bedd8-192">PDF</span><span class="sxs-lookup"><span data-stu-id="bedd8-192">PDF</span></span>
    
- <span data-ttu-id="bedd8-193">MHTML (Web アーカイブ)</span><span class="sxs-lookup"><span data-stu-id="bedd8-193">MHTML (web archive)</span></span>
    
- <span data-ttu-id="bedd8-194">Excel</span><span class="sxs-lookup"><span data-stu-id="bedd8-194">Excel</span></span>
    
- <span data-ttu-id="bedd8-195">TIFF ファイル</span><span class="sxs-lookup"><span data-stu-id="bedd8-195">TIFF file</span></span>
    
- <span data-ttu-id="bedd8-196">Word</span><span class="sxs-lookup"><span data-stu-id="bedd8-196">Word</span></span>
    
<span data-ttu-id="bedd8-197">現在のダッシュボード ビュー (および値) をエクスポートするには、目的のエクスポート オプションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bedd8-197">To export the current dashboard view (and its values), click the desired export option.</span></span> <span data-ttu-id="bedd8-198">Skype for Business Server は、指定した形式でレポートを生成し、そのレポートを開くまたは保存するオプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="bedd8-198">Skype for Business Server generates a report in the specified format and then give you the option of opening that report or saving it.</span></span> <span data-ttu-id="bedd8-199">既定では、Skype for Business Server はレポートの監視ダッシュボードにタイトルを付け、それをダウンロード フォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="bedd8-199">Note that, by default, Skype for Business Server titles the report **Monitoring Dashboard** and saves it to your Downloads folder.</span></span> <span data-ttu-id="bedd8-200">レポートに別の名前を付け、または別のフォルダーに保存するには、[保存] ボタンの横にある矢印をクリックし、[名前を付けて保存]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="bedd8-200">To give the report a different name or to store it in a different folder, click the arrow next to the **Save** button and then click **Save As**.</span></span> <span data-ttu-id="bedd8-201">[監視ダッシュボード] という名前に問題が生じ、レポートが [ダウンロード] フォルダーに保存されている場合は、[保存] ボタンを **クリック** します。</span><span class="sxs-lookup"><span data-stu-id="bedd8-201">If you are fine with name **Monitoring Dashboard** and with having the report saved in the Downloads folder you can just click the **Save** button.</span></span>
  
<span data-ttu-id="bedd8-202">ダッシュボード データをエクスポートしようとするときに、[セキュリティアラート] ダイアログ ボックスが表示され、[現在の設定ではこのファイルをダウンロードできません] というメッセージが表示される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bedd8-202">It's possible that, when you try to export dashboard data, a **Security Alert** dialog box will appear along with the message "Your current settings do not allow this file to be downloaded."</span></span> <span data-ttu-id="bedd8-203">この場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="bedd8-203">If that occurs, do the following:</span></span>
  
- <span data-ttu-id="bedd8-204">[インターネット Internet Explorer] で、[インターネット オプション **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="bedd8-204">In Internet Explorer, select **Internet Options**.</span></span>
    
- <span data-ttu-id="bedd8-205">[インターネット **オプション] ダイアログ** ボックスの [セキュリティ] タブ **で** 、[信頼済みサイト] **を** クリックし、[サイト] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="bedd8-205">In the **Internet Options** dialog box, on the **Security** tab, click **Trusted sites** and then click **Sites**.</span></span>
    
- <span data-ttu-id="bedd8-206">[信頼済 **みサイト]** ダイアログボックスで、[追加] をクリックして、Skype for Business Server レポートを実行している Skype for Business Server を信頼できる Web サイトのコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="bedd8-206">In the **Trusted sites** dialog box, click **Add** to add the Skype for Business Server that is running Skype for Business Server Reports to the collections of trusted websites.</span></span>
    
- <span data-ttu-id="bedd8-207">[閉 **じる] を** クリックし **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="bedd8-207">Click **Close** and then click **OK**.</span></span>
    
<span data-ttu-id="bedd8-208">その後、変更を有効にする前に監視ダッシュボードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bedd8-208">You will then need to refresh the Monitoring Dashboard before the changes take effect.</span></span> <span data-ttu-id="bedd8-209">これを行うには、F5 キーを押するか、[ダッシュボード] ツールバーの **[** 更新] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bedd8-209">To do that, either press F5 or click the **Refresh** icon in the Dashboard toolbar.</span></span> <span data-ttu-id="bedd8-210">([ **更新]** アイコンは、緑色の矢印のペアが含む円です)。</span><span class="sxs-lookup"><span data-stu-id="bedd8-210">(The **Refresh** icon is a circle with a pair of green arrows in it.)</span></span>
  
<span data-ttu-id="bedd8-211">また、最新の監視ダッシュボード データへのリンクを含む、ライブ データ フィードを含む Excel スプレッドシートを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="bedd8-211">You can also create an Excel spreadsheet that includes live data feeds, which includes links to the latest Monitoring Dashboard data.</span></span> <span data-ttu-id="bedd8-212">ライブ データ フィード ファイルを作成するには、ツールバーのオレンジ色の **[データ** フィードにエクスポート] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bedd8-212">To create a live data feed file, click the orange **Export to Data Feed** icon in the toolbar.</span></span>
  
<span data-ttu-id="bedd8-213">現在のダッシュボードを印刷する場合は、ツールバーのプリンター アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bedd8-213">If you would prefer to print the current Dashboard then click the printer icon in the toolbar.</span></span>
