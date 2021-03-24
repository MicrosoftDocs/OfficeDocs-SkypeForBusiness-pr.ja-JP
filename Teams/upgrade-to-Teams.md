---
title: Microsoft Teams へのアップグレードの実装の概要
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 現在の Skype for Business 展開に基づいて、Microsoft Teams への最適なアップグレード パスを決定します。
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
ms.openlocfilehash: 3eb6c65d414217810c795aa72701a8e546f30643
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096031"
---
# <a name="overview-of-implementing-your-upgrade"></a><span data-ttu-id="d0c0f-103">アップグレードの実装の概要</span><span class="sxs-lookup"><span data-stu-id="d0c0f-103">Overview of implementing your upgrade</span></span>

<span data-ttu-id="d0c0f-104">![「展開と実装」段階が強調表示された、アップグレード行程の各段階](media/upgrade-banner-deployment.png "「展開と実装」段階が強調表示された、アップグレード行程の各段階")</span><span class="sxs-lookup"><span data-stu-id="d0c0f-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="d0c0f-105">この記事は、アップグレードの手順の展開と実装のステージの一部です。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> 



## <a name="prerequisite-planning-activities"></a><span data-ttu-id="d0c0f-106">前提条件となる計画アクティビティ</span><span class="sxs-lookup"><span data-stu-id="d0c0f-106">Prerequisite planning activities</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d0c0f-107">アップグレードの実装を進める前に、すべての前提条件となる計画の有効化を完了するために、[](upgrade-plan-journey.md)アップグレードの計画から始まる計画コンテンツを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-107">Before proceeding with your upgrade implementation, confirm that you've read the planning content starting with [Plan your upgrade](upgrade-plan-journey.md) to ensure you've completed all prerequisite planning activites.</span></span>


- [<span data-ttu-id="d0c0f-108">プロジェクトの関係者をリスト化した</span><span class="sxs-lookup"><span data-stu-id="d0c0f-108">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="d0c0f-109">プロジェクトの対象範囲を定義した</span><span class="sxs-lookup"><span data-stu-id="d0c0f-109">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="d0c0f-110">Skype for Business と Teams の共存と相互運用を理解した</span><span class="sxs-lookup"><span data-stu-id="d0c0f-110">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="d0c0f-111">アップグレードの手順を選択した</span><span class="sxs-lookup"><span data-stu-id="d0c0f-111">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="d0c0f-112">ユーザー パイロットを計画しました</span><span class="sxs-lookup"><span data-stu-id="d0c0f-112">Planned a user pilot</span></span>](pilot-essentials.md)
- [<span data-ttu-id="d0c0f-113">環境を準備した</span><span class="sxs-lookup"><span data-stu-id="d0c0f-113">Prepared your environment</span></span>](./upgrade-prepare-environment.md)
- [<span data-ttu-id="d0c0f-114">組織を準備した</span><span class="sxs-lookup"><span data-stu-id="d0c0f-114">Prepared your organization</span></span>](./upgrade-prepare-organization.md)

## <a name="choose-your-upgrade-starting-point"></a><span data-ttu-id="d0c0f-115">アップグレードの開始点を選択する</span><span class="sxs-lookup"><span data-stu-id="d0c0f-115">Choose your upgrade starting point</span></span>

<span data-ttu-id="d0c0f-116">Teams へのアップグレードを実行する手順は、Skype for Business の現在の展開によって異なります。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-116">The steps you take to perform your upgrade to Teams depends on your current deployment of Skype for Business:</span></span>

<span data-ttu-id="d0c0f-117">現在の環境に基づいて、開始点を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-117">Based on your current environment, choose your starting point:</span></span>  

- <span data-ttu-id="d0c0f-118">**Skype for Business Online** から Teams にアップグレードする場合は、「Skype for Business Online から Teams にアップグレードする [」の手順に従います](./upgrade-to-teams-execute-skypeforbusinessonline.md)。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-118">**If you are upgrading from Skype for Business Online to Teams**, follow the steps in [Upgrade from Skype for Business Online to Teams](./upgrade-to-teams-execute-skypeforbusinessonline.md).</span></span>

-  <span data-ttu-id="d0c0f-119">**Skype for Business** オンプレミス環境からアップグレードする場合は、ユーザーを Teams に移動する前に、オンプレミス環境とオンライン環境間の接続をセットアップするための追加の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-119">**If you are upgrading from a Skype for Business on-premises environment**, you'll need to perform some extra steps to set up connectivity between your on-premises and online environments before you move your users to Teams.</span></span> <span data-ttu-id="d0c0f-120">詳細については [、「Skype for Business オンプレミスを Teams にアップグレードする」を参照してください](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md)。</span><span class="sxs-lookup"><span data-stu-id="d0c0f-120">For more information, see [Upgrade Skype for Business on-premises to Teams](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md).</span></span>





> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]