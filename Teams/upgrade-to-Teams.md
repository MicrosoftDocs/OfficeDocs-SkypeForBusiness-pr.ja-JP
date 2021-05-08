---
title: アプリケーションへのアップグレードの実装のMicrosoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 現在のデプロイに基づいて、Microsoft TeamsアップグレードパスをSkype for Businessします。
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
ms.openlocfilehash: 1774b8bebc1330e69a611e64d4f0a8e01f05febb
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282374"
---
# <a name="overview-of-implementing-your-upgrade"></a><span data-ttu-id="9f974-103">アップグレードの実装の概要</span><span class="sxs-lookup"><span data-stu-id="9f974-103">Overview of implementing your upgrade</span></span>

<span data-ttu-id="9f974-104">![「展開と実装」段階が強調表示された、アップグレード行程の各段階](media/upgrade-banner-deployment.png "「展開と実装」段階が強調表示された、アップグレード行程の各段階")</span><span class="sxs-lookup"><span data-stu-id="9f974-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="9f974-105">この記事は、アップグレード体験のデプロイと実装のステージの一部です。</span><span class="sxs-lookup"><span data-stu-id="9f974-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> 



## <a name="prerequisite-planning-activities"></a><span data-ttu-id="9f974-106">前提条件となる計画アクティビティ</span><span class="sxs-lookup"><span data-stu-id="9f974-106">Prerequisite planning activities</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9f974-107">アップグレードの実装に進む前に、「アップグレードを計画する」から始まる計画コンテンツ[](upgrade-plan-journey.md)を読んで、前提条件となる計画のすべての活動が完了されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9f974-107">Before proceeding with your upgrade implementation, confirm that you've read the planning content starting with [Plan your upgrade](upgrade-plan-journey.md) to ensure you've completed all prerequisite planning activites.</span></span>


- [<span data-ttu-id="9f974-108">プロジェクトの関係者をリスト化した</span><span class="sxs-lookup"><span data-stu-id="9f974-108">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="9f974-109">プロジェクトの対象範囲を定義した</span><span class="sxs-lookup"><span data-stu-id="9f974-109">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="9f974-110">Skype for Business と Teams の共存と相互運用を理解した</span><span class="sxs-lookup"><span data-stu-id="9f974-110">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="9f974-111">アップグレードの手順を選択した</span><span class="sxs-lookup"><span data-stu-id="9f974-111">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="9f974-112">ユーザー パイロットの計画</span><span class="sxs-lookup"><span data-stu-id="9f974-112">Planned a user pilot</span></span>](pilot-essentials.md)
- [<span data-ttu-id="9f974-113">環境を準備した</span><span class="sxs-lookup"><span data-stu-id="9f974-113">Prepared your environment</span></span>](./upgrade-prepare-environment.md)
- [<span data-ttu-id="9f974-114">組織を準備した</span><span class="sxs-lookup"><span data-stu-id="9f974-114">Prepared your organization</span></span>](./upgrade-prepare-organization.md)

## <a name="choose-your-upgrade-starting-point"></a><span data-ttu-id="9f974-115">アップグレードの開始点を選択する</span><span class="sxs-lookup"><span data-stu-id="9f974-115">Choose your upgrade starting point</span></span>

<span data-ttu-id="9f974-116">アプリケーションへのアップグレードを実行する手順は、Teamsのデプロイによって異Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="9f974-116">The steps you take to perform your upgrade to Teams depends on your current deployment of Skype for Business:</span></span>

<span data-ttu-id="9f974-117">現在の環境に基づいて、開始点を選択します。</span><span class="sxs-lookup"><span data-stu-id="9f974-117">Based on your current environment, choose your starting point:</span></span>  

- <span data-ttu-id="9f974-118">Skype for Business Online から Teams にアップグレードする場合は **、「Skype for Business Online** から Teams にアップグレードする」の手順に [従います](./upgrade-to-teams-execute-skypeforbusinessonline.md)。</span><span class="sxs-lookup"><span data-stu-id="9f974-118">**If you are upgrading from Skype for Business Online to Teams**, follow the steps in [Upgrade from Skype for Business Online to Teams](./upgrade-to-teams-execute-skypeforbusinessonline.md).</span></span>

-  <span data-ttu-id="9f974-119">**Skype for Business** オンプレミス環境からアップグレードする場合は、ユーザーを Teams に移動する前に、オンプレミス環境とオンライン環境間の接続を設定するための追加の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f974-119">**If you are upgrading from a Skype for Business on-premises environment**, you'll need to perform some extra steps to set up connectivity between your on-premises and online environments before you move your users to Teams.</span></span> <span data-ttu-id="9f974-120">詳細については、「オンプレミスからオンプレミス[へのSkype for Businessアップグレード」を参照Teams。](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md)</span><span class="sxs-lookup"><span data-stu-id="9f974-120">For more information, see [Upgrade Skype for Business on-premises to Teams](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md).</span></span>





> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]