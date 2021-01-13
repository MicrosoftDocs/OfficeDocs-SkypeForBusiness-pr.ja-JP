---
title: Skype for Business オンプレミスから Teams にアップグレードする
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Skype for Business オンプレミス展開から組織を Microsoft Teams に移行する方法について説明します。
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
ms.openlocfilehash: 90542f680c1d3992f5f318bfedad8a12470d282b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820947"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a><span data-ttu-id="40365-103">Skype for Business オンプレミス展開から Teams にアップグレードする</span><span class="sxs-lookup"><span data-stu-id="40365-103">Upgrade from a Skype for Business on-premises deployment to Teams</span></span>

<span data-ttu-id="40365-104">![「展開と実装」段階が強調表示された、アップグレード行程の各段階](media/upgrade-banner-deployment.png "「展開と実装」段階が強調表示された、アップグレード行程の各段階")</span><span class="sxs-lookup"><span data-stu-id="40365-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="40365-105">この記事は、アップグレードの手順の展開と実装のステージの一部です。</span><span class="sxs-lookup"><span data-stu-id="40365-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="40365-106">続く前に、次のアクティビティを完了したと確認します。</span><span class="sxs-lookup"><span data-stu-id="40365-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="40365-107">プロジェクトの関係者をリスト化した</span><span class="sxs-lookup"><span data-stu-id="40365-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="40365-108">プロジェクトの対象範囲を定義した</span><span class="sxs-lookup"><span data-stu-id="40365-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="40365-109">Skype for Business と Teams の共存と相互運用を理解した</span><span class="sxs-lookup"><span data-stu-id="40365-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="40365-110">アップグレードの手順を選択した</span><span class="sxs-lookup"><span data-stu-id="40365-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="40365-111">環境を準備した</span><span class="sxs-lookup"><span data-stu-id="40365-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="40365-112">組織を準備した</span><span class="sxs-lookup"><span data-stu-id="40365-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="40365-113">パイロットを実施した</span><span class="sxs-lookup"><span data-stu-id="40365-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="40365-114">Skype for Business または Microsoft Lync をオンプレミスに展開し、組織が複数の共存モードを使用して Microsoft Teams にアップグレードする場合、またはすべてのモードを使用する場合は、この記事のガイダンスに従います。</span><span class="sxs-lookup"><span data-stu-id="40365-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Microsoft Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="40365-115">手順 1: ハイブリッド接続の展開</span><span class="sxs-lookup"><span data-stu-id="40365-115">Step 1: Deploy hybrid connectivity</span></span>

<span data-ttu-id="40365-116">ユーザーを Teams にアップグレードする際の重要な前提条件は、ハイブリッド接続を展開することです。</span><span class="sxs-lookup"><span data-stu-id="40365-116">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span>

<span data-ttu-id="40365-117">詳細については、「Skype for Business Server と Skype for Business Online の間にハイブリッド接続を展開する[」を参照してください](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)。</span><span class="sxs-lookup"><span data-stu-id="40365-117">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span></span>

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a><span data-ttu-id="40365-118">手順 2: 組織に対して選択したアップグレードの手順を実装する</span><span class="sxs-lookup"><span data-stu-id="40365-118">Step 2: Implement your chosen upgrade journey for your organization</span></span>

<span data-ttu-id="40365-119">ハイブリッド セットアップが完了したら、ユーザーを Microsoft 365 または Office 365 に移行することができます。</span><span class="sxs-lookup"><span data-stu-id="40365-119">After you've completed your hybrid setup, you can plan to move your users to Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="40365-120">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40365-120">For more information, see:</span></span>

- <span data-ttu-id="40365-121">[TeamsUpgradePolicy: 移行と共存の管理](upgrade-to-teams-on-prem-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="40365-121">[TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).</span></span>

- <span data-ttu-id="40365-122">[オンプレミスから Skype for Business Online にユーザーを移動します](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)。</span><span class="sxs-lookup"><span data-stu-id="40365-122">[Move users from on premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="40365-123">電話システムと Teams のアップグレード</span><span class="sxs-lookup"><span data-stu-id="40365-123">Phone System and Teams upgrade</span></span>

<span data-ttu-id="40365-124">オンプレミスの電話システムから Teams に移行すると、電話システムダイレクト ルーティング ("ダイレクト ルーティング") または Microsoft が提供する Microsoft 365 または Office 365 の通話プランを利用できます。</span><span class="sxs-lookup"><span data-stu-id="40365-124">Transitioning from on-premises phone systems to Teams will allow you to take advantage of Phone System Direct Routing ("Direct Routing") or the Microsoft-provided Calling Plans for Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="40365-125">通話プランを使用していない場合は、Teams へのアップグレードの一環として、エンタープライズ 音声展開を電話システム ダイレクト ルーティングに移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40365-125">If you're not using Calling Plans, you need to transition your enterprise voice deployment to Phone System Direct Routing as part of your upgrade to Teams.</span></span>

<span data-ttu-id="40365-126">詳細については、電話システム ダイレクト [ルーティングに関するその他の考慮事項を参照してください](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing)。</span><span class="sxs-lookup"><span data-stu-id="40365-126">For more information, see [additional considerations for Phone System Direct Routing](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing).</span></span> <span data-ttu-id="40365-127">通話プランを使用する予定の場合は、電話番号を Teams に移行する方法のガイダンス [を参照してください](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="40365-127">If you are planning to use Calling Plans, please refer to our guidance for [transferring your phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>