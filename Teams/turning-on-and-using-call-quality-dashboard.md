---
title: 通話品質ダッシュボードをオンにして使用する
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.ToolsCallQualityDashboard
ms.custom:
- Reporting
description: 'オンにし、ビジネス オンライン コール品質のダッシュ ボードに、Skype を使用し、通話の品質の概要のレポートを取得する方法を参照してください。 '
ms.openlocfilehash: 008fbeca5ae9b81d74e9a38f60c12a6fc1f919cc
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373809"
---
# <a name="turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a><span data-ttu-id="b54bd-103">有効にして、マイクロソフトのチームと Skype のオンライン ビジネスの品質のダッシュ ボードの呼び出しを使用して</span><span class="sxs-lookup"><span data-stu-id="b54bd-103">Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online</span></span>

<span data-ttu-id="b54bd-104">呼び出し品質ダッシュ ボードを使用して、通話の品質を監視するために Office 365 の組織を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b54bd-104">Learn how to configure your Office 365 organization to use the Call Quality Dashboard to monitor call quality.</span></span>
  
<span data-ttu-id="b54bd-105">マイクロソフト チームの呼び出し品質ダッシュ ボード (救難) とオンライン ビジネスの Skype では、ビジネス サービスのマイクロソフトのチームと Skype を使用して行われた通話の品質の洞察を得るために。</span><span class="sxs-lookup"><span data-stu-id="b54bd-105">The Call Quality Dashboard (CQD) for Microsoft Teams and Skype for Business Online allows you to gain insights into the quality of calls made using Microsoft Teams and Skype for Business services.</span></span> <span data-ttu-id="b54bd-106">このトピックでは、データの収集を開始するために完了する必要があります手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="b54bd-106">This topic describes the steps you'll need to complete to start collecting data.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b54bd-107">救難の詳細なレポートは、現在テクニカル プレビューとして使用可能ですが、すべての顧客に利用できます。</span><span class="sxs-lookup"><span data-stu-id="b54bd-107">The CQD detailed reports are currently available as Tech Preview but available to all customers.</span></span> 
  
## <a name="latest-changes-and-updates"></a><span data-ttu-id="b54bd-108">最新の変更と更新</span><span class="sxs-lookup"><span data-stu-id="b54bd-108">Latest changes and updates</span></span>

<span data-ttu-id="b54bd-109">救難に最新の変更内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b54bd-109">The most recent changes to CQD are as follows:</span></span>
  
- <span data-ttu-id="b54bd-110">ビジネスをオンラインでのデータの Skype の他のマイクロソフトのチーム データが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b54bd-110">Includes Microsoft Teams data in addition to Skype for Business Online data.</span></span>
    
- <span data-ttu-id="b54bd-111">サマリー レポートには、ビジネスをオンラインでのデータのすべてのデータ、マイクロソフトのチームのデータ、または Skype を選択するのには製品のフィルターが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b54bd-111">Summary reports include a product filter to select all data, Microsoft Teams data, or Skype for Business Online data.</span></span>

- <span data-ttu-id="b54bd-112">ビデオおよび VBSS のストリームの品質分類ロジックが更新されました。</span><span class="sxs-lookup"><span data-stu-id="b54bd-112">Video and VBSS stream quality classification logic has been updated.</span></span> <span data-ttu-id="b54bd-113">最新の分類子の定義については、[品質のダッシュ ボードの呼び出しでストリームの分類](stream-classification-in-call-quality-dashboard.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b54bd-113">Refer to [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md) for the latest classifier definitions.</span></span>

<span data-ttu-id="b54bd-114">[ディメンションとメジャーのコール品質のダッシュ ボードで使用可能な](dimensions-and-measures-available-in-call-quality-dashboard.md)一覧については、この資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b54bd-114">Refer to this article for a list of [Dimensions and measures available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b54bd-115">リンクをクリックしてダッシュ ボードに対する更新や変更についての情報を参照して、**朗報!**</span><span class="sxs-lookup"><span data-stu-id="b54bd-115">Information about updates and changes to the dashboard can be found by clicking the link in the **Good news!**</span></span> <span data-ttu-id="b54bd-116">ダッシュ ボードに表示する場合のバナーです。</span><span class="sxs-lookup"><span data-stu-id="b54bd-116">banner when it is displayed on the dashboard.</span></span>
  
## <a name="activate-microsoft-call-quality-dashboard-cqd-summary-reports"></a><span data-ttu-id="b54bd-117">Microsoft 呼び出し品質ダッシュ ボード (救難) の要約レポートをアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="b54bd-117">Activate Microsoft Call Quality Dashboard (CQD) Summary Reports</span></span>

<span data-ttu-id="b54bd-118">救難を使用する前に、Office 365 の組織を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b54bd-118">Before you can start using the CQD, you'll need to activate it for your Office 365 organization.</span></span>
 
<span data-ttu-id="b54bd-119">![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="b54bd-119">![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="b54bd-120">、管理者アカウントを使用して、Office 365 の組織にサインインし、管理センターを開くに**管理者**のタイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="b54bd-120">Sign in to your Office 365 organization using an admin account, and then select the **Admin** tile to open the Admin center.</span></span>
    
2. <span data-ttu-id="b54bd-121">**管理センター**を、下の左側のウィンドウで開くには、Skype のビジネス管理センターに**ビジネス用の Skype**を選択します。</span><span class="sxs-lookup"><span data-stu-id="b54bd-121">In the left pane, under **Admin centers**, select **Skype for Business** to open the Skype for Business admin center.</span></span>
    
3. <span data-ttu-id="b54bd-122">Skype のビジネス管理センターでは、左側のウィンドウで**ツール**を選択し、 **Skype**ビジネス オンライン コール品質のダッシュ ボードのします。</span><span class="sxs-lookup"><span data-stu-id="b54bd-122">In the Skype for Business admin center, select **Tools** in the left pane, and then select **Skype for Business Online Call Quality Dashboard**.</span></span>
    
     ![Skype のビジネス ツール](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)
  
4. <span data-ttu-id="b54bd-124">[開く] ページで、グローバル管理者アカウントでサインインし、が表示されたら、アカウントの資格情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="b54bd-124">On the page that opens, sign in with your Global Administrator account, and then provide the credentials for the account when prompted.</span></span>
    
     ![救難ログイン](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
<span data-ttu-id="b54bd-126">サインイン後、1 回だけをアクティブ化、CQD はデータの収集と処理を開始します。</span><span class="sxs-lookup"><span data-stu-id="b54bd-126">After you sign in, once activated, the CQD will begin collecting and processing data.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b54bd-127">いくつかのレポートには意味のある結果を表示するための十分なデータの処理に時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b54bd-127">It may take a couple of hours to process enough data to display meaningful results in the reports.</span></span> 
  
## <a name="features-of-the-call-quality-dashboard-for-skype-for-business-online"></a><span data-ttu-id="b54bd-128">オンライン ビジネスの Skype の通話品質のダッシュ ボードの機能</span><span class="sxs-lookup"><span data-stu-id="b54bd-128">Features of the Call Quality Dashboard for Skype for Business Online</span></span>
<span data-ttu-id="b54bd-129"><a name="BKMKFeaturesOfTheCQD"> </a></span><span class="sxs-lookup"><span data-stu-id="b54bd-129"></span></span>

<span data-ttu-id="b54bd-130">救難の概要のレポートでは、計画の詳細なレポート機能のサブセットを提供します。</span><span class="sxs-lookup"><span data-stu-id="b54bd-130">CQD Summary Reports provide a subset of the features planned for Detailed Reports.</span></span> <span data-ttu-id="b54bd-131">ここで 2 つのエディションの相違点の概要します。</span><span class="sxs-lookup"><span data-stu-id="b54bd-131">The differences between the two editions are summarized here:</span></span>
  
|<span data-ttu-id="b54bd-132">**機能**</span><span class="sxs-lookup"><span data-stu-id="b54bd-132">**Feature**</span></span>|<span data-ttu-id="b54bd-133">**サマリー ・ レポート**</span><span class="sxs-lookup"><span data-stu-id="b54bd-133">**Summary Reports**</span></span>|<span data-ttu-id="b54bd-134">**詳細なレポート**</span><span class="sxs-lookup"><span data-stu-id="b54bd-134">**Detailed Reports**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b54bd-135">アプリケーション共有の指標</span><span class="sxs-lookup"><span data-stu-id="b54bd-135">Application sharing metric</span></span>  <br/> |<span data-ttu-id="b54bd-136">なし</span><span class="sxs-lookup"><span data-stu-id="b54bd-136">No</span></span>  <br/> |<span data-ttu-id="b54bd-137">あり</span><span class="sxs-lookup"><span data-stu-id="b54bd-137">Yes</span></span>  <br/> |
|<span data-ttu-id="b54bd-138">お客様の情報のサポートを構築します。</span><span class="sxs-lookup"><span data-stu-id="b54bd-138">Customer building information support</span></span>  <br/> |<span data-ttu-id="b54bd-139">あり</span><span class="sxs-lookup"><span data-stu-id="b54bd-139">Yes</span></span>  <br/> |<span data-ttu-id="b54bd-140">あり</span><span class="sxs-lookup"><span data-stu-id="b54bd-140">Yes</span></span>  <br/> |
|<span data-ttu-id="b54bd-141">ドリルダウン分析サポート</span><span class="sxs-lookup"><span data-stu-id="b54bd-141">Drill-down analysis support</span></span>  <br/> |<span data-ttu-id="b54bd-142">なし</span><span class="sxs-lookup"><span data-stu-id="b54bd-142">No</span></span>  <br/> |<span data-ttu-id="b54bd-143">あり</span><span class="sxs-lookup"><span data-stu-id="b54bd-143">Yes</span></span>  <br/> |
|<span data-ttu-id="b54bd-144">メディアの信頼性の指標</span><span class="sxs-lookup"><span data-stu-id="b54bd-144">Media reliability metrics</span></span>  <br/> |<span data-ttu-id="b54bd-145">なし</span><span class="sxs-lookup"><span data-stu-id="b54bd-145">No</span></span>  <br/> |<span data-ttu-id="b54bd-146">あり</span><span class="sxs-lookup"><span data-stu-id="b54bd-146">Yes</span></span>  <br/> |
|<span data-ttu-id="b54bd-147">ボックスのレポート</span><span class="sxs-lookup"><span data-stu-id="b54bd-147">Out-of-the-box reports</span></span>  <br/> |<span data-ttu-id="b54bd-148">あり</span><span class="sxs-lookup"><span data-stu-id="b54bd-148">Yes</span></span>  <br/> |<span data-ttu-id="b54bd-149">あり</span><span class="sxs-lookup"><span data-stu-id="b54bd-149">Yes</span></span>  <br/> |
|<span data-ttu-id="b54bd-150">プロジェクト概要のレポート</span><span class="sxs-lookup"><span data-stu-id="b54bd-150">Overview reports</span></span>  <br/> |<span data-ttu-id="b54bd-151">あり</span><span class="sxs-lookup"><span data-stu-id="b54bd-151">Yes</span></span>  <br/> |<span data-ttu-id="b54bd-152">あり</span><span class="sxs-lookup"><span data-stu-id="b54bd-152">Yes</span></span>  <br/> |
|<span data-ttu-id="b54bd-153">ユーザーごとにレポートのセット</span><span class="sxs-lookup"><span data-stu-id="b54bd-153">Per-user report set</span></span>  <br/> |<span data-ttu-id="b54bd-154">なし</span><span class="sxs-lookup"><span data-stu-id="b54bd-154">No</span></span>  <br/> |<span data-ttu-id="b54bd-155">あり</span><span class="sxs-lookup"><span data-stu-id="b54bd-155">Yes</span></span>  <br/> |
|<span data-ttu-id="b54bd-156">レポートのカスタマイズの設定 (追加、削除、レポートの変更)</span><span class="sxs-lookup"><span data-stu-id="b54bd-156">Report set customization (add, delete, modify reports)</span></span>  <br/> |<span data-ttu-id="b54bd-157">なし</span><span class="sxs-lookup"><span data-stu-id="b54bd-157">No</span></span>  <br/> |<span data-ttu-id="b54bd-158">あり</span><span class="sxs-lookup"><span data-stu-id="b54bd-158">Yes</span></span>  <br/> |
|<span data-ttu-id="b54bd-159">ビデオ ベースの画面の測定値を共有</span><span class="sxs-lookup"><span data-stu-id="b54bd-159">Video-based screen sharing metrics</span></span>  <br/> |<span data-ttu-id="b54bd-160">なし</span><span class="sxs-lookup"><span data-stu-id="b54bd-160">No</span></span>  <br/> |<span data-ttu-id="b54bd-161">あり</span><span class="sxs-lookup"><span data-stu-id="b54bd-161">Yes</span></span>  <br/> |
|<span data-ttu-id="b54bd-162">ビデオの測定基準</span><span class="sxs-lookup"><span data-stu-id="b54bd-162">Video metrics</span></span>  <br/> |<span data-ttu-id="b54bd-163">なし</span><span class="sxs-lookup"><span data-stu-id="b54bd-163">No</span></span>  <br/> |<span data-ttu-id="b54bd-164">あり</span><span class="sxs-lookup"><span data-stu-id="b54bd-164">Yes</span></span>  <br/> |
|<span data-ttu-id="b54bd-165">利用可能なデータ量です。</span><span class="sxs-lookup"><span data-stu-id="b54bd-165">Amount of data available</span></span>  <br/> |<span data-ttu-id="b54bd-166">過去 6 か月</span><span class="sxs-lookup"><span data-stu-id="b54bd-166">Last 6 months</span></span>  <br/> |<span data-ttu-id="b54bd-167">過去 6 か月</span><span class="sxs-lookup"><span data-stu-id="b54bd-167">Last 6 months</span></span>  <br/> |
|<span data-ttu-id="b54bd-168">マイクロソフト チームのデータ</span><span class="sxs-lookup"><span data-stu-id="b54bd-168">Microsoft Teams data</span></span>  <br/> |<span data-ttu-id="b54bd-169">あり</span><span class="sxs-lookup"><span data-stu-id="b54bd-169">Yes</span></span>  <br/> |<span data-ttu-id="b54bd-170">あり</span><span class="sxs-lookup"><span data-stu-id="b54bd-170">Yes</span></span>  <br/> |
   
### <a name="out-of-the-box-reports"></a><span data-ttu-id="b54bd-171">ボックスのレポート</span><span class="sxs-lookup"><span data-stu-id="b54bd-171">Out-of-the-box reports</span></span>

<span data-ttu-id="b54bd-172">救難の両方のエディションは、- の標準を提供する経験をすることが、新しいレポートを作成する必要のない品質基準を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b54bd-172">Both editions of CQD provide an out-of-the-box experience, giving you call quality metrics without the need to create any new reports.</span></span> <span data-ttu-id="b54bd-173">表示を開始するには、バックエンドのデータが処理されると、レポートのデータの品質を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b54bd-173">Once data is processed in the back-end, you can start seeing call quality data in the reports.</span></span>
  
### <a name="overview-reports"></a><span data-ttu-id="b54bd-174">プロジェクト概要のレポート</span><span class="sxs-lookup"><span data-stu-id="b54bd-174">Overview reports</span></span>

<span data-ttu-id="b54bd-175">救難の両方のエディションに、全体的な通話品質については、高度なエントリ ポイントを提供するが、サマリー レポートに情報を表示する方法の詳細なレポートの場合と異なる。</span><span class="sxs-lookup"><span data-stu-id="b54bd-175">Both editions of the CQD provide a high-level entry point to the overall call quality information, but the way information is presented in Summary Reports is different from that of Detailed Reports.</span></span>
  
<span data-ttu-id="b54bd-176">サマリー ・ レポートを簡単に参照し、全体的な通話品質のステータスと傾向を理解できるようにするシンプルなタブ付きページのレポート ビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="b54bd-176">Summary Reports provide a simplified tabbed page report view that enables users to quickly browse and understand the overall call quality status and trends.</span></span>
  
<span data-ttu-id="b54bd-177">4 つのタブは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b54bd-177">The four tabs include:</span></span>
  
- <span data-ttu-id="b54bd-178">**呼び出しの全体的な品質**のでは、すべてのストリームは、ストリームのクライアント サーバーの集約とクライアント ストリームと同様に別々 のサーバー ・ クライアントと毎月と毎日の傾向として、クライアントのストリームに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="b54bd-178">**Overall Call Quality** - provides information about all streams, which is an aggregation of Server-Client streams and Client-Client streams, as well as separate Server-Client and Client-Client streams, in the form of monthly and daily trends.</span></span>
    
- <span data-ttu-id="b54bd-179">**サーバ ・ クライアント**・ サーバーとクライアントのエンドポイント間でのストリームの追加の詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="b54bd-179">**Server - Client** - provides additional details for the streams between Server and Client endpoints.</span></span>
    
- <span data-ttu-id="b54bd-180">**クライアント - クライアント**- クライアントの 2 つのエンドポイント間でのストリームの追加の詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="b54bd-180">**Client - Client** - provides additional details for the streams between two Client endpoints.</span></span>
    
- <span data-ttu-id="b54bd-181">**音声品質の SLA**では、呼び出し、Skype ビジネス オンライン音声品質の SLA に含まれているに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="b54bd-181">**Voice Quality SLA** - provides information about calls that are included in the Skype for Business Online Voice Quality SLA.</span></span>
    
### <a name="overall-call-quality-tab"></a><span data-ttu-id="b54bd-182">全体的な品質の電話] タブ</span><span class="sxs-lookup"><span data-stu-id="b54bd-182">Overall Call Quality tab</span></span>

<span data-ttu-id="b54bd-183">ストリームの数と割合の低下を見て、通話品質のステータスと傾向を評価するために、このタブでデータを使用します。</span><span class="sxs-lookup"><span data-stu-id="b54bd-183">Use the data on this tab to evaluate call quality status and trends by looking at the stream counts and poor percentages.</span></span> <span data-ttu-id="b54bd-184">右上隅の凡例は、どの色と視覚的な要素は、これらの測定値を表すかを示しています。</span><span class="sxs-lookup"><span data-stu-id="b54bd-184">The legend in the upper-right corner shows which color and visual elements represent these metrics.</span></span>
  
![救難データ キー](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
<span data-ttu-id="b54bd-186">ストリームは、3 つのグループに分類されます: 良い、悪い、および未分類。</span><span class="sxs-lookup"><span data-stu-id="b54bd-186">Streams are classified in three groups: Good, Poor, and Unclassified.</span></span> <span data-ttu-id="b54bd-187">あるも計算 *% が不適切な*値はように分類されたストリームの合計数*が低い*と分類するストリームの比率です。</span><span class="sxs-lookup"><span data-stu-id="b54bd-187">There are also calculated  *Poor %*  values that give you the ratio of streams classified as *Poor*  to the total classified stream count.</span></span> <span data-ttu-id="b54bd-188">*% の低下 = 低下ストリーム/(不適切なストリーム + 良いストリーム) \* 100* 、これにより、 *% の低下*は、*未分類*の複数のストリームが存在することによって影響を受けていません。</span><span class="sxs-lookup"><span data-stu-id="b54bd-188">Since *Poor % = Poor streams/ (Poor streams+ Good streams) \* 100*  , this makes the *Poor %*  unaffected by the presence with multiple *Unclassified*  streams.</span></span> <span data-ttu-id="b54bd-189">用途として不適切なまたは適切なストリームをクラス分けするため、[品質のダッシュ ボードの呼び出しでストリームの分類](stream-classification-in-call-quality-dashboard.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b54bd-189">For what is used for classifying a stream as poor or good, refer to [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md).</span></span>
  
<span data-ttu-id="b54bd-190">左側のスケールを使用すると、ストリームの数の値を測定できます。</span><span class="sxs-lookup"><span data-stu-id="b54bd-190">Use the scale on the left to measure the stream count values.</span></span>
  
![救難データ数](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
<span data-ttu-id="b54bd-192">右側のスケールを使用すると、低下の % 値を測定できます。</span><span class="sxs-lookup"><span data-stu-id="b54bd-192">Use the scale on the right to measure the Poor % values.</span></span>
  
![救難データ パーセント](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
<span data-ttu-id="b54bd-194">バーの上にマウスを合わせると、実際の数値を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="b54bd-194">You can also obtain the actual numerical values by hovering the mouse over a bar.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b54bd-195">次の例では、非常に小規模なサンプル データ セットから、値は実際の展開を写実的です。</span><span class="sxs-lookup"><span data-stu-id="b54bd-195">The following example is from a very small sample data set, and the values aren't realistic for an actual deployment.</span></span> 
  
![救難データ数値](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
<span data-ttu-id="b54bd-197">ストリームの全体のボリュームは、重要な要因を判断する方法に関連する集計の割合は低いのです。</span><span class="sxs-lookup"><span data-stu-id="b54bd-197">The overall stream volume is an important factor in determining how relevant the calculated Poor percentages are.</span></span> <span data-ttu-id="b54bd-198">報告された不適切な割合の値は、ストリームの全体的な量が小さいほど、信頼性が低いです。</span><span class="sxs-lookup"><span data-stu-id="b54bd-198">The smaller the volume of overall streams, the less reliable the reported Poor percentage values are.</span></span>
  
### <a name="server-client-tab-and-client-client-tabs"></a><span data-ttu-id="b54bd-199">クライアント サーバー] タブと [クライアントのタブ</span><span class="sxs-lookup"><span data-stu-id="b54bd-199">Server-Client tab and Client-Client tabs</span></span>

<span data-ttu-id="b54bd-200">これら 2 つのタブは、そのエンドポイントのエンドポイントへのシナリオで行われたストリームの追加の詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="b54bd-200">These two tabs provide additional details for the streams that took place in their endpoint-to-endpoint scenarios.</span></span> <span data-ttu-id="b54bd-201">両方のタブには、メディア ストリームがフローする 4 つのシナリオを表す 4 つの折りたたみ可能なセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="b54bd-201">Both tabs have four collapsible sections, representing four scenarios under which media streams would flow.</span></span>
  
- <span data-ttu-id="b54bd-202">内ワイヤード (有線)</span><span class="sxs-lookup"><span data-stu-id="b54bd-202">Wired Inside</span></span>
    
- <span data-ttu-id="b54bd-203">外ワイヤード (有線)</span><span class="sxs-lookup"><span data-stu-id="b54bd-203">Wired Outside</span></span>
    
- <span data-ttu-id="b54bd-204">Wifi の内側</span><span class="sxs-lookup"><span data-stu-id="b54bd-204">Wifi Inside</span></span>
    
- <span data-ttu-id="b54bd-205">Wifi 外</span><span class="sxs-lookup"><span data-stu-id="b54bd-205">Wifi Outside</span></span>
    
#### <a name="inside-test"></a><span data-ttu-id="b54bd-206">内部テスト</span><span class="sxs-lookup"><span data-stu-id="b54bd-206">Inside Test</span></span>

<span data-ttu-id="b54bd-207">処理中に救難のバックエンドは、存在する場合*の内側*または*外側*建物の情報を使用してストリームを分類します。</span><span class="sxs-lookup"><span data-stu-id="b54bd-207">During processing, the CQD back-end classifies a stream as  *Inside*  or *Outside*  using Building information, if it exists.</span></span> <span data-ttu-id="b54bd-208">各ストリームのエンドポイントでは、サブネット アドレスに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="b54bd-208">Endpoints of each stream are associated with a subnet address.</span></span> <span data-ttu-id="b54bd-209">アップロードされた建物の情報で InsideCorp をマークするサブネットの一覧で、サブネットがある場合は、*内部*見なされます。</span><span class="sxs-lookup"><span data-stu-id="b54bd-209">If the subnet is in the list of the subnets marked InsideCorp in the uploaded Building information, then it is considered *Inside*.</span></span> <span data-ttu-id="b54bd-210">建物情報がまだアップロードされていない場合、テスト中は常にストリームとして分類*外側*。</span><span class="sxs-lookup"><span data-stu-id="b54bd-210">If Building information has not yet been uploaded, then Inside Test will always classify the streams as *Outside*.</span></span> <span data-ttu-id="b54bd-211">クライアント サーバー シナリオのテストの中にクライアント エンドポイントのみと見なされることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b54bd-211">Please note that Inside Test for Server-Client scenario only considers the client endpoint.</span></span> <span data-ttu-id="b54bd-212">サーバーであるため常に外部ユーザーの観点からこの加算されません、テストします。</span><span class="sxs-lookup"><span data-stu-id="b54bd-212">Because servers are always outside from a user's perspective, this isn't accounted for in the test.</span></span>
  
#### <a name="wired-vs-wifi"></a><span data-ttu-id="b54bd-213">Wifi とワイヤード (有線)</span><span class="sxs-lookup"><span data-stu-id="b54bd-213">Wired vs. wifi</span></span>

<span data-ttu-id="b54bd-214">名前が示す、これは、クライアント接続の種類に基づく分類の基準。</span><span class="sxs-lookup"><span data-stu-id="b54bd-214">As the names indicate, this is a classification criteria based on the type of client connections.</span></span> <span data-ttu-id="b54bd-215">もう一度、サーバーが常にワイヤード (有線) し、それは計算に含まれていません。</span><span class="sxs-lookup"><span data-stu-id="b54bd-215">Again, server is always wired and it isn't included in the calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b54bd-216">Wifi ネットワークに接続されている 2 つのエンドポイントのいずれかの場合に、ストリームを指定し、として分類されます救難の Wifi。</span><span class="sxs-lookup"><span data-stu-id="b54bd-216">Given a stream, if one of the two endpoints is connected to a Wifi network, then it is classified as Wifi in CQD.</span></span> 
  
## <a name="selecting-product-data-to-see-in-reports"></a><span data-ttu-id="b54bd-217">レポートに表示する製品データを選択します。</span><span class="sxs-lookup"><span data-stu-id="b54bd-217">Selecting product data to see in reports</span></span>
<span data-ttu-id="b54bd-218"><a name="BKMKFeaturesOfTheCQD"> </a></span><span class="sxs-lookup"><span data-stu-id="b54bd-218"></span></span>

<span data-ttu-id="b54bd-219">製品のすべてのデータを表示するのには**製品のフィルター**のドロップダウン メニューを使用する概要および強化されたレポートの場所では、マイクロソフトのチームのデータのみに使用する場合、またはオンライン ビジネスのデータを Skype だけです。</span><span class="sxs-lookup"><span data-stu-id="b54bd-219">In the Summary and Location Enhanced Reports, you can use the **Product Filter** drop-down to show all product data, only Microsoft Teams data, or only Skype for Business Online data.</span></span>
  
![スクリーン ショットは、すべてのオプション、Microsoft チーム、およびビジネスのための Skype 製品のフィルター コントロールを示しています。](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
<span data-ttu-id="b54bd-221">詳細なレポートは、マイクロソフトのチームまたは Skype のオンライン ビジネスのデータをレポートの定義の一部としてデータをフィルター選択するのには **、チーム**の分析コードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b54bd-221">In Detailed reports, you can use the **Is Teams** dimension to filter the data to Microsoft Teams or Skype for Business Online data as part of defining the report.</span></span>
  
## <a name="upload-building-information"></a><span data-ttu-id="b54bd-222">アップロードの構築について</span><span class="sxs-lookup"><span data-stu-id="b54bd-222">Upload Building information</span></span>
<span data-ttu-id="b54bd-223"><a name="BKMKFeaturesOfTheCQD"> </a></span><span class="sxs-lookup"><span data-stu-id="b54bd-223"></span></span>

<span data-ttu-id="b54bd-224">救難の概要レポートのダッシュ ボードには、**テナントのデータのアップロード**] ページで、右上隅で [設定] メニューから**テナントのデータのアップロード**を選択することによってアクセスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b54bd-224">The CQD Summary Reports dashboard includes a **Tenant Data Upload** page, accessed by selecting **Tenant Data Upload** from the settings menu in the top-right corner.</span></span> <span data-ttu-id="b54bd-225">このページは地理的な情報は、IP アドレスのマッピングなど、独自の情報をアップロードするのには管理者の使用などの各ワイヤレス AP とその MAC アドレスのマッピング、します。</span><span class="sxs-lookup"><span data-stu-id="b54bd-225">This page is used for admins to upload their own information, such as mapping of IP address and geographical information, mapping each wireless AP and its MAC address, etc.</span></span>
  
![救難のダッシュ ボード](media/839c9ab4-0246-46c9-8402-aafd83a0bc63.png)
  
1. <span data-ttu-id="b54bd-227">**テナント データのアップロード**] ページで、アップロードするファイルの種類を選択するのにドロップ ダウン メニューを使用します。</span><span class="sxs-lookup"><span data-stu-id="b54bd-227">On the **Tenant Data Upload** page, use the drop-down menu to choose a data file type for uploading.</span></span> <span data-ttu-id="b54bd-228">ファイルのデータ型は、ファイルの内容を表します (たとえば、「建物」は、IP アドレスのマッピングと同様に他の地理的な情報を構築) します。</span><span class="sxs-lookup"><span data-stu-id="b54bd-228">The file data type denotes the content of the file (for example, "Building" refers to mapping of IP address and building as well as other geographical information).</span></span> <span data-ttu-id="b54bd-229">現在構築のデータ型はサポートのみです。</span><span class="sxs-lookup"><span data-stu-id="b54bd-229">Currently we are only supporting the "Building" data type.</span></span> <span data-ttu-id="b54bd-230">以降のリリースでは、いくつかの複数のデータ型が追加されます。</span><span class="sxs-lookup"><span data-stu-id="b54bd-230">A few more data types will be added with subsequent releases.</span></span>
    
2. <span data-ttu-id="b54bd-231">ファイルのデータ型を選択すると、データ ファイルを選択する**参照**ををクリックします。</span><span class="sxs-lookup"><span data-stu-id="b54bd-231">After selecting the file data type, click **Browse** to choose a data file.</span></span>
    
   - <span data-ttu-id="b54bd-232">.Tsv (タブ区切り) ファイルまたは .csv (コンマ区切り値) ファイル、データ ファイルがある必要があります。</span><span class="sxs-lookup"><span data-stu-id="b54bd-232">The data file must be a .tsv (Tab-separated values) file or a .csv (Comma-separated value) file.</span></span> <span data-ttu-id="b54bd-233">.Csv ファイルを使用する場合は、コンマを含む任意のフィールド引用符で囲む必要がありますもコンマを削除します。</span><span class="sxs-lookup"><span data-stu-id="b54bd-233">If using a .csv file, any field that contains a comma must be surrounded by quotes or have the comma removed.</span></span> <span data-ttu-id="b54bd-234">などの場合は、建物の名前は、ニューヨーク州、ニューヨーク州、.csv ファイルで、必要がありますとして入力する「ニューヨーク州、ニューヨーク州」。</span><span class="sxs-lookup"><span data-stu-id="b54bd-234">For example, if your building name is NY,NY, in the .csv file it should be entered as "NY,NY".</span></span>
    
   - <span data-ttu-id="b54bd-235">データ ファイルは、サイズが 50 MB を超えるする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b54bd-235">The data file must be no larger than 50MB in size.</span></span>
    
   - <span data-ttu-id="b54bd-236">ファイル内の各列は、データ ファイルごとに、このトピックの後半で説明、定義済みのデータ型を一致しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="b54bd-236">For each data file, each column in the file must match a predefined data type, discussed later in this topic.</span></span>
    
3. <span data-ttu-id="b54bd-237">データ ファイルを選択すると、**開始日**と、必要に応じて、**終了日を指定**を指定します。</span><span class="sxs-lookup"><span data-stu-id="b54bd-237">After selecting a data file, specify **Start date** and, optionally, **Specify an end date**.</span></span>
    
4. <span data-ttu-id="b54bd-238">**開始日**を選択すると、救難サーバーにファイルをアップロードして**アップロード**を選択します。</span><span class="sxs-lookup"><span data-stu-id="b54bd-238">After selecting **Start date**, select **Upload** to upload the file to the CQD server.</span></span>
    
    <span data-ttu-id="b54bd-239">ファイルをアップロードすると、前に、最初に検証されます。</span><span class="sxs-lookup"><span data-stu-id="b54bd-239">Before the file is uploaded, it is first validated.</span></span> <span data-ttu-id="b54bd-240">検証、Azure blob に格納されます。</span><span class="sxs-lookup"><span data-stu-id="b54bd-240">Once validated, it is stored in an Azure blob.</span></span> <span data-ttu-id="b54bd-241">Azure blob に格納する検証が失敗した場合またはファイルが失敗したかどうか、ファイルへの修正を要求するエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b54bd-241">If validation fails or the file fails to be stored in an Azure blob, an error message is displayed requesting a correction to the file.</span></span> <span data-ttu-id="b54bd-242">次の図は、データ ファイル内の列の数が正しくないときに発生するエラーを示しています。</span><span class="sxs-lookup"><span data-stu-id="b54bd-242">The following image shows an error occurring when the number of columns in the data file is incorrect.</span></span>
    
     ![救難例アップロードの妥当性確認エラー](media/22716a32-3d3d-4870-983c-46089e8b212a.png)
  
5. <span data-ttu-id="b54bd-244">検証中にエラーが発生しない場合、ファイルのアップロードは成功します。</span><span class="sxs-lookup"><span data-stu-id="b54bd-244">If no errors occur during validation, the file upload will succeed.</span></span> <span data-ttu-id="b54bd-245">そのページの下部にある現在のテナントのすべてのアップロードされたファイルの完全な一覧を表示 **、アップロード**の表にデータがアップロードされたファイルを表示できます。</span><span class="sxs-lookup"><span data-stu-id="b54bd-245">You can then see the uploaded data file in the **My uploads** table, which shows the full list of all uploaded files for the current tenant at the bottom of that page.</span></span>
    
    <span data-ttu-id="b54bd-246">各レコードは、データ ファイル、ファイルの種類、最終更新時刻、期間、説明、[削除] アイコンと、ダウンロード アイコンのアップロードされたテナントの 1 つを示しています。</span><span class="sxs-lookup"><span data-stu-id="b54bd-246">Each record shows one uploaded tenant data file, with file type, last update time, time period, description, a remove icon, and a download icon.</span></span> <span data-ttu-id="b54bd-247">ファイルを削除するには、表に、ごみ箱] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="b54bd-247">To remove a file, select the trash bin icon in the table.</span></span> <span data-ttu-id="b54bd-248">ファイルをダウンロードするには、テーブルの [**ダウンロード**] 列でのダウンロード アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="b54bd-248">To download a file, select the download icon in the **Download** column of the table.</span></span>
    
     ![救難マイ アップロード ・ テーブル](media/4168a883-bbea-461a-80b1-42eedf2e7732.png)
  
### <a name="tenant-data-file-format-and-building-data-file-structure"></a><span data-ttu-id="b54bd-250">テナント データのファイル形式とデータ ファイルの構造を構築</span><span class="sxs-lookup"><span data-stu-id="b54bd-250">Tenant data file format and Building data file structure</span></span>
<span data-ttu-id="b54bd-251"><a name="BKMKTenantDataFile"> </a></span><span class="sxs-lookup"><span data-stu-id="b54bd-251"></span></span>

<span data-ttu-id="b54bd-252">アップロードするデータ ファイルの形式では、アップロードする前に検証チェックに合格するのには以下を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="b54bd-252">The format of the data file you upload must meet the following to pass the validation check before uploading.</span></span>
  
- <span data-ttu-id="b54bd-253">.Tsv ファイルには、行ごとに列がタブで区切られたまたはコンマで区切られた各列を含む .csv ファイルのいずれか、ファイルがある必要があります。</span><span class="sxs-lookup"><span data-stu-id="b54bd-253">The file must be either a .tsv file, which means, in each row, columns are separated by a TAB, or a .csv file with each column separated by a comma.</span></span>
    
- <span data-ttu-id="b54bd-254">データ ファイルの内容には、テーブルの見出しが含まれていません。</span><span class="sxs-lookup"><span data-stu-id="b54bd-254">The content of the data file doesn't include table headers.</span></span> <span data-ttu-id="b54bd-255">ヘッダーではないなどの「ネットワーク」は、データ ファイルの最初の行には、実際のデータ必要があることなどです。</span><span class="sxs-lookup"><span data-stu-id="b54bd-255">That means the first line of the data file should be real data, not headers like "Network," etc.</span></span>
    
- <span data-ttu-id="b54bd-256">列ごとにデータ型は、必ず文字列、数値、またはブール値です。</span><span class="sxs-lookup"><span data-stu-id="b54bd-256">For each column, the data type can only be String, Number, or Bool.</span></span> <span data-ttu-id="b54bd-257">値が数値値をする必要があります数の場合は、Bool の場合、値は 0 または 1 のいずれかにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b54bd-257">If it is Number, the value must be a numeric value; if it is Bool, the value must be either 0 or 1.</span></span>
    
- <span data-ttu-id="b54bd-258">列ごとにデータ型が文字列である場合、データ空にすることができます (ですが、まだ、適切な区切り文字 (つまり、タブまたはカンマ) で区切る必要があります。</span><span class="sxs-lookup"><span data-stu-id="b54bd-258">For each column, if the data type is string, the data can be empty (but still must be separated by an appropriate delimiter (i.e., a tab or comma).</span></span> <span data-ttu-id="b54bd-259">これだけでフィールドに割り当て、その空の文字列値。</span><span class="sxs-lookup"><span data-stu-id="b54bd-259">This just assigns that field an empty string value.</span></span>
    
- <span data-ttu-id="b54bd-260">行ごとに 14 の列が存在する必要があります各列には、次のデータ型、および列は、次の表に記載されている順序である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b54bd-260">There must be 14 columns for each row, each column must have the following data type, and the columns must be in the order listed in the following table:</span></span>
    
|<span data-ttu-id="b54bd-261">**列名**</span><span class="sxs-lookup"><span data-stu-id="b54bd-261">**Column Name**</span></span>|<span data-ttu-id="b54bd-262">**データ型**</span><span class="sxs-lookup"><span data-stu-id="b54bd-262">**Data type**</span></span>|<span data-ttu-id="b54bd-263">**例**</span><span class="sxs-lookup"><span data-stu-id="b54bd-263">**Example**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b54bd-264">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="b54bd-264">Network</span></span>  <br/> |<span data-ttu-id="b54bd-265">文字列</span><span class="sxs-lookup"><span data-stu-id="b54bd-265">String</span></span>  <br/> |<span data-ttu-id="b54bd-266">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="b54bd-266">192.168.1.0</span></span>  <br/> |
|<span data-ttu-id="b54bd-267">ネットワーク名リソース</span><span class="sxs-lookup"><span data-stu-id="b54bd-267">NetworkName</span></span>  <br/> |<span data-ttu-id="b54bd-268">文字列</span><span class="sxs-lookup"><span data-stu-id="b54bd-268">String</span></span>  <br/> |<span data-ttu-id="b54bd-269">米国/シアトル/シアトル-海-1</span><span class="sxs-lookup"><span data-stu-id="b54bd-269">USA/Seattle/SEATTLE-SEA-1</span></span>  <br/> |
|<span data-ttu-id="b54bd-270">NetworkRange</span><span class="sxs-lookup"><span data-stu-id="b54bd-270">NetworkRange</span></span>  <br/> |<span data-ttu-id="b54bd-271">数値</span><span class="sxs-lookup"><span data-stu-id="b54bd-271">Number</span></span>  <br/> |<span data-ttu-id="b54bd-272">26</span><span class="sxs-lookup"><span data-stu-id="b54bd-272">26</span></span>  <br/> |
|<span data-ttu-id="b54bd-273">BuildingName</span><span class="sxs-lookup"><span data-stu-id="b54bd-273">BuildingName</span></span>  <br/> |<span data-ttu-id="b54bd-274">文字列</span><span class="sxs-lookup"><span data-stu-id="b54bd-274">String</span></span>  <br/> |<span data-ttu-id="b54bd-275">シアトル-海-1</span><span class="sxs-lookup"><span data-stu-id="b54bd-275">SEATTLE-SEA-1</span></span>  <br/> |
|<span data-ttu-id="b54bd-276">OwnershipType</span><span class="sxs-lookup"><span data-stu-id="b54bd-276">OwnershipType</span></span>  <br/> |<span data-ttu-id="b54bd-277">文字列</span><span class="sxs-lookup"><span data-stu-id="b54bd-277">String</span></span>  <br/> |<span data-ttu-id="b54bd-278">Contoso 社</span><span class="sxs-lookup"><span data-stu-id="b54bd-278">Contoso</span></span>  <br/> |
|<span data-ttu-id="b54bd-279">BuildingType</span><span class="sxs-lookup"><span data-stu-id="b54bd-279">BuildingType</span></span>  <br/> |<span data-ttu-id="b54bd-280">文字列</span><span class="sxs-lookup"><span data-stu-id="b54bd-280">String</span></span>  <br/> |<span data-ttu-id="b54bd-281">IT 終了</span><span class="sxs-lookup"><span data-stu-id="b54bd-281">IT Termination</span></span>  <br/> |
|<span data-ttu-id="b54bd-282">BuildingOfficeType</span><span class="sxs-lookup"><span data-stu-id="b54bd-282">BuildingOfficeType</span></span>  <br/> |<span data-ttu-id="b54bd-283">文字列</span><span class="sxs-lookup"><span data-stu-id="b54bd-283">String</span></span>  <br/> |<span data-ttu-id="b54bd-284">エンジニア リング</span><span class="sxs-lookup"><span data-stu-id="b54bd-284">Engineering</span></span>  <br/> |
|<span data-ttu-id="b54bd-285">市区町村</span><span class="sxs-lookup"><span data-stu-id="b54bd-285">City</span></span>  <br/> |<span data-ttu-id="b54bd-286">文字列</span><span class="sxs-lookup"><span data-stu-id="b54bd-286">String</span></span>  <br/> |<span data-ttu-id="b54bd-287">調布市調布ヶ丘</span><span class="sxs-lookup"><span data-stu-id="b54bd-287">Seattle</span></span>  <br/> |
|<span data-ttu-id="b54bd-288">ZipCode</span><span class="sxs-lookup"><span data-stu-id="b54bd-288">ZipCode</span></span>  <br/> |<span data-ttu-id="b54bd-289">文字列</span><span class="sxs-lookup"><span data-stu-id="b54bd-289">String</span></span>  <br/> |<span data-ttu-id="b54bd-290">98001</span><span class="sxs-lookup"><span data-stu-id="b54bd-290">98001</span></span>  <br/> |
|<span data-ttu-id="b54bd-291">国</span><span class="sxs-lookup"><span data-stu-id="b54bd-291">Country</span></span>  <br/> |<span data-ttu-id="b54bd-292">文字列</span><span class="sxs-lookup"><span data-stu-id="b54bd-292">String</span></span>  <br/> |<span data-ttu-id="b54bd-293">ご</span><span class="sxs-lookup"><span data-stu-id="b54bd-293">US</span></span>  <br/> |
|<span data-ttu-id="b54bd-294">都道府県</span><span class="sxs-lookup"><span data-stu-id="b54bd-294">State</span></span>  <br/> |<span data-ttu-id="b54bd-295">文字列</span><span class="sxs-lookup"><span data-stu-id="b54bd-295">String</span></span>  <br/> |<span data-ttu-id="b54bd-296">WA</span><span class="sxs-lookup"><span data-stu-id="b54bd-296">WA</span></span>  <br/> |
|<span data-ttu-id="b54bd-297">Region</span><span class="sxs-lookup"><span data-stu-id="b54bd-297">Region</span></span>  <br/> |<span data-ttu-id="b54bd-298">文字列</span><span class="sxs-lookup"><span data-stu-id="b54bd-298">String</span></span>  <br/> |<span data-ttu-id="b54bd-299">MSU</span><span class="sxs-lookup"><span data-stu-id="b54bd-299">MSUS</span></span>  <br/> |
|<span data-ttu-id="b54bd-300">InsideCorp</span><span class="sxs-lookup"><span data-stu-id="b54bd-300">InsideCorp</span></span>  <br/> |<span data-ttu-id="b54bd-301">ブール値</span><span class="sxs-lookup"><span data-stu-id="b54bd-301">Bool</span></span>  <br/> |<span data-ttu-id="b54bd-302">1</span><span class="sxs-lookup"><span data-stu-id="b54bd-302">1</span></span>  <br/> |
|<span data-ttu-id="b54bd-303">ExpressRoute</span><span class="sxs-lookup"><span data-stu-id="b54bd-303">ExpressRoute</span></span>  <br/> |<span data-ttu-id="b54bd-304">ブール値</span><span class="sxs-lookup"><span data-stu-id="b54bd-304">Bool</span></span>  <br/> |<span data-ttu-id="b54bd-305">0</span><span class="sxs-lookup"><span data-stu-id="b54bd-305">0</span></span>  <br/> |
   
> [!IMPORTANT]
> <span data-ttu-id="b54bd-306">スーパー (1 つのルーティング プレフィックスを持つ複数のサブネットの組み合わせ) を表すには、ネットワークの範囲を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b54bd-306">The network range can be used to represent a supernet (combination of several subnets with a single routing prefix).</span></span> <span data-ttu-id="b54bd-307">任意の重複する範囲のすべての新しい文書のアップロードがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="b54bd-307">All new building uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="b54bd-308">以前構築ファイルをアップロードした場合は、現在のファイルをダウンロードし、再すべての重複を識別し、再度アップロードする前に問題を修正するのには。</span><span class="sxs-lookup"><span data-stu-id="b54bd-308">If you have previously uploaded a building file, you should download the current file and re-upload it to identify any overlaps and fix the issue before uploading again.</span></span> <span data-ttu-id="b54bd-309">レポート内にある建物にサブネットの誤ったマッピング以前アップロードしたファイルの重複している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b54bd-309">Any overlap in previously uploaded files may result in the wrong mappings of subnets to buildings in the reports.</span></span> <span data-ttu-id="b54bd-310">特定の VPN 実装では、サブネット情報は正確に報告はありません。</span><span class="sxs-lookup"><span data-stu-id="b54bd-310">Certain VPN implementations do not accurately report the subnet information.</span></span> <span data-ttu-id="b54bd-311">お勧めする、サブネットの 1 つのエントリではなく、ファイルを作成する VPN のサブネットを追加するときに別のエントリとして追加されます VPN のサブネットのアドレスごとに別の 32 ビット ネットワーク。</span><span class="sxs-lookup"><span data-stu-id="b54bd-311">It is recommended that when adding a VPN subnet to the building file, instead of one entry for the subnet, separate entries are added for each address in the VPN subnet as a separate 32-bit network.</span></span> <span data-ttu-id="b54bd-312">各行には、同じ文書のメタデータを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="b54bd-312">Each row can have the same building metadata.</span></span> <span data-ttu-id="b54bd-313">などの 172.16.18.0/24 の 1 つの行ではなく 256 行は、172.16.18.0/32 と 172.16.18.255/32、包括的なアドレスごとに 1 行を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="b54bd-313">For example, instead of one row for 172.16.18.0/24, you should have 256 rows, with one row for each address between 172.16.18.0/32 and 172.16.18.255/32, inclusive.</span></span> 
  
## <a name="selecting-media-type-in-detailed-reports"></a><span data-ttu-id="b54bd-314">詳細なレポートにメディアの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="b54bd-314">Selecting media type in detailed reports</span></span>
<span data-ttu-id="b54bd-315"><a name="BKMKFeaturesOfTheCQD"> </a></span><span class="sxs-lookup"><span data-stu-id="b54bd-315"></span></span>

<span data-ttu-id="b54bd-316">詳細なレポートでは、オーディオ、ビデオ、アプリケーション共有、および画面共有するメディアの種類のビデオ ・ ベースの品質とメディアの信頼性を見るをサポートします。</span><span class="sxs-lookup"><span data-stu-id="b54bd-316">The detailed reports support looking at quality and media reliability for audio, video, application sharing, and video-based screen-sharing media types.</span></span> <span data-ttu-id="b54bd-317">ディメンション、メジャー、および 1 つのメディアの種類に固有のフィルターをプレフィックスとして「オーディオ」、「ビデオ」、「AppSharing」、または「VBSS」があります。</span><span class="sxs-lookup"><span data-stu-id="b54bd-317">Dimensions, measures, and filters that are specific to a single media type have "Audio", "Video", "AppSharing", or "VBSS" as a prefix.</span></span>
  
![品質のダッシュ ボードの大きさを呼び出します。](media/ae132202-d6dc-43bd-b8b3-ea9c24c519e8.png)
  
<span data-ttu-id="b54bd-319">ディメンションと 1 つのメディア タイプのメジャーを表示する場合は、新しいメディアの種類のディメンションとフィルターが必要な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b54bd-319">If you want to view the dimensions and measures for a single media type, the new MediaType dimension and filter may be required.</span></span> <span data-ttu-id="b54bd-320">たとえば、合計のセッションは、別のメディアの種類を示すレポートを表示するには、メディアの種類のディメンションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b54bd-320">For example, to have a report that shows the total session counts across different media types, include the MediaType dimension.</span></span>
  
![品質のダッシュ ボードのストリームの合計数を呼び出します。](media/21d5d0dc-2321-415e-8ef2-cea06165601c.png)

## <a name="related-topics"></a><span data-ttu-id="b54bd-322">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b54bd-322">Related topics</span></span>
[<span data-ttu-id="b54bd-323">Skype for Business の通話分析をセットアップする</span><span class="sxs-lookup"><span data-stu-id="b54bd-323">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="b54bd-324">分析機能の呼び出しを使用して不適切な通話の音質をトラブルシューティングするには</span><span class="sxs-lookup"><span data-stu-id="b54bd-324">Use Call Analytics to troubleshoot poor  call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="b54bd-325">呼び出しを分析し、通話品質のダッシュ ボード</span><span class="sxs-lookup"><span data-stu-id="b54bd-325">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 