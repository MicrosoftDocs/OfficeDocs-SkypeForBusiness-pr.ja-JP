---
title: 通話品質ダッシュボード (CQD) のデータとレポート
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Microsoft 通話品質ダッシュボード (CQD) で利用できるデータとレポートについて説明します。
ms.openlocfilehash: ec9714e0eae187bc82edf01809b50d8512d04e01
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583094"
---
# <a name="data-and-reports-in-call-quality-dashboard-cqd"></a><span data-ttu-id="354ae-103">通話品質ダッシュボード (CQD) のデータとレポート</span><span class="sxs-lookup"><span data-stu-id="354ae-103">Data and reports in Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="354ae-104">Microsoft 通話品質ダッシュボード (CQD) は、near リアルタイム (NRT) データフィードを使用します。</span><span class="sxs-lookup"><span data-stu-id="354ae-104">Microsoft Call Quality Dashboard (CQD) uses a near-real-time (NRT) data feed.</span></span> <span data-ttu-id="354ae-105">通話記録は、通話の終了後30分以内に CQD で利用できます。</span><span class="sxs-lookup"><span data-stu-id="354ae-105">Call records are available in CQD within 30 minutes of the end of a call.</span></span> <span data-ttu-id="354ae-106">NRT パイプラインからの通話レコードは、データセットから削除されるまで数ヶ月分しか使用できません。</span><span class="sxs-lookup"><span data-stu-id="354ae-106">Call records from the NRT pipeline are only available for a few months before they are removed from the data set.</span></span> 


## <a name="many-ways-to-access-cqd-data"></a><span data-ttu-id="354ae-107">CQD データにアクセスするさまざまな方法</span><span class="sxs-lookup"><span data-stu-id="354ae-107">Many ways to access CQD data</span></span>

<span data-ttu-id="354ae-108">複数の異なる方法で CQD データにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="354ae-108">You can access CQD data by several different avenues.</span></span> <span data-ttu-id="354ae-109">ニーズに最も合ったものを選択してください。</span><span class="sxs-lookup"><span data-stu-id="354ae-109">Pick the one that best meets your needs:</span></span>

|  |  |
|---------|---------|
|<span data-ttu-id="354ae-110">Teams 管理センター [( https://admin.teams.microsoft.com) ](https://admin.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="354ae-110">Teams admin center [(https://admin.teams.microsoft.com)](https://admin.teams.microsoft.com)</span></span>    | <span data-ttu-id="354ae-111">CQD データは Teams 管理センターの [**ユーザー** ] ページに含まれており、必要なデータが読みやすい形式で表示されています。</span><span class="sxs-lookup"><span data-stu-id="354ae-111">CQD data is included on the **Users** page in the Teams admin center, showing the most common data you need in an easy-to-read format.</span></span> <span data-ttu-id="354ae-112">[**ユーザー**] で見つかった CQD データはカスタマイズできません。</span><span class="sxs-lookup"><span data-stu-id="354ae-112">You can't customize CQD data that you find under **Users**.</span></span>  |
|<span data-ttu-id="354ae-113">CQD ポータル[( https://cqd.teams.microsoft.com) ](https://cqd.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="354ae-113">CQD portal [(https://cqd.teams.microsoft.com)](https://cqd.teams.microsoft.com)</span></span>     | <span data-ttu-id="354ae-114">ドリルスルーフィルター機能を使用して、ほとんどのニーズを満たす信頼性の高い概要と詳細なレポート。</span><span class="sxs-lookup"><span data-stu-id="354ae-114">Robust summary and detailed reports that meet most needs, with drill-through filtering.</span></span> <span data-ttu-id="354ae-115">CQD ポータルでレポートをカスタマイズすることもできます。</span><span class="sxs-lookup"><span data-stu-id="354ae-115">You can also customize reports in the CQD portal.</span></span> <br><br><span data-ttu-id="354ae-116">CQD ポータルでデータを分析するための2つの[CQD レポートテンプレート](#import-the-cqd-report-templates)を取得します。</span><span class="sxs-lookup"><span data-stu-id="354ae-116">Get two [CQD report templates](#import-the-cqd-report-templates) to help you analyze data in the CQD portal.</span></span>       |
|<span data-ttu-id="354ae-117">Power BI</span><span class="sxs-lookup"><span data-stu-id="354ae-117">Power BI</span></span>     | <span data-ttu-id="354ae-118">[カスタマイズ可能な POWER bi テンプレート](CQD-Power-BI-query-templates.md)を使用して、CQD データを power bi で表示するには、ダイレクトクエリを使います。</span><span class="sxs-lookup"><span data-stu-id="354ae-118">Use direct queries to view your CQD data in Power BI using [customizable Power BI templates](CQD-Power-BI-query-templates.md).</span></span> <span data-ttu-id="354ae-119">[CQD の POWER BI クエリテンプレートをダウンロード](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)します。</span><span class="sxs-lookup"><span data-stu-id="354ae-119">[Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span><br><br><span data-ttu-id="354ae-120">また、REST API を使用して、Power BI で[CQD データにアクセスする](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/data-api)こともできます。</span><span class="sxs-lookup"><span data-stu-id="354ae-120">You can also [use the REST API to access CQD data](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/data-api) through Power BI.</span></span> <span data-ttu-id="354ae-121">CQD データをダウンロードしてオフラインで作業できるようにする場合は、この方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="354ae-121">Use this method if you want to download your CQD data so you can work on it offline.</span></span> <span data-ttu-id="354ae-122">この方法を使用するとパフォーマンスが向上します。特に、オンラインの場合は、Power BI で bog されていない大きなデータセットに適しています。</span><span class="sxs-lookup"><span data-stu-id="354ae-122">The benefit of using this method is better performance, especially useful for large data sets that bog down in Power BI when you're online.</span></span>       |
|<span data-ttu-id="354ae-123">Graph API</span><span class="sxs-lookup"><span data-stu-id="354ae-123">Graph API</span></span>     | <span data-ttu-id="354ae-124">[GRAPH API](https://docs.microsoft.com/graph/api/resources/callrecords-api-overview?view=graph-rest-beta)を使用して、自分で通話品質データにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="354ae-124">Access call quality data yourself using the [Graph API](https://docs.microsoft.com/graph/api/resources/callrecords-api-overview?view=graph-rest-beta).</span></span> <span data-ttu-id="354ae-125">これは最も複雑な方法ですが、通話品質データを分析するのに最適なコントロールと柔軟性を提供します。</span><span class="sxs-lookup"><span data-stu-id="354ae-125">This is the most complex method, but it gives you the most control and flexibility in analyzing your call quality data.</span></span> <span data-ttu-id="354ae-126">たとえば、組織の他のデータに参加する必要がある場合は、Graph API を使ってデータモデルを作成し、通話品質データを組み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="354ae-126">For example, if you need to join it with other data for your organization, you can use the Graph API to create a data model and incorporate call quality data.</span></span>        |

## <a name="import-the-cqd-report-templates"></a><span data-ttu-id="354ae-127">CQD レポートテンプレートをインポートする</span><span class="sxs-lookup"><span data-stu-id="354ae-127">Import the CQD report templates</span></span>

<span data-ttu-id="354ae-128">CQD ですばやく作業を開始できるように、 [2 つの CURATED CQD レポートテンプレート](https://aka.ms/qertemplates)(すべてのネットワークと管理されたネットワーク) をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="354ae-128">Download [two curated CQD report templates](https://aka.ms/qertemplates) (All Networks and Managed Networks) to help you get up to speed quickly with CQD.</span></span> <span data-ttu-id="354ae-129">建物のデータファイルを操作するために最適化された [すべてのネットワーク] テンプレートは、次のセクションで説明するように、建物情報を収集して CQD にアップロードするときに使用できます。</span><span class="sxs-lookup"><span data-stu-id="354ae-129">The All Networks template, though optimized to work with a building data file, can be used while you work toward collecting and uploading building information into CQD, as described in the next section.</span></span>

<span data-ttu-id="354ae-130">**テンプレートをインポートするには (.CQDX) を CQD**</span><span class="sxs-lookup"><span data-stu-id="354ae-130">**To import the templates (.CQDX) into CQD**</span></span>

1. <span data-ttu-id="354ae-131">CQD で、ページの上部にあるメニューから [**詳細レポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="354ae-131">In CQD, select **Detailed Reports** from the menu at the top of the page.</span></span>

2. <span data-ttu-id="354ae-132">左側のパネルで、[**インポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="354ae-132">In the left panel, select **Import**.</span></span> <span data-ttu-id="354ae-133">1つ目の CQDX テンプレートを参照し、[**開く**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="354ae-133">Browse to the first CQDX template and select **Open**.</span></span>

3. <span data-ttu-id="354ae-134">テンプレートがアップロードされると、ポップアップウィンドウに "レポートのインポートが成功しました。" というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="354ae-134">After the template is uploaded, a pop-up window will display the message "Report import was successful."</span></span> 

4. <span data-ttu-id="354ae-135">2番目の CQD テンプレートについて、手順2と3を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="354ae-135">Repeat steps 2 and 3 for the second CQD template.</span></span>

> [!NOTE]
> <span data-ttu-id="354ae-136">各ユーザーは、CQD テンプレートを CQD インスタンスにインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="354ae-136">Each user must import the CQD templates into their CQD instance.</span></span> 



## <a name="euii-data"></a><span data-ttu-id="354ae-137">EUII データ</span><span class="sxs-lookup"><span data-stu-id="354ae-137">EUII data</span></span>

<span data-ttu-id="354ae-138">コンプライアンス上の理由から、エンドユーザーを特定できる情報 (EUII) データ (個人を特定できる情報または PII とも呼ばれます) は、30日間のみ保持されます。</span><span class="sxs-lookup"><span data-stu-id="354ae-138">For compliance reasons, end-user identifiable information (EUII) data (also known as personally-identifiable information or PII) is only kept for 30 days.</span></span> <span data-ttu-id="354ae-139">NRT データは、30日間のマークと交差するため、EUII を含むフィールドは消去され、EUII-free NRT データが生成されます。</span><span class="sxs-lookup"><span data-stu-id="354ae-139">As NRT data crosses the 30-day mark, fields that contain EUII are cleared, resulting in EUII-free NRT data.</span></span> <span data-ttu-id="354ae-140">EUII データを含むフィールドは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="354ae-140">Fields that contain EUII data are:</span></span>

- <span data-ttu-id="354ae-141">完全な IP アドレス</span><span class="sxs-lookup"><span data-stu-id="354ae-141">Full IP address</span></span>
- <span data-ttu-id="354ae-142">メディアアクセス制御 (MAC) アドレス</span><span class="sxs-lookup"><span data-stu-id="354ae-142">Media Access Control (MAC) Address</span></span>
- <span data-ttu-id="354ae-143">基本サービスセット識別子 (BSSID)</span><span class="sxs-lookup"><span data-stu-id="354ae-143">Basic Service Set identifier (BSSID)</span></span>
- <span data-ttu-id="354ae-144">セッション開始プロトコル (SIP) URI (Skype for Business のみ)</span><span class="sxs-lookup"><span data-stu-id="354ae-144">Session Initiation Protocol (SIP) URI (Skype for Business only)</span></span>
- <span data-ttu-id="354ae-145">ユーザー プリンシパル名 (UPN)</span><span class="sxs-lookup"><span data-stu-id="354ae-145">User Principal Name (UPN)</span></span>
- <span data-ttu-id="354ae-146">マシンのエンドポイント名</span><span class="sxs-lookup"><span data-stu-id="354ae-146">Machine Endpoint Name</span></span>
- <span data-ttu-id="354ae-147">ユーザーからのフィードバック</span><span class="sxs-lookup"><span data-stu-id="354ae-147">User Verbatim Feedback</span></span>
- <span data-ttu-id="354ae-148">オブジェクト ID (エンドポイントのユーザーの Active Directory オブジェクト ID)</span><span class="sxs-lookup"><span data-stu-id="354ae-148">Object ID (the Active Directory object ID of the endpoint's user)</span></span>

### <a name="admin-roles-with-and-without-euii-access"></a><span data-ttu-id="354ae-149">EUII access を含む、または持たない管理者の役割</span><span class="sxs-lookup"><span data-stu-id="354ae-149">Admin roles with and without EUII access</span></span>

<span data-ttu-id="354ae-150">この[RBAC](https://docs.microsoft.com/azure/role-based-access-control/overview)ロール**には、** 次のような euii アクセスがあります。</span><span class="sxs-lookup"><span data-stu-id="354ae-150">These [RBAC](https://docs.microsoft.com/azure/role-based-access-control/overview) roles **DO** have EUII access:</span></span>
- <span data-ttu-id="354ae-151">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="354ae-151">Global Admin</span></span>
- <span data-ttu-id="354ae-152">Teams サービス管理者</span><span class="sxs-lookup"><span data-stu-id="354ae-152">Teams Service Admin</span></span>
- <span data-ttu-id="354ae-153">Teams のコミュニケーション管理者</span><span class="sxs-lookup"><span data-stu-id="354ae-153">Teams Communications Admin</span></span>
- <span data-ttu-id="354ae-154">Teams 通信サポート エンジニア</span><span class="sxs-lookup"><span data-stu-id="354ae-154">Teams Communications Support Engineer</span></span>
- <span data-ttu-id="354ae-155">グローバルリーダー</span><span class="sxs-lookup"><span data-stu-id="354ae-155">Global Reader</span></span>
- <span data-ttu-id="354ae-156">Skype for Business 管理者</span><span class="sxs-lookup"><span data-stu-id="354ae-156">Skype for Business Admin</span></span>

<span data-ttu-id="354ae-157">これらの RBAC ロールには、EUII アクセスがあり**ません**。</span><span class="sxs-lookup"><span data-stu-id="354ae-157">These RBAC roles **DON'T** have EUII access:</span></span>
- <span data-ttu-id="354ae-158">レポートリーダー</span><span class="sxs-lookup"><span data-stu-id="354ae-158">Reports Reader</span></span>
- <span data-ttu-id="354ae-159">Teams 通信サポート スペシャリスト</span><span class="sxs-lookup"><span data-stu-id="354ae-159">Teams Communications Support Specialist</span></span>


## <a name="date-controls"></a><span data-ttu-id="354ae-160">日付コントロール</span><span class="sxs-lookup"><span data-stu-id="354ae-160">Date controls</span></span>

<span data-ttu-id="354ae-161">CQD は、次のローリング傾向の型をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="354ae-161">CQD supports the following Rolling Trend types:</span></span>

- <span data-ttu-id="354ae-162">5日</span><span class="sxs-lookup"><span data-stu-id="354ae-162">5-day</span></span>
- <span data-ttu-id="354ae-163">7日間</span><span class="sxs-lookup"><span data-stu-id="354ae-163">7-day</span></span>
- <span data-ttu-id="354ae-164">30日間</span><span class="sxs-lookup"><span data-stu-id="354ae-164">30-day</span></span>
- <span data-ttu-id="354ae-165">60日</span><span class="sxs-lookup"><span data-stu-id="354ae-165">60-day</span></span>
- <span data-ttu-id="354ae-166">90日</span><span class="sxs-lookup"><span data-stu-id="354ae-166">90-day</span></span>

<span data-ttu-id="354ae-167">URL Date パラメーターは Day フィールドを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="354ae-167">The URL Date parameter accepts a Day field.</span></span> <span data-ttu-id="354ae-168">ローリングレポートでは、トレンドの最終日として YYYY-MM-DD 形式の日付が使用されます。</span><span class="sxs-lookup"><span data-stu-id="354ae-168">Rolling-day reports use dates specified in the YYYY-MM-DD format as the last day of the trend.</span></span> <span data-ttu-id="354ae-169">URL Date パラメーター "00" は "today" を示します。</span><span class="sxs-lookup"><span data-stu-id="354ae-169">The URL Date parameter “00”  indicates “today”.</span></span>

|<span data-ttu-id="354ae-170">URL</span><span class="sxs-lookup"><span data-stu-id="354ae-170">URL</span></span>| <span data-ttu-id="354ae-171">ローリング日のトレンドの終了日</span><span class="sxs-lookup"><span data-stu-id="354ae-171">End date of Rolling Day Trend</span></span>|
|:---|:---|
|<span data-ttu-id="354ae-172"><span>https:// <cqdv3> /spd/#/ダッシュボード/ <reportid> /2019-02/</span></span><span class="sxs-lookup"><span data-stu-id="354ae-172"><span>https://<cqdv3>/spd/#/Dashboard/<reportid>/2019-02/</span></span></span>   |<span data-ttu-id="354ae-173">2019年2月の現在の日付</span><span class="sxs-lookup"><span data-stu-id="354ae-173">Current Day of Feb 2019</span></span>|
|<span data-ttu-id="354ae-174"><span>https:// <cqdv3> /spd/#/ダッシュボード/ <reportid> /2019-02-15/</span></span><span class="sxs-lookup"><span data-stu-id="354ae-174"><span>https://<cqdv3>/spd/#/Dashboard/<reportid>/2019-02-15/</span></span></span>|<span data-ttu-id="354ae-175">2019年2月15日</span><span class="sxs-lookup"><span data-stu-id="354ae-175">Feb 15, 2019</span></span>|
|<span data-ttu-id="354ae-176"><span>https:// <cqdv3> /spd/#/ダッシュボード/ <reportid> /00/</span></span><span class="sxs-lookup"><span data-stu-id="354ae-176"><span>https://<cqdv3>/spd/#/Dashboard/<reportid>/00/</span></span></span>        |<span data-ttu-id="354ae-177">現在の日付</span><span class="sxs-lookup"><span data-stu-id="354ae-177">Current Day</span></span>|
|||

<span data-ttu-id="354ae-178">既定では、月の現在の日付が、ローリング日の傾向の最終日として使用されます。</span><span class="sxs-lookup"><span data-stu-id="354ae-178">By default, the current day of the month is used as the last day of the Rolling Day Trend.</span></span>


## <a name="data-available-in-cqd-reports"></a><span data-ttu-id="354ae-179">CQD レポートで利用可能なデータ</span><span class="sxs-lookup"><span data-stu-id="354ae-179">Data available in CQD reports</span></span>

<span data-ttu-id="354ae-180">既定の概要と詳細な CQD レポートは、組織の通話品質を管理するために必要なものである場合があります。必要に応じて、[カスタムレポートを作成](#create-custom-detailed-reports)することができます。</span><span class="sxs-lookup"><span data-stu-id="354ae-180">The default summary and detailed CQD reports may be all you need to manage call quality for your org. If you need to, you can [create custom reports](#create-custom-detailed-reports).</span></span> 

<span data-ttu-id="354ae-181">Power BI を使用して CQD データを分析する場合は、「 [POWER bi を使用して Teams の CQD データを分析](CQD-Power-BI-query-templates.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="354ae-181">If you want to use Power BI to analyze your CQD data, read [Use Power BI to analyze CQD data for Teams](CQD-Power-BI-query-templates.md).</span></span>

|<span data-ttu-id="354ae-182">機能</span><span class="sxs-lookup"><span data-stu-id="354ae-182">Feature</span></span>|<span data-ttu-id="354ae-183">概要レポート</span><span class="sxs-lookup"><span data-stu-id="354ae-183">Summary Reports</span></span>|<span data-ttu-id="354ae-184">詳細レポート</span><span class="sxs-lookup"><span data-stu-id="354ae-184">Detailed Reports</span></span>|
|:--- |:--- |:--- |
|<span data-ttu-id="354ae-185">アプリケーション共有のメトリック</span><span class="sxs-lookup"><span data-stu-id="354ae-185">Application sharing metric</span></span> | <span data-ttu-id="354ae-186">いいえ</span><span class="sxs-lookup"><span data-stu-id="354ae-186">No</span></span> | <span data-ttu-id="354ae-187">はい</span><span class="sxs-lookup"><span data-stu-id="354ae-187">Yes</span></span> |
|<span data-ttu-id="354ae-188">顧客の建物情報のサポート</span><span class="sxs-lookup"><span data-stu-id="354ae-188">Customer building information support</span></span> | <span data-ttu-id="354ae-189">はい</span><span class="sxs-lookup"><span data-stu-id="354ae-189">Yes</span></span> | <span data-ttu-id="354ae-190">はい</span><span class="sxs-lookup"><span data-stu-id="354ae-190">Yes</span></span> |
|<span data-ttu-id="354ae-191">顧客エンドポイント情報のサポート</span><span class="sxs-lookup"><span data-stu-id="354ae-191">Customer endpoint information support</span></span> | <span data-ttu-id="354ae-192">Cqd.teams.microsoft.com のみ <span><span/></span><span class="sxs-lookup"><span data-stu-id="354ae-192">Only in <span>cqd.teams.microsoft.com<span/></span></span> | <span data-ttu-id="354ae-193">Cqd.teams.microsoft.com のみ <span><span/></span><span class="sxs-lookup"><span data-stu-id="354ae-193">Only in <span>cqd.teams.microsoft.com<span/></span></span> |
|<span data-ttu-id="354ae-194">ドリルダウン分析のサポート</span><span class="sxs-lookup"><span data-stu-id="354ae-194">Drill down analysis support</span></span>   | <span data-ttu-id="354ae-195">いいえ</span><span class="sxs-lookup"><span data-stu-id="354ae-195">No</span></span>   | <span data-ttu-id="354ae-196">はい</span><span class="sxs-lookup"><span data-stu-id="354ae-196">Yes</span></span>   |
|<span data-ttu-id="354ae-197">メディアの信頼性のメトリック</span><span class="sxs-lookup"><span data-stu-id="354ae-197">Media reliability metrics</span></span>   | <span data-ttu-id="354ae-198">いいえ</span><span class="sxs-lookup"><span data-stu-id="354ae-198">No</span></span>   | <span data-ttu-id="354ae-199">はい</span><span class="sxs-lookup"><span data-stu-id="354ae-199">Yes</span></span>   |
|<span data-ttu-id="354ae-200">ボックスのないレポート</span><span class="sxs-lookup"><span data-stu-id="354ae-200">Out-of-the-box reports</span></span>   | <span data-ttu-id="354ae-201">はい</span><span class="sxs-lookup"><span data-stu-id="354ae-201">Yes</span></span>   | <span data-ttu-id="354ae-202">はい</span><span class="sxs-lookup"><span data-stu-id="354ae-202">Yes</span></span>   |
|<span data-ttu-id="354ae-203">概要レポート</span><span class="sxs-lookup"><span data-stu-id="354ae-203">Overview reports</span></span>   | <span data-ttu-id="354ae-204">はい</span><span class="sxs-lookup"><span data-stu-id="354ae-204">Yes</span></span>   | <span data-ttu-id="354ae-205">はい</span><span class="sxs-lookup"><span data-stu-id="354ae-205">Yes</span></span>   |
|<span data-ttu-id="354ae-206">ユーザーごとのレポートセット</span><span class="sxs-lookup"><span data-stu-id="354ae-206">Per-user report set</span></span>   | <span data-ttu-id="354ae-207">いいえ</span><span class="sxs-lookup"><span data-stu-id="354ae-207">No</span></span>   | <span data-ttu-id="354ae-208">はい</span><span class="sxs-lookup"><span data-stu-id="354ae-208">Yes</span></span>   |
|<span data-ttu-id="354ae-209">レポートセットのカスタマイズ (レポートの追加、削除、変更)</span><span class="sxs-lookup"><span data-stu-id="354ae-209">Report set customization (add, delete, modify reports)</span></span>   | <span data-ttu-id="354ae-210">いいえ</span><span class="sxs-lookup"><span data-stu-id="354ae-210">No</span></span>   | <span data-ttu-id="354ae-211">はい</span><span class="sxs-lookup"><span data-stu-id="354ae-211">Yes</span></span>   |
|<span data-ttu-id="354ae-212">ビデオベースの画面共有のメトリック</span><span class="sxs-lookup"><span data-stu-id="354ae-212">Video-based screen sharing metrics</span></span>   | <span data-ttu-id="354ae-213">いいえ</span><span class="sxs-lookup"><span data-stu-id="354ae-213">No</span></span>   | <span data-ttu-id="354ae-214">はい</span><span class="sxs-lookup"><span data-stu-id="354ae-214">Yes</span></span>   |
|<span data-ttu-id="354ae-215">ビデオ指標</span><span class="sxs-lookup"><span data-stu-id="354ae-215">Video metrics</span></span>   | <span data-ttu-id="354ae-216">いいえ</span><span class="sxs-lookup"><span data-stu-id="354ae-216">No</span></span>   | <span data-ttu-id="354ae-217">はい</span><span class="sxs-lookup"><span data-stu-id="354ae-217">Yes</span></span>   |
|<span data-ttu-id="354ae-218">利用可能なデータの量</span><span class="sxs-lookup"><span data-stu-id="354ae-218">Amount of data available</span></span>   | <span data-ttu-id="354ae-219">過去12か月間</span><span class="sxs-lookup"><span data-stu-id="354ae-219">Last 12 months</span></span>   | <span data-ttu-id="354ae-220">過去12か月間</span><span class="sxs-lookup"><span data-stu-id="354ae-220">Last 12 months</span></span>   |
|<span data-ttu-id="354ae-221">Microsoft Teams データ</span><span class="sxs-lookup"><span data-stu-id="354ae-221">Microsoft Teams data</span></span>   | <span data-ttu-id="354ae-222">はい</span><span class="sxs-lookup"><span data-stu-id="354ae-222">Yes</span></span>   | <span data-ttu-id="354ae-223">はい</span><span class="sxs-lookup"><span data-stu-id="354ae-223">Yes</span></span>   |
| | | |


 
### <a name="select-product-data-to-see-in-reports"></a><span data-ttu-id="354ae-224">レポートで表示する製品データを選ぶ</span><span class="sxs-lookup"><span data-stu-id="354ae-224">Select product data to see in reports</span></span>

<span data-ttu-id="354ae-225">概要と場所で強化されたレポートでは、[**製品フィルター** ] ドロップダウンを使用して、すべての製品データを表示したり、Microsoft Teams のデータのみを表示したり、Skype For business Online データのみを表示したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="354ae-225">In the Summary and Location-Enhanced Reports, you can use the **Product Filter** drop-down to show all product data, only Microsoft Teams data, or only Skype for Business Online data.</span></span>
  
![スクリーンショット: 製品フィルターコントロールオプションを示します。](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
<span data-ttu-id="354ae-227">詳細レポートで**は、Is Teams**ディメンションを使用して、Microsoft Teams または Skype For business Online データにデータをフィルター処理することができます。</span><span class="sxs-lookup"><span data-stu-id="354ae-227">In Detailed reports, you can use the **Is Teams** dimension to filter the data to Microsoft Teams or Skype for Business Online data.</span></span>

## <a name="summary-reports"></a><span data-ttu-id="354ae-228">概要レポート</span><span class="sxs-lookup"><span data-stu-id="354ae-228">Summary Reports</span></span>

<span data-ttu-id="354ae-229">以下は、CQD に初めてサインインしたときに CQD ダッシュボードに表示されるレポートです。</span><span class="sxs-lookup"><span data-stu-id="354ae-229">These are the reports that you'll see on the CQD Dashboard when you first sign in to CQD.</span></span> <span data-ttu-id="354ae-230">高品質のサブネットを特定するのに役立つ、毎日、毎月、およびテーブルレポートを使用して、高品質の傾向を把握することができます。</span><span class="sxs-lookup"><span data-stu-id="354ae-230">They give you an at-a-glance look at quality trends with daily, monthly, and table reports to assist with identifying subnets that have poor quality.</span></span> 

|<span data-ttu-id="354ae-231">見出し</span><span class="sxs-lookup"><span data-stu-id="354ae-231">Tab</span></span>  |  |
|---------|---------|
|<span data-ttu-id="354ae-232">全体的な通話品質</span><span class="sxs-lookup"><span data-stu-id="354ae-232">Overall Call Quality</span></span>     | <span data-ttu-id="354ae-233">他の3つのタブの集計</span><span class="sxs-lookup"><span data-stu-id="354ae-233">Aggregate of the other 3 tabs</span></span>        |
|<span data-ttu-id="354ae-234">サーバ-クライアント</span><span class="sxs-lookup"><span data-stu-id="354ae-234">Server—Client</span></span>     |<span data-ttu-id="354ae-235">サーバーエンドポイントとクライアントエンドポイント間のストリームの詳細</span><span class="sxs-lookup"><span data-stu-id="354ae-235">Details of the streams between server and client endpoints</span></span>         |
|<span data-ttu-id="354ae-236">クライアント-クライアント</span><span class="sxs-lookup"><span data-stu-id="354ae-236">Client—Client</span></span>     |<span data-ttu-id="354ae-237">2つのクライアントエンドポイント間のストリームの詳細</span><span class="sxs-lookup"><span data-stu-id="354ae-237">Details of the streams between two client endpoints</span></span>         |
|<span data-ttu-id="354ae-238">音声品質の SLA</span><span class="sxs-lookup"><span data-stu-id="354ae-238">Voice Quality SLA</span></span>     |<span data-ttu-id="354ae-239">Skype for Business の音声品質の[SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)に含まれる通話に関する情報</span><span class="sxs-lookup"><span data-stu-id="354ae-239">Info about calls included in the Skype for Business voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)</span></span>         |

### <a name="overall-call-quality-tab"></a><span data-ttu-id="354ae-240">[全体的な通話品質] タブ</span><span class="sxs-lookup"><span data-stu-id="354ae-240">Overall Call Quality tab</span></span>

<span data-ttu-id="354ae-241">このタブのデータを使用して、通話品質の状態と、ストリーミングカウントと低い割合に基づいた傾向を評価します。</span><span class="sxs-lookup"><span data-stu-id="354ae-241">Use the data on this tab to evaluate call quality status and trends based on stream counts and poor percentages.</span></span> <span data-ttu-id="354ae-242">右上隅の凡例は、どの色と視覚要素がこれらのメトリックを表しているかを示しています。</span><span class="sxs-lookup"><span data-stu-id="354ae-242">The legend in the upper-right corner shows which color and visual elements represent these metrics.</span></span>
  
![スクリーンショット: [通話品質] タブを表示する](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
<span data-ttu-id="354ae-244">ストリームは、良好、低品質、未分類の3つのグループに分類されます。</span><span class="sxs-lookup"><span data-stu-id="354ae-244">Streams are classified in three groups: Good, Poor, and Unclassified.</span></span> <span data-ttu-id="354ae-245">また、分類されたストリームの合計数に*低品質*として分類されたストリームの比率を示す*低品質*の値が計算されます。</span><span class="sxs-lookup"><span data-stu-id="354ae-245">There are also calculated  *Poor %*  values that give you the ratio of streams classified as *Poor*  to the total classified stream count.</span></span> <span data-ttu-id="354ae-246">*低品質のストリーム/(不十分なストリーム + 良好なストリーム) \* 100\*\*は、* 複数の*未分類*ストリームの存在によって影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="354ae-246">Since *Poor % = Poor streams/ (Poor streams+ Good streams) \* 100*, the *Poor %*  is unaffected by the presence of multiple *Unclassified*  streams.</span></span> <span data-ttu-id="354ae-247">ストリームを低品質または良好な状態として分類する方法については、「[通話品質ダッシュボードでのストリームの分類」](stream-classification-in-call-quality-dashboard.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="354ae-247">To see what classifies a stream as poor or good, refer to [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md).</span></span>
  
<span data-ttu-id="354ae-248">ストリーム数の値を測定するには、左側のスケールを使用します。</span><span class="sxs-lookup"><span data-stu-id="354ae-248">Use the scale on the left to measure the stream count values.</span></span>
  
![スクリーンショット: ストリームカウント値の表示](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
<span data-ttu-id="354ae-250">右側のスケールを使用して、低品質の値を測定します。</span><span class="sxs-lookup"><span data-stu-id="354ae-250">Use the scale on the right to measure the Poor % values.</span></span>
  
![スクリーンショット: 低品質の値が表示されます](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
<span data-ttu-id="354ae-252">また、バーの上にマウスを置くと、実際の数値を取得できます。</span><span class="sxs-lookup"><span data-stu-id="354ae-252">You can also obtain the actual numerical values by hovering the mouse over a bar.</span></span>
  
> [!NOTE]
> <span data-ttu-id="354ae-253">次の例は、非常に小さなサンプルデータセットからの値で、実際の展開には現実的ではありません。</span><span class="sxs-lookup"><span data-stu-id="354ae-253">The following example is from a very small sample data set, and the values aren't realistic for an actual deployment.</span></span>
  
![スクリーンショット: データへのアクセスに使用されたマウスの表示](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
<span data-ttu-id="354ae-255">全体的なストリームボリュームは、計算された低品質の割合の関連性を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="354ae-255">The overall stream volume helps determine how relevant the calculated Poor percentages are.</span></span> <span data-ttu-id="354ae-256">全体的なストリームの量が少ないほど、報告される低割合の値は、信頼性が低くなります。</span><span class="sxs-lookup"><span data-stu-id="354ae-256">The smaller the volume of overall streams, the less reliable the reported Poor percentage values are.</span></span>
  
### <a name="server-client-tab-and-client-client-tabs"></a><span data-ttu-id="354ae-257">[サーバー-クライアント] タブと [クライアント-クライアント] タブ</span><span class="sxs-lookup"><span data-stu-id="354ae-257">Server-Client tab and Client-Client tabs</span></span>

<span data-ttu-id="354ae-258">次の2つのタブは、エンドポイント間のシナリオで発生したストリームの詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="354ae-258">These two tabs provide details for the streams that took place in their endpoint-to-endpoint scenarios.</span></span> <span data-ttu-id="354ae-259">[サーバー-クライアント] タブには、メディアストリームが流れる4つのシナリオを表す4つの折りたたみ可能なセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="354ae-259">The Server-Client tab has four collapsible sections that represent four scenarios under which media streams would flow.</span></span>
  
- <span data-ttu-id="354ae-260">有線 (内部)</span><span class="sxs-lookup"><span data-stu-id="354ae-260">Wired Inside</span></span>
- <span data-ttu-id="354ae-261">有線 (外部)</span><span class="sxs-lookup"><span data-stu-id="354ae-261">Wired Outside</span></span>
- <span data-ttu-id="354ae-262">WiFi (内部)</span><span class="sxs-lookup"><span data-stu-id="354ae-262">WiFi Inside</span></span>
- <span data-ttu-id="354ae-263">WiFi (外部)</span><span class="sxs-lookup"><span data-stu-id="354ae-263">WiFi Outside</span></span>

<span data-ttu-id="354ae-264">同様に、[クライアント-クライアント] タブには、5つの折りたたみ可能なセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="354ae-264">Similarly, the Client-Client tab has five collapsible sections:</span></span>

- <span data-ttu-id="354ae-265">有線 (内側)、有線</span><span class="sxs-lookup"><span data-stu-id="354ae-265">Wired Inside — Wired Inside</span></span>
- <span data-ttu-id="354ae-266">有線 (内部)-有線 (外部)</span><span class="sxs-lookup"><span data-stu-id="354ae-266">Wired Inside — Wired Outside</span></span>
- <span data-ttu-id="354ae-267">有線 (外部)-有線 (外部)</span><span class="sxs-lookup"><span data-stu-id="354ae-267">Wired Outside — Wired Outside</span></span>
- <span data-ttu-id="354ae-268">有線 (内部) — WiFi (内部)</span><span class="sxs-lookup"><span data-stu-id="354ae-268">Wired Inside — WiFi Inside</span></span>
- <span data-ttu-id="354ae-269">有線 (内部) — WiFi (外部)</span><span class="sxs-lookup"><span data-stu-id="354ae-269">Wired Inside — WiFi Outside</span></span>

#### <a name="inside-versus-outside"></a><span data-ttu-id="354ae-270">内側と外側</span><span class="sxs-lookup"><span data-stu-id="354ae-270">Inside versus Outside</span></span>

<span data-ttu-id="354ae-271">CQD は、存在する場合は、建物情報を使用して、ストリームを*内部*または*外部*として分類します。</span><span class="sxs-lookup"><span data-stu-id="354ae-271">CQD classifies a stream as  *Inside*  or *Outside*  using Building information, if it exists.</span></span> <span data-ttu-id="354ae-272">各ストリームのエンドポイントは、サブネットアドレスと関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="354ae-272">Endpoints of each stream are associated with a subnet address.</span></span> <span data-ttu-id="354ae-273">アップロードした建物情報の InsideCorp とマークされているサブネットの一覧にサブネットがある場合、そのサブネットは*内部*と見なされます。</span><span class="sxs-lookup"><span data-stu-id="354ae-273">If the subnet is in the list of the subnets marked InsideCorp in the uploaded Building information, then it is considered *Inside*.</span></span> <span data-ttu-id="354ae-274">作成情報がまだアップロードされていない場合は、内側のテストでは常に*外部*としてストリームを分類します。</span><span class="sxs-lookup"><span data-stu-id="354ae-274">If Building information has not yet been uploaded, then Inside Test always classifies the streams as *Outside*.</span></span> 

<span data-ttu-id="354ae-275">サーバークライアントシナリオの内部テストでは、クライアントエンドポイントのみが考慮されます。</span><span class="sxs-lookup"><span data-stu-id="354ae-275">The Inside Test for a Server-Client scenario only considers the client endpoint.</span></span> <span data-ttu-id="354ae-276">サーバーは常にユーザーの視点から外れているため、これはテストでは考慮されません。</span><span class="sxs-lookup"><span data-stu-id="354ae-276">Because servers are always outside from a user's perspective, this isn't accounted for in the test.</span></span>
  
#### <a name="wired-versus-wifi"></a><span data-ttu-id="354ae-277">有線と WiFi の比較</span><span class="sxs-lookup"><span data-stu-id="354ae-277">Wired versus WiFi</span></span>

<span data-ttu-id="354ae-278">名前が示すように、分類条件は、クライアント接続の種類に基づいています。</span><span class="sxs-lookup"><span data-stu-id="354ae-278">As the names indicate, the classification criteria is based on the type of client connections.</span></span> <span data-ttu-id="354ae-279">サーバーは常に有線であり、計算に含まれていません。</span><span class="sxs-lookup"><span data-stu-id="354ae-279">Server is always wired and it isn't included in the calculation.</span></span> <span data-ttu-id="354ae-280">特定のストリームで、2つのエンドポイントの一方が WiFi ネットワークに接続されている場合は、CQD は WiFi として分類されます。</span><span class="sxs-lookup"><span data-stu-id="354ae-280">In a given stream, if one of the two endpoints is connected to a WiFi network, then CQD classifies it as WiFi.</span></span>
> [!NOTE]
> <span data-ttu-id="354ae-281">特定のストリームについて、2つのエンドポイントの一方が WiFi ネットワークに接続されていれば、CQD で WiFi として分類されます。</span><span class="sxs-lookup"><span data-stu-id="354ae-281">Given a stream, if one of the two endpoints is connected to a WiFi network, then it is classified as WiFi in CQD.</span></span>
  
  
## <a name="tenant-data-information"></a><span data-ttu-id="354ae-282">テナントデータ情報</span><span class="sxs-lookup"><span data-stu-id="354ae-282">Tenant Data information</span></span>

<span data-ttu-id="354ae-283">CQD Summary レポートダッシュボードには、右上隅にある [設定] メニューから [**テナントデータ**アップロード] を選択することによってアクセスできる**テナントデータアップロード**ページが含まれています。</span><span class="sxs-lookup"><span data-stu-id="354ae-283">The CQD Summary Reports dashboard includes a **Tenant Data Upload** page, accessed by selecting **Tenant Data Upload** from the settings menu in the top-right corner.</span></span> <span data-ttu-id="354ae-284">このページは、管理者が次のような独自の情報をアップロードするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="354ae-284">This page is used for admins to upload their own information, such as:</span></span>

- <span data-ttu-id="354ae-285">IP アドレスと地理的情報のマップ</span><span class="sxs-lookup"><span data-stu-id="354ae-285">A map of IP address and geographical information</span></span>
- <span data-ttu-id="354ae-286">各ワイヤレス AP とその MAC アドレスの地図</span><span class="sxs-lookup"><span data-stu-id="354ae-286">A map of each wireless AP and its MAC address</span></span>
- <span data-ttu-id="354ae-287">エンドポイントからエンドポイントの作成/モデル/型へのマップ。など</span><span class="sxs-lookup"><span data-stu-id="354ae-287">A map of Endpoint to Endpoint Make/Model/Type, etc.</span></span>
  
<span data-ttu-id="354ae-288">CQD がレポートにこの情報を含めることができるように、テナント、建物、および場所のデータをアップロードすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="354ae-288">We recommend that you upload your tenant, building, and location data so CQD can include this information in your reports.</span></span> <span data-ttu-id="354ae-289">このデータをまだアップロードしていない場合は、「[テナントのアップロードとデータの構築](CQD-upload-tenant-building-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="354ae-289">If you haven't already uploaded this data, read [Upload tenant and building data](CQD-upload-tenant-building-data.md).</span></span> 


## <a name="detailed-reports"></a><span data-ttu-id="354ae-290">詳細レポート</span><span class="sxs-lookup"><span data-stu-id="354ae-290">Detailed reports</span></span>

|<span data-ttu-id="354ae-291">名前</span><span class="sxs-lookup"><span data-stu-id="354ae-291">Name</span></span>  |  |
|---------|---------|
|<span data-ttu-id="354ae-292">位置情報を強化したレポート</span><span class="sxs-lookup"><span data-stu-id="354ae-292">Location-Enhanced Reports</span></span>     |<span data-ttu-id="354ae-293">位置情報に基づいて品質の傾向を示します。</span><span class="sxs-lookup"><span data-stu-id="354ae-293">Shows quality trends based on location information.</span></span> <span data-ttu-id="354ae-294">このレポートは[、テナントデータをアップロード](CQD-upload-tenant-building-data.md)した場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="354ae-294">This report appears only if you've [uploaded your tenant data](CQD-upload-tenant-building-data.md).</span></span>        |
|<span data-ttu-id="354ae-295">信頼性レポート</span><span class="sxs-lookup"><span data-stu-id="354ae-295">Reliability Reports</span></span>     |<span data-ttu-id="354ae-296">オーディオ、ビデオ、ビデオベースの画面共有 (VBSS)、アプリ共有レポートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="354ae-296">Includes audio, video, video-based screen sharing (VBSS), and app sharing reports</span></span>         |
|<span data-ttu-id="354ae-297">エクスペリエンスの品質レポート</span><span class="sxs-lookup"><span data-stu-id="354ae-297">Quality of Experience Reports</span></span>     |<span data-ttu-id="354ae-298">会議室を含むすべてのクライアントとデバイスの音声品質と信頼性。</span><span class="sxs-lookup"><span data-stu-id="354ae-298">Audio quality and reliability for all clients and devices, including meeting rooms.</span></span> <span data-ttu-id="354ae-299">これらのレポートは、ダウンロード可能な[CQD テンプレート](https://aka.ms/QERtemplates)の "slimmed" バージョンであり、オーディオの品質と信頼性を分析するための主要な領域に重点を置いています。</span><span class="sxs-lookup"><span data-stu-id="354ae-299">These reports are a “slimmed-down” version of the downloadable [CQD templates](https://aka.ms/QERtemplates), focusing on key areas for analyzing audio quality and reliability.</span></span>         |
|<span data-ttu-id="354ae-300">品質ドリルダウンレポート</span><span class="sxs-lookup"><span data-stu-id="354ae-300">Quality Drill Down Reports</span></span>     | <span data-ttu-id="354ae-301">ドリルダウン: 地域、場所、サブネット、時間、ユーザー別の日付</span><span class="sxs-lookup"><span data-stu-id="354ae-301">Drill downs: Date by region, locations, subnets, hour, and users</span></span>         |
|<span data-ttu-id="354ae-302">失敗したドリルダウンレポート</span><span class="sxs-lookup"><span data-stu-id="354ae-302">Failure Drill Down Reports</span></span>     | <span data-ttu-id="354ae-303">ドリルダウン: 地域、場所、サブネット、時間、ユーザー別の日付</span><span class="sxs-lookup"><span data-stu-id="354ae-303">Drill downs: Date by region, locations, subnets, hour, and users</span></span>        |
|<span data-ttu-id="354ae-304">通話レポートの評価</span><span class="sxs-lookup"><span data-stu-id="354ae-304">Rate My Call Reports</span></span>     |<span data-ttu-id="354ae-305">地域、場所、ユーザー別によるユーザー呼び出しの評価を分析します。</span><span class="sxs-lookup"><span data-stu-id="354ae-305">Analyze user call ratings by region, location, or by user.</span></span> <span data-ttu-id="354ae-306">その他のフィードバックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="354ae-306">Includes verbatim feedback.</span></span>         |
|<span data-ttu-id="354ae-307">ヘルプデスクのレポート</span><span class="sxs-lookup"><span data-stu-id="354ae-307">Help Desk Reports</span></span>     |<span data-ttu-id="354ae-308">ヘルプデスクレポートでは、個々のユーザー、ユーザーのグループ、または全員の通話と会議データが表示されます。</span><span class="sxs-lookup"><span data-stu-id="354ae-308">Help Desk Reports look at call and meeting data for individual users, groups of users, or everyone.</span></span> <span data-ttu-id="354ae-309">このレポートは、建物と EUII のデータを組み込み、ネットワークの場所、会議の詳細、デバイス、またはファームウェアに基づいて、発生する可能性のあるシステムの問題を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="354ae-309">Incorporating building and EUII data, these reports help identify possible system issues based on network location, conference details, devices, or firmware.</span></span>         |
|<span data-ttu-id="354ae-310">クライアントバージョンレポート</span><span class="sxs-lookup"><span data-stu-id="354ae-310">Client Version Reports</span></span>     |<span data-ttu-id="354ae-311">クライアントバージョンの概要: クライアントアプリの各バージョンのセッション数とユーザー数を表示します。</span><span class="sxs-lookup"><span data-stu-id="354ae-311">Client Version Summary: View the Sessions and Users counts for each client app version</span></span><br><br><span data-ttu-id="354ae-312">ユーザー別クライアントバージョン: 各クライアントアプリのバージョンのユーザー名を表示する</span><span class="sxs-lookup"><span data-stu-id="354ae-312">Client Version by User: View user names for each client app version</span></span> <br><br><span data-ttu-id="354ae-313">製品とクライアントの種類の事前に構築されたフィルターによって、バージョンが特定のクライアントに焦点を当てていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="354ae-313">Pre-built filters for Product and Client Type help focus the versions to specific clients.</span></span>         |
|<span data-ttu-id="354ae-314">エンドポイントレポート</span><span class="sxs-lookup"><span data-stu-id="354ae-314">Endpoint Reports</span></span>     |<span data-ttu-id="354ae-315">マシンのエンドポイントによって通話品質が表示されます (コンピュータのメーカーとモデル)。</span><span class="sxs-lookup"><span data-stu-id="354ae-315">Shows call quality by machine endpoints (computer make and model).</span></span> <span data-ttu-id="354ae-316">このレポートには、アップロードしたデータの作成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="354ae-316">These reports include building data, if you've uploaded it.</span></span>         |


## <a name="create-custom-detailed-reports"></a><span data-ttu-id="354ae-317">ユーザー設定の詳細レポートを作成する</span><span class="sxs-lookup"><span data-stu-id="354ae-317">Create custom detailed reports</span></span>

<span data-ttu-id="354ae-318">既定の CQD レポートが目的に合わない場合は、次の手順を使用してカスタムレポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="354ae-318">If the default CQD reports don't meet your needs, use these instructions to create a custom report.</span></span> <span data-ttu-id="354ae-319">または (2020 年1月以降)、 [POWER BI FOR CQD レポートを代わりに使用](cqd-power-bi-query-templates.md)します。</span><span class="sxs-lookup"><span data-stu-id="354ae-319">Or (as of January 2020) [Use Power BI for CQD reports ](cqd-power-bi-query-templates.md)instead.</span></span>

<span data-ttu-id="354ae-320">ログイン時に表示される画面の上部にあるレポートのプルダウンリストから、[レポートの \( **概要**] 画面で [ \) **詳細レポート**]、[**新規**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="354ae-320">From the pull-down list of reports at the top of the screen displayed at login \(the **Summary Reports** screen\) Select **Detailed Reports**  and then **New**.</span></span> <span data-ttu-id="354ae-321">[レポートの**編集**] をクリックして、クエリエディターを表示します。</span><span class="sxs-lookup"><span data-stu-id="354ae-321">Click **Edit** in a report to see the Query Editor.</span></span> <span data-ttu-id="354ae-322">それぞれのレポートは、キューブに対するクエリに基づきます。</span><span class="sxs-lookup"><span data-stu-id="354ae-322">Each report is backed by a query into the cube.</span></span> <span data-ttu-id="354ae-323">レポートは、クエリから返されたデータを視覚化したものです。</span><span class="sxs-lookup"><span data-stu-id="354ae-323">A report is a visualization of the data returned by its query.</span></span> <span data-ttu-id="354ae-324">クエリエディターを使用すると、これらのクエリやレポートの表示オプションを編集できます。</span><span class="sxs-lookup"><span data-stu-id="354ae-324">The Query Editor helps you edit these queries and the display options of the report.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="354ae-325">ネットワーク範囲は、スーパーネット (単一のルーティングプレフィックスを持つ複数のサブネットの組み合わせ) を表すために使用できます。</span><span class="sxs-lookup"><span data-stu-id="354ae-325">The network range can be used to represent a supernet (combination of several subnets with a single routing prefix).</span></span> <span data-ttu-id="354ae-326">新しくなったすべての文書のアップロードで、重複範囲が確認されます。</span><span class="sxs-lookup"><span data-stu-id="354ae-326">All new building uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="354ae-327">以前にビルドファイルをアップロードしたことがある場合は、現在のファイルをダウンロードして再アップロードし、重複を特定し、問題を解決してからもう一度アップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="354ae-327">If you have previously uploaded a building file, you should download the current file and re-upload it to identify any overlaps and fix the issue before uploading again.</span></span> <span data-ttu-id="354ae-328">以前にアップロードされたファイルが重なっていると、サブネットとレポートの建物とのマッピングが間違っている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="354ae-328">Any overlap in previously uploaded files may result in the wrong mappings of subnets to buildings in the reports.</span></span> <span data-ttu-id="354ae-329">特定の VPN の実装では、サブネット情報が正確に報告されません。</span><span class="sxs-lookup"><span data-stu-id="354ae-329">Certain VPN implementations do not accurately report the subnet information.</span></span> <span data-ttu-id="354ae-330">構成ファイルに VPN サブネットを追加するときは、サブネットのエントリの1つではなく、個別の32ビットネットワークとして、VPN サブネットの各アドレスに個別のエントリを追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="354ae-330">It is recommended that when adding a VPN subnet to the building file, instead of one entry for the subnet, separate entries are added for each address in the VPN subnet as a separate 32-bit network.</span></span> <span data-ttu-id="354ae-331">各行には、同じビルドメタデータを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="354ae-331">Each row can have the same building metadata.</span></span> <span data-ttu-id="354ae-332">たとえば、172.16.18.0/24 の1行ではなく、256行と、172.16.18.0/32 と 172.16.18.255/32 の間の各アドレスに1つの行が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="354ae-332">For example, instead of one row for 172.16.18.0/24, you should have 256 rows, with one row for each address between 172.16.18.0/32 and 172.16.18.255/32, inclusive.</span></span>
>
> <span data-ttu-id="354ae-333">VPN 列はオプションであり、既定値は0に設定されます。</span><span class="sxs-lookup"><span data-stu-id="354ae-333">The VPN column is optional and will default to 0.</span></span>  <span data-ttu-id="354ae-334">VPN 列の値が1に設定されている場合、その行で表されるサブネットは、サブネット内のすべての IP アドレスと一致するように完全に拡張されます。</span><span class="sxs-lookup"><span data-stu-id="354ae-334">If the VPN column's value is set to 1, the subnet represented by that row will be fully expanded to match all IP addresses within the subnet.</span></span>  <span data-ttu-id="354ae-335">これらのサブネットを完全に拡張すると、データの作成に関係するクエリのクエリ時間に悪影響を与える可能性があるため、このように慎重に使用してください。</span><span class="sxs-lookup"><span data-stu-id="354ae-335">Please use this sparingly and only for VPN subnets since fully expanding these subnets will have a negative impact on query times for queries involving building data.</span></span>

<span data-ttu-id="354ae-336">レポートの [横棒グラフ] および [近似曲線] をポイントして、詳細な値を表示します。</span><span class="sxs-lookup"><span data-stu-id="354ae-336">Point to bar charts and trend lines in the report to display detailed values.</span></span> <span data-ttu-id="354ae-337">フォーカスがあるレポートには、[アクション] メニュー ([**編集**]、[**複製**]、[**削除**]、[**ダウンロード**]、[エクスポート] の各**レポート**) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="354ae-337">The report that has focus will show the action menu: **Edit**, **Clone**, **Delete**, **Download**, and **Export Report Tree**.</span></span>



## <a name="query-filters"></a><span data-ttu-id="354ae-338">クエリフィルター</span><span class="sxs-lookup"><span data-stu-id="354ae-338">Query filters</span></span>

<span data-ttu-id="354ae-339">クエリフィルターは、CQD のクエリエディターを使用して実装されます。</span><span class="sxs-lookup"><span data-stu-id="354ae-339">Query filters are implemented by using the Query Editor in CQD.</span></span> <span data-ttu-id="354ae-340">これらのフィルターは、CQD によって返されるレコード数を減らすために使用されるため、レポート全体のサイズとクエリの時間を最小限に抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="354ae-340">These filters are used to reduce the number of records returned by CQD, thus minimizing the report’s overall size and query times.</span></span> <span data-ttu-id="354ae-341">これは、管理されていないネットワークをフィルター処理する場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="354ae-341">This is especially useful for filtering out unmanaged networks.</span></span> <span data-ttu-id="354ae-342">次の表に示すフィルターは、正規表現 (RegEx) を使用しています。</span><span class="sxs-lookup"><span data-stu-id="354ae-342">The filters listed in the following table use regular expressions (RegEx).</span></span>


| <span data-ttu-id="354ae-343">フィルター</span><span class="sxs-lookup"><span data-stu-id="354ae-343">Filter</span></span>         | <span data-ttu-id="354ae-344">説明</span><span class="sxs-lookup"><span data-stu-id="354ae-344">Description</span></span>          | <span data-ttu-id="354ae-345">CQD クエリフィルターの例</span><span class="sxs-lookup"><span data-stu-id="354ae-345">CQD query filter example</span></span>      |
|----------------|----------------------|-------------------------------|
| <span data-ttu-id="354ae-346">空白値はありません</span><span class="sxs-lookup"><span data-stu-id="354ae-346">No blank values</span></span>   | <span data-ttu-id="354ae-347">一部のフィルターには、空の値をフィルター処理するオプションがありません。</span><span class="sxs-lookup"><span data-stu-id="354ae-347">Some filters don’t have the option to filter for blank values.</span></span> <span data-ttu-id="354ae-348">空の値を手動でフィルター処理するには、必要に応じて、空の式を使用し、フィルターを "等しい" または "Not Equals" に設定します。</span><span class="sxs-lookup"><span data-stu-id="354ae-348">To filter blank values manually, use the blank expression and set the filter to Equals or Not Equals, depending on your needs.</span></span>      | <span data-ttu-id="354ae-349">第2の建物 \<\> の名前 \^ \\\*\$</span><span class="sxs-lookup"><span data-stu-id="354ae-349">Second Building Name \<\> \^\\s\*\$</span></span>                       |
| <span data-ttu-id="354ae-350">共通サブネットを除外する</span><span class="sxs-lookup"><span data-stu-id="354ae-350">Exclude common subnets</span></span> | <span data-ttu-id="354ae-351">管理されていないネットワークから個別に管理するための有効な建物ファイルがない場合、ホームネットワークはレポートに含まれます。</span><span class="sxs-lookup"><span data-stu-id="354ae-351">Without a valid building file to separate managed from unmanaged networks, home networks will be included in the reports.</span></span> <span data-ttu-id="354ae-352">これらのホームサブネットは、その制御の範囲外であり、レポートからすばやく除外することができます。</span><span class="sxs-lookup"><span data-stu-id="354ae-352">These home subnets are outside the scope of IT’s control and can be quickly excluded from a report.</span></span> <span data-ttu-id="354ae-353">このガイドで定義されている一般的なサブネットは、10.0.0.0、192.168.1.0、192.168.0.0 です。</span><span class="sxs-lookup"><span data-stu-id="354ae-353">Common subnets, as defined in this guide, are 10.0.0.0, 192.168.1.0 and 192.168.0.0.</span></span> | <span data-ttu-id="354ae-354">第2のサブネット \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="354ae-354">Second Subnet \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0</span></span> |
| <span data-ttu-id="354ae-355">内部でのみ表示</span><span class="sxs-lookup"><span data-stu-id="354ae-355">View inside only</span></span>  | <span data-ttu-id="354ae-356">管理対象 (内部) または非管理 (外部) のレポートをフィルター処理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="354ae-356">Used to filter a report for managed (inside) or unmanaged (outside).</span></span> <span data-ttu-id="354ae-357">管理された CQD テンプレートは、これらのフィルターで既に構成されています。</span><span class="sxs-lookup"><span data-stu-id="354ae-357">The managed CQD template is already preconfigured with these filters.</span></span>       | <span data-ttu-id="354ae-358">2番目の内部企業 = 内部</span><span class="sxs-lookup"><span data-stu-id="354ae-358">Second Inside Corp = Inside</span></span>        |

## <a name="report-filters"></a><span data-ttu-id="354ae-359">レポートフィルター</span><span class="sxs-lookup"><span data-stu-id="354ae-359">Report filters</span></span>

<span data-ttu-id="354ae-360">CQD レポートフィルターを使用して、調査の焦点を絞ることができます。</span><span class="sxs-lookup"><span data-stu-id="354ae-360">Use CQD report filters to narrow the focus of your investigations.</span></span> <span data-ttu-id="354ae-361">レポートフィルターを使用するには、レンダリングされたレポートにフィルターを追加します。</span><span class="sxs-lookup"><span data-stu-id="354ae-361">Use report filters by adding a filter to the rendered report either in the Query Editor or directly in the report.</span></span> <span data-ttu-id="354ae-362">次のレポートフィルターは、 [CQD テンプレート](https://aka.ms/QERtemplates)全体で使用されます。</span><span class="sxs-lookup"><span data-stu-id="354ae-362">The following report filters are used throughout the [CQD templates](https://aka.ms/QERtemplates).</span></span>


| <span data-ttu-id="354ae-363">フィルター</span><span class="sxs-lookup"><span data-stu-id="354ae-363">Filter</span></span>     | <span data-ttu-id="354ae-364">説明</span><span class="sxs-lookup"><span data-stu-id="354ae-364">Description</span></span>                            | <span data-ttu-id="354ae-365">CQD レポートフィルターの例</span><span class="sxs-lookup"><span data-stu-id="354ae-365">CQD report filter example</span></span>         |
|------------|----------------------------------------|-----------------------------------|
| <span data-ttu-id="354ae-366">Month</span><span class="sxs-lookup"><span data-stu-id="354ae-366">Month</span></span>      | <span data-ttu-id="354ae-367">最初の年から月までを開始します。</span><span class="sxs-lookup"><span data-stu-id="354ae-367">Start with the year first, then month.</span></span> | <span data-ttu-id="354ae-368">2017-10</span><span class="sxs-lookup"><span data-stu-id="354ae-368">2017-10</span></span>                           |
| <span data-ttu-id="354ae-369">昇順</span><span class="sxs-lookup"><span data-stu-id="354ae-369">Alphabetic</span></span> | <span data-ttu-id="354ae-370">任意のアルファベット文字をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="354ae-370">Filters for any alphabetic characters.</span></span> | <span data-ttu-id="354ae-371">[a-z]</span><span class="sxs-lookup"><span data-stu-id="354ae-371">[a-z]</span></span>                             |
| <span data-ttu-id="354ae-372">真数</span><span class="sxs-lookup"><span data-stu-id="354ae-372">Numeric</span></span>    | <span data-ttu-id="354ae-373">任意の数字をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="354ae-373">Filters for any numeric characters.</span></span>    | <span data-ttu-id="354ae-374">[0-9]</span><span class="sxs-lookup"><span data-stu-id="354ae-374">[0-9]</span></span>                             |
| <span data-ttu-id="354ae-375">パーセンテージ</span><span class="sxs-lookup"><span data-stu-id="354ae-375">Percentage</span></span> | <span data-ttu-id="354ae-376">フィルターでパーセンテージを指定します。</span><span class="sxs-lookup"><span data-stu-id="354ae-376">Filters for a percentage.</span></span>              | <span data-ttu-id="354ae-377">([3-9] \\ ) \|([3-9]) \|([1-9] [0-9])</span><span class="sxs-lookup"><span data-stu-id="354ae-377">([3-9]\\.)\|([3-9])\|([1-9][0-9])</span></span> |


### <a name="drill-down-filters"></a><span data-ttu-id="354ae-378">ドリルダウンフィルター</span><span class="sxs-lookup"><span data-stu-id="354ae-378">Drill-down filters</span></span>

<span data-ttu-id="354ae-379">CQD reports は、いくつかのドリルダウンフィルター機能を備えており、通話品質調査の焦点を絞るための強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="354ae-379">CQD reports feature several drill-down filters, which are powerful tools for narrowing the focus of your call-quality investigations.</span></span> <span data-ttu-id="354ae-380">ドリルダウンフィールドを選択すると、レポートによって適切なタブが自動的に開かれ、選択した値に基づいてフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="354ae-380">If you select a drill-down field, the report automatically opens the appropriate tab and filters on the selected value.</span></span> <span data-ttu-id="354ae-381">このタブに固有のドリルダウンフィールドがあり、1つが選択されている場合は、両方のフィルターセットが適用され、結果のデータセットが段階的に縮小されます。</span><span class="sxs-lookup"><span data-stu-id="354ae-381">If that tab has its own drill-down fields and one is selected, both sets of filters are applied, progressively narrowing the resulting data set.</span></span>

![ドリルダウンレポートフローを示す図](media/qerguide-image-drillthrureportflow.png)


#### <a name="adding-and-editing-drill-down-fields"></a><span data-ttu-id="354ae-383">ドリルダウンフィールドの追加と編集</span><span class="sxs-lookup"><span data-stu-id="354ae-383">Adding and editing drill-down fields</span></span>

<span data-ttu-id="354ae-384">レポートを編集するときに、クエリエディターを使用して独自のドリルダウンフィールドを指定するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="354ae-384">When editing a report, you have the option to specify drill-down fields of your own using the Query Editor.</span></span>

<span data-ttu-id="354ae-385">まず、[.. **.** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="354ae-385">Start by clicking **…**</span></span> <span data-ttu-id="354ae-386">編集するレポートの場合は、[**編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="354ae-386">for the report you want to edit, then select **Edit**.</span></span>

![ドリルダウンフィールドの編集のスクリーンショット](media/qerguide-image-addeditdrilldownfields.png)

<span data-ttu-id="354ae-388">クエリエディターの左側の一覧からディメンションを選びます。</span><span class="sxs-lookup"><span data-stu-id="354ae-388">Select a Dimension from the list on the left side of the Query Editor.</span></span> <span data-ttu-id="354ae-389">次に、[**移動**] ラベルの下にあるドロップダウンをクリックして、そのディメンションをドリルダウンするタブとエキスパンダーグループを選びます。</span><span class="sxs-lookup"><span data-stu-id="354ae-389">Then click on the dropdown below the **Navigate To** label and select the tab and expander group that you want that Dimension to drill through to.</span></span> <span data-ttu-id="354ae-390">注: 現在、ドリルダウン機能を使用するには、別のタブに移動します。</span><span class="sxs-lookup"><span data-stu-id="354ae-390">Note: Presently, drill-down functionality only works by navigating to different tabs.</span></span> <span data-ttu-id="354ae-391">特定の展開へのドリルスルーのサポートは、後で追加されます。</span><span class="sxs-lookup"><span data-stu-id="354ae-391">Support for drilling through to a specific expander will be added later.</span></span> <span data-ttu-id="354ae-392">最後に、[**閉じる**] をクリックして変更内容をディメンションに保存し、[**保存**] をクリックしてクエリエディターを閉じます。</span><span class="sxs-lookup"><span data-stu-id="354ae-392">Finally, click **Close** to save your changes to the Dimension, then click **Save** to save and close the Query Editor.</span></span>

![クエリエディターでディメンションを選択するスクリーンショット](media/qerguide-image-selectquerydimension.png)

### <a name="multi-select-filters"></a><span data-ttu-id="354ae-394">複数選択フィルター</span><span class="sxs-lookup"><span data-stu-id="354ae-394">Multi-select filters</span></span>

<span data-ttu-id="354ae-395">CQD では、ドリルダウン機能に加えて、複数の値 (またはフィルター) を使ったフィルターの指定もサポートされています。</span><span class="sxs-lookup"><span data-stu-id="354ae-395">In addition to drill-down functionality, CQD also supports specifying Filters with multiple values (OR filters).</span></span>

<span data-ttu-id="354ae-396">複数のフィルター値を選ぶには、まず新しいフィルターをレポートに追加します。</span><span class="sxs-lookup"><span data-stu-id="354ae-396">In order to select multiple filter values, begin by adding a new filter to the report.</span></span> <span data-ttu-id="354ae-397">[ **+** **フィルター** ] ラベルの横にあるをクリックし、使用するディメンションの名前を入力して、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="354ae-397">Click **+** beside the **Filters** label, enter the name of the Dimension you want to use, and click **Add**.</span></span>

![複数選択フィルターの追加のスクリーンショット](media/qerguide-image-addmultiselectfilter.png)

<span data-ttu-id="354ae-399">次に、[**検索**] (新しいフィルターの横の虫眼鏡アイコン) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="354ae-399">Then, click **Search** (a magnifying glass icon next to the new filter).</span></span> <span data-ttu-id="354ae-400">テキストフィールドと、 **[すべて選択] と [** **反転**] などのさまざまなオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="354ae-400">You'll see a text field, and a number of options, including **Select All** and **Invert**.</span></span> <span data-ttu-id="354ae-401">値を入力し、検索するフィールドの横にある [**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="354ae-401">Enter a value,  and click **Search** next to that field to search.</span></span> <span data-ttu-id="354ae-402">または、テキストフィールドを空白のままにして、[**検索**] をクリックすると、最初の100のオプションに移動します。</span><span class="sxs-lookup"><span data-stu-id="354ae-402">Alternatively, leave the text field empty and click **Search** to view up to the first 100 options.</span></span>

```PowerShell
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

<span data-ttu-id="354ae-403">例:</span><span class="sxs-lookup"><span data-stu-id="354ae-403">Example:</span></span>  

![クエリフィルターの追加のスクリーンショット](media/qerguide-image-addfilter.png)

### <a name="dashboard-level-filters"></a><span data-ttu-id="354ae-405">ダッシュボードレベルのフィルター</span><span class="sxs-lookup"><span data-stu-id="354ae-405">Dashboard level filters</span></span>
<span data-ttu-id="354ae-406">一部の CQD レポートには、ダッシュボードレベルのフィルターが追加されているため、一般的なパラメーターで簡単にフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="354ae-406">Certain CQD reports have dashboard-level filters added to them, making it easy to filter by common parameters.</span></span> <span data-ttu-id="354ae-407">これらのフィルターは、標準の [レポート] タブの外部に表示され、[製品] フィルターのすぐ下に表示され、ダッシュボードのすべてのフィルターに適用されます。</span><span class="sxs-lookup"><span data-stu-id="354ae-407">These filters appear outside the regular report tabs and directly beneath the Product filter, and they apply to all filters in the Dashboard.</span></span>

![ダッシュボードフィルターのスクリーンショット](media/qerguide-image-dashboardfilters.png)
```PowerShell
/filter/[AllStreams].[Is Teams]|[TRUE | FALSE]
```

### <a name="url-filters"></a><span data-ttu-id="354ae-409">URL フィルター</span><span class="sxs-lookup"><span data-stu-id="354ae-409">URL filters</span></span>

<span data-ttu-id="354ae-410">CQD は、URL へのフィルターの追加をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="354ae-410">CQD supports adding filters to the URL.</span></span> <span data-ttu-id="354ae-411">これにより、CQD クエリの共有やブックマークを簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="354ae-411">This makes it easy to share or bookmark a CQD query.</span></span> <span data-ttu-id="354ae-412">URL には、トレンドの月数、テナント ID、言語などのパラメーターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="354ae-412">You can define parameters in the URL, such as Trending Month, tenant ID, or language.</span></span> <span data-ttu-id="354ae-413">また、URL に製品またはダッシュボードレベルフィルターを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="354ae-413">You can also add Product or Dashboard level filters to the URL.</span></span>
<span data-ttu-id="354ae-414">CQD レポートからフェデレーションデータを除外することは、フェデレーションエンドポイントがレポートに影響を与える可能性のある、管理された建物またはネットワークをを修復するする場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="354ae-414">Excluding federated data from CQD reports is useful when you're remediating managed buildings or networks where federated endpoints might influence your reports.</span></span>

<span data-ttu-id="354ae-415">フィルターを追加するには、URL の末尾に次の内容を追加します。</span><span class="sxs-lookup"><span data-stu-id="354ae-415">To add a filter, append the following to the end of the URL:</span></span>

```
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

<span data-ttu-id="354ae-416">例:</span><span class="sxs-lookup"><span data-stu-id="354ae-416">Example:</span></span>  

```https://cqd.teams.microsoft.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Second Tenant Id]|[TENANTID]```

<span data-ttu-id="354ae-417">ダッシュボードレベルのフィルターを URL に追加するには、そのフィルターが製品またはダッシュボードレベルフィルターとして CQD 内に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="354ae-417">To add a Dashboard-level filter to a URL, that filter must exist in CQD as either a Product or Dashboard level filter.</span></span> <span data-ttu-id="354ae-418">次のフィルターを、トレンドの月の後に URL パラメーターの前にある URL に追加します。</span><span class="sxs-lookup"><span data-stu-id="354ae-418">Add these filters to the URL after the Trending Month and before the URL parameters:</span></span>

```filter/DATA_MODEL_NAME|VALUE```

<span data-ttu-id="354ae-419">たとえば、Microsoft Teams の製品フィルター値を適用するには、次のように追加します。</span><span class="sxs-lookup"><span data-stu-id="354ae-419">For example, to apply a Product filter value of Microsoft Teams, you'd add the following:</span></span>

```filter/[AllStreams].[Is%20Teams]|[True]```

<span data-ttu-id="354ae-420">URL 全体は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="354ae-420">Your entire URL would look something like this:</span></span>

```https://cqd.teams.microsoft.com/spd/#/Dashboard/2624085/2018-9/filter/[AllStreams].[Is%20Teams]|[True]```

<span data-ttu-id="354ae-421">複数選択値を持つ URL フィルターを適用するには、各値をパイプ (|) 文字で区切ります。</span><span class="sxs-lookup"><span data-stu-id="354ae-421">To apply URL filters with multi-select values, separate each value with a pipe ( | ) character.</span></span> <span data-ttu-id="354ae-422">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="354ae-422">For example:</span></span>

```filter/[AllStreams].[Media%20Type]|[Video]|[Audio]|[VBSS]```

<span data-ttu-id="354ae-423">無効な名前または値を指定した場合、URL フィルターは適用されません。</span><span class="sxs-lookup"><span data-stu-id="354ae-423">If you specify an invalid name or value, the URL filter won't be applied.</span></span>


<span data-ttu-id="354ae-424">URL フィルターを使用して、特定のディメンションのすべてのレポートをフィルター処理することができます。</span><span class="sxs-lookup"><span data-stu-id="354ae-424">You can use a URL filter to filter every report for a specific dimension.</span></span> <span data-ttu-id="354ae-425">最も一般的な URL フィルターは、フェデレーション参加者のテレメトリを除外するレポート、またはチームまたは Skype for Business Online のみにフォーカスするレポートをフィルター処理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="354ae-425">The most common URL filters are used to filter reports to exclude federated participant telemetry, or focus on only Teams or Skype for Business Online.</span></span> <span data-ttu-id="354ae-426">CQD レポートからフェデレーションデータを除外することは、フェデレーションエンドポイントがレポートに影響を与える可能性のある、管理された建物またはネットワークをを修復するする場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="354ae-426">Excluding federated data from CQD reports is useful when you're remediating managed buildings or networks where federated endpoints might influence your reports.</span></span>

| <span data-ttu-id="354ae-427">フィルター</span><span class="sxs-lookup"><span data-stu-id="354ae-427">Filter</span></span>         | <span data-ttu-id="354ae-428">説明</span><span class="sxs-lookup"><span data-stu-id="354ae-428">Description</span></span>          | <span data-ttu-id="354ae-429">CQD クエリフィルターの例</span><span class="sxs-lookup"><span data-stu-id="354ae-429">CQD query filter example</span></span>      |
|----------------|----------------------|-------------------------------|
| <span data-ttu-id="354ae-430">空白値はありません</span><span class="sxs-lookup"><span data-stu-id="354ae-430">No blank values</span></span>   | <span data-ttu-id="354ae-431">一部のフィルターには、空の値をフィルター処理するオプションがありません。</span><span class="sxs-lookup"><span data-stu-id="354ae-431">Some filters don't have the option to filter for blank values.</span></span> <span data-ttu-id="354ae-432">空の値を手動でフィルター処理するには、必要に応じて、空の式を使用し、フィルターを "等しい" または "Not Equals" に設定します。</span><span class="sxs-lookup"><span data-stu-id="354ae-432">To filter blank values manually, use the blank expression and set the filter to Equals or Not Equals, depending on your needs.</span></span>      | <span data-ttu-id="354ae-433">第2の建物 \<\> の名前 \^ \\\*\$</span><span class="sxs-lookup"><span data-stu-id="354ae-433">Second Building Name \<\> \^\\s\*\$</span></span>                       |
| <span data-ttu-id="354ae-434">共通サブネットを除外する</span><span class="sxs-lookup"><span data-stu-id="354ae-434">Exclude common subnets</span></span> | <span data-ttu-id="354ae-435">管理されていないネットワークから個別に管理するための有効な建物ファイルがない場合、ホームネットワークはレポートに含まれます。</span><span class="sxs-lookup"><span data-stu-id="354ae-435">Without a valid building file to separate managed from unmanaged networks, home networks will be included in the reports.</span></span> <span data-ttu-id="354ae-436">これらのホームサブネットは、その制御の範囲外であり、レポートからすばやく除外することができます。</span><span class="sxs-lookup"><span data-stu-id="354ae-436">These home subnets are outside the scope of IT's control and can be quickly excluded from a report.</span></span> <span data-ttu-id="354ae-437">この記事で定義されている一般的なサブネットは、10.0.0.0、192.168.1.0、192.168.0.0 です。</span><span class="sxs-lookup"><span data-stu-id="354ae-437">Common subnets, as defined in this article, are 10.0.0.0, 192.168.1.0 and 192.168.0.0.</span></span> | <span data-ttu-id="354ae-438">第2のサブネット \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="354ae-438">Second Subnet \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0</span></span> |
| <span data-ttu-id="354ae-439">内部でのみ表示</span><span class="sxs-lookup"><span data-stu-id="354ae-439">View inside only</span></span>  | <span data-ttu-id="354ae-440">管理対象 (内部) または非管理 (外部) のレポートをフィルター処理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="354ae-440">Used to filter a report for managed (inside) or unmanaged (outside).</span></span> <span data-ttu-id="354ae-441">管理された CQD テンプレートは、これらのフィルターで既に構成されています。</span><span class="sxs-lookup"><span data-stu-id="354ae-441">The managed CQD template is already preconfigured with these filters.</span></span>       | <span data-ttu-id="354ae-442">2番目の内部企業 = 内部</span><span class="sxs-lookup"><span data-stu-id="354ae-442">Second Inside Corp = Inside</span></span>        |


#### <a name="how-to-find-your-tenant-id"></a><span data-ttu-id="354ae-443">テナント ID を見つける方法</span><span class="sxs-lookup"><span data-stu-id="354ae-443">How to find your tenant ID</span></span>

<span data-ttu-id="354ae-444">CQD のテナント ID は、Azure のディレクトリ ID に対応しています。</span><span class="sxs-lookup"><span data-stu-id="354ae-444">The tenant ID in CQD corresponds to the Directory ID in Azure.</span></span> <span data-ttu-id="354ae-445">ディレクトリ ID がわからない場合は、Azure ポータルで見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="354ae-445">If you don't know your Directory ID, you can find it in the Azure portal:</span></span>

1.  <span data-ttu-id="354ae-446">Microsoft Azure ポータルにサインインします。<https://portal.azure.com></span><span class="sxs-lookup"><span data-stu-id="354ae-446">Sign in to the Microsoft Azure portal: <https://portal.azure.com></span></span>

2.  <span data-ttu-id="354ae-447">[ **Azure Active Directory**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="354ae-447">Select **Azure Active Directory**.</span></span>

3.  <span data-ttu-id="354ae-448">[**管理**] で [**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="354ae-448">Under **Manage**, select **Properties**.</span></span> <span data-ttu-id="354ae-449">テナント ID は [**ディレクトリ ID** ] ボックスにあります。</span><span class="sxs-lookup"><span data-stu-id="354ae-449">Your tenant ID is in the **Directory ID** box.</span></span>

<span data-ttu-id="354ae-450">PowerShell を使用して、テナント ID を見つけることもできます。</span><span class="sxs-lookup"><span data-stu-id="354ae-450">You can also find your tenant ID by using PowerShell:</span></span> 
  ```
  Login-AzureRmAccount
  ```



## <a name="comparing-teams-and-skype-for-business-cqd-data"></a><span data-ttu-id="354ae-451">Teams と Skype for Business の CQD データを比較する</span><span class="sxs-lookup"><span data-stu-id="354ae-451">Comparing Teams and Skype for Business CQD data</span></span>

<span data-ttu-id="354ae-452">最新の CQD (cqd.teams.microsoft.com) 内でも、Teams と Skype for Business の間でのデータの相違点が表示されます。</span><span class="sxs-lookup"><span data-stu-id="354ae-452">Even within the latest CQD (cqd.teams.microsoft.com), you'll see differences in data between Teams and Skype for Business.</span></span> <span data-ttu-id="354ae-453">いくつかの理由があります。</span><span class="sxs-lookup"><span data-stu-id="354ae-453">Some reasons:</span></span>
- <span data-ttu-id="354ae-454">パフォーマンスと信頼性を確保するためのメカニズムの違い</span><span class="sxs-lookup"><span data-stu-id="354ae-454">Differences in the mechanisms for ensuring performance and reliability</span></span>
  - <span data-ttu-id="354ae-455">チームは自動再接続と高速ローミングを備えています。</span><span class="sxs-lookup"><span data-stu-id="354ae-455">Teams has auto-reconnect and fast roaming.</span></span> <span data-ttu-id="354ae-456">Skype for Business は使用できません。</span><span class="sxs-lookup"><span data-stu-id="354ae-456">Skype for Business doesn't.</span></span>
  - <span data-ttu-id="354ae-457">チームには動的な帯域幅管理があります。</span><span class="sxs-lookup"><span data-stu-id="354ae-457">Teams has dynamic bandwidth management.</span></span> <span data-ttu-id="354ae-458">Skype for Business は使用できません。</span><span class="sxs-lookup"><span data-stu-id="354ae-458">Skype for Business doesn't.</span></span>
- <span data-ttu-id="354ae-459">チームと Skype for Business の間の[IP アドレス範囲](Office-365-URLs-IP-address-ranges.md)の違い</span><span class="sxs-lookup"><span data-stu-id="354ae-459">Differences in [IP address ranges](Office-365-URLs-IP-address-ranges.md) between Teams and Skype for Business.</span></span> <span data-ttu-id="354ae-460">Teams の IP 範囲が新しくなりました。ファイアウォールで接続の問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="354ae-460">The Teams IP ranges are newer, which could cause connectivity problems at the firewall.</span></span>

## <a name="open-cqd-from-the-skype-for-business-legacy-portal"></a><span data-ttu-id="354ae-461">Skype for Business のレガシポータルから CQD を開く</span><span class="sxs-lookup"><span data-stu-id="354ae-461">Open CQD from the Skype for Business legacy portal</span></span>

<span data-ttu-id="354ae-462">![Skype for business の ](media/sfb-logo-30x30.png) **レガシポータルを使用し**た skype for business ロゴのアイコン</span><span class="sxs-lookup"><span data-stu-id="354ae-462">![An icon of the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business legacy portal**</span></span>

1. <span data-ttu-id="354ae-463">管理者アカウントを使用して Office 365 組織にサインインし、[**管理者**] タイルを選んで管理センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="354ae-463">Sign in to your Office 365 organization using an admin account, and then select the **Admin** tile to open the Admin center.</span></span>
2. <span data-ttu-id="354ae-464">左側のウィンドウの [**管理センター**] で、[ **Microsoft teams** ] を選択して teams 管理センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="354ae-464">In the left pane, under **Admin centers**, select **Microsoft Teams** to open the Teams admin center.</span></span>
3. <span data-ttu-id="354ae-465">Teams 管理センターで、左側のウィンドウで [**従来のポータル**] を選び、[**ツール**]、[ **Skype For business Online 通話品質ダッシュボード**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="354ae-465">In the Teams admin center, select **Legacy Portal** in the left pane, select **Tools**, and then select **Skype for Business Online Call Quality Dashboard**.</span></span>

     ![スクリーンショット: 通話品質ダッシュボードを選択します。](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)

4. <span data-ttu-id="354ae-467">表示されたページで、グローバル管理者アカウントでサインインし、メッセージが表示されたらアカウントの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="354ae-467">On the page that opens, sign in with your Global Administrator account, and then provide the credentials for the account when prompted.</span></span>

<span data-ttu-id="354ae-468">初めてサインインすると、CQD でデータの収集と処理が開始されます。</span><span class="sxs-lookup"><span data-stu-id="354ae-468">After the first time you sign in, CQD will begin collecting and processing data.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="354ae-469">2019年12月以降、古いバージョンの CQD (cqd.lync.com) にアクセスできます。ただし、従来のポータルでは、最新の CQD (cqd.teams.microsoft.com) へのリンクが提供されています。</span><span class="sxs-lookup"><span data-stu-id="354ae-469">As of December 2019, you can still access the older version of CQD (cqd.lync.com), although the legacy portal gives you a link to the latest CQD (cqd.teams.microsoft.com).</span></span> <span data-ttu-id="354ae-470">最終的には、古いバージョンの CQD が廃止されます。</span><span class="sxs-lookup"><span data-stu-id="354ae-470">Eventually, the older version of CQD will be decommissioned.</span></span> <span data-ttu-id="354ae-471">2020年7月1日以降、古いバージョンの CQD では、新しい CQD からデータにアクセス https://CQD.teams.microsoft.com) できます ()。建物やレポートのデータをエクスポートすることはできなくなりました。</span><span class="sxs-lookup"><span data-stu-id="354ae-471">As of July 1, 2020, the older version of CQD accesses data from the new CQD (https://CQD.teams.microsoft.com), and you can no longer export building and report data.</span></span> <span data-ttu-id="354ae-472">2020の遅延があるときは、古い CQD を無効にします。これでアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="354ae-472">Sometime in late 2020, we'll turn off the old CQD and you'll no longer be able to access it.</span></span>


## <a name="related-topics"></a><span data-ttu-id="354ae-473">関連トピック</span><span class="sxs-lookup"><span data-stu-id="354ae-473">Related topics</span></span>

[<span data-ttu-id="354ae-474">Teams の通話品質を向上させて監視する</span><span class="sxs-lookup"><span data-stu-id="354ae-474">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="354ae-475">CQD とは何ですか?</span><span class="sxs-lookup"><span data-stu-id="354ae-475">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="354ae-476">通話品質ダッシュボード (CQD) を設定する</span><span class="sxs-lookup"><span data-stu-id="354ae-476">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="354ae-477">テナントのアップロードとデータの構築</span><span class="sxs-lookup"><span data-stu-id="354ae-477">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="354ae-478">CQD を使用して通話と会議の品質を管理する</span><span class="sxs-lookup"><span data-stu-id="354ae-478">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="354ae-479">CQD で使用できるディメンションとメジャー</span><span class="sxs-lookup"><span data-stu-id="354ae-479">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="354ae-480">CQD でのストリームの分類</span><span class="sxs-lookup"><span data-stu-id="354ae-480">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="354ae-481">Power BI を使用して CQD データを分析する</span><span class="sxs-lookup"><span data-stu-id="354ae-481">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)
