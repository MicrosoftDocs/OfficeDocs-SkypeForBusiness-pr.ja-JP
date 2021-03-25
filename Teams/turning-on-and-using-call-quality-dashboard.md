---
title: 通話品質ダッシュボード (CQD) を設定する
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
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: 通話品質ダッシュボードを有効にし、使用する方法と、通話の品質に関する概要レポートを取得する方法について学習します。
ms.openlocfilehash: 2d671de0e2ddc5d4c2a4e321cf90e2e2f0dbe770
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51162692"
---
# <a name="set-up-call-quality-dashboard-cqd"></a><span data-ttu-id="359ac-103">通話品質ダッシュボード (CQD) を設定する</span><span class="sxs-lookup"><span data-stu-id="359ac-103">Set up Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="359ac-104">Microsoft 通話品質ダッシュボード (CQD) を開 [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) きます (管理者の資格情報でサインインします)。</span><span class="sxs-lookup"><span data-stu-id="359ac-104">Open the Microsoft Call Quality Dashboard (CQD) at [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (sign in with your admin credentials).</span></span> <span data-ttu-id="359ac-105">または、Teams 管理センターに移動し、[通話品質 **ダッシュボード] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="359ac-105">Or go to the Teams admin center and select **Call Quality Dashboard**.</span></span> 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Teams 管理センターの [通話品質ダッシュボード] ボタンのスクリーンショット":::

<span data-ttu-id="359ac-107">表示されたページで、[ **サインイン]** をクリックし、グローバル管理者アカウントまたは Microsoft Teams サービス管理者アカウント情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="359ac-107">On the page that opens, click **Sign in** and enter your Global Administrator account or Microsoft Teams Service Administrator account information.</span></span> <span data-ttu-id="359ac-108">初めてサインインすると、CQD はデータの収集と処理を開始します。</span><span class="sxs-lookup"><span data-stu-id="359ac-108">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="359ac-109">レポートに意味のある結果を表示するのに十分なデータを処理するのに 1 時間以上かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="359ac-109">Keep in mind that it may take one or more hours to process enough data to display meaningful results in the reports.</span></span>

<span data-ttu-id="359ac-110">CQD では、Microsoft Teams、Skype for Business Online、Skype for Business Server 2019 の通話と会議の品質が組織全体レベルで表示されます。</span><span class="sxs-lookup"><span data-stu-id="359ac-110">CQD shows call and meeting quality, at an org-wide level, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="359ac-111">Skype for Business Server 2019 で CQD を使用するには、通話データ コネクタを [構成する必要があります](/skypeforbusiness/hybrid/configure-call-data-connector)。</span><span class="sxs-lookup"><span data-stu-id="359ac-111">To use CQD with Skype for Business Server 2019, you'll have to [Configure Call Data Connector](/skypeforbusiness/hybrid/configure-call-data-connector).</span></span> <span data-ttu-id="359ac-112">開始 [する前に、「通話データ コネクタを](/skypeforbusiness/hybrid/plan-call-data-connector) 計画する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="359ac-112">See [Plan Call Data Connector](/skypeforbusiness/hybrid/plan-call-data-connector) before you start.</span></span>


## <a name="assign-admin-roles-for-access-to-cqd"></a><span data-ttu-id="359ac-113">CQD へのアクセスに管理者ロールを割り当てる</span><span class="sxs-lookup"><span data-stu-id="359ac-113">Assign admin roles for access to CQD</span></span>

<span data-ttu-id="359ac-114">[CQD](/microsoft-365/admin/add-users/about-admin-roles)にアクセスするロールを、CQD を使用する必要があるユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="359ac-114">Assign [roles](/microsoft-365/admin/add-users/about-admin-roles) for accessing CQD to the people who need to use it.</span></span>

<span data-ttu-id="359ac-115">管理者以外のユーザー (サポート エンジニアやヘルプデスク エージェントなど) に通話品質ダッシュボードを使用する場合は、これらのユーザーに次のいずれかの役割を割り当て、CQD にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="359ac-115">If you want non-admin users (such as support engineers and helpdesk agents) to use Call Quality Dashboard, you can assign those users one of the following roles, which gives access to CQD.</span></span> 


|  |<span data-ttu-id="359ac-116">レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="359ac-116">View reports</span></span>  |<span data-ttu-id="359ac-117">[EUII] フィールドを表示する</span><span class="sxs-lookup"><span data-stu-id="359ac-117">View EUII fields</span></span>  |<span data-ttu-id="359ac-118">レポートを作成する</span><span class="sxs-lookup"><span data-stu-id="359ac-118">Create reports</span></span>  |<span data-ttu-id="359ac-119">建物データをアップロードする</span><span class="sxs-lookup"><span data-stu-id="359ac-119">Upload building data</span></span>  |
|---------|:-------:|:-------:|:-------:|:-------:|
|<span data-ttu-id="359ac-120">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="359ac-120">Global Administrator</span></span>     |<span data-ttu-id="359ac-121">はい</span><span class="sxs-lookup"><span data-stu-id="359ac-121">Yes</span></span>         |<span data-ttu-id="359ac-122">はい</span><span class="sxs-lookup"><span data-stu-id="359ac-122">Yes</span></span>         |<span data-ttu-id="359ac-123">はい</span><span class="sxs-lookup"><span data-stu-id="359ac-123">Yes</span></span>         |<span data-ttu-id="359ac-124">はい</span><span class="sxs-lookup"><span data-stu-id="359ac-124">Yes</span></span>         |
|<span data-ttu-id="359ac-125">Teams サービス管理者</span><span class="sxs-lookup"><span data-stu-id="359ac-125">Teams Service Administrator</span></span>     |<span data-ttu-id="359ac-126">はい</span><span class="sxs-lookup"><span data-stu-id="359ac-126">Yes</span></span>         |<span data-ttu-id="359ac-127">はい</span><span class="sxs-lookup"><span data-stu-id="359ac-127">Yes</span></span>         |<span data-ttu-id="359ac-128">はい</span><span class="sxs-lookup"><span data-stu-id="359ac-128">Yes</span></span>         |<span data-ttu-id="359ac-129">はい</span><span class="sxs-lookup"><span data-stu-id="359ac-129">Yes</span></span>         |
|<span data-ttu-id="359ac-130">Teams 通信管理者</span><span class="sxs-lookup"><span data-stu-id="359ac-130">Teams Communications Administrator</span></span>     |<span data-ttu-id="359ac-131">はい</span><span class="sxs-lookup"><span data-stu-id="359ac-131">Yes</span></span>         |<span data-ttu-id="359ac-132">はい</span><span class="sxs-lookup"><span data-stu-id="359ac-132">Yes</span></span>         |<span data-ttu-id="359ac-133">はい</span><span class="sxs-lookup"><span data-stu-id="359ac-133">Yes</span></span>         |<span data-ttu-id="359ac-134">はい</span><span class="sxs-lookup"><span data-stu-id="359ac-134">Yes</span></span>         |
|<span data-ttu-id="359ac-135">Teams 通信サポート エンジニア</span><span class="sxs-lookup"><span data-stu-id="359ac-135">Teams Communications Support Engineer</span></span>     |<span data-ttu-id="359ac-136">はい</span><span class="sxs-lookup"><span data-stu-id="359ac-136">Yes</span></span>         |<span data-ttu-id="359ac-137">はい</span><span class="sxs-lookup"><span data-stu-id="359ac-137">Yes</span></span>         |<span data-ttu-id="359ac-138">はい</span><span class="sxs-lookup"><span data-stu-id="359ac-138">Yes</span></span>         |<span data-ttu-id="359ac-139">いいえ</span><span class="sxs-lookup"><span data-stu-id="359ac-139">No</span></span>         |
|<span data-ttu-id="359ac-140">Teams 通信サポート スペシャリスト</span><span class="sxs-lookup"><span data-stu-id="359ac-140">Teams Communications Support Specialist</span></span>     |<span data-ttu-id="359ac-141">はい</span><span class="sxs-lookup"><span data-stu-id="359ac-141">Yes</span></span>         |<span data-ttu-id="359ac-142">いいえ</span><span class="sxs-lookup"><span data-stu-id="359ac-142">No</span></span>         |<span data-ttu-id="359ac-143">はい</span><span class="sxs-lookup"><span data-stu-id="359ac-143">Yes</span></span>         |<span data-ttu-id="359ac-144">いいえ</span><span class="sxs-lookup"><span data-stu-id="359ac-144">No</span></span>         |
|<span data-ttu-id="359ac-145">Skype for Business 管理者</span><span class="sxs-lookup"><span data-stu-id="359ac-145">Skype for Business Administrator</span></span>     |<span data-ttu-id="359ac-146">はい</span><span class="sxs-lookup"><span data-stu-id="359ac-146">Yes</span></span>         |<span data-ttu-id="359ac-147">はい</span><span class="sxs-lookup"><span data-stu-id="359ac-147">Yes</span></span>         |<span data-ttu-id="359ac-148">はい</span><span class="sxs-lookup"><span data-stu-id="359ac-148">Yes</span></span>         |<span data-ttu-id="359ac-149">はい</span><span class="sxs-lookup"><span data-stu-id="359ac-149">Yes</span></span>         |
|<span data-ttu-id="359ac-150">グローバル リーダー</span><span class="sxs-lookup"><span data-stu-id="359ac-150">Global Reader</span></span> |<span data-ttu-id="359ac-151">はい</span><span class="sxs-lookup"><span data-stu-id="359ac-151">Yes</span></span>         |<span data-ttu-id="359ac-152">はい</span><span class="sxs-lookup"><span data-stu-id="359ac-152">Yes</span></span>         |<span data-ttu-id="359ac-153">はい</span><span class="sxs-lookup"><span data-stu-id="359ac-153">Yes</span></span>         |<span data-ttu-id="359ac-154">いいえ</span><span class="sxs-lookup"><span data-stu-id="359ac-154">No</span></span>         |
|<span data-ttu-id="359ac-155">レポート リーダー<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="359ac-155">Reports Reader<sup>1</sup></span></span>     |<span data-ttu-id="359ac-156">はい</span><span class="sxs-lookup"><span data-stu-id="359ac-156">Yes</span></span>         |<span data-ttu-id="359ac-157">いいえ</span><span class="sxs-lookup"><span data-stu-id="359ac-157">No</span></span>         |<span data-ttu-id="359ac-158">はい</span><span class="sxs-lookup"><span data-stu-id="359ac-158">Yes</span></span>         |<span data-ttu-id="359ac-159">いいえ</span><span class="sxs-lookup"><span data-stu-id="359ac-159">No</span></span>         |

<span data-ttu-id="359ac-160"><sup>1</sup>レポート リーダーは、CQD レポートを読むだけでなく、[](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263)管理センターのすべてのアクティビティ レポートと[、Microsoft 365 導入](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)コンテンツ パックのレポートも表示できます。</span><span class="sxs-lookup"><span data-stu-id="359ac-160"><sup>1</sup> In addition to reading CQD reports, the Reports Reader can view all the [activity reports](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) in the admin center and any reports from the [Microsoft 365 Adoption content pack](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).</span></span>

> [!NOTE]
> <span data-ttu-id="359ac-161">[EUII (](CQD-data-and-reports.md#euii-data)エンド ユーザーを特定できる情報) が表示されない場合、この情報の表示が許可されているロールの 1 つを持っている場合は、CQD は 28 日間のみ EUII を保持します。</span><span class="sxs-lookup"><span data-stu-id="359ac-161">If you're not seeing [EUII (end-user identifiable information)](CQD-data-and-reports.md#euii-data) and you have one of the roles that's permitted to see this information, keep in mind that CQD only keeps EUII for 28 days.</span></span> <span data-ttu-id="359ac-162">28 日より前のデータは削除されます。</span><span class="sxs-lookup"><span data-stu-id="359ac-162">Anything older than 28 days is deleted.</span></span>

<span data-ttu-id="359ac-163">これらの役割の詳細については [、「365 管理者ロールの概要Officeを参照してください](/office365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="359ac-163">For more information about these roles, see [About Office 365 admin roles](/office365/admin/add-users/about-admin-roles).</span></span>


<span data-ttu-id="359ac-164">初めてサインインすると、CQD はデータの収集と処理を開始します。</span><span class="sxs-lookup"><span data-stu-id="359ac-164">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="359ac-165">2019 年 12 月の現在、古いバージョンの CQD (cqd.lync.com) には引き続きアクセスできます。ただし、従来のポータルでは最新の CQD (cqd.teams.microsoft.com) へのリンクが提供されています。</span><span class="sxs-lookup"><span data-stu-id="359ac-165">As of December 2019, you can still access the older version of CQD (cqd.lync.com), although the legacy portal gives you a link to the latest CQD (cqd.teams.microsoft.com).</span></span> <span data-ttu-id="359ac-166">最終的には、古いバージョンの CQD は使用停止されます。</span><span class="sxs-lookup"><span data-stu-id="359ac-166">Eventually, the older version of CQD will be decommissioned.</span></span> <span data-ttu-id="359ac-167">2020 年 7 月 1 日の現在、古いバージョンの CQD は最新の CQD のデータにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="359ac-167">As of July 1, 2020, the older version of CQD accesses data from the latest CQD.</span></span>


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a><span data-ttu-id="359ac-168">以前のバージョンの CQD から建物データとレポートを移行する</span><span class="sxs-lookup"><span data-stu-id="359ac-168">Migrate building data and reports from previous version of CQD</span></span>

> [!IMPORTANT]
> <span data-ttu-id="359ac-169">2020 年 7 月 1 日の現在、以前の CQD https://CQD.lync.com) (.</span><span class="sxs-lookup"><span data-stu-id="359ac-169">As of July 1, 2020, you can no longer migrate building data and reports from the old CQD (https://CQD.lync.com).</span></span> 



## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="359ac-170">Power BI を使用して CQD データを分析する</span><span class="sxs-lookup"><span data-stu-id="359ac-170">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="359ac-171">2020 年 1 月の新機能: [CQD 用の Power BI クエリ テンプレートをダウンロードします](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="359ac-171">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="359ac-172">カスタマイズ可能な Power BI テンプレートを使用して、CQD データを分析およびレポートできます。</span><span class="sxs-lookup"><span data-stu-id="359ac-172">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="359ac-173">詳細 [については、「Power BI を使用して CQD データを分析する](CQD-Power-BI-query-templates.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="359ac-173">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>


## <a name="related-topics"></a><span data-ttu-id="359ac-174">関連項目</span><span class="sxs-lookup"><span data-stu-id="359ac-174">Related topics</span></span>

[<span data-ttu-id="359ac-175">Teams の通話品質の向上と監視</span><span class="sxs-lookup"><span data-stu-id="359ac-175">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="359ac-176">CQD とは</span><span class="sxs-lookup"><span data-stu-id="359ac-176">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="359ac-177">テナントと建物のデータをアップロードする</span><span class="sxs-lookup"><span data-stu-id="359ac-177">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="359ac-178">CQD データとレポート</span><span class="sxs-lookup"><span data-stu-id="359ac-178">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="359ac-179">CQD を使用して通話と会議の品質を管理する</span><span class="sxs-lookup"><span data-stu-id="359ac-179">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="359ac-180">CQD で使用できるディメンションとメジャー</span><span class="sxs-lookup"><span data-stu-id="359ac-180">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="359ac-181">CQD でのストリームの分類</span><span class="sxs-lookup"><span data-stu-id="359ac-181">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="359ac-182">Power BI を使用して CQD データを分析する</span><span class="sxs-lookup"><span data-stu-id="359ac-182">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)