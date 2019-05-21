---
title: Skype for Business Server の通話品質ダッシュボードを使用する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec62b70f-885e-4272-b9d2-a574ea434b64
description: '概要: 通話品質ダッシュボードの使用方法について説明します。 通話品質ダッシュボードは、Skype for Business Server のツールです。'
ms.openlocfilehash: b89f766cfcbfbc9fe2c700162f3c0b4e69a7e6bd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274556"
---
# <a name="use-call-quality-dashboard-for-skype-for-business-server"></a><span data-ttu-id="be691-104">Skype for Business Server の通話品質ダッシュボードを使用する</span><span class="sxs-lookup"><span data-stu-id="be691-104">Use Call Quality Dashboard for Skype for Business Server</span></span>
 
<span data-ttu-id="be691-105">**概要:** 通話品質ダッシュボードの使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="be691-105">**Summary:** Learn about how to use the Call Quality Dashboard.</span></span> <span data-ttu-id="be691-106">通話品質ダッシュボードは、Skype for Business Server のツールです。</span><span class="sxs-lookup"><span data-stu-id="be691-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="be691-p103">CQD により、IT 担当者は集計データを使用して、メディア品質の問題が発生している環境におけるフォーカス領域を識別できるようになります。これにより、IT 担当者は異なるユーザーのグループの統計情報を比較して、傾向とパターンを識別できます。個別の通話に関する問題の解決にフォーカスしていませんが、特定の環境内の多くのユーザーに該当する問題と解決策の識別にフォーカスしています。</span><span class="sxs-lookup"><span data-stu-id="be691-p103">CQD allows IT Pros to use aggregate data to identify focus areas in their environment experiencing media quality issues. It allows an IT Pro to compare statistics for different groups of users and identify trends and patterns. It is not focused on solving individual call issues, but on identifying problems and solutions that will apply to many users in a given environment.</span></span>
  
## <a name="call-quality-dashboard-user-guide"></a><span data-ttu-id="be691-110">通話品質ダッシュボード ユーザー ガイド</span><span class="sxs-lookup"><span data-stu-id="be691-110">Call Quality Dashboard User Guide</span></span>

<span data-ttu-id="be691-p104">通話品質ダッシュボード (CQD) は、QoE (Quality of Experience) データに基づいてすばやくレポートをすばやく作成および整理するための Web ポータルです。CQD は、SSAS キューブを展開して、データを QoE 指標データベースに集約します。これにより、ユーザーは、レポートの作成と変更、およびリアルタイムの調査を行うことができます。Excel を使用してキューブに直接接続することもできますが、このポータルは、QoE データを扱ういくつかのワークフロー向けに最適化されています。このようなデータには、高速アクセスのためのレポート データのキャッシュ、情報の共有と公開のためのレポート ページへのディープ リンク、合理化されたレポートの編集と作成、レポートの説明の編集可能なメタデータが含まれます。さらに、CQD の Web API が公開されているため、ユーザーは、カスタム ダッシュボードで使用するキューブ データにプログラムでアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="be691-p104">The Call Quality Dashboard (CQD) is a web portal for quickly creating and organizing reports based on Quality of Experience (QoE) data. CQD deploys a SSAS cube to aggregate the data in the QoE Metrics database. This enables users to create and modify reports and do investigations in real-time. While it is possible to use Excel to connect directly to the cube, the portal is optimized for several workflows involving QoE data. This data includes caching of report data for fast access, deep links to report pages for information sharing and publishing, streamlined report editing and creation, and editable metadata for report descriptions. Additionally, CQD exposes web APIs that give users programmatic access to the cube data for use in custom dashboards.</span></span> 
  
### <a name="feature-overview"></a><span data-ttu-id="be691-117">機能の概要</span><span class="sxs-lookup"><span data-stu-id="be691-117">Feature Overview</span></span>

<span data-ttu-id="be691-118">ユーザーが通話品質ダッシュボードにアクセスすると、次のような画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="be691-118">When a user visits the Call Quality Dashboard, this is what s/he will see:</span></span>
  
![CQD の使用](../../media/1e061858-db6f-452b-9ae4-eab507220371.png)
  
1. <span data-ttu-id="be691-120">"サマリーウィンドウ" には、"レポートセット" (右) のコンテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="be691-120">The "Summary Pane" is where context for the "Report Set" (to the right) can be found.</span></span> 
    
2. <span data-ttu-id="be691-121">レポートセットレベルのプロパティ (Y 軸の高さを含む) を設定するには、[概要] ウィンドウで [編集] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="be691-121">Report Set level properties (including Y-axis height) can be set by clicking on "Edit" in the Summary Pane.</span></span>
    
3. <span data-ttu-id="be691-122">階層リンクにより、レポート セット階層内の現在の位置を識別できます。</span><span class="sxs-lookup"><span data-stu-id="be691-122">The Breadcrumb helps users identify their current location within the report set hierarchy.</span></span> 
    
4. <span data-ttu-id="be691-p105">サブレポートを含むレポートには、青いリンクが示されます。リンクをクリックすると、子レポートにドリル ダウンします。</span><span class="sxs-lookup"><span data-stu-id="be691-p105">Reports with sub-reports are shown with a blue link. Clicking on the link will drill down to the child reports.</span></span> 
    
<span data-ttu-id="be691-125">マウス カーソルを棒グラフや傾向線の上に移動すると、詳細な値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="be691-125">Moving the mouse over the bar charts and trend lines will show detailed values.</span></span> <span data-ttu-id="be691-126">フォーカスがあるレポートには、[編集]、[複製]、[削除]、[ダウンロード] というアクションメニューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="be691-126">The report that has focus will show the action menu: "Edit", "Clone", "Delete", and "Download".</span></span> 
  
### <a name="default-reports"></a><span data-ttu-id="be691-127">既定のレポート</span><span class="sxs-lookup"><span data-stu-id="be691-127">Default Reports</span></span>

<span data-ttu-id="be691-p107">ユーザーが通話品質ダッシュボード ポータルに初めてアクセスすると、既定のレポートのセットが自動的に作成されます。これらのレポートは、「システム レポート」とも呼ばれます。ユーザーは、これらのレポートを自由に変更したり削除したりできます。通常は、これらのレポートを拡張して新しい兄弟レポートや子レポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="be691-p107">When a user first accesses the Call Quality Dashboard portal, a default set of reports is automatically created. These reports are sometimes referred to as system reports. The user is able to freely modify or delete these reports. Generally, users will extend them by creating new sibling and child reports.</span></span> 
  
<span data-ttu-id="be691-132">最上位レベルでは、"オーディオストリームの月間トレンド" レポートには、すべてのオーディオストリームの月間トレンドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="be691-132">At the top level, the "Audio Streams Monthly Trend" report shows the monthly trend for all audio streams.</span></span> <span data-ttu-id="be691-133">横棒グラフの棒の上にマウスを移動すると、横棒グラフで表されるデータの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="be691-133">Moving the mouse over the bars in a bar chart will show a more detailed view of the data represented by the bar chart.</span></span> <span data-ttu-id="be691-134">オーディオストリームの月次トレンドレポートのタイトルをクリックすると、[管理された管理と非管理のオーディオストリーム] レポートに移動します。ここでは、管理と非管理の呼び出しの間でレポートが分割されます。</span><span class="sxs-lookup"><span data-stu-id="be691-134">Clicking on the title of the Audio Streams Monthly Trend report will navigate to the "Managed vs Unmanaged Audio Streams" report, where the reports are split between Managed and Unmanaged calls.</span></span> <span data-ttu-id="be691-135">管理された通話とは、有線接続経由で企業のファイアウォール内から発信された通話のことです。</span><span class="sxs-lookup"><span data-stu-id="be691-135">Managed calls are calls made from inside the corporate firewall over wired connections.</span></span> <span data-ttu-id="be691-136">非管理された通話には、会社のファイアウォールの外側から発信された通話、および wi-fi 経由のすべての通話が含まれます。</span><span class="sxs-lookup"><span data-stu-id="be691-136">Unmanaged calls include calls made from outside the corporate firewall as well as all calls made over Wi-Fi.</span></span>
  
<span data-ttu-id="be691-137">その他のトップレベルレポートは、"ユーザーから報告された通話品質評価のヒストグラム" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="be691-137">The other top level report is called the "User-reported Call Quality Rating Histogram."</span></span> <span data-ttu-id="be691-138">通話品質評価は、通話の品質を示すために、通話の終了時に Skype for Business ユーザーから提供された電話番号です。</span><span class="sxs-lookup"><span data-stu-id="be691-138">The Call Quality Ratings are the numbers given by Skype for Business users at the end of a call to indicate the quality of the call.</span></span> <span data-ttu-id="be691-139">評価の番号の範囲は 1 ~ 5 です。1は最も悪い値で、5が最も良いものになります。</span><span class="sxs-lookup"><span data-stu-id="be691-139">The rating numbers range from 1 to 5, with 1 being the worst and 5 being the best.</span></span> <span data-ttu-id="be691-140">ヒストグラムには、1か月の評価が表示された音声通話の数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="be691-140">The histogram shows the number of audio calls that had the indicated rating in one month.</span></span> 
  
<span data-ttu-id="be691-p110">通常、レポートのタイトルをクリックすると、データに対して追加のフィルターが適用されたレポートが表示されます。システム レポートの場合、それぞれの子レポートには、親レポートで使用できるデータのサブセットが表示されます。これにより、概念的にシンプルな問題解決のためのモデルが提供されます。つまり、問題を含むデータまたは傾向が示されるサブレポートを見極めることによって、問題空間を絞り込みます。新しいサブレポートを作成すると、特定のデータの傾向の起源に関して、独自の仮説を調査できます。</span><span class="sxs-lookup"><span data-stu-id="be691-p110">In general, clicking on the title of any of the reports will navigate into reports with additional filters on the data. In the system reports, each child report displays a subset of the data available in its parent report. This provides a conceptually simple model for problem solving: narrow down the problem space by investigating which sub-report the problematic data or trend is confined to. The ability to create new sub-reports allows users to investigate their own hypotheses as to the provenance of specific data trends.</span></span>
  
### <a name="creating-and-editing-reports"></a><span data-ttu-id="be691-145">レポートの作成および編集</span><span class="sxs-lookup"><span data-stu-id="be691-145">Creating and Editing Reports</span></span>

<span data-ttu-id="be691-146">レポートのアクションメニューで [編集] をクリックすると、レポートエディターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="be691-146">When clicking on "Edit" in the action menu of a report, users will see the Report Editor.</span></span> <span data-ttu-id="be691-147">それぞれのレポートは、キューブに対するクエリに基づきます。</span><span class="sxs-lookup"><span data-stu-id="be691-147">Each report is backed by a query into the cube.</span></span> <span data-ttu-id="be691-148">レポートは、クエリから返されたデータを視覚化したものです。</span><span class="sxs-lookup"><span data-stu-id="be691-148">A report is a visualization of the data returned by its query.</span></span> <span data-ttu-id="be691-149">レポート エディターは、これらのクエリやレポートの表示オプションを編集するためのユーザー インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="be691-149">The Report Editor is a user interface for editing these queries, as well as the display options of the report.</span></span> <span data-ttu-id="be691-150">レポート エディターを開くと、次のような画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="be691-150">When a user opens the Report Editor, this is what s/he will see:</span></span>
  
![CQD の使用](../../media/e8969625-e6f9-4d67-873f-93e78dd12b35.png)
  
1. <span data-ttu-id="be691-152">左側のウィンドウでは、ディメンション、メジャー、およびフィルターを選択します。</span><span class="sxs-lookup"><span data-stu-id="be691-152">Dimensions, measures, and filters are chosen in the left pane.</span></span> <span data-ttu-id="be691-153">既存の値のいずれかにマウスポインターを合わせると、値を削除できる "x" ボタンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="be691-153">Hovering over one of the existing values will show an "x" button that allows the value to be removed.</span></span> <span data-ttu-id="be691-154">見出しの横にあるプラス記号 (+) をクリックすると、新しい寸法、測定、またはフィルターを追加するためのダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="be691-154">Clicking on the "plus" button next to a heading will open the dialog for adding a new dimension, measure or filter.</span></span> 
    
2. <span data-ttu-id="be691-155">最上部には、グラフをカスタマイズするためのオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="be691-155">Options for chart customization are displayed at the top.</span></span>
    
3. <span data-ttu-id="be691-156">レポート エディターには、レポートのプレビュー機能があります。</span><span class="sxs-lookup"><span data-stu-id="be691-156">A preview of the report is available in the Report Editor.</span></span> 
    
4. <span data-ttu-id="be691-157">下部の編集ボックスを使用して、詳細なレポートの説明を作成できます。</span><span class="sxs-lookup"><span data-stu-id="be691-157">A detailed report description can be created using the edit box at the bottom.</span></span> 
    
### <a name="sparklines-in-tables"></a><span data-ttu-id="be691-158">表のスパークライン</span><span class="sxs-lookup"><span data-stu-id="be691-158">Sparklines in Tables</span></span>

<span data-ttu-id="be691-p113">StartDate.Month をディメンションとして追加し、データを表形式の傾向として表示すると、表のセル内に棒グラフとスパークラインを表示できます。棒グラフまたはスパークライン上にマウス カーソルを移動すると、各月の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="be691-p113">When StartDate.Month is added as a dimension and the data is rendered as a trend in table form, bar charts and sparklines can be shown inside the table cells. Moving the mouse pointer over the bar chart and the sparklines will show values for individual months.</span></span> 
  
![CQD の使用](../../media/fe6b18d7-b8cf-472a-9c93-0f7703f5a700.png)
  
<span data-ttu-id="be691-162">棒グラフとスパークラインが表示されるためには、レポートエディターの上部にある [スパークラインの表示] チェックボックスをオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="be691-162">In order for the bar charts and the sparklines to appear, the "Show sparklines" checkbox at the top of the Report Editor must be checked.</span></span> <span data-ttu-id="be691-163">[近似曲線] オプションを選択し、月を下方に移動して最後の寸法にします。これは、[月] をクリックし、上矢印と下矢印を使用して稼働日を上または下に移動することもできます。</span><span class="sxs-lookup"><span data-stu-id="be691-163">This will select the Trend option and move Month down to be the last dimension, which can also be accomplished by clicking on Month and using the up and down arrows to shift StartDate.Month up or down.</span></span> 
  
### <a name="settings"></a><span data-ttu-id="be691-164">設定</span><span class="sxs-lookup"><span data-stu-id="be691-164">Settings</span></span>

<span data-ttu-id="be691-165">ダッシュボードの右上隅にある設定メニューには、[システム正常性]、[バージョン情報] などの便利なページへのリンクが用意されています。</span><span class="sxs-lookup"><span data-stu-id="be691-165">Located in the top right corner of the dashboard, the settings menu contains links to useful pages like the System Health and About pages.</span></span>
  
![CQD の使用](../../media/0e9ae123-e231-4fea-94e1-5788e8f3e1d3.png)
  
<span data-ttu-id="be691-167">説明とタイムスタンプを個別のユーザーが表示するかどうかにかかわらず、これらの設定は個々のユーザーにのみ影響します。これらの設定は、レポートセットの変更ではなく、他のユーザーに表示されるものではありません。</span><span class="sxs-lookup"><span data-stu-id="be691-167">Whether or not to show descriptions and time stamps is up to individual users, and these settings only affect the individual's version of the dashboard, not does not modify the report set or what other users see.</span></span> <span data-ttu-id="be691-168">キャッシュをクリアすると、すべてのクエリによってキューブからデータが再読み込みされますが、既定値を復元すると、ユーザーが作成または変更したレポートのすべてが削除され、システムレポートセット (ユーザーが初めてログインしたときに表示される内容) が削除されます。</span><span class="sxs-lookup"><span data-stu-id="be691-168">Clearing the cache causes all queries to reload their data from the cube, while restoring defaults deletes all of user-created or modified reports and recreates the system report set — what a user would see when logging in for the first time.</span></span>
  
<span data-ttu-id="be691-169">[ユーザー ダッシュボード リンク] を選択すると、CQD の他のユーザーや、そのレポートを表示できるページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="be691-169">The Users Dashboard Link shows a page where users can view other users of CQD and browse their reports.</span></span> <span data-ttu-id="be691-170">レポート セットを共有する場合は、URL バーのリンクをコピーしてそれを他の CQD ユーザーと共有します。</span><span class="sxs-lookup"><span data-stu-id="be691-170">When sharing a report set, simply copy the link in the URL bar and share it with another CQD user.</span></span> <span data-ttu-id="be691-171">このリンクは、他のユーザーのユーザー名の下にある [ユーザーダッシュボード] リンクページに表示されるものと同じです。</span><span class="sxs-lookup"><span data-stu-id="be691-171">This link will be the same as the one other users would see in the Users Dashboard Link page under the user's username.</span></span>
  
### <a name="supplying-subnet-information"></a><span data-ttu-id="be691-172">サブネット情報の入力</span><span class="sxs-lookup"><span data-stu-id="be691-172">Supplying Subnet Information</span></span>

<span data-ttu-id="be691-173">サイトに固有の情報をアーカイブ データベースに入力してサブネットと建物のマッピング情報 (たとえば、建物ごとのケーブル接続通話または無線通話の品質) を提供すると、別の側面からデータを見ることができます。</span><span class="sxs-lookup"><span data-stu-id="be691-173">Additional insights can be revealed if site-specific information is entered into the Archive database to provide subnet-to-building mapping information (e.g. wired/wireless call quality by building).</span></span> 
  
<span data-ttu-id="be691-174">これらのレポートを作成するには、少なくとも次のテーブルに値を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be691-174">At a minimum, the following tables need to be populated to create these reports:</span></span>
  
- <span data-ttu-id="be691-175">CqdBuilding</span><span class="sxs-lookup"><span data-stu-id="be691-175">CqdBuilding</span></span>
    
- <span data-ttu-id="be691-176">CqdNetwork</span><span class="sxs-lookup"><span data-stu-id="be691-176">CqdNetwork</span></span>
    
<span data-ttu-id="be691-177">追加情報を CqdBuildingType テーブルと CqdBuildingOwnershipType テーブルに入力すると、追加のフィルター処理とドリル ダウンが可能になります。</span><span class="sxs-lookup"><span data-stu-id="be691-177">Additional information can be provided in CqdBuildingType and CqdBuildingOwnershipType tables to allow further filtering and drill-down.</span></span> 
  
<span data-ttu-id="be691-178">これらのテーブルのスキーマは、次のように定義されます。</span><span class="sxs-lookup"><span data-stu-id="be691-178">The schema for these tables are defined as follows:</span></span>
  
<span data-ttu-id="be691-179">**CqdBuilding**</span><span class="sxs-lookup"><span data-stu-id="be691-179">**CqdBuilding**</span></span>

|<span data-ttu-id="be691-180">**列**</span><span class="sxs-lookup"><span data-stu-id="be691-180">**Column**</span></span>|<span data-ttu-id="be691-181">**データ型**</span><span class="sxs-lookup"><span data-stu-id="be691-181">**Data Type**</span></span>|<span data-ttu-id="be691-182">**null を許可**</span><span class="sxs-lookup"><span data-stu-id="be691-182">**Allow Nulls?**</span></span>|<span data-ttu-id="be691-183">**詳細**</span><span class="sxs-lookup"><span data-stu-id="be691-183">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="be691-184">BuildingKey</span><span class="sxs-lookup"><span data-stu-id="be691-184">BuildingKey</span></span>  <br/> |<span data-ttu-id="be691-185">int</span><span class="sxs-lookup"><span data-stu-id="be691-185">int</span></span>  <br/> |<span data-ttu-id="be691-186">いいえ</span><span class="sxs-lookup"><span data-stu-id="be691-186">No</span></span>  <br/> |<span data-ttu-id="be691-187">CqdBuilding テーブルの主キー。</span><span class="sxs-lookup"><span data-stu-id="be691-187">Primary key for the CqdBuilding table.</span></span>  <br/> |
|<span data-ttu-id="be691-188">BuildingName</span><span class="sxs-lookup"><span data-stu-id="be691-188">BuildingName</span></span>  <br/> |<span data-ttu-id="be691-189">varchar(80)</span><span class="sxs-lookup"><span data-stu-id="be691-189">varchar(80)</span></span>  <br/> |<span data-ttu-id="be691-190">いいえ</span><span class="sxs-lookup"><span data-stu-id="be691-190">No</span></span>  <br/> |<span data-ttu-id="be691-191">建物名。</span><span class="sxs-lookup"><span data-stu-id="be691-191">Building name.</span></span>  <br/> |
|<span data-ttu-id="be691-192">BuildingShortName</span><span class="sxs-lookup"><span data-stu-id="be691-192">BuildingShortName</span></span>  <br/> |<span data-ttu-id="be691-193">varchar(10)</span><span class="sxs-lookup"><span data-stu-id="be691-193">varchar(10)</span></span>  <br/> |<span data-ttu-id="be691-194">×</span><span class="sxs-lookup"><span data-stu-id="be691-194">No</span></span>  <br/> |<span data-ttu-id="be691-195">建物の短縮名。</span><span class="sxs-lookup"><span data-stu-id="be691-195">Shorter version of the Building name.</span></span>  <br/> |
|<span data-ttu-id="be691-196">OwnershipTypeId</span><span class="sxs-lookup"><span data-stu-id="be691-196">OwnershipTypeId</span></span>  <br/> |<span data-ttu-id="be691-197">int</span><span class="sxs-lookup"><span data-stu-id="be691-197">int</span></span>  <br/> |<span data-ttu-id="be691-198">いいえ</span><span class="sxs-lookup"><span data-stu-id="be691-198">No</span></span>  <br/> |<span data-ttu-id="be691-199">外部キー。CqdBuildingOwners テーブルのいずれかのエントリに一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be691-199">Foreign key, should match one of the entreis in the CqdBuildingOwners table.</span></span>  <br/> |
|<span data-ttu-id="be691-200">BuildingTypeId</span><span class="sxs-lookup"><span data-stu-id="be691-200">BuildingTypeId</span></span>  <br/> |<span data-ttu-id="be691-201">int</span><span class="sxs-lookup"><span data-stu-id="be691-201">int</span></span>  <br/> |<span data-ttu-id="be691-202">×</span><span class="sxs-lookup"><span data-stu-id="be691-202">No</span></span>  <br/> |<span data-ttu-id="be691-203">外部キー。CqdBuildingType テーブルのいずれかのエントリに一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be691-203">Foreign key, should match one of the entries in the CqdBuildingType table.</span></span>  <br/> |
|<span data-ttu-id="be691-204">Latitutde</span><span class="sxs-lookup"><span data-stu-id="be691-204">Latitutde</span></span>  <br/> |<span data-ttu-id="be691-205">float</span><span class="sxs-lookup"><span data-stu-id="be691-205">float</span></span>  <br/> |<span data-ttu-id="be691-206">はい</span><span class="sxs-lookup"><span data-stu-id="be691-206">Yes</span></span>  <br/> |<span data-ttu-id="be691-207">建物の緯度。</span><span class="sxs-lookup"><span data-stu-id="be691-207">Latitude of the building.</span></span>  <br/> |
|<span data-ttu-id="be691-208">Longitude</span><span class="sxs-lookup"><span data-stu-id="be691-208">Longitude</span></span>  <br/> |<span data-ttu-id="be691-209">float</span><span class="sxs-lookup"><span data-stu-id="be691-209">float</span></span>  <br/> |<span data-ttu-id="be691-210">はい</span><span class="sxs-lookup"><span data-stu-id="be691-210">Yes</span></span>  <br/> |<span data-ttu-id="be691-211">建物の経度。</span><span class="sxs-lookup"><span data-stu-id="be691-211">Longitude of the building.</span></span>  <br/> |
|<span data-ttu-id="be691-212">CityName</span><span class="sxs-lookup"><span data-stu-id="be691-212">CityName</span></span>  <br/> |<span data-ttu-id="be691-213">varchar(30)</span><span class="sxs-lookup"><span data-stu-id="be691-213">varchar(30)</span></span>  <br/> |<span data-ttu-id="be691-214">はい</span><span class="sxs-lookup"><span data-stu-id="be691-214">Yes</span></span>  <br/> |<span data-ttu-id="be691-215">建物がある市区町村の名前。</span><span class="sxs-lookup"><span data-stu-id="be691-215">City name where the building is located.</span></span>  <br/> |
|<span data-ttu-id="be691-216">ZipCode</span><span class="sxs-lookup"><span data-stu-id="be691-216">ZipCode</span></span>  <br/> |<span data-ttu-id="be691-217">varchar(25)</span><span class="sxs-lookup"><span data-stu-id="be691-217">varchar(25)</span></span>  <br/> |<span data-ttu-id="be691-218">○</span><span class="sxs-lookup"><span data-stu-id="be691-218">Yes</span></span>  <br/> |<span data-ttu-id="be691-219">建物がある場所の郵便番号。</span><span class="sxs-lookup"><span data-stu-id="be691-219">Zip code where the building is located.</span></span>  <br/> |
|<span data-ttu-id="be691-220">CountryShortCode</span><span class="sxs-lookup"><span data-stu-id="be691-220">CountryShortCode</span></span>  <br/> |<span data-ttu-id="be691-221">varchar(2)</span><span class="sxs-lookup"><span data-stu-id="be691-221">varchar(2)</span></span>  <br/> |<span data-ttu-id="be691-222">はい</span><span class="sxs-lookup"><span data-stu-id="be691-222">Yes</span></span>  <br/> |<span data-ttu-id="be691-223">建物がある国の ISO 3166-1 alpha-2 コード。</span><span class="sxs-lookup"><span data-stu-id="be691-223">ISO 3166-1 alpha-2 codes for the country where the building is located.</span></span>  <br/> |
|<span data-ttu-id="be691-224">StateProvinceCode</span><span class="sxs-lookup"><span data-stu-id="be691-224">StateProvinceCode</span></span>  <br/> |<span data-ttu-id="be691-225">varchar(3)</span><span class="sxs-lookup"><span data-stu-id="be691-225">varchar(3)</span></span>  <br/> |<span data-ttu-id="be691-226">はい</span><span class="sxs-lookup"><span data-stu-id="be691-226">Yes</span></span>  <br/> |<span data-ttu-id="be691-227">建物がある都道府県の 3 文字の短縮形。</span><span class="sxs-lookup"><span data-stu-id="be691-227">3-letter abbreviation for the State/Province where the building is located.</span></span>  <br/> |
|<span data-ttu-id="be691-228">InsideCorp</span><span class="sxs-lookup"><span data-stu-id="be691-228">InsideCorp</span></span>  <br/> |<span data-ttu-id="be691-229">bit</span><span class="sxs-lookup"><span data-stu-id="be691-229">bit</span></span>  <br/> |<span data-ttu-id="be691-230">はい</span><span class="sxs-lookup"><span data-stu-id="be691-230">Yes</span></span>  <br/> |<span data-ttu-id="be691-231">建物が企業ネットワークの一部であるかどうかを示すビット。</span><span class="sxs-lookup"><span data-stu-id="be691-231">Bit indicating whether the building is part of the corporate network.</span></span>  <br/> |
|<span data-ttu-id="be691-232">BuildingOfficeType</span><span class="sxs-lookup"><span data-stu-id="be691-232">BuildingOfficeType</span></span>  <br/> |<span data-ttu-id="be691-233">nvarchar(150)</span><span class="sxs-lookup"><span data-stu-id="be691-233">nvarchar(150)</span></span>  <br/> |<span data-ttu-id="be691-234">はい</span><span class="sxs-lookup"><span data-stu-id="be691-234">Yes</span></span>  <br/> |<span data-ttu-id="be691-235">オフィス ビルの種類の説明。</span><span class="sxs-lookup"><span data-stu-id="be691-235">Description of the building office type.</span></span>  <br/> |
|<span data-ttu-id="be691-236">Region</span><span class="sxs-lookup"><span data-stu-id="be691-236">Region</span></span>  <br/> |<span data-ttu-id="be691-237">varchar(25)</span><span class="sxs-lookup"><span data-stu-id="be691-237">varchar(25)</span></span>  <br/> |<span data-ttu-id="be691-238">はい</span><span class="sxs-lookup"><span data-stu-id="be691-238">Yes</span></span>  <br/> |<span data-ttu-id="be691-239">建物がある場所のリージョン。</span><span class="sxs-lookup"><span data-stu-id="be691-239">Region where the building is located.</span></span>  <br/> |
   
<span data-ttu-id="be691-240">**CqdNetwork**</span><span class="sxs-lookup"><span data-stu-id="be691-240">**CqdNetwork**</span></span>

|<span data-ttu-id="be691-241">**列**</span><span class="sxs-lookup"><span data-stu-id="be691-241">**Column**</span></span>|<span data-ttu-id="be691-242">**データ型**</span><span class="sxs-lookup"><span data-stu-id="be691-242">**Data Type**</span></span>|<span data-ttu-id="be691-243">**null を許可**</span><span class="sxs-lookup"><span data-stu-id="be691-243">**Allow Nulls?**</span></span>|<span data-ttu-id="be691-244">**詳細**</span><span class="sxs-lookup"><span data-stu-id="be691-244">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="be691-245">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="be691-245">Network</span></span>  <br/> |<span data-ttu-id="be691-246">varchar(25)</span><span class="sxs-lookup"><span data-stu-id="be691-246">varchar(25)</span></span>  <br/> |<span data-ttu-id="be691-247">いいえ</span><span class="sxs-lookup"><span data-stu-id="be691-247">No</span></span>  <br/> |<span data-ttu-id="be691-248">サブネット アドレス。</span><span class="sxs-lookup"><span data-stu-id="be691-248">Subnet address.</span></span>  <br/> |
|<span data-ttu-id="be691-249">NetworkRange</span><span class="sxs-lookup"><span data-stu-id="be691-249">NetworkRange</span></span>  <br/> |<span data-ttu-id="be691-250">tinyint</span><span class="sxs-lookup"><span data-stu-id="be691-250">tinyint</span></span>  <br/> |<span data-ttu-id="be691-251">はい</span><span class="sxs-lookup"><span data-stu-id="be691-251">Yes</span></span>  <br/> |<span data-ttu-id="be691-252">サブネット マスク。</span><span class="sxs-lookup"><span data-stu-id="be691-252">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="be691-253">NetworkNameID</span><span class="sxs-lookup"><span data-stu-id="be691-253">NetworkNameID</span></span>  <br/> |<span data-ttu-id="be691-254">int</span><span class="sxs-lookup"><span data-stu-id="be691-254">int</span></span>  <br/> |<span data-ttu-id="be691-255">はい</span><span class="sxs-lookup"><span data-stu-id="be691-255">Yes</span></span>  <br/> |<span data-ttu-id="be691-256">オプションで CqdNetworkName テーブルの行にマップします。</span><span class="sxs-lookup"><span data-stu-id="be691-256">Optionally maps to a row in CqdNetworkName table.</span></span>  <br/> |
|<span data-ttu-id="be691-257">BuildingKey</span><span class="sxs-lookup"><span data-stu-id="be691-257">BuildingKey</span></span>  <br/> |<span data-ttu-id="be691-258">int</span><span class="sxs-lookup"><span data-stu-id="be691-258">int</span></span>  <br/> |<span data-ttu-id="be691-259">はい</span><span class="sxs-lookup"><span data-stu-id="be691-259">Yes</span></span>  <br/> |<span data-ttu-id="be691-260">外部キー。CqdBuilding テーブルのいずれかのエントリに一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be691-260">Foreign key, should match one of the entries in the CqdBuilding table.</span></span>  <br/> |
|<span data-ttu-id="be691-261">UpdatedDate</span><span class="sxs-lookup"><span data-stu-id="be691-261">UpdatedDate</span></span>  <br/> |<span data-ttu-id="be691-262">datetime</span><span class="sxs-lookup"><span data-stu-id="be691-262">datetime</span></span>  <br/> |<span data-ttu-id="be691-263">いいえ</span><span class="sxs-lookup"><span data-stu-id="be691-263">No</span></span>  <br/> |<span data-ttu-id="be691-264">エントリが最後に更新された日時。</span><span class="sxs-lookup"><span data-stu-id="be691-264">Datetime for when the entry was last updated.</span></span>  <br/> |
   
<span data-ttu-id="be691-265">既定では、次のテーブルには1つのエントリがあります (0, ' Unknown ')。</span><span class="sxs-lookup"><span data-stu-id="be691-265">By default this next table has one entry (0, 'Unknown').</span></span>
  
<span data-ttu-id="be691-266">**CqdBuildingType**</span><span class="sxs-lookup"><span data-stu-id="be691-266">**CqdBuildingType**</span></span>

|<span data-ttu-id="be691-267">**列**</span><span class="sxs-lookup"><span data-stu-id="be691-267">**Column**</span></span>|<span data-ttu-id="be691-268">**データ型**</span><span class="sxs-lookup"><span data-stu-id="be691-268">**Data Type**</span></span>|<span data-ttu-id="be691-269">**null を許可**</span><span class="sxs-lookup"><span data-stu-id="be691-269">**Allow Nulls?**</span></span>|<span data-ttu-id="be691-270">**詳細**</span><span class="sxs-lookup"><span data-stu-id="be691-270">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="be691-271">BuildingTypeId</span><span class="sxs-lookup"><span data-stu-id="be691-271">BuildingTypeId</span></span>  <br/> |<span data-ttu-id="be691-272">int</span><span class="sxs-lookup"><span data-stu-id="be691-272">int</span></span>  <br/> |<span data-ttu-id="be691-273">いいえ</span><span class="sxs-lookup"><span data-stu-id="be691-273">No</span></span>  <br/> |<span data-ttu-id="be691-274">CqdBuildingType テーブルの主キー。</span><span class="sxs-lookup"><span data-stu-id="be691-274">Primary key for the CqdBuildingType table.</span></span>  <br/> |
|<span data-ttu-id="be691-275">BuildingTypeDesc</span><span class="sxs-lookup"><span data-stu-id="be691-275">BuildingTypeDesc</span></span>  <br/> |<span data-ttu-id="be691-276">char(18)</span><span class="sxs-lookup"><span data-stu-id="be691-276">char(18)</span></span>  <br/> |<span data-ttu-id="be691-277">いいえ</span><span class="sxs-lookup"><span data-stu-id="be691-277">No</span></span>  <br/> |<span data-ttu-id="be691-278">建物の種類の説明。</span><span class="sxs-lookup"><span data-stu-id="be691-278">Building type description.</span></span>  <br/> |
   
<span data-ttu-id="be691-279">既定では、次のテーブルには1つのエントリ (0、' Unknown '、0、null) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="be691-279">By default this next table has one entry (0, 'Unknown', 0, null).</span></span>
  
<span data-ttu-id="be691-280">**CqdBuildingOwnershipType**</span><span class="sxs-lookup"><span data-stu-id="be691-280">**CqdBuildingOwnershipType**</span></span>

|<span data-ttu-id="be691-281">**列**</span><span class="sxs-lookup"><span data-stu-id="be691-281">**Column**</span></span>|<span data-ttu-id="be691-282">**データ型**</span><span class="sxs-lookup"><span data-stu-id="be691-282">**Data Type**</span></span>|<span data-ttu-id="be691-283">**null を許可**</span><span class="sxs-lookup"><span data-stu-id="be691-283">**Allow Nulls?**</span></span>|<span data-ttu-id="be691-284">**詳細**</span><span class="sxs-lookup"><span data-stu-id="be691-284">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="be691-285">OwnershipTypeId</span><span class="sxs-lookup"><span data-stu-id="be691-285">OwnershipTypeId</span></span>  <br/> |<span data-ttu-id="be691-286">int</span><span class="sxs-lookup"><span data-stu-id="be691-286">int</span></span>  <br/> |<span data-ttu-id="be691-287">いいえ</span><span class="sxs-lookup"><span data-stu-id="be691-287">No</span></span>  <br/> |<span data-ttu-id="be691-288">CqdBuildingOwnershipType テーブルの主キー。</span><span class="sxs-lookup"><span data-stu-id="be691-288">Primary key for the CqdBuildingOwnershipType table.</span></span>  <br/> |
|<span data-ttu-id="be691-289">OwnershipTypeDesc</span><span class="sxs-lookup"><span data-stu-id="be691-289">OwnershipTypeDesc</span></span>  <br/> |<span data-ttu-id="be691-290">varchar(25)</span><span class="sxs-lookup"><span data-stu-id="be691-290">varchar(25)</span></span>  <br/> |<span data-ttu-id="be691-291">いいえ</span><span class="sxs-lookup"><span data-stu-id="be691-291">No</span></span>  <br/> |<span data-ttu-id="be691-292">所有権の種類の説明。</span><span class="sxs-lookup"><span data-stu-id="be691-292">Ownership type description.</span></span>  <br/> |
|<span data-ttu-id="be691-293">LeaseInd</span><span class="sxs-lookup"><span data-stu-id="be691-293">LeaseInd</span></span>  <br/> |<span data-ttu-id="be691-294">tinyint</span><span class="sxs-lookup"><span data-stu-id="be691-294">tinyint</span></span>  <br/> |<span data-ttu-id="be691-295">はい</span><span class="sxs-lookup"><span data-stu-id="be691-295">Yes</span></span>  <br/> |<span data-ttu-id="be691-296">リースされている建物を識別するために使用される、CqdBuildingOwnershipType テーブル内の別の行を参照するインデックス。</span><span class="sxs-lookup"><span data-stu-id="be691-296">Index referencing another row in the CqdBuildingOwnershipType table, used for identifying leased buildings.</span></span>  <br/> |
|<span data-ttu-id="be691-297">所有者</span><span class="sxs-lookup"><span data-stu-id="be691-297">Owner</span></span>  <br/> |<span data-ttu-id="be691-298">varchar(50)</span><span class="sxs-lookup"><span data-stu-id="be691-298">varchar(50)</span></span>  <br/> |<span data-ttu-id="be691-299">はい</span><span class="sxs-lookup"><span data-stu-id="be691-299">Yes</span></span>  <br/> |<span data-ttu-id="be691-300">建物の所有者。</span><span class="sxs-lookup"><span data-stu-id="be691-300">Building owner.</span></span>  <br/> |
   
<span data-ttu-id="be691-301">既定では、次のテーブルには1つのエントリ (0、' Unknown '、0、null) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="be691-301">By default this next table has one entry (0, 'Unknown', 0, null).</span></span>
  
<span data-ttu-id="be691-302">**CqdBssid**</span><span class="sxs-lookup"><span data-stu-id="be691-302">**CqdBssid**</span></span>

|<span data-ttu-id="be691-303">**列**</span><span class="sxs-lookup"><span data-stu-id="be691-303">**Column**</span></span>|<span data-ttu-id="be691-304">**データ型**</span><span class="sxs-lookup"><span data-stu-id="be691-304">**Data Type**</span></span>|<span data-ttu-id="be691-305">**null を許可**</span><span class="sxs-lookup"><span data-stu-id="be691-305">**Allow Nulls?**</span></span>|<span data-ttu-id="be691-306">**詳細**</span><span class="sxs-lookup"><span data-stu-id="be691-306">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="be691-307">bss</span><span class="sxs-lookup"><span data-stu-id="be691-307">bss</span></span>  <br/> |<span data-ttu-id="be691-308">nvarchar(50)</span><span class="sxs-lookup"><span data-stu-id="be691-308">nvarchar(50)</span></span>  <br/> |<span data-ttu-id="be691-309">×</span><span class="sxs-lookup"><span data-stu-id="be691-309">No</span></span>  <br/> |<span data-ttu-id="be691-p117">CqdBssid テーブルの主キー。Wifi アクセス ポイントの BSSID。</span><span class="sxs-lookup"><span data-stu-id="be691-p117">Primary key for the CqdBssid table. Is the BSSID of the Wifi Access Point.</span></span>  <br/> |
|<span data-ttu-id="be691-312">ess</span><span class="sxs-lookup"><span data-stu-id="be691-312">ess</span></span>  <br/> |<span data-ttu-id="be691-313">nvarchar(50)</span><span class="sxs-lookup"><span data-stu-id="be691-313">nvarchar(50)</span></span>  <br/> |<span data-ttu-id="be691-314">○</span><span class="sxs-lookup"><span data-stu-id="be691-314">Yes</span></span>  <br/> |<span data-ttu-id="be691-315">Wifi アクセス ポイント コントローラーの情報。</span><span class="sxs-lookup"><span data-stu-id="be691-315">Wifi Access Point Controller information.</span></span>  <br/> |
|<span data-ttu-id="be691-316">phy</span><span class="sxs-lookup"><span data-stu-id="be691-316">phy</span></span>  <br/> |<span data-ttu-id="be691-317">nvarchar(50)</span><span class="sxs-lookup"><span data-stu-id="be691-317">nvarchar(50)</span></span>  <br/> |<span data-ttu-id="be691-318">○</span><span class="sxs-lookup"><span data-stu-id="be691-318">Yes</span></span>  <br/> |<span data-ttu-id="be691-319">Phy 情報。</span><span class="sxs-lookup"><span data-stu-id="be691-319">Phy information.</span></span>  <br/> |
|<span data-ttu-id="be691-320">ap</span><span class="sxs-lookup"><span data-stu-id="be691-320">ap</span></span>  <br/> |<span data-ttu-id="be691-321">nvarchar(50)</span><span class="sxs-lookup"><span data-stu-id="be691-321">nvarchar(50)</span></span>  <br/> |<span data-ttu-id="be691-322">○</span><span class="sxs-lookup"><span data-stu-id="be691-322">Yes</span></span>  <br/> |<span data-ttu-id="be691-323">Wifi アクセス ポイント名。</span><span class="sxs-lookup"><span data-stu-id="be691-323">Wifi Access Point Name.</span></span>  <br/> |
|<span data-ttu-id="be691-324">建物</span><span class="sxs-lookup"><span data-stu-id="be691-324">Building</span></span>  <br/> |<span data-ttu-id="be691-325">nvarchar(500)</span><span class="sxs-lookup"><span data-stu-id="be691-325">nvarchar(500)</span></span>  <br/> |<span data-ttu-id="be691-326">○</span><span class="sxs-lookup"><span data-stu-id="be691-326">Yes</span></span>  <br/> |<span data-ttu-id="be691-327">Wifi アクセス ポイントが配置されている建物名。</span><span class="sxs-lookup"><span data-stu-id="be691-327">The Building Name the Wifi Access Point is located in.</span></span>  <br/> |
   
## <a name="cqd-streams"></a><span data-ttu-id="be691-328">CQD ストリーム</span><span class="sxs-lookup"><span data-stu-id="be691-328">CQD Streams</span></span>

<span data-ttu-id="be691-p118">CQD ストリームは良好、不良、または未分類となります。CQM 1.5 は次の CQD 定義を使用するようになりました。</span><span class="sxs-lookup"><span data-stu-id="be691-p118">A CQD stream will be good, poor or unclassified. CQM 1.5 now uses the following CQD definition:</span></span> 
  
- <span data-ttu-id="be691-331">不良ストリームは、しきい値を超えている低品質通話の指標の組み合わせになります。</span><span class="sxs-lookup"><span data-stu-id="be691-331">A poor stream is any combination of the poor call metrics going beyond threshold.</span></span>
    
- <span data-ttu-id="be691-332">通話中の1つのストリームの品質が悪い場合、通話の両方のストリームのフラグが低品質になります。</span><span class="sxs-lookup"><span data-stu-id="be691-332">When one stream in a call is poor, both streams of the call are flagged poor.</span></span> <span data-ttu-id="be691-333">会議では、参加者はそれぞれ固有の通話としてカウントされ、他の参加者と個別に報告されます。</span><span class="sxs-lookup"><span data-stu-id="be691-333">In conferences, each participant is counted as a unique call and is reported on independently of all others.</span></span>
    
- <span data-ttu-id="be691-334">未分類のストリームは、品質の指標がないストリーム (代理トランザクション、短い通話など) です。</span><span class="sxs-lookup"><span data-stu-id="be691-334">Unclassified streams are streams without quality metrics (i.e. Synthetic Transactions, short calls).</span></span>
    
- <span data-ttu-id="be691-335">有効なストリーム = 非モバイル クライアント</span><span class="sxs-lookup"><span data-stu-id="be691-335">Valid Streams = non-mobile clients</span></span>
    
- <span data-ttu-id="be691-336">分類子は変更できません</span><span class="sxs-lookup"><span data-stu-id="be691-336">Classifier cannot be modified</span></span>
    
<span data-ttu-id="be691-337">**低品質通話の定義/分類子**</span><span class="sxs-lookup"><span data-stu-id="be691-337">**Poor call definition/classifier**</span></span>

|<span data-ttu-id="be691-338">**指標**</span><span class="sxs-lookup"><span data-stu-id="be691-338">**Metric**</span></span>|<span data-ttu-id="be691-339">**しきい値**</span><span class="sxs-lookup"><span data-stu-id="be691-339">**Threshold**</span></span>|
|:-----|:-----|
|<span data-ttu-id="be691-340">DDegradationAvg</span><span class="sxs-lookup"><span data-stu-id="be691-340">DDegradationAvg</span></span>  <br/> |<span data-ttu-id="be691-341">1.0 (-1 ネットワーク MOS) より大きい</span><span class="sxs-lookup"><span data-stu-id="be691-341">Greater than 1.0 (-1 network MOS)</span></span>  <br/> |
|<span data-ttu-id="be691-342">RoundTrip</span><span class="sxs-lookup"><span data-stu-id="be691-342">RoundTrip</span></span>  <br/> |<span data-ttu-id="be691-343">500 より大きい </span><span class="sxs-lookup"><span data-stu-id="be691-343">Greater than 500</span></span>  <br/> |
|<span data-ttu-id="be691-344">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="be691-344">PacketLossRate</span></span>  <br/> |<span data-ttu-id="be691-345">0.1 (10%) より大きい </span><span class="sxs-lookup"><span data-stu-id="be691-345">Greater than .1 (10%)</span></span>  <br/> |
|<span data-ttu-id="be691-346">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="be691-346">JitterInterArrival</span></span>  <br/> |<span data-ttu-id="be691-347">30 より大きい </span><span class="sxs-lookup"><span data-stu-id="be691-347">Greater than 30</span></span>  <br/> |
|<span data-ttu-id="be691-348">RRatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="be691-348">RRatioConcealedSamplesAvg</span></span>  <br/> |<span data-ttu-id="be691-349">0.07 より大きい </span><span class="sxs-lookup"><span data-stu-id="be691-349">Greater than .07</span></span>  <br/> |
   
<span data-ttu-id="be691-350">JPDR 定義 = 低品質通話の定義 - RatioConcealedSamplesAvg </span><span class="sxs-lookup"><span data-stu-id="be691-350">JPDR definition = Poor call definition minus RatioConcealedSamplesAvg</span></span> 
  
## <a name="where-is-callercallee"></a><span data-ttu-id="be691-351">呼び出し元/呼び出し先の場所</span><span class="sxs-lookup"><span data-stu-id="be691-351">Where is Caller/Callee?</span></span>

<span data-ttu-id="be691-352">CQD では、発信者番号と呼び出し先のフィールドは使用されません。</span><span class="sxs-lookup"><span data-stu-id="be691-352">CQD doesn't use Caller/Callee fields.</span></span> <span data-ttu-id="be691-353">これらの名前は、"First" と "Second" の名前が変更されました。これは、呼び出し元と呼び出し先の間に手順が介在しているためです。</span><span class="sxs-lookup"><span data-stu-id="be691-353">These have been renamed "First" and "Second" because there are intervening steps between the caller and callee.</span></span>
  
 <span data-ttu-id="be691-354">**1 番目** サーバーがストリーム内に関与している場合は常にサーバーのエンドポイントになります (AV MCU、仲介サーバー)。</span><span class="sxs-lookup"><span data-stu-id="be691-354">**First** Will always be the Server endpoint (e.g. AV MCU; Mediation Server) if a Server is involved in the stream.</span></span>
  
 <span data-ttu-id="be691-355">**2 番目** サーバー間のストリームでない限り、常にクライアントのエンドポイントになります。</span><span class="sxs-lookup"><span data-stu-id="be691-355">**Second** Will always be the Client endpoint, unless it is a Server-Server stream.</span></span>
  
<span data-ttu-id="be691-356">**1 番目と 2 番目の分類の例**</span><span class="sxs-lookup"><span data-stu-id="be691-356">**Example of First and Second classification**</span></span>

|<span data-ttu-id="be691-357">\*\*エンドポイント 1 UAType \*\*</span><span class="sxs-lookup"><span data-stu-id="be691-357">**Endpoint 1 UAType**</span></span>|<span data-ttu-id="be691-358">\*\*エンドポイント 2 UUAType \*\*</span><span class="sxs-lookup"><span data-stu-id="be691-358">**Endpoint 2 UUAType**</span></span>|<span data-ttu-id="be691-359">**1 番目**</span><span class="sxs-lookup"><span data-stu-id="be691-359">**First**</span></span>|<span data-ttu-id="be691-360">**2 番目**</span><span class="sxs-lookup"><span data-stu-id="be691-360">**Second**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="be691-361">2 (AVMCU) </span><span class="sxs-lookup"><span data-stu-id="be691-361">2 (AVMCU)</span></span>  <br/> |<span data-ttu-id="be691-362">4 (Skype for Business) </span><span class="sxs-lookup"><span data-stu-id="be691-362">4 (Skype for Business)</span></span>  <br/> |<span data-ttu-id="be691-363">エンドポイント 1</span><span class="sxs-lookup"><span data-stu-id="be691-363">Endpoint 1</span></span>  <br/> |<span data-ttu-id="be691-364">エンドポイント 2</span><span class="sxs-lookup"><span data-stu-id="be691-364">Endpoint 2</span></span>  <br/> |
|<span data-ttu-id="be691-365">2 (AVMCU) </span><span class="sxs-lookup"><span data-stu-id="be691-365">2 (AVMCU)</span></span>  <br/> |<span data-ttu-id="be691-366">1 (mMediationServer) </span><span class="sxs-lookup"><span data-stu-id="be691-366">1 (mMediationServer)</span></span>  <br/> |<span data-ttu-id="be691-367">エンドポイント 2</span><span class="sxs-lookup"><span data-stu-id="be691-367">Endpoint 2</span></span>  <br/> |<span data-ttu-id="be691-368">エンドポイント 1</span><span class="sxs-lookup"><span data-stu-id="be691-368">Endpoint 1</span></span>  <br/> |
|<span data-ttu-id="be691-369">4 (Skype for Business)</span><span class="sxs-lookup"><span data-stu-id="be691-369">4 (Skype for Business)</span></span>  <br/> |<span data-ttu-id="be691-370">4 (Skype for Business) </span><span class="sxs-lookup"><span data-stu-id="be691-370">4 (Skype for Business)</span></span>  <br/> |<span data-ttu-id="be691-371">MediaLine での呼び出し元 </span><span class="sxs-lookup"><span data-stu-id="be691-371">The Caller in MediaLine</span></span>  <br/> |<span data-ttu-id="be691-372">MMediaLine での呼び出し先</span><span class="sxs-lookup"><span data-stu-id="be691-372">The Callee in MMediaLine</span></span>  <br/> |
   
<span data-ttu-id="be691-373">両方のエンドポイントが同じ種類の場合、CQD は呼び出し元のエントリを 1 番目にして、呼び出し先を 2 番目にします。</span><span class="sxs-lookup"><span data-stu-id="be691-373">If both endpoints are the same type, CQD will make the Caller entry First and Callee will become Second.</span></span> <span data-ttu-id="be691-374">詳細については、[このブログ](https://blogs.technet.com/b/jenstr/archive/2015/05/22/call-quality-dashboard-tips-and-tricks.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be691-374">See [this blog](https://blogs.technet.com/b/jenstr/archive/2015/05/22/call-quality-dashboard-tips-and-tricks.aspx) for more information.</span></span>
  
## <a name="accounting-for-vpn"></a><span data-ttu-id="be691-375">VPN のアカウンティング</span><span class="sxs-lookup"><span data-stu-id="be691-375">Accounting for VPN</span></span>

<span data-ttu-id="be691-376">VPN ソリューションで VPN フラグが正しく設定されていることがわかっている場合は、すべて設定されています。</span><span class="sxs-lookup"><span data-stu-id="be691-376">If VPN solution is known to accurately set VPN flag, you're all set.</span></span> <span data-ttu-id="be691-377">そうでない場合は、以下の方法のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="be691-377">Otherwise, use one of the methods below:</span></span>
  
- <span data-ttu-id="be691-378">VPN というネットワークの種類を作成 (推奨) して、VPN サブネットをこの新しいネットワークの種類の VPN に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="be691-378">Create a Network Type called VPN (preferred), then Associate VPN Subnets with this new VPN NetworkType.</span></span>
    
- <span data-ttu-id="be691-379">VPN という建物を作成して、その建物に VPN サブネットを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="be691-379">Create a building called VPN, then Associate VPN Subnets with this building.</span></span> 
    
## <a name="query-fundamentals"></a><span data-ttu-id="be691-380">クエリーの基本事項</span><span class="sxs-lookup"><span data-stu-id="be691-380">Query Fundamentals</span></span>

<span data-ttu-id="be691-381">正しい形式のクエリーには、次の 3 つのパラメーターがすべて含まれます。</span><span class="sxs-lookup"><span data-stu-id="be691-381">A well-formed query contains all three of these parameters:</span></span> 
  
- <span data-ttu-id="be691-382">測定</span><span class="sxs-lookup"><span data-stu-id="be691-382">Measurement</span></span>
    
- <span data-ttu-id="be691-383">ディメンション</span><span class="sxs-lookup"><span data-stu-id="be691-383">Dimension</span></span>
    
- <span data-ttu-id="be691-384">フィルター</span><span class="sxs-lookup"><span data-stu-id="be691-384">Filter</span></span>
    
<span data-ttu-id="be691-385">正しい形式のクエリーの例は、「建物 6 [フィルター] のサブネット [ディメンション] ごとに不良ストリーム [測定] を表示してください。」のようになります</span><span class="sxs-lookup"><span data-stu-id="be691-385">An example of a well-formed query would be "Show me Poor Streams [Measurement] by Subnet [Dimension] for Building 6 [Filter]."</span></span>
  
## <a name="what-does-union-do"></a><span data-ttu-id="be691-386">UNION で行えること</span><span class="sxs-lookup"><span data-stu-id="be691-386">What does UNION do?</span></span>

<span data-ttu-id="be691-p123">Union は、AND 演算子を使って条件をフィルターすることができます。OR like での結果を得るために複数のフィルター条件を組み合わせる必要があるシナリオが考えられます。</span><span class="sxs-lookup"><span data-stu-id="be691-p123">Union allows you to filter conditions using the AND operator. There are scenarios where you need to combine multiple Filter conditions together to achieve an OR like result</span></span>
  
<span data-ttu-id="be691-p124">例: 建物からのすべてのストリームを取得する必要がある場合に、UNION は結合したデータセットを別個に表示できます。UNION を使用するには、統合 (UNION) したい 2 つのフィルターについて、UNION フィールドに一般的なテキストを挿入します。</span><span class="sxs-lookup"><span data-stu-id="be691-p124">Example: When you need to get all streams from a building UNION will provide a distinct view of the merged dataset. To use the UNION, insert common text into the UNION field on the two filter conditions you want to UNION.</span></span> 
  
## <a name="default-report-breakdown"></a><span data-ttu-id="be691-391">既定のレポートの詳細</span><span class="sxs-lookup"><span data-stu-id="be691-391">Default Report Breakdown</span></span>

<span data-ttu-id="be691-392">ワイヤレスが内部で管理されている場合、管理されたバケットでワイヤレス レポートを再作成できます。</span><span class="sxs-lookup"><span data-stu-id="be691-392">If Wireless is managed internally, you can recreate the Wireless reports in the Managed bucket.</span></span> 
  
![CQD レポートの詳細](../../media/658b8568-0d68-4f5f-83e8-5abc63a85c1d.png)
  
## <a name="operational-processes"></a><span data-ttu-id="be691-394">運用プロセス</span><span class="sxs-lookup"><span data-stu-id="be691-394">Operational Processes</span></span>

<span data-ttu-id="be691-p125">管理されたストリームのレビューおよび修復によって開始します。この領域の品質は管理下で 100% となるべきものであるため、修復するのが最も簡単になります。</span><span class="sxs-lookup"><span data-stu-id="be691-p125">Start by reviewing and remediating Managed Streams. Quality in this area should be 100% within your control and therefore easiest to remediate.</span></span> 
  
### <a name="managed-streams"></a><span data-ttu-id="be691-397">管理されたストリーム </span><span class="sxs-lookup"><span data-stu-id="be691-397">Managed Streams</span></span>

<span data-ttu-id="be691-398">次の順に管理されたストリームをレビューおよび修復します。</span><span class="sxs-lookup"><span data-stu-id="be691-398">Review and remediate managed streams in the following order:</span></span> 
  
1. <span data-ttu-id="be691-399">サーバー間 </span><span class="sxs-lookup"><span data-stu-id="be691-399">Server-Server</span></span> 
    
2.  <span data-ttu-id="be691-400"> サーバーと有線 (内部)</span><span class="sxs-lookup"><span data-stu-id="be691-400">Server-Wired-Inside</span></span>
    
3. <span data-ttu-id="be691-401">有線と有線 (内部) </span><span class="sxs-lookup"><span data-stu-id="be691-401">Wired-Wired-Inside</span></span> 
    
### <a name="unmanaged-streams"></a><span data-ttu-id="be691-402">管理されていないストリーム</span><span class="sxs-lookup"><span data-stu-id="be691-402">Unmanaged Streams</span></span>

<span data-ttu-id="be691-403">次の順に管理されていないストリームをレビューおよび修復します。</span><span class="sxs-lookup"><span data-stu-id="be691-403">Review and remediate unmanaged streams in the following order:</span></span> 
  
1. <span data-ttu-id="be691-404">サーバーと Wifi (内部)</span><span class="sxs-lookup"><span data-stu-id="be691-404">Server-Wifi-Inside</span></span>
    
2. <span data-ttu-id="be691-405">サーバーと有線 (外部)</span><span class="sxs-lookup"><span data-stu-id="be691-405">Server-Wired-Outside</span></span>
    
3. <span data-ttu-id="be691-406">サーバーと Wifi (外部)</span><span class="sxs-lookup"><span data-stu-id="be691-406">Server-Wifi-Outside</span></span>
    
4. <span data-ttu-id="be691-407">有線 (外部) とダイレクト</span><span class="sxs-lookup"><span data-stu-id="be691-407">Wired-Outside-Direct</span></span>
    
5. <span data-ttu-id="be691-408">有線 (外部) とリレー</span><span class="sxs-lookup"><span data-stu-id="be691-408">Wired-Outside-Relay</span></span>
    
6. <span data-ttu-id="be691-409">その他の管理されていないもの</span><span class="sxs-lookup"><span data-stu-id="be691-409">Other Unmanaged</span></span>
    

