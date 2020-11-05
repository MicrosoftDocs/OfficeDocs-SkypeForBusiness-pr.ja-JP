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
description: 通話品質ダッシュボードをオンにして使用し、通話の品質に関する概要レポートを取得する方法について説明します。
ms.openlocfilehash: 9a864b0ad0f48e3a0bd8665b8dfeb917e67f4062
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2020
ms.locfileid: "48918648"
---
# <a name="set-up-call-quality-dashboard-cqd"></a><span data-ttu-id="55f8f-103">通話品質ダッシュボード (CQD) を設定する</span><span class="sxs-lookup"><span data-stu-id="55f8f-103">Set up Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="55f8f-104">で Microsoft 通話品質ダッシュボード (CQD) を開き [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) ます (管理者の資格情報でサインインします)。</span><span class="sxs-lookup"><span data-stu-id="55f8f-104">Open the Microsoft Call Quality Dashboard (CQD) at [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (sign in with your admin credentials).</span></span> <span data-ttu-id="55f8f-105">または、Teams 管理センターに移動して、[ **通話品質ダッシュボード** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="55f8f-105">Or go to the Teams admin center and select **Call Quality Dashboard**.</span></span> 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Teams 管理センターの [通話品質ダッシュボード] ボタンのスクリーンショット":::

<span data-ttu-id="55f8f-107">表示されたページで、[ **サインイン** ] をクリックして、グローバル管理者アカウントまたは Microsoft Teams サービス管理者アカウント情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="55f8f-107">On the page that opens, click **Sign in** and enter your Global Administrator account or Microsoft Teams Service Admin account information.</span></span> <span data-ttu-id="55f8f-108">初めてサインインすると、CQD でデータの収集と処理が開始されます。</span><span class="sxs-lookup"><span data-stu-id="55f8f-108">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="55f8f-109">レポートに意味のある結果を表示するために十分なデータの処理には、1時間以上かかる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="55f8f-109">Keep in mind that it may take one or more hours to process enough data to display meaningful results in the reports.</span></span>

<span data-ttu-id="55f8f-110">CQD は、組織全体のレベルで、Microsoft Teams、Skype for Business Online、Skype for Business Server 2019 に、通話と会議の品質を示します。</span><span class="sxs-lookup"><span data-stu-id="55f8f-110">CQD shows call and meeting quality, at an org-wide level, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="55f8f-111">Skype for Business Server 2019 で CQD を使用するには、 [通話データコネクタを構成](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="55f8f-111">To use CQD with Skype for Business Server 2019, you'll have to [Configure Call Data Connector](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector).</span></span> <span data-ttu-id="55f8f-112">始める前に「 [通話データコネクタを計画](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55f8f-112">See [Plan Call Data Connector](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) before you start.</span></span>


## <a name="assign-admin-roles-for-access-to-cqd"></a><span data-ttu-id="55f8f-113">CQD へのアクセスに管理者ロールを割り当てる</span><span class="sxs-lookup"><span data-stu-id="55f8f-113">Assign admin roles for access to CQD</span></span>

<span data-ttu-id="55f8f-114">CQD にアクセスするための [役割](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) を、使用する必要があるユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="55f8f-114">Assign [roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) for accessing CQD to the people who need to use it.</span></span>

<span data-ttu-id="55f8f-115">管理者以外のユーザー (サポートエンジニアやヘルプデスクエージェントなど) が通話品質ダッシュボードを使用できるようにするには、次のロールのいずれかをユーザーに割り当てることができます。これにより、CQD へのアクセスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="55f8f-115">If you want non-admin users (such as support engineers and helpdesk agents) to use Call Quality Dashboard, you can assign those users one of the following roles, which gives access to CQD.</span></span> 


|  |<span data-ttu-id="55f8f-116">レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="55f8f-116">View reports</span></span>  |<span data-ttu-id="55f8f-117">EUII フィールドを表示する</span><span class="sxs-lookup"><span data-stu-id="55f8f-117">View EUII fields</span></span>  |<span data-ttu-id="55f8f-118">レポートを作成する</span><span class="sxs-lookup"><span data-stu-id="55f8f-118">Create reports</span></span>  |<span data-ttu-id="55f8f-119">建物のデータをアップロードする</span><span class="sxs-lookup"><span data-stu-id="55f8f-119">Upload building data</span></span>  |
|---------|:-------:|:-------:|:-------:|:-------:|
|<span data-ttu-id="55f8f-120">Office 365 のグローバル管理者</span><span class="sxs-lookup"><span data-stu-id="55f8f-120">Office 365 Global Administrator</span></span>     |<span data-ttu-id="55f8f-121">はい</span><span class="sxs-lookup"><span data-stu-id="55f8f-121">Yes</span></span>         |<span data-ttu-id="55f8f-122">はい</span><span class="sxs-lookup"><span data-stu-id="55f8f-122">Yes</span></span>         |<span data-ttu-id="55f8f-123">はい</span><span class="sxs-lookup"><span data-stu-id="55f8f-123">Yes</span></span>         |<span data-ttu-id="55f8f-124">はい</span><span class="sxs-lookup"><span data-stu-id="55f8f-124">Yes</span></span>         |
|<span data-ttu-id="55f8f-125">Teams サービス管理者</span><span class="sxs-lookup"><span data-stu-id="55f8f-125">Teams Service Administrator</span></span>     |<span data-ttu-id="55f8f-126">はい</span><span class="sxs-lookup"><span data-stu-id="55f8f-126">Yes</span></span>         |<span data-ttu-id="55f8f-127">はい</span><span class="sxs-lookup"><span data-stu-id="55f8f-127">Yes</span></span>         |<span data-ttu-id="55f8f-128">はい</span><span class="sxs-lookup"><span data-stu-id="55f8f-128">Yes</span></span>         |<span data-ttu-id="55f8f-129">はい</span><span class="sxs-lookup"><span data-stu-id="55f8f-129">Yes</span></span>         |
|<span data-ttu-id="55f8f-130">Teams 通信管理者</span><span class="sxs-lookup"><span data-stu-id="55f8f-130">Teams Communications Administrator</span></span>     |<span data-ttu-id="55f8f-131">はい</span><span class="sxs-lookup"><span data-stu-id="55f8f-131">Yes</span></span>         |<span data-ttu-id="55f8f-132">はい</span><span class="sxs-lookup"><span data-stu-id="55f8f-132">Yes</span></span>         |<span data-ttu-id="55f8f-133">はい</span><span class="sxs-lookup"><span data-stu-id="55f8f-133">Yes</span></span>         |<span data-ttu-id="55f8f-134">はい</span><span class="sxs-lookup"><span data-stu-id="55f8f-134">Yes</span></span>         |
|<span data-ttu-id="55f8f-135">Teams 通信サポート エンジニア</span><span class="sxs-lookup"><span data-stu-id="55f8f-135">Teams Communications Support Engineer</span></span>     |<span data-ttu-id="55f8f-136">はい</span><span class="sxs-lookup"><span data-stu-id="55f8f-136">Yes</span></span>         |<span data-ttu-id="55f8f-137">はい</span><span class="sxs-lookup"><span data-stu-id="55f8f-137">Yes</span></span>         |<span data-ttu-id="55f8f-138">はい</span><span class="sxs-lookup"><span data-stu-id="55f8f-138">Yes</span></span>         |<span data-ttu-id="55f8f-139">いいえ</span><span class="sxs-lookup"><span data-stu-id="55f8f-139">No</span></span>         |
|<span data-ttu-id="55f8f-140">Teams 通信サポート スペシャリスト</span><span class="sxs-lookup"><span data-stu-id="55f8f-140">Teams Communications Support Specialist</span></span>     |<span data-ttu-id="55f8f-141">はい</span><span class="sxs-lookup"><span data-stu-id="55f8f-141">Yes</span></span>         |<span data-ttu-id="55f8f-142">いいえ</span><span class="sxs-lookup"><span data-stu-id="55f8f-142">No</span></span>         |<span data-ttu-id="55f8f-143">はい</span><span class="sxs-lookup"><span data-stu-id="55f8f-143">Yes</span></span>         |<span data-ttu-id="55f8f-144">いいえ</span><span class="sxs-lookup"><span data-stu-id="55f8f-144">No</span></span>         |
|<span data-ttu-id="55f8f-145">Skype for Business 管理者</span><span class="sxs-lookup"><span data-stu-id="55f8f-145">Skype for Business Administrator</span></span>     |<span data-ttu-id="55f8f-146">はい</span><span class="sxs-lookup"><span data-stu-id="55f8f-146">Yes</span></span>         |<span data-ttu-id="55f8f-147">はい</span><span class="sxs-lookup"><span data-stu-id="55f8f-147">Yes</span></span>         |<span data-ttu-id="55f8f-148">はい</span><span class="sxs-lookup"><span data-stu-id="55f8f-148">Yes</span></span>         |<span data-ttu-id="55f8f-149">はい</span><span class="sxs-lookup"><span data-stu-id="55f8f-149">Yes</span></span>         |
|<span data-ttu-id="55f8f-150">Azure AD グローバルリーダー</span><span class="sxs-lookup"><span data-stu-id="55f8f-150">Azure AD Global Reader</span></span> |<span data-ttu-id="55f8f-151">はい</span><span class="sxs-lookup"><span data-stu-id="55f8f-151">Yes</span></span>         |<span data-ttu-id="55f8f-152">はい</span><span class="sxs-lookup"><span data-stu-id="55f8f-152">Yes</span></span>         |<span data-ttu-id="55f8f-153">はい</span><span class="sxs-lookup"><span data-stu-id="55f8f-153">Yes</span></span>         |<span data-ttu-id="55f8f-154">いいえ</span><span class="sxs-lookup"><span data-stu-id="55f8f-154">No</span></span>         |
|<span data-ttu-id="55f8f-155">Office 365 レポートリーダー<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="55f8f-155">Office 365 Reports Reader<sup>1</sup></span></span>     |<span data-ttu-id="55f8f-156">はい</span><span class="sxs-lookup"><span data-stu-id="55f8f-156">Yes</span></span>         |<span data-ttu-id="55f8f-157">いいえ</span><span class="sxs-lookup"><span data-stu-id="55f8f-157">No</span></span>         |<span data-ttu-id="55f8f-158">はい</span><span class="sxs-lookup"><span data-stu-id="55f8f-158">Yes</span></span>         |<span data-ttu-id="55f8f-159">いいえ</span><span class="sxs-lookup"><span data-stu-id="55f8f-159">No</span></span>         |

<span data-ttu-id="55f8f-160"><sup>1</sup> CQD レポートの読み取りに加えて、Office 365 レポート閲覧者は、管理センターのすべての [アクティビティレポート](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) と、 [Microsoft 365 導入コンテンツパック](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)のすべてのレポートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="55f8f-160"><sup>1</sup> In addition to reading CQD reports, the Office 365 Reports Reader can view all the [activity reports](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) in the admin center and any reports from the [Microsoft 365 Adoption content pack](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).</span></span>

> [!NOTE]
> <span data-ttu-id="55f8f-161">[Euii (エンドユーザーを特定できる情報)](CQD-data-and-reports.md#euii-data)が表示されず、この情報を表示することを許可されているロールの1つがある場合は、CQD によって、28日間のみ EUII が保持されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="55f8f-161">If you're not seeing [EUII (end-user identifiable information)](CQD-data-and-reports.md#euii-data) and you have one of the roles that's permitted to see this information, keep in mind that CQD only keeps EUII for 28 days.</span></span> <span data-ttu-id="55f8f-162">28日より前のものは削除されます。</span><span class="sxs-lookup"><span data-stu-id="55f8f-162">Anything older than 28 days is deleted.</span></span>

<span data-ttu-id="55f8f-163">これらの役割の詳細については、「 [Office 365 管理者ロールについ](/office365/admin/add-users/about-admin-roles)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55f8f-163">For more information about these roles, see [About Office 365 admin roles](/office365/admin/add-users/about-admin-roles).</span></span>


<span data-ttu-id="55f8f-164">初めてサインインすると、CQD でデータの収集と処理が開始されます。</span><span class="sxs-lookup"><span data-stu-id="55f8f-164">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="55f8f-165">2019年12月以降、古いバージョンの CQD (cqd.lync.com) にアクセスできます。ただし、従来のポータルでは、最新の CQD (cqd.teams.microsoft.com) へのリンクが提供されています。</span><span class="sxs-lookup"><span data-stu-id="55f8f-165">As of December 2019, you can still access the older version of CQD (cqd.lync.com), although the legacy portal gives you a link to the latest CQD (cqd.teams.microsoft.com).</span></span> <span data-ttu-id="55f8f-166">最終的には、古いバージョンの CQD が廃止されます。</span><span class="sxs-lookup"><span data-stu-id="55f8f-166">Eventually, the older version of CQD will be decommissioned.</span></span> <span data-ttu-id="55f8f-167">2020年7月1日以降、古いバージョンの CQD は最新の CQD のデータにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="55f8f-167">As of July 1, 2020, the older version of CQD accesses data from the latest CQD.</span></span>


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a><span data-ttu-id="55f8f-168">以前のバージョンの CQD から作成したデータとレポートを移行する</span><span class="sxs-lookup"><span data-stu-id="55f8f-168">Migrate building data and reports from previous version of CQD</span></span>

> [!IMPORTANT]
> <span data-ttu-id="55f8f-169">2020年7月1日以降、古い CQD () からの建物データとレポートの移行はできなくなりました https://CQD.lync.com) 。</span><span class="sxs-lookup"><span data-stu-id="55f8f-169">As of July 1, 2020, you can no longer migrate building data and reports from the old CQD (https://CQD.lync.com).</span></span> 



## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="55f8f-170">Power BI を使用して CQD データを分析する</span><span class="sxs-lookup"><span data-stu-id="55f8f-170">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="55f8f-171">2020年1月の新 [機能: POWER BI クエリテンプレートをダウンロードして CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)します。</span><span class="sxs-lookup"><span data-stu-id="55f8f-171">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="55f8f-172">CQD データの分析と報告に使用できる、カスタマイズ可能な Power BI テンプレート。</span><span class="sxs-lookup"><span data-stu-id="55f8f-172">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="55f8f-173">詳細については、「 [POWER BI を使用して CQD データを分析する](CQD-Power-BI-query-templates.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55f8f-173">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>


## <a name="related-topics"></a><span data-ttu-id="55f8f-174">関連項目</span><span class="sxs-lookup"><span data-stu-id="55f8f-174">Related topics</span></span>

[<span data-ttu-id="55f8f-175">Teams の通話品質を向上させて監視する</span><span class="sxs-lookup"><span data-stu-id="55f8f-175">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="55f8f-176">CQD とは何ですか?</span><span class="sxs-lookup"><span data-stu-id="55f8f-176">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="55f8f-177">テナントのアップロードとデータの構築</span><span class="sxs-lookup"><span data-stu-id="55f8f-177">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="55f8f-178">CQD データとレポート</span><span class="sxs-lookup"><span data-stu-id="55f8f-178">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="55f8f-179">CQD を使用して通話と会議の品質を管理する</span><span class="sxs-lookup"><span data-stu-id="55f8f-179">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="55f8f-180">CQD で使用できるディメンションとメジャー</span><span class="sxs-lookup"><span data-stu-id="55f8f-180">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="55f8f-181">CQD でのストリームの分類</span><span class="sxs-lookup"><span data-stu-id="55f8f-181">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="55f8f-182">Power BI を使用して CQD データを分析する</span><span class="sxs-lookup"><span data-stu-id="55f8f-182">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)
