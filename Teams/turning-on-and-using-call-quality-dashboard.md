---
title: 通話品質ダッシュボードをオンにして使用する
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney, gageames
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
ms.custom:
- Reporting
description: 'Skype for Business Online 通話品質ダッシュボードをオンにして使用する方法と、通話の品質に関する概要レポートを取得する方法について説明します。 '
ms.openlocfilehash: cf937a159eba723ee4ac7fc2ae01aa733e57170f
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "36483772"
---
# <a name="turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a><span data-ttu-id="82b33-103">Microsoft Teams および Skype for Business Online で通話品質ダッシュボードをオンにして使用する</span><span class="sxs-lookup"><span data-stu-id="82b33-103">Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online</span></span>

<span data-ttu-id="82b33-104">通話品質ダッシュボードを使って通話品質を監視できるように Office 365 組織を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="82b33-104">Learn how to configure your Office 365 organization to use the Call Quality Dashboard to monitor call quality.</span></span>
  
<span data-ttu-id="82b33-105">Microsoft Teams と Skype for Business Online の通話品質ダッシュボード (CQD) を使用すると、Microsoft Teams と Skype for business のサービスを使って発信した通話の品質を把握することができます。</span><span class="sxs-lookup"><span data-stu-id="82b33-105">The Call Quality Dashboard (CQD) for Microsoft Teams and Skype for Business Online allows you to gain insights into the quality of calls made using Microsoft Teams and Skype for Business services.</span></span> <span data-ttu-id="82b33-106">このトピックでは、データの収集を開始するために必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="82b33-106">This topic describes the steps you'll need to complete to start collecting data.</span></span>
  
  
## <a name="latest-changes-and-updates"></a><span data-ttu-id="82b33-107">最新の変更と更新</span><span class="sxs-lookup"><span data-stu-id="82b33-107">Latest changes and updates</span></span>

<span data-ttu-id="82b33-108">CQD に対する最新の変更点は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="82b33-108">The most recent changes to CQD are as follows:</span></span>
  
- <span data-ttu-id="82b33-109">Microsoft Teams のデータに加えて、Skype for Business Online データも含まれます。</span><span class="sxs-lookup"><span data-stu-id="82b33-109">Includes Microsoft Teams data in addition to Skype for Business Online data.</span></span>
    
- <span data-ttu-id="82b33-110">概要レポートには、すべてのデータ、Microsoft Teams データ、または Skype for Business Online データを選択するための製品フィルターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="82b33-110">Summary reports include a product filter to select all data, Microsoft Teams data, or Skype for Business Online data.</span></span>

- <span data-ttu-id="82b33-111">ビデオと VBSS ストリーム品質分類ロジックが更新されました。</span><span class="sxs-lookup"><span data-stu-id="82b33-111">Video and VBSS stream quality classification logic has been updated.</span></span> <span data-ttu-id="82b33-112">最新の分類子定義については、[通話品質ダッシュボードのストリーム分類](stream-classification-in-call-quality-dashboard.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82b33-112">Refer to [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md) for the latest classifier definitions.</span></span>

<span data-ttu-id="82b33-113">[通話品質ダッシュボードで利用できるディメンションとメジャー](dimensions-and-measures-available-in-call-quality-dashboard.md)の一覧については、この記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82b33-113">Refer to this article for a list of [Dimensions and measures available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="82b33-114">ダッシュボードの更新と変更についての情報は、**優れたニュース**のリンクをクリックすると確認できます。</span><span class="sxs-lookup"><span data-stu-id="82b33-114">Information about updates and changes to the dashboard can be found by clicking the link in the **Good news!**</span></span> <span data-ttu-id="82b33-115">ダッシュボードに表示されたバナー</span><span class="sxs-lookup"><span data-stu-id="82b33-115">banner when it is displayed on the dashboard.</span></span>
  
## <a name="activate-microsoft-call-quality-dashboard-cqd-summary-reports"></a><span data-ttu-id="82b33-116">Microsoft 通話品質ダッシュボード (CQD) の概要レポートを有効にする</span><span class="sxs-lookup"><span data-stu-id="82b33-116">Activate Microsoft Call Quality Dashboard (CQD) Summary Reports</span></span>

<span data-ttu-id="82b33-117">CQD の使用を開始する前に、Office 365 組織でライセンス認証を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="82b33-117">Before you can start using the CQD, you'll need to activate it for your Office 365 organization.</span></span>

<span data-ttu-id="82b33-118">![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン</span><span class="sxs-lookup"><span data-stu-id="82b33-118">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>
 
1. <span data-ttu-id="82b33-119">Microsoft Teams service 管理者アカウントを使用して Office 365 組織にサインインし、[**管理者**] タイルを選んで管理センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="82b33-119">Sign in to your Office 365 organization using Microsoft Teams service admin account, and then select the **Admin** tile to open the Admin center.</span></span>
    
2. <span data-ttu-id="82b33-120">左側のウィンドウの [**管理センター**] で、[ **microsoft teams** ] を選択して、microsoft teams 管理センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="82b33-120">In the left pane, under **Admin centers**, select **Microsoft Teams** to open the Microsoft Teams admin center.</span></span>
    
3. <span data-ttu-id="82b33-121">Microsoft Teams 管理センターで、左側のウィンドウの [**通話品質ダッシュボード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="82b33-121">In the Microsoft Teams admin center, select **Call quality dashboard** in the left pane.</span></span>
    
  
4. <span data-ttu-id="82b33-122">表示されたページで、グローバル管理者アカウントまたは Microsoft Teams サービス管理者アカウントでサインインし、メッセージが表示されたら、アカウントの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="82b33-122">On the page that opens, sign in with your Global Administrator account or Microsoft Teams Service Admin account, and then provide the credentials for the account when prompted.</span></span>
    
     ![資格情報のプロンプトが表示されたスクリーンショット](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
<span data-ttu-id="82b33-124">サインインすると、CQD によってデータの収集と処理が開始されます。</span><span class="sxs-lookup"><span data-stu-id="82b33-124">After you sign in, once activated, the CQD will begin collecting and processing data.</span></span>  
> [!NOTE]
> <span data-ttu-id="82b33-125">レポートに意味のある結果を表示するために十分なデータの処理には、数時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="82b33-125">It may take a couple of hours to process enough data to display meaningful results in the reports.</span></span> 

<span data-ttu-id="82b33-126">![](media/sfb-logo-30x30.png) **Skype for business 管理センターを使用し**た skype for business ロゴを示すアイコン</span><span class="sxs-lookup"><span data-stu-id="82b33-126">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="82b33-127">管理者アカウントを使用して Office 365 組織にサインインし、[**管理者**] タイルを選んで管理センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="82b33-127">Sign in to your Office 365 organization using an admin account, and then select the **Admin** tile to open the Admin center.</span></span>
    
2. <span data-ttu-id="82b33-128">左側のウィンドウの [**管理センター**] で、[ **skype for business** ] を選んで、skype for business 管理センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="82b33-128">In the left pane, under **Admin centers**, select **Skype for Business** to open the Skype for Business admin center.</span></span>
    
3. <span data-ttu-id="82b33-129">Skype for Business 管理センターで、左側のウィンドウの [**ツール**] を選択し、[ **Skype For Business Online 通話品質ダッシュボード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="82b33-129">In the Skype for Business admin center, select **Tools** in the left pane, and then select **Skype for Business Online Call Quality Dashboard**.</span></span>
    
     ![通話品質ダッシュボードの選択を示すスクリーンショット](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)
  
4. <span data-ttu-id="82b33-131">表示されたページで、グローバル管理者アカウントでサインインし、メッセージが表示されたらアカウントの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="82b33-131">On the page that opens, sign in with your Global Administrator account, and then provide the credentials for the account when prompted.</span></span>
    
     ![資格情報のプロンプトが表示されたスクリーンショット](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
<span data-ttu-id="82b33-133">サインインすると、CQD によってデータの収集と処理が開始されます。</span><span class="sxs-lookup"><span data-stu-id="82b33-133">After you sign in, once activated, the CQD will begin collecting and processing data.</span></span>


  
## <a name="features-of-the-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a><span data-ttu-id="82b33-134">Microsoft Teams および Skype for Business Online の通話品質ダッシュボードの機能</span><span class="sxs-lookup"><span data-stu-id="82b33-134">Features of the Call Quality Dashboard for Microsoft Teams and Skype for Business Online</span></span> 
<span data-ttu-id="82b33-135"><a name="BKMKFeaturesOfTheCQD"> </a></span><span class="sxs-lookup"><span data-stu-id="82b33-135"></span></span>

<span data-ttu-id="82b33-136">CQD の概要レポートには、詳細レポート用に計画されている機能のサブセットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="82b33-136">CQD Summary Reports provide a subset of the features planned for Detailed Reports.</span></span> <span data-ttu-id="82b33-137">ここでは、2つのエディションの違いについて説明します。</span><span class="sxs-lookup"><span data-stu-id="82b33-137">The differences between the two editions are summarized here:</span></span>
  
|<span data-ttu-id="82b33-138">**機能**</span><span class="sxs-lookup"><span data-stu-id="82b33-138">**Feature**</span></span>|<span data-ttu-id="82b33-139">**概要レポート**</span><span class="sxs-lookup"><span data-stu-id="82b33-139">**Summary Reports**</span></span>|<span data-ttu-id="82b33-140">**詳細レポート**</span><span class="sxs-lookup"><span data-stu-id="82b33-140">**Detailed Reports**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="82b33-141">アプリケーション共有のメトリック</span><span class="sxs-lookup"><span data-stu-id="82b33-141">Application sharing metric</span></span>  <br/> |<span data-ttu-id="82b33-142">いいえ</span><span class="sxs-lookup"><span data-stu-id="82b33-142">No</span></span>  <br/> |<span data-ttu-id="82b33-143">はい</span><span class="sxs-lookup"><span data-stu-id="82b33-143">Yes</span></span>  <br/> |
|<span data-ttu-id="82b33-144">顧客の建物情報のサポート</span><span class="sxs-lookup"><span data-stu-id="82b33-144">Customer building information support</span></span>  <br/> |<span data-ttu-id="82b33-145">はい</span><span class="sxs-lookup"><span data-stu-id="82b33-145">Yes</span></span>  <br/> |<span data-ttu-id="82b33-146">可</span><span class="sxs-lookup"><span data-stu-id="82b33-146">Yes</span></span>  <br/> |
|<span data-ttu-id="82b33-147">顧客エンドポイント情報のサポート</span><span class="sxs-lookup"><span data-stu-id="82b33-147">Customer endpoint information support</span></span>  <br/> |<span data-ttu-id="82b33-148">Cqd.teams.microsoft.com のみ</span><span class="sxs-lookup"><span data-stu-id="82b33-148">Only in cqd.teams.microsoft.com</span></span>  <br/> |<span data-ttu-id="82b33-149">Cqd.teams.microsoft.com のみ</span><span class="sxs-lookup"><span data-stu-id="82b33-149">Only in cqd.teams.microsoft.com</span></span>  <br/> |
|<span data-ttu-id="82b33-150">ドリルダウン分析のサポート</span><span class="sxs-lookup"><span data-stu-id="82b33-150">Drill-down analysis support</span></span>  <br/> |<span data-ttu-id="82b33-151">いいえ</span><span class="sxs-lookup"><span data-stu-id="82b33-151">No</span></span>  <br/> |<span data-ttu-id="82b33-152">はい</span><span class="sxs-lookup"><span data-stu-id="82b33-152">Yes</span></span>  <br/> |
|<span data-ttu-id="82b33-153">メディアの信頼性のメトリック</span><span class="sxs-lookup"><span data-stu-id="82b33-153">Media reliability metrics</span></span>  <br/> |<span data-ttu-id="82b33-154">いいえ</span><span class="sxs-lookup"><span data-stu-id="82b33-154">No</span></span>  <br/> |<span data-ttu-id="82b33-155">はい</span><span class="sxs-lookup"><span data-stu-id="82b33-155">Yes</span></span>  <br/> |
|<span data-ttu-id="82b33-156">ボックスのないレポート</span><span class="sxs-lookup"><span data-stu-id="82b33-156">Out-of-the-box reports</span></span>  <br/> |<span data-ttu-id="82b33-157">はい</span><span class="sxs-lookup"><span data-stu-id="82b33-157">Yes</span></span>  <br/> |<span data-ttu-id="82b33-158">可</span><span class="sxs-lookup"><span data-stu-id="82b33-158">Yes</span></span>  <br/> |
|<span data-ttu-id="82b33-159">概要レポート</span><span class="sxs-lookup"><span data-stu-id="82b33-159">Overview reports</span></span>  <br/> |<span data-ttu-id="82b33-160">はい</span><span class="sxs-lookup"><span data-stu-id="82b33-160">Yes</span></span>  <br/> |<span data-ttu-id="82b33-161">可</span><span class="sxs-lookup"><span data-stu-id="82b33-161">Yes</span></span>  <br/> |
|<span data-ttu-id="82b33-162">ユーザーごとのレポートセット</span><span class="sxs-lookup"><span data-stu-id="82b33-162">Per-user report set</span></span>  <br/> |<span data-ttu-id="82b33-163">いいえ</span><span class="sxs-lookup"><span data-stu-id="82b33-163">No</span></span>  <br/> |<span data-ttu-id="82b33-164">はい</span><span class="sxs-lookup"><span data-stu-id="82b33-164">Yes</span></span>  <br/> |
|<span data-ttu-id="82b33-165">レポートセットのカスタマイズ (レポートの追加、削除、変更)</span><span class="sxs-lookup"><span data-stu-id="82b33-165">Report set customization (add, delete, modify reports)</span></span>  <br/> |<span data-ttu-id="82b33-166">いいえ</span><span class="sxs-lookup"><span data-stu-id="82b33-166">No</span></span>  <br/> |<span data-ttu-id="82b33-167">はい</span><span class="sxs-lookup"><span data-stu-id="82b33-167">Yes</span></span>  <br/> |
|<span data-ttu-id="82b33-168">ビデオベースの画面共有のメトリック</span><span class="sxs-lookup"><span data-stu-id="82b33-168">Video-based screen sharing metrics</span></span>  <br/> |<span data-ttu-id="82b33-169">いいえ</span><span class="sxs-lookup"><span data-stu-id="82b33-169">No</span></span>  <br/> |<span data-ttu-id="82b33-170">はい</span><span class="sxs-lookup"><span data-stu-id="82b33-170">Yes</span></span>  <br/> |
|<span data-ttu-id="82b33-171">ビデオ指標</span><span class="sxs-lookup"><span data-stu-id="82b33-171">Video metrics</span></span>  <br/> |<span data-ttu-id="82b33-172">いいえ</span><span class="sxs-lookup"><span data-stu-id="82b33-172">No</span></span>  <br/> |<span data-ttu-id="82b33-173">はい</span><span class="sxs-lookup"><span data-stu-id="82b33-173">Yes</span></span>  <br/> |
|<span data-ttu-id="82b33-174">利用可能なデータの量</span><span class="sxs-lookup"><span data-stu-id="82b33-174">Amount of data available</span></span>  <br/> |<span data-ttu-id="82b33-175">過去6ヶ月</span><span class="sxs-lookup"><span data-stu-id="82b33-175">Last 6 months</span></span>  <br/> |<span data-ttu-id="82b33-176">過去6ヶ月</span><span class="sxs-lookup"><span data-stu-id="82b33-176">Last 6 months</span></span>  <br/> |
|<span data-ttu-id="82b33-177">Microsoft Teams データ</span><span class="sxs-lookup"><span data-stu-id="82b33-177">Microsoft Teams data</span></span>  <br/> |<span data-ttu-id="82b33-178">はい</span><span class="sxs-lookup"><span data-stu-id="82b33-178">Yes</span></span>  <br/> |<span data-ttu-id="82b33-179">可</span><span class="sxs-lookup"><span data-stu-id="82b33-179">Yes</span></span>  <br/> |
   
### <a name="out-of-the-box-reports"></a><span data-ttu-id="82b33-180">ボックスのないレポート</span><span class="sxs-lookup"><span data-stu-id="82b33-180">Out-of-the-box reports</span></span>

<span data-ttu-id="82b33-181">どちらのエディションも、CQD のエクスペリエンスを提供しており、新しいレポートを作成することなく品質指標を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="82b33-181">Both editions of CQD provide an out-of-the-box experience, giving you call quality metrics without the need to create any new reports.</span></span> <span data-ttu-id="82b33-182">バックエンドでデータが処理されると、レポートでの通話品質データの表示を開始できます。</span><span class="sxs-lookup"><span data-stu-id="82b33-182">Once data is processed in the back-end, you can start seeing call quality data in the reports.</span></span>
  
### <a name="overview-reports"></a><span data-ttu-id="82b33-183">概要レポート</span><span class="sxs-lookup"><span data-stu-id="82b33-183">Overview reports</span></span>

<span data-ttu-id="82b33-184">どちらのエディションの CQD でも、全体的な通話品質情報への優れたエントリポイントが提供されますが、概要レポートでは情報の表示方法は、詳細レポートの場合とは異なります。</span><span class="sxs-lookup"><span data-stu-id="82b33-184">Both editions of the CQD provide a high-level entry point to the overall call quality information, but the way information is presented in Summary Reports is different from that of Detailed Reports.</span></span>
  
<span data-ttu-id="82b33-185">概要レポートには、シンプルなタブ表示のページレポートビューがあり、ユーザーは全体的な通話品質の状態と傾向を簡単に参照して理解することができます。</span><span class="sxs-lookup"><span data-stu-id="82b33-185">Summary Reports provide a simplified tabbed page report view that enables users to quickly browse and understand the overall call quality status and trends.</span></span>
  
<span data-ttu-id="82b33-186">次の4つのタブがあります。</span><span class="sxs-lookup"><span data-stu-id="82b33-186">The four tabs include:</span></span>
  
- <span data-ttu-id="82b33-187">**全体的な通話品質**-すべてのストリームについての情報が提供されます。これは、サーバークライアントストリームとクライアントクライアントストリームを集計したもので、個別のサーバークライアントストリームと、1つの月と1日の傾向の形式で示されています。</span><span class="sxs-lookup"><span data-stu-id="82b33-187">**Overall Call Quality** - provides information about all streams, which is an aggregation of Server-Client streams and Client-Client streams, as well as separate Server-Client and Client-Client streams, in the form of monthly and daily trends.</span></span>
    
- <span data-ttu-id="82b33-188">**サーバー-クライアント**-サーバーエンドポイントとクライアントエンドポイント間のストリームに関するその他の詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="82b33-188">**Server - Client** - provides additional details for the streams between Server and Client endpoints.</span></span>
    
- <span data-ttu-id="82b33-189">**クライアント**-クライアント-2 つのクライアントエンドポイント間のストリームに関するその他の詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="82b33-189">**Client - Client** - provides additional details for the streams between two Client endpoints.</span></span>
    
- <span data-ttu-id="82b33-190">[**音声品質の sla** -Skype For business Online の音声品質の sla に含まれる通話に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="82b33-190">**Voice Quality SLA** - provides information about calls that are included in the Skype for Business Online Voice Quality SLA.</span></span>
    
### <a name="overall-call-quality-tab"></a><span data-ttu-id="82b33-191">[全体的な通話品質] タブ</span><span class="sxs-lookup"><span data-stu-id="82b33-191">Overall Call Quality tab</span></span>

<span data-ttu-id="82b33-192">このタブのデータを使用して、通話品質の状態と傾向を測定します。</span><span class="sxs-lookup"><span data-stu-id="82b33-192">Use the data on this tab to evaluate call quality status and trends by looking at the stream counts and poor percentages.</span></span> <span data-ttu-id="82b33-193">右上隅の凡例は、どの色と視覚要素がこれらのメトリックを表しているかを示しています。</span><span class="sxs-lookup"><span data-stu-id="82b33-193">The legend in the upper-right corner shows which color and visual elements represent these metrics.</span></span>
  
![[通話品質] タブを示すスクリーンショット](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
<span data-ttu-id="82b33-195">ストリームは、良好、低品質、未分類の3つのグループに分類されます。</span><span class="sxs-lookup"><span data-stu-id="82b33-195">Streams are classified in three groups: Good, Poor, and Unclassified.</span></span> <span data-ttu-id="82b33-196">また、分類されたストリームの合計数に*低品質*として分類されたストリームの比率を示す*低品質*の値が計算されます。</span><span class="sxs-lookup"><span data-stu-id="82b33-196">There are also calculated  *Poor %*  values that give you the ratio of streams classified as *Poor*  to the total classified stream count.</span></span> <span data-ttu-id="82b33-197">*低品質のストリーム/(不十分なストリーム + 良好なストリーム) \* 100*では、複数\*\* の*未分類*ストリームによるプレゼンスの影響を受けにくくなります。</span><span class="sxs-lookup"><span data-stu-id="82b33-197">Since *Poor % = Poor streams/ (Poor streams+ Good streams) \* 100*  , this makes the *Poor %*  unaffected by the presence with multiple *Unclassified*  streams.</span></span> <span data-ttu-id="82b33-198">ストリームを低品質または良好な状態として分類するために使用される機能については、「[通話品質ダッシュボードでのストリームの分類」](stream-classification-in-call-quality-dashboard.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82b33-198">For what is used for classifying a stream as poor or good, refer to [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md).</span></span>
  
<span data-ttu-id="82b33-199">ストリーム数の値を測定するには、左側のスケールを使用します。</span><span class="sxs-lookup"><span data-stu-id="82b33-199">Use the scale on the left to measure the stream count values.</span></span>
  
![ストリームカウント値が表示されたスクリーンショット](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
<span data-ttu-id="82b33-201">右側のスケールを使用して、低品質の値を測定します。</span><span class="sxs-lookup"><span data-stu-id="82b33-201">Use the scale on the right to measure the Poor % values.</span></span>
  
![低% の値が表示されたスクリーンショット](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
<span data-ttu-id="82b33-203">また、バーの上にマウスを置くと、実際の数値を取得できます。</span><span class="sxs-lookup"><span data-stu-id="82b33-203">You can also obtain the actual numerical values by hovering the mouse over a bar.</span></span>
  
> [!NOTE]
> <span data-ttu-id="82b33-204">次の例は、非常に小さなサンプルデータセットからの値で、実際の展開には現実的ではありません。</span><span class="sxs-lookup"><span data-stu-id="82b33-204">The following example is from a very small sample data set, and the values aren't realistic for an actual deployment.</span></span> 
  
![マウスを使用してデータにアクセスすることを示すスクリーンショット](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
<span data-ttu-id="82b33-206">ストリームの全体的なボリュームは、計算された低品質の割合がどのように関連しているかを判断するうえで重要な要素です。</span><span class="sxs-lookup"><span data-stu-id="82b33-206">The overall stream volume is an important factor in determining how relevant the calculated Poor percentages are.</span></span> <span data-ttu-id="82b33-207">全体的なストリームの量が少ないほど、報告される低割合の値は、信頼性が低くなります。</span><span class="sxs-lookup"><span data-stu-id="82b33-207">The smaller the volume of overall streams, the less reliable the reported Poor percentage values are.</span></span>
  
### <a name="server-client-tab-and-client-client-tabs"></a><span data-ttu-id="82b33-208">[サーバー-クライアント] タブと [クライアント-クライアント] タブ</span><span class="sxs-lookup"><span data-stu-id="82b33-208">Server-Client tab and Client-Client tabs</span></span>

<span data-ttu-id="82b33-209">次の2つのタブでは、エンドポイント間のシナリオで発生したストリームについて追加の詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="82b33-209">These two tabs provide additional details for the streams that took place in their endpoint-to-endpoint scenarios.</span></span> <span data-ttu-id="82b33-210">[サーバー-クライアント] タブには、折りたたみ可能な4つのセクションがあります。これは、メディアストリームが流れる4つのシナリオを表します。</span><span class="sxs-lookup"><span data-stu-id="82b33-210">The Server-Client tab has four collapsible sections, representing four scenarios under which media streams would flow.</span></span>
  
- <span data-ttu-id="82b33-211">有線 (内部)</span><span class="sxs-lookup"><span data-stu-id="82b33-211">Wired Inside</span></span>
    
- <span data-ttu-id="82b33-212">有線 (外部)</span><span class="sxs-lookup"><span data-stu-id="82b33-212">Wired Outside</span></span>
    
- <span data-ttu-id="82b33-213">Wifi (内部)</span><span class="sxs-lookup"><span data-stu-id="82b33-213">Wifi Inside</span></span>
    
- <span data-ttu-id="82b33-214">Wifi (外部)</span><span class="sxs-lookup"><span data-stu-id="82b33-214">Wifi Outside</span></span>

<span data-ttu-id="82b33-215">同様に、[クライアント-クライアント] タブには、5つの折りたたみ可能なセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="82b33-215">Similarly, the Client-Client tab has five collapsible sections:</span></span>

- <span data-ttu-id="82b33-216">有線-有線 (内部)</span><span class="sxs-lookup"><span data-stu-id="82b33-216">Wired Inside - Wired Inside</span></span>

- <span data-ttu-id="82b33-217">有線-有線 (外部)</span><span class="sxs-lookup"><span data-stu-id="82b33-217">Wired Inside - Wired Outside</span></span>

- <span data-ttu-id="82b33-218">有線 (外部)</span><span class="sxs-lookup"><span data-stu-id="82b33-218">Wired Outside - Wired Outside</span></span>

- <span data-ttu-id="82b33-219">有線-Wifi (内部)</span><span class="sxs-lookup"><span data-stu-id="82b33-219">Wired Inside - Wifi Inside</span></span>

- <span data-ttu-id="82b33-220">有線-Wifi (外部)</span><span class="sxs-lookup"><span data-stu-id="82b33-220">Wired Inside - Wifi Outside</span></span>
    
    
#### <a name="inside-test"></a><span data-ttu-id="82b33-221">内部テスト</span><span class="sxs-lookup"><span data-stu-id="82b33-221">Inside Test</span></span>

<span data-ttu-id="82b33-222">処理中、CQD バックエンドは、構築情報を使用してストリームを*内部*または*外部*として分類します (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="82b33-222">During processing, the CQD back-end classifies a stream as  *Inside*  or *Outside*  using Building information, if it exists.</span></span> <span data-ttu-id="82b33-223">各ストリームのエンドポイントは、サブネットアドレスと関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="82b33-223">Endpoints of each stream are associated with a subnet address.</span></span> <span data-ttu-id="82b33-224">アップロードした建物情報の InsideCorp とマークされているサブネットの一覧にサブネットがある場合、そのサブネットは*内部*と見なされます。</span><span class="sxs-lookup"><span data-stu-id="82b33-224">If the subnet is in the list of the subnets marked InsideCorp in the uploaded Building information, then it is considered *Inside*.</span></span> <span data-ttu-id="82b33-225">作成情報がまだアップロードされていない場合は、内側のテストでは常にストリームが*外部*として分類されます。</span><span class="sxs-lookup"><span data-stu-id="82b33-225">If Building information has not yet been uploaded, then Inside Test will always classify the streams as *Outside*.</span></span> <span data-ttu-id="82b33-226">「サーバーのテスト」のシナリオでは、クライアントのエンドポイントのみが考慮されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="82b33-226">Please note that Inside Test for Server-Client scenario only considers the client endpoint.</span></span> <span data-ttu-id="82b33-227">サーバーは常にユーザーの視点から外れているため、これはテストでは考慮されません。</span><span class="sxs-lookup"><span data-stu-id="82b33-227">Because servers are always outside from a user's perspective, this isn't accounted for in the test.</span></span>
  
#### <a name="wired-vs-wifi"></a><span data-ttu-id="82b33-228">有線と wifi の比較</span><span class="sxs-lookup"><span data-stu-id="82b33-228">Wired vs. wifi</span></span>

<span data-ttu-id="82b33-229">名前が示すように、これは、クライアント接続の種類に基づいた分類条件です。</span><span class="sxs-lookup"><span data-stu-id="82b33-229">As the names indicate, this is a classification criteria based on the type of client connections.</span></span> <span data-ttu-id="82b33-230">この場合も、サーバーは常に有線であり、計算に含まれていません。</span><span class="sxs-lookup"><span data-stu-id="82b33-230">Again, server is always wired and it isn't included in the calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="82b33-231">特定のストリームについて、2つのエンドポイントの一方が Wifi ネットワークに接続されていれば、CQD で Wifi として分類されます。</span><span class="sxs-lookup"><span data-stu-id="82b33-231">Given a stream, if one of the two endpoints is connected to a Wifi network, then it is classified as Wifi in CQD.</span></span> 
  
## <a name="selecting-product-data-to-see-in-reports"></a><span data-ttu-id="82b33-232">レポートで表示する製品データの選択</span><span class="sxs-lookup"><span data-stu-id="82b33-232">Selecting product data to see in reports</span></span>
<a name="BKMKProductFilter"></a>

<span data-ttu-id="82b33-233">概要と位置を拡張したレポートでは、[**製品フィルター** ] ドロップダウンを使用して、すべての製品データ、Microsoft Teams のデータのみ、または Skype For business Online データのみを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="82b33-233">In the Summary and Location Enhanced Reports, you can use the **Product Filter** drop-down to show all product data, only Microsoft Teams data, or only Skype for Business Online data.</span></span>
  
![製品フィルターコントロールオプションを示すスクリーンショット](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
<span data-ttu-id="82b33-235">詳細レポートで**は、Is Teams**ディメンションを使用して、レポートの定義の一部として、Microsoft Teams または Skype For business Online データにデータをフィルター処理することができます。</span><span class="sxs-lookup"><span data-stu-id="82b33-235">In Detailed reports, you can use the **Is Teams** dimension to filter the data to Microsoft Teams or Skype for Business Online data as part of defining the report.</span></span>
  
## <a name="upload-tenant-data-information"></a><span data-ttu-id="82b33-236">テナントデータ情報をアップロードする</span><span class="sxs-lookup"><span data-stu-id="82b33-236">Upload Tenant Data information</span></span>
<a name="BKMKTenantDataInformationUpload"></a>

<span data-ttu-id="82b33-237">CQD Summary レポートダッシュボードには、右上隅にある [設定] メニューから [**テナントデータ**アップロード] を選択することによってアクセスできる**テナントデータアップロード**ページが含まれています。</span><span class="sxs-lookup"><span data-stu-id="82b33-237">The CQD Summary Reports dashboard includes a **Tenant Data Upload** page, accessed by selecting **Tenant Data Upload** from the settings menu in the top-right corner.</span></span> <span data-ttu-id="82b33-238">このページでは、管理者が自分の情報 (IP アドレスと地理的情報のマッピング、各ワイヤレス AP とその MAC アドレスのマッピング、エンドポイントの型のマッピング/モデル/タイプのマッピングなど) をアップロードするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="82b33-238">This page is used for admins to upload their own information, such as mapping of IP address and geographical information, mapping each wireless AP and its MAC address, mapping of Endpoint to Endpoint Make/Model/Type, etc.</span></span>
  
![通話品質ダッシュボードを示すスクリーンショット](media/839c9ab4-0246-46c9-8402-aafd83a0bc63.png)
  
1. <span data-ttu-id="82b33-240">[**テナントデータのアップロード**] ページで、ドロップダウンメニューを使用して、アップロードするデータファイルの種類を選びます。</span><span class="sxs-lookup"><span data-stu-id="82b33-240">On the **Tenant Data Upload** page, use the drop-down menu to choose a data file type for uploading.</span></span> <span data-ttu-id="82b33-241">ファイルのデータ型は、ファイルの内容を示します (たとえば、"建物" は、IP アドレスと建物、およびその他の地理情報のマッピングを意味します)。 "Endpoint" は、エンドポイント名とエンドポイントの型のマッピングを指します。</span><span class="sxs-lookup"><span data-stu-id="82b33-241">The file data type denotes the content of the file (for example, "Building" refers to mapping of IP address and building as well as other geographical information, “Endpoint” refers to mapping of Endpoint Name to Endpoint Make/Model/Type…</span></span> <span data-ttu-id="82b33-242">情報)。</span><span class="sxs-lookup"><span data-stu-id="82b33-242">information).</span></span> <span data-ttu-id="82b33-243">現時点では、cqd.teams.microsoft.com の "ビルディング" と "Endpoint" データ型のアップロードをサポートしています (まだ正式に利用可能ではありません)。 cqd.lync.com は、"構築" データ型のアップロードのみサポートしています。</span><span class="sxs-lookup"><span data-stu-id="82b33-243">Currently we support uploading “Building” and “Endpoint” data types for cqd.teams.microsoft.com (in preview stage and not officially available yet), cqd.lync.com only supports uploading "Building" data type.</span></span> <span data-ttu-id="82b33-244">今後のリリースでは、さらにいくつかのデータ型が追加されます。</span><span class="sxs-lookup"><span data-stu-id="82b33-244">A few more data types will be added with subsequent releases.</span></span>
    
2. <span data-ttu-id="82b33-245">ファイルデータの種類を選んだら、[**参照**] をクリックしてデータファイルを選びます。</span><span class="sxs-lookup"><span data-stu-id="82b33-245">After selecting the file data type, click **Browse** to choose a data file.</span></span>
    
   - <span data-ttu-id="82b33-246">データファイルは、tsv (タブ区切り値) ファイルまたは .csv (カンマ区切り値) ファイルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="82b33-246">The data file must be a .tsv (Tab-separated values) file or a .csv (Comma-separated value) file.</span></span> <span data-ttu-id="82b33-247">.Csv ファイルを使用している場合、カンマが含まれているフィールドは引用符で囲む必要があります。または、コンマが削除されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="82b33-247">If using a .csv file, any field that contains a comma must be surrounded by quotes or have the comma removed.</span></span> <span data-ttu-id="82b33-248">たとえば、作成名が ny で NY である場合は、"NY, NY" として入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82b33-248">For example, if your building name is NY,NY, in the .csv file it should be entered as "NY,NY".</span></span>
    
   - <span data-ttu-id="82b33-249">データファイルのサイズは、50 MB よりも大きくする必要があります。</span><span class="sxs-lookup"><span data-stu-id="82b33-249">The data file must be no larger than 50MB in size.</span></span>

   - <span data-ttu-id="82b33-250">Cqd.teams.microsoft.com にアップロードされたファイルには、クエリのパフォーマンスを速く維持するために、100万の行の上限が拡張されています。</span><span class="sxs-lookup"><span data-stu-id="82b33-250">Files uploaded to cqd.teams.microsoft.com have an expanded row limit of 1,000,000 in order to keep query performance fast.</span></span> <span data-ttu-id="82b33-251">Cqd.lync.com にもこの制限を課すことができます。</span><span class="sxs-lookup"><span data-stu-id="82b33-251">We may impose that limit on cqd.lync.com as well.</span></span>
    
   - <span data-ttu-id="82b33-252">データファイルの各列は、このトピックの後半で説明するように、定義済みのデータ型と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="82b33-252">For each data file, each column in the file must match a predefined data type, discussed later in this topic.</span></span>
    
3. <span data-ttu-id="82b33-253">データファイルを選択した後、[**開始日**] を指定し、必要に応じて**終了日を指定**します。</span><span class="sxs-lookup"><span data-stu-id="82b33-253">After selecting a data file, specify **Start date** and, optionally, **Specify an end date**.</span></span>
    
4. <span data-ttu-id="82b33-254">[**開始日**] を選んだら、[**アップロード**] を選んで、CQD サーバーにファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="82b33-254">After selecting **Start date**, select **Upload** to upload the file to the CQD server.</span></span>
    
    <span data-ttu-id="82b33-255">ファイルがアップロードされる前に、まず検証されます。</span><span class="sxs-lookup"><span data-stu-id="82b33-255">Before the file is uploaded, it is first validated.</span></span> <span data-ttu-id="82b33-256">検証が完了すると、Azure blob に格納されます。</span><span class="sxs-lookup"><span data-stu-id="82b33-256">Once validated, it is stored in an Azure blob.</span></span> <span data-ttu-id="82b33-257">検証に失敗した場合、またはファイルが Azure blob に保存されていない場合は、エラーメッセージが表示され、ファイルに修正を要求します。</span><span class="sxs-lookup"><span data-stu-id="82b33-257">If validation fails or the file fails to be stored in an Azure blob, an error message is displayed requesting a correction to the file.</span></span> <span data-ttu-id="82b33-258">次の図は、データファイルの列数が正しくない場合に発生するエラーを示しています。</span><span class="sxs-lookup"><span data-stu-id="82b33-258">The following image shows an error occurring when the number of columns in the data file is incorrect.</span></span>
    
     ![アップロード検証エラーが表示されたスクリーンショット](media/22716a32-3d3d-4870-983c-46089e8b212a.png)
  
5. <span data-ttu-id="82b33-260">検証中にエラーが発生しなかった場合、ファイルのアップロードは成功します。</span><span class="sxs-lookup"><span data-stu-id="82b33-260">If no errors occur during validation, the file upload will succeed.</span></span> <span data-ttu-id="82b33-261">アップロードしたデータファイルが **[マイアップロード**] テーブルに表示されます。これにより、そのページの下部にある現在のテナントのすべてのアップロードされたファイルの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="82b33-261">You can then see the uploaded data file in the **My uploads** table, which shows the full list of all uploaded files for the current tenant at the bottom of that page.</span></span>
    
    <span data-ttu-id="82b33-262">各レコードには、アップロードされたテナントデータファイルが1つ表示されます。これには、ファイルの種類、最終更新時刻、[期間]、[説明]、[削除] アイコン、ダウンロードアイコンがあります。</span><span class="sxs-lookup"><span data-stu-id="82b33-262">Each record shows one uploaded tenant data file, with file type, last update time, time period, description, a remove icon, and a download icon.</span></span> <span data-ttu-id="82b33-263">ファイルを削除するには、表のゴミ箱アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="82b33-263">To remove a file, select the trash bin icon in the table.</span></span> <span data-ttu-id="82b33-264">ファイルをダウンロードするには、表の [**ダウンロード**] 列の [ダウンロード] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="82b33-264">To download a file, select the download icon in the **Download** column of the table.</span></span>
    
     ![[マイアップロード] テーブルが表示されたスクリーンショット](media/4168a883-bbea-461a-80b1-42eedf2e7732.png)

6. <span data-ttu-id="82b33-266">複数の建物データファイルまたは複数のエンドポイントデータファイルを使用する場合は、一部のレポートの操作速度が遅くなることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="82b33-266">Note that if you choose to use multiple building data files or multiple endpoint data files, the operation speed of some reports will be slower.</span></span>

### <a name="tenant-data-file-format-and-structure"></a><span data-ttu-id="82b33-267">テナントデータファイルの形式と構造</span><span class="sxs-lookup"><span data-stu-id="82b33-267">Tenant data file format and structure</span></span>
<span data-ttu-id="82b33-268"><a name="BKMKTenantDataFile"> </a></span><span class="sxs-lookup"><span data-stu-id="82b33-268"></span></span>

### <a name="building-data-file"></a><span data-ttu-id="82b33-269">データファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="82b33-269">Building data file</span></span>
<span data-ttu-id="82b33-270">CQD では、最初に Network + NetworkRange 列を展開して Subnet 列を作成し、サブネット列を呼び出しレコードの最初の Subnet/第2サブネット列に参加させて、建物名、市区町村、国/地域を表示します。</span><span class="sxs-lookup"><span data-stu-id="82b33-270">CQD uses Building data file by first deriving the Subnet column from expanding the Network+NetworkRange column, then joining the Subnet column to the call record’s First Subnet/Second Subnet column to show Building/City/Country/Region…</span></span> <span data-ttu-id="82b33-271">詳しく.</span><span class="sxs-lookup"><span data-stu-id="82b33-271">information.</span></span> <span data-ttu-id="82b33-272">アップロードするデータファイルの形式は、次の条件を満たしている必要があります。これは、アップロード前に検証チェックに合格するためです。</span><span class="sxs-lookup"><span data-stu-id="82b33-272">The format of the data file you upload must meet the following to pass the validation check before uploading.</span></span>
  
- <span data-ttu-id="82b33-273">ファイルは、各行の列がタブで区切られる .tsv ファイル、または各列がカンマで区切られた .csv ファイルのいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="82b33-273">The file must be either a .tsv file, which means, in each row, columns are separated by a TAB, or a .csv file with each column separated by a comma.</span></span>
    
- <span data-ttu-id="82b33-274">データファイルの内容には、テーブル見出しは含まれません。</span><span class="sxs-lookup"><span data-stu-id="82b33-274">The content of the data file doesn't include table headers.</span></span> <span data-ttu-id="82b33-275">つまり、データファイルの最初の行は、"ネットワーク" のような見出しではなく、実際のデータである必要があります。</span><span class="sxs-lookup"><span data-stu-id="82b33-275">That means the first line of the data file should be real data, not headers like "Network," etc.</span></span>
    
- <span data-ttu-id="82b33-276">列ごとに、データ型に指定できるのは String、Number、またはブール値のみです。</span><span class="sxs-lookup"><span data-stu-id="82b33-276">For each column, the data type can only be String, Number, or Bool.</span></span> <span data-ttu-id="82b33-277">数値の場合、値は数値である必要があります。ブール値の場合は、0または1のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="82b33-277">If it is Number, the value must be a numeric value; if it is Bool, the value must be either 0 or 1.</span></span>
    
- <span data-ttu-id="82b33-278">列ごとにデータ型が文字列の場合、データは空にすることができます (ただし、その場合も、適切な区切り記号 (タブまたはコンマ) で区切る必要があります。</span><span class="sxs-lookup"><span data-stu-id="82b33-278">For each column, if the data type is string, the data can be empty (but still must be separated by an appropriate delimiter (i.e., a tab or comma).</span></span> <span data-ttu-id="82b33-279">これにより、このフィールドは空の文字列値として割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="82b33-279">This just assigns that field an empty string value.</span></span>
    
- <span data-ttu-id="82b33-280">各行には14個の列がある必要があります。各列のデータ型は次のとおりです。列の順序は、次の表の順序になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="82b33-280">There must be 14 columns for each row, each column must have the following data type, and the columns must be in the order listed in the following table:</span></span>
    
|<span data-ttu-id="82b33-281">**列名**</span><span class="sxs-lookup"><span data-stu-id="82b33-281">**Column Name**</span></span>|<span data-ttu-id="82b33-282">**データ型**</span><span class="sxs-lookup"><span data-stu-id="82b33-282">**Data type**</span></span>|<span data-ttu-id="82b33-283">**例**</span><span class="sxs-lookup"><span data-stu-id="82b33-283">**Example**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="82b33-284">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="82b33-284">Network</span></span>  <br/> |<span data-ttu-id="82b33-285">String</span><span class="sxs-lookup"><span data-stu-id="82b33-285">String</span></span>  <br/> |<span data-ttu-id="82b33-286">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="82b33-286">192.168.1.0</span></span>  <br/> |
|<span data-ttu-id="82b33-287">NetworkName</span><span class="sxs-lookup"><span data-stu-id="82b33-287">NetworkName</span></span>  <br/> |<span data-ttu-id="82b33-288">String</span><span class="sxs-lookup"><span data-stu-id="82b33-288">String</span></span>  <br/> |<span data-ttu-id="82b33-289">米国/シアトル/シアトル-SEA-1</span><span class="sxs-lookup"><span data-stu-id="82b33-289">USA/Seattle/SEATTLE-SEA-1</span></span>  <br/> |
|<span data-ttu-id="82b33-290">NetworkRange</span><span class="sxs-lookup"><span data-stu-id="82b33-290">NetworkRange</span></span>  <br/> |<span data-ttu-id="82b33-291">数値</span><span class="sxs-lookup"><span data-stu-id="82b33-291">Number</span></span>  <br/> |<span data-ttu-id="82b33-292">#</span><span class="sxs-lookup"><span data-stu-id="82b33-292">26</span></span>  <br/> |
|<span data-ttu-id="82b33-293">BuildingName</span><span class="sxs-lookup"><span data-stu-id="82b33-293">BuildingName</span></span>  <br/> |<span data-ttu-id="82b33-294">String</span><span class="sxs-lookup"><span data-stu-id="82b33-294">String</span></span>  <br/> |<span data-ttu-id="82b33-295">シアトル-SEA-1</span><span class="sxs-lookup"><span data-stu-id="82b33-295">SEATTLE-SEA-1</span></span>  <br/> |
|<span data-ttu-id="82b33-296">OwnershipType</span><span class="sxs-lookup"><span data-stu-id="82b33-296">OwnershipType</span></span>  <br/> |<span data-ttu-id="82b33-297">String</span><span class="sxs-lookup"><span data-stu-id="82b33-297">String</span></span>  <br/> |<span data-ttu-id="82b33-298">コントソ</span><span class="sxs-lookup"><span data-stu-id="82b33-298">Contoso</span></span>  <br/> |
|<span data-ttu-id="82b33-299">BuildingType</span><span class="sxs-lookup"><span data-stu-id="82b33-299">BuildingType</span></span>  <br/> |<span data-ttu-id="82b33-300">String</span><span class="sxs-lookup"><span data-stu-id="82b33-300">String</span></span>  <br/> |<span data-ttu-id="82b33-301">IT の終了</span><span class="sxs-lookup"><span data-stu-id="82b33-301">IT Termination</span></span>  <br/> |
|<span data-ttu-id="82b33-302">BuildingOfficeType</span><span class="sxs-lookup"><span data-stu-id="82b33-302">BuildingOfficeType</span></span>  <br/> |<span data-ttu-id="82b33-303">String</span><span class="sxs-lookup"><span data-stu-id="82b33-303">String</span></span>  <br/> |<span data-ttu-id="82b33-304">エンジニアリング</span><span class="sxs-lookup"><span data-stu-id="82b33-304">Engineering</span></span>  <br/> |
|<span data-ttu-id="82b33-305">市区町村</span><span class="sxs-lookup"><span data-stu-id="82b33-305">City</span></span>  <br/> |<span data-ttu-id="82b33-306">String</span><span class="sxs-lookup"><span data-stu-id="82b33-306">String</span></span>  <br/> |<span data-ttu-id="82b33-307">調布市調布ヶ丘</span><span class="sxs-lookup"><span data-stu-id="82b33-307">Seattle</span></span>  <br/> |
|<span data-ttu-id="82b33-308">ZipCode</span><span class="sxs-lookup"><span data-stu-id="82b33-308">ZipCode</span></span>  <br/> |<span data-ttu-id="82b33-309">String</span><span class="sxs-lookup"><span data-stu-id="82b33-309">String</span></span>  <br/> |<span data-ttu-id="82b33-310">98001</span><span class="sxs-lookup"><span data-stu-id="82b33-310">98001</span></span>  <br/> |
|<span data-ttu-id="82b33-311">居住</span><span class="sxs-lookup"><span data-stu-id="82b33-311">Country</span></span>  <br/> |<span data-ttu-id="82b33-312">String</span><span class="sxs-lookup"><span data-stu-id="82b33-312">String</span></span>  <br/> |<span data-ttu-id="82b33-313">プロセッサー</span><span class="sxs-lookup"><span data-stu-id="82b33-313">US</span></span>  <br/> |
|<span data-ttu-id="82b33-314">都道府県</span><span class="sxs-lookup"><span data-stu-id="82b33-314">State</span></span>  <br/> |<span data-ttu-id="82b33-315">String</span><span class="sxs-lookup"><span data-stu-id="82b33-315">String</span></span>  <br/> |<span data-ttu-id="82b33-316">WA</span><span class="sxs-lookup"><span data-stu-id="82b33-316">WA</span></span>  <br/> |
|<span data-ttu-id="82b33-317">Region</span><span class="sxs-lookup"><span data-stu-id="82b33-317">Region</span></span>  <br/> |<span data-ttu-id="82b33-318">String</span><span class="sxs-lookup"><span data-stu-id="82b33-318">String</span></span>  <br/> |<span data-ttu-id="82b33-319">MSUS</span><span class="sxs-lookup"><span data-stu-id="82b33-319">MSUS</span></span>  <br/> |
|<span data-ttu-id="82b33-320">InsideCorp</span><span class="sxs-lookup"><span data-stu-id="82b33-320">InsideCorp</span></span>  <br/> |<span data-ttu-id="82b33-321">ブール</span><span class="sxs-lookup"><span data-stu-id="82b33-321">Bool</span></span>  <br/> |<span data-ttu-id="82b33-322">1</span><span class="sxs-lookup"><span data-stu-id="82b33-322">1</span></span>  <br/> |
|<span data-ttu-id="82b33-323">ExpressRoute</span><span class="sxs-lookup"><span data-stu-id="82b33-323">ExpressRoute</span></span>  <br/> |<span data-ttu-id="82b33-324">ブール</span><span class="sxs-lookup"><span data-stu-id="82b33-324">Bool</span></span>  <br/> |<span data-ttu-id="82b33-325">0</span><span class="sxs-lookup"><span data-stu-id="82b33-325">0</span></span>  <br/> |
   
> [!IMPORTANT]
> <span data-ttu-id="82b33-326">ネットワーク範囲は、スーパーネット (単一のルーティングプレフィックスを持つ複数のサブネットの組み合わせ) を表すために使用できます。</span><span class="sxs-lookup"><span data-stu-id="82b33-326">The network range can be used to represent a supernet (combination of several subnets with a single routing prefix).</span></span> <span data-ttu-id="82b33-327">新しくなったすべての文書のアップロードで、重複範囲が確認されます。</span><span class="sxs-lookup"><span data-stu-id="82b33-327">All new building uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="82b33-328">以前にビルドファイルをアップロードしたことがある場合は、現在のファイルをダウンロードして再アップロードし、重複を特定し、問題を解決してからもう一度アップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="82b33-328">If you have previously uploaded a building file, you should download the current file and re-upload it to identify any overlaps and fix the issue before uploading again.</span></span> <span data-ttu-id="82b33-329">以前にアップロードされたファイルが重なっていると、サブネットとレポートの建物とのマッピングが間違っている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="82b33-329">Any overlap in previously uploaded files may result in the wrong mappings of subnets to buildings in the reports.</span></span> <span data-ttu-id="82b33-330">特定の VPN の実装では、サブネット情報が正確に報告されません。</span><span class="sxs-lookup"><span data-stu-id="82b33-330">Certain VPN implementations do not accurately report the subnet information.</span></span> <span data-ttu-id="82b33-331">構成ファイルに VPN サブネットを追加するときは、サブネットのエントリの1つではなく、個別の32ビットネットワークとして、VPN サブネットの各アドレスに個別のエントリを追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="82b33-331">It is recommended that when adding a VPN subnet to the building file, instead of one entry for the subnet, separate entries are added for each address in the VPN subnet as a separate 32-bit network.</span></span> <span data-ttu-id="82b33-332">各行には、同じビルドメタデータを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="82b33-332">Each row can have the same building metadata.</span></span> <span data-ttu-id="82b33-333">たとえば、172.16.18.0/24 の1行ではなく、256行と、172.16.18.0/32 と 172.16.18.255/32 の間の各アドレスに1つの行が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="82b33-333">For example, instead of one row for 172.16.18.0/24, you should have 256 rows, with one row for each address between 172.16.18.0/32 and 172.16.18.255/32, inclusive.</span></span> 

### <a name="endpoint-data-file"></a><span data-ttu-id="82b33-334">エンドポイントデータファイル</span><span class="sxs-lookup"><span data-stu-id="82b33-334">Endpoint data file</span></span>
<span data-ttu-id="82b33-335">CQD は、EndpointName 列を呼び出しレコードの [最初のクライアントエンドポイント名/第2クライアントエンドポイント名] 列に結合してエンドポイントの作成/モデル/タイプの情報を表示することによって、エンドポイントデータファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="82b33-335">CQD uses Endpoint data file by joining its EndpointName column to the call record’s First Client Endpoint Name/Second Client Endpoint Name column to show Endpoint Make/Model/Type information.</span></span> <span data-ttu-id="82b33-336">アップロードするデータファイルの形式は、次の条件を満たしている必要があります。これは、アップロード前に検証チェックに合格するためです。</span><span class="sxs-lookup"><span data-stu-id="82b33-336">The format of the data file you upload must meet the following to pass the validation check before uploading.</span></span>

- <span data-ttu-id="82b33-337">ファイルは、各行の列がタブで区切られる .tsv ファイル、または各列がカンマで区切られた .csv ファイルのいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="82b33-337">The file must be either a .tsv file, which means, in each row, columns are separated by a TAB, or a .csv file with each column separated by a comma.</span></span>

- <span data-ttu-id="82b33-338">データファイルの内容には、テーブル見出しは含まれません。</span><span class="sxs-lookup"><span data-stu-id="82b33-338">The content of the data file doesn't include table headers.</span></span> <span data-ttu-id="82b33-339">つまり、データファイルの最初の行は、"EndpointName" のように、ヘッダーではなく実際のデータである必要があります。</span><span class="sxs-lookup"><span data-stu-id="82b33-339">That means the first line of the data file should be real data, not headers like "EndpointName," etc.</span></span>

- <span data-ttu-id="82b33-340">列ごとに、データ型は String のみにすることができ、64文字以内にする必要があります。これは最大許容サイズです。</span><span class="sxs-lookup"><span data-stu-id="82b33-340">For each column, the data type can only be String and it should have no more than 64 chars, which is maximum allowed length.</span></span>

- <span data-ttu-id="82b33-341">列ごとに、データを空にすることができます (ただし、適切な区切り記号 (タブまたはコンマ) で区切る必要があります。</span><span class="sxs-lookup"><span data-stu-id="82b33-341">For each column, the data can be empty (but still must be separated by an appropriate delimiter (i.e., a tab or comma).</span></span> <span data-ttu-id="82b33-342">これにより、このフィールドは空の文字列値として割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="82b33-342">This just assigns that field an empty string value.</span></span>

- <span data-ttu-id="82b33-343">各行には7つの列があり、列は、次の表の順序になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="82b33-343">There must be 7 columns for each row and the columns must be in the order listed in the following table.</span></span>

- <span data-ttu-id="82b33-344">EndpointName は一意である必要があります。重複しているため、重複している可能性があるため、アップロードは失敗します。</span><span class="sxs-lookup"><span data-stu-id="82b33-344">EndpointName must be unique otherwise upload will fail due to duplicate row as it will cause incorrect joining.</span></span>

-  <span data-ttu-id="82b33-345">EndpointLabel1、EndpointLabel2、EndpointLable3 はユーザーによるカスタマイズが可能なラベルで、空の文字列または値は、"IT 部門が指定した2018ノート Pc"、"アセットタグ 5678" のようなものです。々.</span><span class="sxs-lookup"><span data-stu-id="82b33-345">EndpointLabel1, EndpointLabel2, EndpointLable3 are user customizable labels, they can be empty strings or value users prefer such as “IT Department designated 2018 Laptop”, “Asset Tag 5678” …etc.</span></span>

|<span data-ttu-id="82b33-346">**列名**</span><span class="sxs-lookup"><span data-stu-id="82b33-346">**Column Name**</span></span>|<span data-ttu-id="82b33-347">**データ型**</span><span class="sxs-lookup"><span data-stu-id="82b33-347">**Data type**</span></span>|<span data-ttu-id="82b33-348">**例**</span><span class="sxs-lookup"><span data-stu-id="82b33-348">**Example**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="82b33-349">EndpointName</span><span class="sxs-lookup"><span data-stu-id="82b33-349">EndpointName</span></span>  <br/> |<span data-ttu-id="82b33-350">String</span><span class="sxs-lookup"><span data-stu-id="82b33-350">String</span></span>  <br/> |<span data-ttu-id="82b33-351">1409W3534</span><span class="sxs-lookup"><span data-stu-id="82b33-351">1409W3534</span></span>  <br/> |
|<span data-ttu-id="82b33-352">EndpointMake</span><span class="sxs-lookup"><span data-stu-id="82b33-352">EndpointMake</span></span>  <br/> |<span data-ttu-id="82b33-353">String</span><span class="sxs-lookup"><span data-stu-id="82b33-353">String</span></span>  <br/> |<span data-ttu-id="82b33-354">Fabrikam Inc.</span><span class="sxs-lookup"><span data-stu-id="82b33-354">Fabrikam Inc</span></span>  <br/> |
|<span data-ttu-id="82b33-355">EndpointModel</span><span class="sxs-lookup"><span data-stu-id="82b33-355">EndpointModel</span></span>  <br/> |<span data-ttu-id="82b33-356">String</span><span class="sxs-lookup"><span data-stu-id="82b33-356">String</span></span>  <br/> |<span data-ttu-id="82b33-357">Fabrikam モデル123</span><span class="sxs-lookup"><span data-stu-id="82b33-357">Fabrikam Model 123</span></span>  <br/> |
|<span data-ttu-id="82b33-358">EndpointType</span><span class="sxs-lookup"><span data-stu-id="82b33-358">EndpointType</span></span>   <br/> |<span data-ttu-id="82b33-359">String</span><span class="sxs-lookup"><span data-stu-id="82b33-359">String</span></span>  <br/> |<span data-ttu-id="82b33-360">コンピューター</span><span class="sxs-lookup"><span data-stu-id="82b33-360">Laptop</span></span>  <br/> |
|<span data-ttu-id="82b33-361">EndpointLabel1</span><span class="sxs-lookup"><span data-stu-id="82b33-361">EndpointLabel1</span></span>  <br/> |<span data-ttu-id="82b33-362">String</span><span class="sxs-lookup"><span data-stu-id="82b33-362">String</span></span>  <br/> |<span data-ttu-id="82b33-363">指定した2018ノート Pc</span><span class="sxs-lookup"><span data-stu-id="82b33-363">IT designated 2018 Laptop</span></span>  <br/> |
|<span data-ttu-id="82b33-364">EndpointLabel2</span><span class="sxs-lookup"><span data-stu-id="82b33-364">EndpointLabel2</span></span>  <br/> |<span data-ttu-id="82b33-365">String</span><span class="sxs-lookup"><span data-stu-id="82b33-365">String</span></span>  <br/> |<span data-ttu-id="82b33-366">資産タグ5678</span><span class="sxs-lookup"><span data-stu-id="82b33-366">Asset Tag 5678</span></span>  <br/> |
|<span data-ttu-id="82b33-367">EndpointLabel3</span><span class="sxs-lookup"><span data-stu-id="82b33-367">EndpointLabel3</span></span>  <br/> |<span data-ttu-id="82b33-368">String</span><span class="sxs-lookup"><span data-stu-id="82b33-368">String</span></span>  <br/> |<span data-ttu-id="82b33-369">2018を購入する</span><span class="sxs-lookup"><span data-stu-id="82b33-369">Purchase 2018</span></span>   <br/> |


## <a name="selecting-media-type-in-detailed-reports"></a><span data-ttu-id="82b33-370">詳細レポートでのメディアの種類の選択</span><span class="sxs-lookup"><span data-stu-id="82b33-370">Selecting media type in detailed reports</span></span>
<a name="BKMKMediaType"></a>

<span data-ttu-id="82b33-371">詳細レポートでは、音声、ビデオ、アプリケーション共有、ビデオベースの画面共有メディアを使用する場合の品質とメディアの信頼性をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="82b33-371">The detailed reports support looking at quality and media reliability for audio, video, application sharing, and video-based screen-sharing media types.</span></span> <span data-ttu-id="82b33-372">1つのメディアの種類に固有のディメンション、メジャー、フィルターには、プレフィックスとして "Audio"、"Video"、"AppSharing"、または "VBSS" があります。</span><span class="sxs-lookup"><span data-stu-id="82b33-372">Dimensions, measures, and filters that are specific to a single media type have "Audio", "Video", "AppSharing", or "VBSS" as a prefix.</span></span>
  
![通話品質ダッシュボードのサイズを示すスクリーンショット。](media/ae132202-d6dc-43bd-b8b3-ea9c24c519e8.png)
  
<span data-ttu-id="82b33-374">1つのメディアの種類の寸法とメジャーを表示する場合は、新しい MediaType ディメンションとフィルターが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="82b33-374">If you want to view the dimensions and measures for a single media type, the new MediaType dimension and filter may be required.</span></span> <span data-ttu-id="82b33-375">たとえば、さまざまな種類のメディアにわたるセッションの合計数を表示するレポートを作成するには、MediaType ディメンションを含めます。</span><span class="sxs-lookup"><span data-stu-id="82b33-375">For example, to have a report that shows the total session counts across different media types, include the MediaType dimension.</span></span>
  
![通話品質ダッシュボードの合計ストリーム数を示すスクリーンショット。](media/21d5d0dc-2321-415e-8ef2-cea06165601c.png)

## <a name="related-topics"></a><span data-ttu-id="82b33-377">関連トピック</span><span class="sxs-lookup"><span data-stu-id="82b33-377">Related topics</span></span>
[<span data-ttu-id="82b33-378">Skype for Business の通話分析をセットアップする</span><span class="sxs-lookup"><span data-stu-id="82b33-378">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="82b33-379">通話分析を使用して通話品質の低下をトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="82b33-379">Use Call Analytics to troubleshoot poor  call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="82b33-380">通話分析および通話品質ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="82b33-380">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
