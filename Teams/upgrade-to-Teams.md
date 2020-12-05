---
title: Microsoft Teams へのアップグレードの実装の概要
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 現在の Skype for Business 展開に基づいて、Microsoft Teams への最適なアップグレードパスを決定します。
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
ms.openlocfilehash: 0db2e752bb163f806c5dcba7aa56fc36bae7c2ef
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578360"
---
# <a name="overview-of-implementing-your-upgrade"></a><span data-ttu-id="3e545-103">アップグレードの実装の概要</span><span class="sxs-lookup"><span data-stu-id="3e545-103">Overview of implementing your upgrade</span></span>

<span data-ttu-id="3e545-104">![「展開と実装」段階が強調表示された、アップグレード行程の各段階](media/upgrade-banner-deployment.png "「展開と実装」段階が強調表示された、アップグレード行程の各段階")</span><span class="sxs-lookup"><span data-stu-id="3e545-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="3e545-105">この記事は、アップグレード過程の展開と実装の段階に含まれています。</span><span class="sxs-lookup"><span data-stu-id="3e545-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> 



## <a name="prerequisite-planning-activities"></a><span data-ttu-id="3e545-106">前提条件の計画アクティビティ</span><span class="sxs-lookup"><span data-stu-id="3e545-106">Prerequisite planning activities</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3e545-107">アップグレードの実装を進める前に、「 [アップグレードの計画](upgrade-plan-journey.md) 」を参照して、前提条件の計画をすべて完了していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3e545-107">Before proceeding with your upgrade implementation, confirm that you've read the planning content starting with [Plan your upgrade](upgrade-plan-journey.md) to ensure you've completed all prerequisite planning activites.</span></span>


- [<span data-ttu-id="3e545-108">プロジェクトの関係者をリスト化した</span><span class="sxs-lookup"><span data-stu-id="3e545-108">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="3e545-109">プロジェクトの対象範囲を定義した</span><span class="sxs-lookup"><span data-stu-id="3e545-109">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="3e545-110">Skype for Business と Teams の共存と相互運用を理解した</span><span class="sxs-lookup"><span data-stu-id="3e545-110">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="3e545-111">アップグレードの手順を選択した</span><span class="sxs-lookup"><span data-stu-id="3e545-111">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="3e545-112">ユーザーパイロットの計画</span><span class="sxs-lookup"><span data-stu-id="3e545-112">Planned a user pilot</span></span>](pilot-essentials.md)
- [<span data-ttu-id="3e545-113">環境を準備した</span><span class="sxs-lookup"><span data-stu-id="3e545-113">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="3e545-114">組織を準備した</span><span class="sxs-lookup"><span data-stu-id="3e545-114">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)

## <a name="choose-your-upgrade-starting-point"></a><span data-ttu-id="3e545-115">アップグレードの出発点を選ぶ</span><span class="sxs-lookup"><span data-stu-id="3e545-115">Choose your upgrade starting point</span></span>

<span data-ttu-id="3e545-116">チームにアップグレードを実行するための手順は、Skype for Business の現在の展開によって異なります。</span><span class="sxs-lookup"><span data-stu-id="3e545-116">The steps you take to perform your upgrade to Teams depends on your current deployment of Skype for Business:</span></span>

<span data-ttu-id="3e545-117">現在の環境に基づいて、出発地点を選択します。</span><span class="sxs-lookup"><span data-stu-id="3e545-117">Based on your current environment, choose your starting point:</span></span>  

- <span data-ttu-id="3e545-118">**Skype For Business online から teams にアップグレードする場合** は、「 [Skype for Business online から teams にアップグレード](https://aka.ms/SkypeToTeams-UpgradeOnline)する」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="3e545-118">**If you are upgrading from Skype for Business Online to Teams**, follow the steps in [Upgrade from Skype for Business Online to Teams](https://aka.ms/SkypeToTeams-UpgradeOnline).</span></span>

-  <span data-ttu-id="3e545-119">**Skype For business のオンプレミス環境からアップグレードする場合** は、ユーザーをチームに移行する前に、オンプレミスとオンラインの環境間の接続を設定するための追加の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e545-119">**If you are upgrading from a Skype for Business on-premises environment**, you'll need to perform some extra steps to set up connectivity between your on-premises and online environments before you move your users to Teams.</span></span> <span data-ttu-id="3e545-120">詳細については、「 [Skype For business をオンプレミスから Teams にアップグレードする](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e545-120">For more information, see [Upgrade Skype for Business on-premises to Teams](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md).</span></span>





> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]
