---
title: Skype のビジネス サーバーの監視のダッシュ ボードを使用します。
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e00e5783-116f-481f-ad17-3af847d6769a
description: '概要: は、ビジネス サーバー、Skype での監視のダッシュ ボードについて説明します。'
ms.openlocfilehash: 19d0ddefc79d97ee19a371cde4fb0dc2d10f7e90
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225350"
---
# <a name="using-the-monitoring-dashboard-in-skype-for-business-server"></a><span data-ttu-id="28df7-103">Skype のビジネス サーバーの監視のダッシュ ボードを使用します。</span><span class="sxs-lookup"><span data-stu-id="28df7-103">Using the Monitoring Dashboard in Skype for Business Server</span></span>
 
<span data-ttu-id="28df7-104">**の概要:** Business Server には、Skype での監視のダッシュ ボードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="28df7-104">**Summary:** Learn about the Monitoring Dashboard in Skype for Business Server.</span></span>
  
<span data-ttu-id="28df7-105">監視ダッシュ ボードでは、ビジネス サーバー システムの状態、システムの使用のため、Skype の概要を簡単に管理者を提供します。</span><span class="sxs-lookup"><span data-stu-id="28df7-105">The Monitoring Dashboard provides administrators with a quick overview of their Skype for Business Server system health and system usage.</span></span> <span data-ttu-id="28df7-106">このダッシュボードは、主要なシステム指標の集計ビューを表示するように設計されており、次のいずれかを表示します。</span><span class="sxs-lookup"><span data-stu-id="28df7-106">The Dashboard is designed to show an aggregate view of key system metrics and to do so by displaying either:</span></span>
  
- <span data-ttu-id="28df7-107">現在の日付の合計。</span><span class="sxs-lookup"><span data-stu-id="28df7-107">Totals for the current day.</span></span> <span data-ttu-id="28df7-108">現在の日付で表示される値は、夜中 12 時から現在の時刻 (レポート サーバーのローカル時刻に基づく) までに記録されたデータを表すことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="28df7-108">Note that values shown for the current day represent data that has been recorded from midnight until the current time (based on the local time of the reporting server).</span></span> <span data-ttu-id="28df7-109">つまり、通常は、24 時間ではなく、特定の日付のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="28df7-109">That means that you will typically be viewing data for a partial day and not for a 24-hour period.</span></span> <span data-ttu-id="28df7-110">たとえば、午前 0 時と午前 8時 00分の現在の時刻との間の 8 時間があるためにするサーバーのローカル時刻が午前 8時 00分の場合は、8 時間分のデータが参照してください。</span><span class="sxs-lookup"><span data-stu-id="28df7-110">For example, if the local time of the server is 8:00 AM, you see eight hours' worth of data because there are eight hours between midnight and the current time of 8:00 AM.</span></span>
    
- <span data-ttu-id="28df7-111">週の合計と過去 6 週間の傾向の合計。</span><span class="sxs-lookup"><span data-stu-id="28df7-111">Totals for the week, and trend totals for the past six weeks.</span></span>
    
- <span data-ttu-id="28df7-112">月の合計と過去 6 か月の傾向の合計 (システム使用状況のみ)。</span><span class="sxs-lookup"><span data-stu-id="28df7-112">Totals for the month, and trend totals for the past six months (for system usage only).</span></span>
    
<span data-ttu-id="28df7-113">Skype ビジネス サーバーの監視のレポートへのアクセスに使用する URL を取得する[Get CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csreportingconfiguration?view=skype-ps)コマンドレットを使用することができることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="28df7-113">Note that you can use the [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) cmdlet to return the URL used for accessing Skype for Business Server Monitoring Reports:</span></span>
  
```
Get-CsReportingConfiguration
```

<span data-ttu-id="28df7-114">既定では、監視ダッシュボードは、現在の週の次の指標 (および過去 6 週間の傾向の合計) を表示します。</span><span class="sxs-lookup"><span data-stu-id="28df7-114">By default, the Monitoring Dashboard shows data for the following metrics for the current week (and trend totals for the previous six weeks):</span></span>
  
## <a name="system-usage-metrics"></a><span data-ttu-id="28df7-115">システム使用状況の指標</span><span class="sxs-lookup"><span data-stu-id="28df7-115">System Usage Metrics</span></span>

 <span data-ttu-id="28df7-116">**登録**</span><span class="sxs-lookup"><span data-stu-id="28df7-116">**Registration**</span></span>
  
- <span data-ttu-id="28df7-117">一意のユーザー ログオン</span><span class="sxs-lookup"><span data-stu-id="28df7-117">Unique user logons</span></span>
    
  <span data-ttu-id="28df7-118">**ピアツーピア**</span><span class="sxs-lookup"><span data-stu-id="28df7-118">**Peer-to-peer**</span></span>
  
- <span data-ttu-id="28df7-119">セッションの合計数</span><span class="sxs-lookup"><span data-stu-id="28df7-119">Total sessions</span></span>
    
- <span data-ttu-id="28df7-120">IM セッション</span><span class="sxs-lookup"><span data-stu-id="28df7-120">IM sessions</span></span>
    
- <span data-ttu-id="28df7-121">音声セッション</span><span class="sxs-lookup"><span data-stu-id="28df7-121">Audio sessions</span></span>
    
- <span data-ttu-id="28df7-122">ビデオ セッション</span><span class="sxs-lookup"><span data-stu-id="28df7-122">Video sessions</span></span>
    
- <span data-ttu-id="28df7-123">アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="28df7-123">Application sharing</span></span>
    
- <span data-ttu-id="28df7-124">音声セッションの合計時間 (分)</span><span class="sxs-lookup"><span data-stu-id="28df7-124">Total audio session minutes</span></span>
    
- <span data-ttu-id="28df7-125">音声セッションの平均時間 (分)</span><span class="sxs-lookup"><span data-stu-id="28df7-125">Avg. audio session minutes</span></span>
    
  <span data-ttu-id="28df7-126">**電話会議**</span><span class="sxs-lookup"><span data-stu-id="28df7-126">**Conference**</span></span>
  
- <span data-ttu-id="28df7-127">電話会議の合計数</span><span class="sxs-lookup"><span data-stu-id="28df7-127">Total conferences</span></span>
    
- <span data-ttu-id="28df7-128">IM 会議</span><span class="sxs-lookup"><span data-stu-id="28df7-128">IM conferences</span></span>
    
- <span data-ttu-id="28df7-129">音声ビデオ会議</span><span class="sxs-lookup"><span data-stu-id="28df7-129">A/V conferences</span></span>
    
- <span data-ttu-id="28df7-130">アプリケーション共有会議</span><span class="sxs-lookup"><span data-stu-id="28df7-130">Application sharing conferences</span></span>
    
- <span data-ttu-id="28df7-131">Web 会議</span><span class="sxs-lookup"><span data-stu-id="28df7-131">Web conferences</span></span>
    
- <span data-ttu-id="28df7-132">開催者の合計数</span><span class="sxs-lookup"><span data-stu-id="28df7-132">Total organizers</span></span>
    
- <span data-ttu-id="28df7-133">音声ビデオ会議の合計時間 (分)</span><span class="sxs-lookup"><span data-stu-id="28df7-133">Total A/V conference minutes</span></span>
    
- <span data-ttu-id="28df7-134">音声ビデオ会議の平均時間 (分)</span><span class="sxs-lookup"><span data-stu-id="28df7-134">Avg. A/V conference minutes</span></span>
    
- <span data-ttu-id="28df7-135">PSTN 電話会議の合計数</span><span class="sxs-lookup"><span data-stu-id="28df7-135">Total PSTN conferences</span></span>
    
- <span data-ttu-id="28df7-136">PSTN 参加者の合計数</span><span class="sxs-lookup"><span data-stu-id="28df7-136">Total PSTN participants</span></span>
    
- <span data-ttu-id="28df7-137">PSTN 参加者の合計時間 (分)</span><span class="sxs-lookup"><span data-stu-id="28df7-137">Total PSTN participant minutes</span></span>
    
<span data-ttu-id="28df7-138">システム使用状況の指標に加えて、次の指標では、現在の日付および過去 6 日間の合計 ([**週ビュー**] を選択した場合)、または現在の週および過去 6 週間の合計 ([**月ビュー**] を選択した場合) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="28df7-138">In addition to the System Usage metrics, the following metrics displays total for the current day and the previous six days (if you select **Weekly View**) or for the current week and the past six weeks if you select **Monthly View**.</span></span>
  
## <a name="per-user-call-diagnostics"></a><span data-ttu-id="28df7-139">ユーザーごとの通話診断</span><span class="sxs-lookup"><span data-stu-id="28df7-139">Per-User Call Diagnostics</span></span>

 <span data-ttu-id="28df7-140">**通話障害が発生したユーザー**</span><span class="sxs-lookup"><span data-stu-id="28df7-140">**Users with call failures**</span></span>
  
- <span data-ttu-id="28df7-141">通話障害が発生したユーザーの合計数</span><span class="sxs-lookup"><span data-stu-id="28df7-141">Total users with call failures</span></span>
    
- <span data-ttu-id="28df7-142">通話障害が発生した電話会議の開催者</span><span class="sxs-lookup"><span data-stu-id="28df7-142">Conference organizers with call failures</span></span>
    
  <span data-ttu-id="28df7-143">**低品質通話のユーザー**</span><span class="sxs-lookup"><span data-stu-id="28df7-143">**Users with poor quality calls**</span></span>
  
- <span data-ttu-id="28df7-144">通話の品質が低いユーザーの合計数</span><span class="sxs-lookup"><span data-stu-id="28df7-144">Total users with poor quality calls</span></span>
    
## <a name="call-diagnostics"></a><span data-ttu-id="28df7-145">通話診断</span><span class="sxs-lookup"><span data-stu-id="28df7-145">Call Diagnostics</span></span>

<span data-ttu-id="28df7-146">ピアツーピア</span><span class="sxs-lookup"><span data-stu-id="28df7-146">Peer-to-peer</span></span>
  
- <span data-ttu-id="28df7-147">エラー総数</span><span class="sxs-lookup"><span data-stu-id="28df7-147">Total failures</span></span>
    
- <span data-ttu-id="28df7-148">総合エラー率</span><span class="sxs-lookup"><span data-stu-id="28df7-148">Overall failure rate</span></span>
    
- <span data-ttu-id="28df7-149">IM エラー率</span><span class="sxs-lookup"><span data-stu-id="28df7-149">IM failure rate</span></span>
    
- <span data-ttu-id="28df7-150">音声エラー率</span><span class="sxs-lookup"><span data-stu-id="28df7-150">Audio failure rate</span></span>
    
- <span data-ttu-id="28df7-151">アプリケーション共有エラー率</span><span class="sxs-lookup"><span data-stu-id="28df7-151">Application sharing failure rate</span></span>
    
<span data-ttu-id="28df7-152">電話会議</span><span class="sxs-lookup"><span data-stu-id="28df7-152">Conference</span></span>
  
- <span data-ttu-id="28df7-153">エラー総数</span><span class="sxs-lookup"><span data-stu-id="28df7-153">Total failures</span></span>
    
- <span data-ttu-id="28df7-154">総合エラー率</span><span class="sxs-lookup"><span data-stu-id="28df7-154">Overall failure rate</span></span>
    
- <span data-ttu-id="28df7-155">IM エラー率</span><span class="sxs-lookup"><span data-stu-id="28df7-155">IM failure rate</span></span>
    
- <span data-ttu-id="28df7-156">音声ビデオ エラー率</span><span class="sxs-lookup"><span data-stu-id="28df7-156">A/V failure rate</span></span>
    
- <span data-ttu-id="28df7-157">アプリケーション共有エラー率</span><span class="sxs-lookup"><span data-stu-id="28df7-157">Application sharing failure rate</span></span>
    
<span data-ttu-id="28df7-158">エラー セッション発生数の上位 5 サーバー</span><span class="sxs-lookup"><span data-stu-id="28df7-158">Top five servers by failed sessions</span></span>
  
## <a name="media-quality-diagnostics"></a><span data-ttu-id="28df7-159">メディア品質診断</span><span class="sxs-lookup"><span data-stu-id="28df7-159">Media Quality Diagnostics</span></span>

<span data-ttu-id="28df7-160">ピアツーピア</span><span class="sxs-lookup"><span data-stu-id="28df7-160">Peer-to-peer</span></span>
  
- <span data-ttu-id="28df7-161">低品質通話の合計数</span><span class="sxs-lookup"><span data-stu-id="28df7-161">Total poor quality calls</span></span>
    
- <span data-ttu-id="28df7-162">低品質通話のパーセンテージ</span><span class="sxs-lookup"><span data-stu-id="28df7-162">Poor quality call percentage</span></span>
    
- <span data-ttu-id="28df7-163">低品質な PSTN 通話の数</span><span class="sxs-lookup"><span data-stu-id="28df7-163">PSTN calls with poor quality</span></span>
    
<span data-ttu-id="28df7-164">電話会議</span><span class="sxs-lookup"><span data-stu-id="28df7-164">Conference</span></span>
  
- <span data-ttu-id="28df7-165">低品質通話の合計数</span><span class="sxs-lookup"><span data-stu-id="28df7-165">Total poor quality calls</span></span>
    
- <span data-ttu-id="28df7-166">低品質通話のパーセンテージ</span><span class="sxs-lookup"><span data-stu-id="28df7-166">Poor quality call percentage</span></span>
    
- <span data-ttu-id="28df7-167">低品質な PSTN 通話の数</span><span class="sxs-lookup"><span data-stu-id="28df7-167">PSTN calls with poor quality</span></span>
    
<span data-ttu-id="28df7-168">低品質通話パーセンテージの上位サーバー</span><span class="sxs-lookup"><span data-stu-id="28df7-168">Top worst servers by poor quality call percentage</span></span>
  
## <a name="working-with-the-monitoring-dashboard"></a><span data-ttu-id="28df7-169">監視ダッシュボードの操作</span><span class="sxs-lookup"><span data-stu-id="28df7-169">Working with the Monitoring Dashboard</span></span>

<span data-ttu-id="28df7-p103">既に説明したように、既定では、現在の週の合計と過去 6 週間の傾向値が表示されます。現在の月の合計 (および過去 6 か月の傾向値) を表示する場合は、ダッシュボードの右上隅にある [**月ビュー**] をクリックします。月の合計の表示を決定すると、リンク テキストが [**週ビュー**] に変わります。そのリンクをクリックすると、週ビューに再び切り替わります。</span><span class="sxs-lookup"><span data-stu-id="28df7-p103">As noted, by default totals are shown for the current week and trend values are shown for the past six weeks. If you would prefer to see totals for the current month (as well as trend values for the past six months), click the **Monthly View** link in the upper right corner of the dashboard. If you decide to view monthly totals, the link text will change to **Weekly View**. You can switch back to the weekly view by clicking that link.</span></span>
  
> [!TIP]
> <span data-ttu-id="28df7-p104">監視ダッシュボードでは、現在の週 (または現在の月) の合計と過去 6 週間 (または過去 6 か月) の傾向値を表示するように制限されています。これらの日時を変更することはできません。たとえば、ダッシュボードを使用して、9 か月前から始まる期間のレポート合計を表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="28df7-p104">The Monitoring Dashboard restricts you to looking at totals for the current week (or month) and trend values for the past six weeks (or months). You cannot change these dates and times. For example, you cannot use the Dashboard to view report totals for the time period beginning nine months ago.</span></span> 
  
<span data-ttu-id="28df7-p105">[**今週**]、[**今月**]、または [**今日**] 列に表示される値は、アイテムに関する詳細情報にリンクされています。その列に表示される列名と値は、選択した指標、および週ビューまたは月ビューのどちらを選択したかに応じて異なることに注意してください。たとえば、[**一意のユーザー ログオン**] 指標で表示される合計をクリックした場合は、指定した期間の [**ユーザー登録レポート**] が表示されます。[**ダッシュボード**] をクリックすると、監視ダッシュボードにいつでも戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="28df7-p105">The values shown in the **This week**, **This month**, or **Today** columns link you to more detailed information about the item. Keep in mind that the column name and the values displayed in that column will often differ depending on the metric chosen and depending on whether you have selected weekly view or monthly view. For example, if you click the totals shown for the **Unique user logons** metric you will see the **User Registration Report** for the specified time period. You can return to the Monitoring Dashboard at any time by clicking **Dashboard**.</span></span>
  
> [!TIP]
> <span data-ttu-id="28df7-181">監視サーバー レポートのホーム ページは、ダッシュ ボードの右上隅の **「レポート**」リンクをクリックしてもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="28df7-181">You can also access the Monitoring Server Reports home page by clicking the **Reports** link in the upper right corner of the Dashboard.</span></span>
  
<span data-ttu-id="28df7-p106">[**傾向**] 列には、過去 6 週間 (または、指標および時間間隔に応じて、過去 6 日間または過去 6 か月) の合計を表す簡単な折れ線グラフが表示されます。これらの簡単な折れ線グラフは、各期間の 1 つの未分類のデータ点 (たとえば、過去 6 週間それぞれの 1 つの未分類のデータ点) を表示します。ただし、マウス ポインターをグラフ上に合わせると、これらのグラフの実際の値を取得できます。この場合、グラフの最大値と最小値がツール ヒントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="28df7-p106">The **Trend** column displays a simple line graph that shows totals for the past six weeks (or, depending on the metric and the time interval, the past six days or the past six months). These simple line graphs display one unlabeled data point for each time period (for example, one unlabeled data point for each of the past six weeks). However, you can retrieve actual values for these graphs by holding your mouse pointer over the graph. In that case, a tool tip shows you the maximum and minimum values in the graph.</span></span>
  
## <a name="exporting-data-from-the-monitoring-dashboard"></a><span data-ttu-id="28df7-186">監視ダッシュボードからのデータ エクスポート</span><span class="sxs-lookup"><span data-stu-id="28df7-186">Exporting Data from the Monitoring Dashboard</span></span>

<span data-ttu-id="28df7-p107">監視ダッシュボードは、現在のダッシュボード ビューをエクスポートするさまざまな方法を備えています。ダッシュボードのツールバーには、緑の矢印が付いたフロッピー ディスクのように見えるアイコンがあります。このアイコンをクリックすると、次のデータ エクスポート形式がリストされたドロップダウン リストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="28df7-p107">The Monitoring Dashboard provides a number of ways to export the current dashboard view. On the Dashboard toolbar, you'll see an icon that looks like a floppy disk with a green arrow attached to it. If you click this icon, a dropdown list will appear giving you the following data export formats:</span></span>
  
- <span data-ttu-id="28df7-190">レポート データが含まれている XML ファイル</span><span class="sxs-lookup"><span data-stu-id="28df7-190">XML file with report data</span></span>
    
- <span data-ttu-id="28df7-191">CSV (コンマ区切り)</span><span class="sxs-lookup"><span data-stu-id="28df7-191">CSV (comma delimited)</span></span>
    
- <span data-ttu-id="28df7-192">PDF</span><span class="sxs-lookup"><span data-stu-id="28df7-192">PDF</span></span>
    
- <span data-ttu-id="28df7-193">MHTML (Web アーカイブ)</span><span class="sxs-lookup"><span data-stu-id="28df7-193">MHTML (web archive)</span></span>
    
- <span data-ttu-id="28df7-194">Excel</span><span class="sxs-lookup"><span data-stu-id="28df7-194">Excel</span></span>
    
- <span data-ttu-id="28df7-195">TIFF ファイル</span><span class="sxs-lookup"><span data-stu-id="28df7-195">TIFF file</span></span>
    
- <span data-ttu-id="28df7-196">Word</span><span class="sxs-lookup"><span data-stu-id="28df7-196">Word</span></span>
    
<span data-ttu-id="28df7-197">現在のダッシュボード ビュー (およびその値) をエクスポートするには、目的のエクスポート オプションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="28df7-197">To export the current dashboard view (and its values), click the desired export option.</span></span> <span data-ttu-id="28df7-198">ビジネス サーバーの Skype では、指定の形式でレポートを生成し、そのレポートを開くまたは保存するためのオプションを提供し。</span><span class="sxs-lookup"><span data-stu-id="28df7-198">Skype for Business Server generates a report in the specified format and then give you the option of opening that report or saving it.</span></span> <span data-ttu-id="28df7-199">既定では、Skype ビジネス サーバーの**監視のダッシュ ボード**のレポートのタイトルし、ダウンロードのフォルダーに保存するに注意してください。</span><span class="sxs-lookup"><span data-stu-id="28df7-199">Note that, by default, Skype for Business Server titles the report **Monitoring Dashboard** and saves it to your Downloads folder.</span></span> <span data-ttu-id="28df7-200">レポートに別の名前を付ける場合、またはレポートを異なるフォルダーに保存する場合は、[**保存**] ボタンの横にある矢印をクリックし、[**名前を付けて保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="28df7-200">To give the report a different name or to store it in a different folder, click the arrow next to the **Save** button and then click **Save As**.</span></span> <span data-ttu-id="28df7-201">レポートを [**監視ダッシュボード**] という名前でダッシュボード フォルダーに保存しても問題ない場合は、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="28df7-201">If you are fine with name **Monitoring Dashboard** and with having the report saved in the Downloads folder you can just click the **Save** button.</span></span>
  
<span data-ttu-id="28df7-p109">ダッシュボード データをエクスポートしようとすると、[**セキュリティの警告**] ダイアログ ボックスと "現在のセキュリティ設定では、このファイルをダウンロードできません。" というメッセージが表示される可能性があります。このダイアログ ボックスとメッセージが表示された場合は、次の操作を実行してください。</span><span class="sxs-lookup"><span data-stu-id="28df7-p109">It's possible that, when you try to export dashboard data, a **Security Alert** dialog box will appear along with the message "Your current settings do not allow this file to be downloaded." If that occurs, do the following:</span></span>
  
- <span data-ttu-id="28df7-204">Internet Explorer で、[**インターネット オプション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="28df7-204">In Internet Explorer, select **Internet Options**.</span></span>
    
- <span data-ttu-id="28df7-205">[**インターネット オプション**] ダイアログ ボックスの [**セキュリティ**] タブで、[**信頼済みサイト**] をクリックし、[**サイト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="28df7-205">In the **Internet Options** dialog box, on the **Security** tab, click **Trusted sites** and then click **Sites**.</span></span>
    
- <span data-ttu-id="28df7-206">**信頼済みサイト**] ダイアログ ボックスで、Skype をビジネス サーバーを実行している Skype ビジネス サーバー レポートを信頼済みサイトのコレクションに追加する**追加**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="28df7-206">In the **Trusted sites** dialog box, click **Add** to add the Skype for Business Server that is running Skype for Business Server Reports to the collections of trusted websites.</span></span>
    
- <span data-ttu-id="28df7-207">[**閉じる**] をクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="28df7-207">Click **Close** and then click **OK**.</span></span>
    
<span data-ttu-id="28df7-p110">次に、変更が反映される前に、監視ダッシュボードを更新する必要があります。監視ダッシュボードを更新するには、F5 キーを押すか、ダッシュボードのツールバーにある [**更新**] アイコンをクリックします ([**更新**] アイコンは緑の矢印のペアを囲んだ丸いアイコンです)。</span><span class="sxs-lookup"><span data-stu-id="28df7-p110">You will then need to refresh the Monitoring Dashboard before the changes take effect. To do that, either press F5 or click the **Refresh** icon in the Dashboard toolbar. (The **Refresh** icon is a circle with a pair of green arrows in it.)</span></span>
  
<span data-ttu-id="28df7-p111">最新の監視ダッシュボード データへのリンクがあるライブ データ フィードが含まれた Excel スプレッドシートを作成することもできます。ライブ データ フィードのファイルを作成するには、ツールバーにあるオレンジ色の [**データ フィードへのエクスポート**] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="28df7-p111">You can also create an Excel spreadsheet that includes live data feeds, which includes links to the latest Monitoring Dashboard data. To create a live data feed file, click the orange **Export to Data Feed** icon in the toolbar.</span></span>
  
<span data-ttu-id="28df7-213">現在のダッシュボードを印刷する場合は、ツールバーのプリンター アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="28df7-213">If you would prefer to print the current Dashboard then click the printer icon in the toolbar.</span></span>
  

