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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.ToolsCallQualityDashboard
- ms.teamsadmincenter.directrouting.cqd
ms.custom:
- Reporting
description: 'オンにし、ビジネス オンライン コール品質のダッシュ ボードに、Skype を使用し、通話の品質の概要のレポートを取得する方法を参照してください。 '
ms.openlocfilehash: 134d0f636719592edca1060d86fbf4fb7c2d9db6
ms.sourcegitcommit: 70d4d02a3cc894f2f197aeea459ac079cde63877
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2019
ms.locfileid: "30543144"
---
# <a name="turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a><span data-ttu-id="6249f-103">有効にして、マイクロソフトのチームと Skype のオンライン ビジネスの品質のダッシュ ボードの呼び出しを使用して</span><span class="sxs-lookup"><span data-stu-id="6249f-103">Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online</span></span>

<span data-ttu-id="6249f-104">呼び出し品質ダッシュ ボードを使用して、通話の品質を監視するために Office 365 の組織を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6249f-104">Learn how to configure your Office 365 organization to use the Call Quality Dashboard to monitor call quality.</span></span>
  
<span data-ttu-id="6249f-105">マイクロソフト チームの呼び出し品質ダッシュ ボード (救難) とオンライン ビジネスの Skype では、ビジネス サービスのマイクロソフトのチームと Skype を使用して行われた通話の品質の洞察を得るために。</span><span class="sxs-lookup"><span data-stu-id="6249f-105">The Call Quality Dashboard (CQD) for Microsoft Teams and Skype for Business Online allows you to gain insights into the quality of calls made using Microsoft Teams and Skype for Business services.</span></span> <span data-ttu-id="6249f-106">このトピックでは、データの収集を開始するために完了する必要があります手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="6249f-106">This topic describes the steps you'll need to complete to start collecting data.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6249f-107">救難の詳細なレポートは、現在テクニカル プレビューとして使用可能ですが、すべての顧客に利用できます。</span><span class="sxs-lookup"><span data-stu-id="6249f-107">The CQD detailed reports are currently available as Tech Preview but available to all customers.</span></span> 
  
## <a name="latest-changes-and-updates"></a><span data-ttu-id="6249f-108">最新の変更と更新</span><span class="sxs-lookup"><span data-stu-id="6249f-108">Latest changes and updates</span></span>

<span data-ttu-id="6249f-109">救難に最新の変更内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6249f-109">The most recent changes to CQD are as follows:</span></span>
  
- <span data-ttu-id="6249f-110">ビジネスをオンラインでのデータの Skype の他のマイクロソフトのチーム データが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6249f-110">Includes Microsoft Teams data in addition to Skype for Business Online data.</span></span>
    
- <span data-ttu-id="6249f-111">サマリー レポートには、ビジネスをオンラインでのデータのすべてのデータ、マイクロソフトのチームのデータ、または Skype を選択するのには製品のフィルターが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6249f-111">Summary reports include a product filter to select all data, Microsoft Teams data, or Skype for Business Online data.</span></span>

- <span data-ttu-id="6249f-112">ビデオおよび VBSS のストリームの品質分類ロジックが更新されました。</span><span class="sxs-lookup"><span data-stu-id="6249f-112">Video and VBSS stream quality classification logic has been updated.</span></span> <span data-ttu-id="6249f-113">最新の分類子の定義については、[品質のダッシュ ボードの呼び出しでストリームの分類](stream-classification-in-call-quality-dashboard.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6249f-113">Refer to [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md) for the latest classifier definitions.</span></span>

<span data-ttu-id="6249f-114">[ディメンションとメジャーのコール品質のダッシュ ボードで使用可能な](dimensions-and-measures-available-in-call-quality-dashboard.md)一覧については、この資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6249f-114">Refer to this article for a list of [Dimensions and measures available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6249f-115">リンクをクリックしてダッシュ ボードに対する更新や変更についての情報を参照して、**朗報!**</span><span class="sxs-lookup"><span data-stu-id="6249f-115">Information about updates and changes to the dashboard can be found by clicking the link in the **Good news!**</span></span> <span data-ttu-id="6249f-116">ダッシュ ボードに表示する場合のバナーです。</span><span class="sxs-lookup"><span data-stu-id="6249f-116">banner when it is displayed on the dashboard.</span></span>
  
## <a name="activate-microsoft-call-quality-dashboard-cqd-summary-reports"></a><span data-ttu-id="6249f-117">Microsoft 呼び出し品質ダッシュ ボード (救難) の要約レポートをアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="6249f-117">Activate Microsoft Call Quality Dashboard (CQD) Summary Reports</span></span>

<span data-ttu-id="6249f-118">救難を使用する前に、Office 365 の組織を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6249f-118">Before you can start using the CQD, you'll need to activate it for your Office 365 organization.</span></span>
 
<span data-ttu-id="6249f-119">![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="6249f-119">![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="6249f-120">、管理者アカウントを使用して、Office 365 の組織にサインインし、管理センターを開くに**管理者**のタイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="6249f-120">Sign in to your Office 365 organization using an admin account, and then select the **Admin** tile to open the Admin center.</span></span>
    
2. <span data-ttu-id="6249f-121">**管理センター**を、下の左側のウィンドウで開くには、Skype のビジネス管理センターに**ビジネス用の Skype**を選択します。</span><span class="sxs-lookup"><span data-stu-id="6249f-121">In the left pane, under **Admin centers**, select **Skype for Business** to open the Skype for Business admin center.</span></span>
    
3. <span data-ttu-id="6249f-122">Skype のビジネス管理センターでは、左側のウィンドウで**ツール**を選択し、 **Skype**ビジネス オンライン コール品質のダッシュ ボードのします。</span><span class="sxs-lookup"><span data-stu-id="6249f-122">In the Skype for Business admin center, select **Tools** in the left pane, and then select **Skype for Business Online Call Quality Dashboard**.</span></span>
    
     ![Skype のビジネス ツール](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)
  
4. <span data-ttu-id="6249f-124">[開く] ページで、グローバル管理者アカウントでサインインし、が表示されたら、アカウントの資格情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="6249f-124">On the page that opens, sign in with your Global Administrator account, and then provide the credentials for the account when prompted.</span></span>
    
     ![救難ログイン](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
<span data-ttu-id="6249f-126">サインイン後、1 回だけをアクティブ化、CQD はデータの収集と処理を開始します。</span><span class="sxs-lookup"><span data-stu-id="6249f-126">After you sign in, once activated, the CQD will begin collecting and processing data.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6249f-127">いくつかのレポートには意味のある結果を表示するための十分なデータの処理に時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6249f-127">It may take a couple of hours to process enough data to display meaningful results in the reports.</span></span> 
  
## <a name="features-of-the-call-quality-dashboard-for-skype-for-business-online"></a><span data-ttu-id="6249f-128">オンライン ビジネスの Skype の通話品質のダッシュ ボードの機能</span><span class="sxs-lookup"><span data-stu-id="6249f-128">Features of the Call Quality Dashboard for Skype for Business Online</span></span>
<span data-ttu-id="6249f-129"><a name="BKMKFeaturesOfTheCQD"> </a></span><span class="sxs-lookup"><span data-stu-id="6249f-129"></span></span>

<span data-ttu-id="6249f-130">救難の概要のレポートでは、計画の詳細なレポート機能のサブセットを提供します。</span><span class="sxs-lookup"><span data-stu-id="6249f-130">CQD Summary Reports provide a subset of the features planned for Detailed Reports.</span></span> <span data-ttu-id="6249f-131">ここで 2 つのエディションの相違点の概要します。</span><span class="sxs-lookup"><span data-stu-id="6249f-131">The differences between the two editions are summarized here:</span></span>
  
|<span data-ttu-id="6249f-132">**機能**</span><span class="sxs-lookup"><span data-stu-id="6249f-132">**Feature**</span></span>|<span data-ttu-id="6249f-133">**サマリー ・ レポート**</span><span class="sxs-lookup"><span data-stu-id="6249f-133">**Summary Reports**</span></span>|<span data-ttu-id="6249f-134">**詳細なレポート**</span><span class="sxs-lookup"><span data-stu-id="6249f-134">**Detailed Reports**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6249f-135">アプリケーション共有の指標</span><span class="sxs-lookup"><span data-stu-id="6249f-135">Application sharing metric</span></span>  <br/> |<span data-ttu-id="6249f-136">いいえ</span><span class="sxs-lookup"><span data-stu-id="6249f-136">No</span></span>  <br/> |<span data-ttu-id="6249f-137">あり</span><span class="sxs-lookup"><span data-stu-id="6249f-137">Yes</span></span>  <br/> |
|<span data-ttu-id="6249f-138">お客様の情報のサポートを構築します。</span><span class="sxs-lookup"><span data-stu-id="6249f-138">Customer building information support</span></span>  <br/> |<span data-ttu-id="6249f-139">あり</span><span class="sxs-lookup"><span data-stu-id="6249f-139">Yes</span></span>  <br/> |<span data-ttu-id="6249f-140">可</span><span class="sxs-lookup"><span data-stu-id="6249f-140">Yes</span></span>  <br/> |
|<span data-ttu-id="6249f-141">ドリルダウン分析サポート</span><span class="sxs-lookup"><span data-stu-id="6249f-141">Drill-down analysis support</span></span>  <br/> |<span data-ttu-id="6249f-142">いいえ</span><span class="sxs-lookup"><span data-stu-id="6249f-142">No</span></span>  <br/> |<span data-ttu-id="6249f-143">あり</span><span class="sxs-lookup"><span data-stu-id="6249f-143">Yes</span></span>  <br/> |
|<span data-ttu-id="6249f-144">メディアの信頼性の指標</span><span class="sxs-lookup"><span data-stu-id="6249f-144">Media reliability metrics</span></span>  <br/> |<span data-ttu-id="6249f-145">いいえ</span><span class="sxs-lookup"><span data-stu-id="6249f-145">No</span></span>  <br/> |<span data-ttu-id="6249f-146">あり</span><span class="sxs-lookup"><span data-stu-id="6249f-146">Yes</span></span>  <br/> |
|<span data-ttu-id="6249f-147">ボックスのレポート</span><span class="sxs-lookup"><span data-stu-id="6249f-147">Out-of-the-box reports</span></span>  <br/> |<span data-ttu-id="6249f-148">あり</span><span class="sxs-lookup"><span data-stu-id="6249f-148">Yes</span></span>  <br/> |<span data-ttu-id="6249f-149">可</span><span class="sxs-lookup"><span data-stu-id="6249f-149">Yes</span></span>  <br/> |
|<span data-ttu-id="6249f-150">プロジェクト概要のレポート</span><span class="sxs-lookup"><span data-stu-id="6249f-150">Overview reports</span></span>  <br/> |<span data-ttu-id="6249f-151">あり</span><span class="sxs-lookup"><span data-stu-id="6249f-151">Yes</span></span>  <br/> |<span data-ttu-id="6249f-152">可</span><span class="sxs-lookup"><span data-stu-id="6249f-152">Yes</span></span>  <br/> |
|<span data-ttu-id="6249f-153">ユーザーごとにレポートのセット</span><span class="sxs-lookup"><span data-stu-id="6249f-153">Per-user report set</span></span>  <br/> |<span data-ttu-id="6249f-154">いいえ</span><span class="sxs-lookup"><span data-stu-id="6249f-154">No</span></span>  <br/> |<span data-ttu-id="6249f-155">あり</span><span class="sxs-lookup"><span data-stu-id="6249f-155">Yes</span></span>  <br/> |
|<span data-ttu-id="6249f-156">レポートのカスタマイズの設定 (追加、削除、レポートの変更)</span><span class="sxs-lookup"><span data-stu-id="6249f-156">Report set customization (add, delete, modify reports)</span></span>  <br/> |<span data-ttu-id="6249f-157">いいえ</span><span class="sxs-lookup"><span data-stu-id="6249f-157">No</span></span>  <br/> |<span data-ttu-id="6249f-158">あり</span><span class="sxs-lookup"><span data-stu-id="6249f-158">Yes</span></span>  <br/> |
|<span data-ttu-id="6249f-159">ビデオ ベースの画面の測定値を共有</span><span class="sxs-lookup"><span data-stu-id="6249f-159">Video-based screen sharing metrics</span></span>  <br/> |<span data-ttu-id="6249f-160">いいえ</span><span class="sxs-lookup"><span data-stu-id="6249f-160">No</span></span>  <br/> |<span data-ttu-id="6249f-161">あり</span><span class="sxs-lookup"><span data-stu-id="6249f-161">Yes</span></span>  <br/> |
|<span data-ttu-id="6249f-162">ビデオの測定基準</span><span class="sxs-lookup"><span data-stu-id="6249f-162">Video metrics</span></span>  <br/> |<span data-ttu-id="6249f-163">いいえ</span><span class="sxs-lookup"><span data-stu-id="6249f-163">No</span></span>  <br/> |<span data-ttu-id="6249f-164">あり</span><span class="sxs-lookup"><span data-stu-id="6249f-164">Yes</span></span>  <br/> |
|<span data-ttu-id="6249f-165">利用可能なデータ量です。</span><span class="sxs-lookup"><span data-stu-id="6249f-165">Amount of data available</span></span>  <br/> |<span data-ttu-id="6249f-166">過去 6 か月</span><span class="sxs-lookup"><span data-stu-id="6249f-166">Last 6 months</span></span>  <br/> |<span data-ttu-id="6249f-167">過去 6 か月</span><span class="sxs-lookup"><span data-stu-id="6249f-167">Last 6 months</span></span>  <br/> |
|<span data-ttu-id="6249f-168">マイクロソフト チームのデータ</span><span class="sxs-lookup"><span data-stu-id="6249f-168">Microsoft Teams data</span></span>  <br/> |<span data-ttu-id="6249f-169">あり</span><span class="sxs-lookup"><span data-stu-id="6249f-169">Yes</span></span>  <br/> |<span data-ttu-id="6249f-170">可</span><span class="sxs-lookup"><span data-stu-id="6249f-170">Yes</span></span>  <br/> |
   
### <a name="out-of-the-box-reports"></a><span data-ttu-id="6249f-171">ボックスのレポート</span><span class="sxs-lookup"><span data-stu-id="6249f-171">Out-of-the-box reports</span></span>

<span data-ttu-id="6249f-172">救難の両方のエディションは、- の標準を提供する経験をすることが、新しいレポートを作成する必要のない品質基準を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="6249f-172">Both editions of CQD provide an out-of-the-box experience, giving you call quality metrics without the need to create any new reports.</span></span> <span data-ttu-id="6249f-173">表示を開始するには、バックエンドのデータが処理されると、レポートのデータの品質を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="6249f-173">Once data is processed in the back-end, you can start seeing call quality data in the reports.</span></span>
  
### <a name="overview-reports"></a><span data-ttu-id="6249f-174">プロジェクト概要のレポート</span><span class="sxs-lookup"><span data-stu-id="6249f-174">Overview reports</span></span>

<span data-ttu-id="6249f-175">救難の両方のエディションに、全体的な通話品質については、高度なエントリ ポイントを提供するが、サマリー レポートに情報を表示する方法の詳細なレポートの場合と異なる。</span><span class="sxs-lookup"><span data-stu-id="6249f-175">Both editions of the CQD provide a high-level entry point to the overall call quality information, but the way information is presented in Summary Reports is different from that of Detailed Reports.</span></span>
  
<span data-ttu-id="6249f-176">サマリー ・ レポートを簡単に参照し、全体的な通話品質のステータスと傾向を理解できるようにするシンプルなタブ付きページのレポート ビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="6249f-176">Summary Reports provide a simplified tabbed page report view that enables users to quickly browse and understand the overall call quality status and trends.</span></span>
  
<span data-ttu-id="6249f-177">4 つのタブは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6249f-177">The four tabs include:</span></span>
  
- <span data-ttu-id="6249f-178">**呼び出しの全体的な品質**のでは、すべてのストリームは、ストリームのクライアント サーバーの集約とクライアント ストリームと同様に別々 のサーバー ・ クライアントと毎月と毎日の傾向として、クライアントのストリームに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="6249f-178">**Overall Call Quality** - provides information about all streams, which is an aggregation of Server-Client streams and Client-Client streams, as well as separate Server-Client and Client-Client streams, in the form of monthly and daily trends.</span></span>
    
- <span data-ttu-id="6249f-179">**サーバ ・ クライアント**・ サーバーとクライアントのエンドポイント間でのストリームの追加の詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="6249f-179">**Server - Client** - provides additional details for the streams between Server and Client endpoints.</span></span>
    
- <span data-ttu-id="6249f-180">**クライアント - クライアント**- クライアントの 2 つのエンドポイント間でのストリームの追加の詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="6249f-180">**Client - Client** - provides additional details for the streams between two Client endpoints.</span></span>
    
- <span data-ttu-id="6249f-181">**音声品質の SLA**では、呼び出し、Skype ビジネス オンライン音声品質の SLA に含まれているに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="6249f-181">**Voice Quality SLA** - provides information about calls that are included in the Skype for Business Online Voice Quality SLA.</span></span>
    
### <a name="overall-call-quality-tab"></a><span data-ttu-id="6249f-182">全体的な品質の電話] タブ</span><span class="sxs-lookup"><span data-stu-id="6249f-182">Overall Call Quality tab</span></span>

<span data-ttu-id="6249f-183">ストリームの数と割合の低下を見て、通話品質のステータスと傾向を評価するために、このタブでデータを使用します。</span><span class="sxs-lookup"><span data-stu-id="6249f-183">Use the data on this tab to evaluate call quality status and trends by looking at the stream counts and poor percentages.</span></span> <span data-ttu-id="6249f-184">右上隅の凡例は、どの色と視覚的な要素は、これらの測定値を表すかを示しています。</span><span class="sxs-lookup"><span data-stu-id="6249f-184">The legend in the upper-right corner shows which color and visual elements represent these metrics.</span></span>
  
![救難データ キー](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
<span data-ttu-id="6249f-186">ストリームは、3 つのグループに分類されます: 良い、悪い、および未分類。</span><span class="sxs-lookup"><span data-stu-id="6249f-186">Streams are classified in three groups: Good, Poor, and Unclassified.</span></span> <span data-ttu-id="6249f-187">あるも計算 *% が不適切な*値はように分類されたストリームの合計数*が低い*と分類するストリームの比率です。</span><span class="sxs-lookup"><span data-stu-id="6249f-187">There are also calculated  *Poor %*  values that give you the ratio of streams classified as *Poor*  to the total classified stream count.</span></span> <span data-ttu-id="6249f-188">*% の低下 = 低下ストリーム/(不適切なストリーム + 良いストリーム) \* 100* 、これにより、 *% の低下*は、*未分類*の複数のストリームが存在することによって影響を受けていません。</span><span class="sxs-lookup"><span data-stu-id="6249f-188">Since *Poor % = Poor streams/ (Poor streams+ Good streams) \* 100*  , this makes the *Poor %*  unaffected by the presence with multiple *Unclassified*  streams.</span></span> <span data-ttu-id="6249f-189">用途として不適切なまたは適切なストリームをクラス分けするため、[品質のダッシュ ボードの呼び出しでストリームの分類](stream-classification-in-call-quality-dashboard.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6249f-189">For what is used for classifying a stream as poor or good, refer to [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md).</span></span>
  
<span data-ttu-id="6249f-190">左側のスケールを使用すると、ストリームの数の値を測定できます。</span><span class="sxs-lookup"><span data-stu-id="6249f-190">Use the scale on the left to measure the stream count values.</span></span>
  
![救難データ数](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
<span data-ttu-id="6249f-192">右側のスケールを使用すると、低下の % 値を測定できます。</span><span class="sxs-lookup"><span data-stu-id="6249f-192">Use the scale on the right to measure the Poor % values.</span></span>
  
![救難データ パーセント](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
<span data-ttu-id="6249f-194">バーの上にマウスを合わせると、実際の数値を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="6249f-194">You can also obtain the actual numerical values by hovering the mouse over a bar.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6249f-195">次の例では、非常に小規模なサンプル データ セットから、値は実際の展開を写実的です。</span><span class="sxs-lookup"><span data-stu-id="6249f-195">The following example is from a very small sample data set, and the values aren't realistic for an actual deployment.</span></span> 
  
![救難データ数値](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
<span data-ttu-id="6249f-197">ストリームの全体のボリュームは、重要な要因を判断する方法に関連する集計の割合は低いのです。</span><span class="sxs-lookup"><span data-stu-id="6249f-197">The overall stream volume is an important factor in determining how relevant the calculated Poor percentages are.</span></span> <span data-ttu-id="6249f-198">報告された不適切な割合の値は、ストリームの全体的な量が小さいほど、信頼性が低いです。</span><span class="sxs-lookup"><span data-stu-id="6249f-198">The smaller the volume of overall streams, the less reliable the reported Poor percentage values are.</span></span>
  
### <a name="server-client-tab-and-client-client-tabs"></a><span data-ttu-id="6249f-199">クライアント サーバー] タブと [クライアントのタブ</span><span class="sxs-lookup"><span data-stu-id="6249f-199">Server-Client tab and Client-Client tabs</span></span>

<span data-ttu-id="6249f-200">これら 2 つのタブは、そのエンドポイントのエンドポイントへのシナリオで行われたストリームの追加の詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="6249f-200">These two tabs provide additional details for the streams that took place in their endpoint-to-endpoint scenarios.</span></span> <span data-ttu-id="6249f-201">両方のタブには、メディア ストリームがフローする 4 つのシナリオを表す 4 つの折りたたみ可能なセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="6249f-201">Both tabs have four collapsible sections, representing four scenarios under which media streams would flow.</span></span>
  
- <span data-ttu-id="6249f-202">内ワイヤード (有線)</span><span class="sxs-lookup"><span data-stu-id="6249f-202">Wired Inside</span></span>
    
- <span data-ttu-id="6249f-203">外ワイヤード (有線)</span><span class="sxs-lookup"><span data-stu-id="6249f-203">Wired Outside</span></span>
    
- <span data-ttu-id="6249f-204">Wifi の内側</span><span class="sxs-lookup"><span data-stu-id="6249f-204">Wifi Inside</span></span>
    
- <span data-ttu-id="6249f-205">Wifi 外</span><span class="sxs-lookup"><span data-stu-id="6249f-205">Wifi Outside</span></span>
    
#### <a name="inside-test"></a><span data-ttu-id="6249f-206">内部テスト</span><span class="sxs-lookup"><span data-stu-id="6249f-206">Inside Test</span></span>

<span data-ttu-id="6249f-207">処理中に救難のバックエンドは、存在する場合*の内側*または*外側*建物の情報を使用してストリームを分類します。</span><span class="sxs-lookup"><span data-stu-id="6249f-207">During processing, the CQD back-end classifies a stream as  *Inside*  or *Outside*  using Building information, if it exists.</span></span> <span data-ttu-id="6249f-208">各ストリームのエンドポイントでは、サブネット アドレスに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="6249f-208">Endpoints of each stream are associated with a subnet address.</span></span> <span data-ttu-id="6249f-209">アップロードされた建物の情報で InsideCorp をマークするサブネットの一覧で、サブネットがある場合は、*内部*見なされます。</span><span class="sxs-lookup"><span data-stu-id="6249f-209">If the subnet is in the list of the subnets marked InsideCorp in the uploaded Building information, then it is considered *Inside*.</span></span> <span data-ttu-id="6249f-210">建物情報がまだアップロードされていない場合、テスト中は常にストリームとして分類*外側*。</span><span class="sxs-lookup"><span data-stu-id="6249f-210">If Building information has not yet been uploaded, then Inside Test will always classify the streams as *Outside*.</span></span> <span data-ttu-id="6249f-211">クライアント サーバー シナリオのテストの中にクライアント エンドポイントのみと見なされることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6249f-211">Please note that Inside Test for Server-Client scenario only considers the client endpoint.</span></span> <span data-ttu-id="6249f-212">サーバーであるため常に外部ユーザーの観点からこの加算されません、テストします。</span><span class="sxs-lookup"><span data-stu-id="6249f-212">Because servers are always outside from a user's perspective, this isn't accounted for in the test.</span></span>
  
#### <a name="wired-vs-wifi"></a><span data-ttu-id="6249f-213">Wifi とワイヤード (有線)</span><span class="sxs-lookup"><span data-stu-id="6249f-213">Wired vs. wifi</span></span>

<span data-ttu-id="6249f-214">名前が示す、これは、クライアント接続の種類に基づく分類の基準。</span><span class="sxs-lookup"><span data-stu-id="6249f-214">As the names indicate, this is a classification criteria based on the type of client connections.</span></span> <span data-ttu-id="6249f-215">もう一度、サーバーが常にワイヤード (有線) し、それは計算に含まれていません。</span><span class="sxs-lookup"><span data-stu-id="6249f-215">Again, server is always wired and it isn't included in the calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6249f-216">Wifi ネットワークに接続されている 2 つのエンドポイントのいずれかの場合に、ストリームを指定し、として分類されます救難の Wifi。</span><span class="sxs-lookup"><span data-stu-id="6249f-216">Given a stream, if one of the two endpoints is connected to a Wifi network, then it is classified as Wifi in CQD.</span></span> 
  
## <a name="selecting-product-data-to-see-in-reports"></a><span data-ttu-id="6249f-217">レポートに表示する製品データを選択します。</span><span class="sxs-lookup"><span data-stu-id="6249f-217">Selecting product data to see in reports</span></span>
<a name="BKMKProductFilter"></a>

<span data-ttu-id="6249f-218">製品のすべてのデータを表示するのには**製品のフィルター**のドロップダウン メニューを使用する概要および強化されたレポートの場所では、マイクロソフトのチームのデータのみに使用する場合、またはオンライン ビジネスのデータを Skype だけです。</span><span class="sxs-lookup"><span data-stu-id="6249f-218">In the Summary and Location Enhanced Reports, you can use the **Product Filter** drop-down to show all product data, only Microsoft Teams data, or only Skype for Business Online data.</span></span>
  
![スクリーン ショットは、すべてのオプション、Microsoft チーム、およびビジネスのための Skype 製品のフィルター コントロールを示しています。](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
<span data-ttu-id="6249f-220">詳細なレポートは、マイクロソフトのチームまたは Skype のオンライン ビジネスのデータをレポートの定義の一部としてデータをフィルター選択するのには **、チーム**の分析コードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6249f-220">In Detailed reports, you can use the **Is Teams** dimension to filter the data to Microsoft Teams or Skype for Business Online data as part of defining the report.</span></span>
  
## <a name="upload-building-information"></a><span data-ttu-id="6249f-221">アップロードの構築について</span><span class="sxs-lookup"><span data-stu-id="6249f-221">Upload Building information</span></span>
<a name="BKMKBuildingInformationUpload"></a>

<span data-ttu-id="6249f-222">救難の概要レポートのダッシュ ボードには、**テナントのデータのアップロード**] ページで、右上隅で [設定] メニューから**テナントのデータのアップロード**を選択することによってアクセスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6249f-222">The CQD Summary Reports dashboard includes a **Tenant Data Upload** page, accessed by selecting **Tenant Data Upload** from the settings menu in the top-right corner.</span></span> <span data-ttu-id="6249f-223">このページは地理的な情報は、IP アドレスのマッピングなど、独自の情報をアップロードするのには管理者の使用などの各ワイヤレス AP とその MAC アドレスのマッピング、します。</span><span class="sxs-lookup"><span data-stu-id="6249f-223">This page is used for admins to upload their own information, such as mapping of IP address and geographical information, mapping each wireless AP and its MAC address, etc.</span></span>
  
![救難のダッシュ ボード](media/839c9ab4-0246-46c9-8402-aafd83a0bc63.png)
  
1. <span data-ttu-id="6249f-225">**テナント データのアップロード**] ページで、アップロードするファイルの種類を選択するのにドロップ ダウン メニューを使用します。</span><span class="sxs-lookup"><span data-stu-id="6249f-225">On the **Tenant Data Upload** page, use the drop-down menu to choose a data file type for uploading.</span></span> <span data-ttu-id="6249f-226">ファイルのデータ型は、ファイルの内容を表します (たとえば、「建物」は、IP アドレスのマッピングと同様に他の地理的な情報を構築) します。</span><span class="sxs-lookup"><span data-stu-id="6249f-226">The file data type denotes the content of the file (for example, "Building" refers to mapping of IP address and building as well as other geographical information).</span></span> <span data-ttu-id="6249f-227">現在構築のデータ型はサポートのみです。</span><span class="sxs-lookup"><span data-stu-id="6249f-227">Currently we are only supporting the "Building" data type.</span></span> <span data-ttu-id="6249f-228">以降のリリースでは、いくつかの複数のデータ型が追加されます。</span><span class="sxs-lookup"><span data-stu-id="6249f-228">A few more data types will be added with subsequent releases.</span></span>
    
2. <span data-ttu-id="6249f-229">ファイルのデータ型を選択すると、データ ファイルを選択する**参照**ををクリックします。</span><span class="sxs-lookup"><span data-stu-id="6249f-229">After selecting the file data type, click **Browse** to choose a data file.</span></span>
    
   - <span data-ttu-id="6249f-230">.Tsv (タブ区切り) ファイルまたは .csv (コンマ区切り値) ファイル、データ ファイルがある必要があります。</span><span class="sxs-lookup"><span data-stu-id="6249f-230">The data file must be a .tsv (Tab-separated values) file or a .csv (Comma-separated value) file.</span></span> <span data-ttu-id="6249f-231">.Csv ファイルを使用する場合は、コンマを含む任意のフィールド引用符で囲む必要がありますもコンマを削除します。</span><span class="sxs-lookup"><span data-stu-id="6249f-231">If using a .csv file, any field that contains a comma must be surrounded by quotes or have the comma removed.</span></span> <span data-ttu-id="6249f-232">などの場合は、建物の名前は、ニューヨーク州、ニューヨーク州、.csv ファイルで、必要がありますとして入力する「ニューヨーク州、ニューヨーク州」。</span><span class="sxs-lookup"><span data-stu-id="6249f-232">For example, if your building name is NY,NY, in the .csv file it should be entered as "NY,NY".</span></span>
    
   - <span data-ttu-id="6249f-233">データ ファイルは、サイズが 50 MB を超えるする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6249f-233">The data file must be no larger than 50MB in size.</span></span>
    
   - <span data-ttu-id="6249f-234">ファイル内の各列は、データ ファイルごとに、このトピックの後半で説明、定義済みのデータ型を一致しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="6249f-234">For each data file, each column in the file must match a predefined data type, discussed later in this topic.</span></span>
    
3. <span data-ttu-id="6249f-235">データ ファイルを選択すると、**開始日**と、必要に応じて、**終了日を指定**を指定します。</span><span class="sxs-lookup"><span data-stu-id="6249f-235">After selecting a data file, specify **Start date** and, optionally, **Specify an end date**.</span></span>
    
4. <span data-ttu-id="6249f-236">**開始日**を選択すると、救難サーバーにファイルをアップロードして**アップロード**を選択します。</span><span class="sxs-lookup"><span data-stu-id="6249f-236">After selecting **Start date**, select **Upload** to upload the file to the CQD server.</span></span>
    
    <span data-ttu-id="6249f-237">ファイルをアップロードすると、前に、最初に検証されます。</span><span class="sxs-lookup"><span data-stu-id="6249f-237">Before the file is uploaded, it is first validated.</span></span> <span data-ttu-id="6249f-238">検証、Azure blob に格納されます。</span><span class="sxs-lookup"><span data-stu-id="6249f-238">Once validated, it is stored in an Azure blob.</span></span> <span data-ttu-id="6249f-239">Azure blob に格納する検証が失敗した場合またはファイルが失敗したかどうか、ファイルへの修正を要求するエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6249f-239">If validation fails or the file fails to be stored in an Azure blob, an error message is displayed requesting a correction to the file.</span></span> <span data-ttu-id="6249f-240">次の図は、データ ファイル内の列の数が正しくないときに発生するエラーを示しています。</span><span class="sxs-lookup"><span data-stu-id="6249f-240">The following image shows an error occurring when the number of columns in the data file is incorrect.</span></span>
    
     ![救難例アップロードの妥当性確認エラー](media/22716a32-3d3d-4870-983c-46089e8b212a.png)
  
5. <span data-ttu-id="6249f-242">検証中にエラーが発生しない場合、ファイルのアップロードは成功します。</span><span class="sxs-lookup"><span data-stu-id="6249f-242">If no errors occur during validation, the file upload will succeed.</span></span> <span data-ttu-id="6249f-243">そのページの下部にある現在のテナントのすべてのアップロードされたファイルの完全な一覧を表示 **、アップロード**の表にデータがアップロードされたファイルを表示できます。</span><span class="sxs-lookup"><span data-stu-id="6249f-243">You can then see the uploaded data file in the **My uploads** table, which shows the full list of all uploaded files for the current tenant at the bottom of that page.</span></span>
    
    <span data-ttu-id="6249f-244">各レコードは、データ ファイル、ファイルの種類、最終更新時刻、期間、説明、[削除] アイコンと、ダウンロード アイコンのアップロードされたテナントの 1 つを示しています。</span><span class="sxs-lookup"><span data-stu-id="6249f-244">Each record shows one uploaded tenant data file, with file type, last update time, time period, description, a remove icon, and a download icon.</span></span> <span data-ttu-id="6249f-245">ファイルを削除するには、表に、ごみ箱] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="6249f-245">To remove a file, select the trash bin icon in the table.</span></span> <span data-ttu-id="6249f-246">ファイルをダウンロードするには、テーブルの [**ダウンロード**] 列でのダウンロード アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="6249f-246">To download a file, select the download icon in the **Download** column of the table.</span></span>
    
     ![救難マイ アップロード ・ テーブル](media/4168a883-bbea-461a-80b1-42eedf2e7732.png)
  
### <a name="tenant-data-file-format-and-building-data-file-structure"></a><span data-ttu-id="6249f-248">テナント データのファイル形式とデータ ファイルの構造を構築</span><span class="sxs-lookup"><span data-stu-id="6249f-248">Tenant data file format and Building data file structure</span></span>
<span data-ttu-id="6249f-249"><a name="BKMKTenantDataFile"> </a></span><span class="sxs-lookup"><span data-stu-id="6249f-249"></span></span>

<span data-ttu-id="6249f-250">アップロードするデータ ファイルの形式では、アップロードする前に検証チェックに合格するのには以下を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="6249f-250">The format of the data file you upload must meet the following to pass the validation check before uploading.</span></span>
  
- <span data-ttu-id="6249f-251">.Tsv ファイルには、行ごとに列がタブで区切られたまたはコンマで区切られた各列を含む .csv ファイルのいずれか、ファイルがある必要があります。</span><span class="sxs-lookup"><span data-stu-id="6249f-251">The file must be either a .tsv file, which means, in each row, columns are separated by a TAB, or a .csv file with each column separated by a comma.</span></span>
    
- <span data-ttu-id="6249f-252">データ ファイルの内容には、テーブルの見出しが含まれていません。</span><span class="sxs-lookup"><span data-stu-id="6249f-252">The content of the data file doesn't include table headers.</span></span> <span data-ttu-id="6249f-253">ヘッダーではないなどの「ネットワーク」は、データ ファイルの最初の行には、実際のデータ必要があることなどです。</span><span class="sxs-lookup"><span data-stu-id="6249f-253">That means the first line of the data file should be real data, not headers like "Network," etc.</span></span>
    
- <span data-ttu-id="6249f-254">列ごとにデータ型は、必ず文字列、数値、またはブール値です。</span><span class="sxs-lookup"><span data-stu-id="6249f-254">For each column, the data type can only be String, Number, or Bool.</span></span> <span data-ttu-id="6249f-255">値が数値値をする必要があります数の場合は、Bool の場合、値は 0 または 1 のいずれかにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6249f-255">If it is Number, the value must be a numeric value; if it is Bool, the value must be either 0 or 1.</span></span>
    
- <span data-ttu-id="6249f-256">列ごとにデータ型が文字列である場合、データ空にすることができます (ですが、まだ、適切な区切り文字 (つまり、タブまたはカンマ) で区切る必要があります。</span><span class="sxs-lookup"><span data-stu-id="6249f-256">For each column, if the data type is string, the data can be empty (but still must be separated by an appropriate delimiter (i.e., a tab or comma).</span></span> <span data-ttu-id="6249f-257">これだけでフィールドに割り当て、その空の文字列値。</span><span class="sxs-lookup"><span data-stu-id="6249f-257">This just assigns that field an empty string value.</span></span>
    
- <span data-ttu-id="6249f-258">行ごとに 14 の列が存在する必要があります各列には、次のデータ型、および列は、次の表に記載されている順序である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6249f-258">There must be 14 columns for each row, each column must have the following data type, and the columns must be in the order listed in the following table:</span></span>
    
|<span data-ttu-id="6249f-259">**列名**</span><span class="sxs-lookup"><span data-stu-id="6249f-259">**Column Name**</span></span>|<span data-ttu-id="6249f-260">**データ型**</span><span class="sxs-lookup"><span data-stu-id="6249f-260">**Data type**</span></span>|<span data-ttu-id="6249f-261">**例**</span><span class="sxs-lookup"><span data-stu-id="6249f-261">**Example**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6249f-262">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="6249f-262">Network</span></span>  <br/> |<span data-ttu-id="6249f-263">String</span><span class="sxs-lookup"><span data-stu-id="6249f-263">String</span></span>  <br/> |<span data-ttu-id="6249f-264">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="6249f-264">192.168.1.0</span></span>  <br/> |
|<span data-ttu-id="6249f-265">ネットワーク名リソース</span><span class="sxs-lookup"><span data-stu-id="6249f-265">NetworkName</span></span>  <br/> |<span data-ttu-id="6249f-266">String</span><span class="sxs-lookup"><span data-stu-id="6249f-266">String</span></span>  <br/> |<span data-ttu-id="6249f-267">米国/シアトル/シアトル-海-1</span><span class="sxs-lookup"><span data-stu-id="6249f-267">USA/Seattle/SEATTLE-SEA-1</span></span>  <br/> |
|<span data-ttu-id="6249f-268">NetworkRange</span><span class="sxs-lookup"><span data-stu-id="6249f-268">NetworkRange</span></span>  <br/> |<span data-ttu-id="6249f-269">数値</span><span class="sxs-lookup"><span data-stu-id="6249f-269">Number</span></span>  <br/> |<span data-ttu-id="6249f-270">26</span><span class="sxs-lookup"><span data-stu-id="6249f-270">26</span></span>  <br/> |
|<span data-ttu-id="6249f-271">BuildingName</span><span class="sxs-lookup"><span data-stu-id="6249f-271">BuildingName</span></span>  <br/> |<span data-ttu-id="6249f-272">String</span><span class="sxs-lookup"><span data-stu-id="6249f-272">String</span></span>  <br/> |<span data-ttu-id="6249f-273">シアトル-海-1</span><span class="sxs-lookup"><span data-stu-id="6249f-273">SEATTLE-SEA-1</span></span>  <br/> |
|<span data-ttu-id="6249f-274">OwnershipType</span><span class="sxs-lookup"><span data-stu-id="6249f-274">OwnershipType</span></span>  <br/> |<span data-ttu-id="6249f-275">String</span><span class="sxs-lookup"><span data-stu-id="6249f-275">String</span></span>  <br/> |<span data-ttu-id="6249f-276">Contoso 社</span><span class="sxs-lookup"><span data-stu-id="6249f-276">Contoso</span></span>  <br/> |
|<span data-ttu-id="6249f-277">BuildingType</span><span class="sxs-lookup"><span data-stu-id="6249f-277">BuildingType</span></span>  <br/> |<span data-ttu-id="6249f-278">String</span><span class="sxs-lookup"><span data-stu-id="6249f-278">String</span></span>  <br/> |<span data-ttu-id="6249f-279">IT 終了</span><span class="sxs-lookup"><span data-stu-id="6249f-279">IT Termination</span></span>  <br/> |
|<span data-ttu-id="6249f-280">BuildingOfficeType</span><span class="sxs-lookup"><span data-stu-id="6249f-280">BuildingOfficeType</span></span>  <br/> |<span data-ttu-id="6249f-281">String</span><span class="sxs-lookup"><span data-stu-id="6249f-281">String</span></span>  <br/> |<span data-ttu-id="6249f-282">エンジニア リング</span><span class="sxs-lookup"><span data-stu-id="6249f-282">Engineering</span></span>  <br/> |
|<span data-ttu-id="6249f-283">市区町村</span><span class="sxs-lookup"><span data-stu-id="6249f-283">City</span></span>  <br/> |<span data-ttu-id="6249f-284">String</span><span class="sxs-lookup"><span data-stu-id="6249f-284">String</span></span>  <br/> |<span data-ttu-id="6249f-285">調布市調布ヶ丘</span><span class="sxs-lookup"><span data-stu-id="6249f-285">Seattle</span></span>  <br/> |
|<span data-ttu-id="6249f-286">ZipCode</span><span class="sxs-lookup"><span data-stu-id="6249f-286">ZipCode</span></span>  <br/> |<span data-ttu-id="6249f-287">String</span><span class="sxs-lookup"><span data-stu-id="6249f-287">String</span></span>  <br/> |<span data-ttu-id="6249f-288">98001</span><span class="sxs-lookup"><span data-stu-id="6249f-288">98001</span></span>  <br/> |
|<span data-ttu-id="6249f-289">国</span><span class="sxs-lookup"><span data-stu-id="6249f-289">Country</span></span>  <br/> |<span data-ttu-id="6249f-290">String</span><span class="sxs-lookup"><span data-stu-id="6249f-290">String</span></span>  <br/> |<span data-ttu-id="6249f-291">ご</span><span class="sxs-lookup"><span data-stu-id="6249f-291">US</span></span>  <br/> |
|<span data-ttu-id="6249f-292">都道府県</span><span class="sxs-lookup"><span data-stu-id="6249f-292">State</span></span>  <br/> |<span data-ttu-id="6249f-293">String</span><span class="sxs-lookup"><span data-stu-id="6249f-293">String</span></span>  <br/> |<span data-ttu-id="6249f-294">WA</span><span class="sxs-lookup"><span data-stu-id="6249f-294">WA</span></span>  <br/> |
|<span data-ttu-id="6249f-295">Region</span><span class="sxs-lookup"><span data-stu-id="6249f-295">Region</span></span>  <br/> |<span data-ttu-id="6249f-296">String</span><span class="sxs-lookup"><span data-stu-id="6249f-296">String</span></span>  <br/> |<span data-ttu-id="6249f-297">MSU</span><span class="sxs-lookup"><span data-stu-id="6249f-297">MSUS</span></span>  <br/> |
|<span data-ttu-id="6249f-298">InsideCorp</span><span class="sxs-lookup"><span data-stu-id="6249f-298">InsideCorp</span></span>  <br/> |<span data-ttu-id="6249f-299">ブール値</span><span class="sxs-lookup"><span data-stu-id="6249f-299">Bool</span></span>  <br/> |<span data-ttu-id="6249f-300">1</span><span class="sxs-lookup"><span data-stu-id="6249f-300">1</span></span>  <br/> |
|<span data-ttu-id="6249f-301">ExpressRoute</span><span class="sxs-lookup"><span data-stu-id="6249f-301">ExpressRoute</span></span>  <br/> |<span data-ttu-id="6249f-302">ブール値</span><span class="sxs-lookup"><span data-stu-id="6249f-302">Bool</span></span>  <br/> |<span data-ttu-id="6249f-303">0</span><span class="sxs-lookup"><span data-stu-id="6249f-303">0</span></span>  <br/> |
   
> [!IMPORTANT]
> <span data-ttu-id="6249f-304">スーパー (1 つのルーティング プレフィックスを持つ複数のサブネットの組み合わせ) を表すには、ネットワークの範囲を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6249f-304">The network range can be used to represent a supernet (combination of several subnets with a single routing prefix).</span></span> <span data-ttu-id="6249f-305">任意の重複する範囲のすべての新しい文書のアップロードがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="6249f-305">All new building uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="6249f-306">以前構築ファイルをアップロードした場合は、現在のファイルをダウンロードし、再すべての重複を識別し、再度アップロードする前に問題を修正するのには。</span><span class="sxs-lookup"><span data-stu-id="6249f-306">If you have previously uploaded a building file, you should download the current file and re-upload it to identify any overlaps and fix the issue before uploading again.</span></span> <span data-ttu-id="6249f-307">レポート内にある建物にサブネットの誤ったマッピング以前アップロードしたファイルの重複している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6249f-307">Any overlap in previously uploaded files may result in the wrong mappings of subnets to buildings in the reports.</span></span> <span data-ttu-id="6249f-308">特定の VPN 実装では、サブネット情報は正確に報告はありません。</span><span class="sxs-lookup"><span data-stu-id="6249f-308">Certain VPN implementations do not accurately report the subnet information.</span></span> <span data-ttu-id="6249f-309">お勧めする、サブネットの 1 つのエントリではなく、ファイルを作成する VPN のサブネットを追加するときに別のエントリとして追加されます VPN のサブネットのアドレスごとに別の 32 ビット ネットワーク。</span><span class="sxs-lookup"><span data-stu-id="6249f-309">It is recommended that when adding a VPN subnet to the building file, instead of one entry for the subnet, separate entries are added for each address in the VPN subnet as a separate 32-bit network.</span></span> <span data-ttu-id="6249f-310">各行には、同じ文書のメタデータを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="6249f-310">Each row can have the same building metadata.</span></span> <span data-ttu-id="6249f-311">などの 172.16.18.0/24 の 1 つの行ではなく 256 行は、172.16.18.0/32 と 172.16.18.255/32、包括的なアドレスごとに 1 行を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="6249f-311">For example, instead of one row for 172.16.18.0/24, you should have 256 rows, with one row for each address between 172.16.18.0/32 and 172.16.18.255/32, inclusive.</span></span> 
  
## <a name="selecting-media-type-in-detailed-reports"></a><span data-ttu-id="6249f-312">詳細なレポートにメディアの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="6249f-312">Selecting media type in detailed reports</span></span>
<a name="BKMKMediaType"></a>

<span data-ttu-id="6249f-313">詳細なレポートでは、オーディオ、ビデオ、アプリケーション共有、および画面共有するメディアの種類のビデオ ・ ベースの品質とメディアの信頼性を見るをサポートします。</span><span class="sxs-lookup"><span data-stu-id="6249f-313">The detailed reports support looking at quality and media reliability for audio, video, application sharing, and video-based screen-sharing media types.</span></span> <span data-ttu-id="6249f-314">ディメンション、メジャー、および 1 つのメディアの種類に固有のフィルターをプレフィックスとして「オーディオ」、「ビデオ」、「AppSharing」、または「VBSS」があります。</span><span class="sxs-lookup"><span data-stu-id="6249f-314">Dimensions, measures, and filters that are specific to a single media type have "Audio", "Video", "AppSharing", or "VBSS" as a prefix.</span></span>
  
![品質のダッシュ ボードの大きさを呼び出します。](media/ae132202-d6dc-43bd-b8b3-ea9c24c519e8.png)
  
<span data-ttu-id="6249f-316">ディメンションと 1 つのメディア タイプのメジャーを表示する場合は、新しいメディアの種類のディメンションとフィルターが必要な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6249f-316">If you want to view the dimensions and measures for a single media type, the new MediaType dimension and filter may be required.</span></span> <span data-ttu-id="6249f-317">たとえば、合計のセッションは、別のメディアの種類を示すレポートを表示するには、メディアの種類のディメンションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6249f-317">For example, to have a report that shows the total session counts across different media types, include the MediaType dimension.</span></span>
  
![品質のダッシュ ボードのストリームの合計数を呼び出します。](media/21d5d0dc-2321-415e-8ef2-cea06165601c.png)

## <a name="related-topics"></a><span data-ttu-id="6249f-319">関連項目</span><span class="sxs-lookup"><span data-stu-id="6249f-319">Related topics</span></span>
[<span data-ttu-id="6249f-320">Skype for Business の通話分析をセットアップする</span><span class="sxs-lookup"><span data-stu-id="6249f-320">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="6249f-321">分析機能の呼び出しを使用して不適切な通話の音質をトラブルシューティングするには</span><span class="sxs-lookup"><span data-stu-id="6249f-321">Use Call Analytics to troubleshoot poor  call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="6249f-322">通話分析および通話品質ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="6249f-322">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 