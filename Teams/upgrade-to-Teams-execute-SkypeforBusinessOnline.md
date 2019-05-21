---
title: Skype for Business Online を Microsoft Teams にアップグレードする |Deploy
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Skype for Business Online から Teams にアップグレードする場合の考慮事項
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6748397c354f9238282f9646388993fc0e9f7b88
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902722"
---
<span data-ttu-id="ad60e-103">![展開と実装の段階に重点を置いた、アップグレード手順の各段階](media/upgrade-banner-deployment.png "展開と実装の段階に重点を置いた、アップグレード手順の各段階")</span><span class="sxs-lookup"><span data-stu-id="ad60e-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="ad60e-104">この記事は、お客様のアップグレード手順における展開と実装の段階の一部を取り上げています。</span><span class="sxs-lookup"><span data-stu-id="ad60e-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="ad60e-105">先に進む前に、次のアクティビティを完了していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ad60e-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="ad60e-106">プロジェクトの関係者をリスト化した</span><span class="sxs-lookup"><span data-stu-id="ad60e-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="ad60e-107">プロジェクトの対象範囲を定義した</span><span class="sxs-lookup"><span data-stu-id="ad60e-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="ad60e-108">Skype for Business と Teams の共存と相互運用を理解した</span><span class="sxs-lookup"><span data-stu-id="ad60e-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="ad60e-109">アップグレードの手順を選択した</span><span class="sxs-lookup"><span data-stu-id="ad60e-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="ad60e-110">環境を準備した</span><span class="sxs-lookup"><span data-stu-id="ad60e-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="ad60e-111">組織を準備した</span><span class="sxs-lookup"><span data-stu-id="ad60e-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="ad60e-112">パイロットを実施した</span><span class="sxs-lookup"><span data-stu-id="ad60e-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-skype-for-business-online-to-teams"></a><span data-ttu-id="ad60e-113">Skype for Business Online から Teams にアップグレードする</span><span class="sxs-lookup"><span data-stu-id="ad60e-113">Upgrade from Skype for Business Online to Teams</span></span>

<span data-ttu-id="ad60e-114">Skype for business Online を完全に展開していて、ユーザーを Skype for Business から Teams にアップグレードする場合は、この記事の指示に従ってください。</span><span class="sxs-lookup"><span data-stu-id="ad60e-114">Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams.</span></span> <span data-ttu-id="ad60e-115">組織で選択されているアップグレードの過程に基づいて、ユーザーを選択的またはすべてのユーザーにアップグレードするには、適切な共存とアップグレードモードをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ad60e-115">You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a><span data-ttu-id="ad60e-116">共存とアップグレードモードを割り当てる</span><span class="sxs-lookup"><span data-stu-id="ad60e-116">Assign the coexistence and upgrade mode</span></span>

<span data-ttu-id="ad60e-117">Microsoft Teams 管理センターまたは Skype for Business リモート Windows Powershell セッションを使用して実行できる TeamsUpgradePolicy の UpgradeToTeams インスタンスを割り当てることによって、ユーザーを TeamsOnly モードにアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="ad60e-117">You can upgrade your users to TeamsOnly mode by assigning the UpgradeToTeams instance of TeamsUpgradePolicy, which can be performed by using the Microsoft Teams admin center or a Skype for Business remote Windows Powershell session.</span></span> <span data-ttu-id="ad60e-118">この操作は、1つのステップでテナント全体を1回で行う場合は、ユーザーごとに、またはテナント全体で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ad60e-118">You can do this either on a per user basis, or on a tenant-wide basis if you want to ugprade the entire tenant in one step.</span></span> 

<span data-ttu-id="ad60e-119">詳細については、「[共存およびアップグレードを設定する](https://aka.ms/SkypeToTeams-SetCoexistence)」および「[TeamsUpgradePolicy: 移行と共存の管理](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad60e-119">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

## <a name="upgrade-all-users-to-teams-at-one-time"></a><span data-ttu-id="ad60e-120">一度にすべてのユーザーを Teams にアップグレードする</span><span class="sxs-lookup"><span data-stu-id="ad60e-120">Upgrade all users to Teams at one time</span></span>

<span data-ttu-id="ad60e-121">すべてのユーザーをチームに一度にアップグレードするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ad60e-121">Follow these steps to upgrade all of your users to Teams at one time.</span></span>

### <a name="step-1-notify-the-users-of-the-change-optional"></a><span data-ttu-id="ad60e-122">手順 1: ユーザーに変更を通知する (省略可能)</span><span class="sxs-lookup"><span data-stu-id="ad60e-122">Step 1: Notify the users of the change (optional)</span></span>

1. <span data-ttu-id="ad60e-123">Microsoft Teams 管理センターで、[**組織全体の設定** > ]**チームのアップグレード**を選択します。</span><span class="sxs-lookup"><span data-stu-id="ad60e-123">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams upgrade**.</span></span>
2. <span data-ttu-id="ad60e-124">[**共存モード**] で、[**チームへのアップグレードが可能であることを Skype for Business ユーザーに通知**する] を **[オン**] に変更します。</span><span class="sxs-lookup"><span data-stu-id="ad60e-124">Under **Coexistence mode**, change the **Notify Skype for Business users that an upgrade to Teams is available** switch to **On**.</span></span>

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a><span data-ttu-id="ad60e-125">手順 2: 組織の場合のみ、共存モードを teams に設定します。</span><span class="sxs-lookup"><span data-stu-id="ad60e-125">Step 2: Set the coexistence mode to TeamsOnly for the organization</span></span>

1. <span data-ttu-id="ad60e-126">Microsoft Teams 管理センターで、[**組織全体の設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ad60e-126">In the Microsoft Teams admin center, select **Org-wide settings**.</span></span>
2. <span data-ttu-id="ad60e-127">[**共存モード**] ドロップダウンリストから [**チームのみ**] モードを選択します。</span><span class="sxs-lookup"><span data-stu-id="ad60e-127">Select **Teams Only** mode from the **Coexistence mode** drop-down list.</span></span>

## <a name="upgrade-users-in-stages"></a><span data-ttu-id="ad60e-128">ユーザーを段階的にアップグレードする</span><span class="sxs-lookup"><span data-stu-id="ad60e-128">Upgrade users in stages</span></span>

<span data-ttu-id="ad60e-129">ユーザーをチームに段階的にアップグレードする場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ad60e-129">Follow these steps if you want to gradually upgrade your users to TeamsOnly.</span></span>

### <a name="step-1-identify-groups-of-users-for-upgrade"></a><span data-ttu-id="ad60e-130">手順 1: アップグレードするユーザーグループを特定する</span><span class="sxs-lookup"><span data-stu-id="ad60e-130">Step 1: Identify groups of users for upgrade</span></span>

<span data-ttu-id="ad60e-131">組織では、ユーザーの成功波で組織のアップグレードが選択されることがあります。</span><span class="sxs-lookup"><span data-stu-id="ad60e-131">Often organizations may choose to upgrade their organizations in success waves of users.</span></span>  <span data-ttu-id="ad60e-132">これらのユーザーを最初に特定して、Microsoft Teams 管理センターで簡単に検索できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ad60e-132">You'll want to identify these users first so you can easily search for them in the Microsoft Teams admin center.</span></span> <span data-ttu-id="ad60e-133">または、PowerShell を使用して、より効率的にこの操作を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="ad60e-133">Alternatively, you may want to use PowerShell to more efficiently do this.</span></span> <span data-ttu-id="ad60e-134">特定のアップグレードウェーブの一連のユーザーを特定したら、残りの手順を続行します。</span><span class="sxs-lookup"><span data-stu-id="ad60e-134">Once you have identified the set of users for a given upgrade wave, continue with the remaining steps.</span></span>

### <a name="step-2-set-notification-for-the-users-in-the-current-ugprade-wave-optional"></a><span data-ttu-id="ad60e-135">手順 2: 現在のユーザーに対して通知を設定する (省略可能)</span><span class="sxs-lookup"><span data-stu-id="ad60e-135">Step 2: Set notification for the users in the current ugprade wave (optional)</span></span>

<span data-ttu-id="ad60e-136">Microsoft Teams 管理センターを使用している場合は、一度に最大20人のユーザーに対して TeamsUpgradePolicy を構成できます。</span><span class="sxs-lookup"><span data-stu-id="ad60e-136">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="ad60e-137">Microsoft Teams 管理センターで、[**ユーザー**] を選択し、アップグレードする必要がある最大20人のユーザーのチェックボックスをオンまたは複数選択します。</span><span class="sxs-lookup"><span data-stu-id="ad60e-137">In the Microsoft Teams admin center, select **Users**, and find and multi-select the checkbox for up to 20 users who should be upgraded.</span></span> 
2. <span data-ttu-id="ad60e-138">Listview の左上隅にある [**設定の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ad60e-138">Select **Edit settings** in the upper left corner of the listview.</span></span> 
3. <span data-ttu-id="ad60e-139">右側の [**設定の編集**] ウィンドウで、[チームの**アップグレード**] の下の [ **Skype for business ユーザーの**切り替え] を **[オン**] に変更します。</span><span class="sxs-lookup"><span data-stu-id="ad60e-139">In the **Edit settings** pane on the right, under **Teams upgrade**, change **Notify the Skype for Business user** switch to **On**.</span></span> <span data-ttu-id="ad60e-140">注: 共存モードの値が "組織全体の設定を使用する" である場合、このスイッチは表示されません。そのため、最初に、これらのユーザーの共存モードを明示的に設定して、組織の既定値にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad60e-140">Note: If the value of coexistence mode is "Use Org-wide settings", you won't see this switch, so you'll need to first explicitly set the Coexistence mode for these users to whatever the default value is for the org.</span></span>

<span data-ttu-id="ad60e-141">または、PowerShell を使用すると、ユーザーのグループに対して簡単に通知を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="ad60e-141">Alternatively, you may find it easier to enable notifications for groups of users at once using PowerShell.</span></span> 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a><span data-ttu-id="ad60e-142">手順 3: ユーザーの共存モードをチームのみに設定する</span><span class="sxs-lookup"><span data-stu-id="ad60e-142">Step 3: Set the coexistence mode for users to Teams Only</span></span>

<span data-ttu-id="ad60e-143">現在のウェーブのユーザーをアップグレードして Teams のみをアプリケーションとして使用できるようにするには、ユーザーの [共存] モードを [チームのみ] に設定します。</span><span class="sxs-lookup"><span data-stu-id="ad60e-143">When you are ready to upgrade the users in the current wave to use Teams as their only application, set the Coexistence mode for the users to Teams Only.</span></span>

<span data-ttu-id="ad60e-144">Microsoft Teams 管理センターを使用している場合は、一度に最大20人のユーザーに対して TeamsUpgradePolicy を構成できます。</span><span class="sxs-lookup"><span data-stu-id="ad60e-144">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="ad60e-145">Microsoft Teams 管理センターで、[**ユーザー**] を選択し、最大20人のユーザーのチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="ad60e-145">In the Microsoft Teams admin center, select **Users**, and then select the checkbox for up to 20 users.</span></span>
2. <span data-ttu-id="ad60e-146">Listview の左上隅にある [**設定の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ad60e-146">Select **Edit settings** in the upper left corner of the listview.</span></span>
3. <span data-ttu-id="ad60e-147">右側の [**編集の設定**] ウィンドウの [**チームのアップグレード**] セクションで、[共存モード] をドロップダウンリストの [**チームのみ**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="ad60e-147">In the **Edit settings** pane on the right, under **Teams upgrade** section, set the coexistence mode to **Teams Only** in the drop-down list.</span></span>

<span data-ttu-id="ad60e-148">または、PowerShell を使用すると、ユーザーのグループを簡単にアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="ad60e-148">Alternatively, you may find it easier to upgrade groups of users at once using PowerShell.</span></span> 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a><span data-ttu-id="ad60e-149">手順 4: 連続したユーザーのために手順1-3 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="ad60e-149">Step 4: Repeat steps 1-3 for successive waves of users</span></span>

<span data-ttu-id="ad60e-150">チーム専用モードへのアップグレードを検証し、展開する準備ができたら、上記の手順を繰り返して、他のユーザーにのみ TeamsOnly を適用します。</span><span class="sxs-lookup"><span data-stu-id="ad60e-150">As you validate your upgrade to Teams Only mode and are ready to expand, repeat the previous steps to apply TeamsOnly to  more users.</span></span>  


## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="ad60e-151">電話システムと Teams のアップグレード</span><span class="sxs-lookup"><span data-stu-id="ad60e-151">Phone System and Teams upgrade</span></span>

<span data-ttu-id="ad60e-152">Skype for Business Online の展開に通話プランを含む電話システムが含まれていて、Microsoft が公衆交換電話網 (PSTN) プロバイダーである場合、ユーザーを Teams にアップグレードすると、着信する PSTN 通話は Teams に自動的に移行されます。</span><span class="sxs-lookup"><span data-stu-id="ad60e-152">If your Skype for Business Online deployment includes Phone System with Calling Plans and Microsoft is your public switched telephone network (PSTN) provider, upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="ad60e-153">Skype for Business Online の展開にクラウドコネクタエディションの電話システムが含まれている場合は、「[電話システムのダイレクトルーティングに関するその他の考慮事項](2-envision-make-my-service-decisions-direct-routing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad60e-153">If your Skype for Business Online deployment includes Phone System with Cloud Connector Edition, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
