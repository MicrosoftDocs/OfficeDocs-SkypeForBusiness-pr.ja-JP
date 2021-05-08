---
title: CQD Microsoft Teamsを使用してPower BIの使用状況を表示する
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
description: '[Teams 使用率Power BI レポートを使用して、Microsoft Teams通話品質ダッシュボード (CQD) データにアクセスして、組織内のMicrosoft Teams使用状況を追跡します。'
ms.openlocfilehash: 719f02ce7a5cd36e96ed7fd563c259c6e77764fd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095041"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a><span data-ttu-id="82db8-103">CQD Microsoft Teamsを使用してPower BIの使用状況を表示する</span><span class="sxs-lookup"><span data-stu-id="82db8-103">View Microsoft Teams utilization in Power BI using CQD data</span></span>

<span data-ttu-id="82db8-104">2020 年 3 月の新機能として[、CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)用のダウンロード可能な Teams クエリ テンプレートに Teams Power BI 使用率レポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="82db8-104">New in March 2020, we've added a Teams Utilization report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 

<span data-ttu-id="82db8-105">この新Teams使用率レポートでは、Microsoft Teams 通話品質ダッシュボード (CQD) データにアクセスして、ユーザーが Microsoft Teams Teams を使用している方法 (およびどれくらい) を確認できます。</span><span class="sxs-lookup"><span data-stu-id="82db8-105">This new Teams Utilization reports lets you see how (and how much) your users are using Microsoft Teams by accessing Teams Call Quality Dashboard (CQD) data.</span></span> <span data-ttu-id="82db8-106">これらのレポートは、管理者とビジネス リーダーの両方が、このデータにすばやくアクセスできる一元的な場所を意図しています。</span><span class="sxs-lookup"><span data-stu-id="82db8-106">These reports are intended to be a centralized location that both administrators and business leaders can quickly go to for this data.</span></span>

<span data-ttu-id="82db8-107">[Teams使用率Power BIレポートは、通話数の概要と音声通話分の概要という **[](#call-count-summary-report)** 2 つの主要な **[レポートで構成されます](#audio-minutes-summary-report)**。</span><span class="sxs-lookup"><span data-stu-id="82db8-107">The Teams Utilization Power BI report consists of two primary reports: **[Call Count Summary](#call-count-summary-report)** and **[Audio Minutes Summary](#audio-minutes-summary-report)**.</span></span> <span data-ttu-id="82db8-108">次[の](#daily-usage)[説明に](#regional-audio-details)示すドリルダウン[](#conference-details)レポートをユーザー[](#user-list)が利用すると、毎日の使用状況、地域のオーディオの詳細、電話会議の詳細、ユーザー リスト の各レポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="82db8-108">The [Daily Usage](#daily-usage), [Regional Audio Details](#regional-audio-details), [Conference Details](#conference-details) and [User List](#user-list) reports come into play when a user takes advantage of the drill-down reports, noted in the descriptions below.</span></span>

> [!NOTE]
> <span data-ttu-id="82db8-109">リージョンとネットワークのフィルター処理機能を提供するには、建物とサブネットのデータを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82db8-109">Building and subnet data must be populated to provide regional and network filtering capabilities.</span></span>

## <a name="call-count-summary-report"></a><span data-ttu-id="82db8-110">通話数の概要レポート</span><span class="sxs-lookup"><span data-stu-id="82db8-110">Call Count Summary Report</span></span>

<span data-ttu-id="82db8-111">メイン ページ (通話数の概要) には、セクション タイトルに示されている過去 30 日間と 90 日間の音声、ビデオ、画面共有セッションの数がすぐに表示されます。</span><span class="sxs-lookup"><span data-stu-id="82db8-111">The main page (Call Count Summary) immediately provides the number of audio, video and screen sharing sessions over the last 30 and 90 days as noted in the section title.</span></span> <span data-ttu-id="82db8-112">最初に表示されるデータは組織全体のデータであり、ページの左側にあるスライサー ドロップダウン オプションを使用してフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="82db8-112">The data initially displayed is for the organization as a whole and can be filtered using the slicer dropdown options on the left side of the page.</span></span>

![スクリーンショット: Teams使用率レポート](media/CQD-teams-utilization-report1.png)

1. <span data-ttu-id="82db8-114">スライサードロップダウンの右側では、メディアの種類別の呼び出し数は、過去 30 日間の内部/外部ビューに分解されます。</span><span class="sxs-lookup"><span data-stu-id="82db8-114">To the right of the slicer dropdowns, the number of calls by media type is broken down to an internal/external view over the past thirty days.</span></span> <span data-ttu-id="82db8-115">上のスクリーンショットを見て、現在のグローバル環境を考慮すると、組織の外部からさらに多くの呼び出しが発生しているのを確認できます。</span><span class="sxs-lookup"><span data-stu-id="82db8-115">We can see through the above screenshot that there are more calls happening from outside organizational locations, which makes sense considering the current global environment.</span></span>
  <span data-ttu-id="82db8-116">![スクリーンショット: Teams使用率レポート](media/CQD-teams-utilization-report2.png)</span><span class="sxs-lookup"><span data-stu-id="82db8-116">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report2.png)</span></span>

1. <span data-ttu-id="82db8-117">[メディアの種類のカウント] ボックスの右側には、過去 90 日間のメディアの種類別の月次通話数があります。</span><span class="sxs-lookup"><span data-stu-id="82db8-117">To the right of the media type count box, we have the Monthly Call Count by Media Type for the last 90 days.</span></span> <span data-ttu-id="82db8-118">各列とメディアの種類にカーソルを合わせると、前月または現在の月の現在の数を表示し、使用状況の傾向情報を提供できます。</span><span class="sxs-lookup"><span data-stu-id="82db8-118">Each column and media type can be hovered over to display the count for a previous month or the current month to date, providing usage trend information.</span></span>
  <span data-ttu-id="82db8-119">![スクリーンショット: Teams使用率レポート](media/CQD-teams-utilization-report3.png)</span><span class="sxs-lookup"><span data-stu-id="82db8-119">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report3.png)</span></span>
 

1. <span data-ttu-id="82db8-120">中央のグラフは 90 日間のグラフと同様に機能しますが、過去 30 日間の毎日の使用状況ビューが提供され、ユーザーは右クリックして特定の日の詳細をドリルダウンできます。</span><span class="sxs-lookup"><span data-stu-id="82db8-120">The middle graph functions as the 90-day graph does, however it provides a daily usage view for the past 30 days and allows a user to right click and drill down into details for a specific day.</span></span>
  <span data-ttu-id="82db8-121">![スクリーンショット: Teams使用率レポート](media/CQD-teams-utilization-report4.png)</span><span class="sxs-lookup"><span data-stu-id="82db8-121">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report4.png)</span></span>

<span data-ttu-id="82db8-122">ページの左下のセクションには、過去 1 年間の各メディア タイプの合計値を示すテーブルがあります。</span><span class="sxs-lookup"><span data-stu-id="82db8-122">On the bottom left section of the page, you'll find a table providing total values for each media type over the past year.</span></span> 
    <span data-ttu-id="82db8-123">![スクリーンショット: Teams使用率レポート ](media/CQD-teams-utilization-report5.png) ![ のスクリーンショット: Teams使用率レポート](media/CQD-teams-utilization-report6.png)</span><span class="sxs-lookup"><span data-stu-id="82db8-123">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report5.png) ![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report6.png)</span></span>   

<span data-ttu-id="82db8-124">表の右側には、過去 30 日間の最も多くの使用 (呼び出し/ストリーム) を持つクライアントが棒グラフに表示されます。</span><span class="sxs-lookup"><span data-stu-id="82db8-124">To the right of the table, a bar chart shows clients with the most use (calls/streams) for the past 30 days.</span></span>
   <span data-ttu-id="82db8-125">![スクリーンショット: Teams使用率レポート](media/CQD-teams-utilization-report7.png)</span><span class="sxs-lookup"><span data-stu-id="82db8-125">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report7.png)</span></span>

<span data-ttu-id="82db8-126">このページのグラフの最後のセットでは、各メディアの種類が個別に表示され、内訳には電話会議と P2P の使用状況が表示されます。</span><span class="sxs-lookup"><span data-stu-id="82db8-126">The last set of charts for this page show each media type individually, with a breakdown showing conference and P2P usage.</span></span> <span data-ttu-id="82db8-127">次のグラフは、P2P と比較して、電話会議の使用量の数が大幅に多い場合を示しています。</span><span class="sxs-lookup"><span data-stu-id="82db8-127">The charts below show that there is a significantly higher number of conference usage as compared to P2P.</span></span>
  <span data-ttu-id="82db8-128">![スクリーンショット: Teams使用率レポート](media/CQD-teams-utilization-report8.png)</span><span class="sxs-lookup"><span data-stu-id="82db8-128">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report8.png)</span></span>

## <a name="audio-minutes-summary-report"></a><span data-ttu-id="82db8-129">オーディオ分の概要レポート</span><span class="sxs-lookup"><span data-stu-id="82db8-129">Audio Minutes Summary Report</span></span>

<span data-ttu-id="82db8-130">オーディオ分の使用状況レポートでは、分の合計使用量は、いくつかの異なるビューを通じて提供されます。</span><span class="sxs-lookup"><span data-stu-id="82db8-130">On the Audio Minutes usage report, the total minute usage is provided through a few different views.</span></span> 

<span data-ttu-id="82db8-131">スライサーの横に、使用しやすいテキスト ボックスとして 30 日間の使用状況の概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="82db8-131">We have the thirty-day usage summary shown next to the slicers as easy to consume text boxes.</span></span> <span data-ttu-id="82db8-132">上位の数値は、30 日間の合計を示し、内部および外部の内訳が下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="82db8-132">The top number shows the thirty-day total, with internal and external breakdowns below that.</span></span>

![スクリーンショット: Teams使用率レポート](media/CQD-teams-utilization-report9.png)

<span data-ttu-id="82db8-134">上部右の棒グラフは、電話会議の音声使用状況を 1 年間表示します。</span><span class="sxs-lookup"><span data-stu-id="82db8-134">The top right bar graph provides a yearlong view of conference audio usage.</span></span> <span data-ttu-id="82db8-135">月にマウス ポインターを合わせると、電話会議の音声分が表示されます。</span><span class="sxs-lookup"><span data-stu-id="82db8-135">Hover over the month to show the conference audio minutes.</span></span>

<span data-ttu-id="82db8-136">P2P と電話会議の音声の違いを示す左下のグラフは、過去 1 年間のすべての音声を受け取り、2 種類の間で分解します。</span><span class="sxs-lookup"><span data-stu-id="82db8-136">To show the difference in P2P and conference audio, the bottom left chart takes all audio for the past year and breaks it up between the two types.</span></span>

![スクリーンショット: Teams使用率レポート](media/CQD-teams-utilization-report10.png)

<span data-ttu-id="82db8-138">[オーディオ分] ページの最後のグラフには、グローバル マップ オーバーレイでのオーディオ分の使用状況が表示されます。</span><span class="sxs-lookup"><span data-stu-id="82db8-138">The last chart for the Audio minutes page shows audio minute usage on a global map overlay.</span></span> <span data-ttu-id="82db8-139">このグラフは、構築とサブネット データがテナントにアップロードされた場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="82db8-139">This chart will only work if building and subnet data is uploaded to the tenant.</span></span> <span data-ttu-id="82db8-140">マップ上の円グラフ オーバーレイを掘り下ろして、その後、地域のオーディオを使用できます。</span><span class="sxs-lookup"><span data-stu-id="82db8-140">The pie chart overlay on the map can be drilled into, subsequently providing regional audio usage.</span></span>

![スクリーンショット: Teams使用率レポート](media/CQD-teams-utilization-report11.png)


## <a name="drill-through-capabilities"></a><span data-ttu-id="82db8-142">ドリルスルー機能</span><span class="sxs-lookup"><span data-stu-id="82db8-142">Drill-through capabilities</span></span>

<span data-ttu-id="82db8-143">前に説明した通り、ユーザーは日次および地域の使用状況レポートを詳細に確認できます。</span><span class="sxs-lookup"><span data-stu-id="82db8-143">As previously noted, users can drill into the daily and regional usage reports.</span></span>

### <a name="daily-usage"></a><span data-ttu-id="82db8-144">毎日の使用状況</span><span class="sxs-lookup"><span data-stu-id="82db8-144">Daily Usage</span></span>

<span data-ttu-id="82db8-145">[毎日の使用状況] レポートを使用すると、管理者は 1 日の間のピーク消費期間を特定できます。</span><span class="sxs-lookup"><span data-stu-id="82db8-145">The Daily Usage report allows an administrator to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="82db8-146">使用状況に加えて、その日の全体的なユーザーセンチメントとフィードバックもキャプチャできます。</span><span class="sxs-lookup"><span data-stu-id="82db8-146">In addition to usage, we are also able to capture overall user sentiment and feedback for that day.</span></span>

![スクリーンショット: Teams使用率レポート](media/CQD-teams-utilization-report12.png)

<span data-ttu-id="82db8-148">[毎日の使用状況] レポートには、選択した日のオーディオ、ビデオ、画面共有の数が表示され、内部接続と外部接続を区別する機能が追加されます。</span><span class="sxs-lookup"><span data-stu-id="82db8-148">The Daily usage report displays the number of Audio, Video and Screen shares for the selected day with the added ability to differentiate between internal and external connectivity.</span></span> <span data-ttu-id="82db8-149">[会議とピア ツー ピア] の内訳は、[モダリティの合計] ボックスの直右に表示されます。</span><span class="sxs-lookup"><span data-stu-id="82db8-149">A Conference and Peer to Peer breakdown is to the immediate right of the modality total box.</span></span> <span data-ttu-id="82db8-150">レポートの右側には、その日の関連付けられた ID と参加者を含む会議の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="82db8-150">The top right of the report provides a list of conferences with their associated ID and participants for the day.</span></span> <span data-ttu-id="82db8-151">会議リストには、電話会議の詳細レポートに関する追加のドリルダウンも表示されます。</span><span class="sxs-lookup"><span data-stu-id="82db8-151">The conference list provides an additional drill down to the Conference Details report as well.</span></span> <span data-ttu-id="82db8-152">グラフィックを置き換える</span><span class="sxs-lookup"><span data-stu-id="82db8-152">REPLACE GRAPHIC</span></span>

![スクリーンショット: Teams使用率レポート](media/CQD-teams-utilization-report13.png)

<span data-ttu-id="82db8-154">中央の領域の棒グラフを使用すると、ユーザーは 1 日の間のピーク消費期間を識別できます。</span><span class="sxs-lookup"><span data-stu-id="82db8-154">The bar graph in the center area allows the user to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="82db8-155">ユーザーは、グラフで表される時間にドリルダウンして、その時間のユーザー リスト レポートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="82db8-155">Users may drill down into the hour represented on the graph which will present the User List report for the hour.</span></span>

<span data-ttu-id="82db8-156">棒グラフの右側には、ユーザー フィードバックが視覚的な形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="82db8-156">To the right of the bar graph, User Feedback is presented in a visual format.</span></span> <span data-ttu-id="82db8-157">ユーザーセンチメントは主観的ですが、潜在的な問題を特定するために使用できる洞察を提供します。</span><span class="sxs-lookup"><span data-stu-id="82db8-157">While user sentiment can be subjective, it does provide insight that can be used to identify potential issues.</span></span>

<span data-ttu-id="82db8-158">下の表は、その日のメトリックの範囲を示しています。</span><span class="sxs-lookup"><span data-stu-id="82db8-158">The bottom table provides a range of metrics for the day.</span></span> <span data-ttu-id="82db8-159">低い割合と障害率は、管理者に改善の可能性のある領域を提供する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="82db8-159">Poor percentages along with failure rates can provide an administrator with potential areas of improvement.</span></span> <span data-ttu-id="82db8-160">次に示すように、1 時間ごとに個別に選択できます。</span><span class="sxs-lookup"><span data-stu-id="82db8-160">Each hour can also be selected individually as shown below.</span></span>

<span data-ttu-id="82db8-161">このデータを使用して、ピーク時に問題が発生しているリージョンを特定できます。</span><span class="sxs-lookup"><span data-stu-id="82db8-161">This data can be used to identify regions having problems during peak consumption times.</span></span>


<span data-ttu-id="82db8-162">その日の列をクリックすると、その時間のメトリックが表示されます。</span><span class="sxs-lookup"><span data-stu-id="82db8-162">Click on the column for that day to display metrics for that hour.</span></span>
<span data-ttu-id="82db8-163">![スクリーンショット: Teams使用率レポート](media/CQD-teams-utilization-report14.png)</span><span class="sxs-lookup"><span data-stu-id="82db8-163">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report14.png)</span></span>
  
  1.  <span data-ttu-id="82db8-164">グラフの下の表には、その時間のメトリックが表示されます。</span><span class="sxs-lookup"><span data-stu-id="82db8-164">The table below the chart will display the metrics for that hour.</span></span> <span data-ttu-id="82db8-165">これは、任意の列ヘッダーで並べ替え可能です。ただし、問題のある領域を見つけることに関心があります。</span><span class="sxs-lookup"><span data-stu-id="82db8-165">This can be sorted by any column header; however, we would be interested in finding problematic areas.</span></span>  
    ![スクリーンショット: Teams使用率レポート](media/CQD-teams-utilization-report15.png)
    
  2.  <span data-ttu-id="82db8-167">この期間中、IND リージョンの会議でビデオパフォーマンスが低下しているのが確認できます。</span><span class="sxs-lookup"><span data-stu-id="82db8-167">We see that the IND region is experiencing poor video performance in conferences during this time frame.</span></span> <span data-ttu-id="82db8-168">その後、CQD QER Microsoft レポートを使用して、リージョンと時間枠が特定された問題のある場所を絞り込む可能性があります。</span><span class="sxs-lookup"><span data-stu-id="82db8-168">Subsequently, the CQD QER Microsoft reports can be used to narrow down the problematic location as the region and time frame has been identified.</span></span>

### <a name="conference-details"></a><span data-ttu-id="82db8-169">電話会議の詳細</span><span class="sxs-lookup"><span data-stu-id="82db8-169">Conference Details</span></span>

<span data-ttu-id="82db8-170">[会議の詳細] レポートでは、出席者リストから、セッション中に使用されるメディアの種類まで、会議に関する追加の分析情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="82db8-170">The Conference Details report provides additional insight for meetings, from an attendee list, to the media types used during the session.</span></span>

<span data-ttu-id="82db8-171">[毎日の使用状況] ページの [会議 ID] グラフの参加者バーを右クリックして、会議の詳細をドリルダウンします。</span><span class="sxs-lookup"><span data-stu-id="82db8-171">Right click a conference the participant bar in the conference ID chart on the Daily usage page to drill down into the conference details.</span></span>

![スクリーンショット: Teams使用率レポート](media/CQD-teams-utilization-report24.png)

![スクリーンショット: Teams使用率レポート](media/CQD-teams-utilization-report25.png)
  

<span data-ttu-id="82db8-174">会議の参加者だけでなく、パケット損失やジッターに関する関連情報はすべて、下の表の潜在的なトラブルシューティング作業に役立つ可能性があります。</span><span class="sxs-lookup"><span data-stu-id="82db8-174">We can see the participants in the conference as well as all the pertinent information down to packet loss and jitter to assist with potential troubleshooting efforts in the bottom table.</span></span>

![スクリーンショット: Teams使用率レポート](media/CQD-teams-utilization-report26.png)


### <a name="regional-audio-details"></a><span data-ttu-id="82db8-176">地域オーディオの詳細</span><span class="sxs-lookup"><span data-stu-id="82db8-176">Regional Audio Details</span></span>

<span data-ttu-id="82db8-177">[地域オーディオの詳細] ドリルダウンには、選択したリージョンの音声分の使用状況が具体的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="82db8-177">The Regional Audio Details drill down specifically shows the audio minute usage for the selected region.</span></span> <span data-ttu-id="82db8-178">CQD にアクセスできるユーザーは、選択したリージョン内の P2P と電話会議音声の両方の使用状況の傾向を確認できます。</span><span class="sxs-lookup"><span data-stu-id="82db8-178">Users with access to CQD can see usage trends for both P2P and conference audio within the selected region.</span></span>

1.  <span data-ttu-id="82db8-179">[Call Count Summary] ページで、テーブルを通じて特定のリージョンにドリルスルーします。</span><span class="sxs-lookup"><span data-stu-id="82db8-179">On the Call Count Summary page, drill-through to as specific region through the table.</span></span>
  <span data-ttu-id="82db8-180">![スクリーンショット: Teams使用率レポート](media/CQD-teams-utilization-report16.png)</span><span class="sxs-lookup"><span data-stu-id="82db8-180">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report16.png)</span></span>

2.  <span data-ttu-id="82db8-181">追加情報が必要な領域を含む行を選択します。</span><span class="sxs-lookup"><span data-stu-id="82db8-181">Select the row with the region additional information is needed for.</span></span>
  <span data-ttu-id="82db8-182">![スクリーンショット: Teams使用率レポート](media/CQD-teams-utilization-report17.png)</span><span class="sxs-lookup"><span data-stu-id="82db8-182">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report17.png)</span></span>

3.  <span data-ttu-id="82db8-183">データの傾向は、会議が P2P の使用をはるかに上回る、内部ネットワークで使用されている分数を示しています。</span><span class="sxs-lookup"><span data-stu-id="82db8-183">The data trends show a significant number of minutes being used on the internal network, with conferencing far surpassing P2P use.</span></span>
  <span data-ttu-id="82db8-184">![スクリーンショット: Teams使用率レポート](media/CQD-teams-utilization-report18.png)</span><span class="sxs-lookup"><span data-stu-id="82db8-184">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report18.png)</span></span>

<span data-ttu-id="82db8-185">地域のオーディオ傾向を使用して、ユーザーが世界の外部からの影響を受ける方法を示します。</span><span class="sxs-lookup"><span data-stu-id="82db8-185">The regional audio trend can be used to show how users are impacted by external influences in the world.</span></span> <span data-ttu-id="82db8-186">具体的には、現在、EMEA リージョンと APAC リージョンの外部使用量が増え、リモートで作業を求めるユーザーが増える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="82db8-186">Specifically, right now, we would expect to see the external usage for the EMEA and APAC regions to increase with people being asked to work remotely.</span></span>


### <a name="user-list"></a><span data-ttu-id="82db8-187">ユーザー リスト</span><span class="sxs-lookup"><span data-stu-id="82db8-187">User List</span></span>

<span data-ttu-id="82db8-188">ユーザー リストのドリルダウンでは、レポートを表示するユーザーが選択した特定の時間のユーザー固有の情報が予想される場合があります。</span><span class="sxs-lookup"><span data-stu-id="82db8-188">The User List drill down provides, as one might expect, user specific information for a specific hour selected by the person viewing the report.</span></span> <span data-ttu-id="82db8-189">ユーザー リスト レポートには、[毎日の使用状況] レポートの [時間別の傾向] グラフのドリルダウンを使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="82db8-189">The User List report is accessible through a drill down in the Hourly Trends graph on the Daily Usage report.</span></span> <span data-ttu-id="82db8-190">次に示すように、追加情報が必要な時間を右クリックし、[ドリルスルー] と [ユーザー リスト] を選択します。</span><span class="sxs-lookup"><span data-stu-id="82db8-190">Right click on the hour additional information is needed for and select Drill through and User List, as shown below.</span></span>

![スクリーンショット: Teams使用率レポート](media/CQD-teams-utilization-report19.png)

<span data-ttu-id="82db8-192">ユーザー リスト レポートには、ページの上部中央にあるドーナツ グラフを介した内部/外部接続が表示されます。</span><span class="sxs-lookup"><span data-stu-id="82db8-192">The User List report shows internal/external connectivity through the doughnut chart in the top center of the page.</span></span> <span data-ttu-id="82db8-193">次の図では、企業ネットワークの外部から大量の参加があるのを確認できます。</span><span class="sxs-lookup"><span data-stu-id="82db8-193">We can see that there is a large amount of participation from Outside the corporate network in the below image.</span></span>

<span data-ttu-id="82db8-194">グラフの右側には、各ユーザーが 1 時間以内に行った呼び出しの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="82db8-194">The top right of the graph shows the number of calls made by each user within that hour.</span></span>

![スクリーンショット: Teams使用率レポート](media/CQD-teams-utilization-report20.png)

<span data-ttu-id="82db8-196">下の表は、各ユーザーがその時間に参加したセッションの詳細情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="82db8-196">The bottom table provides detailed information for the sessions each user participated in during that hour.</span></span> <span data-ttu-id="82db8-197">[エラーの種類] 列は、呼び出しがドロップされた原因を特定する際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="82db8-197">The Failure Type column is useful in determining what caused a call to drop.</span></span> <span data-ttu-id="82db8-198">[Capture] 列と [Render Device] 列は、低品質の通話が報告された理由を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="82db8-198">The Capture and Render Device columns are useful in identifying why a call was reported having poor quality.</span></span>


## <a name="related-topics"></a><span data-ttu-id="82db8-199">関連トピック</span><span class="sxs-lookup"><span data-stu-id="82db8-199">Related topics</span></span>

[<span data-ttu-id="82db8-200">通話品質ダッシュボードで利用できるディメンションとメジャー</span><span class="sxs-lookup"><span data-stu-id="82db8-200">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="82db8-201">通話品質ダッシュボードでのストリームの分類</span><span class="sxs-lookup"><span data-stu-id="82db8-201">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="82db8-202">Skype for Business の通話分析をセットアップする</span><span class="sxs-lookup"><span data-stu-id="82db8-202">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="82db8-203">通話分析を使用して低品質の通話をトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="82db8-203">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="82db8-204">通話分析および通話品質ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="82db8-204">Call Analytics and Call Quality Dashboard</span></span>](./monitor-call-quality-qos.md)

[<span data-ttu-id="82db8-205">Teams のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="82db8-205">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
