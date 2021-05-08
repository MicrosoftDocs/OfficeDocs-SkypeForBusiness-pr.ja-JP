---
title: Skype for Business オンプレミスから Teams にアップグレードする
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 組織をオンプレミスのデプロイからMicrosoft Teams移行Skype for Business方法について説明します。
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
ms.openlocfilehash: 0585f0ad829f19334d5a970461f1f3248a107e9d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115555"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a><span data-ttu-id="f2671-103">オンプレミスのデプロイSkype for BusinessからオンプレミスデプロイにアップグレードTeams</span><span class="sxs-lookup"><span data-stu-id="f2671-103">Upgrade from a Skype for Business on-premises deployment to Teams</span></span>

<span data-ttu-id="f2671-104">![「展開と実装」段階が強調表示された、アップグレード行程の各段階](media/upgrade-banner-deployment.png "「展開と実装」段階が強調表示された、アップグレード行程の各段階")</span><span class="sxs-lookup"><span data-stu-id="f2671-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="f2671-105">この記事は、アップグレード体験のデプロイと実装のステージの一部です。</span><span class="sxs-lookup"><span data-stu-id="f2671-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="f2671-106">先に進む前に、次のアクティビティを完了していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f2671-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="f2671-107">プロジェクトの関係者をリスト化した</span><span class="sxs-lookup"><span data-stu-id="f2671-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="f2671-108">プロジェクトの対象範囲を定義した</span><span class="sxs-lookup"><span data-stu-id="f2671-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="f2671-109">Skype for Business と Teams の共存と相互運用を理解した</span><span class="sxs-lookup"><span data-stu-id="f2671-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="f2671-110">アップグレードの手順を選択した</span><span class="sxs-lookup"><span data-stu-id="f2671-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="f2671-111">環境を準備した</span><span class="sxs-lookup"><span data-stu-id="f2671-111">Prepared your environment</span></span>](./upgrade-prepare-environment.md)
- [<span data-ttu-id="f2671-112">組織を準備した</span><span class="sxs-lookup"><span data-stu-id="f2671-112">Prepared your organization</span></span>](./upgrade-prepare-organization.md)
- [<span data-ttu-id="f2671-113">パイロットを実施した</span><span class="sxs-lookup"><span data-stu-id="f2671-113">Conducted a pilot</span></span>](./pilot-essentials.md)

<span data-ttu-id="f2671-114">Skype for Business または Microsoft Lync をオンプレミスに展開し、組織が複数の共存モードを使用して選択的に Microsoft Teams にアップグレードする場合、またはすべて使用する場合は、この記事のガイダンスに従います。</span><span class="sxs-lookup"><span data-stu-id="f2671-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Microsoft Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="f2671-115">手順 1: ハイブリッド接続の展開</span><span class="sxs-lookup"><span data-stu-id="f2671-115">Step 1: Deploy hybrid connectivity</span></span>

<span data-ttu-id="f2671-116">ユーザーを Teams にアップグレードする際の重要な前提条件は、ハイブリッド接続を展開することです。</span><span class="sxs-lookup"><span data-stu-id="f2671-116">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span>

<span data-ttu-id="f2671-117">詳細については、「Deploy [hybrid connectivity between Skype for Business Server and Skype for Business Online 」を参照してください。](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span><span class="sxs-lookup"><span data-stu-id="f2671-117">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span></span>

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a><span data-ttu-id="f2671-118">手順 2: 選択したアップグレード体験を組織に実装する</span><span class="sxs-lookup"><span data-stu-id="f2671-118">Step 2: Implement your chosen upgrade journey for your organization</span></span>

<span data-ttu-id="f2671-119">ハイブリッドセットアップが完了したら、ユーザーを別のユーザーに移行Microsoft 365またはOffice 365。</span><span class="sxs-lookup"><span data-stu-id="f2671-119">After you've completed your hybrid setup, you can plan to move your users to Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="f2671-120">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2671-120">For more information, see:</span></span>

- <span data-ttu-id="f2671-121">[TeamsUpgradePolicy: 移行と共存の管理](upgrade-to-teams-on-prem-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="f2671-121">[TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).</span></span>

- <span data-ttu-id="f2671-122">[オンプレミスからオンライン にユーザーをSkype for Businessします](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)。</span><span class="sxs-lookup"><span data-stu-id="f2671-122">[Move users from on premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="f2671-123">電話システムと Teams のアップグレード</span><span class="sxs-lookup"><span data-stu-id="f2671-123">Phone System and Teams upgrade</span></span>

<span data-ttu-id="f2671-124">オンプレミスの電話システムから Teams に移行すると、電話システム ダイレクト ルーティング ("ダイレクト ルーティング") または Microsoft が提供する Microsoft 365 または Office 365 の通話プランを利用できます。</span><span class="sxs-lookup"><span data-stu-id="f2671-124">Transitioning from on-premises phone systems to Teams will allow you to take advantage of Phone System Direct Routing ("Direct Routing") or the Microsoft-provided Calling Plans for Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="f2671-125">通話プランを使用していない場合は、アップグレードの一環として、エンタープライズ音声展開を 電話システム 直接ルーティングに移行する必要Teams。</span><span class="sxs-lookup"><span data-stu-id="f2671-125">If you're not using Calling Plans, you need to transition your enterprise voice deployment to Phone System Direct Routing as part of your upgrade to Teams.</span></span>

<span data-ttu-id="f2671-126">詳細については、「ダイレクト ルーティング[の追加の考慮事項」電話システム参照してください](./direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="f2671-126">For more information, see [additional considerations for Phone System Direct Routing](./direct-routing-landing-page.md).</span></span> <span data-ttu-id="f2671-127">通話プランを使用する予定の場合は、電話番号を通話プランに移行する場合のガイダンス[をTeams。](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)</span><span class="sxs-lookup"><span data-stu-id="f2671-127">If you are planning to use Calling Plans, please refer to our guidance for [transferring your phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>