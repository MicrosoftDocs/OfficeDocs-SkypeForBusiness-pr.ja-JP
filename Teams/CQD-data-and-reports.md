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
ms.openlocfilehash: 2d36787a5341db016c18a30977cb086b0b6d7afc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111543"
---
# <a name="data-and-reports-in-call-quality-dashboard-cqd"></a><span data-ttu-id="0107e-103">通話品質ダッシュボード (CQD) のデータとレポート</span><span class="sxs-lookup"><span data-stu-id="0107e-103">Data and reports in Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="0107e-104">Microsoft 通話品質ダッシュボード (CQD) では、ほぼリアルタイム (NRT) データ フィードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="0107e-104">Microsoft Call Quality Dashboard (CQD) uses a near-real-time (NRT) data feed.</span></span> <span data-ttu-id="0107e-105">通話レコードは、通話の終了から 30 分以内に CQD で利用できます。</span><span class="sxs-lookup"><span data-stu-id="0107e-105">Call records are available in CQD within 30 minutes of the end of a call.</span></span> <span data-ttu-id="0107e-106">NRT パイプラインからの呼び出しレコードは、データ セットから削除される前の数か月間のみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="0107e-106">Call records from the NRT pipeline are only available for a few months before they are removed from the data set.</span></span> 


## <a name="many-ways-to-access-cqd-data"></a><span data-ttu-id="0107e-107">CQD データにアクセスする多くの方法</span><span class="sxs-lookup"><span data-stu-id="0107e-107">Many ways to access CQD data</span></span>

<span data-ttu-id="0107e-108">CQD データには、さまざまな方法でアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="0107e-108">You can access CQD data by several different avenues.</span></span> <span data-ttu-id="0107e-109">ニーズに最も合った 1 つを選択します。</span><span class="sxs-lookup"><span data-stu-id="0107e-109">Pick the one that best meets your needs:</span></span>

|  |  |
|---------|---------|
|<span data-ttu-id="0107e-110">Teams 管理センター [( https://admin.teams.microsoft.com) ](https://admin.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="0107e-110">Teams admin center [(https://admin.teams.microsoft.com)](https://admin.teams.microsoft.com)</span></span>    | <span data-ttu-id="0107e-111">CQD データは Teams管理センターの [ユーザー] ページに含まれており、必要な最も一般的なデータが読みやすく表示されます。</span><span class="sxs-lookup"><span data-stu-id="0107e-111">CQD data is included on the **Users** page in the Teams admin center, showing the most common data you need in an easy-to-read format.</span></span> <span data-ttu-id="0107e-112">[ユーザー] の下にある CQD データをカスタマイズ **できない**。</span><span class="sxs-lookup"><span data-stu-id="0107e-112">You can't customize CQD data that you find under **Users**.</span></span>  |
|<span data-ttu-id="0107e-113">CQD ポータル[( https://cqd.teams.microsoft.com) ](https://cqd.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="0107e-113">CQD portal [(https://cqd.teams.microsoft.com)](https://cqd.teams.microsoft.com)</span></span>     | <span data-ttu-id="0107e-114">ドリルスルー フィルターを使用して、ほとんどのニーズを満たす堅牢なサマリー レポートと詳細レポート。</span><span class="sxs-lookup"><span data-stu-id="0107e-114">Robust summary and detailed reports that meet most needs, with drill-through filtering.</span></span> <span data-ttu-id="0107e-115">CQD ポータルでレポートをカスタマイズすることもできます。</span><span class="sxs-lookup"><span data-stu-id="0107e-115">You can also customize reports in the CQD portal.</span></span> <br><br><span data-ttu-id="0107e-116">[CQD ポータルでデータを分析](#import-the-cqd-report-templates)するのに役立つ 2 つの CQD レポート テンプレートを取得します。</span><span class="sxs-lookup"><span data-stu-id="0107e-116">Get two [CQD report templates](#import-the-cqd-report-templates) to help you analyze data in the CQD portal.</span></span>       |
|<span data-ttu-id="0107e-117">Power BI</span><span class="sxs-lookup"><span data-stu-id="0107e-117">Power BI</span></span>     | <span data-ttu-id="0107e-118">カスタマイズ可能な Power BI テンプレートを使用して、直接クエリを使用して Power BI で [CQD データを表示します](CQD-Power-BI-query-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="0107e-118">Use direct queries to view your CQD data in Power BI using [customizable Power BI templates](CQD-Power-BI-query-templates.md).</span></span> <span data-ttu-id="0107e-119">[CQD 用の Power BI クエリ テンプレートをダウンロードします](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="0107e-119">[Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span><br><br><span data-ttu-id="0107e-120">REST API を [使用して、Power](/skypeforbusiness/management-tools/call-quality-dashboard/data-api) BI を介して CQD データにアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="0107e-120">You can also [use the REST API to access CQD data](/skypeforbusiness/management-tools/call-quality-dashboard/data-api) through Power BI.</span></span> <span data-ttu-id="0107e-121">CQD データをダウンロードしてオフラインで作業する場合は、この方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="0107e-121">Use this method if you want to download your CQD data so you can work on it offline.</span></span> <span data-ttu-id="0107e-122">この方法を使用する利点は、パフォーマンスが向上し、特にオンラインのときに Power BI で大きなデータ セットが低下する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="0107e-122">The benefit of using this method is better performance, especially useful for large data sets that bog down in Power BI when you're online.</span></span>       |
|<span data-ttu-id="0107e-123">Graph API</span><span class="sxs-lookup"><span data-stu-id="0107e-123">Graph API</span></span>     | <span data-ttu-id="0107e-124">Graph API を使用して、通話品質データに [自分でアクセスします](/graph/api/resources/callrecords-api-overview?view=graph-rest-beta)。</span><span class="sxs-lookup"><span data-stu-id="0107e-124">Access call quality data yourself using the [Graph API](/graph/api/resources/callrecords-api-overview?view=graph-rest-beta).</span></span> <span data-ttu-id="0107e-125">これは最も複雑な方法ですが、通話品質データを最も柔軟に分析できます。</span><span class="sxs-lookup"><span data-stu-id="0107e-125">This is the most complex method, but it gives you the most control and flexibility in analyzing your call quality data.</span></span> <span data-ttu-id="0107e-126">たとえば、組織の他のデータと結合する必要がある場合は、Graph API を使用してデータ モデルを作成し、通話品質データを取り込むできます。</span><span class="sxs-lookup"><span data-stu-id="0107e-126">For example, if you need to join it with other data for your organization, you can use the Graph API to create a data model and incorporate call quality data.</span></span>        |

## <a name="import-the-cqd-report-templates"></a><span data-ttu-id="0107e-127">CQD レポート テンプレートをインポートする</span><span class="sxs-lookup"><span data-stu-id="0107e-127">Import the CQD report templates</span></span>

<span data-ttu-id="0107e-128">[CQD レポート](https://aka.ms/qertemplates)テンプレート (すべてのネットワークと管理ネットワーク) を 2 つダウンロードすると、CQD をすばやく利用できます。</span><span class="sxs-lookup"><span data-stu-id="0107e-128">Download [two curated CQD report templates](https://aka.ms/qertemplates) (All Networks and Managed Networks) to help you get up to speed quickly with CQD.</span></span> <span data-ttu-id="0107e-129">建物データ ファイルの使用に最適化された All Networks テンプレートは、次のセクションで説明するように、建物情報の収集と CQD へのアップロードに向けて取り組む間に使用できます。</span><span class="sxs-lookup"><span data-stu-id="0107e-129">The All Networks template, though optimized to work with a building data file, can be used while you work toward collecting and uploading building information into CQD, as described in the next section.</span></span>

<span data-ttu-id="0107e-130">**テンプレートをインポートするには (.CQDX) を CQD に変換する**</span><span class="sxs-lookup"><span data-stu-id="0107e-130">**To import the templates (.CQDX) into CQD**</span></span>

1. <span data-ttu-id="0107e-131">CQD で、ページ **の** 上部にあるメニューから [詳細レポート] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0107e-131">In CQD, select **Detailed Reports** from the menu at the top of the page.</span></span>

2. <span data-ttu-id="0107e-132">左側のパネルで、[インポート] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="0107e-132">In the left panel, select **Import**.</span></span> <span data-ttu-id="0107e-133">最初の CQDX テンプレートを参照し、[開く] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="0107e-133">Browse to the first CQDX template and select **Open**.</span></span>

3. <span data-ttu-id="0107e-134">テンプレートがアップロードされると、ポップアップ ウィンドウに "レポートのインポートは成功しました" というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0107e-134">After the template is uploaded, a pop-up window will display the message "Report import was successful."</span></span> 

4. <span data-ttu-id="0107e-135">手順 2 と 3 を 2 つ目の CQD テンプレートに対して繰り返します。</span><span class="sxs-lookup"><span data-stu-id="0107e-135">Repeat steps 2 and 3 for the second CQD template.</span></span>

   > [!NOTE]
   > <span data-ttu-id="0107e-136">各ユーザーは CQD テンプレートを CQD インスタンスにインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0107e-136">Each user must import the CQD templates into their CQD instance.</span></span> 



## <a name="euii-data"></a><span data-ttu-id="0107e-137">EUII データ</span><span class="sxs-lookup"><span data-stu-id="0107e-137">EUII data</span></span>

<span data-ttu-id="0107e-138">コンプライアンス上の理由から、エンド ユーザーを特定できる情報 (EUII) データ (個人を特定できる情報または PII とも呼ばれる) は 28 日間のみ保持されます。</span><span class="sxs-lookup"><span data-stu-id="0107e-138">For compliance reasons, end-user identifiable information (EUII) data (also known as personally-identifiable information or PII) is only kept for 28 days.</span></span> <span data-ttu-id="0107e-139">NRT データが 28 日間のマークと交わると、EUII を含むフィールドがクリアされ、結果として EUII フリーの NRT データが生成されます。</span><span class="sxs-lookup"><span data-stu-id="0107e-139">As NRT data crosses the 28-day mark, fields that contain EUII are cleared, resulting in EUII-free NRT data.</span></span> <span data-ttu-id="0107e-140">EUII データを含むフィールドは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0107e-140">Fields that contain EUII data are:</span></span>

- <span data-ttu-id="0107e-141">完全な IP アドレス</span><span class="sxs-lookup"><span data-stu-id="0107e-141">Full IP address</span></span>
- <span data-ttu-id="0107e-142">メディア アクセス制御 (MAC) アドレス</span><span class="sxs-lookup"><span data-stu-id="0107e-142">Media Access Control (MAC) Address</span></span>
- <span data-ttu-id="0107e-143">基本サービス セット識別子 (BSSID)</span><span class="sxs-lookup"><span data-stu-id="0107e-143">Basic Service Set identifier (BSSID)</span></span>
- <span data-ttu-id="0107e-144">セッション開始プロトコル (SIP) URI (Skype for Business のみ)</span><span class="sxs-lookup"><span data-stu-id="0107e-144">Session Initiation Protocol (SIP) URI (Skype for Business only)</span></span>
- <span data-ttu-id="0107e-145">ユーザー プリンシパル名 (UPN)</span><span class="sxs-lookup"><span data-stu-id="0107e-145">User Principal Name (UPN)</span></span>
- <span data-ttu-id="0107e-146">マシン エンドポイント名</span><span class="sxs-lookup"><span data-stu-id="0107e-146">Machine Endpoint Name</span></span>
- <span data-ttu-id="0107e-147">ユーザーの詳細なフィードバック</span><span class="sxs-lookup"><span data-stu-id="0107e-147">User Verbatim Feedback</span></span>
- <span data-ttu-id="0107e-148">オブジェクト ID (エンドポイントのユーザーの Active Directory オブジェクト ID)</span><span class="sxs-lookup"><span data-stu-id="0107e-148">Object ID (the Active Directory object ID of the endpoint's user)</span></span>

### <a name="admin-roles-with-and-without-euii-access"></a><span data-ttu-id="0107e-149">EUII アクセスを使用する場合とアクセスしない場合の管理者ロール</span><span class="sxs-lookup"><span data-stu-id="0107e-149">Admin roles with and without EUII access</span></span>

<span data-ttu-id="0107e-150">次の [RBAC](/azure/role-based-access-control/overview) ロール **には、EUII** アクセスがあります。</span><span class="sxs-lookup"><span data-stu-id="0107e-150">These [RBAC](/azure/role-based-access-control/overview) roles **DO** have EUII access:</span></span>
- <span data-ttu-id="0107e-151">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="0107e-151">Global Admin</span></span>
- <span data-ttu-id="0107e-152">Teams サービス管理者</span><span class="sxs-lookup"><span data-stu-id="0107e-152">Teams Service Admin</span></span>
- <span data-ttu-id="0107e-153">Teams Communications Admin</span><span class="sxs-lookup"><span data-stu-id="0107e-153">Teams Communications Admin</span></span>
- <span data-ttu-id="0107e-154">Teams 通信サポート エンジニア</span><span class="sxs-lookup"><span data-stu-id="0107e-154">Teams Communications Support Engineer</span></span>
- <span data-ttu-id="0107e-155">グローバル リーダー</span><span class="sxs-lookup"><span data-stu-id="0107e-155">Global Reader</span></span>
- <span data-ttu-id="0107e-156">Skype for Business 管理者</span><span class="sxs-lookup"><span data-stu-id="0107e-156">Skype for Business Admin</span></span>

<span data-ttu-id="0107e-157">次の RBAC **ロールには** 、EUII アクセス権が付与されています。</span><span class="sxs-lookup"><span data-stu-id="0107e-157">These RBAC roles **DON'T** have EUII access:</span></span>
- <span data-ttu-id="0107e-158">レポート リーダー</span><span class="sxs-lookup"><span data-stu-id="0107e-158">Reports Reader</span></span>
- <span data-ttu-id="0107e-159">Teams 通信サポート スペシャリスト</span><span class="sxs-lookup"><span data-stu-id="0107e-159">Teams Communications Support Specialist</span></span>


## <a name="date-controls"></a><span data-ttu-id="0107e-160">日付コントロール</span><span class="sxs-lookup"><span data-stu-id="0107e-160">Date controls</span></span>

<span data-ttu-id="0107e-161">CQD では、次のローリング 傾向の種類がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0107e-161">CQD supports the following Rolling Trend types:</span></span>

- <span data-ttu-id="0107e-162">5 日間</span><span class="sxs-lookup"><span data-stu-id="0107e-162">5-day</span></span>
- <span data-ttu-id="0107e-163">7 日間</span><span class="sxs-lookup"><span data-stu-id="0107e-163">7-day</span></span>
- <span data-ttu-id="0107e-164">30 日間</span><span class="sxs-lookup"><span data-stu-id="0107e-164">30-day</span></span>
- <span data-ttu-id="0107e-165">60 日間</span><span class="sxs-lookup"><span data-stu-id="0107e-165">60-day</span></span>
- <span data-ttu-id="0107e-166">90 日間</span><span class="sxs-lookup"><span data-stu-id="0107e-166">90-day</span></span>

<span data-ttu-id="0107e-167">URL Date パラメーターは Day フィールドを受け入れる。</span><span class="sxs-lookup"><span data-stu-id="0107e-167">The URL Date parameter accepts a Day field.</span></span> <span data-ttu-id="0107e-168">ローリング 日レポートでは、傾向の最終日として YYYY-MM-DD 形式で指定された日付が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0107e-168">Rolling-day reports use dates specified in the YYYY-MM-DD format as the last day of the trend.</span></span> <span data-ttu-id="0107e-169">URL Date パラメーター "00" は "today" を示します。</span><span class="sxs-lookup"><span data-stu-id="0107e-169">The URL Date parameter “00”  indicates “today”.</span></span>

|<span data-ttu-id="0107e-170">URL</span><span class="sxs-lookup"><span data-stu-id="0107e-170">URL</span></span>| <span data-ttu-id="0107e-171">ローリング デイ傾向の終了日</span><span class="sxs-lookup"><span data-stu-id="0107e-171">End date of Rolling Day Trend</span></span>|
|:---|:---|
|<span data-ttu-id="0107e-172"><span>https:// <cqdv3> /spd/#/Dashboard/ <reportid> /2019-02/</span></span><span class="sxs-lookup"><span data-stu-id="0107e-172"><span>https://<cqdv3>/spd/#/Dashboard/<reportid>/2019-02/</span></span></span>   |<span data-ttu-id="0107e-173">2019 年 2 月の現在の日</span><span class="sxs-lookup"><span data-stu-id="0107e-173">Current Day of Feb 2019</span></span>|
|<span data-ttu-id="0107e-174"><span>https:// <cqdv3> /spd/#/Dashboard/ <reportid> /2019-02-15/</span></span><span class="sxs-lookup"><span data-stu-id="0107e-174"><span>https://<cqdv3>/spd/#/Dashboard/<reportid>/2019-02-15/</span></span></span>|<span data-ttu-id="0107e-175">2019 年 2 月 15 日</span><span class="sxs-lookup"><span data-stu-id="0107e-175">Feb 15, 2019</span></span>|
|<span data-ttu-id="0107e-176"><span>https:// <cqdv3> /spd/#/Dashboard/ <reportid> /00/</span></span><span class="sxs-lookup"><span data-stu-id="0107e-176"><span>https://<cqdv3>/spd/#/Dashboard/<reportid>/00/</span></span></span>        |<span data-ttu-id="0107e-177">現在の日</span><span class="sxs-lookup"><span data-stu-id="0107e-177">Current Day</span></span>|
|||

<span data-ttu-id="0107e-178">既定では、月の現在の日が、ローリング デイ傾向の最終日として使用されます。</span><span class="sxs-lookup"><span data-stu-id="0107e-178">By default, the current day of the month is used as the last day of the Rolling Day Trend.</span></span>


## <a name="data-available-in-cqd-reports"></a><span data-ttu-id="0107e-179">CQD レポートで使用可能なデータ</span><span class="sxs-lookup"><span data-stu-id="0107e-179">Data available in CQD reports</span></span>

<span data-ttu-id="0107e-180">既定の概要と詳細な CQD レポートは、組織の通話品質を管理するために必要なすべてである場合があります。必要に応じて、カスタム レポート [を作成できます](#create-custom-detailed-reports)。</span><span class="sxs-lookup"><span data-stu-id="0107e-180">The default summary and detailed CQD reports may be all you need to manage call quality for your org. If you need to, you can [create custom reports](#create-custom-detailed-reports).</span></span> 

<span data-ttu-id="0107e-181">Power BI を使用して CQD データを分析する場合は、「Power BI を使用して Teams の [CQD データを分析](CQD-Power-BI-query-templates.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0107e-181">If you want to use Power BI to analyze your CQD data, read [Use Power BI to analyze CQD data for Teams](CQD-Power-BI-query-templates.md).</span></span>

|<span data-ttu-id="0107e-182">機能</span><span class="sxs-lookup"><span data-stu-id="0107e-182">Feature</span></span>|<span data-ttu-id="0107e-183">概要レポート</span><span class="sxs-lookup"><span data-stu-id="0107e-183">Summary Reports</span></span>|<span data-ttu-id="0107e-184">詳細レポート</span><span class="sxs-lookup"><span data-stu-id="0107e-184">Detailed Reports</span></span>|
|:--- |:--- |:--- |
|<span data-ttu-id="0107e-185">アプリケーション共有メトリック</span><span class="sxs-lookup"><span data-stu-id="0107e-185">Application sharing metric</span></span> | <span data-ttu-id="0107e-186">いいえ</span><span class="sxs-lookup"><span data-stu-id="0107e-186">No</span></span> | <span data-ttu-id="0107e-187">はい</span><span class="sxs-lookup"><span data-stu-id="0107e-187">Yes</span></span> |
|<span data-ttu-id="0107e-188">顧客の建物情報のサポート</span><span class="sxs-lookup"><span data-stu-id="0107e-188">Customer building information support</span></span> | <span data-ttu-id="0107e-189">はい</span><span class="sxs-lookup"><span data-stu-id="0107e-189">Yes</span></span> | <span data-ttu-id="0107e-190">はい</span><span class="sxs-lookup"><span data-stu-id="0107e-190">Yes</span></span> |
|<span data-ttu-id="0107e-191">顧客のエンドポイント情報のサポート</span><span class="sxs-lookup"><span data-stu-id="0107e-191">Customer endpoint information support</span></span> | <span data-ttu-id="0107e-192">cqd.teams.microsoft.com <span><span/></span><span class="sxs-lookup"><span data-stu-id="0107e-192">Only in <span>cqd.teams.microsoft.com<span/></span></span> | <span data-ttu-id="0107e-193">cqd.teams.microsoft.com <span><span/></span><span class="sxs-lookup"><span data-stu-id="0107e-193">Only in <span>cqd.teams.microsoft.com<span/></span></span> |
|<span data-ttu-id="0107e-194">ドリルダウン分析のサポート</span><span class="sxs-lookup"><span data-stu-id="0107e-194">Drill down analysis support</span></span>   | <span data-ttu-id="0107e-195">いいえ</span><span class="sxs-lookup"><span data-stu-id="0107e-195">No</span></span>   | <span data-ttu-id="0107e-196">はい</span><span class="sxs-lookup"><span data-stu-id="0107e-196">Yes</span></span>   |
|<span data-ttu-id="0107e-197">メディアの信頼性に関する指標</span><span class="sxs-lookup"><span data-stu-id="0107e-197">Media reliability metrics</span></span>   | <span data-ttu-id="0107e-198">いいえ</span><span class="sxs-lookup"><span data-stu-id="0107e-198">No</span></span>   | <span data-ttu-id="0107e-199">はい</span><span class="sxs-lookup"><span data-stu-id="0107e-199">Yes</span></span>   |
|<span data-ttu-id="0107e-200">使い切ったレポート</span><span class="sxs-lookup"><span data-stu-id="0107e-200">Out-of-the-box reports</span></span>   | <span data-ttu-id="0107e-201">はい</span><span class="sxs-lookup"><span data-stu-id="0107e-201">Yes</span></span>   | <span data-ttu-id="0107e-202">はい</span><span class="sxs-lookup"><span data-stu-id="0107e-202">Yes</span></span>   |
|<span data-ttu-id="0107e-203">概要レポート</span><span class="sxs-lookup"><span data-stu-id="0107e-203">Overview reports</span></span>   | <span data-ttu-id="0107e-204">はい</span><span class="sxs-lookup"><span data-stu-id="0107e-204">Yes</span></span>   | <span data-ttu-id="0107e-205">はい</span><span class="sxs-lookup"><span data-stu-id="0107e-205">Yes</span></span>   |
|<span data-ttu-id="0107e-206">ユーザーごとのレポート セット</span><span class="sxs-lookup"><span data-stu-id="0107e-206">Per-user report set</span></span>   | <span data-ttu-id="0107e-207">いいえ</span><span class="sxs-lookup"><span data-stu-id="0107e-207">No</span></span>   | <span data-ttu-id="0107e-208">はい</span><span class="sxs-lookup"><span data-stu-id="0107e-208">Yes</span></span>   |
|<span data-ttu-id="0107e-209">レポート セットのカスタマイズ (レポートの追加、削除、変更)</span><span class="sxs-lookup"><span data-stu-id="0107e-209">Report set customization (add, delete, modify reports)</span></span>   | <span data-ttu-id="0107e-210">いいえ</span><span class="sxs-lookup"><span data-stu-id="0107e-210">No</span></span>   | <span data-ttu-id="0107e-211">はい</span><span class="sxs-lookup"><span data-stu-id="0107e-211">Yes</span></span>   |
|<span data-ttu-id="0107e-212">ビデオベースの画面共有メトリック</span><span class="sxs-lookup"><span data-stu-id="0107e-212">Video-based screen sharing metrics</span></span>   | <span data-ttu-id="0107e-213">いいえ</span><span class="sxs-lookup"><span data-stu-id="0107e-213">No</span></span>   | <span data-ttu-id="0107e-214">はい</span><span class="sxs-lookup"><span data-stu-id="0107e-214">Yes</span></span>   |
|<span data-ttu-id="0107e-215">ビデオのメトリック</span><span class="sxs-lookup"><span data-stu-id="0107e-215">Video metrics</span></span>   | <span data-ttu-id="0107e-216">いいえ</span><span class="sxs-lookup"><span data-stu-id="0107e-216">No</span></span>   | <span data-ttu-id="0107e-217">はい</span><span class="sxs-lookup"><span data-stu-id="0107e-217">Yes</span></span>   |
|<span data-ttu-id="0107e-218">利用可能なデータの量</span><span class="sxs-lookup"><span data-stu-id="0107e-218">Amount of data available</span></span>   | <span data-ttu-id="0107e-219">過去 12 か月間</span><span class="sxs-lookup"><span data-stu-id="0107e-219">Last 12 months</span></span>   | <span data-ttu-id="0107e-220">過去 12 か月間</span><span class="sxs-lookup"><span data-stu-id="0107e-220">Last 12 months</span></span>   |
|<span data-ttu-id="0107e-221">Microsoft Teams データ</span><span class="sxs-lookup"><span data-stu-id="0107e-221">Microsoft Teams data</span></span>   | <span data-ttu-id="0107e-222">はい</span><span class="sxs-lookup"><span data-stu-id="0107e-222">Yes</span></span>   | <span data-ttu-id="0107e-223">はい</span><span class="sxs-lookup"><span data-stu-id="0107e-223">Yes</span></span>   |
| | | |


 
### <a name="select-product-data-to-see-in-reports"></a><span data-ttu-id="0107e-224">レポートに表示する製品データを選択する</span><span class="sxs-lookup"><span data-stu-id="0107e-224">Select product data to see in reports</span></span>

<span data-ttu-id="0107e-225">概要レポートと Location-Enhanced レポートでは、[製品フィルター] ドロップダウンを使用して、すべての製品データ、Microsoft Teams データのみ、または Skype for Business Online データのみを表示できます。</span><span class="sxs-lookup"><span data-stu-id="0107e-225">In the Summary and Location-Enhanced Reports, you can use the **Product Filter** drop-down to show all product data, only Microsoft Teams data, or only Skype for Business Online data.</span></span>
  
![スクリーンショット: [製品フィルター] コントロール オプションを示す](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
<span data-ttu-id="0107e-227">詳細レポートでは **、[Is Teams]** ディメンションを使用して、データを Microsoft Teams または Skype for Business Online データにフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="0107e-227">In Detailed reports, you can use the **Is Teams** dimension to filter the data to Microsoft Teams or Skype for Business Online data.</span></span>

## <a name="summary-reports"></a><span data-ttu-id="0107e-228">概要レポート</span><span class="sxs-lookup"><span data-stu-id="0107e-228">Summary Reports</span></span>

<span data-ttu-id="0107e-229">これらは、CQD に初めてサインインするときに CQD ダッシュボードに表示されるレポートです。</span><span class="sxs-lookup"><span data-stu-id="0107e-229">These are the reports that you'll see on the CQD Dashboard when you first sign in to CQD.</span></span> <span data-ttu-id="0107e-230">日次、月次、およびテーブル レポートを使用して品質の傾向を一目で確認し、品質の低いサブネットの識別を支援します。</span><span class="sxs-lookup"><span data-stu-id="0107e-230">They give you an at-a-glance look at quality trends with daily, monthly, and table reports to assist with identifying subnets that have poor quality.</span></span> 

| <span data-ttu-id="0107e-231">Tab</span><span class="sxs-lookup"><span data-stu-id="0107e-231">Tab</span></span> | <span data-ttu-id="0107e-232">説明</span><span class="sxs-lookup"><span data-stu-id="0107e-232">Description</span></span> |
|---------|---------|
|<span data-ttu-id="0107e-233">全体的な通話品質</span><span class="sxs-lookup"><span data-stu-id="0107e-233">Overall Call Quality</span></span>     | <span data-ttu-id="0107e-234">他の 3 つのタブの集計。</span><span class="sxs-lookup"><span data-stu-id="0107e-234">Aggregate of the other 3 tabs.</span></span>       |
|<span data-ttu-id="0107e-235">サーバー — クライアント</span><span class="sxs-lookup"><span data-stu-id="0107e-235">Server—Client</span></span>     |<span data-ttu-id="0107e-236">サーバーエンドポイントとクライアント エンドポイント間のストリームの詳細。</span><span class="sxs-lookup"><span data-stu-id="0107e-236">Details of the streams between server and client endpoints.</span></span>        |
|<span data-ttu-id="0107e-237">クライアント — クライアント</span><span class="sxs-lookup"><span data-stu-id="0107e-237">Client—Client</span></span>     |<span data-ttu-id="0107e-238">2 つのクライアント エンドポイント間のストリームの詳細。</span><span class="sxs-lookup"><span data-stu-id="0107e-238">Details of the streams between two client endpoints.</span></span>        |
|<span data-ttu-id="0107e-239">音声品質 SLA</span><span class="sxs-lookup"><span data-stu-id="0107e-239">Voice Quality SLA</span></span>     |<span data-ttu-id="0107e-240">Skype for Business の音声品質 SLA に含まれる通話に関 [する情報](https://go.microsoft.com/fwlink/p/?linkid=846252)。</span><span class="sxs-lookup"><span data-stu-id="0107e-240">Info about calls included in the Skype for Business voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span>        |

### <a name="overall-call-quality-tab"></a><span data-ttu-id="0107e-241">[全体的な通話品質] タブ</span><span class="sxs-lookup"><span data-stu-id="0107e-241">Overall Call Quality tab</span></span>

<span data-ttu-id="0107e-242">このタブのデータを使用して、通話品質の状態と傾向をストリーム数と低品質のパーセンテージに基づいて評価します。</span><span class="sxs-lookup"><span data-stu-id="0107e-242">Use the data on this tab to evaluate call quality status and trends based on stream counts and poor percentages.</span></span> <span data-ttu-id="0107e-243">右上隅の凡例は、これらのメトリックを表す色と視覚要素を示します。</span><span class="sxs-lookup"><span data-stu-id="0107e-243">The legend in the upper-right corner shows which color and visual elements represent these metrics.</span></span>
  
![スクリーンショット: [通話品質] タブを表示する](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
<span data-ttu-id="0107e-245">ストリームは、良好、低品質、未分類の 3 つのグループに分類されます。</span><span class="sxs-lookup"><span data-stu-id="0107e-245">Streams are classified in three groups: Good, Poor, and Unclassified.</span></span> <span data-ttu-id="0107e-246">また、低品質と分類されたストリーム数の合計に対する低品質として分類されたストリームの比率を示す低品質 *%* 値も計算されます。</span><span class="sxs-lookup"><span data-stu-id="0107e-246">There are also calculated  *Poor %*  values that give you the ratio of streams classified as *Poor*  to the total classified stream count.</span></span> <span data-ttu-id="0107e-247">Poor *% = Poor streams/ (Poor streams+ Good streams) \* 100*, Poor *%* は、複数の未分類ストリームの存在の影響を *受けません。*</span><span class="sxs-lookup"><span data-stu-id="0107e-247">Since *Poor % = Poor streams/ (Poor streams+ Good streams) \* 100*, the *Poor %*  is unaffected by the presence of multiple *Unclassified*  streams.</span></span> <span data-ttu-id="0107e-248">ストリームを低品質または良好と分類する場合は、「通話品質ダッシュボードのストリームの分類 [」を参照してください](stream-classification-in-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="0107e-248">To see what classifies a stream as poor or good, refer to [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md).</span></span>
  
<span data-ttu-id="0107e-249">左側のスケールを使用して、ストリーム カウントの値を測定します。</span><span class="sxs-lookup"><span data-stu-id="0107e-249">Use the scale on the left to measure the stream count values.</span></span>
  
![スクリーンショット: ストリーム数の値を示しています](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
<span data-ttu-id="0107e-251">右側の目盛を使用して、低品質 %値を測定します。</span><span class="sxs-lookup"><span data-stu-id="0107e-251">Use the scale on the right to measure the Poor % values.</span></span>
  
![スクリーンショット: 低品質の % 値を示す](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
<span data-ttu-id="0107e-253">バーの上にマウスを置くと、実際の数値を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="0107e-253">You can also obtain the actual numerical values by hovering the mouse over a bar.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0107e-254">次の例は非常に小さいサンプル データ セットであり、値は実際の展開では現実的ではありません。</span><span class="sxs-lookup"><span data-stu-id="0107e-254">The following example is from a very small sample data set, and the values aren't realistic for an actual deployment.</span></span>
  
![スクリーンショット: データにアクセスするために使用されるマウスを示しています](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
<span data-ttu-id="0107e-256">全体的なストリーム ボリュームは、計算された低品質パーセンテージの関連性を判断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0107e-256">The overall stream volume helps determine how relevant the calculated Poor percentages are.</span></span> <span data-ttu-id="0107e-257">ストリーム全体のボリュームが小さくなると、低品質という報告された値の信頼性が低くなるのです。</span><span class="sxs-lookup"><span data-stu-id="0107e-257">The smaller the volume of overall streams, the less reliable the reported Poor percentage values are.</span></span>
  
### <a name="server-client-tab-and-client-client-tabs"></a><span data-ttu-id="0107e-258">Server-ClientタブとタブClient-Clientする</span><span class="sxs-lookup"><span data-stu-id="0107e-258">Server-Client tab and Client-Client tabs</span></span>

<span data-ttu-id="0107e-259">これら 2 つのタブには、エンドポイント間のシナリオで実行されるストリームの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0107e-259">These two tabs provide details for the streams that took place in their endpoint-to-endpoint scenarios.</span></span> <span data-ttu-id="0107e-260">[Server-Client] タブには、メディア ストリームが流れる 4 つのシナリオを表す 4 つの折りたたみ可能なセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="0107e-260">The Server-Client tab has four collapsible sections that represent four scenarios under which media streams would flow.</span></span>
  
- <span data-ttu-id="0107e-261">有線 (内部)</span><span class="sxs-lookup"><span data-stu-id="0107e-261">Wired Inside</span></span>
- <span data-ttu-id="0107e-262">有線 (外部)</span><span class="sxs-lookup"><span data-stu-id="0107e-262">Wired Outside</span></span>
- <span data-ttu-id="0107e-263">WiFi Inside</span><span class="sxs-lookup"><span data-stu-id="0107e-263">WiFi Inside</span></span>
- <span data-ttu-id="0107e-264">WiFi (外部)</span><span class="sxs-lookup"><span data-stu-id="0107e-264">WiFi Outside</span></span>

<span data-ttu-id="0107e-265">同様に、[セクション] タブClient-Client 5 つの折りたたみ可能なセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="0107e-265">Similarly, the Client-Client tab has five collapsible sections:</span></span>

- <span data-ttu-id="0107e-266">有線 (内部) — 有線 (内部)</span><span class="sxs-lookup"><span data-stu-id="0107e-266">Wired Inside — Wired Inside</span></span>
- <span data-ttu-id="0107e-267">有線 (内部) — 有線 (外側)</span><span class="sxs-lookup"><span data-stu-id="0107e-267">Wired Inside — Wired Outside</span></span>
- <span data-ttu-id="0107e-268">有線 (外部) — 有線 (外部)</span><span class="sxs-lookup"><span data-stu-id="0107e-268">Wired Outside — Wired Outside</span></span>
- <span data-ttu-id="0107e-269">有線 (内部) — 内部の WiFi</span><span class="sxs-lookup"><span data-stu-id="0107e-269">Wired Inside — WiFi Inside</span></span>
- <span data-ttu-id="0107e-270">有線 (内部) — WiFi (外部)</span><span class="sxs-lookup"><span data-stu-id="0107e-270">Wired Inside — WiFi Outside</span></span>

#### <a name="inside-versus-outside"></a><span data-ttu-id="0107e-271">内部と外部</span><span class="sxs-lookup"><span data-stu-id="0107e-271">Inside versus Outside</span></span>

<span data-ttu-id="0107e-272">CQD では、建物情報が存在  *する場合は*  、 *内部または外部*  としてストリームを分類します。</span><span class="sxs-lookup"><span data-stu-id="0107e-272">CQD classifies a stream as  *Inside*  or *Outside*  using Building information, if it exists.</span></span> <span data-ttu-id="0107e-273">各ストリームのエンドポイントは、サブネット アドレスに関連付けられている。</span><span class="sxs-lookup"><span data-stu-id="0107e-273">Endpoints of each stream are associated with a subnet address.</span></span> <span data-ttu-id="0107e-274">アップロードされた建物情報で InsideCorp とマークされたサブネットの一覧にサブネットがある場合、そのサブネットは Inside と見な *されます*。</span><span class="sxs-lookup"><span data-stu-id="0107e-274">If the subnet is in the list of the subnets marked InsideCorp in the uploaded Building information, then it is considered *Inside*.</span></span> <span data-ttu-id="0107e-275">建物情報がまだアップロードされていない場合、Inside Test は常にストリームを外部として分類 *します*。</span><span class="sxs-lookup"><span data-stu-id="0107e-275">If Building information has not yet been uploaded, then Inside Test always classifies the streams as *Outside*.</span></span> 

<span data-ttu-id="0107e-276">シナリオの内部テストではServer-Clientエンドポイントのみを考慮します。</span><span class="sxs-lookup"><span data-stu-id="0107e-276">The Inside Test for a Server-Client scenario only considers the client endpoint.</span></span> <span data-ttu-id="0107e-277">サーバーは常にユーザーの観点から外れた場所にあるため、これはテストでは考慮されません。</span><span class="sxs-lookup"><span data-stu-id="0107e-277">Because servers are always outside from a user's perspective, this isn't accounted for in the test.</span></span>
  
#### <a name="wired-versus-wifi"></a><span data-ttu-id="0107e-278">有線と WiFi</span><span class="sxs-lookup"><span data-stu-id="0107e-278">Wired versus WiFi</span></span>

<span data-ttu-id="0107e-279">名前が示す通り、分類の条件はクライアント接続の種類に基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="0107e-279">As the names indicate, the classification criteria is based on the type of client connections.</span></span> <span data-ttu-id="0107e-280">サーバーは常に有線で接続され、計算に含まれません。</span><span class="sxs-lookup"><span data-stu-id="0107e-280">Server is always wired and it isn't included in the calculation.</span></span> <span data-ttu-id="0107e-281">特定のストリームで、2 つのエンドポイントの 1 つが WiFi ネットワークに接続されている場合、CQD は WiFi として分類します。</span><span class="sxs-lookup"><span data-stu-id="0107e-281">In a given stream, if one of the two endpoints is connected to a WiFi network, then CQD classifies it as WiFi.</span></span>

> [!NOTE]
> <span data-ttu-id="0107e-282">ストリームが指定されると、2 つのエンドポイントの 1 つが WiFi ネットワークに接続されている場合、CQD では WiFi として分類されます。</span><span class="sxs-lookup"><span data-stu-id="0107e-282">Given a stream, if one of the two endpoints is connected to a WiFi network, then it is classified as WiFi in CQD.</span></span>
  
  
## <a name="tenant-data-information"></a><span data-ttu-id="0107e-283">テナント データ情報</span><span class="sxs-lookup"><span data-stu-id="0107e-283">Tenant Data information</span></span>

<span data-ttu-id="0107e-284">CQD サマリー レポート ダッシュボードには、[テナント データのアップロード] ページが含まれており、右上隅の設定メニューから [テナント データのアップロード] を選択してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="0107e-284">The CQD Summary Reports dashboard includes a **Tenant Data Upload** page, accessed by selecting **Tenant Data Upload** from the settings menu in the top-right corner.</span></span> <span data-ttu-id="0107e-285">このページは、管理者が次のような自分の情報をアップロードするために使用します。</span><span class="sxs-lookup"><span data-stu-id="0107e-285">This page is used for admins to upload their own information, such as:</span></span>

- <span data-ttu-id="0107e-286">IP アドレスと地理情報のマップ。</span><span class="sxs-lookup"><span data-stu-id="0107e-286">A map of IP address and geographical information.</span></span>
- <span data-ttu-id="0107e-287">各ワイヤレス AP とその MAC アドレスのマップ。</span><span class="sxs-lookup"><span data-stu-id="0107e-287">A map of each wireless AP and its MAC address.</span></span>
- <span data-ttu-id="0107e-288">エンドポイント間の Make/Model/Type のマップなど</span><span class="sxs-lookup"><span data-stu-id="0107e-288">A map of Endpoint to Endpoint Make/Model/Type, etc.</span></span>
  
<span data-ttu-id="0107e-289">CQD がレポートにこの情報を含めることができるようになりました。テナント、建物、場所のデータをアップロードすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0107e-289">We recommend that you upload your tenant, building, and location data so CQD can include this information in your reports.</span></span> <span data-ttu-id="0107e-290">このデータをまだアップロードしていない場合は、「テナントのアップロードとデータの作成 [」を参照してください](CQD-upload-tenant-building-data.md)。</span><span class="sxs-lookup"><span data-stu-id="0107e-290">If you haven't already uploaded this data, read [Upload tenant and building data](CQD-upload-tenant-building-data.md).</span></span> 


## <a name="detailed-reports"></a><span data-ttu-id="0107e-291">詳細レポート</span><span class="sxs-lookup"><span data-stu-id="0107e-291">Detailed reports</span></span>

| <span data-ttu-id="0107e-292">名前</span><span class="sxs-lookup"><span data-stu-id="0107e-292">Name</span></span> | <span data-ttu-id="0107e-293">説明</span><span class="sxs-lookup"><span data-stu-id="0107e-293">Description</span></span> |
|---------|---------|
|<span data-ttu-id="0107e-294">Location-Enhanced レポート</span><span class="sxs-lookup"><span data-stu-id="0107e-294">Location-Enhanced Reports</span></span>     |<span data-ttu-id="0107e-295">場所情報に基づいて品質の傾向を表示します。</span><span class="sxs-lookup"><span data-stu-id="0107e-295">Shows quality trends based on location information.</span></span> <span data-ttu-id="0107e-296">このレポートは、テナント データをアップロード [した場合にのみ表示されます](CQD-upload-tenant-building-data.md)。</span><span class="sxs-lookup"><span data-stu-id="0107e-296">This report appears only if you've [uploaded your tenant data](CQD-upload-tenant-building-data.md).</span></span>        |
|<span data-ttu-id="0107e-297">信頼性レポート</span><span class="sxs-lookup"><span data-stu-id="0107e-297">Reliability Reports</span></span>     |<span data-ttu-id="0107e-298">オーディオ、ビデオ、ビデオベースの画面共有 (VBSS)、アプリ共有レポートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0107e-298">Includes audio, video, video-based screen sharing (VBSS), and app sharing reports.</span></span>        |
|<span data-ttu-id="0107e-299">Quality of Experience レポート</span><span class="sxs-lookup"><span data-stu-id="0107e-299">Quality of Experience Reports</span></span>     |<span data-ttu-id="0107e-300">会議室を含むすべてのクライアントとデバイスの音声品質と信頼性。</span><span class="sxs-lookup"><span data-stu-id="0107e-300">Audio quality and reliability for all clients and devices, including meeting rooms.</span></span> <span data-ttu-id="0107e-301">これらのレポートは、ダウンロード可能 [な CQD](https://aka.ms/QERtemplates)テンプレートの "スリムダウン" バージョンであり、オーディオの品質と信頼性を分析するための重要な領域に重点を置いて行います。</span><span class="sxs-lookup"><span data-stu-id="0107e-301">These reports are a “slimmed-down” version of the downloadable [CQD templates](https://aka.ms/QERtemplates), focusing on key areas for analyzing audio quality and reliability.</span></span>         |
|<span data-ttu-id="0107e-302">品質ドリルダウン レポート</span><span class="sxs-lookup"><span data-stu-id="0107e-302">Quality Drill Down Reports</span></span>     | <span data-ttu-id="0107e-303">ドリルダウン: 地域、場所、サブネット、時間、ユーザー別の日付。</span><span class="sxs-lookup"><span data-stu-id="0107e-303">Drill downs: Date by region, locations, subnets, hour, and users.</span></span>        |
|<span data-ttu-id="0107e-304">エラー ドリルダウン レポート</span><span class="sxs-lookup"><span data-stu-id="0107e-304">Failure Drill Down Reports</span></span>     | <span data-ttu-id="0107e-305">ドリルダウン: 地域、場所、サブネット、時間、ユーザー別の日付。</span><span class="sxs-lookup"><span data-stu-id="0107e-305">Drill downs: Date by region, locations, subnets, hour, and users.</span></span>        |
|<span data-ttu-id="0107e-306">通話レポートの評価</span><span class="sxs-lookup"><span data-stu-id="0107e-306">Rate My Call Reports</span></span>     |<span data-ttu-id="0107e-307">地域、場所、またはユーザー別にユーザー通話の評価を分析します。</span><span class="sxs-lookup"><span data-stu-id="0107e-307">Analyze user call ratings by region, location, or by user.</span></span> <span data-ttu-id="0107e-308">詳細なフィードバックを含む。</span><span class="sxs-lookup"><span data-stu-id="0107e-308">Includes verbatim feedback.</span></span>         |
|<span data-ttu-id="0107e-309">ヘルプ デスク レポート</span><span class="sxs-lookup"><span data-stu-id="0107e-309">Help Desk Reports</span></span>     |<span data-ttu-id="0107e-310">ヘルプ デスク レポートは、個々のユーザー、ユーザーのグループ、または全員の通話と会議のデータを確認します。</span><span class="sxs-lookup"><span data-stu-id="0107e-310">Help Desk Reports look at call and meeting data for individual users, groups of users, or everyone.</span></span> <span data-ttu-id="0107e-311">建物と EUII データを組み込むこれらのレポートは、ネットワークの場所、会議の詳細、デバイス、またはファームウェアに基づいて、考えられるシステムの問題を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0107e-311">Incorporating building and EUII data, these reports help identify possible system issues based on network location, conference details, devices, or firmware.</span></span>         |
|<span data-ttu-id="0107e-312">クライアント バージョン レポート</span><span class="sxs-lookup"><span data-stu-id="0107e-312">Client Version Reports</span></span>     |<span data-ttu-id="0107e-313">クライアント バージョンの概要: クライアント アプリのバージョンごとにセッション数とユーザー数を表示する</span><span class="sxs-lookup"><span data-stu-id="0107e-313">Client Version Summary: View the Sessions and Users counts for each client app version</span></span><br><br><span data-ttu-id="0107e-314">ユーザー別のクライアント バージョン: クライアント アプリのバージョンごとにユーザー名を表示する</span><span class="sxs-lookup"><span data-stu-id="0107e-314">Client Version by User: View user names for each client app version</span></span> <br><br><span data-ttu-id="0107e-315">製品とクライアントの種類の事前に作成されたフィルターは、特定のクライアントにバージョンを集中するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0107e-315">Pre-built filters for Product and Client Type help focus the versions to specific clients.</span></span>         |
|<span data-ttu-id="0107e-316">エンドポイント レポート</span><span class="sxs-lookup"><span data-stu-id="0107e-316">Endpoint Reports</span></span>     |<span data-ttu-id="0107e-317">マシン エンドポイント別の通話品質 (コンピューターの作成とモデル) を示します。</span><span class="sxs-lookup"><span data-stu-id="0107e-317">Shows call quality by machine endpoints (computer make and model).</span></span> <span data-ttu-id="0107e-318">これらのレポートには、アップロードした場合の建物データが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0107e-318">These reports include building data, if you've uploaded it.</span></span>         |


## <a name="create-custom-detailed-reports"></a><span data-ttu-id="0107e-319">カスタム詳細レポートを作成する</span><span class="sxs-lookup"><span data-stu-id="0107e-319">Create custom detailed reports</span></span>

<span data-ttu-id="0107e-320">既定の CQD レポートがニーズを満たしない場合は、次の手順に従ってカスタム レポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="0107e-320">If the default CQD reports don't meet your needs, use these instructions to create a custom report.</span></span> <span data-ttu-id="0107e-321">または (2020 年 1 月より) 代わりに [Power BI for CQD レポートを ](cqd-power-bi-query-templates.md)使用します。</span><span class="sxs-lookup"><span data-stu-id="0107e-321">Or (as of January 2020) [Use Power BI for CQD reports ](cqd-power-bi-query-templates.md)instead.</span></span>

<span data-ttu-id="0107e-322">ログイン時に表示される画面の上部にあるレポートのプルダウン リストから、[概要レポート] 画面で詳細レポートを選択し、[新規] を選択 \(  \) **します**。 </span><span class="sxs-lookup"><span data-stu-id="0107e-322">From the pull-down list of reports at the top of the screen displayed at login \(the **Summary Reports** screen\) Select **Detailed Reports**  and then **New**.</span></span> <span data-ttu-id="0107e-323">レポート **で [** 編集] をクリックすると、クエリ エディターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0107e-323">Click **Edit** in a report to see the Query Editor.</span></span> <span data-ttu-id="0107e-324">それぞれのレポートは、キューブに対するクエリに基づきます。</span><span class="sxs-lookup"><span data-stu-id="0107e-324">Each report is backed by a query into the cube.</span></span> <span data-ttu-id="0107e-325">レポートは、クエリから返されたデータを視覚化したものです。</span><span class="sxs-lookup"><span data-stu-id="0107e-325">A report is a visualization of the data returned by its query.</span></span> <span data-ttu-id="0107e-326">クエリ エディターを使用すると、これらのクエリとレポートの表示オプションを編集できます。</span><span class="sxs-lookup"><span data-stu-id="0107e-326">The Query Editor helps you edit these queries and the display options of the report.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0107e-327">ネットワーク範囲は、スーパーネット (複数のサブネットと 1 つのルーティング プレフィックスの組み合わせ) を表す場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="0107e-327">The network range can be used to represent a supernet (combination of several subnets with a single routing prefix).</span></span> <span data-ttu-id="0107e-328">新しい建物のアップロードはすべて、重複する範囲がチェックされます。</span><span class="sxs-lookup"><span data-stu-id="0107e-328">All new building uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="0107e-329">以前に建物のファイルをアップロードした場合は、現在のファイルをダウンロードし、もう一度アップロードして重複を特定し、問題を修正してから、もう一度アップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0107e-329">If you have previously uploaded a building file, you should download the current file and re-upload it to identify any overlaps and fix the issue before uploading again.</span></span> <span data-ttu-id="0107e-330">以前にアップロードしたファイルで重複すると、レポート内の建物に対するサブネットのマッピングが間違っている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0107e-330">Any overlap in previously uploaded files may result in the wrong mappings of subnets to buildings in the reports.</span></span> <span data-ttu-id="0107e-331">VPN の実装によっては、サブネット情報が正確に報告されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="0107e-331">Certain VPN implementations do not accurately report the subnet information.</span></span> <span data-ttu-id="0107e-332">VPN サブネットを建物ファイルに追加する場合、サブネットのエントリは 1 つではなく、VPN サブネットのアドレスごとに個別の 32 ビット ネットワークとして追加されます。</span><span class="sxs-lookup"><span data-stu-id="0107e-332">It is recommended that when adding a VPN subnet to the building file, instead of one entry for the subnet, separate entries are added for each address in the VPN subnet as a separate 32-bit network.</span></span> <span data-ttu-id="0107e-333">各行には、同じ建物のメタデータを含めできます。</span><span class="sxs-lookup"><span data-stu-id="0107e-333">Each row can have the same building metadata.</span></span> <span data-ttu-id="0107e-334">たとえば、172.16.18.0/24 の 1 行ではなく、256 行を含め、住所ごとに 1 つの行を 172.16.18.0/32 から 172.16.18.255/32 まで含む必要があります。</span><span class="sxs-lookup"><span data-stu-id="0107e-334">For example, instead of one row for 172.16.18.0/24, you should have 256 rows, with one row for each address between 172.16.18.0/32 and 172.16.18.255/32, inclusive.</span></span>
>
> <span data-ttu-id="0107e-335">VPN 列は省略可能で、既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="0107e-335">The VPN column is optional and will default to 0.</span></span>  <span data-ttu-id="0107e-336">VPN 列の値が 1 に設定されている場合、その行で表されるサブネットは、サブネット内のすべての IP アドレスと一致するために完全に拡張されます。</span><span class="sxs-lookup"><span data-stu-id="0107e-336">If the VPN column's value is set to 1, the subnet represented by that row will be fully expanded to match all IP addresses within the subnet.</span></span>  <span data-ttu-id="0107e-337">これらのサブネットを完全に拡張すると、データの構築に関連するクエリのクエリ時間に悪影響を与えるので、VPN サブネットに対してだけ、この設定は少し注意して使用してください。</span><span class="sxs-lookup"><span data-stu-id="0107e-337">Please use this sparingly and only for VPN subnets since fully expanding these subnets will have a negative impact on query times for queries involving building data.</span></span>

<span data-ttu-id="0107e-338">レポート内の棒グラフと傾向線をポイントして、詳細な値を表示します。</span><span class="sxs-lookup"><span data-stu-id="0107e-338">Point to bar charts and trend lines in the report to display detailed values.</span></span> <span data-ttu-id="0107e-339">フォーカスがあるレポートには、[編集]、[複製]、[削除]、[ダウンロード]、および [レポート ツリーのエクスポート] というアクション **メニューが表示されます**。 </span><span class="sxs-lookup"><span data-stu-id="0107e-339">The report that has focus will show the action menu: **Edit**, **Clone**, **Delete**, **Download**, and **Export Report Tree**.</span></span>



## <a name="query-filters"></a><span data-ttu-id="0107e-340">クエリ フィルター</span><span class="sxs-lookup"><span data-stu-id="0107e-340">Query filters</span></span>

<span data-ttu-id="0107e-341">クエリ フィルターは、CQD のクエリ エディターを使用して実装されます。</span><span class="sxs-lookup"><span data-stu-id="0107e-341">Query filters are implemented by using the Query Editor in CQD.</span></span> <span data-ttu-id="0107e-342">これらのフィルターは、CQD から返されるレコードの数を減らすために使用され、レポートの全体的なサイズとクエリ時間を最小限に抑えるのに使用されます。</span><span class="sxs-lookup"><span data-stu-id="0107e-342">These filters are used to reduce the number of records returned by CQD, thus minimizing the report’s overall size and query times.</span></span> <span data-ttu-id="0107e-343">これは、非管理対象ネットワークをフィルター処理する場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="0107e-343">This is especially useful for filtering out unmanaged networks.</span></span> <span data-ttu-id="0107e-344">次の表に示すフィルターでは、正規表現 (RegEx) を使用します。</span><span class="sxs-lookup"><span data-stu-id="0107e-344">The filters listed in the following table use regular expressions (RegEx).</span></span>


| <span data-ttu-id="0107e-345">フィルター</span><span class="sxs-lookup"><span data-stu-id="0107e-345">Filter</span></span>         | <span data-ttu-id="0107e-346">説明</span><span class="sxs-lookup"><span data-stu-id="0107e-346">Description</span></span>          | <span data-ttu-id="0107e-347">CQD クエリ フィルターの例</span><span class="sxs-lookup"><span data-stu-id="0107e-347">CQD query filter example</span></span>      |
|----------------|----------------------|-------------------------------|
| <span data-ttu-id="0107e-348">空白値なし</span><span class="sxs-lookup"><span data-stu-id="0107e-348">No blank values</span></span>   | <span data-ttu-id="0107e-349">一部のフィルターには、空白値をフィルター処理するオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="0107e-349">Some filters don’t have the option to filter for blank values.</span></span> <span data-ttu-id="0107e-350">空白値を手動でフィルター処理するには、空の式を使用し、必要に応じて [等しい] または [等しくない] に設定します。</span><span class="sxs-lookup"><span data-stu-id="0107e-350">To filter blank values manually, use the blank expression and set the filter to Equals or Not Equals, depending on your needs.</span></span>      | <span data-ttu-id="0107e-351">Second Building Name \<\> \^ \\ s\*\$</span><span class="sxs-lookup"><span data-stu-id="0107e-351">Second Building Name \<\> \^\\s\*\$</span></span>                       |
| <span data-ttu-id="0107e-352">一般的なサブネットを除外する</span><span class="sxs-lookup"><span data-stu-id="0107e-352">Exclude common subnets</span></span> | <span data-ttu-id="0107e-353">管理されていないネットワークから管理される有効な建物ファイルがない場合、ホーム ネットワークはレポートに含まれます。</span><span class="sxs-lookup"><span data-stu-id="0107e-353">Without a valid building file to separate managed from unmanaged networks, home networks will be included in the reports.</span></span> <span data-ttu-id="0107e-354">これらのホーム サブネットは、IT の制御の対象外であり、レポートからすぐに除外できます。</span><span class="sxs-lookup"><span data-stu-id="0107e-354">These home subnets are outside the scope of IT’s control and can be quickly excluded from a report.</span></span> <span data-ttu-id="0107e-355">このガイドで定義されている一般的なサブネットは、10.0.0.0、192.168.1.0、192.168.0.0 です。</span><span class="sxs-lookup"><span data-stu-id="0107e-355">Common subnets, as defined in this guide, are 10.0.0.0, 192.168.1.0 and 192.168.0.0.</span></span> | <span data-ttu-id="0107e-356">Second Subnet \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="0107e-356">Second Subnet \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0</span></span> |
| <span data-ttu-id="0107e-357">内部のみ表示</span><span class="sxs-lookup"><span data-stu-id="0107e-357">View inside only</span></span>  | <span data-ttu-id="0107e-358">管理 (内部) または非管理 (外部) のレポートをフィルター処理するために使用します。</span><span class="sxs-lookup"><span data-stu-id="0107e-358">Used to filter a report for managed (inside) or unmanaged (outside).</span></span> <span data-ttu-id="0107e-359">管理された CQD テンプレートには、これらのフィルターが既に構成されています。</span><span class="sxs-lookup"><span data-stu-id="0107e-359">The managed CQD template is already preconfigured with these filters.</span></span>       | <span data-ttu-id="0107e-360">Second Inside Corp = Inside</span><span class="sxs-lookup"><span data-stu-id="0107e-360">Second Inside Corp = Inside</span></span>        |

## <a name="report-filters"></a><span data-ttu-id="0107e-361">レポート フィルター</span><span class="sxs-lookup"><span data-stu-id="0107e-361">Report filters</span></span>

<span data-ttu-id="0107e-362">CQD レポート フィルターを使用して、調査の焦点を絞り込む。</span><span class="sxs-lookup"><span data-stu-id="0107e-362">Use CQD report filters to narrow the focus of your investigations.</span></span> <span data-ttu-id="0107e-363">レポート フィルターを使用するには、クエリ エディターまたはレポート内で直接、表示されたレポートにフィルターを追加します。</span><span class="sxs-lookup"><span data-stu-id="0107e-363">Use report filters by adding a filter to the rendered report either in the Query Editor or directly in the report.</span></span> <span data-ttu-id="0107e-364">次のレポート フィルターは [、CQD テンプレート全体で使用されます](https://aka.ms/QERtemplates)。</span><span class="sxs-lookup"><span data-stu-id="0107e-364">The following report filters are used throughout the [CQD templates](https://aka.ms/QERtemplates).</span></span>


| <span data-ttu-id="0107e-365">フィルター</span><span class="sxs-lookup"><span data-stu-id="0107e-365">Filter</span></span>     | <span data-ttu-id="0107e-366">説明</span><span class="sxs-lookup"><span data-stu-id="0107e-366">Description</span></span>                            | <span data-ttu-id="0107e-367">CQD レポート フィルターの例</span><span class="sxs-lookup"><span data-stu-id="0107e-367">CQD report filter example</span></span>         |
|------------|----------------------------------------|-----------------------------------|
| <span data-ttu-id="0107e-368">Month</span><span class="sxs-lookup"><span data-stu-id="0107e-368">Month</span></span>      | <span data-ttu-id="0107e-369">年を最初に、次に月から始める。</span><span class="sxs-lookup"><span data-stu-id="0107e-369">Start with the year first, then month.</span></span> | <span data-ttu-id="0107e-370">2017-10</span><span class="sxs-lookup"><span data-stu-id="0107e-370">2017-10</span></span>                           |
| <span data-ttu-id="0107e-371">アルファベット順</span><span class="sxs-lookup"><span data-stu-id="0107e-371">Alphabetic</span></span> | <span data-ttu-id="0107e-372">任意の英字をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="0107e-372">Filters for any alphabetic characters.</span></span> | <span data-ttu-id="0107e-373">[a-z]</span><span class="sxs-lookup"><span data-stu-id="0107e-373">[a-z]</span></span>                             |
| <span data-ttu-id="0107e-374">数値</span><span class="sxs-lookup"><span data-stu-id="0107e-374">Numeric</span></span>    | <span data-ttu-id="0107e-375">任意の数値をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="0107e-375">Filters for any numeric characters.</span></span>    | <span data-ttu-id="0107e-376">[0-9]</span><span class="sxs-lookup"><span data-stu-id="0107e-376">[0-9]</span></span>                             |
| <span data-ttu-id="0107e-377">パーセンテージ</span><span class="sxs-lookup"><span data-stu-id="0107e-377">Percentage</span></span> | <span data-ttu-id="0107e-378">パーセンテージのフィルター。</span><span class="sxs-lookup"><span data-stu-id="0107e-378">Filters for a percentage.</span></span>              | <span data-ttu-id="0107e-379">([3-9] \\ .) \|([3-9]) \|([1-9][0-9])</span><span class="sxs-lookup"><span data-stu-id="0107e-379">([3-9]\\.)\|([3-9])\|([1-9][0-9])</span></span> |


### <a name="drill-down-filters"></a><span data-ttu-id="0107e-380">ドリルダウン フィルター</span><span class="sxs-lookup"><span data-stu-id="0107e-380">Drill-down filters</span></span>

<span data-ttu-id="0107e-381">CQD レポートにはいくつかのドリルダウン フィルターが含まれています。これは、通話品質調査の焦点を絞り込む強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="0107e-381">CQD reports feature several drill-down filters, which are powerful tools for narrowing the focus of your call-quality investigations.</span></span> <span data-ttu-id="0107e-382">ドリルダウン フィールドを選択すると、レポートによって適切なタブが自動的に開き、選択した値にフィルターが適用されます。</span><span class="sxs-lookup"><span data-stu-id="0107e-382">If you select a drill-down field, the report automatically opens the appropriate tab and filters on the selected value.</span></span> <span data-ttu-id="0107e-383">タブに独自のドリルダウン フィールドが含まれており、1 つが選択されている場合、両方のフィルター セットが適用され、結果のデータ セットが徐々に絞り込まれます。</span><span class="sxs-lookup"><span data-stu-id="0107e-383">If that tab has its own drill-down fields and one is selected, both sets of filters are applied, progressively narrowing the resulting data set.</span></span>

![ドリルダウン レポート フローを示す図](media/qerguide-image-drillthrureportflow.png)


#### <a name="adding-and-editing-drill-down-fields"></a><span data-ttu-id="0107e-385">ドリルダウン フィールドの追加と編集</span><span class="sxs-lookup"><span data-stu-id="0107e-385">Adding and editing drill-down fields</span></span>

<span data-ttu-id="0107e-386">レポートを編集する場合、クエリ エディターを使用して、独自のドリルダウン フィールドを指定できます。</span><span class="sxs-lookup"><span data-stu-id="0107e-386">When editing a report, you have the option to specify drill-down fields of your own using the Query Editor.</span></span>

<span data-ttu-id="0107e-387">[... ] をクリック **して開始します。**</span><span class="sxs-lookup"><span data-stu-id="0107e-387">Start by clicking **…**</span></span> <span data-ttu-id="0107e-388">を選び、[編集] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="0107e-388">for the report you want to edit, then select **Edit**.</span></span>

![ドリルダウン フィールドの編集のスクリーンショット](media/qerguide-image-addeditdrilldownfields.png)

<span data-ttu-id="0107e-390">クエリ エディターの左側にある一覧からディメンションを選択します。</span><span class="sxs-lookup"><span data-stu-id="0107e-390">Select a Dimension from the list on the left side of the Query Editor.</span></span> <span data-ttu-id="0107e-391">次に、[ラベルに移動]の下にあるドロップダウンをクリックし、そのディメンションのドリルスルーに使用するタブと展開グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="0107e-391">Then click on the dropdown below the **Navigate To** label and select the tab and expander group that you want that Dimension to drill through to.</span></span> <span data-ttu-id="0107e-392">注: 現在のところ、ドリルダウン機能は、異なるタブに移動する場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="0107e-392">Note: Presently, drill-down functionality only works by navigating to different tabs.</span></span> <span data-ttu-id="0107e-393">特定の展開器へのドリルスルーのサポートは、後で追加される予定です。</span><span class="sxs-lookup"><span data-stu-id="0107e-393">Support for drilling through to a specific expander will be added later.</span></span> <span data-ttu-id="0107e-394">最後に、[閉じる **]** をクリックしてディメンションへの変更を保存し、[保存] をクリックしてクエリ エディターを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="0107e-394">Finally, click **Close** to save your changes to the Dimension, then click **Save** to save and close the Query Editor.</span></span>

![クエリ エディターでディメンションを選択したスクリーンショット](media/qerguide-image-selectquerydimension.png)

### <a name="multi-select-filters"></a><span data-ttu-id="0107e-396">複数選択フィルター</span><span class="sxs-lookup"><span data-stu-id="0107e-396">Multi-select filters</span></span>

<span data-ttu-id="0107e-397">ドリルダウン機能に加えて、CQD では複数の値 (OR フィルター) を使用したフィルターの指定もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="0107e-397">In addition to drill-down functionality, CQD also supports specifying Filters with multiple values (OR filters).</span></span>

<span data-ttu-id="0107e-398">複数のフィルター値を選択するには、まず、新しいフィルターをレポートに追加します。</span><span class="sxs-lookup"><span data-stu-id="0107e-398">In order to select multiple filter values, begin by adding a new filter to the report.</span></span> <span data-ttu-id="0107e-399">[ **+** フィルター] ラベル **の横** をクリックし、使用するディメンションの名前を入力して、[追加] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="0107e-399">Click **+** beside the **Filters** label, enter the name of the Dimension you want to use, and click **Add**.</span></span>

![複数選択フィルターの追加のスクリーンショット](media/qerguide-image-addmultiselectfilter.png)

<span data-ttu-id="0107e-401">次に、[ **検索]** (新しいフィルターの横にある虫眼鏡アイコン) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0107e-401">Then, click **Search** (a magnifying glass icon next to the new filter).</span></span> <span data-ttu-id="0107e-402">テキスト フィールドと、[すべて選択] や [反転] など、さまざまな **オプション** が **表示されます**。</span><span class="sxs-lookup"><span data-stu-id="0107e-402">You'll see a text field, and a number of options, including **Select All** and **Invert**.</span></span> <span data-ttu-id="0107e-403">値を入力し、そのフィールド **の横にある [** 検索] をクリックして検索します。</span><span class="sxs-lookup"><span data-stu-id="0107e-403">Enter a value,  and click **Search** next to that field to search.</span></span> <span data-ttu-id="0107e-404">または、テキスト フィールドを空のままにし、[検索] をクリックして、最初の 100 のオプションまで表示します。</span><span class="sxs-lookup"><span data-stu-id="0107e-404">Alternatively, leave the text field empty and click **Search** to view up to the first 100 options.</span></span>

```powershell
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

<span data-ttu-id="0107e-405">例: </span><span class="sxs-lookup"><span data-stu-id="0107e-405">Example:</span></span>  

![クエリ フィルターの追加のスクリーンショット](media/qerguide-image-addfilter.png)

### <a name="dashboard-level-filters"></a><span data-ttu-id="0107e-407">ダッシュボード レベルのフィルター</span><span class="sxs-lookup"><span data-stu-id="0107e-407">Dashboard level filters</span></span>
<span data-ttu-id="0107e-408">特定の CQD レポートにはダッシュボード レベルのフィルターが追加され、一般的なパラメーターで簡単にフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="0107e-408">Certain CQD reports have dashboard-level filters added to them, making it easy to filter by common parameters.</span></span> <span data-ttu-id="0107e-409">これらのフィルターは、通常のレポート タブの外に表示され、製品フィルターの直下に表示され、ダッシュボードのすべてのフィルターに適用されます。</span><span class="sxs-lookup"><span data-stu-id="0107e-409">These filters appear outside the regular report tabs and directly beneath the Product filter, and they apply to all filters in the Dashboard.</span></span>

![ダッシュボード フィルターのスクリーンショット](media/qerguide-image-dashboardfilters.png)
```powershell
/filter/[AllStreams].[Is Teams]|[TRUE | FALSE]
```

### <a name="url-filters"></a><span data-ttu-id="0107e-411">URL フィルター</span><span class="sxs-lookup"><span data-stu-id="0107e-411">URL filters</span></span>

<span data-ttu-id="0107e-412">CQD では、URL へのフィルターの追加がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0107e-412">CQD supports adding filters to the URL.</span></span> <span data-ttu-id="0107e-413">これにより、CQD クエリを簡単に共有またはブックマークできます。</span><span class="sxs-lookup"><span data-stu-id="0107e-413">This makes it easy to share or bookmark a CQD query.</span></span> <span data-ttu-id="0107e-414">URL には、人気上昇中の月、テナント ID、言語などのパラメーターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="0107e-414">You can define parameters in the URL, such as Trending Month, tenant ID, or language.</span></span> <span data-ttu-id="0107e-415">製品レベルまたはダッシュボード レベルのフィルターを URL に追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="0107e-415">You can also add Product or Dashboard level filters to the URL.</span></span>
<span data-ttu-id="0107e-416">フェデレーション エンドポイントがレポートに影響を与える可能性がある管理された建物やネットワークを修復する場合は、CQD レポートからフェデレーション データを除外すると便利です。</span><span class="sxs-lookup"><span data-stu-id="0107e-416">Excluding federated data from CQD reports is useful when you're remediating managed buildings or networks where federated endpoints might influence your reports.</span></span>

<span data-ttu-id="0107e-417">フィルターを追加するには、URL の末尾に次を追加します。</span><span class="sxs-lookup"><span data-stu-id="0107e-417">To add a filter, append the following to the end of the URL:</span></span>

```console
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

<span data-ttu-id="0107e-418">例: </span><span class="sxs-lookup"><span data-stu-id="0107e-418">Example:</span></span>  

`https://cqd.teams.microsoft.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Second Tenant Id]|[TENANTID]`

<span data-ttu-id="0107e-419">ダッシュボード レベルのフィルターを URL に追加するには、そのフィルターが製品レベルまたはダッシュボード レベルのフィルターとして CQD に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="0107e-419">To add a Dashboard-level filter to a URL, that filter must exist in CQD as either a Product or Dashboard level filter.</span></span> <span data-ttu-id="0107e-420">次のフィルターを、上昇中の月の後と URL パラメーターの前の URL に追加します。</span><span class="sxs-lookup"><span data-stu-id="0107e-420">Add these filters to the URL after the Trending Month and before the URL parameters:</span></span>

`filter/DATA_MODEL_NAME|VALUE`

<span data-ttu-id="0107e-421">たとえば、Microsoft Teams の製品フィルター値を適用するには、次を追加します。</span><span class="sxs-lookup"><span data-stu-id="0107e-421">For example, to apply a Product filter value of Microsoft Teams, you'd add the following:</span></span>

`filter/[AllStreams].[Is%20Teams]|[True]`

<span data-ttu-id="0107e-422">URL 全体は次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="0107e-422">Your entire URL would look something like this:</span></span>

`https://cqd.teams.microsoft.com/spd/#/Dashboard/2624085/2018-9/filter/[AllStreams].[Is%20Teams]|[True]`

<span data-ttu-id="0107e-423">複数選択値を含む URL フィルターを適用するには、各値をパイプ (|) 文字で分離します。</span><span class="sxs-lookup"><span data-stu-id="0107e-423">To apply URL filters with multi-select values, separate each value with a pipe ( | ) character.</span></span> <span data-ttu-id="0107e-424">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0107e-424">For example:</span></span>

`filter/[AllStreams].[Media%20Type]|[Video]|[Audio]|[VBSS]`

<span data-ttu-id="0107e-425">無効な名前または値を指定した場合、URL フィルターは適用されません。</span><span class="sxs-lookup"><span data-stu-id="0107e-425">If you specify an invalid name or value, the URL filter won't be applied.</span></span>


<span data-ttu-id="0107e-426">URL フィルターを使用して、特定のディメンションについてすべてのレポートをフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="0107e-426">You can use a URL filter to filter every report for a specific dimension.</span></span> <span data-ttu-id="0107e-427">最も一般的な URL フィルターは、レポートをフィルター処理してフェデレーション参加者テレメトリを除外したり、Teams または Skype for Business Online にのみ焦点を当てたりするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="0107e-427">The most common URL filters are used to filter reports to exclude federated participant telemetry, or focus on only Teams or Skype for Business Online.</span></span> <span data-ttu-id="0107e-428">フェデレーション エンドポイントがレポートに影響を与える可能性がある管理された建物やネットワークを修復する場合は、CQD レポートからフェデレーション データを除外すると便利です。</span><span class="sxs-lookup"><span data-stu-id="0107e-428">Excluding federated data from CQD reports is useful when you're remediating managed buildings or networks where federated endpoints might influence your reports.</span></span>

| <span data-ttu-id="0107e-429">フィルター</span><span class="sxs-lookup"><span data-stu-id="0107e-429">Filter</span></span>         | <span data-ttu-id="0107e-430">説明</span><span class="sxs-lookup"><span data-stu-id="0107e-430">Description</span></span>          | <span data-ttu-id="0107e-431">CQD クエリ フィルターの例</span><span class="sxs-lookup"><span data-stu-id="0107e-431">CQD query filter example</span></span>      |
|----------------|----------------------|-------------------------------|
| <span data-ttu-id="0107e-432">空白値なし</span><span class="sxs-lookup"><span data-stu-id="0107e-432">No blank values</span></span>   | <span data-ttu-id="0107e-433">一部のフィルターには、空白値をフィルター処理するオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="0107e-433">Some filters don't have the option to filter for blank values.</span></span> <span data-ttu-id="0107e-434">空白値を手動でフィルター処理するには、空の式を使用し、必要に応じて [等しい] または [等しくない] に設定します。</span><span class="sxs-lookup"><span data-stu-id="0107e-434">To filter blank values manually, use the blank expression and set the filter to Equals or Not Equals, depending on your needs.</span></span>      | <span data-ttu-id="0107e-435">Second Building Name \<\> \^ \\ s\*\$</span><span class="sxs-lookup"><span data-stu-id="0107e-435">Second Building Name \<\> \^\\s\*\$</span></span>                       |
| <span data-ttu-id="0107e-436">一般的なサブネットを除外する</span><span class="sxs-lookup"><span data-stu-id="0107e-436">Exclude common subnets</span></span> | <span data-ttu-id="0107e-437">管理されていないネットワークから管理される有効な建物ファイルがない場合、ホーム ネットワークはレポートに含まれます。</span><span class="sxs-lookup"><span data-stu-id="0107e-437">Without a valid building file to separate managed from unmanaged networks, home networks will be included in the reports.</span></span> <span data-ttu-id="0107e-438">これらのホーム サブネットは、IT の制御の対象外であり、レポートからすぐに除外できます。</span><span class="sxs-lookup"><span data-stu-id="0107e-438">These home subnets are outside the scope of IT's control and can be quickly excluded from a report.</span></span> <span data-ttu-id="0107e-439">この記事で定義されている一般的なサブネットは、10.0.0.0、192.168.1.0、192.168.0.0 です。</span><span class="sxs-lookup"><span data-stu-id="0107e-439">Common subnets, as defined in this article, are 10.0.0.0, 192.168.1.0 and 192.168.0.0.</span></span> | <span data-ttu-id="0107e-440">Second Subnet \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="0107e-440">Second Subnet \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0</span></span> |
| <span data-ttu-id="0107e-441">内部のみ表示</span><span class="sxs-lookup"><span data-stu-id="0107e-441">View inside only</span></span>  | <span data-ttu-id="0107e-442">管理 (内部) または非管理 (外部) のレポートをフィルター処理するために使用します。</span><span class="sxs-lookup"><span data-stu-id="0107e-442">Used to filter a report for managed (inside) or unmanaged (outside).</span></span> <span data-ttu-id="0107e-443">管理された CQD テンプレートには、これらのフィルターが既に構成されています。</span><span class="sxs-lookup"><span data-stu-id="0107e-443">The managed CQD template is already preconfigured with these filters.</span></span>       | <span data-ttu-id="0107e-444">Second Inside Corp = Inside</span><span class="sxs-lookup"><span data-stu-id="0107e-444">Second Inside Corp = Inside</span></span>        |


#### <a name="how-to-find-your-tenant-id"></a><span data-ttu-id="0107e-445">テナント ID を見つける方法</span><span class="sxs-lookup"><span data-stu-id="0107e-445">How to find your tenant ID</span></span>

<span data-ttu-id="0107e-446">CQD のテナント ID は、Azure のディレクトリ ID に対応します。</span><span class="sxs-lookup"><span data-stu-id="0107e-446">The tenant ID in CQD corresponds to the Directory ID in Azure.</span></span> <span data-ttu-id="0107e-447">ディレクトリ ID が分からない場合は、Azure ポータルで確認できます。</span><span class="sxs-lookup"><span data-stu-id="0107e-447">If you don't know your Directory ID, you can find it in the Azure portal:</span></span>

1.  <span data-ttu-id="0107e-448">Microsoft Azure ポータルにサインインします。 <https://portal.azure.com></span><span class="sxs-lookup"><span data-stu-id="0107e-448">Sign in to the Microsoft Azure portal: <https://portal.azure.com></span></span>

2.  <span data-ttu-id="0107e-449">**Azure Active Directory を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0107e-449">Select **Azure Active Directory**.</span></span>

3.  <span data-ttu-id="0107e-450">[管理 **] で**[プロパティ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="0107e-450">Under **Manage**, select **Properties**.</span></span> <span data-ttu-id="0107e-451">テナント ID が [ディレクトリ **ID] ボックスに表示** されます。</span><span class="sxs-lookup"><span data-stu-id="0107e-451">Your tenant ID is in the **Directory ID** box.</span></span>

<span data-ttu-id="0107e-452">また、PowerShell を使用してテナント ID を確認できます。</span><span class="sxs-lookup"><span data-stu-id="0107e-452">You can also find your tenant ID by using PowerShell:</span></span> 

```powershell
Login-AzureRmAccount
```

## <a name="comparing-teams-and-skype-for-business-cqd-data"></a><span data-ttu-id="0107e-453">Teams と Skype for Business の CQD データの比較</span><span class="sxs-lookup"><span data-stu-id="0107e-453">Comparing Teams and Skype for Business CQD data</span></span>

<span data-ttu-id="0107e-454">最新の CQD (cqd.teams.microsoft.com) 内でも、Teams と Skype for Business の間にデータの違いが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0107e-454">Even within the latest CQD (cqd.teams.microsoft.com), you'll see differences in data between Teams and Skype for Business.</span></span> <span data-ttu-id="0107e-455">次の理由があります。</span><span class="sxs-lookup"><span data-stu-id="0107e-455">Some reasons:</span></span>
- <span data-ttu-id="0107e-456">パフォーマンスと信頼性を確保するためのメカニズムの違い:</span><span class="sxs-lookup"><span data-stu-id="0107e-456">Differences in the mechanisms for ensuring performance and reliability:</span></span>
  - <span data-ttu-id="0107e-457">Teams には自動再接続と高速ローミングがあります。</span><span class="sxs-lookup"><span data-stu-id="0107e-457">Teams has auto-reconnect and fast roaming.</span></span> <span data-ttu-id="0107e-458">Skype for Business では使用できない機能です。</span><span class="sxs-lookup"><span data-stu-id="0107e-458">Skype for Business doesn't.</span></span>
  - <span data-ttu-id="0107e-459">Teams には動的帯域幅管理があります。</span><span class="sxs-lookup"><span data-stu-id="0107e-459">Teams has dynamic bandwidth management.</span></span> <span data-ttu-id="0107e-460">Skype for Business では使用できない機能です。</span><span class="sxs-lookup"><span data-stu-id="0107e-460">Skype for Business doesn't.</span></span>
- <span data-ttu-id="0107e-461">Teams と Skype for Business [の間](Office-365-URLs-IP-address-ranges.md) の IP アドレス範囲の違い。</span><span class="sxs-lookup"><span data-stu-id="0107e-461">Differences in [IP address ranges](Office-365-URLs-IP-address-ranges.md) between Teams and Skype for Business.</span></span> <span data-ttu-id="0107e-462">Teams の IP 範囲は新しいので、ファイアウォールで接続の問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0107e-462">The Teams IP ranges are newer, which could cause connectivity problems at the firewall.</span></span>

## <a name="open-cqd-from-the-skype-for-business-legacy-portal"></a><span data-ttu-id="0107e-463">Skype for Business レガシ ポータルから CQD を開く</span><span class="sxs-lookup"><span data-stu-id="0107e-463">Open CQD from the Skype for Business legacy portal</span></span>

<span data-ttu-id="0107e-464">![Skype for Business の従来のポータルを使用する ](media/sfb-logo-30x30.png) **Skype for Business ロゴのアイコン**</span><span class="sxs-lookup"><span data-stu-id="0107e-464">![An icon of the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business legacy portal**</span></span>

1. <span data-ttu-id="0107e-465">管理者アカウントを使用して Office 365 組織にサインインし、[管理者]タイルを選択して管理センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="0107e-465">Sign in to your Office 365 organization using an admin account, and then select the **Admin** tile to open the Admin center.</span></span>

2. <span data-ttu-id="0107e-466">左側のウィンドウの [管理センター]**で\*\*\*\*、Microsoft Teams を選択して Teams** 管理センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="0107e-466">In the left pane, under **Admin centers**, select **Microsoft Teams** to open the Teams admin center.</span></span>

3. <span data-ttu-id="0107e-467">Teams 管理センターで、左側のウィンドウで [レガシポータル] を選択し、[ツール] を選択し **、[Skype for Business Online 通話品質ダッシュボード] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0107e-467">In the Teams admin center, select **Legacy Portal** in the left pane, select **Tools**, and then select **Skype for Business Online Call Quality Dashboard**.</span></span>

   ![スクリーンショット: 通話品質ダッシュボードを選択する](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)

4. <span data-ttu-id="0107e-469">表示されたページで、グローバル管理者アカウントでサインインし、メッセージが表示されたらアカウントの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="0107e-469">On the page that opens, sign in with your Global Administrator account, and then provide the credentials for the account when prompted.</span></span>

<span data-ttu-id="0107e-470">初めてサインインすると、CQD はデータの収集と処理を開始します。</span><span class="sxs-lookup"><span data-stu-id="0107e-470">After the first time you sign in, CQD will begin collecting and processing data.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="0107e-471">2019 年 12 月の現在、古いバージョンの CQD (cqd.lync.com) には引き続きアクセスできます。ただし、従来のポータルでは最新の CQD (cqd.teams.microsoft.com) へのリンクが提供されています。</span><span class="sxs-lookup"><span data-stu-id="0107e-471">As of December 2019, you can still access the older version of CQD (cqd.lync.com), although the legacy portal gives you a link to the latest CQD (cqd.teams.microsoft.com).</span></span> <span data-ttu-id="0107e-472">最終的には、古いバージョンの CQD は使用停止されます。</span><span class="sxs-lookup"><span data-stu-id="0107e-472">Eventually, the older version of CQD will be decommissioned.</span></span> <span data-ttu-id="0107e-473">2020 年 7 月 1 日の現在、古いバージョンの CQD は新しい CQD () からデータにアクセスし、建物やレポートのデータをエクスポートでき https://CQD.teams.microsoft.com) なくなりました。</span><span class="sxs-lookup"><span data-stu-id="0107e-473">As of July 1, 2020, the older version of CQD accesses data from the new CQD (https://CQD.teams.microsoft.com), and you can no longer export building and report data.</span></span> <span data-ttu-id="0107e-474">2020 年後半には、古い CQD を無効にし、アクセスできなくなりました。</span><span class="sxs-lookup"><span data-stu-id="0107e-474">Sometime in late 2020, we'll turn off the old CQD and you'll no longer be able to access it.</span></span>


## <a name="related-topics"></a><span data-ttu-id="0107e-475">関連項目</span><span class="sxs-lookup"><span data-stu-id="0107e-475">Related topics</span></span>

[<span data-ttu-id="0107e-476">Teams の通話品質の向上と監視</span><span class="sxs-lookup"><span data-stu-id="0107e-476">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="0107e-477">CQD とは</span><span class="sxs-lookup"><span data-stu-id="0107e-477">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="0107e-478">通話品質ダッシュボード (CQD) を設定する</span><span class="sxs-lookup"><span data-stu-id="0107e-478">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="0107e-479">テナントと建物のデータをアップロードする</span><span class="sxs-lookup"><span data-stu-id="0107e-479">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="0107e-480">CQD を使用して通話と会議の品質を管理する</span><span class="sxs-lookup"><span data-stu-id="0107e-480">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="0107e-481">CQD で使用できるディメンションとメジャー</span><span class="sxs-lookup"><span data-stu-id="0107e-481">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="0107e-482">CQD でのストリームの分類</span><span class="sxs-lookup"><span data-stu-id="0107e-482">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="0107e-483">Power BI を使用して CQD データを分析する</span><span class="sxs-lookup"><span data-stu-id="0107e-483">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)