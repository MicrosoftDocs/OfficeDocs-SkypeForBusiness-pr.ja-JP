---
title: 設置型のビジネスには、マイクロソフトのチームの Skype のアップグレードします。展開 |Lync
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: ビジネス上の設置型展開チームに、Skype のアップグレードに関する考慮事項
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 78c69b8fb54a430269e63836ef430d63270841f8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32211967"
---
<span data-ttu-id="94882-103">![展開と実装の段階に重点を置いた、アップグレード手順の各段階](media/upgrade-banner-deployment.png "展開と実装の段階に重点を置いた、アップグレード手順の各段階")</span><span class="sxs-lookup"><span data-stu-id="94882-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="94882-104">この記事は、お客様のアップグレード手順における展開と実装の段階の一部を取り上げています。</span><span class="sxs-lookup"><span data-stu-id="94882-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="94882-105">先に進む前に、次のアクティビティを完了していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="94882-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="94882-106">プロジェクトの関係者をリスト化した</span><span class="sxs-lookup"><span data-stu-id="94882-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="94882-107">プロジェクトの対象範囲を定義した</span><span class="sxs-lookup"><span data-stu-id="94882-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="94882-108">Skype for Business と Teams の共存と相互運用を理解した</span><span class="sxs-lookup"><span data-stu-id="94882-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="94882-109">アップグレードの手順を選択した</span><span class="sxs-lookup"><span data-stu-id="94882-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="94882-110">環境を準備した</span><span class="sxs-lookup"><span data-stu-id="94882-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="94882-111">組織を準備した</span><span class="sxs-lookup"><span data-stu-id="94882-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="94882-112">パイロットを実施した</span><span class="sxs-lookup"><span data-stu-id="94882-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a><span data-ttu-id="94882-113">ビジネス設置型展開で、Skype からチームへのアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="94882-113">Upgrade from a Skype for Business on-premises deployment to Teams</span></span>

<span data-ttu-id="94882-114">オンプレミス環境の Skype for Business または Microsoft Lync を展開していて、組織が選択的 (複数の共存モードを使用) または全体的に Teams にアップグレードする場合は、この記事のガイダンスに従ってください。</span><span class="sxs-lookup"><span data-stu-id="94882-114">Follow the guidance in this article if you’ve deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="94882-115">最初の手順では、Office 365 テナントとのハイブリッド接続を設定して、ユーザーを Skype for Business Online に移動し、適切な共存およびアップグレード モードをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="94882-115">The first step is to set up hybrid connectivity with your Office 365 tenant, and then move your users to Skype for Business Online and assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="94882-116">手順 1: ハイブリッド接続の展開</span><span class="sxs-lookup"><span data-stu-id="94882-116">Step 1: Deploy hybrid connectivity</span></span>

<span data-ttu-id="94882-117">ユーザーを Teams にアップグレードする際の重要な前提条件は、ハイブリッド接続を展開することです。</span><span class="sxs-lookup"><span data-stu-id="94882-117">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span> <span data-ttu-id="94882-118">このために、既存の Skype for Business または Lync の展開環境に新しい外部接続を展開するか、単に Office 365 テナントとのハイブリッド リレーションシップを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94882-118">This might involve deploying new external connectivity for your existing Skype for Business or Lync deployment, or simply configuring a hybrid relationship with your Office 365 tenant.</span></span>

<span data-ttu-id="94882-119">詳細については、[サーバーのビジネスとオンライン ビジネスの Skype の Skype 間のハイブリッド接続の展開](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94882-119">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span></span>

## <a name="step-2-move-users-to-skype-for-business-online"></a><span data-ttu-id="94882-120">手順 2: Skype for Business Online にユーザーを移動する</span><span class="sxs-lookup"><span data-stu-id="94882-120">Step 2: Move users to Skype for Business Online</span></span>

<span data-ttu-id="94882-121">ハイブリッドの設定が完了したら、Skype for Business Online にユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="94882-121">After you’ve completed your hybrid setup, move users to Skype for Business Online.</span></span>

<span data-ttu-id="94882-122">詳細については、[ビジネス オンラインの Skype を施設内でのユーザーの移動](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94882-122">For more information, see [Move users from on premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)</span></span>

## <a name="step-3-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="94882-123">手順 3: 共存およびアップグレード モードを割り当てる</span><span class="sxs-lookup"><span data-stu-id="94882-123">Step 3: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="94882-124">Skype for Business Online にユーザーを移動したら、組織が選択したアップグレードの手順に応じて、ユーザーに適切な共存モードを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="94882-124">After you’ve moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="94882-125">詳細については、「[共存およびアップグレードを設定する](https://aka.ms/SkypeToTeams-SetCoexistence)」および「[TeamsUpgradePolicy: 移行と共存の管理](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94882-125">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

> [!NOTE]
> <span data-ttu-id="94882-126">Business Server 2019 および Skype for Business Server 2015 の将来の累積的な更新プログラムでは、手順 2 (Skype for Business Online にユーザーを移動する) と手順 3 (ユーザーを Teams にアップグレードする) を 1 つの手順で実行できます。</span><span class="sxs-lookup"><span data-stu-id="94882-126">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you’ll be able to perform Step 2 (moving users to Skype for Business Online) and Step 3 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="94882-127">詳細については、Skype for Business Server 2019 のリリース後に発表されます。</span><span class="sxs-lookup"><span data-stu-id="94882-127">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="94882-128">電話システムと Teams のアップグレード</span><span class="sxs-lookup"><span data-stu-id="94882-128">Phone System and Teams upgrade</span></span>

<span data-ttu-id="94882-129">エンタープライズ ボイスの計画を呼び出すと、電話システムにビジネスの設置を展開するため、Skype に移行しているし、Microsoft は、公衆交換電話網 (PSTN) プロバイダーになる場合、電話番号を完了したことを前提として、移植-チームにユーザーをアップグレードすると、チームへのインバウンドの PSTN 通話は自動的に移行します。</span><span class="sxs-lookup"><span data-stu-id="94882-129">If you’re transitioning your Skype for Business on-premises deployment from enterprise voice to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you’ve completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="94882-130">通話プランが利用できない場合は、エンタープライズ ボイスを Microsoft 電話システム ダイレクト ルーティングに移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94882-130">If Calling Plans isn’t available, you need to transition your enterprise voice deployment to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="94882-131">ユーザーを Teams にアップグレードする場合は、[電話システム ダイレクト ルーティングに関する考慮事項](2-envision-make-my-service-decisions-direct-routing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94882-131">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>