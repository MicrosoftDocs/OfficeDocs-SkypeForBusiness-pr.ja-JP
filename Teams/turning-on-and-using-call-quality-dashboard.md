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
description: 通話品質ダッシュボードを有効にし、使用する方法と、通話品質の概要レポートを取得する方法について学習します。
ms.openlocfilehash: c71cb25732a99f207467a988ad0db54c959d15f4
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52254465"
---
# <a name="set-up-call-quality-dashboard-cqd"></a><span data-ttu-id="cd670-103">通話品質ダッシュボード (CQD) を設定する</span><span class="sxs-lookup"><span data-stu-id="cd670-103">Set up Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="cd670-104">で Microsoft 通話品質ダッシュボード (CQD) を開 [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) きます (管理者の資格情報でサインインします)。</span><span class="sxs-lookup"><span data-stu-id="cd670-104">Open the Microsoft Call Quality Dashboard (CQD) at [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (sign in with your admin credentials).</span></span> <span data-ttu-id="cd670-105">または、管理センターの [Teamsに移動し、[通話品質ダッシュボード **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cd670-105">Or go to the Teams admin center and select **Call Quality Dashboard**.</span></span> 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="管理センターの [通話品質] ダッシュボード ボタンTeamsスクリーンショット":::

<span data-ttu-id="cd670-107">表示されたページで、[サインイン]**をクリック** し、グローバル管理者アカウントまたは管理者アカウントMicrosoft Teams入力します。</span><span class="sxs-lookup"><span data-stu-id="cd670-107">On the page that opens, click **Sign in** and enter your Global Administrator account or Microsoft Teams Administrator account information.</span></span> <span data-ttu-id="cd670-108">初めてサインインすると、CQD はデータの収集と処理を開始します。</span><span class="sxs-lookup"><span data-stu-id="cd670-108">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="cd670-109">レポートに意味のある結果を表示するのに十分なデータを処理するのに 1 時間以上かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="cd670-109">Keep in mind that it may take one or more hours to process enough data to display meaningful results in the reports.</span></span>

<span data-ttu-id="cd670-110">CQD では、Microsoft Teams、Skype for Business Online、および 2019 年の組織全体の通話と会議の品質がSkype for Business Serverされます。</span><span class="sxs-lookup"><span data-stu-id="cd670-110">CQD shows call and meeting quality, at an org-wide level, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="cd670-111">Skype for Business Server 2019 で CQD を使用するには、通話データ コネクタ を[構成する必要があります](/skypeforbusiness/hybrid/configure-call-data-connector)。</span><span class="sxs-lookup"><span data-stu-id="cd670-111">To use CQD with Skype for Business Server 2019, you'll have to [Configure Call Data Connector](/skypeforbusiness/hybrid/configure-call-data-connector).</span></span> <span data-ttu-id="cd670-112">開始する [前に、「通話データ コネクタを計画](/skypeforbusiness/hybrid/plan-call-data-connector) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd670-112">See [Plan Call Data Connector](/skypeforbusiness/hybrid/plan-call-data-connector) before you start.</span></span>


## <a name="assign-admin-roles-for-access-to-cqd"></a><span data-ttu-id="cd670-113">CQD にアクセスするために管理者ロールを割り当てる</span><span class="sxs-lookup"><span data-stu-id="cd670-113">Assign admin roles for access to CQD</span></span>

<span data-ttu-id="cd670-114">[CQD](/microsoft-365/admin/add-users/about-admin-roles)にアクセスするロールを、それを使用する必要があるユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="cd670-114">Assign [roles](/microsoft-365/admin/add-users/about-admin-roles) for accessing CQD to the people who need to use it.</span></span>

<span data-ttu-id="cd670-115">管理者以外のユーザー (サポート エンジニアやヘルプデスク エージェントなど) に通話品質ダッシュボードを使用する場合は、これらのユーザーに次のいずれかのロールを割り当てることができます。これにより、CQD にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="cd670-115">If you want non-admin users (such as support engineers and helpdesk agents) to use Call Quality Dashboard, you can assign those users one of the following roles, which gives access to CQD.</span></span> 


|  |<span data-ttu-id="cd670-116">レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="cd670-116">View reports</span></span>  |<span data-ttu-id="cd670-117">EUII フィールドを表示する</span><span class="sxs-lookup"><span data-stu-id="cd670-117">View EUII fields</span></span>  |<span data-ttu-id="cd670-118">レポートを作成する</span><span class="sxs-lookup"><span data-stu-id="cd670-118">Create reports</span></span>  |<span data-ttu-id="cd670-119">アップロードの作成</span><span class="sxs-lookup"><span data-stu-id="cd670-119">Upload building data</span></span>  |
|---------|:-------:|:-------:|:-------:|:-------:|
|<span data-ttu-id="cd670-120">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="cd670-120">Global Administrator</span></span>     |<span data-ttu-id="cd670-121">はい</span><span class="sxs-lookup"><span data-stu-id="cd670-121">Yes</span></span>         |<span data-ttu-id="cd670-122">はい</span><span class="sxs-lookup"><span data-stu-id="cd670-122">Yes</span></span>         |<span data-ttu-id="cd670-123">はい</span><span class="sxs-lookup"><span data-stu-id="cd670-123">Yes</span></span>         |<span data-ttu-id="cd670-124">はい</span><span class="sxs-lookup"><span data-stu-id="cd670-124">Yes</span></span>         |
|<span data-ttu-id="cd670-125">Teams 管理者</span><span class="sxs-lookup"><span data-stu-id="cd670-125">Teams Administrator</span></span>     |<span data-ttu-id="cd670-126">はい</span><span class="sxs-lookup"><span data-stu-id="cd670-126">Yes</span></span>         |<span data-ttu-id="cd670-127">はい</span><span class="sxs-lookup"><span data-stu-id="cd670-127">Yes</span></span>         |<span data-ttu-id="cd670-128">はい</span><span class="sxs-lookup"><span data-stu-id="cd670-128">Yes</span></span>         |<span data-ttu-id="cd670-129">はい</span><span class="sxs-lookup"><span data-stu-id="cd670-129">Yes</span></span>         |
|<span data-ttu-id="cd670-130">Teams 通信管理者</span><span class="sxs-lookup"><span data-stu-id="cd670-130">Teams Communications Administrator</span></span>     |<span data-ttu-id="cd670-131">はい</span><span class="sxs-lookup"><span data-stu-id="cd670-131">Yes</span></span>         |<span data-ttu-id="cd670-132">はい</span><span class="sxs-lookup"><span data-stu-id="cd670-132">Yes</span></span>         |<span data-ttu-id="cd670-133">はい</span><span class="sxs-lookup"><span data-stu-id="cd670-133">Yes</span></span>         |<span data-ttu-id="cd670-134">はい</span><span class="sxs-lookup"><span data-stu-id="cd670-134">Yes</span></span>         |
|<span data-ttu-id="cd670-135">Teams 通信サポート エンジニア</span><span class="sxs-lookup"><span data-stu-id="cd670-135">Teams Communications Support Engineer</span></span>     |<span data-ttu-id="cd670-136">はい</span><span class="sxs-lookup"><span data-stu-id="cd670-136">Yes</span></span>         |<span data-ttu-id="cd670-137">はい</span><span class="sxs-lookup"><span data-stu-id="cd670-137">Yes</span></span>         |<span data-ttu-id="cd670-138">はい</span><span class="sxs-lookup"><span data-stu-id="cd670-138">Yes</span></span>         |<span data-ttu-id="cd670-139">いいえ</span><span class="sxs-lookup"><span data-stu-id="cd670-139">No</span></span>         |
|<span data-ttu-id="cd670-140">Teams 通信サポート スペシャリスト</span><span class="sxs-lookup"><span data-stu-id="cd670-140">Teams Communications Support Specialist</span></span>     |<span data-ttu-id="cd670-141">はい</span><span class="sxs-lookup"><span data-stu-id="cd670-141">Yes</span></span>         |<span data-ttu-id="cd670-142">いいえ</span><span class="sxs-lookup"><span data-stu-id="cd670-142">No</span></span>         |<span data-ttu-id="cd670-143">はい</span><span class="sxs-lookup"><span data-stu-id="cd670-143">Yes</span></span>         |<span data-ttu-id="cd670-144">いいえ</span><span class="sxs-lookup"><span data-stu-id="cd670-144">No</span></span>         |
|<span data-ttu-id="cd670-145">Skype for Business管理者</span><span class="sxs-lookup"><span data-stu-id="cd670-145">Skype for Business Administrator</span></span>     |<span data-ttu-id="cd670-146">はい</span><span class="sxs-lookup"><span data-stu-id="cd670-146">Yes</span></span>         |<span data-ttu-id="cd670-147">はい</span><span class="sxs-lookup"><span data-stu-id="cd670-147">Yes</span></span>         |<span data-ttu-id="cd670-148">はい</span><span class="sxs-lookup"><span data-stu-id="cd670-148">Yes</span></span>         |<span data-ttu-id="cd670-149">はい</span><span class="sxs-lookup"><span data-stu-id="cd670-149">Yes</span></span>         |
|<span data-ttu-id="cd670-150">グローバル リーダー</span><span class="sxs-lookup"><span data-stu-id="cd670-150">Global Reader</span></span> |<span data-ttu-id="cd670-151">はい</span><span class="sxs-lookup"><span data-stu-id="cd670-151">Yes</span></span>         |<span data-ttu-id="cd670-152">はい</span><span class="sxs-lookup"><span data-stu-id="cd670-152">Yes</span></span>         |<span data-ttu-id="cd670-153">はい</span><span class="sxs-lookup"><span data-stu-id="cd670-153">Yes</span></span>         |<span data-ttu-id="cd670-154">いいえ</span><span class="sxs-lookup"><span data-stu-id="cd670-154">No</span></span>         |
|<span data-ttu-id="cd670-155">レポート閲覧<sup>者 1</sup></span><span class="sxs-lookup"><span data-stu-id="cd670-155">Reports Reader<sup>1</sup></span></span>     |<span data-ttu-id="cd670-156">はい</span><span class="sxs-lookup"><span data-stu-id="cd670-156">Yes</span></span>         |<span data-ttu-id="cd670-157">いいえ</span><span class="sxs-lookup"><span data-stu-id="cd670-157">No</span></span>         |<span data-ttu-id="cd670-158">はい</span><span class="sxs-lookup"><span data-stu-id="cd670-158">Yes</span></span>         |<span data-ttu-id="cd670-159">いいえ</span><span class="sxs-lookup"><span data-stu-id="cd670-159">No</span></span>         |

<span data-ttu-id="cd670-160"><sup>1</sup>レポート 閲覧者は、CQD レポートを読み取[](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263)るだけでなく、管理センター内のすべてのアクティビティ レポートと、Microsoft 365 導入コンテンツ パック[からのすべてのレポートを表示できます](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)。</span><span class="sxs-lookup"><span data-stu-id="cd670-160"><sup>1</sup> In addition to reading CQD reports, the Reports Reader can view all the [activity reports](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) in the admin center and any reports from the [Microsoft 365 Adoption content pack](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).</span></span>

> [!NOTE]
> <span data-ttu-id="cd670-161">[EUII (](CQD-data-and-reports.md#euii-data)エンドユーザーを特定できる情報) が表示されない場合、この情報の表示が許可されているロールの 1 つがある場合、CQD は EUII を 28 日間のみ保持します。</span><span class="sxs-lookup"><span data-stu-id="cd670-161">If you're not seeing [EUII (end-user identifiable information)](CQD-data-and-reports.md#euii-data) and you have one of the roles that's permitted to see this information, keep in mind that CQD only keeps EUII for 28 days.</span></span> <span data-ttu-id="cd670-162">28 日より前のデータは削除されます。</span><span class="sxs-lookup"><span data-stu-id="cd670-162">Anything older than 28 days is deleted.</span></span>

<span data-ttu-id="cd670-163">これらのロールの詳細については、「管理者ロールについて[」Office 365参照してください](/office365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="cd670-163">For more information about these roles, see [About Office 365 admin roles](/office365/admin/add-users/about-admin-roles).</span></span>


<span data-ttu-id="cd670-164">初めてサインインすると、CQD はデータの収集と処理を開始します。</span><span class="sxs-lookup"><span data-stu-id="cd670-164">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="cd670-165">2019 年 12 月の現在でも、古いバージョンの CQD (cqd.lync.com) にアクセスできます。ただし、レガシ ポータルには最新の CQD (cqd.teams.microsoft.com) へのリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cd670-165">As of December 2019, you can still access the older version of CQD (cqd.lync.com), although the legacy portal gives you a link to the latest CQD (cqd.teams.microsoft.com).</span></span> <span data-ttu-id="cd670-166">最終的に、以前のバージョンの CQD は使用停止されます。</span><span class="sxs-lookup"><span data-stu-id="cd670-166">Eventually, the older version of CQD will be decommissioned.</span></span> <span data-ttu-id="cd670-167">2020 年 7 月 1 日の現在、古いバージョンの CQD は最新の CQD からデータにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="cd670-167">As of July 1, 2020, the older version of CQD accesses data from the latest CQD.</span></span>


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a><span data-ttu-id="cd670-168">以前のバージョンの CQD から建物のデータとレポートを移行する</span><span class="sxs-lookup"><span data-stu-id="cd670-168">Migrate building data and reports from previous version of CQD</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cd670-169">2020 年 7 月 1 日の現在、以前の CQD () から建物のデータとレポートを移行できなくなりました https://CQD.lync.com) 。</span><span class="sxs-lookup"><span data-stu-id="cd670-169">As of July 1, 2020, you can no longer migrate building data and reports from the old CQD (https://CQD.lync.com).</span></span> 



## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="cd670-170">CQD Power BI分析するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="cd670-170">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="cd670-171">2020 年 1 月の新機能: [CQD Power BIテンプレートをダウンロードします](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="cd670-171">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="cd670-172">カスタマイズ可能Power BI、CQD データの分析とレポートに使用できるテンプレートです。</span><span class="sxs-lookup"><span data-stu-id="cd670-172">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="cd670-173">詳細[については、「Power BI を使用して CQD データを分析する](CQD-Power-BI-query-templates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd670-173">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>


## <a name="related-topics"></a><span data-ttu-id="cd670-174">関連トピック</span><span class="sxs-lookup"><span data-stu-id="cd670-174">Related topics</span></span>

[<span data-ttu-id="cd670-175">Teams の通話品質の向上と監視</span><span class="sxs-lookup"><span data-stu-id="cd670-175">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="cd670-176">CQD とは</span><span class="sxs-lookup"><span data-stu-id="cd670-176">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="cd670-177">アップロードとデータの構築</span><span class="sxs-lookup"><span data-stu-id="cd670-177">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="cd670-178">CQD データとレポート</span><span class="sxs-lookup"><span data-stu-id="cd670-178">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="cd670-179">CQD を使用して通話と会議の品質を管理する</span><span class="sxs-lookup"><span data-stu-id="cd670-179">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="cd670-180">CQD で使用可能なディメンションとメジャー</span><span class="sxs-lookup"><span data-stu-id="cd670-180">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="cd670-181">CQD のストリーム分類</span><span class="sxs-lookup"><span data-stu-id="cd670-181">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="cd670-182">CQD Power BI分析するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="cd670-182">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)