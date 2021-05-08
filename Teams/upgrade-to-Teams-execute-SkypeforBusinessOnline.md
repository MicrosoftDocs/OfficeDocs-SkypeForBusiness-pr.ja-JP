---
title: Skype for Business Online から Microsoft Teams にアップグレードする
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 組織をアップグレードして、Microsoft Teams Online 展開Skype for Business説明します。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7c35909bf7787242a07f89d1442a25365348c91a
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282104"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a><span data-ttu-id="f20a8-103">Skype for Business Online から Teams にアップグレードする</span><span class="sxs-lookup"><span data-stu-id="f20a8-103">Upgrade from Skype for Business Online to Teams</span></span>

<span data-ttu-id="f20a8-104">![展開と実装に重点を置いた、アップグレードのフロー図](media/upgrade-banner-deployment.png "「展開と実装」段階が強調表示された、アップグレード行程の各段階")</span><span class="sxs-lookup"><span data-stu-id="f20a8-104">![Upgrade journey diagram, emphasizing Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="f20a8-105">この記事は、お客様のアップグレード手順における展開と実装の段階の一部を取り上げています。</span><span class="sxs-lookup"><span data-stu-id="f20a8-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="f20a8-106">先に進む前に、次のアクティビティを完了していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f20a8-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="f20a8-107">プロジェクトの関係者をリスト化した</span><span class="sxs-lookup"><span data-stu-id="f20a8-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="f20a8-108">プロジェクトの対象範囲を定義した</span><span class="sxs-lookup"><span data-stu-id="f20a8-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="f20a8-109">Skype for Business と Teams の共存と相互運用を理解した</span><span class="sxs-lookup"><span data-stu-id="f20a8-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="f20a8-110">アップグレードの手順を選択した</span><span class="sxs-lookup"><span data-stu-id="f20a8-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="f20a8-111">環境を準備した</span><span class="sxs-lookup"><span data-stu-id="f20a8-111">Prepared your environment</span></span>](./upgrade-prepare-environment.md)
- [<span data-ttu-id="f20a8-112">組織を準備した</span><span class="sxs-lookup"><span data-stu-id="f20a8-112">Prepared your organization</span></span>](./upgrade-prepare-organization.md)
- [<span data-ttu-id="f20a8-113">パイロットを実施した</span><span class="sxs-lookup"><span data-stu-id="f20a8-113">Conducted a pilot</span></span>](./pilot-essentials.md)

<span data-ttu-id="f20a8-114">Skype for Business Online を完全にデプロイし、ユーザーを Skype for Business から Teams にアップグレードする場合は、この記事のガイダンスに従います。</span><span class="sxs-lookup"><span data-stu-id="f20a8-114">Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams.</span></span> <span data-ttu-id="f20a8-115">適切な共存モードとアップグレード モードをユーザーに割り当てると、組織が選択したアップグレード体験に基づいて、ユーザーを選択的またはすべてアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="f20a8-115">You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f20a8-116">Skype for Business Online は 2021 年 7 月 31 日に廃止される予定です。それ以降、アクセスとサポートが終了します。</span><span class="sxs-lookup"><span data-stu-id="f20a8-116">Skype for Business Online will be retired on July 31, 2021, after which it will no longer be accessible or supported.</span></span> <span data-ttu-id="f20a8-117">移行によるメリットを最大限に高め、アップグレード実施のための時間を組織で十分確保できるよう、Microsoft Teams への移行をすぐに開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f20a8-117">To maximize benefit realization and ensure your organization has proper time to implement your upgrade, we encourage you to begin your journey to Microsoft Teams today.</span></span> <span data-ttu-id="f20a8-118">アップグレードが成功すると、技術面およびユーザーの準備が整ったことになります。Microsoft Teams への移行を進める際には、必ずこのガイドを活用してください。</span><span class="sxs-lookup"><span data-stu-id="f20a8-118">Remember that a successful upgrade aligns technical and user readiness, so be sure to leverage the guidance herein as you navigate your journey to Microsoft Teams.</span></span>

## <a name="assign-the-coexistence-and-upgrade-mode"></a><span data-ttu-id="f20a8-119">共存モードとアップグレード モードを割り当てる</span><span class="sxs-lookup"><span data-stu-id="f20a8-119">Assign the coexistence and upgrade mode</span></span>

<span data-ttu-id="f20a8-120">TeamsUpgradePolicy の UpgradeToTeams インスタンスを割り当てると、ユーザーを TeamsOnly モードにアップグレードできます。このインスタンスは、Microsoft Teams 管理センターまたは Skype for Business リモート Windows PowerShell セッションを使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="f20a8-120">You can upgrade your users to TeamsOnly mode by assigning the UpgradeToTeams instance of TeamsUpgradePolicy, which can be performed by using the Microsoft Teams admin center or a Skype for Business remote Windows PowerShell session.</span></span> <span data-ttu-id="f20a8-121">これを行うには、ユーザーごとに、またはテナント全体を 1 つの手順でアップグレードする場合は、テナント全体で行います。</span><span class="sxs-lookup"><span data-stu-id="f20a8-121">You can do this either on a per user basis, or on a tenant-wide basis if you want to upgrade the entire tenant in one step.</span></span> 

<span data-ttu-id="f20a8-122">詳細については、「[共存およびアップグレードを設定する](./setting-your-coexistence-and-upgrade-settings.md)」および「[TeamsUpgradePolicy: 移行と共存の管理](upgrade-to-teams-on-prem-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f20a8-122">For more information, see [Setting your coexistence and upgrade settings](./setting-your-coexistence-and-upgrade-settings.md) and [TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).</span></span>

## <a name="upgrade-all-users-to-teams-at-one-time"></a><span data-ttu-id="f20a8-123">すべてのユーザーを一度Teamsにアップグレードする</span><span class="sxs-lookup"><span data-stu-id="f20a8-123">Upgrade all users to Teams at one time</span></span>

<span data-ttu-id="f20a8-124">次の手順に従って、すべてのユーザーを一度にTeamsアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="f20a8-124">Follow these steps to upgrade all of your users to Teams at one time.</span></span>

### <a name="step-1-notify-the-users-of-the-change-optional"></a><span data-ttu-id="f20a8-125">手順 1: 変更をユーザーに通知する (省略可能)</span><span class="sxs-lookup"><span data-stu-id="f20a8-125">Step 1: Notify the users of the change (optional)</span></span>

1. <span data-ttu-id="f20a8-126">管理センター Microsoft Teamsで、[アップグレード] で **[組織全体の設定**  >  **] Teams選択します**。</span><span class="sxs-lookup"><span data-stu-id="f20a8-126">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams upgrade**.</span></span>
2. <span data-ttu-id="f20a8-127">[**共存モード] で**、[アップグレードが利用可能Skype for Businessユーザーに通知する] Teams **を**[オン] に **変更します**。</span><span class="sxs-lookup"><span data-stu-id="f20a8-127">Under **Coexistence mode**, change the **Notify Skype for Business users that an upgrade to Teams is available** switch to **On**.</span></span>

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a><span data-ttu-id="f20a8-128">手順 2: 組織の共存モードを TeamsOnly に設定する</span><span class="sxs-lookup"><span data-stu-id="f20a8-128">Step 2: Set the coexistence mode to TeamsOnly for the organization</span></span>

1. <span data-ttu-id="f20a8-129">管理センター Microsoft Teams、組織全体の設定 **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f20a8-129">In the Microsoft Teams admin center, select **Org-wide settings**.</span></span>
2. <span data-ttu-id="f20a8-130">[Teams **モード] ドロップダウン** リストから **[モード** のみ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f20a8-130">Select **Teams Only** mode from the **Coexistence mode** drop-down list.</span></span>

## <a name="upgrade-users-in-stages"></a><span data-ttu-id="f20a8-131">ユーザーをステージにアップグレードする</span><span class="sxs-lookup"><span data-stu-id="f20a8-131">Upgrade users in stages</span></span>

<span data-ttu-id="f20a8-132">ユーザーを TeamsOnly に段階的にアップグレードする場合は、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="f20a8-132">Follow these steps if you want to gradually upgrade your users to TeamsOnly.</span></span>

### <a name="step-1-identify-groups-of-users-for-upgrade"></a><span data-ttu-id="f20a8-133">手順 1: アップグレードするユーザーのグループを識別する</span><span class="sxs-lookup"><span data-stu-id="f20a8-133">Step 1: Identify groups of users for upgrade</span></span>

<span data-ttu-id="f20a8-134">多くの場合、組織はユーザーの成功の波で組織をアップグレードすることができます。</span><span class="sxs-lookup"><span data-stu-id="f20a8-134">Often organizations may choose to upgrade their organizations in success waves of users.</span></span>  <span data-ttu-id="f20a8-135">これらのユーザーを最初に特定して、管理センターで簡単に検索Microsoft Teams必要があります。</span><span class="sxs-lookup"><span data-stu-id="f20a8-135">You'll want to identify these users first so you can easily search for them in the Microsoft Teams admin center.</span></span> <span data-ttu-id="f20a8-136">または、PowerShell を使用して、より効率的に行う必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="f20a8-136">Alternatively, you may want to use PowerShell to more efficiently do this.</span></span> <span data-ttu-id="f20a8-137">特定のアップグレード ウェーブの一連のユーザーを特定したら、残りの手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="f20a8-137">Once you have identified the set of users for a given upgrade wave, continue with the remaining steps.</span></span>

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a><span data-ttu-id="f20a8-138">手順 2: 現在のアップグレード ウェーブのユーザーに通知を設定する (省略可能)</span><span class="sxs-lookup"><span data-stu-id="f20a8-138">Step 2: Set notification for the users in the current upgrade wave (optional)</span></span>

<span data-ttu-id="f20a8-139">管理センター Microsoft Teams場合、最大 20 人のユーザーに対して TeamsUpgradePolicy を一度に構成できます。</span><span class="sxs-lookup"><span data-stu-id="f20a8-139">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="f20a8-140">管理センター Microsoft Teams[ユーザー] を選択し、アップグレードする必要がある最大 20 人のユーザーのチェック ボックスを見つけて複数選択します。</span><span class="sxs-lookup"><span data-stu-id="f20a8-140">In the Microsoft Teams admin center, select **Users**, and find and multi-select the checkbox for up to 20 users who should be upgraded.</span></span> 
2. <span data-ttu-id="f20a8-141">リスト **ビューの左上** 隅にある [設定の編集] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f20a8-141">Select **Edit settings** in the upper left corner of the listview.</span></span> 
3. <span data-ttu-id="f20a8-142">右側の **[設定の編集**] ウィンドウの [アップグレード] で、[Teams **通知**] を [ユーザーに通知 **Skype for Business]** スイッチを [オン] に **変更します**。</span><span class="sxs-lookup"><span data-stu-id="f20a8-142">In the **Edit settings** pane on the right, under **Teams upgrade**, change **Notify the Skype for Business user** switch to **On**.</span></span> <span data-ttu-id="f20a8-143">注: 共存モードの値が "組織全体の設定を使用" の場合、このスイッチは表示されません。そのため、これらのユーザーの共存モードを組織の既定値に明示的に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f20a8-143">Note: If the value of coexistence mode is "Use Org-wide settings", you won't see this switch, so you'll need to first explicitly set the Coexistence mode for these users to whatever the default value is for the org.</span></span>

<span data-ttu-id="f20a8-144">または、PowerShell を使用して一度にユーザー のグループに対する通知を有効にする方が簡単な場合があります。</span><span class="sxs-lookup"><span data-stu-id="f20a8-144">Alternatively, you may find it easier to enable notifications for groups of users at once using PowerShell.</span></span> 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a><span data-ttu-id="f20a8-145">手順 3: ユーザーの共存モードを [共有のみ] Teamsする</span><span class="sxs-lookup"><span data-stu-id="f20a8-145">Step 3: Set the coexistence mode for users to Teams Only</span></span>

<span data-ttu-id="f20a8-146">現在のウェーブのユーザーをアップグレードして、Teams を唯一のアプリケーションとして使用する準備ができたら、ユーザーの共存モードを [Teams のみ] に設定します。</span><span class="sxs-lookup"><span data-stu-id="f20a8-146">When you are ready to upgrade the users in the current wave to use Teams as their only application, set the Coexistence mode for the users to Teams Only.</span></span>

<span data-ttu-id="f20a8-147">管理センター Microsoft Teams場合、最大 20 人のユーザーに対して TeamsUpgradePolicy を一度に構成できます。</span><span class="sxs-lookup"><span data-stu-id="f20a8-147">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="f20a8-148">管理センター Microsoft Teams、[ユーザー]**を選択** し、最大 20 人のユーザーのチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="f20a8-148">In the Microsoft Teams admin center, select **Users**, and then select the checkbox for up to 20 users.</span></span>
2. <span data-ttu-id="f20a8-149">リスト **ビューの左上** 隅にある [設定の編集] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f20a8-149">Select **Edit settings** in the upper left corner of the listview.</span></span>
3. <span data-ttu-id="f20a8-150">右側の **[設定** の編集] ウィンドウの [Teams **アップグレード**] セクションで、共存モードをドロップダウン リストの [Teams **のみ**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="f20a8-150">In the **Edit settings** pane on the right, under **Teams upgrade** section, set the coexistence mode to **Teams Only** in the drop-down list.</span></span>

<span data-ttu-id="f20a8-151">または、PowerShell を使用してユーザーのグループを一度にアップグレードする方が簡単な場合があります。</span><span class="sxs-lookup"><span data-stu-id="f20a8-151">Alternatively, you may find it easier to upgrade groups of users at once using PowerShell.</span></span> 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a><span data-ttu-id="f20a8-152">手順 4: 連続するユーザーのウェーブに対して手順 1 ~ 3 を繰り返す</span><span class="sxs-lookup"><span data-stu-id="f20a8-152">Step 4: Repeat steps 1-3 for successive waves of users</span></span>

<span data-ttu-id="f20a8-153">Teams モードへのアップグレードを検証し、展開する準備ができたら、前の手順を繰り返して TeamsOnly を他のユーザーに適用します。</span><span class="sxs-lookup"><span data-stu-id="f20a8-153">As you validate your upgrade to Teams Only mode and are ready to expand, repeat the previous steps to apply TeamsOnly to  more users.</span></span>  


## <a name="phone-system-and-pstn-connectivity-options"></a><span data-ttu-id="f20a8-154">電話システム PSTN 接続オプション</span><span class="sxs-lookup"><span data-stu-id="f20a8-154">Phone System and PSTN connectivity options</span></span>

<span data-ttu-id="f20a8-155">電話システムのTeamsは、ユーザーが TeamsOnly モードの場合にサポートされます。</span><span class="sxs-lookup"><span data-stu-id="f20a8-155">Phone System with Teams is supported after the user is in TeamsOnly mode.</span></span> <span data-ttu-id="f20a8-156">(ユーザーが Islands モードの場合電話システムは、Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="f20a8-156">(If the user is in Islands mode, Phone System is only supported with Skype for Business.)</span></span>  

### <a name="pstn-connectivity-options"></a><span data-ttu-id="f20a8-157">PSTN 接続オプション</span><span class="sxs-lookup"><span data-stu-id="f20a8-157">PSTN connectivity options</span></span>

<span data-ttu-id="f20a8-158">公衆交換電話網 (PSTN) 接続オプションを検討する場合、Skype for Business Online から TeamsOnly モードに移行する場合、次の 2 つのシナリオが考えられます。</span><span class="sxs-lookup"><span data-stu-id="f20a8-158">When considering Public Switched Telephone Network (PSTN) connectivity options, there are two possible scenarios when moving from Skype for Business Online to TeamsOnly mode:</span></span>

- <span data-ttu-id="f20a8-159">Microsoft 通話プランを使用している Skype for Business Online のユーザー。</span><span class="sxs-lookup"><span data-stu-id="f20a8-159">A user in Skype for Business Online, with a Microsoft Calling Plan.</span></span> <span data-ttu-id="f20a8-160">アップグレードすると、このユーザーは Microsoft 通話プランを引き続き使用します。</span><span class="sxs-lookup"><span data-stu-id="f20a8-160">Upon upgrade, this user will continue to have a Microsoft Calling plan.</span></span> <span data-ttu-id="f20a8-161">これは、いくつかの手順のみを必要とする最も簡単なシナリオです。</span><span class="sxs-lookup"><span data-stu-id="f20a8-161">This is the simplest scenario requiring only a couple of steps.</span></span> <span data-ttu-id="f20a8-162">詳細については、「Microsoft 通話プランを[使用Skype for Businessオンラインから」を参照してください](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="f20a8-162">For more information, see [From Skype for Business Online with Microsoft Calling Plans](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans).</span></span>

- <span data-ttu-id="f20a8-163">Skype for Business Online のユーザー。オンプレミスまたは Cloud Connector Edition を介してSkype for Business音声機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="f20a8-163">A user in Skype for Business Online, with on-premises voice functionality through Skype for Business on-premises or Cloud Connector Edition.</span></span> <span data-ttu-id="f20a8-164">このユーザーの Teams へのアップグレードは、その TeamsOnly ユーザーが確実に PSTN 機能を持てるようにするため、ユーザーのダイレクト ルーティングへの移行に合わせた調整が必要になります。</span><span class="sxs-lookup"><span data-stu-id="f20a8-164">The user’s upgrade to Teams needs to be coordinated with migration of the user to Direct Routing to ensure the TeamsOnly user has PSTN functionality.</span></span>  <span data-ttu-id="f20a8-165">詳細については、「オンプレミス音声を使用[した Skype for Business Online から」を参照してください](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)。</span><span class="sxs-lookup"><span data-stu-id="f20a8-165">For more information see, [From Skype for Business Online with on-premises voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice).</span></span>