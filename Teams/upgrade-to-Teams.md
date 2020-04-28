---
title: Microsoft Teams にアップグレードする |Skype for Business Teams のロードマップ
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
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
ms.openlocfilehash: 030081b4fbf633e808e1c340f7b88b8224c13700
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905189"
---
# <a name="overview"></a><span data-ttu-id="7d9ee-103">概要</span><span class="sxs-lookup"><span data-stu-id="7d9ee-103">Overview</span></span>

<span data-ttu-id="7d9ee-104">![「展開と実装」段階が強調表示された、アップグレード行程の各段階](media/upgrade-banner-deployment.png "「展開と実装」段階が強調表示された、アップグレード行程の各段階")</span><span class="sxs-lookup"><span data-stu-id="7d9ee-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="7d9ee-105">この記事は、アップグレード過程の展開と実装の段階に含まれています。</span><span class="sxs-lookup"><span data-stu-id="7d9ee-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="7d9ee-106">続行する前に、次の作業が完了していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7d9ee-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="7d9ee-107">プロジェクトの関係者をリスト化した</span><span class="sxs-lookup"><span data-stu-id="7d9ee-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="7d9ee-108">プロジェクトの対象範囲を定義した</span><span class="sxs-lookup"><span data-stu-id="7d9ee-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="7d9ee-109">Skype for Business と Teams の共存と相互運用を理解した</span><span class="sxs-lookup"><span data-stu-id="7d9ee-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="7d9ee-110">アップグレードの手順を選択した</span><span class="sxs-lookup"><span data-stu-id="7d9ee-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="7d9ee-111">環境を準備した</span><span class="sxs-lookup"><span data-stu-id="7d9ee-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="7d9ee-112">組織を準備した</span><span class="sxs-lookup"><span data-stu-id="7d9ee-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)

<span data-ttu-id="7d9ee-113">チームにアップグレードを実行するための手順は、Skype for Business の現在の展開によって異なります。</span><span class="sxs-lookup"><span data-stu-id="7d9ee-113">The steps you take to perform your upgrade to Teams depends on your current deployment of Skype for Business:</span></span>

1. <span data-ttu-id="7d9ee-114">アップグレードを開始する前に、[ユーザーのパイロットを実施](pilot-essentials.md)してください。</span><span class="sxs-lookup"><span data-stu-id="7d9ee-114">Before beginning your upgrade, be sure you [conduct a user pilot](pilot-essentials.md).</span></span>

2.  <span data-ttu-id="7d9ee-115">次に、現在の環境に基づいて、出発地点を選択します。</span><span class="sxs-lookup"><span data-stu-id="7d9ee-115">Next, based on your current environment, choose your starting point:</span></span>  

    - <span data-ttu-id="7d9ee-116">**Skype For Business online から teams にアップグレードする場合**は、「 [Skype for Business online から teams にアップグレード](https://aka.ms/SkypeToTeams-UpgradeOnline)する」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="7d9ee-116">**If you are upgrading from Skype for Business Online to Teams**, follow the steps in [Upgrade from Skype for Business Online to Teams](https://aka.ms/SkypeToTeams-UpgradeOnline).</span></span>

    -  <span data-ttu-id="7d9ee-117">**Skype For business のオンプレミス環境からアップグレードする場合**は、ユーザーをチームに移行する前に、オンプレミスとオンラインの環境間の接続を設定するための追加の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d9ee-117">**If you are upgrading from a Skype for Business on-premises environment**, you'll need to perform some extra steps to set up connectivity between your on-premises and online environments before you move your users to Teams.</span></span> <span data-ttu-id="7d9ee-118">詳細については、「 [Skype For business をオンプレミスから Teams にアップグレードする](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d9ee-118">For more information, see [Upgrade Skype for Business on-premises to Teams](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md).</span></span>





> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]
