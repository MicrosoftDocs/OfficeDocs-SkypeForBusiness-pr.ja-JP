---
title: CQD データを使用して Power BI で Microsoft Teams の使用率を表示する
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Teams 使用率 Power BI レポートを使用して、Microsoft Teams 通話品質ダッシュボード (CQD) データにアクセスし、組織内での Microsoft Teams の使用状況を追跡します。
ms.openlocfilehash: 719f02ce7a5cd36e96ed7fd563c259c6e77764fd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095041"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a><span data-ttu-id="afbff-103">CQD データを使用して Power BI で Microsoft Teams の使用率を表示する</span><span class="sxs-lookup"><span data-stu-id="afbff-103">View Microsoft Teams utilization in Power BI using CQD data</span></span>

<span data-ttu-id="afbff-104">2020 年 3 月の新機能として [、CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)用のダウンロード可能な Power BI クエリ テンプレートに Teams 使用率レポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="afbff-104">New in March 2020, we've added a Teams Utilization report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 

<span data-ttu-id="afbff-105">この新しい Teams 使用率レポートでは、Teams 通話品質ダッシュボード (CQD) データにアクセスして、ユーザーが Microsoft Teams を使用している方法 (およびどのくらい) を確認できます。</span><span class="sxs-lookup"><span data-stu-id="afbff-105">This new Teams Utilization reports lets you see how (and how much) your users are using Microsoft Teams by accessing Teams Call Quality Dashboard (CQD) data.</span></span> <span data-ttu-id="afbff-106">これらのレポートは、管理者とビジネス リーダーの両方が、このデータにすばやくアクセスできる一元管理された場所を目的としています。</span><span class="sxs-lookup"><span data-stu-id="afbff-106">These reports are intended to be a centralized location that both administrators and business leaders can quickly go to for this data.</span></span>

<span data-ttu-id="afbff-107">Teams 使用率 Power BI レポートは、通話カウント **[](#call-count-summary-report)** の概要と音声通話分数の概要という 2 つの主要なレポート **[で構成されます](#audio-minutes-summary-report)**。</span><span class="sxs-lookup"><span data-stu-id="afbff-107">The Teams Utilization Power BI report consists of two primary reports: **[Call Count Summary](#call-count-summary-report)** and **[Audio Minutes Summary](#audio-minutes-summary-report)**.</span></span> <span data-ttu-id="afbff-108">次[の](#daily-usage)[説明に示](#regional-audio-details)すドリルダウン[](#conference-details)レポートをユーザー[](#user-list)が利用すると、[毎日の使用状況]、[地域の音声の詳細]、[電話会議の詳細]、および [ユーザー リスト] レポートが再生されます。</span><span class="sxs-lookup"><span data-stu-id="afbff-108">The [Daily Usage](#daily-usage), [Regional Audio Details](#regional-audio-details), [Conference Details](#conference-details) and [User List](#user-list) reports come into play when a user takes advantage of the drill-down reports, noted in the descriptions below.</span></span>

> [!NOTE]
> <span data-ttu-id="afbff-109">地域とネットワークのフィルター機能を提供するには、建物とサブネットのデータを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="afbff-109">Building and subnet data must be populated to provide regional and network filtering capabilities.</span></span>

## <a name="call-count-summary-report"></a><span data-ttu-id="afbff-110">通話数の概要レポート</span><span class="sxs-lookup"><span data-stu-id="afbff-110">Call Count Summary Report</span></span>

<span data-ttu-id="afbff-111">メイン ページ (通話カウントの概要) では、セクション タイトルに示されている過去 30 日間と 90 日間の音声、ビデオ、画面共有セッションの数がすぐに表示されます。</span><span class="sxs-lookup"><span data-stu-id="afbff-111">The main page (Call Count Summary) immediately provides the number of audio, video and screen sharing sessions over the last 30 and 90 days as noted in the section title.</span></span> <span data-ttu-id="afbff-112">最初に表示されるデータは組織全体を表し、ページの左側にあるスライサードロップダウン オプションを使用してフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="afbff-112">The data initially displayed is for the organization as a whole and can be filtered using the slicer dropdown options on the left side of the page.</span></span>

![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report1.png)

1. <span data-ttu-id="afbff-114">スライサーのドロップダウンの右側では、メディアの種類別の通話数は、過去 30 日間の内部ビューまたは外部ビューに分解されます。</span><span class="sxs-lookup"><span data-stu-id="afbff-114">To the right of the slicer dropdowns, the number of calls by media type is broken down to an internal/external view over the past thirty days.</span></span> <span data-ttu-id="afbff-115">上のスクリーンショットを見て、組織の外部からの通話が多く発生しているのを確認できます。これは、現在のグローバル環境を考慮すると理にかなっています。</span><span class="sxs-lookup"><span data-stu-id="afbff-115">We can see through the above screenshot that there are more calls happening from outside organizational locations, which makes sense considering the current global environment.</span></span>
  <span data-ttu-id="afbff-116">![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report2.png)</span><span class="sxs-lookup"><span data-stu-id="afbff-116">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report2.png)</span></span>

1. <span data-ttu-id="afbff-117">メディアの種類数ボックスの右側には、過去 90 日間のメディアの種類別の月間通話数があります。</span><span class="sxs-lookup"><span data-stu-id="afbff-117">To the right of the media type count box, we have the Monthly Call Count by Media Type for the last 90 days.</span></span> <span data-ttu-id="afbff-118">各列とメディアの種類をマウスでポイントすると、前月または現在の月の数が表示され、使用状況の傾向情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="afbff-118">Each column and media type can be hovered over to display the count for a previous month or the current month to date, providing usage trend information.</span></span>
  <span data-ttu-id="afbff-119">![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report3.png)</span><span class="sxs-lookup"><span data-stu-id="afbff-119">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report3.png)</span></span>
 

1. <span data-ttu-id="afbff-120">中央のグラフは 90 日間のグラフと同様に機能しますが、過去 30 日間の毎日の利用状況ビューが提供され、ユーザーは特定の日の詳細を右クリックしてドリルダウンできます。</span><span class="sxs-lookup"><span data-stu-id="afbff-120">The middle graph functions as the 90-day graph does, however it provides a daily usage view for the past 30 days and allows a user to right click and drill down into details for a specific day.</span></span>
  <span data-ttu-id="afbff-121">![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report4.png)</span><span class="sxs-lookup"><span data-stu-id="afbff-121">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report4.png)</span></span>

<span data-ttu-id="afbff-122">ページの左下のセクションには、過去 1 年間のメディアの種類ごとに合計値を提供するテーブルがあります。</span><span class="sxs-lookup"><span data-stu-id="afbff-122">On the bottom left section of the page, you'll find a table providing total values for each media type over the past year.</span></span> 
    <span data-ttu-id="afbff-123">![スクリーンショット: Teams 使用率レポート ](media/CQD-teams-utilization-report5.png) ![ のスクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report6.png)</span><span class="sxs-lookup"><span data-stu-id="afbff-123">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report5.png) ![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report6.png)</span></span>   

<span data-ttu-id="afbff-124">表の右側には、過去 30 日間のクライアントが最も多く使用されている (通話/ストリーム) が棒グラフに表示されます。</span><span class="sxs-lookup"><span data-stu-id="afbff-124">To the right of the table, a bar chart shows clients with the most use (calls/streams) for the past 30 days.</span></span>
   <span data-ttu-id="afbff-125">![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report7.png)</span><span class="sxs-lookup"><span data-stu-id="afbff-125">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report7.png)</span></span>

<span data-ttu-id="afbff-126">このページの最後のグラフ セットでは、各メディアの種類が個別に表示され、内訳には電話会議と P2P の使用状況が表示されます。</span><span class="sxs-lookup"><span data-stu-id="afbff-126">The last set of charts for this page show each media type individually, with a breakdown showing conference and P2P usage.</span></span> <span data-ttu-id="afbff-127">次のグラフは、P2P と比較して、電話会議の使用状況の数が非常に多い場合を示しています。</span><span class="sxs-lookup"><span data-stu-id="afbff-127">The charts below show that there is a significantly higher number of conference usage as compared to P2P.</span></span>
  <span data-ttu-id="afbff-128">![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report8.png)</span><span class="sxs-lookup"><span data-stu-id="afbff-128">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report8.png)</span></span>

## <a name="audio-minutes-summary-report"></a><span data-ttu-id="afbff-129">Audio Minutes Summary Report</span><span class="sxs-lookup"><span data-stu-id="afbff-129">Audio Minutes Summary Report</span></span>

<span data-ttu-id="afbff-130">オーディオ分数の使用状況レポートでは、分の合計使用量がいくつかの異なるビューで提供されます。</span><span class="sxs-lookup"><span data-stu-id="afbff-130">On the Audio Minutes usage report, the total minute usage is provided through a few different views.</span></span> 

<span data-ttu-id="afbff-131">スライサーの横に、テキスト ボックスを簡単に使用できる 30 日間の使用状況の概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="afbff-131">We have the thirty-day usage summary shown next to the slicers as easy to consume text boxes.</span></span> <span data-ttu-id="afbff-132">上位の数値は 30 日間の合計を示し、内部と外部の内訳が下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="afbff-132">The top number shows the thirty-day total, with internal and external breakdowns below that.</span></span>

![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report9.png)

<span data-ttu-id="afbff-134">上の右の棒グラフは、電話会議の音声使用状況を 1 年間表示します。</span><span class="sxs-lookup"><span data-stu-id="afbff-134">The top right bar graph provides a yearlong view of conference audio usage.</span></span> <span data-ttu-id="afbff-135">月の上にマウス ポインターを置くと、会議の音声の分数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="afbff-135">Hover over the month to show the conference audio minutes.</span></span>

<span data-ttu-id="afbff-136">P2P と電話会議の音声の違いを示す左下のグラフは、過去 1 年間のすべての音声を取得し、2 つの種類の間で分解します。</span><span class="sxs-lookup"><span data-stu-id="afbff-136">To show the difference in P2P and conference audio, the bottom left chart takes all audio for the past year and breaks it up between the two types.</span></span>

![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report10.png)

<span data-ttu-id="afbff-138">[オーディオ分数] ページの最後のグラフには、グローバル マップ オーバーレイでの音声の分の使用状況が表示されます。</span><span class="sxs-lookup"><span data-stu-id="afbff-138">The last chart for the Audio minutes page shows audio minute usage on a global map overlay.</span></span> <span data-ttu-id="afbff-139">このグラフは、建物とサブネットのデータがテナントにアップロードされた場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="afbff-139">This chart will only work if building and subnet data is uploaded to the tenant.</span></span> <span data-ttu-id="afbff-140">マップ上の円グラフのオーバーレイを詳細に表示し、その後で地域の音声を使用できます。</span><span class="sxs-lookup"><span data-stu-id="afbff-140">The pie chart overlay on the map can be drilled into, subsequently providing regional audio usage.</span></span>

![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report11.png)


## <a name="drill-through-capabilities"></a><span data-ttu-id="afbff-142">ドリルスルー機能</span><span class="sxs-lookup"><span data-stu-id="afbff-142">Drill-through capabilities</span></span>

<span data-ttu-id="afbff-143">前に説明した通り、ユーザーは日次および地域の使用状況レポートを詳細に表示できます。</span><span class="sxs-lookup"><span data-stu-id="afbff-143">As previously noted, users can drill into the daily and regional usage reports.</span></span>

### <a name="daily-usage"></a><span data-ttu-id="afbff-144">1 日の使用状況</span><span class="sxs-lookup"><span data-stu-id="afbff-144">Daily Usage</span></span>

<span data-ttu-id="afbff-145">[毎日の使用状況] レポートを使用すると、管理者は 1 日の間に最大使用時間を特定できます。</span><span class="sxs-lookup"><span data-stu-id="afbff-145">The Daily Usage report allows an administrator to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="afbff-146">また、使用状況に加えて、その日の全体的なユーザー の感情やフィードバックも取り込む可能性があります。</span><span class="sxs-lookup"><span data-stu-id="afbff-146">In addition to usage, we are also able to capture overall user sentiment and feedback for that day.</span></span>

![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report12.png)

<span data-ttu-id="afbff-148">[毎日の使用状況] レポートには、選択した日のオーディオ、ビデオ、画面共有の数が表示され、内部接続と外部接続を区別する機能が追加されます。</span><span class="sxs-lookup"><span data-stu-id="afbff-148">The Daily usage report displays the number of Audio, Video and Screen shares for the selected day with the added ability to differentiate between internal and external connectivity.</span></span> <span data-ttu-id="afbff-149">会議およびピアツーピアのブレークダウンは、モーダル合計ボックスの右側に表示されます。</span><span class="sxs-lookup"><span data-stu-id="afbff-149">A Conference and Peer to Peer breakdown is to the immediate right of the modality total box.</span></span> <span data-ttu-id="afbff-150">レポートの上部の右側には、その日の関連付けられた ID と参加者を含む電話会議の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="afbff-150">The top right of the report provides a list of conferences with their associated ID and participants for the day.</span></span> <span data-ttu-id="afbff-151">電話会議リストには、電話会議の詳細レポートのドリルダウンが追加で表示されます。</span><span class="sxs-lookup"><span data-stu-id="afbff-151">The conference list provides an additional drill down to the Conference Details report as well.</span></span> <span data-ttu-id="afbff-152">グラフィックを置き換える</span><span class="sxs-lookup"><span data-stu-id="afbff-152">REPLACE GRAPHIC</span></span>

![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report13.png)

<span data-ttu-id="afbff-154">中央の領域の棒グラフを使用すると、ユーザーは 1 日の間にピーク時の消費期間を特定できます。</span><span class="sxs-lookup"><span data-stu-id="afbff-154">The bar graph in the center area allows the user to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="afbff-155">ユーザーは、グラフに表示される時間をドリルダウンして、その時間のユーザー リスト レポートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="afbff-155">Users may drill down into the hour represented on the graph which will present the User List report for the hour.</span></span>

<span data-ttu-id="afbff-156">棒グラフの右側には、ユーザー フィードバックが視覚的な形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="afbff-156">To the right of the bar graph, User Feedback is presented in a visual format.</span></span> <span data-ttu-id="afbff-157">ユーザーの感情は主観的な場合がある一方で、潜在的な問題を特定するために使用できる洞察を提供します。</span><span class="sxs-lookup"><span data-stu-id="afbff-157">While user sentiment can be subjective, it does provide insight that can be used to identify potential issues.</span></span>

<span data-ttu-id="afbff-158">下の表には、その日のメトリックの範囲が表示されます。</span><span class="sxs-lookup"><span data-stu-id="afbff-158">The bottom table provides a range of metrics for the day.</span></span> <span data-ttu-id="afbff-159">低品質のパーセンテージと障害率は、管理者に改善の可能性がある領域を提供する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="afbff-159">Poor percentages along with failure rates can provide an administrator with potential areas of improvement.</span></span> <span data-ttu-id="afbff-160">次に示すように、各時間を個別に選択できます。</span><span class="sxs-lookup"><span data-stu-id="afbff-160">Each hour can also be selected individually as shown below.</span></span>

<span data-ttu-id="afbff-161">このデータは、ピーク時に問題がある地域を特定するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="afbff-161">This data can be used to identify regions having problems during peak consumption times.</span></span>


<span data-ttu-id="afbff-162">その日の列をクリックすると、その時間のメトリックが表示されます。</span><span class="sxs-lookup"><span data-stu-id="afbff-162">Click on the column for that day to display metrics for that hour.</span></span>
<span data-ttu-id="afbff-163">![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report14.png)</span><span class="sxs-lookup"><span data-stu-id="afbff-163">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report14.png)</span></span>
  
  1.  <span data-ttu-id="afbff-164">グラフの下の表には、その時間のメトリックが表示されます。</span><span class="sxs-lookup"><span data-stu-id="afbff-164">The table below the chart will display the metrics for that hour.</span></span> <span data-ttu-id="afbff-165">任意の列見出しで並べ替えを行います。ただし、問題のある領域を見つけることに関心があります。</span><span class="sxs-lookup"><span data-stu-id="afbff-165">This can be sorted by any column header; however, we would be interested in finding problematic areas.</span></span>  
    ![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report15.png)
    
  2.  <span data-ttu-id="afbff-167">IND 地域では、この期間中の電話会議でのビデオパフォーマンスが低下しています。</span><span class="sxs-lookup"><span data-stu-id="afbff-167">We see that the IND region is experiencing poor video performance in conferences during this time frame.</span></span> <span data-ttu-id="afbff-168">その後、CQD QER Microsoft レポートを使用して、領域と時間枠が特定されると、問題のある場所を絞り込む可能性があります。</span><span class="sxs-lookup"><span data-stu-id="afbff-168">Subsequently, the CQD QER Microsoft reports can be used to narrow down the problematic location as the region and time frame has been identified.</span></span>

### <a name="conference-details"></a><span data-ttu-id="afbff-169">電話会議の詳細</span><span class="sxs-lookup"><span data-stu-id="afbff-169">Conference Details</span></span>

<span data-ttu-id="afbff-170">会議の詳細レポートでは、出席者リストからセッション中に使用されるメディアの種類まで、会議に関する追加の分析情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="afbff-170">The Conference Details report provides additional insight for meetings, from an attendee list, to the media types used during the session.</span></span>

<span data-ttu-id="afbff-171">[毎日の利用状況] ページの会議 ID グラフの参加者バーを右クリックして、会議の詳細をドリルダウンします。</span><span class="sxs-lookup"><span data-stu-id="afbff-171">Right click a conference the participant bar in the conference ID chart on the Daily usage page to drill down into the conference details.</span></span>

![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report24.png)

![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report25.png)
  

<span data-ttu-id="afbff-174">会議の参加者だけでなく、すべての関連情報をパケット損失とジッターにまで表示して、下の表のトラブルシューティング作業の可能性を支援できます。</span><span class="sxs-lookup"><span data-stu-id="afbff-174">We can see the participants in the conference as well as all the pertinent information down to packet loss and jitter to assist with potential troubleshooting efforts in the bottom table.</span></span>

![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report26.png)


### <a name="regional-audio-details"></a><span data-ttu-id="afbff-176">地域の音声の詳細</span><span class="sxs-lookup"><span data-stu-id="afbff-176">Regional Audio Details</span></span>

<span data-ttu-id="afbff-177">地域のオーディオの詳細のドリルダウンには、選択した地域の音声分の使用状況が具体的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="afbff-177">The Regional Audio Details drill down specifically shows the audio minute usage for the selected region.</span></span> <span data-ttu-id="afbff-178">CQD にアクセスできるユーザーは、選択した地域内の P2P と電話会議の音声の両方の使用状況の傾向を確認できます。</span><span class="sxs-lookup"><span data-stu-id="afbff-178">Users with access to CQD can see usage trends for both P2P and conference audio within the selected region.</span></span>

1.  <span data-ttu-id="afbff-179">[通話カウントの概要] ページで、テーブル内の特定の領域にドリルスルーします。</span><span class="sxs-lookup"><span data-stu-id="afbff-179">On the Call Count Summary page, drill-through to as specific region through the table.</span></span>
  <span data-ttu-id="afbff-180">![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report16.png)</span><span class="sxs-lookup"><span data-stu-id="afbff-180">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report16.png)</span></span>

2.  <span data-ttu-id="afbff-181">追加情報が必要な領域を含む行を選択します。</span><span class="sxs-lookup"><span data-stu-id="afbff-181">Select the row with the region additional information is needed for.</span></span>
  <span data-ttu-id="afbff-182">![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report17.png)</span><span class="sxs-lookup"><span data-stu-id="afbff-182">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report17.png)</span></span>

3.  <span data-ttu-id="afbff-183">データの傾向は、内部ネットワークで使用されている分数が非常に多く、会議は P2P の使用をはるかに上回っています。</span><span class="sxs-lookup"><span data-stu-id="afbff-183">The data trends show a significant number of minutes being used on the internal network, with conferencing far surpassing P2P use.</span></span>
  <span data-ttu-id="afbff-184">![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report18.png)</span><span class="sxs-lookup"><span data-stu-id="afbff-184">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report18.png)</span></span>

<span data-ttu-id="afbff-185">地域の音声傾向は、ユーザーが世界の外部影響の影響を受ける方法を示す場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="afbff-185">The regional audio trend can be used to show how users are impacted by external influences in the world.</span></span> <span data-ttu-id="afbff-186">具体的には、現在、EMEA 地域と APAC 地域の外部使用量が増加し、リモートで作業を求める人々が増える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="afbff-186">Specifically, right now, we would expect to see the external usage for the EMEA and APAC regions to increase with people being asked to work remotely.</span></span>


### <a name="user-list"></a><span data-ttu-id="afbff-187">ユーザー リスト</span><span class="sxs-lookup"><span data-stu-id="afbff-187">User List</span></span>

<span data-ttu-id="afbff-188">ユーザー リストのドリルダウンでは、予想される方法として、レポートを表示しているユーザーが選択した特定の時間のユーザー固有の情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="afbff-188">The User List drill down provides, as one might expect, user specific information for a specific hour selected by the person viewing the report.</span></span> <span data-ttu-id="afbff-189">ユーザー リスト レポートには、[毎日の使用状況] レポートの [時間別傾向] グラフのドリルダウンを使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="afbff-189">The User List report is accessible through a drill down in the Hourly Trends graph on the Daily Usage report.</span></span> <span data-ttu-id="afbff-190">次に示すように、追加情報が必要な時間を右クリックし、[ドリルスルーとユーザー リスト] を選択します。</span><span class="sxs-lookup"><span data-stu-id="afbff-190">Right click on the hour additional information is needed for and select Drill through and User List, as shown below.</span></span>

![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report19.png)

<span data-ttu-id="afbff-192">ユーザー リスト レポートには、ページの上部中央にあるドーナツ グラフを介した内部または外部の接続が表示されます。</span><span class="sxs-lookup"><span data-stu-id="afbff-192">The User List report shows internal/external connectivity through the doughnut chart in the top center of the page.</span></span> <span data-ttu-id="afbff-193">次の画像では、企業ネットワークの外部からの大量の参加が見受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="afbff-193">We can see that there is a large amount of participation from Outside the corporate network in the below image.</span></span>

<span data-ttu-id="afbff-194">グラフの上の右には、その時間内に各ユーザーによって行われた通話の数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="afbff-194">The top right of the graph shows the number of calls made by each user within that hour.</span></span>

![スクリーンショット: Teams 使用率レポート](media/CQD-teams-utilization-report20.png)

<span data-ttu-id="afbff-196">下の表は、各ユーザーがその時間に参加したセッションの詳細情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="afbff-196">The bottom table provides detailed information for the sessions each user participated in during that hour.</span></span> <span data-ttu-id="afbff-197">[エラーの種類] 列は、呼び出しがドロップされる原因を特定する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="afbff-197">The Failure Type column is useful in determining what caused a call to drop.</span></span> <span data-ttu-id="afbff-198">キャプチャとレンダリング デバイスの列は、通話が低品質と報告された理由を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="afbff-198">The Capture and Render Device columns are useful in identifying why a call was reported having poor quality.</span></span>


## <a name="related-topics"></a><span data-ttu-id="afbff-199">関連項目</span><span class="sxs-lookup"><span data-stu-id="afbff-199">Related topics</span></span>

[<span data-ttu-id="afbff-200">通話品質ダッシュボードで利用できるディメンションとメジャー</span><span class="sxs-lookup"><span data-stu-id="afbff-200">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="afbff-201">通話品質ダッシュボードでのストリームの分類</span><span class="sxs-lookup"><span data-stu-id="afbff-201">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="afbff-202">Skype for Business の通話分析をセットアップする</span><span class="sxs-lookup"><span data-stu-id="afbff-202">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="afbff-203">通話分析を使用して低品質の通話をトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="afbff-203">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="afbff-204">通話分析および通話品質ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="afbff-204">Call Analytics and Call Quality Dashboard</span></span>](./monitor-call-quality-qos.md)

[<span data-ttu-id="afbff-205">Teams のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="afbff-205">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
