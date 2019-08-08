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
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7729cd65ff5d58d348229c4ec5ec6182f06aa5de
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235910"
---
<span data-ttu-id="4e924-103">![展開と実装の段階に重点を置いた、アップグレード手順の各段階](media/upgrade-banner-deployment.png "展開と実装の段階に重点を置いた、アップグレード手順の各段階")</span><span class="sxs-lookup"><span data-stu-id="4e924-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="4e924-104">この記事は、お客様のアップグレード手順における展開と実装の段階の一部を取り上げています。</span><span class="sxs-lookup"><span data-stu-id="4e924-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="4e924-105">先に進む前に、次のアクティビティを完了していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4e924-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="4e924-106">プロジェクトの関係者をリスト化した</span><span class="sxs-lookup"><span data-stu-id="4e924-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="4e924-107">プロジェクトの対象範囲を定義した</span><span class="sxs-lookup"><span data-stu-id="4e924-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="4e924-108">Skype for Business と Teams の共存と相互運用を理解した</span><span class="sxs-lookup"><span data-stu-id="4e924-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="4e924-109">アップグレードの手順を選択した</span><span class="sxs-lookup"><span data-stu-id="4e924-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="4e924-110">環境を準備した</span><span class="sxs-lookup"><span data-stu-id="4e924-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="4e924-111">組織を準備した</span><span class="sxs-lookup"><span data-stu-id="4e924-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="4e924-112">パイロットを実施した</span><span class="sxs-lookup"><span data-stu-id="4e924-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a><span data-ttu-id="4e924-113">Skype for Business ハイブリッド展開から Teams にアップグレードする</span><span class="sxs-lookup"><span data-stu-id="4e924-113">Upgrade from a Skype for Business hybrid deployment to Teams</span></span>

<span data-ttu-id="4e924-114">この記事のガイダンスに従って、Skype for Business または Microsoft Lync をオンプレミスで展開し、Office 365 テナントでハイブリッド展開で構成している場合は、複数のユーザーを使用して、組織で選択的にチームにアップグレードすることを希望しています。共存モード (またはすべて)</span><span class="sxs-lookup"><span data-stu-id="4e924-114">Follow the guidance in this article if you’ve deployed Skype for Business or Microsoft Lync on-premises and configured it in a hybrid deployment with your Office 365 tenant, and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="4e924-115">アップグレードの過程では、ユーザーを Skype for Business Online に移行する必要があり (まだオンラインになっていない場合)、適切な共存とアップグレードモードを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4e924-115">For either upgrade journey, you need to move your users to Skype for Business Online (if they aren’t already homed online) and then assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a><span data-ttu-id="4e924-116">手順 1: ユーザーを Skype for Business Online に移動する</span><span class="sxs-lookup"><span data-stu-id="4e924-116">Step 1: Move users to Skype for Business Online</span></span>

<span data-ttu-id="4e924-117">この手順は、現在オンプレミスのホームユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="4e924-117">This step applies to users who are currently homed on-premises.</span></span> <span data-ttu-id="4e924-118">これらのユーザーを Skype for Business Online に移行する方法の詳細については、「[オンプレミスから skype For Business online にユーザーを移行する](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e924-118">For more information about moving these users to Skype for Business Online, see [Move users from on -premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="4e924-119">手順 2: 共存とアップグレードモードを割り当てる</span><span class="sxs-lookup"><span data-stu-id="4e924-119">Step 2: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="4e924-120">Skype for Business Online にユーザーを移動したら、組織が選択したアップグレードの手順に応じて、ユーザーに適切な共存モードを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4e924-120">After you’ve moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="4e924-121">詳細については、「[共存およびアップグレードを設定する](https://aka.ms/SkypeToTeams-SetCoexistence)」および「[TeamsUpgradePolicy: 移行と共存の管理](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e924-121">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

> [!NOTE]
> <span data-ttu-id="4e924-122">Skype for Business Server 2019 および今後の Skype for Business Server 2015 の累積的な更新プログラムでは、手順 1 (ユーザーを Skype for Business Online に移行する) と手順 2 (ユーザーを Teams にアップグレードする) を1つの手順で実行できます。</span><span class="sxs-lookup"><span data-stu-id="4e924-122">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you’ll be able to perform Step 1 (moving users to Skype for Business Online) and Step 2 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="4e924-123">詳細については、Skype for Business Server 2019 のリリース後に発表されます。</span><span class="sxs-lookup"><span data-stu-id="4e924-123">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="4e924-124">電話システムと Teams のアップグレード</span><span class="sxs-lookup"><span data-stu-id="4e924-124">Phone System and Teams upgrade</span></span>

<span data-ttu-id="4e924-125">Skype for Business のハイブリッド展開を通話プラン付きの電話システムに移行して、Microsoft が公衆交換電話網 (PSTN) プロバイダーになる場合、電話番号持ち運びの手続きを完了していれば、ユーザーを Teams にアップグレードすることで、着信 PSTN 通話は自動的に Teams に移行されます。</span><span class="sxs-lookup"><span data-stu-id="4e924-125">If you’re transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you’ve completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="4e924-126">通話プランを利用できない場合、または既存の PSTN 接続プロバイダーを使用する場合は、エンタープライズ voip 展開 (または既存のオンプレミス展開またはクラウドコネクタエディションを使用するハイブリッド音声の展開) に移行する必要があります。Microsoft Phone システムのダイレクトルーティング。</span><span class="sxs-lookup"><span data-stu-id="4e924-126">If Calling Plans isn’t available or you intend to use your existing PSTN connectivity provider, you need to transition your enterprise voice deployment—or hybrid voice deployment that uses your existing on-premises deployment or Cloud Connector Edition—to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="4e924-127">ユーザーを Teams にアップグレードする場合は、[電話システム ダイレクト ルーティングに関する考慮事項](2-envision-make-my-service-decisions-direct-routing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e924-127">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
