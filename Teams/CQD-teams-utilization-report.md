---
title: CQD のデータを使用して、Power BI で Microsoft Teams の使用率を表示する
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Teams 使用率の Power BI レポートを使って、組織での Microsoft Teams の利用状況を追跡します。
ms.openlocfilehash: d22f37bb230ecbaa3cf6c33c2ba43f5ea92afaad
ms.sourcegitcommit: 98fcfc03c55917d0aca48b7bd97988f81e8930c1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2020
ms.locfileid: "42559485"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a><span data-ttu-id="fc754-103">CQD のデータを使用して、Power BI で Microsoft Teams の使用率を表示する</span><span class="sxs-lookup"><span data-stu-id="fc754-103">View Microsoft Teams utilization in Power BI using CQD data</span></span>

<span data-ttu-id="fc754-104">2020年3月に初めて、CQD のダウンロード可能な[POWER BI クエリテンプレート](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)に Teams の使用状況レポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="fc754-104">New in March 2020, we've added a Teams Utilization report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 

<span data-ttu-id="fc754-105">この新しいチームの使用状況レポートでは、ユーザーが Microsoft Teams を使用している方法 (およびその程度) を確認できます。</span><span class="sxs-lookup"><span data-stu-id="fc754-105">This new Teams Utilization reports lets you see how (and how much) your users are using Microsoft Teams.</span></span> <span data-ttu-id="fc754-106">これらのレポートは、管理者とビジネスリーダーの両方がこのデータにすばやくアクセスできる一元的な場所です。</span><span class="sxs-lookup"><span data-stu-id="fc754-106">These reports are intended to be a centralized location that both administrators and business leaders can quickly go to for this data.</span></span>

<span data-ttu-id="fc754-107">Teams 使用率 Power BI レポートは、2つの主要なレポートで構成されています。**[通話カウントの概要](#call-count-summary-report)** と**[音声分の概要](#audio-minutes-summary-report)**。</span><span class="sxs-lookup"><span data-stu-id="fc754-107">The Teams Utilization Power BI report consists of two primary reports: **[Call Count Summary](#call-count-summary-report)** and **[Audio Minutes Summary](#audio-minutes-summary-report)**.</span></span> <span data-ttu-id="fc754-108">以下の説明に記載されているように、ユーザーがドリルダウンレポートを利用すると、[デイリー Usage](#daily-usage)と[地域の音声詳細](#regional-audio-details)レポートが再生されます。</span><span class="sxs-lookup"><span data-stu-id="fc754-108">The [Daily Usage](#daily-usage) and [Regional Audio Details](#regional-audio-details) reports come into play when a user takes advantage of the drill-down reports, noted in the descriptions below.</span></span>

> [!NOTE]
> <span data-ttu-id="fc754-109">地域とネットワークのフィルター処理機能を提供するには、建物およびサブネットデータを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc754-109">Building and subnet data must be populated to provide regional and network filtering capabilities.</span></span>

## <a name="call-count-summary-report"></a><span data-ttu-id="fc754-110">通話カウントの概要レポート</span><span class="sxs-lookup"><span data-stu-id="fc754-110">Call Count Summary Report</span></span>

<span data-ttu-id="fc754-111">メインページ ([通話カウントの概要]) には、セクションタイトルに記載されているように、最後の 30 ~ 90 日間の音声、ビデオ、画面共有セッションの数がすぐに表示されます。</span><span class="sxs-lookup"><span data-stu-id="fc754-111">The main page (Call Count Summary) immediately provides the number of audio, video and screen sharing sessions over the last 30 and 90 days as noted in the section title.</span></span> <span data-ttu-id="fc754-112">最初に表示されるデータは組織全体に対して設定され、ページの左側にある [スライサー] ドロップダウンオプションを使ってフィルター処理することができます。</span><span class="sxs-lookup"><span data-stu-id="fc754-112">The data initially displayed is for the organization as a whole and can be filtered using the slicer dropdown options on the left side of the page.</span></span>

![スクリーンショット: 通話郡の概要レポート](media/CQD-teams-utilization-report1.png)

1. <span data-ttu-id="fc754-114">スライサードロップダウンの右側では、メディアの種類別の呼び出しの数が、過去30日間にわたって内部/外部ビューに分割されます。</span><span class="sxs-lookup"><span data-stu-id="fc754-114">To the right of the slicer dropdowns, the number of calls by media type is broken down to an internal/external view over the past thirty days.</span></span> <span data-ttu-id="fc754-115">上のスクリーンショットでは、組織外の場所からより多くの通話が行われていることを示しています。これは、現在のグローバル環境を考慮していることを意味します。</span><span class="sxs-lookup"><span data-stu-id="fc754-115">We can see through the above screenshot that there are more calls happening from outside organizational locations, which makes sense considering the current global environment.</span></span>
  <span data-ttu-id="fc754-116">![スクリーンショット: 通話郡の概要レポート](media/CQD-teams-utilization-report2.png)</span><span class="sxs-lookup"><span data-stu-id="fc754-116">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report2.png)</span></span>

1. <span data-ttu-id="fc754-117">[メディアの種類のカウント] ボックスの右側には、過去90日間のメディアの種類別の月次通話カウントがあります。</span><span class="sxs-lookup"><span data-stu-id="fc754-117">To the right of the media type count box, we have the Monthly Call Count by Media Type for the last 90 days.</span></span> <span data-ttu-id="fc754-118">各列とメディアの種類をマウスでポイントすると、前月または現在の月の数が表示され、使用傾向の情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="fc754-118">Each column and media type can be hovered over to display the count for a previous month or the current month to date, providing usage trend information.</span></span>
  <span data-ttu-id="fc754-119">![スクリーンショット: 通話郡の概要レポート](media/CQD-teams-utilization-report3.png)</span><span class="sxs-lookup"><span data-stu-id="fc754-119">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report3.png)</span></span>

1. <span data-ttu-id="fc754-120">中央のグラフは、90日間のグラフとして機能しますが、過去30日間の日次利用状況ビューを提供し、ユーザーが右クリックして特定の日の詳細をドリルダウンできるようにします。</span><span class="sxs-lookup"><span data-stu-id="fc754-120">The middle graph functions as the 90-day graph does, however it provides a daily usage view for the past 30 days and allows a user to right click and drill down into details for a specific day.</span></span>
  <span data-ttu-id="fc754-121">![スクリーンショット: 通話郡の概要レポート](media/CQD-teams-utilization-report4.png)</span><span class="sxs-lookup"><span data-stu-id="fc754-121">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report4.png)</span></span>

<span data-ttu-id="fc754-122">ページの左下のセクションでは、過去1年の各メディアの種類の合計値を提供するテーブルが見つかります。</span><span class="sxs-lookup"><span data-stu-id="fc754-122">On the bottom left section of the page, you'll find a table providing total values for each media type over the past year.</span></span> 
    <span data-ttu-id="fc754-123">![スクリーンショット: 通話郡の概要レポート](media/CQD-teams-utilization-report5.png)</span><span class="sxs-lookup"><span data-stu-id="fc754-123">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report5.png)</span></span>
  
<span data-ttu-id="fc754-124">また、テーブルには、地域データの分類を表示できるドリルダウンもあります。</span><span class="sxs-lookup"><span data-stu-id="fc754-124">The table also has an available drill down where you can see a regional data breakdown.</span></span>
    <span data-ttu-id="fc754-125">![スクリーンショット: 通話郡の概要レポート](media/CQD-teams-utilization-report6.png)</span><span class="sxs-lookup"><span data-stu-id="fc754-125">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report6.png)</span></span>

<span data-ttu-id="fc754-126">テーブルの右側にある棒グラフには、過去30日間に最も頻繁に使用されているクライアント (通話/ストリーム) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fc754-126">To the right of the table, a bar chart shows clients with the most use (calls/streams) for the past 30 days.</span></span>
   <span data-ttu-id="fc754-127">![スクリーンショット: 通話郡の概要レポート](media/CQD-teams-utilization-report7.png)</span><span class="sxs-lookup"><span data-stu-id="fc754-127">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report7.png)</span></span>


<span data-ttu-id="fc754-128">このページの最後のグラフセットでは、各メディアの種類が個別に表示され、会議と P2P の使用状況を示すブレークダウンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fc754-128">The last set of charts for this page show each media type individually, with a breakdown showing conference and P2P usage.</span></span> <span data-ttu-id="fc754-129">以下の図は、P2P と比較した場合の会議の利用回数が非常に多いことを示しています。</span><span class="sxs-lookup"><span data-stu-id="fc754-129">The charts below show that there is a significantly higher number of conference usage as compared to P2P.</span></span>
  <span data-ttu-id="fc754-130">![スクリーンショット: 通話郡の概要レポート](media/CQD-teams-utilization-report8.png)</span><span class="sxs-lookup"><span data-stu-id="fc754-130">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report8.png)</span></span>

## <a name="audio-minutes-summary-report"></a><span data-ttu-id="fc754-131">オーディオ分のサマリーレポート</span><span class="sxs-lookup"><span data-stu-id="fc754-131">Audio Minutes Summary Report</span></span>

<span data-ttu-id="fc754-132">[オーディオ時間の利用状況] レポートでは、合計分使用量がいくつかの異なるビューで提供されます。</span><span class="sxs-lookup"><span data-stu-id="fc754-132">On the Audio Minutes usage report, the total minute usage is provided through a few different views.</span></span> 

<span data-ttu-id="fc754-133">スライサーの隣には、テキストボックスを簡単に利用できるように、30日間の使用状況の概要が表示されています。</span><span class="sxs-lookup"><span data-stu-id="fc754-133">We have the thirty-day usage summary shown next to the slicers as easy to consume text boxes.</span></span> <span data-ttu-id="fc754-134">上部の番号には、その下に内部と外部の内訳が表示された、30日間の合計が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fc754-134">The top number shows the thirty-day total, with internal and external breakdowns below that.</span></span>

![スクリーンショット: 通話郡の概要レポート](media/CQD-teams-utilization-report9.png)

<span data-ttu-id="fc754-136">右上の棒グラフでは、電話会議の音声使用状況が yearlong で表示されます。</span><span class="sxs-lookup"><span data-stu-id="fc754-136">The top right bar graph provides a yearlong view of conference audio usage.</span></span> <span data-ttu-id="fc754-137">月をポイントすると、会議の音声通話時間が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fc754-137">Hover over the month to show the conference audio minutes.</span></span>

<span data-ttu-id="fc754-138">P2P と会議の音声の違いを示すために、左下のグラフはすべてのオーディオを過去の年に向けて受け取り、2つの種類の間で分割します。</span><span class="sxs-lookup"><span data-stu-id="fc754-138">To show the difference in P2P and conference audio, the bottom left chart takes all audio for the past year and breaks it up between the two types.</span></span>

<span data-ttu-id="fc754-139">![スクリーンショット: 通話先の](media/CQD-teams-utilization-report10.png)通話先の [分間のサマリー] ページの最後のグラフには、グローバルマップオーバーレイでのオーディオ分の使用状況が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fc754-139">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report10.png) The last chart for the Audio minutes page shows audio minute usage on a global map overlay.</span></span> <span data-ttu-id="fc754-140">このグラフは、構築およびサブネットデータがテナントにアップロードされた場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="fc754-140">This chart will only work if building and subnet data is uploaded to the tenant.</span></span> <span data-ttu-id="fc754-141">地図上の円グラフのオーバーレイを表示して、その後で地域のオーディオ使用法を提供できます。</span><span class="sxs-lookup"><span data-stu-id="fc754-141">The pie chart overlay on the map can be drilled into, subsequently providing regional audio usage.</span></span>

![スクリーンショット: 通話郡の概要レポート](media/CQD-teams-utilization-report11.png)

## <a name="drill-through-capabilities"></a><span data-ttu-id="fc754-143">ドリルスルー機能</span><span class="sxs-lookup"><span data-stu-id="fc754-143">Drill-through capabilities</span></span>

<span data-ttu-id="fc754-144">前に説明したように、ユーザーは日単位および地域の利用状況レポートについて詳しく調べることができます。</span><span class="sxs-lookup"><span data-stu-id="fc754-144">As previously noted, users can drill into the daily and regional usage reports.</span></span>

### <a name="daily-usage"></a><span data-ttu-id="fc754-145">日常的な利用状況</span><span class="sxs-lookup"><span data-stu-id="fc754-145">Daily Usage</span></span>

<span data-ttu-id="fc754-146">日次利用状況レポートを使用すると、管理者は1日の間にピークの消費期間を特定できます。</span><span class="sxs-lookup"><span data-stu-id="fc754-146">The Daily Usage report allows an administrator to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="fc754-147">利用状況に加えて、その日の全体的なユーザー感情とフィードバックをキャプチャすることもできます。</span><span class="sxs-lookup"><span data-stu-id="fc754-147">In addition to usage, we are also able to capture overall user sentiment and feedback for that day.</span></span>

![スクリーンショット: 通話郡の概要レポート](media/CQD-teams-utilization-report12.png)

<span data-ttu-id="fc754-149">このデータは、消費時間のピーク時に問題が発生した地域を特定するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="fc754-149">This data can be used to identify regions having problems during peak consumption times.</span></span>

1.  <span data-ttu-id="fc754-150">[通話カウントの概要] ページで、特定の日にドリルスルーします。</span><span class="sxs-lookup"><span data-stu-id="fc754-150">On the Call Count Summary page, drill-through on a specific date.</span></span> <span data-ttu-id="fc754-151">その日の1時間の傾向を確認して、ピーク使用率を確認します。</span><span class="sxs-lookup"><span data-stu-id="fc754-151">Look at the hourly trend that day to find the peak utilization.</span></span>
  <span data-ttu-id="fc754-152">![スクリーンショット: 通話郡の概要レポート](media/CQD-teams-utilization-report13.png)</span><span class="sxs-lookup"><span data-stu-id="fc754-152">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report13.png)</span></span>

2.  <span data-ttu-id="fc754-153">その日の列をクリックして、その時間の指標を表示します。</span><span class="sxs-lookup"><span data-stu-id="fc754-153">Click on the column for that day to display metrics for that hour.</span></span>
  <span data-ttu-id="fc754-154">![スクリーンショット: 通話郡の概要レポート](media/CQD-teams-utilization-report14.png)</span><span class="sxs-lookup"><span data-stu-id="fc754-154">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report14.png)</span></span>
    
    1.  <span data-ttu-id="fc754-155">グラフの下の表には、その時間の測度が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fc754-155">The table below the chart will display the metrics for that hour.</span></span> <span data-ttu-id="fc754-156">これは、任意の列見出しを基準にして並べ替えることができます。ただし、問題のある領域を見つけることに関心を持っています。</span><span class="sxs-lookup"><span data-stu-id="fc754-156">This can be sorted by any column header; however, we would be interested in finding problematic areas.</span></span>  
        ![スクリーンショット: 通話郡の概要レポート](media/CQD-teams-utilization-report15.png)
    
    2.  <span data-ttu-id="fc754-158">この期間中の会議では、IND 領域のビデオパフォーマンスが低下していることがわかります。</span><span class="sxs-lookup"><span data-stu-id="fc754-158">We see that the IND region is experiencing poor video performance in conferences during this time frame.</span></span> <span data-ttu-id="fc754-159">その後、CQD QER Microsoft レポートを使って、地域と時間のフレームが識別されたために、問題のある場所を絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="fc754-159">Subsequently, the CQD QER Microsoft reports can be used to narrow down the problematic location as the region and time frame has been identified.</span></span>

### <a name="regional-audio-details"></a><span data-ttu-id="fc754-160">地域の音声の詳細</span><span class="sxs-lookup"><span data-stu-id="fc754-160">Regional Audio Details</span></span>

<span data-ttu-id="fc754-161">[地域のオーディオ詳細] のドリルダウンでは、選択した地域の音声分の使用状況が具体的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="fc754-161">The Regional Audio Details drill down specifically shows the audio minute usage for the selected region.</span></span> <span data-ttu-id="fc754-162">CQD へのアクセス権を持つユーザーは、選択した地域内の P2P と会議のオーディオの使用状況の傾向を確認できます。</span><span class="sxs-lookup"><span data-stu-id="fc754-162">Users with access to CQD can see usage trends for both P2P and conference audio within the selected region.</span></span>

1.  <span data-ttu-id="fc754-163">[通話カウントの概要] ページで、表を通じて特定の地域にドリルダウンします。</span><span class="sxs-lookup"><span data-stu-id="fc754-163">On the Call Count Summary page, drill-through to as specific region through the table.</span></span>
  <span data-ttu-id="fc754-164">![スクリーンショット: 通話郡の概要レポート](media/CQD-teams-utilization-report16.png)</span><span class="sxs-lookup"><span data-stu-id="fc754-164">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report16.png)</span></span>

2.  <span data-ttu-id="fc754-165">領域の追加情報が必要な行を選択します。</span><span class="sxs-lookup"><span data-stu-id="fc754-165">Select the row with the region additional information is needed for.</span></span>
  <span data-ttu-id="fc754-166">![スクリーンショット: 通話郡の概要レポート](media/CQD-teams-utilization-report17.png)</span><span class="sxs-lookup"><span data-stu-id="fc754-166">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report17.png)</span></span>

3.  <span data-ttu-id="fc754-167">データの傾向は、内部ネットワークで利用されている長い時間 (分単位) を示しています。これには、surpassing が P2P を使用しています。</span><span class="sxs-lookup"><span data-stu-id="fc754-167">The data trends show a significant number of minutes being used on the internal network, with conferencing far surpassing P2P use.</span></span>
  <span data-ttu-id="fc754-168">![スクリーンショット: 通話郡の概要レポート](media/CQD-teams-utilization-report18.png)</span><span class="sxs-lookup"><span data-stu-id="fc754-168">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report18.png)</span></span>

<span data-ttu-id="fc754-169">地域オーディオの傾向を使って、世界中の外部の影響によってユーザーがどのように影響を受けるかを示すことができます。</span><span class="sxs-lookup"><span data-stu-id="fc754-169">The regional audio trend can be used to show how users are impacted by external influences in the world.</span></span> <span data-ttu-id="fc754-170">具体的には、この時点で、ユーザーがリモートで作業することを求められる場合に、EMEA と APAC 地域の外部使用が表示されることを想定しています。</span><span class="sxs-lookup"><span data-stu-id="fc754-170">Specifically, right now, we would expect to see the external usage for the EMEA and APAC regions to increase with people being asked to work remotely.</span></span>



## <a name="related-topics"></a><span data-ttu-id="fc754-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="fc754-171">Related topics</span></span>

[<span data-ttu-id="fc754-172">通話品質ダッシュボードで利用できるディメンションとメジャー</span><span class="sxs-lookup"><span data-stu-id="fc754-172">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="fc754-173">通話品質ダッシュボードでのストリームの分類</span><span class="sxs-lookup"><span data-stu-id="fc754-173">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="fc754-174">Skype for Business の通話分析をセットアップする</span><span class="sxs-lookup"><span data-stu-id="fc754-174">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="fc754-175">通話分析を使用して低品質の通話をトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="fc754-175">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="fc754-176">通話分析および通話品質ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="fc754-176">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)
 