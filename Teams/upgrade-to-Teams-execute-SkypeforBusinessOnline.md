---
title: マイクロソフト チームをオンラインでビジネス用の Skype のアップグレードします。展開
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: ビジネス オンラインの Skype からチームへのアップグレードに関する考慮事項
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 82577b8e8102baca9ea9681bb94d4a0c73f8b01e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32218678"
---
<span data-ttu-id="5fae4-103">![展開と実装の段階に重点を置いた、アップグレード手順の各段階](media/upgrade-banner-deployment.png "展開と実装の段階に重点を置いた、アップグレード手順の各段階")</span><span class="sxs-lookup"><span data-stu-id="5fae4-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="5fae4-104">この記事は、お客様のアップグレード手順における展開と実装の段階の一部を取り上げています。</span><span class="sxs-lookup"><span data-stu-id="5fae4-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="5fae4-105">先に進む前に、次のアクティビティを完了していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5fae4-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="5fae4-106">プロジェクトの関係者をリスト化した</span><span class="sxs-lookup"><span data-stu-id="5fae4-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="5fae4-107">プロジェクトの対象範囲を定義した</span><span class="sxs-lookup"><span data-stu-id="5fae4-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="5fae4-108">Skype for Business と Teams の共存と相互運用を理解した</span><span class="sxs-lookup"><span data-stu-id="5fae4-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="5fae4-109">アップグレードの手順を選択した</span><span class="sxs-lookup"><span data-stu-id="5fae4-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="5fae4-110">環境を準備した</span><span class="sxs-lookup"><span data-stu-id="5fae4-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="5fae4-111">組織を準備した</span><span class="sxs-lookup"><span data-stu-id="5fae4-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="5fae4-112">パイロットを実施した</span><span class="sxs-lookup"><span data-stu-id="5fae4-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-skype-for-business-online-to-teams"></a><span data-ttu-id="5fae4-113">Skype for Business Online から Teams にアップグレードする</span><span class="sxs-lookup"><span data-stu-id="5fae4-113">Upgrade from Skype for Business Online to Teams</span></span>

<span data-ttu-id="5fae4-114">完全 Skype をオンライン ビジネスを展開しているし、ビジネスの Skype からのチームにユーザーをアップグレードする場合のこの資料の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="5fae4-114">Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams.</span></span> <span data-ttu-id="5fae4-115">ユーザーを選択的にアップグレードすることができますまたはアップグレードをに基づいて、オールインワンの旅を適切な共存およびアップグレード モードをユーザーに割り当てることにより、組織が選択されます。</span><span class="sxs-lookup"><span data-stu-id="5fae4-115">You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a><span data-ttu-id="5fae4-116">共存およびアップグレード モードを割り当てる</span><span class="sxs-lookup"><span data-stu-id="5fae4-116">Assign the coexistence and upgrade mode</span></span>

<span data-ttu-id="5fae4-117">ビジネス リモートの Windows Powershell セッションでマイクロソフトのチームの管理センターや、Skype を使用して実行することができる TeamsUpgradePolicy の TeamsOnly モードを割り当てることによって、チームがユーザーをアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="5fae4-117">You can upgrade your users by Teams by assigning the TeamsOnly mode of TeamsUpgradePolicy, which can be performed by using the Microsoft Teams admin center or a Skype for Business remote Windows Powershell session.</span></span>

<span data-ttu-id="5fae4-118">詳細については、「[共存およびアップグレードを設定する](https://aka.ms/SkypeToTeams-SetCoexistence)」および「[TeamsUpgradePolicy: 移行と共存の管理](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5fae4-118">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

## <a name="upgrade-all-users-to-teams-at-one-time"></a><span data-ttu-id="5fae4-119">チームにすべてのユーザーを同時にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="5fae4-119">Upgrade all users to Teams at one time</span></span>

<span data-ttu-id="5fae4-120">この手順では、一度に 1 つのチームにすべてのユーザーをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="5fae4-120">Follow these steps to upgrade all of your users to Teams at one time.</span></span>

### <a name="step-1-notify-the-users-of-the-change"></a><span data-ttu-id="5fae4-121">手順 1: ユーザーに変更を通知します。</span><span class="sxs-lookup"><span data-stu-id="5fae4-121">Step 1: Notify the users of the change</span></span>

1. <span data-ttu-id="5fae4-122">マイクロソフトのチーム管理センターで、**組織全体の設定**を選択して > **のチームをアップグレード**します。</span><span class="sxs-lookup"><span data-stu-id="5fae4-122">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams upgrade**.</span></span>
2. <span data-ttu-id="5fae4-123">**共存モード**では、[**上**に**チームへのアップグレードが利用可能なビジネス ・ ユーザーの通知の Skype**のスイッチを変更します。</span><span class="sxs-lookup"><span data-stu-id="5fae4-123">Under **Coexistence mode**, change the **Notify Skype for Business users that an upgrade to Teams is available** switch to **On**.</span></span>

### <a name="step-2-set-the-coexistence-mode-for-the-users"></a><span data-ttu-id="5fae4-124">ステップ 2: ユーザーの共存モードを設定します。</span><span class="sxs-lookup"><span data-stu-id="5fae4-124">Step 2: Set the coexistence mode for the users</span></span>

1. <span data-ttu-id="5fae4-125">マイクロソフトのチーム管理センターでは、**組織全体の設定**を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fae4-125">In the Microsoft Teams admin center, select **Org-wide settings**.</span></span>
2. <span data-ttu-id="5fae4-126">**共存モード**」ドロップ ダウン リストから**チームのみ**のモードを選択します。</span><span class="sxs-lookup"><span data-stu-id="5fae4-126">Select **Teams Only** mode from the **Coexistence mode** drop-down list.</span></span>

## <a name="upgrade-users-in-stages"></a><span data-ttu-id="5fae4-127">ユーザーを段階的にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="5fae4-127">Upgrade users in stages</span></span>

<span data-ttu-id="5fae4-128">チームにユーザーを段階的にアップグレードする場合は、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5fae4-128">Follow these steps if you want to gradually upgrade your users to Teams.</span></span>

### <a name="step-1-create-your-user-cohorts-for-the-upgrade"></a><span data-ttu-id="5fae4-129">手順 1: アップグレードのため、ユーザーの cohorts を作成します。</span><span class="sxs-lookup"><span data-stu-id="5fae4-129">Step 1: Create your user cohorts for the upgrade</span></span>

<span data-ttu-id="5fae4-130">Cohorts のユーザーは、同時にチームのみのモードに移動するユーザーのグループです。</span><span class="sxs-lookup"><span data-stu-id="5fae4-130">User cohorts are groups of users who will be moved to Teams Only mode at the same time.</span></span>

<span data-ttu-id="5fae4-131">ユーザーの cohorts (追加のユーザーの選択] ページへのリンク) を作成するには</span><span class="sxs-lookup"><span data-stu-id="5fae4-131">To create your user cohorts (Add link to user selection page)</span></span>

### <a name="step-2-set-the-user-mode-to-islands"></a><span data-ttu-id="5fae4-132">ステップ 2: 島へのユーザー モードを設定します。</span><span class="sxs-lookup"><span data-stu-id="5fae4-132">Step 2: Set the user mode to Islands</span></span>

1. <span data-ttu-id="5fae4-133">マイクロソフトのチーム管理センターで、**ユーザー**を選択し、ユーザーの cohort します。</span><span class="sxs-lookup"><span data-stu-id="5fae4-133">In the Microsoft Teams admin center, select **Users**, and then select a user cohort.</span></span>
2. <span data-ttu-id="5fae4-134">**チームのアップグレード**をするには、横の**編集**を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fae4-134">Next to **Teams upgrade**, select **Edit**.</span></span>
3. <span data-ttu-id="5fae4-135">**共存モード**では、下の**チームのアップグレード**ウィンドウのドロップ ダウン リストから**島**を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fae4-135">In the **Teams Upgrade** pane, under **Coexistence mode**, select **Islands** from the drop-down list.</span></span>

### <a name="step-3-set-notification-for-the-user-optional"></a><span data-ttu-id="5fae4-136">ユーザーの通知を設定 (省略可能) 手順 3。</span><span class="sxs-lookup"><span data-stu-id="5fae4-136">Step 3: Set notification for the user (optional)</span></span>

1. <span data-ttu-id="5fae4-137">マイクロソフトのチーム管理センターでは、**ユーザー**を選択し、ユーザー cohort を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fae4-137">In the Microsoft Teams admin center, select **Users**, and select a user cohort.</span></span>
2. <span data-ttu-id="5fae4-138">**チームのアップグレード**をするには、横の**編集**を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fae4-138">Next to **Teams upgrade**, select **Edit**.</span></span>
3. <span data-ttu-id="5fae4-139">**共存モード**では、下の**チームのアップグレード**ウィンドウの**上**に**通知 Skype ビジネス ユーザーの**スイッチを変更します。</span><span class="sxs-lookup"><span data-stu-id="5fae4-139">In the **Teams Upgrade** pane, under **Coexistence mode**, change **Notify the Skype for Business user** switch to **On**.</span></span>

### <a name="step-4-set-the-user-mode-to-teams-only"></a><span data-ttu-id="5fae4-140">手順 4: チームのみに、ユーザー モードを設定します。</span><span class="sxs-lookup"><span data-stu-id="5fae4-140">Step 4: Set the user mode to Teams Only</span></span>

<span data-ttu-id="5fae4-141">唯一のアプリケーションとして、チームを使用するユーザーをアップグレードする準備ができたら、チームだけにユーザーの共存モードを設定します。</span><span class="sxs-lookup"><span data-stu-id="5fae4-141">When you are ready to upgrade the users to use Teams as their only application, set the Coexistence mode for the user to Teams Only.</span></span>

1. <span data-ttu-id="5fae4-142">マイクロソフトのチーム管理センターで、**ユーザー**を選択し、ユーザーの cohort します。</span><span class="sxs-lookup"><span data-stu-id="5fae4-142">In the Microsoft Teams admin center, select **Users**, and then select a user cohort.</span></span>
2. <span data-ttu-id="5fae4-143">**チームのアップグレード**をするには、横の**編集**を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fae4-143">Next to **Teams upgrade**, select **Edit**.</span></span>
3. <span data-ttu-id="5fae4-144">**チームのアップグレード**ウィンドウの [、**共存モード**では、ドロップ ダウン リストからの**チームのみ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fae4-144">In the **Teams Upgrade** pane, under **Coexistence mode**, select **Teams Only** from the drop-down list.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="5fae4-145">電話システムと Teams のアップグレード</span><span class="sxs-lookup"><span data-stu-id="5fae4-145">Phone System and Teams upgrade</span></span>

<span data-ttu-id="5fae4-146">場合は、オンライン ビジネスの展開、Skype には、計画を呼び出すと、電話システムが含まれています、、公衆交換電話網 (PSTN) プロバイダーが、チームにユーザーをアップグレードするは自動的に移行チームを呼び出す PSTN を受信します。</span><span class="sxs-lookup"><span data-stu-id="5fae4-146">If your Skype for Business Online deployment includes Phone System with Calling Plans and Microsoft is your public switched telephone network (PSTN) provider, upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="5fae4-147">オンライン ビジネス展開するため、Skype には、クラウドのコネクタのエディションでの電話システムが含まれている場合は、[電話システムの直接のルーティングのための追加の考慮事項](2-envision-make-my-service-decisions-direct-routing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5fae4-147">If your Skype for Business Online deployment includes Phone System with Cloud Connector Edition, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>