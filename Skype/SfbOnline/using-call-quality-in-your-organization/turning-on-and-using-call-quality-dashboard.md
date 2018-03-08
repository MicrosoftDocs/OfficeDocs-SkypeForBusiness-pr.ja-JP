---
title: "有効にして、通話品質のダッシュ ボードを使用します。"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.ToolsCallQualityDashboard
ms.custom:
- Reporting
description: "使用してを有効にして、Skype for Business Online 通話品質のダッシュ ボード通話の品質の概要のレポートを入手する方法を参照してください。 "
ms.openlocfilehash: d2cbcf0a7acdfebd3ba3fb1a2cc109d32f4213a9
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a><span data-ttu-id="e3265-103">有効にして、Microsoft チームと Skype for Business Online 通話品質のダッシュ ボードを使用します。</span><span class="sxs-lookup"><span data-stu-id="e3265-103">Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online</span></span>

<span data-ttu-id="e3265-104">通話品質を監視する通話品質のダッシュ ボードを使用する Office 365 の組織を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e3265-104">Learn how to configure your Office 365 organization to use the Call Quality Dashboard to monitor call quality.</span></span>
  
<span data-ttu-id="e3265-p101">Microsoft チームの通話品質のダッシュ ボード (CQD) と Skype for Business Online を使用すると、Business services 用 Microsoft チームと Skype を使用して通話の品質をより深く洞察を取得できます。ここでは、手順を完了すると、データの収集を開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3265-p101">The Call Quality Dashboard (CQD) for Microsoft Teams and Skype for Business Online allows you to gain insights into the quality of calls made using Microsoft Teams and Skype for Business services. This topic describes the steps you'll need to complete to start collecting data.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e3265-107">詳細な CQD レポートは現在 Tech Preview として利用可能なすべてのユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="e3265-107">The CQD detailed reports are currently available as Tech Preview but available to all customers.</span></span> 
  
## <a name="latest-changes-and-updates"></a><span data-ttu-id="e3265-108">最新の変更と更新プログラム</span><span class="sxs-lookup"><span data-stu-id="e3265-108">Latest changes and updates</span></span>

<span data-ttu-id="e3265-109">CQD に最新の変更は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e3265-109">The most recent changes to CQD are as follows:</span></span>
  
- <span data-ttu-id="e3265-110">に加えて、Skype for Business Online のデータの Microsoft チーム データが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e3265-110">Includes Microsoft Teams data in addition to Skype for Business Online data.</span></span>
    
- <span data-ttu-id="e3265-111">サマリー レポートには、製品フィルターすべてのデータ、マイクロソフトのチームのデータ、または Skype for Business Online のデータにはが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e3265-111">Summary reports include a product filter to select all data, Microsoft Teams data, or Skype for Business Online data.</span></span>
    
<span data-ttu-id="e3265-112">[ディメンション](dimensions-and-measures-available-in-call-quality-dashboard.md)とメジャー Microsoft チームと Skype for Business Online の品質ダッシュ ボードの電話で利用可能な一覧については、この記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3265-112">Refer to this article for a list of [Dimensions and measures available in Call Quality Dashboard for Microsoft Teams and Skype for Business Online](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e3265-p102">更新プログラムとダッシュ ボードへの変更について参照してください] をクリックして**すばらしい!**ダッシュ ボードにします。[[通話品質のダッシュ ボード](https://aka.ms/CQDOnline)に移動できます。</span><span class="sxs-lookup"><span data-stu-id="e3265-p102">Information about updates and changes to the dashboard can be found by clicking **Good news!** in the dashboard. You can go to [Call Quality dashboard](https://aka.ms/CQDOnline).</span></span> 
  
## <a name="activate-microsoft-call-quality-dashboard-cqd-summary-reports"></a><span data-ttu-id="e3265-116">Microsoft 通話品質のダッシュ ボード (CQD) の概要レポートのライセンス認証を行う</span><span class="sxs-lookup"><span data-stu-id="e3265-116">Activate Microsoft Call Quality Dashboard (CQD) Summary Reports</span></span>

<span data-ttu-id="e3265-117">CQD の使用を開始する前に、Office 365 の組織のアクティブ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3265-117">Before you can start using the CQD, you'll need to activate it for your Office 365 organization.</span></span>
  
1. <span data-ttu-id="e3265-118">管理者アカウントを使用して、Office 365 の組織にサインインし、[**管理**] タイル、管理センターを開く] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e3265-118">Sign in to your Office 365 organization using an admin account, and then select the **Admin** tile to open the Admin center.</span></span>
    
2. <span data-ttu-id="e3265-119">**管理センター**] の下の左側のウィンドウでは、Skype for Business 管理センターを開くには、 **Skype for Business**を選択します。</span><span class="sxs-lookup"><span data-stu-id="e3265-119">In the left pane, under **Admin centers**, select **Skype for Business** to open the Skype for Business admin center.</span></span>
    
3. <span data-ttu-id="e3265-120">Skype for Business 管理センターでは、左側のウィンドウで**ツール**を選択し、[ **Skype for Business Online 通話品質のダッシュ ボード**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e3265-120">In the Skype for Business admin center, select **Tools** in the left pane, and then select **Skype for Business Online Call Quality Dashboard**.</span></span>
    
     ![Skype for Business ツール](../images/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)
  
4. <span data-ttu-id="e3265-122">表示されるページをグローバル管理者アカウントでログインしが表示されたら、アカウントの資格情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="e3265-122">On the page that opens, log in with your Global Administrator account, and then provide the credentials for the account when prompted.</span></span>
    
     ![CQD ログイン](../images/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
<span data-ttu-id="e3265-124">1 回アクティブ化されている、ログインした後、CQD によってデータの収集と処理が開始されます。</span><span class="sxs-lookup"><span data-stu-id="e3265-124">After you login, once activated, the CQD will begin collecting and processing data.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e3265-125">2 つのレポートに意味のある結果を表示するには、十分なデータを処理するに時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e3265-125">It may take a couple of hours to process enough data to display meaningful results in the reports.</span></span> 
  
## <a name="features-of-the-call-quality-dashboard-for-skype-for-business-online"></a><span data-ttu-id="e3265-126">オンラインの Skype for Business 通話品質のダッシュ ボードの機能</span><span class="sxs-lookup"><span data-stu-id="e3265-126">Features of the Call Quality Dashboard for Skype for Business Online</span></span>
<span data-ttu-id="e3265-127"><a name="BKMKFeaturesOfTheCQD"> </a></span><span class="sxs-lookup"><span data-stu-id="e3265-127"></span></span>

<span data-ttu-id="e3265-p103">CQD 概要のレポートでは、予定の詳細なレポート機能のサブセットを提供します。ここでは、2 つのエディションの相違点。</span><span class="sxs-lookup"><span data-stu-id="e3265-p103">CQD Summary Reports provide a subset of the features planned for Detailed Reports. The differences between the two editions are summarized here:</span></span>
  
|<span data-ttu-id="e3265-130">**機能**</span><span class="sxs-lookup"><span data-stu-id="e3265-130">**Feature**</span></span>|<span data-ttu-id="e3265-131">**サマリー レポート**</span><span class="sxs-lookup"><span data-stu-id="e3265-131">**Summary Reports**</span></span>|<span data-ttu-id="e3265-132">**詳細レポート**</span><span class="sxs-lookup"><span data-stu-id="e3265-132">**Detailed Reports**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e3265-133">アプリケーション共有メートル法</span><span class="sxs-lookup"><span data-stu-id="e3265-133">Application sharing metric</span></span>  <br/> |<span data-ttu-id="e3265-134">×</span><span class="sxs-lookup"><span data-stu-id="e3265-134">No</span></span>  <br/> |<span data-ttu-id="e3265-135">○</span><span class="sxs-lookup"><span data-stu-id="e3265-135">Yes</span></span>  <br/> |
|<span data-ttu-id="e3265-136">顧客の情報のサポート</span><span class="sxs-lookup"><span data-stu-id="e3265-136">Customer building information support</span></span>  <br/> |<span data-ttu-id="e3265-137">○</span><span class="sxs-lookup"><span data-stu-id="e3265-137">Yes</span></span>  <br/> |<span data-ttu-id="e3265-138">○</span><span class="sxs-lookup"><span data-stu-id="e3265-138">Yes</span></span>  <br/> |
|<span data-ttu-id="e3265-139">ドリル ダウン分析のサポート</span><span class="sxs-lookup"><span data-stu-id="e3265-139">Drill-down analysis support</span></span>  <br/> |<span data-ttu-id="e3265-140">×</span><span class="sxs-lookup"><span data-stu-id="e3265-140">No</span></span>  <br/> |<span data-ttu-id="e3265-141">○</span><span class="sxs-lookup"><span data-stu-id="e3265-141">Yes</span></span>  <br/> |
|<span data-ttu-id="e3265-142">メディアの信頼性メトリックス</span><span class="sxs-lookup"><span data-stu-id="e3265-142">Media reliability metrics</span></span>  <br/> |<span data-ttu-id="e3265-143">×</span><span class="sxs-lookup"><span data-stu-id="e3265-143">No</span></span>  <br/> |<span data-ttu-id="e3265-144">○</span><span class="sxs-lookup"><span data-stu-id="e3265-144">Yes</span></span>  <br/> |
|<span data-ttu-id="e3265-145">既定のレポート</span><span class="sxs-lookup"><span data-stu-id="e3265-145">Out-of-the-box reports</span></span>  <br/> |<span data-ttu-id="e3265-146">○</span><span class="sxs-lookup"><span data-stu-id="e3265-146">Yes</span></span>  <br/> |<span data-ttu-id="e3265-147">○</span><span class="sxs-lookup"><span data-stu-id="e3265-147">Yes</span></span>  <br/> |
|<span data-ttu-id="e3265-148">プロジェクト概要のレポート</span><span class="sxs-lookup"><span data-stu-id="e3265-148">Overview reports</span></span>  <br/> |<span data-ttu-id="e3265-149">○</span><span class="sxs-lookup"><span data-stu-id="e3265-149">Yes</span></span>  <br/> |<span data-ttu-id="e3265-150">○</span><span class="sxs-lookup"><span data-stu-id="e3265-150">Yes</span></span>  <br/> |
|<span data-ttu-id="e3265-151">ユーザーごとのレポートの設定</span><span class="sxs-lookup"><span data-stu-id="e3265-151">Per-user report set</span></span>  <br/> |<span data-ttu-id="e3265-152">×</span><span class="sxs-lookup"><span data-stu-id="e3265-152">No</span></span>  <br/> |<span data-ttu-id="e3265-153">○</span><span class="sxs-lookup"><span data-stu-id="e3265-153">Yes</span></span>  <br/> |
|<span data-ttu-id="e3265-154">レポートのカスタマイズを設定する (追加、削除、レポートの変更)</span><span class="sxs-lookup"><span data-stu-id="e3265-154">Report set customization (add, delete, modify reports)</span></span>  <br/> |<span data-ttu-id="e3265-155">×</span><span class="sxs-lookup"><span data-stu-id="e3265-155">No</span></span>  <br/> |<span data-ttu-id="e3265-156">○</span><span class="sxs-lookup"><span data-stu-id="e3265-156">Yes</span></span>  <br/> |
|<span data-ttu-id="e3265-157">ビデオを使った画面をメトリックを共有します。</span><span class="sxs-lookup"><span data-stu-id="e3265-157">Video-based screen sharing metrics</span></span>  <br/> |<span data-ttu-id="e3265-158">×</span><span class="sxs-lookup"><span data-stu-id="e3265-158">No</span></span>  <br/> |<span data-ttu-id="e3265-159">○</span><span class="sxs-lookup"><span data-stu-id="e3265-159">Yes</span></span>  <br/> |
|<span data-ttu-id="e3265-160">ビデオの基準</span><span class="sxs-lookup"><span data-stu-id="e3265-160">Video metrics</span></span>  <br/> |<span data-ttu-id="e3265-161">×</span><span class="sxs-lookup"><span data-stu-id="e3265-161">No</span></span>  <br/> |<span data-ttu-id="e3265-162">○</span><span class="sxs-lookup"><span data-stu-id="e3265-162">Yes</span></span>  <br/> |
|<span data-ttu-id="e3265-163">データの量</span><span class="sxs-lookup"><span data-stu-id="e3265-163">Amount of data available</span></span>  <br/> |<span data-ttu-id="e3265-164">最後の 6 か月</span><span class="sxs-lookup"><span data-stu-id="e3265-164">Last 6 months</span></span>  <br/> |<span data-ttu-id="e3265-165">最後の 6 か月</span><span class="sxs-lookup"><span data-stu-id="e3265-165">Last 6 months</span></span>  <br/> |
|<span data-ttu-id="e3265-166">Microsoft チーム データ</span><span class="sxs-lookup"><span data-stu-id="e3265-166">Microsoft Teams data</span></span>  <br/> |<span data-ttu-id="e3265-167">○</span><span class="sxs-lookup"><span data-stu-id="e3265-167">Yes</span></span>  <br/> |<span data-ttu-id="e3265-168">○</span><span class="sxs-lookup"><span data-stu-id="e3265-168">Yes</span></span>  <br/> |
   
### <a name="out-of-the-box-reports"></a><span data-ttu-id="e3265-169">既定のレポート</span><span class="sxs-lookup"><span data-stu-id="e3265-169">Out-of-the-box reports</span></span>

<span data-ttu-id="e3265-p104">CQD のエディションの両方の [の組み込みを提供するエクスペリエンスを提供する通話品質の基準の新しいレポートを作成する必要はありません。表示を開始するには、バックエンドのデータが処理されると、レポートでデータの品質に電話します。</span><span class="sxs-lookup"><span data-stu-id="e3265-p104">Both editions of CQD provide an out-of-the-box experience, giving you call quality metrics without the need to create any new reports. Once data is processed in the back-end, you can start seeing call quality data in the reports.</span></span>
  
### <a name="overview-reports"></a><span data-ttu-id="e3265-172">プロジェクト概要のレポート</span><span class="sxs-lookup"><span data-stu-id="e3265-172">Overview reports</span></span>

<span data-ttu-id="e3265-173">CQD のエディションの両方が全体の通話品質の情報に高度なエントリ ポイントを提供が要約レポートで情報を表示する方法の詳細なレポートの異なるです。</span><span class="sxs-lookup"><span data-stu-id="e3265-173">Both editions of the CQD provide a high-level entry point to the overall call quality information, but the way information is presented in Summary Reports is different from that of Detailed Reports.</span></span>
  
<span data-ttu-id="e3265-174">サマリー レポートでは、ユーザーが迅速に参照し、全体的な通話品質の状態と傾向を把握できるようにするタブ ページを簡素化されたレポート ビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="e3265-174">Summary Reports provide a simplified tabbed page report view that enables users to quickly browse and understand the overall call quality status and trends.</span></span>
  
<span data-ttu-id="e3265-175">4 つのタブは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e3265-175">The four tabs include:</span></span>
  
- <span data-ttu-id="e3265-176">**通話品質の全体的な**は、すべてのストリームで、サーバー クライアント ストリームの集約とクライアント ストリームに別のサーバー クライアントと傾向の月と日単位の形式でクライアント ストリームに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="e3265-176">**Overall Call Quality** - provides information about all streams, which is an aggregation of Server-Client streams and Client-Client streams, as well as separate Server-Client and Client-Client streams, in the form of monthly and daily trends.</span></span>
    
- <span data-ttu-id="e3265-177">**サーバーのクライアント**のでは、サーバーとクライアントの端点の間でストリームの詳細についてを提供します。</span><span class="sxs-lookup"><span data-stu-id="e3265-177">**Server - Client** - provides additional details for the streams between Server and Client endpoints.</span></span>
    
- <span data-ttu-id="e3265-178">**クライアント**の - では、2 つのクライアントの端点の間でストリーム追加の詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="e3265-178">**Client - Client** - provides additional details for the streams between two Client endpoints.</span></span>
    
- <span data-ttu-id="e3265-179">**音声品質の SLA**には、通話に含まれている、Skype for Business Online の音声品質 SLA に関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="e3265-179">**Voice Quality SLA** - provides information about calls that are included in the Skype for Business Online Voice Quality SLA.</span></span>
    
### <a name="overall-call-quality-tab"></a><span data-ttu-id="e3265-180">[通話品質の全体的な] タブ</span><span class="sxs-lookup"><span data-stu-id="e3265-180">Overall Call Quality tab</span></span>

<span data-ttu-id="e3265-p105">このタブでデータを使用して、ストリーム カウントと低下パーセンテージを見て、通話品質の状態と傾向を評価します。右上隅の凡例は、これらの測定値を表す色と視覚的な要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="e3265-p105">Use the data on this tab to evaluate call quality status and trends by looking at the stream counts and poor percentages. The legend in the upper-right corner shows which color and visual elements represent these metrics.</span></span>
  
![CQD データ キー](../images/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
<span data-ttu-id="e3265-p106">次の 3 つのグループに分類ストリーム: 低い、不明なします。あるも計算*が低下 %*の値として分類をストリームの比率ように \* 悪い \* 分類ストリームの合計数にします。*低下 % = 低下ストリーム/(低いストリーム + 良いストリーム) \* 100* 、これにより、*低下率*は、*未分類*ストリームが複数存在することによって影響を受けません。どのような低下または適切なストリームの分類に使う、[通話品質のしきい値](https://aka.ms/cqd_quality_thresholds)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3265-p106">Streams are classified in three groups: Good, Poor, and Unclassified. There are also calculated  *Poor %*  values that give you the ratio of streams classified as \* Poor\*  to the total classified stream count. Since *Poor % = Poor streams/ (Poor streams+ Good streams) \* 100*  , this makes the *Poor %*  unaffected by the presence with multiple *Unclassified*  streams. For what is used for classifying a stream as poor or good, refer to [Call Quality Thresholds](https://aka.ms/cqd_quality_thresholds).</span></span>
  
<span data-ttu-id="e3265-188">左側の目盛を使用すると、通話の値のカウントを測定できます。</span><span class="sxs-lookup"><span data-stu-id="e3265-188">Use the scale on the left to measure the call count values.</span></span>
  
![CQD データの数](../images/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
<span data-ttu-id="e3265-190">右側の低下 % の値を測定するのにスケールを使用します。</span><span class="sxs-lookup"><span data-stu-id="e3265-190">Use the scale on the right to measure the Poor % values.</span></span>
  
![CQD データ パーセント](../images/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
<span data-ttu-id="e3265-192">バーの上にマウスを置いて、実際の数値を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="e3265-192">You can also obtain the actual numerical values by hovering the mouse over a bar.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e3265-193">次の例は、非常に小さいサンプル データ セットからし、値は、実際に配置する現実的なします。</span><span class="sxs-lookup"><span data-stu-id="e3265-193">The following example is from a very small sample data set, and the values aren't realistic for an actual deployment.</span></span> 
  
![数値の CQD データ](../images/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
<span data-ttu-id="e3265-p107">全体的なストリーム ボリュームは、どのように関連する計算が低下率はの決定に重要な要因です。全体的なストリーム量が小さいほど、信頼性が低いほど低下率を報告された値があります。</span><span class="sxs-lookup"><span data-stu-id="e3265-p107">The overall stream volume is an important factor in determining how relevant the calculated Poor percentages are. The smaller the volume of overall stream, the less reliable the reported Poor percentage values are.</span></span>
  
### <a name="server-client-tab-and-client-client-tabs"></a><span data-ttu-id="e3265-197">クライアント サーバー] タブの [とクライアントのタブ</span><span class="sxs-lookup"><span data-stu-id="e3265-197">Server-Client tab and Client-Client tabs</span></span>

<span data-ttu-id="e3265-p108">これら 2 つのタブは、そのエンドポイントの両端のシートのシナリオで行われたストリームに追加の詳細情報を提供します。両方のタブには、[メディア ストリームをフローは 4 つのシナリオを表す、折りたたみ可能な 4 つのセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="e3265-p108">These two tabs provide additional details for the streams that took place in their endpoint-to-endpoint scenarios. Both tabs have four collapsible sections, representing four scenarios under which media streams would flow.</span></span>
  
- <span data-ttu-id="e3265-200">内部ワイヤード (有線)</span><span class="sxs-lookup"><span data-stu-id="e3265-200">Wired Inside</span></span>
    
- <span data-ttu-id="e3265-201">外部ワイヤード (有線)</span><span class="sxs-lookup"><span data-stu-id="e3265-201">Wired Outside</span></span>
    
- <span data-ttu-id="e3265-202">Wifi 内側</span><span class="sxs-lookup"><span data-stu-id="e3265-202">Wifi Inside</span></span>
    
- <span data-ttu-id="e3265-203">Wifi 外</span><span class="sxs-lookup"><span data-stu-id="e3265-203">Wifi Outside</span></span>
    
#### <a name="inside-test"></a><span data-ttu-id="e3265-204">内側のテスト</span><span class="sxs-lookup"><span data-stu-id="e3265-204">Inside Test</span></span>

<span data-ttu-id="e3265-p109">処理中に存在する場合、CQD バックエンドは*内側*または*外側*建物の情報を使用する名前を付けてストリームを分類します。各ストリームの端点は、サブネット アドレスに関連付けられます。サブネットがアップロードされた建物の情報のサブネットの一覧である場合は、内部見なされます。建物情報がまだアップロードされていない場合、[内のテストが常にストリームとして分類*外側*します。内部テスト Server クライアントのシナリオのみクライアント エンドポイントを考慮することに注意してください。サーバーが常にための外部ユーザーの観点から、この加算されませんテストします。</span><span class="sxs-lookup"><span data-stu-id="e3265-p109">During processing, the CQD back-end classifies a stream as  *Inside*  or *Outside*  using Building information, if it exists. Endpoints of each stream are associated with a subnet address. If the subnet is in the list of the subnets in the uploaded Building information, then it is considered Inside. If Building information has not yet been uploaded, then Inside Test will always classify the streams as *Outside*  . Please note that Inside Test for Server-Client scenario only considers the client endpoint. Because servers are always outside from a user's perspective, this isn't accounted for in the test.</span></span>
  
#### <a name="wired-vs-wifi"></a><span data-ttu-id="e3265-211">Wifi とワイヤード (有線)</span><span class="sxs-lookup"><span data-stu-id="e3265-211">Wired vs. wifi</span></span>

<span data-ttu-id="e3265-p110">名前が示すクライアント接続の種類に基づいて分類基準です。もう一度、サーバーが常にワイヤード (有線) し、計算に含まれていないこと。</span><span class="sxs-lookup"><span data-stu-id="e3265-p110">As the names indicate, this is a classification criteria based on the type of client connections. Again, server is always wired and it isn't included in the calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e3265-214">ストリームを指定すると 2 つのエンドポイントのいずれかの Wifi ネットワークに接続されている場合、[として分類されます CQD で Wifi します。</span><span class="sxs-lookup"><span data-stu-id="e3265-214">Given a stream, if one of the two endpoints is connected to a Wifi network, then it is classified as Wifi in CQD.</span></span> 
  
## <a name="selecting-product-data-to-see-in-reports"></a><span data-ttu-id="e3265-215">レポートを表示する製品データを選択します。</span><span class="sxs-lookup"><span data-stu-id="e3265-215">Selecting product data to see in reports</span></span>
<span data-ttu-id="e3265-216"><a name="BKMKFeaturesOfTheCQD"> </a></span><span class="sxs-lookup"><span data-stu-id="e3265-216"></span></span>

<span data-ttu-id="e3265-217">すべての製品データを表示する**製品フィルター**のドロップダウン メニューを使用する概要と強化されたレポートの場所で、マイクロソフトのチーム データだけまたは [のみ Skype for Business Online のデータします。</span><span class="sxs-lookup"><span data-stu-id="e3265-217">In the Summary and Location Enhanced Reports, you can use the **Product Filter** drop-down to show all product data, only Microsoft Teams data, or only Skype for Business Online data.</span></span>
  
![スクリーン ショットは、すべてのオプション、Microsoft チーム、Skype for Business と製品フィルター コントロールが表示されます。](../images/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
<span data-ttu-id="e3265-219">詳細なレポートは、Microsoft チームまたは Skype for Business Online のデータ レポートの定義の一部としてデータをフィルター処理するのにチーム ディメンションを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="e3265-219">In Detailed reports, you can use the Teams dimension to filter the data to Microsoft Teams or Skype for Business Online data as part of defining the report.</span></span>
  
## <a name="upload-building-information"></a><span data-ttu-id="e3265-220">アップロード建物の情報</span><span class="sxs-lookup"><span data-stu-id="e3265-220">Upload Building information</span></span>
<span data-ttu-id="e3265-221"><a name="BKMKFeaturesOfTheCQD"> </a></span><span class="sxs-lookup"><span data-stu-id="e3265-221"></span></span>

<span data-ttu-id="e3265-p111">CQD の概要レポートのダッシュ ボードには、右上隅にある [設定] メニューから**テナントのデータのアップロード**を選択してアクセス、**テナントのデータをアップロード**したページが含まれています。このページを使用管理者用の IP アドレスと地理的な情報は、マッピングなどの独自の情報をアップロードするなどの各ワイヤレス アクセス ポイントと MAC アドレスをマッピングします。</span><span class="sxs-lookup"><span data-stu-id="e3265-p111">The CQD Summary Reports dashboard includes a **Tenant Data Upload** page, accessed by selecting **Tenant Data Upload** from the settings menu in the top-right corner. This page is used for admins to upload their own information, such as mapping of IP address and geographical information, mapping each wireless AP and its MAC address, etc.</span></span>
  
![CQD ダッシュ ボード](../images/839c9ab4-0246-46c9-8402-aafd83a0bc63.png)
  
1. <span data-ttu-id="e3265-p112">**テナントのデータのアップロード**] ページで、[ドロップダウン メニューを使用して、アップロードするファイルの種類を選択します。ファイルのデータ型は、ファイルの内容を示します (たとえば、「作成」を参照する IP アドレスのマッピングをも、その他の地理的な情報を使った)。現在「文書」データ型はサポートのみです。今後のリリースでは、いくつかの他のデータ型が追加されます。</span><span class="sxs-lookup"><span data-stu-id="e3265-p112">On the **Tenant Data Upload** page, use the drop-down menu to choose a data file type for uploading. The file data type denotes the content of the file (for example, "Building" refers to mapping of IP address and building as well as other geographical information). Currently we are only supporting the "Building" data type. A few more data types will be added with subsequent releases.</span></span>
    
2. <span data-ttu-id="e3265-229">ファイルのデータ型を選択すると、**参照**をデータ ファイルを選択する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e3265-229">After selecting the file data type, click **Browse** to choose a data file.</span></span>
    
  - <span data-ttu-id="e3265-p113">データ ファイルは、.tsv (タブ区切り値) ファイルまたは .csv (カンマ区切り値) ファイルである必要があります。場合 .csv ファイルを使用するには、カンマが含まれている任意のフィールドする必要があります引用符を含むがないか、カンマを削除します。たとえば、文書名が NY、NY] の場合、.csv ファイルで、必要がありますとして入力する"NY、NY"。</span><span class="sxs-lookup"><span data-stu-id="e3265-p113">The data file must be a .tsv (Tab-separated values) file or a .csv (Comma-separated value) file. If using a .csv file, any field that contains a comma must contain quotes or have the comma removed. For example, if your building name is NY,NY, in the .csv file it should be entered as "NY,NY".</span></span>
    
  - <span data-ttu-id="e3265-233">データ ファイルを 50 MB を超えることがあります。</span><span class="sxs-lookup"><span data-stu-id="e3265-233">The data file must be no larger than 50MB in size.</span></span>
    
  - <span data-ttu-id="e3265-234">個々 のデータ ファイル、ファイル内の各列が、このトピックの後半で説明されている定義済みのデータ型と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3265-234">For each data file, each column in the file must match a predefined data type, discussed later in this topic.</span></span>
    
3. <span data-ttu-id="e3265-235">データ ファイルを選択すると、**開始日**と、必要に応じて、**終了日が指定**を指定します。</span><span class="sxs-lookup"><span data-stu-id="e3265-235">After selecting a data file, specify **Start date** and, optionally, **Specify an end date**.</span></span>
    
4. <span data-ttu-id="e3265-236">**開始日**を選択すると、**アップロード**CQD サーバーにファイルをアップロードする] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e3265-236">After selecting **Start date**, select **Upload** to upload the file to the CQD server.</span></span>
    
    <span data-ttu-id="e3265-p114">ファイルをアップロードする前に、まず検証されます。検証された後、Azure blob に保存されます。Azure blob に格納される検証が失敗したか、ファイルが失敗したかどうか、ファイルへの修正を要求するエラー メッセージが表示されます。次の図では、データ ファイルの列の数が正しくないときに発生するエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3265-p114">Before the file is uploaded, it is first validated. Once validated, it is stored in an Azure blob. If validation fails or the file fails to be stored in an Azure blob, an error message is displayed requesting a correction to the file. The following image shows an error occurring when the number of columns in the data file is incorrect.</span></span>
    
     ![アップロードの入力規則のエラーの CQD の例](../images/22716a32-3d3d-4870-983c-46089e8b212a.png)
  
5. <span data-ttu-id="e3265-p115">入力規則の中にエラーが発生しない場合、ファイルのアップロードは成功します。表内の**自分のアップロード**、そのページの下部に現在のテナントのすべてアップロードされたファイルの完全な一覧を表示するデータをアップロードしたファイルを表示できます。</span><span class="sxs-lookup"><span data-stu-id="e3265-p115">If no errors occur during validation, the file upload will succeed. You can then see the uploaded data file in the **My uploads** table, which shows the full list of all uploaded files for the current tenant at the bottom of that page.</span></span>
    
    <span data-ttu-id="e3265-p116">各レコードの表示にアップロードした 1 つのテナント データ ファイル、ファイルの種類、最終更新日時、期間、説明、削除、およびダウンロード アイコンにします。ファイルを削除するには、表内のごみ箱アイコンを選択します。ファイルをダウンロードするには、[テーブルの [**ダウンロード**] 列でダウンロード アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="e3265-p116">Each record shows one uploaded tenant data file, with file type, last update time, time period, description, remove, and a download icon. To remove a file, select the trash bin icon in the table. To download a file, select the download icon in the **Download** column of the table.</span></span>
    
     ![テーブルな CQD マイ アップロード](../images/4168a883-bbea-461a-80b1-42eedf2e7732.png)
  
### <a name="tenant-data-file-format-and-building-data-file-structure"></a><span data-ttu-id="e3265-248">テナント データ ファイル形式で文書のデータ ファイルの構造</span><span class="sxs-lookup"><span data-stu-id="e3265-248">Tenant data file format and Building data file structure</span></span>
<span data-ttu-id="e3265-249"><a name="BKMKTenantDataFile"> </a></span><span class="sxs-lookup"><span data-stu-id="e3265-249"></span></span>

<span data-ttu-id="e3265-250">アップロードするデータ ファイルの書式には、アップロードする前に確認を通過するのには、次を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3265-250">The format of the data file you upload must meet the following to pass the validation check before uploading.</span></span>
  
- <span data-ttu-id="e3265-251">つまり、行ごとに、列見出しをで区切られて .tsv ファイル、または .csv ファイルをカンマで区切られた各列のいずれかのファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="e3265-251">The file must be either a .tsv file, which means, in each row, columns are separated by a TAB, or a .csv file with each column separated by a comma.</span></span>
    
- <span data-ttu-id="e3265-p117">データ ファイルの内容には、テーブルの見出しが含まれていません。ヘッダーしないなどの「ネットワーク」は、データ ファイルの最初の行には、実際のデータ必要があることなどです。</span><span class="sxs-lookup"><span data-stu-id="e3265-p117">The content of the data file doesn't include table headers. That means the first line of the data file should be real data, not headers like "Network," etc.</span></span>
    
- <span data-ttu-id="e3265-p118">各列のデータ型できるだけ文字列、数値、またはブール値です。数値の場合は、値があります数値を指定します。ブール値の場合は、値は 0 または 1 は必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3265-p118">For each column, the data type can only be String, Number, or Bool. If it is Number, the value must be a numeric value; if it is Bool, the value must be either 0 or 1.</span></span>
    
- <span data-ttu-id="e3265-p119">各列のデータ型が文字列の場合は、データ空 (まだ、適切な区切りで区切る必要がありますが、(タブまたはコンマなど)。これは、したフィールドに割り当て、その空の文字列値。</span><span class="sxs-lookup"><span data-stu-id="e3265-p119">For each column, if the data type is string, the data can be empty (but still must be separated by an appropriate delimited (i.e., a tab or comma). This just assigns that field an empty string value.</span></span>
    
- <span data-ttu-id="e3265-258">必要があります、各行の 14 列と、各列は次のデータが必要です型、および列は、次の表に記載されている順序である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3265-258">There must be 14 columns for each row, and each column must have the following data type, and the columns must be in the order listed in the following table:</span></span>
    
|<span data-ttu-id="e3265-259">**列名**</span><span class="sxs-lookup"><span data-stu-id="e3265-259">**Column Name**</span></span>|<span data-ttu-id="e3265-260">**データ型**</span><span class="sxs-lookup"><span data-stu-id="e3265-260">**Data type**</span></span>|<span data-ttu-id="e3265-261">**{例}**</span><span class="sxs-lookup"><span data-stu-id="e3265-261">**Example**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e3265-262">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="e3265-262">Network</span></span>  <br/> |<span data-ttu-id="e3265-263">String</span><span class="sxs-lookup"><span data-stu-id="e3265-263">String</span></span>  <br/> |<span data-ttu-id="e3265-264">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="e3265-264">192.168.1.0</span></span>  <br/> |
|<span data-ttu-id="e3265-265">チーム</span><span class="sxs-lookup"><span data-stu-id="e3265-265">NetworkName</span></span>  <br/> |<span data-ttu-id="e3265-266">String</span><span class="sxs-lookup"><span data-stu-id="e3265-266">String</span></span>  <br/> |<span data-ttu-id="e3265-267">米国/シアトル/シアトル-海-1</span><span class="sxs-lookup"><span data-stu-id="e3265-267">USA/Seattle/SEATTLE-SEA-1</span></span>  <br/> |
|<span data-ttu-id="e3265-268">NetworkRange</span><span class="sxs-lookup"><span data-stu-id="e3265-268">NetworkRange</span></span>  <br/> |<span data-ttu-id="e3265-269">番号</span><span class="sxs-lookup"><span data-stu-id="e3265-269">Number</span></span>  <br/> |<span data-ttu-id="e3265-270">26</span><span class="sxs-lookup"><span data-stu-id="e3265-270">26</span></span>  <br/> |
|<span data-ttu-id="e3265-271">BuildingName</span><span class="sxs-lookup"><span data-stu-id="e3265-271">BuildingName</span></span>  <br/> |<span data-ttu-id="e3265-272">String</span><span class="sxs-lookup"><span data-stu-id="e3265-272">String</span></span>  <br/> |<span data-ttu-id="e3265-273">シアトル-海-1</span><span class="sxs-lookup"><span data-stu-id="e3265-273">SEATTLE-SEA-1</span></span>  <br/> |
|<span data-ttu-id="e3265-274">OwnershipType</span><span class="sxs-lookup"><span data-stu-id="e3265-274">OwnershipType</span></span>  <br/> |<span data-ttu-id="e3265-275">String</span><span class="sxs-lookup"><span data-stu-id="e3265-275">String</span></span>  <br/> |<span data-ttu-id="e3265-276">Contoso 社</span><span class="sxs-lookup"><span data-stu-id="e3265-276">Contoso</span></span>  <br/> |
|<span data-ttu-id="e3265-277">BuildingType</span><span class="sxs-lookup"><span data-stu-id="e3265-277">BuildingType</span></span>  <br/> |<span data-ttu-id="e3265-278">String</span><span class="sxs-lookup"><span data-stu-id="e3265-278">String</span></span>  <br/> |<span data-ttu-id="e3265-279">IT の終了</span><span class="sxs-lookup"><span data-stu-id="e3265-279">IT Termination</span></span>  <br/> |
|<span data-ttu-id="e3265-280">BuildingOfficeType</span><span class="sxs-lookup"><span data-stu-id="e3265-280">BuildingOfficeType</span></span>  <br/> |<span data-ttu-id="e3265-281">String</span><span class="sxs-lookup"><span data-stu-id="e3265-281">String</span></span>  <br/> |<span data-ttu-id="e3265-282">エンジニア リング</span><span class="sxs-lookup"><span data-stu-id="e3265-282">Engineering</span></span>  <br/> |
|<span data-ttu-id="e3265-283">市区町村</span><span class="sxs-lookup"><span data-stu-id="e3265-283">City</span></span>  <br/> |<span data-ttu-id="e3265-284">String</span><span class="sxs-lookup"><span data-stu-id="e3265-284">String</span></span>  <br/> |<span data-ttu-id="e3265-285">港区</span><span class="sxs-lookup"><span data-stu-id="e3265-285">Seattle</span></span>  <br/> |
|<span data-ttu-id="e3265-286">一括</span><span class="sxs-lookup"><span data-stu-id="e3265-286">ZipCode</span></span>  <br/> |<span data-ttu-id="e3265-287">String</span><span class="sxs-lookup"><span data-stu-id="e3265-287">String</span></span>  <br/> |<span data-ttu-id="e3265-288">98001</span><span class="sxs-lookup"><span data-stu-id="e3265-288">98001</span></span>  <br/> |
|<span data-ttu-id="e3265-289">国</span><span class="sxs-lookup"><span data-stu-id="e3265-289">Country</span></span>  <br/> |<span data-ttu-id="e3265-290">String</span><span class="sxs-lookup"><span data-stu-id="e3265-290">String</span></span>  <br/> |<span data-ttu-id="e3265-291">US</span><span class="sxs-lookup"><span data-stu-id="e3265-291">US</span></span>  <br/> |
|<span data-ttu-id="e3265-292">州</span><span class="sxs-lookup"><span data-stu-id="e3265-292">State</span></span>  <br/> |<span data-ttu-id="e3265-293">String</span><span class="sxs-lookup"><span data-stu-id="e3265-293">String</span></span>  <br/> |<span data-ttu-id="e3265-294">34-2</span><span class="sxs-lookup"><span data-stu-id="e3265-294">WA</span></span>  <br/> |
|<span data-ttu-id="e3265-295">地域</span><span class="sxs-lookup"><span data-stu-id="e3265-295">Region</span></span>  <br/> |<span data-ttu-id="e3265-296">String</span><span class="sxs-lookup"><span data-stu-id="e3265-296">String</span></span>  <br/> |<span data-ttu-id="e3265-297">MSUS</span><span class="sxs-lookup"><span data-stu-id="e3265-297">MSUS</span></span>  <br/> |
|<span data-ttu-id="e3265-298">InsideCorp</span><span class="sxs-lookup"><span data-stu-id="e3265-298">InsideCorp</span></span>  <br/> |<span data-ttu-id="e3265-299">ブール値</span><span class="sxs-lookup"><span data-stu-id="e3265-299">Bool</span></span>  <br/> |<span data-ttu-id="e3265-300">1</span><span class="sxs-lookup"><span data-stu-id="e3265-300">1</span></span>  <br/> |
|<span data-ttu-id="e3265-301">ExpressRoute</span><span class="sxs-lookup"><span data-stu-id="e3265-301">ExpressRoute</span></span>  <br/> |<span data-ttu-id="e3265-302">ブール値</span><span class="sxs-lookup"><span data-stu-id="e3265-302">Bool</span></span>  <br/> |<span data-ttu-id="e3265-303">0</span><span class="sxs-lookup"><span data-stu-id="e3265-303">0</span></span>  <br/> |
   
> [!IMPORTANT]
> <span data-ttu-id="e3265-p120">スーパー (1 つのルーティング プレフィックスをいくつかのサブネットの組み合わせ) を表示するのには、ネットワークの範囲を使用できます。重複する範囲のすべての新しい文書のアップロードがチェックされます。文書ファイルを以前にアップロードした場合は、現在のファイルをダウンロードし、もう一度、重複を識別してもう一度アップロードする前に、問題を解決するのには、ください。レポート内の建物サブネットの問題が発生のマッピングで以前にアップロードされたファイルが重複可能性があります。特定の VPN 実装サブネット情報を正確に報告しません。お勧めする VPN サブネットを追加、サブネットの 1 つのエントリの代わりに、[ファイルを作成するときに別のエントリとして追加されます VPN サブネットのアドレスごとに個別の 32 ビット ネットワーク。各行には、同じ文書メタデータをことができます。たとえば、172.16.18.0/24 の 1 つの行ではなく、172.16.18.0/32 と 172.16.18.255/32、範囲のそれぞれのアドレスに 1 つの行を持つ 256 の行が必要です。</span><span class="sxs-lookup"><span data-stu-id="e3265-p120">The network range can be used to represent a supernet (combination of several subnets with a single routing prefix). All new building uploads will be checked for any overlapping ranges. If you have previously uploaded a building file, you should download the current file and re-upload it to identify any overlaps and fix the issue before uploading again. Any overlap in previously uploaded files may result in the wrong mappings of subnets to buildings in the reports. Certain VPN implementations do not accurately report the subnet information. It is recommended that when adding a VPN subnet to the building file, instead of one entry for the subnet, separate entries are added for each address in the VPN subnet as a separate 32-bit network. Each row can have the same building metadata. For example, instead of one row for 172.16.18.0/24, you should have 256 rows, with one row for each address between 172.16.18.0/32 and 172.16.18.255/32, inclusive.</span></span> 
  
## <a name="selecting-media-type-in-detailed-reports"></a><span data-ttu-id="e3265-312">詳細なレポートでメディアの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="e3265-312">Selecting media type in detailed reports</span></span>
<span data-ttu-id="e3265-313"><a name="BKMKFeaturesOfTheCQD"> </a></span><span class="sxs-lookup"><span data-stu-id="e3265-313"></span></span>

<span data-ttu-id="e3265-p121">詳細なレポートでは、音声、ビデオ、アプリケーションの共有、および画面共有メディアの種類のビデオを使ったの品質とメディアの信頼性を見てをサポートします。ディメンション、メジャー、および、1 つのメディアの種類に固有のフィルターと接頭辞を「オーディオ」、「ビデオ」、"AppSharing"、または"VBSS"であります。</span><span class="sxs-lookup"><span data-stu-id="e3265-p121">The detailed reports support looking at quality and media reliability for audio, video, application sharing, and video-based screen-sharing media types. Dimensions, measures, and filters that are specific for a single media type have "Audio", "Video", "AppSharing", or "VBSS" as a prefix.</span></span>
  
![品質のダッシュ ボードの大きさを呼び出します。](../images/ae132202-d6dc-43bd-b8b3-ea9c24c519e8.png)
  
<span data-ttu-id="e3265-p122">ディメンションとメジャーの 1 つのメディアの種類を表示する場合は、新しいメディアの種類のディメンションとフィルター必要があります。たとえば、合計セッションを別のメディアの種類にわたってカウントが表示されているレポートを表示するには、メディアの種類のディメンションを追加します。</span><span class="sxs-lookup"><span data-stu-id="e3265-p122">If you want to view the dimensions and measures for a single media type, the new MediaType dimension and filter may be required. For example, to have a report that shows the total session counts across different media types, include the MediaType dimension.</span></span>
  
![品質ダッシュ ボードのストリームの合計数を呼び出します。](../images/21d5d0dc-2321-415e-8ef2-cea06165601c.png)

## <a name="related-topics"></a><span data-ttu-id="e3265-320">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e3265-320">Related topics</span></span>
[<span data-ttu-id="e3265-321">Skype for Business 通話分析を設定します。</span><span class="sxs-lookup"><span data-stu-id="e3265-321">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="e3265-322">通話の分析を使って低下通話品質のトラブルシューティングを行う</span><span class="sxs-lookup"><span data-stu-id="e3265-322">Use Call Analytics to troubleshoot poor  call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="e3265-323">通話の分析手法と通話品質のダッシュ ボードの違いですか。</span><span class="sxs-lookup"><span data-stu-id="e3265-323">Difference between Call Analytics and Call Quality Dashboard?</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)
