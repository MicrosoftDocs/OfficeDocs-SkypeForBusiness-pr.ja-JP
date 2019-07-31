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
ms.openlocfilehash: 9994bb8efa862cc66cb1e081d0ca8136b4fb1871
ms.sourcegitcommit: 195a4e1bbab46034408a22d636874c10f797945a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "35934503"
---
<span data-ttu-id="d5551-103">![展開と実装を強調したアップグレードの図](media/upgrade-banner-deployment.png "展開と実装のステージに重点を置いたアップグレードの段階")</span><span class="sxs-lookup"><span data-stu-id="d5551-103">![Upgrade journey diagram, emphasizing Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="d5551-104">この記事は、お客様のアップグレード手順における展開と実装の段階の一部を取り上げています。</span><span class="sxs-lookup"><span data-stu-id="d5551-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="d5551-105">先に進む前に、次のアクティビティを完了していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d5551-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="d5551-106">プロジェクトの関係者をリスト化した</span><span class="sxs-lookup"><span data-stu-id="d5551-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="d5551-107">プロジェクトの対象範囲を定義した</span><span class="sxs-lookup"><span data-stu-id="d5551-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="d5551-108">Skype for Business と Teams の共存と相互運用を理解した</span><span class="sxs-lookup"><span data-stu-id="d5551-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="d5551-109">アップグレードの手順を選択した</span><span class="sxs-lookup"><span data-stu-id="d5551-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="d5551-110">環境を準備した</span><span class="sxs-lookup"><span data-stu-id="d5551-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="d5551-111">組織を準備した</span><span class="sxs-lookup"><span data-stu-id="d5551-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="d5551-112">パイロットを実施した</span><span class="sxs-lookup"><span data-stu-id="d5551-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-skype-for-business-online-to-teams"></a><span data-ttu-id="d5551-113">Skype for Business Online から Teams にアップグレードする</span><span class="sxs-lookup"><span data-stu-id="d5551-113">Upgrade from Skype for Business Online to Teams</span></span>

<span data-ttu-id="d5551-114">Skype for business Online を完全に展開していて、ユーザーを Skype for Business から Teams にアップグレードする場合は、この記事の指示に従ってください。</span><span class="sxs-lookup"><span data-stu-id="d5551-114">Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams.</span></span> <span data-ttu-id="d5551-115">組織で選択されているアップグレードの過程に基づいて、ユーザーを選択的またはすべてのユーザーにアップグレードするには、適切な共存とアップグレードモードをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d5551-115">You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d5551-116">Skype for Business Online は、2021年7月31日に廃止されます。その後、アクセスまたはサポートされなくなります。</span><span class="sxs-lookup"><span data-stu-id="d5551-116">Skype for Business Online will be retired on July 31, 2021, after which it will no longer be accessible or supported.</span></span> <span data-ttu-id="d5551-117">給付金を最大限に活用し、組織がアップグレードを実装するための適切な時間を確保するために、Microsoft Teams の現在の旅を開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d5551-117">To maximize benefit realization and ensure your organization has proper time to implement your upgrade, we encourage you to begin your journey to Microsoft Teams today.</span></span> <span data-ttu-id="d5551-118">アップグレードが正常に完了した場合は、技術的かつユーザーの準備ができていることに注意してください。このガイドは、Microsoft Teams への旅に進むときに必ずご利用ください。</span><span class="sxs-lookup"><span data-stu-id="d5551-118">Remember that a successful upgrade aligns technical and user readiness, so be sure to leverage the guidance herein as you navigate your journey to Microsoft Teams.</span></span>

## <a name="assign-the-coexistence-and-upgrade-mode"></a><span data-ttu-id="d5551-119">共存とアップグレードモードを割り当てる</span><span class="sxs-lookup"><span data-stu-id="d5551-119">Assign the coexistence and upgrade mode</span></span>

<span data-ttu-id="d5551-120">Microsoft Teams 管理センターまたは Skype for Business リモート Windows Powershell セッションを使用して実行できる TeamsUpgradePolicy の UpgradeToTeams インスタンスを割り当てることによって、ユーザーを TeamsOnly モードにアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="d5551-120">You can upgrade your users to TeamsOnly mode by assigning the UpgradeToTeams instance of TeamsUpgradePolicy, which can be performed by using the Microsoft Teams admin center or a Skype for Business remote Windows Powershell session.</span></span> <span data-ttu-id="d5551-121">これは、1つの手順でテナント全体をアップグレードする場合に、ユーザーごと、またはテナント全体で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d5551-121">You can do this either on a per user basis, or on a tenant-wide basis if you want to upgrade the entire tenant in one step.</span></span> 

<span data-ttu-id="d5551-122">詳細については、「[共存およびアップグレードを設定する](https://aka.ms/SkypeToTeams-SetCoexistence)」および「[TeamsUpgradePolicy: 移行と共存の管理](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5551-122">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

## <a name="upgrade-all-users-to-teams-at-one-time"></a><span data-ttu-id="d5551-123">一度にすべてのユーザーを Teams にアップグレードする</span><span class="sxs-lookup"><span data-stu-id="d5551-123">Upgrade all users to Teams at one time</span></span>

<span data-ttu-id="d5551-124">すべてのユーザーをチームに一度にアップグレードするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d5551-124">Follow these steps to upgrade all of your users to Teams at one time.</span></span>

### <a name="step-1-notify-the-users-of-the-change-optional"></a><span data-ttu-id="d5551-125">手順 1: ユーザーに変更を通知する (省略可能)</span><span class="sxs-lookup"><span data-stu-id="d5551-125">Step 1: Notify the users of the change (optional)</span></span>

1. <span data-ttu-id="d5551-126">Microsoft Teams 管理センターで、[**組織全体の設定** > ]**チームのアップグレード**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d5551-126">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams upgrade**.</span></span>
2. <span data-ttu-id="d5551-127">[**共存モード**] で、[**チームへのアップグレードが可能であることを Skype for Business ユーザーに通知**する] を **[オン**] に変更します。</span><span class="sxs-lookup"><span data-stu-id="d5551-127">Under **Coexistence mode**, change the **Notify Skype for Business users that an upgrade to Teams is available** switch to **On**.</span></span>

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a><span data-ttu-id="d5551-128">手順 2: 組織の場合のみ、共存モードを teams に設定します。</span><span class="sxs-lookup"><span data-stu-id="d5551-128">Step 2: Set the coexistence mode to TeamsOnly for the organization</span></span>

1. <span data-ttu-id="d5551-129">Microsoft Teams 管理センターで、[**組織全体の設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d5551-129">In the Microsoft Teams admin center, select **Org-wide settings**.</span></span>
2. <span data-ttu-id="d5551-130">[**共存モード**] ドロップダウンリストから [**チームのみ**] モードを選択します。</span><span class="sxs-lookup"><span data-stu-id="d5551-130">Select **Teams Only** mode from the **Coexistence mode** drop-down list.</span></span>

## <a name="upgrade-users-in-stages"></a><span data-ttu-id="d5551-131">ユーザーを段階的にアップグレードする</span><span class="sxs-lookup"><span data-stu-id="d5551-131">Upgrade users in stages</span></span>

<span data-ttu-id="d5551-132">ユーザーをチームに段階的にアップグレードする場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d5551-132">Follow these steps if you want to gradually upgrade your users to TeamsOnly.</span></span>

### <a name="step-1-identify-groups-of-users-for-upgrade"></a><span data-ttu-id="d5551-133">手順 1: アップグレードするユーザーグループを特定する</span><span class="sxs-lookup"><span data-stu-id="d5551-133">Step 1: Identify groups of users for upgrade</span></span>

<span data-ttu-id="d5551-134">組織では、ユーザーの成功波で組織のアップグレードが選択されることがあります。</span><span class="sxs-lookup"><span data-stu-id="d5551-134">Often organizations may choose to upgrade their organizations in success waves of users.</span></span>  <span data-ttu-id="d5551-135">これらのユーザーを最初に特定して、Microsoft Teams 管理センターで簡単に検索できるようにします。</span><span class="sxs-lookup"><span data-stu-id="d5551-135">You'll want to identify these users first so you can easily search for them in the Microsoft Teams admin center.</span></span> <span data-ttu-id="d5551-136">または、PowerShell を使用して、より効率的にこの操作を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="d5551-136">Alternatively, you may want to use PowerShell to more efficiently do this.</span></span> <span data-ttu-id="d5551-137">特定のアップグレードウェーブの一連のユーザーを特定したら、残りの手順を続行します。</span><span class="sxs-lookup"><span data-stu-id="d5551-137">Once you have identified the set of users for a given upgrade wave, continue with the remaining steps.</span></span>

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a><span data-ttu-id="d5551-138">手順 2: 現在のアップグレードウェーブでユーザーに通知を設定する (省略可能)</span><span class="sxs-lookup"><span data-stu-id="d5551-138">Step 2: Set notification for the users in the current upgrade wave (optional)</span></span>

<span data-ttu-id="d5551-139">Microsoft Teams 管理センターを使用している場合は、一度に最大20人のユーザーに対して TeamsUpgradePolicy を構成できます。</span><span class="sxs-lookup"><span data-stu-id="d5551-139">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="d5551-140">Microsoft Teams 管理センターで、[**ユーザー**] を選択し、アップグレードする必要がある最大20人のユーザーのチェックボックスをオンまたは複数選択します。</span><span class="sxs-lookup"><span data-stu-id="d5551-140">In the Microsoft Teams admin center, select **Users**, and find and multi-select the checkbox for up to 20 users who should be upgraded.</span></span> 
2. <span data-ttu-id="d5551-141">Listview の左上隅にある [**設定の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d5551-141">Select **Edit settings** in the upper left corner of the listview.</span></span> 
3. <span data-ttu-id="d5551-142">右側の [**設定の編集**] ウィンドウで、[チームの**アップグレード**] の下の [ **Skype for business ユーザーの**切り替え] を **[オン**] に変更します。</span><span class="sxs-lookup"><span data-stu-id="d5551-142">In the **Edit settings** pane on the right, under **Teams upgrade**, change **Notify the Skype for Business user** switch to **On**.</span></span> <span data-ttu-id="d5551-143">注: 共存モードの値が "組織全体の設定を使用する" である場合、このスイッチは表示されません。そのため、最初に、これらのユーザーの共存モードを明示的に設定して、組織の既定値にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5551-143">Note: If the value of coexistence mode is "Use Org-wide settings", you won't see this switch, so you'll need to first explicitly set the Coexistence mode for these users to whatever the default value is for the org.</span></span>

<span data-ttu-id="d5551-144">または、PowerShell を使用すると、ユーザーのグループに対して簡単に通知を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d5551-144">Alternatively, you may find it easier to enable notifications for groups of users at once using PowerShell.</span></span> 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a><span data-ttu-id="d5551-145">手順 3: ユーザーの共存モードをチームのみに設定する</span><span class="sxs-lookup"><span data-stu-id="d5551-145">Step 3: Set the coexistence mode for users to Teams Only</span></span>

<span data-ttu-id="d5551-146">現在のウェーブのユーザーをアップグレードして Teams のみをアプリケーションとして使用できるようにするには、ユーザーの [共存] モードを [チームのみ] に設定します。</span><span class="sxs-lookup"><span data-stu-id="d5551-146">When you are ready to upgrade the users in the current wave to use Teams as their only application, set the Coexistence mode for the users to Teams Only.</span></span>

<span data-ttu-id="d5551-147">Microsoft Teams 管理センターを使用している場合は、一度に最大20人のユーザーに対して TeamsUpgradePolicy を構成できます。</span><span class="sxs-lookup"><span data-stu-id="d5551-147">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="d5551-148">Microsoft Teams 管理センターで、[**ユーザー**] を選択し、最大20人のユーザーのチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d5551-148">In the Microsoft Teams admin center, select **Users**, and then select the checkbox for up to 20 users.</span></span>
2. <span data-ttu-id="d5551-149">Listview の左上隅にある [**設定の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d5551-149">Select **Edit settings** in the upper left corner of the listview.</span></span>
3. <span data-ttu-id="d5551-150">右側の [**編集の設定**] ウィンドウの [**チームのアップグレード**] セクションで、[共存モード] をドロップダウンリストの [**チームのみ**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="d5551-150">In the **Edit settings** pane on the right, under **Teams upgrade** section, set the coexistence mode to **Teams Only** in the drop-down list.</span></span>

<span data-ttu-id="d5551-151">または、PowerShell を使用すると、ユーザーのグループを簡単にアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="d5551-151">Alternatively, you may find it easier to upgrade groups of users at once using PowerShell.</span></span> 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a><span data-ttu-id="d5551-152">手順 4: 連続したユーザーのために手順1-3 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d5551-152">Step 4: Repeat steps 1-3 for successive waves of users</span></span>

<span data-ttu-id="d5551-153">チーム専用モードへのアップグレードを検証し、展開する準備ができたら、上記の手順を繰り返して、他のユーザーにのみ TeamsOnly を適用します。</span><span class="sxs-lookup"><span data-stu-id="d5551-153">As you validate your upgrade to Teams Only mode and are ready to expand, repeat the previous steps to apply TeamsOnly to  more users.</span></span>  


## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="d5551-154">電話システムと Teams のアップグレード</span><span class="sxs-lookup"><span data-stu-id="d5551-154">Phone System and Teams upgrade</span></span>

<span data-ttu-id="d5551-155">Skype for Business Online の展開に通話プランを含む電話システムが含まれていて、Microsoft が公衆交換電話網 (PSTN) プロバイダーである場合、ユーザーを Teams にアップグレードすると、着信する PSTN 通話は Teams に自動的に移行されます。</span><span class="sxs-lookup"><span data-stu-id="d5551-155">If your Skype for Business Online deployment includes Phone System with Calling Plans and Microsoft is your public switched telephone network (PSTN) provider, upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="d5551-156">Skype for Business Online の展開にクラウドコネクタエディションの電話システムが含まれている場合は、「[電話システムのダイレクトルーティングに関するその他の考慮事項](2-envision-make-my-service-decisions-direct-routing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5551-156">If your Skype for Business Online deployment includes Phone System with Cloud Connector Edition, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
