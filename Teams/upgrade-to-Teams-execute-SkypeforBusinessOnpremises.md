---
title: オンプレミスの Skype for Business を Microsoft Teams にアップグレードする |展開 |Lync
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Skype for Business オンプレミスの展開から Teams にアップグレードする場合の考慮事項
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f234c6fe959d35d2f92e117e28af8d15f0a02819
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235902"
---
<span data-ttu-id="4c937-103">![展開と実装の段階に重点を置いた、アップグレード手順の各段階](media/upgrade-banner-deployment.png "展開と実装の段階に重点を置いた、アップグレード手順の各段階")</span><span class="sxs-lookup"><span data-stu-id="4c937-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="4c937-104">この記事は、アップグレード過程の展開と実装の段階に含まれています。</span><span class="sxs-lookup"><span data-stu-id="4c937-104">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="4c937-105">先に進む前に、次のアクティビティを完了していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4c937-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="4c937-106">プロジェクトの関係者をリスト化した</span><span class="sxs-lookup"><span data-stu-id="4c937-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="4c937-107">プロジェクトの対象範囲を定義した</span><span class="sxs-lookup"><span data-stu-id="4c937-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="4c937-108">Skype for Business と Teams の共存と相互運用を理解した</span><span class="sxs-lookup"><span data-stu-id="4c937-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="4c937-109">アップグレードの手順を選択した</span><span class="sxs-lookup"><span data-stu-id="4c937-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="4c937-110">環境を準備した</span><span class="sxs-lookup"><span data-stu-id="4c937-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="4c937-111">組織を準備した</span><span class="sxs-lookup"><span data-stu-id="4c937-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="4c937-112">パイロットを実施した</span><span class="sxs-lookup"><span data-stu-id="4c937-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a><span data-ttu-id="4c937-113">Skype for Business オンプレミスの展開から Teams にアップグレードする</span><span class="sxs-lookup"><span data-stu-id="4c937-113">Upgrade from a Skype for Business on-premises deployment to Teams</span></span>

<span data-ttu-id="4c937-114">オンプレミスの Skype for Business または Microsoft Lync を展開していて、組織が複数の共存モード (またはすべて) を使用して、選択的に Microsoft Teams にアップグレードする場合は、この記事のガイダンスに従ってください。</span><span class="sxs-lookup"><span data-stu-id="4c937-114">Follow the guidance in this article if you’ve deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Microsoft Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="4c937-115">手順 1: ハイブリッド接続の展開</span><span class="sxs-lookup"><span data-stu-id="4c937-115">Step 1: Deploy hybrid connectivity</span></span>

<span data-ttu-id="4c937-116">ユーザーを Teams にアップグレードする際の重要な前提条件は、ハイブリッド接続を展開することです。</span><span class="sxs-lookup"><span data-stu-id="4c937-116">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span>

<span data-ttu-id="4c937-117">詳細については、「 [skype For Business Server と skype For Business Online の間にハイブリッド接続を展開](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c937-117">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span></span>

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a><span data-ttu-id="4c937-118">手順 2: 組織に対して選択したアップグレードを実装する</span><span class="sxs-lookup"><span data-stu-id="4c937-118">Step 2: Implement your chosen upgrade journey for your organization</span></span>

<span data-ttu-id="4c937-119">ハイブリッドセットアップが完了したら、Office 365 にユーザーを移動することを計画できます。</span><span class="sxs-lookup"><span data-stu-id="4c937-119">After you’ve completed your hybrid setup, you can plan to move your users to Office 365.</span></span>

<span data-ttu-id="4c937-120">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c937-120">For more information, see:</span></span>

- <span data-ttu-id="4c937-121">[TeamsUpgradePolicy: 移行と共存を管理](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)します。</span><span class="sxs-lookup"><span data-stu-id="4c937-121">[TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

- <span data-ttu-id="4c937-122">[オンプレミスから Skype For Business Online にユーザーを移動](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)します。</span><span class="sxs-lookup"><span data-stu-id="4c937-122">[Move users from on premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="4c937-123">電話システムと Teams のアップグレード</span><span class="sxs-lookup"><span data-stu-id="4c937-123">Phone System and Teams upgrade</span></span>

<span data-ttu-id="4c937-124">オンプレミスの電話システムから Teams への移行では、電話システムのダイレクトルーティング ("直接ルーティング") または Microsoft から提供されている Office 365 の通話プランを利用できます。</span><span class="sxs-lookup"><span data-stu-id="4c937-124">Transitioning from on-premises phone systems to Teams will allow you to take advantage of Phone System Direct Routing (“Direct Routing”) or the Microsoft-provided Calling Plans for Office 365.</span></span>

<span data-ttu-id="4c937-125">Office 365 で通話プランを使用していない場合は、チームへのアップグレードの一環として、エンタープライズボイスの展開を電話システムのダイレクトルーティングに切り替える必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c937-125">If you're not using Calling Plans in Office 365, you need to transition your enterprise voice deployment to Phone System Direct Routing as part of your upgrade to Teams.</span></span>

<span data-ttu-id="4c937-126">詳細については、「[電話システムのダイレクトルーティングに関するその他の考慮事項](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c937-126">For more information, see [additional considerations for Phone System Direct Routing](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing).</span></span> <span data-ttu-id="4c937-127">Office 365 での通話プランの使用を計画している場合は、[電話番号を office 365 に移行](https://docs.microsoft.com/microsoftteams/transfer-phone-numbers-to-office-365)するためのガイダンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c937-127">If you are planning to use Calling Plans in Office 365, please refer to our guidance for [transferring your phone numbers to Office 365](https://docs.microsoft.com/microsoftteams/transfer-phone-numbers-to-office-365).</span></span>