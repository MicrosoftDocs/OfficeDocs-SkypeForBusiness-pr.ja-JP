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
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Teams 使用率の Power BI レポートを使って、組織での Microsoft Teams の利用状況を追跡します。
ms.openlocfilehash: efca39a89eecdf9d603a81a07d8529147f87698a
ms.sourcegitcommit: 4d376449a75928282373598647f2b82127909c4f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2020
ms.locfileid: "42978556"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a><span data-ttu-id="bd92f-103">CQD のデータを使用して、Power BI で Microsoft Teams の使用率を表示する</span><span class="sxs-lookup"><span data-stu-id="bd92f-103">View Microsoft Teams utilization in Power BI using CQD data</span></span>

<span data-ttu-id="bd92f-104">2020年3月に初めて、CQD のダウンロード可能な[POWER BI クエリテンプレート](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)に Teams の使用状況レポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="bd92f-104">New in March 2020, we've added a Teams Utilization report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 

<span data-ttu-id="bd92f-105">この新しいチームの使用状況レポートでは、ユーザーが Microsoft Teams を使用している方法 (およびその程度) を確認できます。</span><span class="sxs-lookup"><span data-stu-id="bd92f-105">This new Teams Utilization reports lets you see how (and how much) your users are using Microsoft Teams.</span></span> <span data-ttu-id="bd92f-106">これらのレポートは、管理者とビジネスリーダーの両方がこのデータにすばやくアクセスできる一元的な場所です。</span><span class="sxs-lookup"><span data-stu-id="bd92f-106">These reports are intended to be a centralized location that both administrators and business leaders can quickly go to for this data.</span></span>

<span data-ttu-id="bd92f-107">Teams 使用率 Power BI レポートは、2つの主要なレポートで構成されています。**[通話カウントの概要](#call-count-summary-report)** と**[音声分の概要](#audio-minutes-summary-report)**。</span><span class="sxs-lookup"><span data-stu-id="bd92f-107">The Teams Utilization Power BI report consists of two primary reports: **[Call Count Summary](#call-count-summary-report)** and **[Audio Minutes Summary](#audio-minutes-summary-report)**.</span></span> <span data-ttu-id="bd92f-108">ユーザーがドリルダウンレポートを利用すると、次の説明に記載されているように、[日常の利用状況](#daily-usage)、[地域の音声の詳細](#regional-audio-details)、会議の[詳細](#conference-details)、[ユーザー一覧](#user-list)のレポートが再生されます。</span><span class="sxs-lookup"><span data-stu-id="bd92f-108">The [Daily Usage](#daily-usage), [Regional Audio Details](#regional-audio-details), [Conference Details](#conference-details) and [User List](#user-list) reports come into play when a user takes advantage of the drill-down reports, noted in the descriptions below.</span></span>

> [!NOTE]
> <span data-ttu-id="bd92f-109">地域とネットワークのフィルター処理機能を提供するには、建物およびサブネットデータを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd92f-109">Building and subnet data must be populated to provide regional and network filtering capabilities.</span></span>

## <a name="call-count-summary-report"></a><span data-ttu-id="bd92f-110">通話カウントの概要レポート</span><span class="sxs-lookup"><span data-stu-id="bd92f-110">Call Count Summary Report</span></span>

<span data-ttu-id="bd92f-111">メインページ ([通話カウントの概要]) には、セクションタイトルに記載されているように、最後の 30 ~ 90 日間の音声、ビデオ、画面共有セッションの数がすぐに表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd92f-111">The main page (Call Count Summary) immediately provides the number of audio, video and screen sharing sessions over the last 30 and 90 days as noted in the section title.</span></span> <span data-ttu-id="bd92f-112">最初に表示されるデータは組織全体に対して設定され、ページの左側にある [スライサー] ドロップダウンオプションを使ってフィルター処理することができます。</span><span class="sxs-lookup"><span data-stu-id="bd92f-112">The data initially displayed is for the organization as a whole and can be filtered using the slicer dropdown options on the left side of the page.</span></span>

![スクリーンショット: チームの使用状況レポート](media/CQD-teams-utilization-report1.png)

1. <span data-ttu-id="bd92f-114">スライサードロップダウンの右側では、メディアの種類別の呼び出しの数が、過去30日間にわたって内部/外部ビューに分割されます。</span><span class="sxs-lookup"><span data-stu-id="bd92f-114">To the right of the slicer dropdowns, the number of calls by media type is broken down to an internal/external view over the past thirty days.</span></span> <span data-ttu-id="bd92f-115">上のスクリーンショットでは、組織外の場所からより多くの通話が行われていることを示しています。これは、現在のグローバル環境を考慮していることを意味します。</span><span class="sxs-lookup"><span data-stu-id="bd92f-115">We can see through the above screenshot that there are more calls happening from outside organizational locations, which makes sense considering the current global environment.</span></span>
  <span data-ttu-id="bd92f-116">![スクリーンショット: チームの使用状況レポート](media/CQD-teams-utilization-report2.png)</span><span class="sxs-lookup"><span data-stu-id="bd92f-116">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report2.png)</span></span>

1. <span data-ttu-id="bd92f-117">[メディアの種類のカウント] ボックスの右側には、過去90日間のメディアの種類別の月次通話カウントがあります。</span><span class="sxs-lookup"><span data-stu-id="bd92f-117">To the right of the media type count box, we have the Monthly Call Count by Media Type for the last 90 days.</span></span> <span data-ttu-id="bd92f-118">各列とメディアの種類をマウスでポイントすると、前月または現在の月の数が表示され、使用傾向の情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="bd92f-118">Each column and media type can be hovered over to display the count for a previous month or the current month to date, providing usage trend information.</span></span>
  <span data-ttu-id="bd92f-119">![スクリーンショット: チームの使用状況レポート](media/CQD-teams-utilization-report3.png)</span><span class="sxs-lookup"><span data-stu-id="bd92f-119">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report3.png)</span></span>
 

1. <span data-ttu-id="bd92f-120">中央のグラフは、90日間のグラフとして機能しますが、過去30日間の日次利用状況ビューを提供し、ユーザーが右クリックして特定の日の詳細をドリルダウンできるようにします。</span><span class="sxs-lookup"><span data-stu-id="bd92f-120">The middle graph functions as the 90-day graph does, however it provides a daily usage view for the past 30 days and allows a user to right click and drill down into details for a specific day.</span></span>
  <span data-ttu-id="bd92f-121">![スクリーンショット: チームの使用状況レポート](media/CQD-teams-utilization-report4.png)</span><span class="sxs-lookup"><span data-stu-id="bd92f-121">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report4.png)</span></span>

<span data-ttu-id="bd92f-122">ページの左下のセクションでは、過去1年の各メディアの種類の合計値を提供するテーブルが見つかります。</span><span class="sxs-lookup"><span data-stu-id="bd92f-122">On the bottom left section of the page, you'll find a table providing total values for each media type over the past year.</span></span> 
    <span data-ttu-id="bd92f-123">![スクリーンショット: チーム使用](media/CQD-teams-utilization-report5.png) ![状況レポートのスクリーンショット: チーム使用率レポート](media/CQD-teams-utilization-report6.png)</span><span class="sxs-lookup"><span data-stu-id="bd92f-123">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report5.png) ![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report6.png)</span></span>   

<span data-ttu-id="bd92f-124">テーブルの右側にある棒グラフには、過去30日間に最も頻繁に使用されているクライアント (通話/ストリーム) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd92f-124">To the right of the table, a bar chart shows clients with the most use (calls/streams) for the past 30 days.</span></span>
   <span data-ttu-id="bd92f-125">![スクリーンショット: チームの使用状況レポート](media/CQD-teams-utilization-report7.png)</span><span class="sxs-lookup"><span data-stu-id="bd92f-125">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report7.png)</span></span>

<span data-ttu-id="bd92f-126">このページの最後のグラフセットでは、各メディアの種類が個別に表示され、会議と P2P の使用状況を示すブレークダウンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd92f-126">The last set of charts for this page show each media type individually, with a breakdown showing conference and P2P usage.</span></span> <span data-ttu-id="bd92f-127">以下の図は、P2P と比較した場合の会議の利用回数が非常に多いことを示しています。</span><span class="sxs-lookup"><span data-stu-id="bd92f-127">The charts below show that there is a significantly higher number of conference usage as compared to P2P.</span></span>
  <span data-ttu-id="bd92f-128">![スクリーンショット: チームの使用状況レポート](media/CQD-teams-utilization-report8.png)</span><span class="sxs-lookup"><span data-stu-id="bd92f-128">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report8.png)</span></span>

## <a name="audio-minutes-summary-report"></a><span data-ttu-id="bd92f-129">オーディオ分のサマリーレポート</span><span class="sxs-lookup"><span data-stu-id="bd92f-129">Audio Minutes Summary Report</span></span>

<span data-ttu-id="bd92f-130">[オーディオ時間の利用状況] レポートでは、合計分使用量がいくつかの異なるビューで提供されます。</span><span class="sxs-lookup"><span data-stu-id="bd92f-130">On the Audio Minutes usage report, the total minute usage is provided through a few different views.</span></span> 

<span data-ttu-id="bd92f-131">スライサーの隣には、テキストボックスを簡単に利用できるように、30日間の使用状況の概要が表示されています。</span><span class="sxs-lookup"><span data-stu-id="bd92f-131">We have the thirty-day usage summary shown next to the slicers as easy to consume text boxes.</span></span> <span data-ttu-id="bd92f-132">上部の番号には、その下に内部と外部の内訳が表示された、30日間の合計が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd92f-132">The top number shows the thirty-day total, with internal and external breakdowns below that.</span></span>

![スクリーンショット: チームの使用状況レポート](media/CQD-teams-utilization-report9.png)

<span data-ttu-id="bd92f-134">右上の棒グラフでは、電話会議の音声使用状況が yearlong で表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd92f-134">The top right bar graph provides a yearlong view of conference audio usage.</span></span> <span data-ttu-id="bd92f-135">月をポイントすると、会議の音声通話時間が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd92f-135">Hover over the month to show the conference audio minutes.</span></span>

<span data-ttu-id="bd92f-136">P2P と会議の音声の違いを示すために、左下のグラフはすべてのオーディオを過去の年に向けて受け取り、2つの種類の間で分割します。</span><span class="sxs-lookup"><span data-stu-id="bd92f-136">To show the difference in P2P and conference audio, the bottom left chart takes all audio for the past year and breaks it up between the two types.</span></span>

![スクリーンショット: チームの使用状況レポート](media/CQD-teams-utilization-report10.png)

<span data-ttu-id="bd92f-138">[オーディオ分数] ページの最後のグラフは、グローバルマップオーバーレイでのオーディオ分の使用状況を示しています。</span><span class="sxs-lookup"><span data-stu-id="bd92f-138">The last chart for the Audio minutes page shows audio minute usage on a global map overlay.</span></span> <span data-ttu-id="bd92f-139">このグラフは、構築およびサブネットデータがテナントにアップロードされた場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="bd92f-139">This chart will only work if building and subnet data is uploaded to the tenant.</span></span> <span data-ttu-id="bd92f-140">地図上の円グラフのオーバーレイを表示して、その後で地域のオーディオ使用法を提供できます。</span><span class="sxs-lookup"><span data-stu-id="bd92f-140">The pie chart overlay on the map can be drilled into, subsequently providing regional audio usage.</span></span>

![スクリーンショット: チームの使用状況レポート](media/CQD-teams-utilization-report11.png)


## <a name="drill-through-capabilities"></a><span data-ttu-id="bd92f-142">ドリルスルー機能</span><span class="sxs-lookup"><span data-stu-id="bd92f-142">Drill-through capabilities</span></span>

<span data-ttu-id="bd92f-143">前に説明したように、ユーザーは日単位および地域の利用状況レポートについて詳しく調べることができます。</span><span class="sxs-lookup"><span data-stu-id="bd92f-143">As previously noted, users can drill into the daily and regional usage reports.</span></span>

### <a name="daily-usage"></a><span data-ttu-id="bd92f-144">日常的な利用状況</span><span class="sxs-lookup"><span data-stu-id="bd92f-144">Daily Usage</span></span>

<span data-ttu-id="bd92f-145">日次利用状況レポートを使用すると、管理者は1日の間にピークの消費期間を特定できます。</span><span class="sxs-lookup"><span data-stu-id="bd92f-145">The Daily Usage report allows an administrator to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="bd92f-146">利用状況に加えて、その日の全体的なユーザー感情とフィードバックをキャプチャすることもできます。</span><span class="sxs-lookup"><span data-stu-id="bd92f-146">In addition to usage, we are also able to capture overall user sentiment and feedback for that day.</span></span>

![スクリーンショット: チームの使用状況レポート](media/CQD-teams-utilization-report12.png)

<span data-ttu-id="bd92f-148">[1 日の利用状況] レポートには、選択した日の音声、ビデオ、画面の共有の数が表示され、内部と外部の接続を区別することができます。</span><span class="sxs-lookup"><span data-stu-id="bd92f-148">The Daily usage report displays the number of Audio, Video and Screen shares for the selected day with the added ability to differentiate between internal and external connectivity.</span></span> <span data-ttu-id="bd92f-149">[会議とピアツーピア] のブレークダウンは、[モダリティ合計] ボックスのすぐ右にあります。</span><span class="sxs-lookup"><span data-stu-id="bd92f-149">A Conference and Peer to Peer breakdown is to the immediate right of the modality total box.</span></span> <span data-ttu-id="bd92f-150">レポートの右上に、その日の会議 ID と参加者が含まれている会議の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd92f-150">The top right of the report provides a list of conferences with their associated ID and participants for the day.</span></span> <span data-ttu-id="bd92f-151">会議の一覧では、会議の詳細レポートも追加で表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd92f-151">The conference list provides an additional drill down to the Conference Details report as well.</span></span> <span data-ttu-id="bd92f-152">図を置き換える</span><span class="sxs-lookup"><span data-stu-id="bd92f-152">REPLACE GRAPHIC</span></span>

![スクリーンショット: チームの使用状況レポート](media/CQD-teams-utilization-report13.png)

<span data-ttu-id="bd92f-154">中央の領域の棒グラフでは、ユーザーは1日の間にピークの消費期間を特定することができます。</span><span class="sxs-lookup"><span data-stu-id="bd92f-154">The bar graph in the center area allows the user to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="bd92f-155">ユーザーはグラフに表示される時間にドリルダウンすることができます。これは、ユーザーリストレポートを表示する時間です。</span><span class="sxs-lookup"><span data-stu-id="bd92f-155">Users may drill down into the hour represented on the graph which will present the User List report for the hour.</span></span>

<span data-ttu-id="bd92f-156">棒グラフの右側には、ユーザーからのフィードバックが視覚的な形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd92f-156">To the right of the bar graph, User Feedback is presented in a visual format.</span></span> <span data-ttu-id="bd92f-157">ユーザー感情は主観的なものにすることもできますが、潜在的な問題を特定するために使用できる洞察が提供されます。</span><span class="sxs-lookup"><span data-stu-id="bd92f-157">While user sentiment can be subjective, it does provide insight that can be used to identify potential issues.</span></span>

<span data-ttu-id="bd92f-158">下部のテーブルには、その日のさまざまなメトリックが用意されています。</span><span class="sxs-lookup"><span data-stu-id="bd92f-158">The bottom table provides a range of metrics for the day.</span></span> <span data-ttu-id="bd92f-159">故障率の低いパーセンテージで、管理者が改善の可能性のある領域を提供できます。</span><span class="sxs-lookup"><span data-stu-id="bd92f-159">Poor percentages along with failure rates can provide an administrator with potential areas of improvement.</span></span> <span data-ttu-id="bd92f-160">次に示すように、1時間ごとに個別に選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="bd92f-160">Each hour can also be selected individually as shown below.</span></span>

<span data-ttu-id="bd92f-161">このデータは、消費時間のピーク時に問題が発生した地域を特定するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="bd92f-161">This data can be used to identify regions having problems during peak consumption times.</span></span>


<span data-ttu-id="bd92f-162">その日の列をクリックして、その時間の指標を表示します。</span><span class="sxs-lookup"><span data-stu-id="bd92f-162">Click on the column for that day to display metrics for that hour.</span></span>
<span data-ttu-id="bd92f-163">![スクリーンショット: チームの使用状況レポート](media/CQD-teams-utilization-report14.png)</span><span class="sxs-lookup"><span data-stu-id="bd92f-163">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report14.png)</span></span>
  
  1.  <span data-ttu-id="bd92f-164">グラフの下の表には、その時間の測度が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd92f-164">The table below the chart will display the metrics for that hour.</span></span> <span data-ttu-id="bd92f-165">これは、任意の列見出しを基準にして並べ替えることができます。ただし、問題のある領域を見つけることに関心を持っています。</span><span class="sxs-lookup"><span data-stu-id="bd92f-165">This can be sorted by any column header; however, we would be interested in finding problematic areas.</span></span>  
    ![スクリーンショット: チームの使用状況レポート](media/CQD-teams-utilization-report15.png)
    
  2.  <span data-ttu-id="bd92f-167">この期間中の会議では、IND 領域のビデオパフォーマンスが低下していることがわかります。</span><span class="sxs-lookup"><span data-stu-id="bd92f-167">We see that the IND region is experiencing poor video performance in conferences during this time frame.</span></span> <span data-ttu-id="bd92f-168">その後、CQD QER Microsoft レポートを使って、地域と時間のフレームが識別されたために、問題のある場所を絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="bd92f-168">Subsequently, the CQD QER Microsoft reports can be used to narrow down the problematic location as the region and time frame has been identified.</span></span>

### <a name="conference-details"></a><span data-ttu-id="bd92f-169">会議の詳細</span><span class="sxs-lookup"><span data-stu-id="bd92f-169">Conference Details</span></span>

<span data-ttu-id="bd92f-170">[会議の詳細] レポートでは、出席者リストの中で、セッション中に使用されたメディアの種類について、会議の詳細を把握できます。</span><span class="sxs-lookup"><span data-stu-id="bd92f-170">The Conference Details report provides additional insight for meetings, from an attendee list, to the media types used during the session.</span></span>

<span data-ttu-id="bd92f-171">[毎日の利用状況] ページの [電話会議 ID] グラフの参加者バーである会議を右クリックして、会議の詳細をドリルダウンします。</span><span class="sxs-lookup"><span data-stu-id="bd92f-171">Right click a conference the participant bar in the conference ID chart on the Daily usage page to drill down into the conference details.</span></span>

![スクリーンショット: チームの使用状況レポート](media/CQD-teams-utilization-report24.png)

![スクリーンショット: チームの使用状況レポート](media/CQD-teams-utilization-report25.png)
  

<span data-ttu-id="bd92f-174">会議の参加者と、パケットの損失とジッターまでの関連情報をすべて、下部の表に記載されている潜在的なトラブルシューティング作業に役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="bd92f-174">We can see the participants in the conference as well as all the pertinent information down to packet loss and jitter to assist with potential troubleshooting efforts in the bottom table.</span></span>

![スクリーンショット: チームの使用状況レポート](media/CQD-teams-utilization-report26.png)


### <a name="regional-audio-details"></a><span data-ttu-id="bd92f-176">地域の音声の詳細</span><span class="sxs-lookup"><span data-stu-id="bd92f-176">Regional Audio Details</span></span>

<span data-ttu-id="bd92f-177">[地域のオーディオ詳細] のドリルダウンでは、選択した地域の音声分の使用状況が具体的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd92f-177">The Regional Audio Details drill down specifically shows the audio minute usage for the selected region.</span></span> <span data-ttu-id="bd92f-178">CQD へのアクセス権を持つユーザーは、選択した地域内の P2P と会議のオーディオの使用状況の傾向を確認できます。</span><span class="sxs-lookup"><span data-stu-id="bd92f-178">Users with access to CQD can see usage trends for both P2P and conference audio within the selected region.</span></span>

1.  <span data-ttu-id="bd92f-179">[通話カウントの概要] ページで、表を通じて特定の地域にドリルダウンします。</span><span class="sxs-lookup"><span data-stu-id="bd92f-179">On the Call Count Summary page, drill-through to as specific region through the table.</span></span>
  <span data-ttu-id="bd92f-180">![スクリーンショット: チームの使用状況レポート](media/CQD-teams-utilization-report16.png)</span><span class="sxs-lookup"><span data-stu-id="bd92f-180">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report16.png)</span></span>

2.  <span data-ttu-id="bd92f-181">領域の追加情報が必要な行を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd92f-181">Select the row with the region additional information is needed for.</span></span>
  <span data-ttu-id="bd92f-182">![スクリーンショット: チームの使用状況レポート](media/CQD-teams-utilization-report17.png)</span><span class="sxs-lookup"><span data-stu-id="bd92f-182">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report17.png)</span></span>

3.  <span data-ttu-id="bd92f-183">データの傾向は、内部ネットワークで利用されている長い時間 (分単位) を示しています。これには、surpassing が P2P を使用しています。</span><span class="sxs-lookup"><span data-stu-id="bd92f-183">The data trends show a significant number of minutes being used on the internal network, with conferencing far surpassing P2P use.</span></span>
  <span data-ttu-id="bd92f-184">![スクリーンショット: チームの使用状況レポート](media/CQD-teams-utilization-report18.png)</span><span class="sxs-lookup"><span data-stu-id="bd92f-184">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report18.png)</span></span>

<span data-ttu-id="bd92f-185">地域オーディオの傾向を使って、世界中の外部の影響によってユーザーがどのように影響を受けるかを示すことができます。</span><span class="sxs-lookup"><span data-stu-id="bd92f-185">The regional audio trend can be used to show how users are impacted by external influences in the world.</span></span> <span data-ttu-id="bd92f-186">具体的には、この時点で、ユーザーがリモートで作業することを求められる場合に、EMEA と APAC 地域の外部使用が表示されることを想定しています。</span><span class="sxs-lookup"><span data-stu-id="bd92f-186">Specifically, right now, we would expect to see the external usage for the EMEA and APAC regions to increase with people being asked to work remotely.</span></span>


### <a name="user-list"></a><span data-ttu-id="bd92f-187">ユーザーリスト</span><span class="sxs-lookup"><span data-stu-id="bd92f-187">User List</span></span>

<span data-ttu-id="bd92f-188">ユーザーリストのドリルダウンでは、レポートを表示しているユーザーによって選択された特定の時間についてユーザー固有の情報が提供される場合があります。</span><span class="sxs-lookup"><span data-stu-id="bd92f-188">The User List drill down provides, as one might expect, user specific information for a specific hour selected by the person viewing the report.</span></span> <span data-ttu-id="bd92f-189">ユーザーリストレポートには、[日単位の利用状況] レポートの時間の傾向グラフでドリルダウンしてアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="bd92f-189">The User List report is accessible through a drill down in the Hourly Trends graph on the Daily Usage report.</span></span> <span data-ttu-id="bd92f-190">次に示すように、必要な追加情報を右クリックして、[ドリルスルー] と [ユーザー] リストを選択します。</span><span class="sxs-lookup"><span data-stu-id="bd92f-190">Right click on the hour additional information is needed for and select Drill through and User List, as shown below.</span></span>

![スクリーンショット: チームの使用状況レポート](media/CQD-teams-utilization-report19.png)

<span data-ttu-id="bd92f-192">[ユーザーリスト] レポートには、ページの上部中央のドーナツグラフによる内部および外部の接続が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd92f-192">The User List report shows internal/external connectivity through the doughnut chart in the top center of the page.</span></span> <span data-ttu-id="bd92f-193">以下の画像では、企業ネットワークの外部から大量の参加があることがわかります。</span><span class="sxs-lookup"><span data-stu-id="bd92f-193">We can see that there is a large amount of participation from Outside the corporate network in the below image.</span></span>

<span data-ttu-id="bd92f-194">グラフの右上には、1時間以内に各ユーザーが行った通話の数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd92f-194">The top right of the graph shows the number of calls made by each user within that hour.</span></span>

![スクリーンショット: チームの使用状況レポート](media/CQD-teams-utilization-report20.png)

<span data-ttu-id="bd92f-196">下の表は、各ユーザーがその時間に参加したセッションの詳細情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="bd92f-196">The bottom table provides detailed information for the sessions each user participated in during that hour.</span></span> <span data-ttu-id="bd92f-197">[エラーの種類] 列は、通話のドロップの原因を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bd92f-197">The Failure Type column is useful in determining what caused a call to drop.</span></span> <span data-ttu-id="bd92f-198">[キャプチャ] と [レンダーデバイス] の列は、通話が低品質であると報告された理由を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bd92f-198">The Capture and Render Device columns are useful in identifying why a call was reported having poor quality.</span></span>


## <a name="related-topics"></a><span data-ttu-id="bd92f-199">関連項目</span><span class="sxs-lookup"><span data-stu-id="bd92f-199">Related topics</span></span>

[<span data-ttu-id="bd92f-200">通話品質ダッシュボードで利用できるディメンションとメジャー</span><span class="sxs-lookup"><span data-stu-id="bd92f-200">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="bd92f-201">通話品質ダッシュボードでのストリームの分類</span><span class="sxs-lookup"><span data-stu-id="bd92f-201">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="bd92f-202">Skype for Business の通話分析をセットアップする</span><span class="sxs-lookup"><span data-stu-id="bd92f-202">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="bd92f-203">通話分析を使用して低品質の通話をトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="bd92f-203">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="bd92f-204">通話分析および通話品質ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="bd92f-204">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)
 