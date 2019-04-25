---
title: 通話品質ダッシュボードをオンにして使用する
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, siunies, gageames
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
ms.openlocfilehash: bfbca275afb6da9dbe0f809906e6053f87e960e8
ms.sourcegitcommit: ee3f79ce1b6da0885e1096f9fba894bcff1814da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/25/2019
ms.locfileid: "33298669"
---
# <a name="turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a><span data-ttu-id="bce89-103">有効にして、マイクロソフトのチームと Skype のオンライン ビジネスの品質のダッシュ ボードの呼び出しを使用して</span><span class="sxs-lookup"><span data-stu-id="bce89-103">Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online</span></span>

<span data-ttu-id="bce89-104">呼び出し品質ダッシュ ボードを使用して、通話の品質を監視するために Office 365 の組織を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bce89-104">Learn how to configure your Office 365 organization to use the Call Quality Dashboard to monitor call quality.</span></span>
  
<span data-ttu-id="bce89-105">マイクロソフト チームの呼び出し品質ダッシュ ボード (救難) とオンライン ビジネスの Skype では、ビジネス サービスのマイクロソフトのチームと Skype を使用して行われた通話の品質の洞察を得るために。</span><span class="sxs-lookup"><span data-stu-id="bce89-105">The Call Quality Dashboard (CQD) for Microsoft Teams and Skype for Business Online allows you to gain insights into the quality of calls made using Microsoft Teams and Skype for Business services.</span></span> <span data-ttu-id="bce89-106">このトピックでは、データの収集を開始するために完了する必要があります手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="bce89-106">This topic describes the steps you'll need to complete to start collecting data.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bce89-107">救難の詳細なレポートは、現在テクニカル プレビューとして使用可能ですが、すべての顧客に利用できます。</span><span class="sxs-lookup"><span data-stu-id="bce89-107">The CQD detailed reports are currently available as Tech Preview but available to all customers.</span></span> 
  
## <a name="latest-changes-and-updates"></a><span data-ttu-id="bce89-108">最新の変更と更新</span><span class="sxs-lookup"><span data-stu-id="bce89-108">Latest changes and updates</span></span>

<span data-ttu-id="bce89-109">救難に最新の変更内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bce89-109">The most recent changes to CQD are as follows:</span></span>
  
- <span data-ttu-id="bce89-110">ビジネスをオンラインでのデータの Skype の他のマイクロソフトのチーム データが含まれます。</span><span class="sxs-lookup"><span data-stu-id="bce89-110">Includes Microsoft Teams data in addition to Skype for Business Online data.</span></span>
    
- <span data-ttu-id="bce89-111">サマリー レポートには、ビジネスをオンラインでのデータのすべてのデータ、マイクロソフトのチームのデータ、または Skype を選択するのには製品のフィルターが含まれます。</span><span class="sxs-lookup"><span data-stu-id="bce89-111">Summary reports include a product filter to select all data, Microsoft Teams data, or Skype for Business Online data.</span></span>

- <span data-ttu-id="bce89-112">ビデオおよび VBSS のストリームの品質分類ロジックが更新されました。</span><span class="sxs-lookup"><span data-stu-id="bce89-112">Video and VBSS stream quality classification logic has been updated.</span></span> <span data-ttu-id="bce89-113">最新の分類子の定義については、[品質のダッシュ ボードの呼び出しでストリームの分類](stream-classification-in-call-quality-dashboard.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bce89-113">Refer to [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md) for the latest classifier definitions.</span></span>

<span data-ttu-id="bce89-114">[ディメンションとメジャーのコール品質のダッシュ ボードで使用可能な](dimensions-and-measures-available-in-call-quality-dashboard.md)一覧については、この資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bce89-114">Refer to this article for a list of [Dimensions and measures available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="bce89-115">リンクをクリックしてダッシュ ボードに対する更新や変更についての情報を参照して、**朗報!**</span><span class="sxs-lookup"><span data-stu-id="bce89-115">Information about updates and changes to the dashboard can be found by clicking the link in the **Good news!**</span></span> <span data-ttu-id="bce89-116">ダッシュ ボードに表示する場合のバナーです。</span><span class="sxs-lookup"><span data-stu-id="bce89-116">banner when it is displayed on the dashboard.</span></span>
  
## <a name="activate-microsoft-call-quality-dashboard-cqd-summary-reports"></a><span data-ttu-id="bce89-117">Microsoft 呼び出し品質ダッシュ ボード (救難) の要約レポートをアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="bce89-117">Activate Microsoft Call Quality Dashboard (CQD) Summary Reports</span></span>

<span data-ttu-id="bce89-118">救難を使用する前に、Office 365 の組織を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bce89-118">Before you can start using the CQD, you'll need to activate it for your Office 365 organization.</span></span>
 
<span data-ttu-id="bce89-119">![デバイスのロゴ-30x30.png](media/sfb-logo-30x30.png) **ビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="bce89-119">![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="bce89-120">、管理者アカウントを使用して、Office 365 の組織にサインインし、管理センターを開くに**管理者**のタイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="bce89-120">Sign in to your Office 365 organization using an admin account, and then select the **Admin** tile to open the Admin center.</span></span>
    
2. <span data-ttu-id="bce89-121">**管理センター**を、下の左側のウィンドウで開くには、Skype のビジネス管理センターに**ビジネス用の Skype**を選択します。</span><span class="sxs-lookup"><span data-stu-id="bce89-121">In the left pane, under **Admin centers**, select **Skype for Business** to open the Skype for Business admin center.</span></span>
    
3. <span data-ttu-id="bce89-122">Skype のビジネス管理センターでは、左側のウィンドウで**ツール**を選択し、 **Skype**ビジネス オンライン コール品質のダッシュ ボードのします。</span><span class="sxs-lookup"><span data-stu-id="bce89-122">In the Skype for Business admin center, select **Tools** in the left pane, and then select **Skype for Business Online Call Quality Dashboard**.</span></span>
    
     ![Skype のビジネス ツール](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)
  
4. <span data-ttu-id="bce89-124">[開く] ページで、グローバル管理者アカウントでサインインし、が表示されたら、アカウントの資格情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="bce89-124">On the page that opens, sign in with your Global Administrator account, and then provide the credentials for the account when prompted.</span></span>
    
     ![救難ログイン](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
<span data-ttu-id="bce89-126">サインイン後、1 回だけをアクティブ化、CQD はデータの収集と処理を開始します。</span><span class="sxs-lookup"><span data-stu-id="bce89-126">After you sign in, once activated, the CQD will begin collecting and processing data.</span></span>

<span data-ttu-id="bce89-127">![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチーム管理センターを使用して**</span><span class="sxs-lookup"><span data-stu-id="bce89-127">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>
 
1. <span data-ttu-id="bce89-128">マイクロソフト チーム サービス管理者アカウントを使用して、Office 365 の組織にサインインし、管理センターを開くに**管理者**のタイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="bce89-128">Sign in to your Office 365 organization using Microsoft Teams service admin account, and then select the **Admin** tile to open the Admin center.</span></span>
    
2. <span data-ttu-id="bce89-129">**管理を中央揃え**、下の左側のウィンドウでは、マイクロソフトのチーム管理センターを開くには、**マイクロソフトのチーム**を選択します。</span><span class="sxs-lookup"><span data-stu-id="bce89-129">In the left pane, under **Admin centers**, select **Microsoft Teams** to open the Microsoft Teams admin center.</span></span>
    
3. <span data-ttu-id="bce89-130">マイクロソフトのチーム管理センターで、左側のペインで**品質のダッシュ ボードを呼び出す**を選択します。</span><span class="sxs-lookup"><span data-stu-id="bce89-130">In the Microsoft Teams admin center, select **Call quality dashboard** in the left pane.</span></span>
    
  
4. <span data-ttu-id="bce89-131">表示されるページ、マイクロソフト チームのサービス管理者アカウント、グローバル ・ アドミニストレータ ・ アカウントを使用してサインインし、が表示されたら、アカウントの資格情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="bce89-131">On the page that opens, sign in with your Global Administrator account or Microsoft Teams Service Admin account, and then provide the credentials for the account when prompted.</span></span>
    
     ![救難ログイン](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
<span data-ttu-id="bce89-133">サインイン後、1 回だけをアクティブ化、CQD はデータの収集と処理を開始します。</span><span class="sxs-lookup"><span data-stu-id="bce89-133">After you sign in, once activated, the CQD will begin collecting and processing data.</span></span>  
> [!NOTE]
> <span data-ttu-id="bce89-134">いくつかのレポートには意味のある結果を表示するための十分なデータの処理に時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="bce89-134">It may take a couple of hours to process enough data to display meaningful results in the reports.</span></span> 
  
## <a name="features-of-the-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a><span data-ttu-id="bce89-135">マイクロソフト チームの通話品質のダッシュ ボード、ビジネス用の Skype のオンライン機能</span><span class="sxs-lookup"><span data-stu-id="bce89-135">Features of the Call Quality Dashboard for Microsoft Teams and Skype for Business Online</span></span> 
<span data-ttu-id="bce89-136"><a name="BKMKFeaturesOfTheCQD"> </a></span><span class="sxs-lookup"><span data-stu-id="bce89-136"></span></span>

<span data-ttu-id="bce89-137">救難の概要のレポートでは、計画の詳細なレポート機能のサブセットを提供します。</span><span class="sxs-lookup"><span data-stu-id="bce89-137">CQD Summary Reports provide a subset of the features planned for Detailed Reports.</span></span> <span data-ttu-id="bce89-138">ここで 2 つのエディションの相違点の概要します。</span><span class="sxs-lookup"><span data-stu-id="bce89-138">The differences between the two editions are summarized here:</span></span>
  
|<span data-ttu-id="bce89-139">**機能**</span><span class="sxs-lookup"><span data-stu-id="bce89-139">**Feature**</span></span>|<span data-ttu-id="bce89-140">**サマリー ・ レポート**</span><span class="sxs-lookup"><span data-stu-id="bce89-140">**Summary Reports**</span></span>|<span data-ttu-id="bce89-141">**詳細なレポート**</span><span class="sxs-lookup"><span data-stu-id="bce89-141">**Detailed Reports**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bce89-142">アプリケーション共有の指標</span><span class="sxs-lookup"><span data-stu-id="bce89-142">Application sharing metric</span></span>  <br/> |<span data-ttu-id="bce89-143">いいえ</span><span class="sxs-lookup"><span data-stu-id="bce89-143">No</span></span>  <br/> |<span data-ttu-id="bce89-144">はい</span><span class="sxs-lookup"><span data-stu-id="bce89-144">Yes</span></span>  <br/> |
|<span data-ttu-id="bce89-145">お客様の情報のサポートを構築します。</span><span class="sxs-lookup"><span data-stu-id="bce89-145">Customer building information support</span></span>  <br/> |<span data-ttu-id="bce89-146">はい</span><span class="sxs-lookup"><span data-stu-id="bce89-146">Yes</span></span>  <br/> |<span data-ttu-id="bce89-147">可</span><span class="sxs-lookup"><span data-stu-id="bce89-147">Yes</span></span>  <br/> |
|<span data-ttu-id="bce89-148">お客様のエンドポイント情報のサポート</span><span class="sxs-lookup"><span data-stu-id="bce89-148">Customer endpoint information support</span></span>  <br/> |<span data-ttu-id="bce89-149">Cqd.teams.microsoft.com でのみ</span><span class="sxs-lookup"><span data-stu-id="bce89-149">Only in cqd.teams.microsoft.com</span></span>  <br/> |<span data-ttu-id="bce89-150">Cqd.teams.microsoft.com でのみ</span><span class="sxs-lookup"><span data-stu-id="bce89-150">Only in cqd.teams.microsoft.com</span></span>  <br/> |
|<span data-ttu-id="bce89-151">ドリルダウン分析サポート</span><span class="sxs-lookup"><span data-stu-id="bce89-151">Drill-down analysis support</span></span>  <br/> |<span data-ttu-id="bce89-152">いいえ</span><span class="sxs-lookup"><span data-stu-id="bce89-152">No</span></span>  <br/> |<span data-ttu-id="bce89-153">はい</span><span class="sxs-lookup"><span data-stu-id="bce89-153">Yes</span></span>  <br/> |
|<span data-ttu-id="bce89-154">メディアの信頼性の指標</span><span class="sxs-lookup"><span data-stu-id="bce89-154">Media reliability metrics</span></span>  <br/> |<span data-ttu-id="bce89-155">いいえ</span><span class="sxs-lookup"><span data-stu-id="bce89-155">No</span></span>  <br/> |<span data-ttu-id="bce89-156">はい</span><span class="sxs-lookup"><span data-stu-id="bce89-156">Yes</span></span>  <br/> |
|<span data-ttu-id="bce89-157">ボックスのレポート</span><span class="sxs-lookup"><span data-stu-id="bce89-157">Out-of-the-box reports</span></span>  <br/> |<span data-ttu-id="bce89-158">はい</span><span class="sxs-lookup"><span data-stu-id="bce89-158">Yes</span></span>  <br/> |<span data-ttu-id="bce89-159">可</span><span class="sxs-lookup"><span data-stu-id="bce89-159">Yes</span></span>  <br/> |
|<span data-ttu-id="bce89-160">プロジェクト概要のレポート</span><span class="sxs-lookup"><span data-stu-id="bce89-160">Overview reports</span></span>  <br/> |<span data-ttu-id="bce89-161">はい</span><span class="sxs-lookup"><span data-stu-id="bce89-161">Yes</span></span>  <br/> |<span data-ttu-id="bce89-162">可</span><span class="sxs-lookup"><span data-stu-id="bce89-162">Yes</span></span>  <br/> |
|<span data-ttu-id="bce89-163">ユーザーごとにレポートのセット</span><span class="sxs-lookup"><span data-stu-id="bce89-163">Per-user report set</span></span>  <br/> |<span data-ttu-id="bce89-164">いいえ</span><span class="sxs-lookup"><span data-stu-id="bce89-164">No</span></span>  <br/> |<span data-ttu-id="bce89-165">はい</span><span class="sxs-lookup"><span data-stu-id="bce89-165">Yes</span></span>  <br/> |
|<span data-ttu-id="bce89-166">レポートのカスタマイズの設定 (追加、削除、レポートの変更)</span><span class="sxs-lookup"><span data-stu-id="bce89-166">Report set customization (add, delete, modify reports)</span></span>  <br/> |<span data-ttu-id="bce89-167">いいえ</span><span class="sxs-lookup"><span data-stu-id="bce89-167">No</span></span>  <br/> |<span data-ttu-id="bce89-168">はい</span><span class="sxs-lookup"><span data-stu-id="bce89-168">Yes</span></span>  <br/> |
|<span data-ttu-id="bce89-169">ビデオ ベースの画面の測定値を共有</span><span class="sxs-lookup"><span data-stu-id="bce89-169">Video-based screen sharing metrics</span></span>  <br/> |<span data-ttu-id="bce89-170">いいえ</span><span class="sxs-lookup"><span data-stu-id="bce89-170">No</span></span>  <br/> |<span data-ttu-id="bce89-171">はい</span><span class="sxs-lookup"><span data-stu-id="bce89-171">Yes</span></span>  <br/> |
|<span data-ttu-id="bce89-172">ビデオの測定基準</span><span class="sxs-lookup"><span data-stu-id="bce89-172">Video metrics</span></span>  <br/> |<span data-ttu-id="bce89-173">いいえ</span><span class="sxs-lookup"><span data-stu-id="bce89-173">No</span></span>  <br/> |<span data-ttu-id="bce89-174">はい</span><span class="sxs-lookup"><span data-stu-id="bce89-174">Yes</span></span>  <br/> |
|<span data-ttu-id="bce89-175">利用可能なデータ量です。</span><span class="sxs-lookup"><span data-stu-id="bce89-175">Amount of data available</span></span>  <br/> |<span data-ttu-id="bce89-176">過去 6 か月</span><span class="sxs-lookup"><span data-stu-id="bce89-176">Last 6 months</span></span>  <br/> |<span data-ttu-id="bce89-177">過去 6 か月</span><span class="sxs-lookup"><span data-stu-id="bce89-177">Last 6 months</span></span>  <br/> |
|<span data-ttu-id="bce89-178">マイクロソフト チームのデータ</span><span class="sxs-lookup"><span data-stu-id="bce89-178">Microsoft Teams data</span></span>  <br/> |<span data-ttu-id="bce89-179">はい</span><span class="sxs-lookup"><span data-stu-id="bce89-179">Yes</span></span>  <br/> |<span data-ttu-id="bce89-180">可</span><span class="sxs-lookup"><span data-stu-id="bce89-180">Yes</span></span>  <br/> |
   
### <a name="out-of-the-box-reports"></a><span data-ttu-id="bce89-181">ボックスのレポート</span><span class="sxs-lookup"><span data-stu-id="bce89-181">Out-of-the-box reports</span></span>

<span data-ttu-id="bce89-182">救難の両方のエディションは、- の標準を提供する経験をすることが、新しいレポートを作成する必要のない品質基準を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="bce89-182">Both editions of CQD provide an out-of-the-box experience, giving you call quality metrics without the need to create any new reports.</span></span> <span data-ttu-id="bce89-183">表示を開始するには、バックエンドのデータが処理されると、レポートのデータの品質を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="bce89-183">Once data is processed in the back-end, you can start seeing call quality data in the reports.</span></span>
  
### <a name="overview-reports"></a><span data-ttu-id="bce89-184">プロジェクト概要のレポート</span><span class="sxs-lookup"><span data-stu-id="bce89-184">Overview reports</span></span>

<span data-ttu-id="bce89-185">救難の両方のエディションに、全体的な通話品質については、高度なエントリ ポイントを提供するが、サマリー レポートに情報を表示する方法の詳細なレポートの場合と異なる。</span><span class="sxs-lookup"><span data-stu-id="bce89-185">Both editions of the CQD provide a high-level entry point to the overall call quality information, but the way information is presented in Summary Reports is different from that of Detailed Reports.</span></span>
  
<span data-ttu-id="bce89-186">サマリー ・ レポートを簡単に参照し、全体的な通話品質のステータスと傾向を理解できるようにするシンプルなタブ付きページのレポート ビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="bce89-186">Summary Reports provide a simplified tabbed page report view that enables users to quickly browse and understand the overall call quality status and trends.</span></span>
  
<span data-ttu-id="bce89-187">4 つのタブは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bce89-187">The four tabs include:</span></span>
  
- <span data-ttu-id="bce89-188">**呼び出しの全体的な品質**のでは、すべてのストリームは、ストリームのクライアント サーバーの集約とクライアント ストリームと同様に別々 のサーバー ・ クライアントと毎月と毎日の傾向として、クライアントのストリームに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="bce89-188">**Overall Call Quality** - provides information about all streams, which is an aggregation of Server-Client streams and Client-Client streams, as well as separate Server-Client and Client-Client streams, in the form of monthly and daily trends.</span></span>
    
- <span data-ttu-id="bce89-189">**サーバ ・ クライアント**・ サーバーとクライアントのエンドポイント間でのストリームの追加の詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="bce89-189">**Server - Client** - provides additional details for the streams between Server and Client endpoints.</span></span>
    
- <span data-ttu-id="bce89-190">**クライアント - クライアント**- クライアントの 2 つのエンドポイント間でのストリームの追加の詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="bce89-190">**Client - Client** - provides additional details for the streams between two Client endpoints.</span></span>
    
- <span data-ttu-id="bce89-191">**音声品質の SLA**では、呼び出し、Skype ビジネス オンライン音声品質の SLA に含まれているに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="bce89-191">**Voice Quality SLA** - provides information about calls that are included in the Skype for Business Online Voice Quality SLA.</span></span>
    
### <a name="overall-call-quality-tab"></a><span data-ttu-id="bce89-192">全体的な品質の電話] タブ</span><span class="sxs-lookup"><span data-stu-id="bce89-192">Overall Call Quality tab</span></span>

<span data-ttu-id="bce89-193">ストリームの数と割合の低下を見て、通話品質のステータスと傾向を評価するために、このタブでデータを使用します。</span><span class="sxs-lookup"><span data-stu-id="bce89-193">Use the data on this tab to evaluate call quality status and trends by looking at the stream counts and poor percentages.</span></span> <span data-ttu-id="bce89-194">右上隅の凡例は、どの色と視覚的な要素は、これらの測定値を表すかを示しています。</span><span class="sxs-lookup"><span data-stu-id="bce89-194">The legend in the upper-right corner shows which color and visual elements represent these metrics.</span></span>
  
![救難データ キー](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
<span data-ttu-id="bce89-196">ストリームは、3 つのグループに分類されます: 良い、悪い、および未分類。</span><span class="sxs-lookup"><span data-stu-id="bce89-196">Streams are classified in three groups: Good, Poor, and Unclassified.</span></span> <span data-ttu-id="bce89-197">あるも計算 *% が不適切な*値はように分類されたストリームの合計数*が低い*と分類するストリームの比率です。</span><span class="sxs-lookup"><span data-stu-id="bce89-197">There are also calculated  *Poor %*  values that give you the ratio of streams classified as *Poor*  to the total classified stream count.</span></span> <span data-ttu-id="bce89-198">*% の低下 = 低下ストリーム/(不適切なストリーム + 良いストリーム) \* 100* 、これにより、 *% の低下*は、*未分類*の複数のストリームが存在することによって影響を受けていません。</span><span class="sxs-lookup"><span data-stu-id="bce89-198">Since *Poor % = Poor streams/ (Poor streams+ Good streams) \* 100*  , this makes the *Poor %*  unaffected by the presence with multiple *Unclassified*  streams.</span></span> <span data-ttu-id="bce89-199">用途として不適切なまたは適切なストリームをクラス分けするため、[品質のダッシュ ボードの呼び出しでストリームの分類](stream-classification-in-call-quality-dashboard.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bce89-199">For what is used for classifying a stream as poor or good, refer to [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md).</span></span>
  
<span data-ttu-id="bce89-200">左側のスケールを使用すると、ストリームの数の値を測定できます。</span><span class="sxs-lookup"><span data-stu-id="bce89-200">Use the scale on the left to measure the stream count values.</span></span>
  
![救難データ数](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
<span data-ttu-id="bce89-202">右側のスケールを使用すると、低下の % 値を測定できます。</span><span class="sxs-lookup"><span data-stu-id="bce89-202">Use the scale on the right to measure the Poor % values.</span></span>
  
![救難データ パーセント](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
<span data-ttu-id="bce89-204">バーの上にマウスを合わせると、実際の数値を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="bce89-204">You can also obtain the actual numerical values by hovering the mouse over a bar.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bce89-205">次の例では、非常に小規模なサンプル データ セットから、値は実際の展開を写実的です。</span><span class="sxs-lookup"><span data-stu-id="bce89-205">The following example is from a very small sample data set, and the values aren't realistic for an actual deployment.</span></span> 
  
![救難データ数値](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
<span data-ttu-id="bce89-207">ストリームの全体のボリュームは、重要な要因を判断する方法に関連する集計の割合は低いのです。</span><span class="sxs-lookup"><span data-stu-id="bce89-207">The overall stream volume is an important factor in determining how relevant the calculated Poor percentages are.</span></span> <span data-ttu-id="bce89-208">報告された不適切な割合の値は、ストリームの全体的な量が小さいほど、信頼性が低いです。</span><span class="sxs-lookup"><span data-stu-id="bce89-208">The smaller the volume of overall streams, the less reliable the reported Poor percentage values are.</span></span>
  
### <a name="server-client-tab-and-client-client-tabs"></a><span data-ttu-id="bce89-209">クライアント サーバー] タブと [クライアントのタブ</span><span class="sxs-lookup"><span data-stu-id="bce89-209">Server-Client tab and Client-Client tabs</span></span>

<span data-ttu-id="bce89-210">これら 2 つのタブは、そのエンドポイントのエンドポイントへのシナリオで行われたストリームの追加の詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="bce89-210">These two tabs provide additional details for the streams that took place in their endpoint-to-endpoint scenarios.</span></span> <span data-ttu-id="bce89-211">両方のタブには、メディア ストリームがフローする 4 つのシナリオを表す 4 つの折りたたみ可能なセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="bce89-211">Both tabs have four collapsible sections, representing four scenarios under which media streams would flow.</span></span>
  
- <span data-ttu-id="bce89-212">内ワイヤード (有線)</span><span class="sxs-lookup"><span data-stu-id="bce89-212">Wired Inside</span></span>
    
- <span data-ttu-id="bce89-213">外ワイヤード (有線)</span><span class="sxs-lookup"><span data-stu-id="bce89-213">Wired Outside</span></span>
    
- <span data-ttu-id="bce89-214">Wifi の内側</span><span class="sxs-lookup"><span data-stu-id="bce89-214">Wifi Inside</span></span>
    
- <span data-ttu-id="bce89-215">Wifi 外</span><span class="sxs-lookup"><span data-stu-id="bce89-215">Wifi Outside</span></span>
    
#### <a name="inside-test"></a><span data-ttu-id="bce89-216">内部テスト</span><span class="sxs-lookup"><span data-stu-id="bce89-216">Inside Test</span></span>

<span data-ttu-id="bce89-217">処理中に救難のバックエンドは、存在する場合*の内側*または*外側*建物の情報を使用してストリームを分類します。</span><span class="sxs-lookup"><span data-stu-id="bce89-217">During processing, the CQD back-end classifies a stream as  *Inside*  or *Outside*  using Building information, if it exists.</span></span> <span data-ttu-id="bce89-218">各ストリームのエンドポイントでは、サブネット アドレスに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="bce89-218">Endpoints of each stream are associated with a subnet address.</span></span> <span data-ttu-id="bce89-219">アップロードされた建物の情報で InsideCorp をマークするサブネットの一覧で、サブネットがある場合は、*内部*見なされます。</span><span class="sxs-lookup"><span data-stu-id="bce89-219">If the subnet is in the list of the subnets marked InsideCorp in the uploaded Building information, then it is considered *Inside*.</span></span> <span data-ttu-id="bce89-220">建物情報がまだアップロードされていない場合、テスト中は常にストリームとして分類*外側*。</span><span class="sxs-lookup"><span data-stu-id="bce89-220">If Building information has not yet been uploaded, then Inside Test will always classify the streams as *Outside*.</span></span> <span data-ttu-id="bce89-221">クライアント サーバー シナリオのテストの中にクライアント エンドポイントのみと見なされることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bce89-221">Please note that Inside Test for Server-Client scenario only considers the client endpoint.</span></span> <span data-ttu-id="bce89-222">サーバーであるため常に外部ユーザーの観点からこの加算されません、テストします。</span><span class="sxs-lookup"><span data-stu-id="bce89-222">Because servers are always outside from a user's perspective, this isn't accounted for in the test.</span></span>
  
#### <a name="wired-vs-wifi"></a><span data-ttu-id="bce89-223">Wifi とワイヤード (有線)</span><span class="sxs-lookup"><span data-stu-id="bce89-223">Wired vs. wifi</span></span>

<span data-ttu-id="bce89-224">名前が示す、これは、クライアント接続の種類に基づく分類の基準。</span><span class="sxs-lookup"><span data-stu-id="bce89-224">As the names indicate, this is a classification criteria based on the type of client connections.</span></span> <span data-ttu-id="bce89-225">もう一度、サーバーが常にワイヤード (有線) し、それは計算に含まれていません。</span><span class="sxs-lookup"><span data-stu-id="bce89-225">Again, server is always wired and it isn't included in the calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bce89-226">Wifi ネットワークに接続されている 2 つのエンドポイントのいずれかの場合に、ストリームを指定し、として分類されます救難の Wifi。</span><span class="sxs-lookup"><span data-stu-id="bce89-226">Given a stream, if one of the two endpoints is connected to a Wifi network, then it is classified as Wifi in CQD.</span></span> 
  
## <a name="selecting-product-data-to-see-in-reports"></a><span data-ttu-id="bce89-227">レポートに表示する製品データを選択します。</span><span class="sxs-lookup"><span data-stu-id="bce89-227">Selecting product data to see in reports</span></span>
<a name="BKMKProductFilter"></a>

<span data-ttu-id="bce89-228">製品のすべてのデータを表示するのには**製品のフィルター**のドロップダウン メニューを使用する概要および強化されたレポートの場所では、マイクロソフトのチームのデータのみに使用する場合、またはオンライン ビジネスのデータを Skype だけです。</span><span class="sxs-lookup"><span data-stu-id="bce89-228">In the Summary and Location Enhanced Reports, you can use the **Product Filter** drop-down to show all product data, only Microsoft Teams data, or only Skype for Business Online data.</span></span>
  
![スクリーン ショットは、すべてのオプション、Microsoft チーム、およびビジネスのための Skype 製品のフィルター コントロールを示しています。](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
<span data-ttu-id="bce89-230">詳細なレポートは、マイクロソフトのチームまたは Skype のオンライン ビジネスのデータをレポートの定義の一部としてデータをフィルター選択するのには **、チーム**の分析コードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="bce89-230">In Detailed reports, you can use the **Is Teams** dimension to filter the data to Microsoft Teams or Skype for Business Online data as part of defining the report.</span></span>
  
## <a name="upload-tenant-data-information"></a><span data-ttu-id="bce89-231">テナント データの情報をアップロードします。</span><span class="sxs-lookup"><span data-stu-id="bce89-231">Upload Tenant Data information</span></span>
<a name="BKMKTenantDataInformationUpload"></a>

<span data-ttu-id="bce89-232">救難の概要レポートのダッシュ ボードには、**テナントのデータのアップロード**] ページで、右上隅で [設定] メニューから**テナントのデータのアップロード**を選択することによってアクセスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bce89-232">The CQD Summary Reports dashboard includes a **Tenant Data Upload** page, accessed by selecting **Tenant Data Upload** from the settings menu in the top-right corner.</span></span> <span data-ttu-id="bce89-233">管理者は、このページを使用してマッピングは、IP アドレスおよび地理的な情報、各ワイヤレス AP の MAC アドレスのマッピング、エンドポイントの作成/モデル/タイプなどのエンドポイントのマッピングなど、独自の情報をアップロードします。</span><span class="sxs-lookup"><span data-stu-id="bce89-233">This page is used for admins to upload their own information, such as mapping of IP address and geographical information, mapping each wireless AP and its MAC address, mapping of Endpoint to Endpoint Make/Model/Type, etc.</span></span>
  
![救難のダッシュ ボード](media/839c9ab4-0246-46c9-8402-aafd83a0bc63.png)
  
1. <span data-ttu-id="bce89-235">**テナント データのアップロード**] ページで、アップロードするファイルの種類を選択するのにドロップ ダウン メニューを使用します。</span><span class="sxs-lookup"><span data-stu-id="bce89-235">On the **Tenant Data Upload** page, use the drop-down menu to choose a data file type for uploading.</span></span> <span data-ttu-id="bce89-236">ファイルのデータ型は、ファイルの内容を表します (たとえば、IP アドレスのマッピングを参照して「ビルド」と「エンドポイント」は... エンドポイント名エンドポイント Make/モデル/型へのマッピングを参照、およびその他の地理的な情報を作成します。情報)。</span><span class="sxs-lookup"><span data-stu-id="bce89-236">The file data type denotes the content of the file (for example, "Building" refers to mapping of IP address and building as well as other geographical information, “Endpoint” refers to mapping of Endpoint Name to Endpoint Make/Model/Type…information).</span></span> <span data-ttu-id="bce89-237">現在アップロード「建物」や「エンドポイント」のデータ型 cqd.teams.microsoft.com のサポート (プレビュー段階で、正式に利用可能なまだ)、cqd.lync.com のみをサポートしていますがデータ型の構築をアップロードします。</span><span class="sxs-lookup"><span data-stu-id="bce89-237">Currently we support upload “Building” and “Endpoint” data types for cqd.teams.microsoft.com(in preview stage and not officially available yet), cqd.lync.com only supports upload "Building" data type.</span></span> <span data-ttu-id="bce89-238">以降のリリースでは、いくつかの複数のデータ型が追加されます。</span><span class="sxs-lookup"><span data-stu-id="bce89-238">A few more data types will be added with subsequent releases.</span></span>
    
2. <span data-ttu-id="bce89-239">ファイルのデータ型を選択すると、データ ファイルを選択する**参照**ををクリックします。</span><span class="sxs-lookup"><span data-stu-id="bce89-239">After selecting the file data type, click **Browse** to choose a data file.</span></span>
    
   - <span data-ttu-id="bce89-240">.Tsv (タブ区切り) ファイルまたは .csv (コンマ区切り値) ファイル、データ ファイルがある必要があります。</span><span class="sxs-lookup"><span data-stu-id="bce89-240">The data file must be a .tsv (Tab-separated values) file or a .csv (Comma-separated value) file.</span></span> <span data-ttu-id="bce89-241">.Csv ファイルを使用する場合は、コンマを含む任意のフィールド引用符で囲む必要がありますもコンマを削除します。</span><span class="sxs-lookup"><span data-stu-id="bce89-241">If using a .csv file, any field that contains a comma must be surrounded by quotes or have the comma removed.</span></span> <span data-ttu-id="bce89-242">などの場合は、建物の名前は、ニューヨーク州、ニューヨーク州、.csv ファイルで、必要がありますとして入力する「ニューヨーク州、ニューヨーク州」。</span><span class="sxs-lookup"><span data-stu-id="bce89-242">For example, if your building name is NY,NY, in the .csv file it should be entered as "NY,NY".</span></span>
    
   - <span data-ttu-id="bce89-243">データ ファイルは、サイズが 50 MB を超えるする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bce89-243">The data file must be no larger than 50MB in size.</span></span>

   - <span data-ttu-id="bce89-244">Cqd.teams.microsoft.com にアップロードされたファイルには、クエリのパフォーマンスを向上させる 1,000,000 の行数の制限を拡大しました。</span><span class="sxs-lookup"><span data-stu-id="bce89-244">File uploaded to cqd.teams.microsoft.com has expanded row limit of 1,000,000 to speed up query performance.</span></span> <span data-ttu-id="bce89-245">Cqd.lync.com も同様に、制限は加わる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bce89-245">We may impose that limit on cqd.lync.com as well.</span></span>
    
   - <span data-ttu-id="bce89-246">ファイル内の各列は、データ ファイルごとに、このトピックの後半で説明、定義済みのデータ型を一致しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="bce89-246">For each data file, each column in the file must match a predefined data type, discussed later in this topic.</span></span>
    
3. <span data-ttu-id="bce89-247">データ ファイルを選択すると、**開始日**と、必要に応じて、**終了日を指定**を指定します。</span><span class="sxs-lookup"><span data-stu-id="bce89-247">After selecting a data file, specify **Start date** and, optionally, **Specify an end date**.</span></span>
    
4. <span data-ttu-id="bce89-248">**開始日**を選択すると、救難サーバーにファイルをアップロードして**アップロード**を選択します。</span><span class="sxs-lookup"><span data-stu-id="bce89-248">After selecting **Start date**, select **Upload** to upload the file to the CQD server.</span></span>
    
    <span data-ttu-id="bce89-249">ファイルをアップロードすると、前に、最初に検証されます。</span><span class="sxs-lookup"><span data-stu-id="bce89-249">Before the file is uploaded, it is first validated.</span></span> <span data-ttu-id="bce89-250">検証、Azure blob に格納されます。</span><span class="sxs-lookup"><span data-stu-id="bce89-250">Once validated, it is stored in an Azure blob.</span></span> <span data-ttu-id="bce89-251">Azure blob に格納する検証が失敗した場合またはファイルが失敗したかどうか、ファイルへの修正を要求するエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bce89-251">If validation fails or the file fails to be stored in an Azure blob, an error message is displayed requesting a correction to the file.</span></span> <span data-ttu-id="bce89-252">次の図は、データ ファイル内の列の数が正しくないときに発生するエラーを示しています。</span><span class="sxs-lookup"><span data-stu-id="bce89-252">The following image shows an error occurring when the number of columns in the data file is incorrect.</span></span>
    
     ![救難例アップロードの妥当性確認エラー](media/22716a32-3d3d-4870-983c-46089e8b212a.png)
  
5. <span data-ttu-id="bce89-254">検証中にエラーが発生しない場合、ファイルのアップロードは成功します。</span><span class="sxs-lookup"><span data-stu-id="bce89-254">If no errors occur during validation, the file upload will succeed.</span></span> <span data-ttu-id="bce89-255">そのページの下部にある現在のテナントのすべてのアップロードされたファイルの完全な一覧を表示 **、アップロード**の表にデータがアップロードされたファイルを表示できます。</span><span class="sxs-lookup"><span data-stu-id="bce89-255">You can then see the uploaded data file in the **My uploads** table, which shows the full list of all uploaded files for the current tenant at the bottom of that page.</span></span>
    
    <span data-ttu-id="bce89-256">各レコードは、データ ファイル、ファイルの種類、最終更新時刻、期間、説明、[削除] アイコンと、ダウンロード アイコンのアップロードされたテナントの 1 つを示しています。</span><span class="sxs-lookup"><span data-stu-id="bce89-256">Each record shows one uploaded tenant data file, with file type, last update time, time period, description, a remove icon, and a download icon.</span></span> <span data-ttu-id="bce89-257">ファイルを削除するには、表に、ごみ箱] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="bce89-257">To remove a file, select the trash bin icon in the table.</span></span> <span data-ttu-id="bce89-258">ファイルをダウンロードするには、テーブルの [**ダウンロード**] 列でのダウンロード アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="bce89-258">To download a file, select the download icon in the **Download** column of the table.</span></span>
    
     ![救難マイ アップロード ・ テーブル](media/4168a883-bbea-461a-80b1-42eedf2e7732.png)
  
### <a name="tenant-data-file-format-and-structure"></a><span data-ttu-id="bce89-260">テナント データのファイル形式と構造</span><span class="sxs-lookup"><span data-stu-id="bce89-260">Tenant data file format and structure</span></span>
<span data-ttu-id="bce89-261"><a name="BKMKTenantDataFile"> </a></span><span class="sxs-lookup"><span data-stu-id="bce89-261"></span></span>

### <a name="building-data-file"></a><span data-ttu-id="bce89-262">データ ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="bce89-262">Building data file</span></span>
<span data-ttu-id="bce89-263">CQD が建物を使用して最初のデータ ファイルから派生してサブネット列し、拡大を続けるネットワーク + NetworkRange] 列で、サブネットの結合先の列の建物、都市、国または地域を表示する呼び出しのレコードの Subnet/Second サブネットの最初の列にしています.</span><span class="sxs-lookup"><span data-stu-id="bce89-263">CQD uses Building data file by first derive Subnet column from expanding Network+NetworkRange column, then joining Subnet column to the call record’s First Subnet/Second Subnet column to show Building/City/Country/Region…</span></span> <span data-ttu-id="bce89-264">情報です。</span><span class="sxs-lookup"><span data-stu-id="bce89-264">information.</span></span> <span data-ttu-id="bce89-265">アップロードするデータ ファイルの形式では、アップロードする前に検証チェックに合格するのには以下を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="bce89-265">The format of the data file you upload must meet the following to pass the validation check before uploading.</span></span>
  
- <span data-ttu-id="bce89-266">.Tsv ファイルには、行ごとに列がタブで区切られたまたはコンマで区切られた各列を含む .csv ファイルのいずれか、ファイルがある必要があります。</span><span class="sxs-lookup"><span data-stu-id="bce89-266">The file must be either a .tsv file, which means, in each row, columns are separated by a TAB, or a .csv file with each column separated by a comma.</span></span>
    
- <span data-ttu-id="bce89-267">データ ファイルの内容には、テーブルの見出しが含まれていません。</span><span class="sxs-lookup"><span data-stu-id="bce89-267">The content of the data file doesn't include table headers.</span></span> <span data-ttu-id="bce89-268">ヘッダーではないなどの「ネットワーク」は、データ ファイルの最初の行には、実際のデータ必要があることなどです。</span><span class="sxs-lookup"><span data-stu-id="bce89-268">That means the first line of the data file should be real data, not headers like "Network," etc.</span></span>
    
- <span data-ttu-id="bce89-269">列ごとにデータ型は、必ず文字列、数値、またはブール値です。</span><span class="sxs-lookup"><span data-stu-id="bce89-269">For each column, the data type can only be String, Number, or Bool.</span></span> <span data-ttu-id="bce89-270">値が数値値をする必要があります数の場合は、Bool の場合、値は 0 または 1 のいずれかにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bce89-270">If it is Number, the value must be a numeric value; if it is Bool, the value must be either 0 or 1.</span></span>
    
- <span data-ttu-id="bce89-271">列ごとにデータ型が文字列である場合、データ空にすることができます (ですが、まだ、適切な区切り文字 (つまり、タブまたはカンマ) で区切る必要があります。</span><span class="sxs-lookup"><span data-stu-id="bce89-271">For each column, if the data type is string, the data can be empty (but still must be separated by an appropriate delimiter (i.e., a tab or comma).</span></span> <span data-ttu-id="bce89-272">これだけでフィールドに割り当て、その空の文字列値。</span><span class="sxs-lookup"><span data-stu-id="bce89-272">This just assigns that field an empty string value.</span></span>
    
- <span data-ttu-id="bce89-273">行ごとに 14 の列が存在する必要があります各列には、次のデータ型、および列は、次の表に記載されている順序である必要があります。</span><span class="sxs-lookup"><span data-stu-id="bce89-273">There must be 14 columns for each row, each column must have the following data type, and the columns must be in the order listed in the following table:</span></span>
    
|<span data-ttu-id="bce89-274">**列名**</span><span class="sxs-lookup"><span data-stu-id="bce89-274">**Column Name**</span></span>|<span data-ttu-id="bce89-275">**データ型**</span><span class="sxs-lookup"><span data-stu-id="bce89-275">**Data type**</span></span>|<span data-ttu-id="bce89-276">**例**</span><span class="sxs-lookup"><span data-stu-id="bce89-276">**Example**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bce89-277">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="bce89-277">Network</span></span>  <br/> |<span data-ttu-id="bce89-278">String</span><span class="sxs-lookup"><span data-stu-id="bce89-278">String</span></span>  <br/> |<span data-ttu-id="bce89-279">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="bce89-279">192.168.1.0</span></span>  <br/> |
|<span data-ttu-id="bce89-280">ネットワーク名リソース</span><span class="sxs-lookup"><span data-stu-id="bce89-280">NetworkName</span></span>  <br/> |<span data-ttu-id="bce89-281">String</span><span class="sxs-lookup"><span data-stu-id="bce89-281">String</span></span>  <br/> |<span data-ttu-id="bce89-282">米国/シアトル/シアトル-海-1</span><span class="sxs-lookup"><span data-stu-id="bce89-282">USA/Seattle/SEATTLE-SEA-1</span></span>  <br/> |
|<span data-ttu-id="bce89-283">NetworkRange</span><span class="sxs-lookup"><span data-stu-id="bce89-283">NetworkRange</span></span>  <br/> |<span data-ttu-id="bce89-284">数値</span><span class="sxs-lookup"><span data-stu-id="bce89-284">Number</span></span>  <br/> |<span data-ttu-id="bce89-285">26</span><span class="sxs-lookup"><span data-stu-id="bce89-285">26</span></span>  <br/> |
|<span data-ttu-id="bce89-286">BuildingName</span><span class="sxs-lookup"><span data-stu-id="bce89-286">BuildingName</span></span>  <br/> |<span data-ttu-id="bce89-287">String</span><span class="sxs-lookup"><span data-stu-id="bce89-287">String</span></span>  <br/> |<span data-ttu-id="bce89-288">シアトル-海-1</span><span class="sxs-lookup"><span data-stu-id="bce89-288">SEATTLE-SEA-1</span></span>  <br/> |
|<span data-ttu-id="bce89-289">OwnershipType</span><span class="sxs-lookup"><span data-stu-id="bce89-289">OwnershipType</span></span>  <br/> |<span data-ttu-id="bce89-290">String</span><span class="sxs-lookup"><span data-stu-id="bce89-290">String</span></span>  <br/> |<span data-ttu-id="bce89-291">Contoso 社</span><span class="sxs-lookup"><span data-stu-id="bce89-291">Contoso</span></span>  <br/> |
|<span data-ttu-id="bce89-292">BuildingType</span><span class="sxs-lookup"><span data-stu-id="bce89-292">BuildingType</span></span>  <br/> |<span data-ttu-id="bce89-293">String</span><span class="sxs-lookup"><span data-stu-id="bce89-293">String</span></span>  <br/> |<span data-ttu-id="bce89-294">IT 終了</span><span class="sxs-lookup"><span data-stu-id="bce89-294">IT Termination</span></span>  <br/> |
|<span data-ttu-id="bce89-295">BuildingOfficeType</span><span class="sxs-lookup"><span data-stu-id="bce89-295">BuildingOfficeType</span></span>  <br/> |<span data-ttu-id="bce89-296">String</span><span class="sxs-lookup"><span data-stu-id="bce89-296">String</span></span>  <br/> |<span data-ttu-id="bce89-297">エンジニア リング</span><span class="sxs-lookup"><span data-stu-id="bce89-297">Engineering</span></span>  <br/> |
|<span data-ttu-id="bce89-298">市区町村</span><span class="sxs-lookup"><span data-stu-id="bce89-298">City</span></span>  <br/> |<span data-ttu-id="bce89-299">String</span><span class="sxs-lookup"><span data-stu-id="bce89-299">String</span></span>  <br/> |<span data-ttu-id="bce89-300">調布市調布ヶ丘</span><span class="sxs-lookup"><span data-stu-id="bce89-300">Seattle</span></span>  <br/> |
|<span data-ttu-id="bce89-301">ZipCode</span><span class="sxs-lookup"><span data-stu-id="bce89-301">ZipCode</span></span>  <br/> |<span data-ttu-id="bce89-302">String</span><span class="sxs-lookup"><span data-stu-id="bce89-302">String</span></span>  <br/> |<span data-ttu-id="bce89-303">98001</span><span class="sxs-lookup"><span data-stu-id="bce89-303">98001</span></span>  <br/> |
|<span data-ttu-id="bce89-304">国</span><span class="sxs-lookup"><span data-stu-id="bce89-304">Country</span></span>  <br/> |<span data-ttu-id="bce89-305">String</span><span class="sxs-lookup"><span data-stu-id="bce89-305">String</span></span>  <br/> |<span data-ttu-id="bce89-306">ご</span><span class="sxs-lookup"><span data-stu-id="bce89-306">US</span></span>  <br/> |
|<span data-ttu-id="bce89-307">都道府県</span><span class="sxs-lookup"><span data-stu-id="bce89-307">State</span></span>  <br/> |<span data-ttu-id="bce89-308">String</span><span class="sxs-lookup"><span data-stu-id="bce89-308">String</span></span>  <br/> |<span data-ttu-id="bce89-309">WA</span><span class="sxs-lookup"><span data-stu-id="bce89-309">WA</span></span>  <br/> |
|<span data-ttu-id="bce89-310">Region</span><span class="sxs-lookup"><span data-stu-id="bce89-310">Region</span></span>  <br/> |<span data-ttu-id="bce89-311">String</span><span class="sxs-lookup"><span data-stu-id="bce89-311">String</span></span>  <br/> |<span data-ttu-id="bce89-312">MSU</span><span class="sxs-lookup"><span data-stu-id="bce89-312">MSUS</span></span>  <br/> |
|<span data-ttu-id="bce89-313">InsideCorp</span><span class="sxs-lookup"><span data-stu-id="bce89-313">InsideCorp</span></span>  <br/> |<span data-ttu-id="bce89-314">ブール</span><span class="sxs-lookup"><span data-stu-id="bce89-314">Bool</span></span>  <br/> |<span data-ttu-id="bce89-315">1</span><span class="sxs-lookup"><span data-stu-id="bce89-315">1</span></span>  <br/> |
|<span data-ttu-id="bce89-316">ExpressRoute</span><span class="sxs-lookup"><span data-stu-id="bce89-316">ExpressRoute</span></span>  <br/> |<span data-ttu-id="bce89-317">ブール</span><span class="sxs-lookup"><span data-stu-id="bce89-317">Bool</span></span>  <br/> |<span data-ttu-id="bce89-318">0</span><span class="sxs-lookup"><span data-stu-id="bce89-318">0</span></span>  <br/> |
   
> [!IMPORTANT]
> <span data-ttu-id="bce89-319">スーパー (1 つのルーティング プレフィックスを持つ複数のサブネットの組み合わせ) を表すには、ネットワークの範囲を使用できます。</span><span class="sxs-lookup"><span data-stu-id="bce89-319">The network range can be used to represent a supernet (combination of several subnets with a single routing prefix).</span></span> <span data-ttu-id="bce89-320">任意の重複する範囲のすべての新しい文書のアップロードがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="bce89-320">All new building uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="bce89-321">以前構築ファイルをアップロードした場合は、現在のファイルをダウンロードし、再すべての重複を識別し、再度アップロードする前に問題を修正するのには。</span><span class="sxs-lookup"><span data-stu-id="bce89-321">If you have previously uploaded a building file, you should download the current file and re-upload it to identify any overlaps and fix the issue before uploading again.</span></span> <span data-ttu-id="bce89-322">レポート内にある建物にサブネットの誤ったマッピング以前アップロードしたファイルの重複している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bce89-322">Any overlap in previously uploaded files may result in the wrong mappings of subnets to buildings in the reports.</span></span> <span data-ttu-id="bce89-323">特定の VPN 実装では、サブネット情報は正確に報告はありません。</span><span class="sxs-lookup"><span data-stu-id="bce89-323">Certain VPN implementations do not accurately report the subnet information.</span></span> <span data-ttu-id="bce89-324">お勧めする、サブネットの 1 つのエントリではなく、ファイルを作成する VPN のサブネットを追加するときに別のエントリとして追加されます VPN のサブネットのアドレスごとに別の 32 ビット ネットワーク。</span><span class="sxs-lookup"><span data-stu-id="bce89-324">It is recommended that when adding a VPN subnet to the building file, instead of one entry for the subnet, separate entries are added for each address in the VPN subnet as a separate 32-bit network.</span></span> <span data-ttu-id="bce89-325">各行には、同じ文書のメタデータを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="bce89-325">Each row can have the same building metadata.</span></span> <span data-ttu-id="bce89-326">などの 172.16.18.0/24 の 1 つの行ではなく 256 行は、172.16.18.0/32 と 172.16.18.255/32、包括的なアドレスごとに 1 行を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="bce89-326">For example, instead of one row for 172.16.18.0/24, you should have 256 rows, with one row for each address between 172.16.18.0/32 and 172.16.18.255/32, inclusive.</span></span> 

### <a name="endpoint-data-file"></a><span data-ttu-id="bce89-327">エンドポイント データ ファイル</span><span class="sxs-lookup"><span data-stu-id="bce89-327">Endpoint data file</span></span>
<span data-ttu-id="bce89-328">救難では、エンドポイントの作成/モデル/種類の情報を表示するのに呼び出しのレコードの最初クライアント エンドポイントの Name/Second クライアント エンドポイント名] 列に、EndpointName 列を結合することでエンドポイントのデータ ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="bce89-328">CQD uses Endpoint data file by joining its EndpointName column to the call record’s First Client Endpoint Name/Second Client Endpoint Name column to show Endpoint Make/Model/Type information.</span></span> <span data-ttu-id="bce89-329">アップロードするデータ ファイルの形式では、アップロードする前に検証チェックに合格するのには以下を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="bce89-329">The format of the data file you upload must meet the following to pass the validation check before uploading.</span></span>

- <span data-ttu-id="bce89-330">.Tsv ファイルには、行ごとに列がタブで区切られたまたはコンマで区切られた各列を含む .csv ファイルのいずれか、ファイルがある必要があります。</span><span class="sxs-lookup"><span data-stu-id="bce89-330">The file must be either a .tsv file, which means, in each row, columns are separated by a TAB, or a .csv file with each column separated by a comma.</span></span>

- <span data-ttu-id="bce89-331">データ ファイルの内容には、テーブルの見出しが含まれていません。</span><span class="sxs-lookup"><span data-stu-id="bce89-331">The content of the data file doesn't include table headers.</span></span> <span data-ttu-id="bce89-332">つまり、データ ファイルの最初の行は"EndpointName、"のようなヘッダーではない実際のデータである必要がありますなど。</span><span class="sxs-lookup"><span data-stu-id="bce89-332">That means the first line of the data file should be real data, not headers like "EndpointName," etc.</span></span>

- <span data-ttu-id="bce89-333">列ごとにデータ型が文字列をできるだけとする必要があります、64 を超える文字数が最大許容長。</span><span class="sxs-lookup"><span data-stu-id="bce89-333">For each column, the data type can only be String and it should have no more than 64 chars, which is maximum allowed length.</span></span>

- <span data-ttu-id="bce89-334">列ごとにデータは空でもかまいません (ですが、まだ、適切な区切り文字 (つまり、タブまたはカンマ) で区切る必要があります。</span><span class="sxs-lookup"><span data-stu-id="bce89-334">For each column, the data can be empty (but still must be separated by an appropriate delimiter (i.e., a tab or comma).</span></span> <span data-ttu-id="bce89-335">これだけでフィールドに割り当て、その空の文字列値。</span><span class="sxs-lookup"><span data-stu-id="bce89-335">This just assigns that field an empty string value.</span></span>

- <span data-ttu-id="bce89-336">行ごとに 7 の列が存在する必要があり、列は、次の表に記載されている順序である必要があります。</span><span class="sxs-lookup"><span data-stu-id="bce89-336">There must be 7 columns for each row and the columns must be in the order listed in the following table.</span></span>

- <span data-ttu-id="bce89-337">EndpointName 必要があります一意であるそれ以外の場合と、不正に参加することにより、重複する行が発生したためアップロードが失敗します。</span><span class="sxs-lookup"><span data-stu-id="bce89-337">EndpointName must be unique otherwise upload will fail due to duplicate row as it will cause incorrect joining.</span></span>

-  <span data-ttu-id="bce89-338">EndpointLabel1、EndpointLabel2、EndpointLable3 は、ユーザーのカスタマイズ可能なラベル、空の文字列になることができます、値のユーザーの方を次のように「IT 部門には、2018 ラップトップ コンピューターが指定されている、」または"資産タグ 5678".など。</span><span class="sxs-lookup"><span data-stu-id="bce89-338">EndpointLabel1, EndpointLabel2, EndpointLable3 are user customizable labels, they can be empty strings or value users prefer such as “IT Department designated 2018 Laptop”, “Asset Tag 5678” …etc.</span></span>

|<span data-ttu-id="bce89-339">**列名**</span><span class="sxs-lookup"><span data-stu-id="bce89-339">**Column Name**</span></span>|<span data-ttu-id="bce89-340">**データ型**</span><span class="sxs-lookup"><span data-stu-id="bce89-340">**Data type**</span></span>|<span data-ttu-id="bce89-341">**例**</span><span class="sxs-lookup"><span data-stu-id="bce89-341">**Example**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bce89-342">EndpointName</span><span class="sxs-lookup"><span data-stu-id="bce89-342">EndpointName</span></span>  <br/> |<span data-ttu-id="bce89-343">String</span><span class="sxs-lookup"><span data-stu-id="bce89-343">String</span></span>  <br/> |<span data-ttu-id="bce89-344">1409W3534</span><span class="sxs-lookup"><span data-stu-id="bce89-344">1409W3534</span></span>  <br/> |
|<span data-ttu-id="bce89-345">EndpointMake</span><span class="sxs-lookup"><span data-stu-id="bce89-345">EndpointMake</span></span>  <br/> |<span data-ttu-id="bce89-346">String</span><span class="sxs-lookup"><span data-stu-id="bce89-346">String</span></span>  <br/> |<span data-ttu-id="bce89-347">Fabrikam Inc</span><span class="sxs-lookup"><span data-stu-id="bce89-347">Fabrikam Inc</span></span>  <br/> |
|<span data-ttu-id="bce89-348">EndpointModel</span><span class="sxs-lookup"><span data-stu-id="bce89-348">EndpointModel</span></span>  <br/> |<span data-ttu-id="bce89-349">String</span><span class="sxs-lookup"><span data-stu-id="bce89-349">String</span></span>  <br/> |<span data-ttu-id="bce89-350">Fabrikam 社のモデル 123</span><span class="sxs-lookup"><span data-stu-id="bce89-350">Fabrikam Model 123</span></span>  <br/> |
|<span data-ttu-id="bce89-351">EndpointType</span><span class="sxs-lookup"><span data-stu-id="bce89-351">EndpointType</span></span>   <br/> |<span data-ttu-id="bce89-352">String</span><span class="sxs-lookup"><span data-stu-id="bce89-352">String</span></span>  <br/> |<span data-ttu-id="bce89-353">ラップトップ</span><span class="sxs-lookup"><span data-stu-id="bce89-353">Laptop</span></span>  <br/> |
|<span data-ttu-id="bce89-354">EndpointLabel1</span><span class="sxs-lookup"><span data-stu-id="bce89-354">EndpointLabel1</span></span>  <br/> |<span data-ttu-id="bce89-355">String</span><span class="sxs-lookup"><span data-stu-id="bce89-355">String</span></span>  <br/> |<span data-ttu-id="bce89-356">指定 IT 2018 ラップトップ</span><span class="sxs-lookup"><span data-stu-id="bce89-356">IT designated 2018 Laptop</span></span>  <br/> |
|<span data-ttu-id="bce89-357">EndpointLabel2</span><span class="sxs-lookup"><span data-stu-id="bce89-357">EndpointLabel2</span></span>  <br/> |<span data-ttu-id="bce89-358">String</span><span class="sxs-lookup"><span data-stu-id="bce89-358">String</span></span>  <br/> |<span data-ttu-id="bce89-359">資産タグ 5678</span><span class="sxs-lookup"><span data-stu-id="bce89-359">Asset Tag 5678</span></span>  <br/> |
|<span data-ttu-id="bce89-360">EndpointLabel3</span><span class="sxs-lookup"><span data-stu-id="bce89-360">EndpointLabel3</span></span>  <br/> |<span data-ttu-id="bce89-361">String</span><span class="sxs-lookup"><span data-stu-id="bce89-361">String</span></span>  <br/> |<span data-ttu-id="bce89-362">購買 2018</span><span class="sxs-lookup"><span data-stu-id="bce89-362">Purchase 2018</span></span>   <br/> |


## <a name="selecting-media-type-in-detailed-reports"></a><span data-ttu-id="bce89-363">詳細なレポートにメディアの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="bce89-363">Selecting media type in detailed reports</span></span>
<a name="BKMKMediaType"></a>

<span data-ttu-id="bce89-364">詳細なレポートでは、オーディオ、ビデオ、アプリケーション共有、および画面共有するメディアの種類のビデオ ・ ベースの品質とメディアの信頼性を見るをサポートします。</span><span class="sxs-lookup"><span data-stu-id="bce89-364">The detailed reports support looking at quality and media reliability for audio, video, application sharing, and video-based screen-sharing media types.</span></span> <span data-ttu-id="bce89-365">ディメンション、メジャー、および 1 つのメディアの種類に固有のフィルターをプレフィックスとして「オーディオ」、「ビデオ」、「AppSharing」、または「VBSS」があります。</span><span class="sxs-lookup"><span data-stu-id="bce89-365">Dimensions, measures, and filters that are specific to a single media type have "Audio", "Video", "AppSharing", or "VBSS" as a prefix.</span></span>
  
![品質のダッシュ ボードの大きさを呼び出します。](media/ae132202-d6dc-43bd-b8b3-ea9c24c519e8.png)
  
<span data-ttu-id="bce89-367">ディメンションと 1 つのメディア タイプのメジャーを表示する場合は、新しいメディアの種類のディメンションとフィルターが必要な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bce89-367">If you want to view the dimensions and measures for a single media type, the new MediaType dimension and filter may be required.</span></span> <span data-ttu-id="bce89-368">たとえば、合計のセッションは、別のメディアの種類を示すレポートを表示するには、メディアの種類のディメンションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="bce89-368">For example, to have a report that shows the total session counts across different media types, include the MediaType dimension.</span></span>
  
![品質のダッシュ ボードのストリームの合計数を呼び出します。](media/21d5d0dc-2321-415e-8ef2-cea06165601c.png)

## <a name="related-topics"></a><span data-ttu-id="bce89-370">関連トピック</span><span class="sxs-lookup"><span data-stu-id="bce89-370">Related topics</span></span>
[<span data-ttu-id="bce89-371">Skype for Business の通話分析をセットアップする</span><span class="sxs-lookup"><span data-stu-id="bce89-371">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="bce89-372">分析機能の呼び出しを使用して不適切な通話の音質をトラブルシューティングするには</span><span class="sxs-lookup"><span data-stu-id="bce89-372">Use Call Analytics to troubleshoot poor  call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="bce89-373">通話分析および通話品質ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="bce89-373">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
