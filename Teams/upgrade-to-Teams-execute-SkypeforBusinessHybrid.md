---
title: ハイブリッドSkype for BusinessデプロイをアップグレードしてTeams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 組織をアップグレードして、ハイブリッド デプロイMicrosoft TeamsアップグレードするSkype for Business説明します。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 97725e7a9790f47f9789366567981f0167fdd806
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104023"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a><span data-ttu-id="b6846-103">ハイブリッド デプロイからSkype for BusinessへのアップグレードTeams</span><span class="sxs-lookup"><span data-stu-id="b6846-103">Upgrade from a Skype for Business hybrid deployment to Teams</span></span>

<span data-ttu-id="b6846-104">![「展開と実装」段階が強調表示された、アップグレード行程の各段階](media/upgrade-banner-deployment.png "「展開と実装」段階が強調表示された、アップグレード行程の各段階")</span><span class="sxs-lookup"><span data-stu-id="b6846-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="b6846-105">この記事は、お客様のアップグレード手順における展開と実装の段階の一部を取り上げています。</span><span class="sxs-lookup"><span data-stu-id="b6846-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="b6846-106">先に進む前に、次のアクティビティを完了していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b6846-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="b6846-107">プロジェクトの関係者をリスト化した</span><span class="sxs-lookup"><span data-stu-id="b6846-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="b6846-108">プロジェクトの対象範囲を定義した</span><span class="sxs-lookup"><span data-stu-id="b6846-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="b6846-109">Skype for Business と Teams の共存と相互運用を理解した</span><span class="sxs-lookup"><span data-stu-id="b6846-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="b6846-110">アップグレードの手順を選択した</span><span class="sxs-lookup"><span data-stu-id="b6846-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="b6846-111">環境を準備した</span><span class="sxs-lookup"><span data-stu-id="b6846-111">Prepared your environment</span></span>](./upgrade-prepare-environment.md)
- [<span data-ttu-id="b6846-112">組織を準備した</span><span class="sxs-lookup"><span data-stu-id="b6846-112">Prepared your organization</span></span>](./upgrade-prepare-organization.md)
- [<span data-ttu-id="b6846-113">パイロットを実施した</span><span class="sxs-lookup"><span data-stu-id="b6846-113">Conducted a pilot</span></span>](./pilot-essentials.md)

<span data-ttu-id="b6846-114">Skype for Business または Microsoft Lync をオンプレミスに展開し、Microsoft 365 または Office 365 組織とのハイブリッド展開で構成し、組織が複数の共存モードを使用するか、またはすべて使用して Teams に選択的にアップグレードする場合は、この記事のガイダンスに従います。</span><span class="sxs-lookup"><span data-stu-id="b6846-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and configured it in a hybrid deployment with your Microsoft 365 or Office 365 organization, and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="b6846-115">どちらのアップグレード体験でも、ユーザーを Skype for Business Online に移動し (オンラインにまだホームしていない場合)、適切な共存モードとアップグレード モードを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6846-115">For either upgrade journey, you need to move your users to Skype for Business Online (if they aren't already homed online) and then assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a><span data-ttu-id="b6846-116">手順 1: ユーザーをオンラインにSkype for Businessする</span><span class="sxs-lookup"><span data-stu-id="b6846-116">Step 1: Move users to Skype for Business Online</span></span>

<span data-ttu-id="b6846-117">この手順は、現在オンプレミスに在宅しているユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="b6846-117">This step applies to users who are currently homed on-premises.</span></span> <span data-ttu-id="b6846-118">これらのユーザーを Skype for Business Online に移動する方法の詳細については、「-premises から Skype for Business Online にユーザーを[移動する」を参照してください](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)。</span><span class="sxs-lookup"><span data-stu-id="b6846-118">For more information about moving these users to Skype for Business Online, see [Move users from on -premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="b6846-119">手順 2: 共存モードとアップグレード モードを割り当てる</span><span class="sxs-lookup"><span data-stu-id="b6846-119">Step 2: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="b6846-120">ユーザーを Skype for Business Online に移動したら、組織が選択したアップグレード体験に基づいて適切な共存モードを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="b6846-120">After you've moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="b6846-121">詳細については、「[共存およびアップグレードを設定する](./setting-your-coexistence-and-upgrade-settings.md)」および「[TeamsUpgradePolicy: 移行と共存の管理](upgrade-to-teams-on-prem-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6846-121">For more information, see [Setting your coexistence and upgrade settings](./setting-your-coexistence-and-upgrade-settings.md) and [TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b6846-122">Skype for Business Server 2019 と将来の累積的な更新プログラム Skype for Business Server 2015 では、手順 1 (ユーザーを Skype for Business Online に移動) と手順 2 (ユーザーを Teams にアップグレード) を 1 つの手順で実行できます。</span><span class="sxs-lookup"><span data-stu-id="b6846-122">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you'll be able to perform Step 1 (moving users to Skype for Business Online) and Step 2 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="b6846-123">詳細については、Skype for Business Server 2019 のリリース後に発表されます。</span><span class="sxs-lookup"><span data-stu-id="b6846-123">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="b6846-124">電話システムと Teams のアップグレード</span><span class="sxs-lookup"><span data-stu-id="b6846-124">Phone System and Teams upgrade</span></span>

<span data-ttu-id="b6846-125">通話プランを使用して Skype for Business ハイブリッド展開を 電話システム に移行する場合、Microsoft は公衆交換電話網 (PSTN) プロバイダーになります。また、電話番号の移行を完了したと仮定すると、ユーザーを Teams にアップグレードすると、受信 PSTN 通話が Teams に自動的に移行されます。</span><span class="sxs-lookup"><span data-stu-id="b6846-125">If you're transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you've completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="b6846-126">通話プランを利用できない場合、または既存の PSTN 接続プロバイダーを使用する場合は、エンタープライズ音声展開 (または既存のオンプレミスデプロイまたは Cloud Connector Edition を使用するハイブリッド音声展開) を Microsoft 電話 System Direct Routing に移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6846-126">If Calling Plans isn't available or you intend to use your existing PSTN connectivity provider, you need to transition your enterprise voice deployment—or hybrid voice deployment that uses your existing on-premises deployment or Cloud Connector Edition—to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="b6846-127">ユーザーを Teams にアップグレードする場合は、[電話システム ダイレクト ルーティングに関する考慮事項](./direct-routing-landing-page.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6846-127">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](./direct-routing-landing-page.md).</span></span>