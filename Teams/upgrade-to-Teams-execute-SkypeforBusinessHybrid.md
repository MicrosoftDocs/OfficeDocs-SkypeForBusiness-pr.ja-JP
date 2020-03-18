---
title: Skype for Business ハイブリッド展開を Microsoft Teams にアップグレードする |SIP-PSTN
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Skype for Business ハイブリッド展開から Teams にアップグレードする場合の考慮事項
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ca9ebc7a28e07eec9b24c0628ade4941c0fd2fa2
ms.sourcegitcommit: 5d64e30a1984a4b1d9ff36e2e1721cb4bbf9e450
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "42706697"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a><span data-ttu-id="29e5c-103">Skype for Business ハイブリッド展開から Teams にアップグレードする</span><span class="sxs-lookup"><span data-stu-id="29e5c-103">Upgrade from a Skype for Business hybrid deployment to Teams</span></span>

<span data-ttu-id="29e5c-104">![「展開と実装」段階が強調表示された、アップグレード行程の各段階](media/upgrade-banner-deployment.png "「展開と実装」段階が強調表示された、アップグレード行程の各段階")</span><span class="sxs-lookup"><span data-stu-id="29e5c-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="29e5c-105">この記事は、お客様のアップグレード手順における展開と実装の段階の一部を取り上げています。</span><span class="sxs-lookup"><span data-stu-id="29e5c-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="29e5c-106">続行する前に、次の作業が完了していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="29e5c-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="29e5c-107">プロジェクトの関係者をリスト化した</span><span class="sxs-lookup"><span data-stu-id="29e5c-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="29e5c-108">プロジェクトの対象範囲を定義した</span><span class="sxs-lookup"><span data-stu-id="29e5c-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="29e5c-109">Skype for Business と Teams の共存と相互運用を理解した</span><span class="sxs-lookup"><span data-stu-id="29e5c-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="29e5c-110">アップグレードの手順を選択した</span><span class="sxs-lookup"><span data-stu-id="29e5c-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="29e5c-111">環境を準備した</span><span class="sxs-lookup"><span data-stu-id="29e5c-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="29e5c-112">組織を準備した</span><span class="sxs-lookup"><span data-stu-id="29e5c-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="29e5c-113">パイロットを実施した</span><span class="sxs-lookup"><span data-stu-id="29e5c-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="29e5c-114">この記事のガイダンスに従って、Skype for Business または Microsoft Lync をオンプレミスで展開し、Office 365 テナントでハイブリッド展開で構成している場合は、複数のユーザーを使用して、組織で選択的にチームにアップグレードすることを希望しています。共存モード (またはすべて)</span><span class="sxs-lookup"><span data-stu-id="29e5c-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and configured it in a hybrid deployment with your Office 365 tenant, and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="29e5c-115">アップグレードの過程では、ユーザーを Skype for Business Online に移行する必要があり (まだオンラインになっていない場合)、適切な共存とアップグレードモードを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="29e5c-115">For either upgrade journey, you need to move your users to Skype for Business Online (if they aren't already homed online) and then assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a><span data-ttu-id="29e5c-116">手順 1: ユーザーを Skype for Business Online に移動する</span><span class="sxs-lookup"><span data-stu-id="29e5c-116">Step 1: Move users to Skype for Business Online</span></span>

<span data-ttu-id="29e5c-117">この手順は、現在オンプレミスのホームユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="29e5c-117">This step applies to users who are currently homed on-premises.</span></span> <span data-ttu-id="29e5c-118">これらのユーザーを Skype for Business Online に移行する方法の詳細については、「[オンプレミスから skype For Business online にユーザーを移行する](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29e5c-118">For more information about moving these users to Skype for Business Online, see [Move users from on -premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="29e5c-119">手順 2: 共存とアップグレードモードを割り当てる</span><span class="sxs-lookup"><span data-stu-id="29e5c-119">Step 2: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="29e5c-120">ユーザーを Skype for Business Online に移行した後は、組織が選択したアップグレードの過程に基づいて適切な共存モードを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="29e5c-120">After you've moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="29e5c-121">詳細については、「[共存およびアップグレードを設定する](https://aka.ms/SkypeToTeams-SetCoexistence)」および「[TeamsUpgradePolicy: 移行と共存の管理](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29e5c-121">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

> [!NOTE]
> <span data-ttu-id="29e5c-122">Skype for Business Server 2019 および今後の Skype for Business Server 2015 の累積的な更新プログラムでは、手順 1 (ユーザーを Skype for Business Online に移行する) と手順 2 (ユーザーを Teams にアップグレードする) を1つの手順で実行できます。</span><span class="sxs-lookup"><span data-stu-id="29e5c-122">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you'll be able to perform Step 1 (moving users to Skype for Business Online) and Step 2 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="29e5c-123">詳細については、Skype for Business Server 2019 のリリース後に発表されます。</span><span class="sxs-lookup"><span data-stu-id="29e5c-123">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="29e5c-124">電話システムと Teams のアップグレード</span><span class="sxs-lookup"><span data-stu-id="29e5c-124">Phone System and Teams upgrade</span></span>

<span data-ttu-id="29e5c-125">Skype for Business ハイブリッド展開を電話システムに移行している場合に、Microsoft が PSTN (公衆交換電話網) プロバイダーとなり、電話番号の移行が完了したことを前提としています。チームは着信 PSTN 通話を Teams に自動的に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="29e5c-125">If you're transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you've completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="29e5c-126">通話プランを利用できない場合、または既存の PSTN 接続プロバイダーを使用する場合は、エンタープライズ voip 展開 (または既存のオンプレミス展開またはクラウドコネクタエディションを使用するハイブリッド音声の展開) に移行する必要があります。Microsoft Phone システムのダイレクトルーティング。</span><span class="sxs-lookup"><span data-stu-id="29e5c-126">If Calling Plans isn't available or you intend to use your existing PSTN connectivity provider, you need to transition your enterprise voice deployment—or hybrid voice deployment that uses your existing on-premises deployment or Cloud Connector Edition—to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="29e5c-127">ユーザーを Teams にアップグレードする場合は、[電話システム ダイレクト ルーティングに関する考慮事項](2-envision-make-my-service-decisions-direct-routing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29e5c-127">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
