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
ms.openlocfilehash: bc1334e019abadb030199518df15b0dde74dde52
ms.sourcegitcommit: c997490cf7239d07e2fd52a4b03bec464b3d192b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2019
ms.locfileid: "33835336"
---
<span data-ttu-id="8a34c-103">![展開と実装の段階に重点を置いた、アップグレード手順の各段階](media/upgrade-banner-deployment.png "展開と実装の段階に重点を置いた、アップグレード手順の各段階")</span><span class="sxs-lookup"><span data-stu-id="8a34c-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="8a34c-104">この記事は、お客様のアップグレード手順における展開と実装の段階の一部を取り上げています。</span><span class="sxs-lookup"><span data-stu-id="8a34c-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="8a34c-105">先に進む前に、次のアクティビティを完了していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8a34c-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="8a34c-106">プロジェクトの関係者をリスト化した</span><span class="sxs-lookup"><span data-stu-id="8a34c-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="8a34c-107">プロジェクトの対象範囲を定義した</span><span class="sxs-lookup"><span data-stu-id="8a34c-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="8a34c-108">Skype for Business と Teams の共存と相互運用を理解した</span><span class="sxs-lookup"><span data-stu-id="8a34c-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="8a34c-109">アップグレードの手順を選択した</span><span class="sxs-lookup"><span data-stu-id="8a34c-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="8a34c-110">環境を準備した</span><span class="sxs-lookup"><span data-stu-id="8a34c-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="8a34c-111">組織を準備した</span><span class="sxs-lookup"><span data-stu-id="8a34c-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="8a34c-112">パイロットを実施した</span><span class="sxs-lookup"><span data-stu-id="8a34c-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-skype-for-business-online-to-teams"></a><span data-ttu-id="8a34c-113">Skype for Business Online から Teams にアップグレードする</span><span class="sxs-lookup"><span data-stu-id="8a34c-113">Upgrade from Skype for Business Online to Teams</span></span>

<span data-ttu-id="8a34c-114">完全 Skype をオンライン ビジネスを展開しているし、ビジネスの Skype からのチームにユーザーをアップグレードする場合のこの資料の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="8a34c-114">Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams.</span></span> <span data-ttu-id="8a34c-115">ユーザーを選択的にアップグレードすることができますまたはアップグレードをに基づいて、オールインワンの旅を適切な共存およびアップグレード モードをユーザーに割り当てることにより、組織が選択されます。</span><span class="sxs-lookup"><span data-stu-id="8a34c-115">You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a><span data-ttu-id="8a34c-116">共存およびアップグレード モードを割り当てる</span><span class="sxs-lookup"><span data-stu-id="8a34c-116">Assign the coexistence and upgrade mode</span></span>

<span data-ttu-id="8a34c-117">ビジネス リモートの Windows Powershell セッションでマイクロソフトのチームの管理センターや、Skype を使用して実行することができる TeamsUpgradePolicy の UpgradeToTeams インスタンスを割り当てることによって、TeamsOnly モードにユーザーをアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="8a34c-117">You can upgrade your users to TeamsOnly mode by assigning the UpgradeToTeams instance of TeamsUpgradePolicy, which can be performed by using the Microsoft Teams admin center or a Skype for Business remote Windows Powershell session.</span></span> <span data-ttu-id="8a34c-118">できますこれを行うユーザーごと、またはテナント単位で 1 つのステップで全体のテナントにアップグレードする場合。</span><span class="sxs-lookup"><span data-stu-id="8a34c-118">You can do this either on a per user basis, or on a tenant-wide basis if you want to ugprade the entire tenant in one step.</span></span> 

<span data-ttu-id="8a34c-119">詳細については、「[共存およびアップグレードを設定する](https://aka.ms/SkypeToTeams-SetCoexistence)」および「[TeamsUpgradePolicy: 移行と共存の管理](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a34c-119">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

## <a name="upgrade-all-users-to-teams-at-one-time"></a><span data-ttu-id="8a34c-120">チームにすべてのユーザーを同時にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="8a34c-120">Upgrade all users to Teams at one time</span></span>

<span data-ttu-id="8a34c-121">この手順では、一度に 1 つのチームにすべてのユーザーをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="8a34c-121">Follow these steps to upgrade all of your users to Teams at one time.</span></span>

### <a name="step-1-notify-the-users-of-the-change-optional"></a><span data-ttu-id="8a34c-122">ステップ 1: (省略可能) の変更をユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="8a34c-122">Step 1: Notify the users of the change (optional)</span></span>

1. <span data-ttu-id="8a34c-123">マイクロソフトのチーム管理センターで、**組織全体の設定**を選択して > **のチームをアップグレード**します。</span><span class="sxs-lookup"><span data-stu-id="8a34c-123">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams upgrade**.</span></span>
2. <span data-ttu-id="8a34c-124">**共存モード**では、[**上**に**チームへのアップグレードが利用可能なビジネス ・ ユーザーの通知の Skype**のスイッチを変更します。</span><span class="sxs-lookup"><span data-stu-id="8a34c-124">Under **Coexistence mode**, change the **Notify Skype for Business users that an upgrade to Teams is available** switch to **On**.</span></span>

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a><span data-ttu-id="8a34c-125">ステップ 2: TeamsOnly に組織で共存モードを設定します。</span><span class="sxs-lookup"><span data-stu-id="8a34c-125">Step 2: Set the coexistence mode to TeamsOnly for the organization</span></span>

1. <span data-ttu-id="8a34c-126">マイクロソフトのチーム管理センターでは、**組織全体の設定**を選択します。</span><span class="sxs-lookup"><span data-stu-id="8a34c-126">In the Microsoft Teams admin center, select **Org-wide settings**.</span></span>
2. <span data-ttu-id="8a34c-127">**共存モード**」ドロップ ダウン リストから**チームのみ**のモードを選択します。</span><span class="sxs-lookup"><span data-stu-id="8a34c-127">Select **Teams Only** mode from the **Coexistence mode** drop-down list.</span></span>

## <a name="upgrade-users-in-stages"></a><span data-ttu-id="8a34c-128">ユーザーを段階的にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="8a34c-128">Upgrade users in stages</span></span>

<span data-ttu-id="8a34c-129">TeamsOnly にユーザーを段階的にアップグレードする場合は、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8a34c-129">Follow these steps if you want to gradually upgrade your users to TeamsOnly.</span></span>

### <a name="step-1-identify-groups-of-users-for-upgrade"></a><span data-ttu-id="8a34c-130">ステップ 1: アップグレードのためのユーザーのグループを識別します。</span><span class="sxs-lookup"><span data-stu-id="8a34c-130">Step 1: Identify groups of users for upgrade</span></span>

<span data-ttu-id="8a34c-131">組織では多くの場合は、ユーザーの成功の波に自分の組織をアップグレードすることができます。</span><span class="sxs-lookup"><span data-stu-id="8a34c-131">Often organizations may choose to upgrade their organizations in success waves of users.</span></span>  <span data-ttu-id="8a34c-132">検索できるように簡単にそれらのマイクロソフトのチームの管理センターで最初にこれらのユーザーを識別します。</span><span class="sxs-lookup"><span data-stu-id="8a34c-132">You'll want to identify these users first so you can easily search for them in the Microsoft Teams admin center.</span></span> <span data-ttu-id="8a34c-133">またはより効率的にこれを行うに PowerShell を使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="8a34c-133">Alternatively, you may want to use PowerShell to more efficiently do this.</span></span> <span data-ttu-id="8a34c-134">アップグレード ウェーブの特定のユーザーのセットを識別した後は、残りの手順を続行します。</span><span class="sxs-lookup"><span data-stu-id="8a34c-134">Once you have identified the set of users for a given upgrade wave, continue with the remaining steps.</span></span>

### <a name="step-2-set-notification-for-the-users-in-the-current-ugprade-wave-optional"></a><span data-ttu-id="8a34c-135">ステップ 2: 通知を設定、ユーザーの現在のアップグレードのウェーブで (省略可能)</span><span class="sxs-lookup"><span data-stu-id="8a34c-135">Step 2: Set notification for the users in the current ugprade wave (optional)</span></span>

<span data-ttu-id="8a34c-136">マイクロソフトのチームの管理センターを使用する場合、一度に最大 20 個のユーザーの TeamsUpgradePolicy を構成できます。</span><span class="sxs-lookup"><span data-stu-id="8a34c-136">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="8a34c-137">マイクロソフトのチーム管理センターで、**ユーザー**、および検索と複数選択チェック ボックスをオンに最大 20 個のユーザーがアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a34c-137">In the Microsoft Teams admin center, select **Users**, and find and multi-select the checkbox for up to 20 users who should be upgraded.</span></span> 
2. <span data-ttu-id="8a34c-138">リスト ビューの左上隅で**設定を編集**を選択します。</span><span class="sxs-lookup"><span data-stu-id="8a34c-138">Select **Edit settings** in the upper left corner of the listview.</span></span> 
3. <span data-ttu-id="8a34c-139">**チームのアップグレード**をするには、下、右上の**設定を編集**] ウィンドウでは、**上**に**通知 Skype ビジネス ユーザーの**スイッチを変更します。</span><span class="sxs-lookup"><span data-stu-id="8a34c-139">In the **Edit settings** pane on the right, under **Teams upgrade**, change **Notify the Skype for Business user** switch to **On**.</span></span> <span data-ttu-id="8a34c-140">注: 共存モードの値が使用して組織全体にわたる設定」の場合は、表示されませんこのスイッチでは、最初にこれらのユーザーに、組織の既定値は、どのような共存モードを明示的に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a34c-140">Note: If the value of coexistence mode is "Use Org-wide settings", you won't see this switch, so you'll need to first explicitly set the Coexistence mode for these users to whatever the default value is for the org.</span></span>

<span data-ttu-id="8a34c-141">または、する場合がありますほうが簡単な PowerShell を使用して、一度にユーザーのグループに通知を有効にします。</span><span class="sxs-lookup"><span data-stu-id="8a34c-141">Alternatively, you may find it easier to enable notifications for groups of users at once using PowerShell.</span></span> 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a><span data-ttu-id="8a34c-142">ステップ 3: ユーザーがチームのみの共存モードを設定します。</span><span class="sxs-lookup"><span data-stu-id="8a34c-142">Step 3: Set the coexistence mode for users to Teams Only</span></span>

<span data-ttu-id="8a34c-143">現在の波形で、唯一のアプリケーションとして、チームを使用するユーザーをアップグレードする準備ができたら、チームだけにユーザーの共存モードを設定します。</span><span class="sxs-lookup"><span data-stu-id="8a34c-143">When you are ready to upgrade the users in the current wave to use Teams as their only application, set the Coexistence mode for the users to Teams Only.</span></span>

<span data-ttu-id="8a34c-144">マイクロソフトのチームの管理センターを使用する場合、一度に最大 20 個のユーザーの TeamsUpgradePolicy を構成できます。</span><span class="sxs-lookup"><span data-stu-id="8a34c-144">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="8a34c-145">マイクロソフトのチーム管理センターで、**ユーザー**を選択し、最大 20 個のユーザーのチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="8a34c-145">In the Microsoft Teams admin center, select **Users**, and then select the checkbox for up to 20 users.</span></span>
2. <span data-ttu-id="8a34c-146">リスト ビューの左上隅で**設定を編集**を選択します。</span><span class="sxs-lookup"><span data-stu-id="8a34c-146">Select **Edit settings** in the upper left corner of the listview.</span></span>
3. <span data-ttu-id="8a34c-147">右側の**チームをアップグレード**] セクションで、[**設定の編集**ウィンドウでドロップ ダウン リストで**チームのみ**に共存モードを設定します。</span><span class="sxs-lookup"><span data-stu-id="8a34c-147">In the **Edit settings** pane on the right, under **Teams upgrade** section, set the coexistence mode to **Teams Only** in the drop-down list.</span></span>

<span data-ttu-id="8a34c-148">または、する場合がありますほうが簡単な PowerShell を使用して、一度にユーザーのグループをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="8a34c-148">Alternatively, you may find it easier to upgrade groups of users at once using PowerShell.</span></span> 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a><span data-ttu-id="8a34c-149">手順 4: ユーザーの連続した波の手順 1 ~ 3 を繰り返します</span><span class="sxs-lookup"><span data-stu-id="8a34c-149">Step 4: Repeat steps 1-3 for successive waves of users</span></span>

<span data-ttu-id="8a34c-150">チームのみのモードへのアップグレードの検証を展開する準備ができているより多くのユーザーに TeamsOnly を適用する前の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="8a34c-150">As you validate your upgrade to Teams Only mode and are ready to expand, repeat the previous steps to apply TeamsOnly to  more users.</span></span>  


## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="8a34c-151">電話システムと Teams のアップグレード</span><span class="sxs-lookup"><span data-stu-id="8a34c-151">Phone System and Teams upgrade</span></span>

<span data-ttu-id="8a34c-152">場合は、オンライン ビジネスの展開、Skype には、計画を呼び出すと、電話システムが含まれています、、公衆交換電話網 (PSTN) プロバイダーが、チームにユーザーをアップグレードするは自動的に移行チームを呼び出す PSTN を受信します。</span><span class="sxs-lookup"><span data-stu-id="8a34c-152">If your Skype for Business Online deployment includes Phone System with Calling Plans and Microsoft is your public switched telephone network (PSTN) provider, upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="8a34c-153">オンライン ビジネス展開するため、Skype には、クラウドのコネクタのエディションでの電話システムが含まれている場合は、[電話システムの直接のルーティングのための追加の考慮事項](2-envision-make-my-service-decisions-direct-routing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a34c-153">If your Skype for Business Online deployment includes Phone System with Cloud Connector Edition, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
