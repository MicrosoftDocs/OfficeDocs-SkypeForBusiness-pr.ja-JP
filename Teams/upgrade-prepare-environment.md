---
title: Teams にアップグレードするための環境の準備
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Skype for Business から Teams へのアップグレードを開始する前に、環境とネットワークの準備を確認します。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6aa61c739910e00a277f6c3f201222ac5eb782da
ms.sourcegitcommit: 6acede580649588334aeb48130ab2a5d73245723
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2020
ms.locfileid: "44523020"
---
# <a name="prepare-your-environment-for-upgrading-to-teams"></a><span data-ttu-id="615a1-103">Teams にアップグレードするための環境の準備</span><span class="sxs-lookup"><span data-stu-id="615a1-103">Prepare your environment for upgrading to Teams</span></span>

<span data-ttu-id="615a1-104">![技術準備段階が協調表示されたアップグレード行程図](media/upgrade-banner-tech-readiness.png "技術準備段階が強調表示された、アップグレード行程の各段階")</span><span class="sxs-lookup"><span data-stu-id="615a1-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="615a1-105">この記事は、ユーザーの準備段階と並行して実行されるアクティビティである、アップグレードが行われる技術準備段階の一部です。</span><span class="sxs-lookup"><span data-stu-id="615a1-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="615a1-106">続行する前に、以前のステージでこれらのアクティビティが完了していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="615a1-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="615a1-107">プロジェクトの関係者をリスト化した</span><span class="sxs-lookup"><span data-stu-id="615a1-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="615a1-108">プロジェクトの対象範囲を定義した</span><span class="sxs-lookup"><span data-stu-id="615a1-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="615a1-109">Skype for Business と Teams の共存と相互運用を理解した</span><span class="sxs-lookup"><span data-stu-id="615a1-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="615a1-110">アップグレードの手順を選択した</span><span class="sxs-lookup"><span data-stu-id="615a1-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="615a1-111">組織のチームのアップグレードを成功させるには、現在の Skype for Business 環境とネットワークの準備を検証することが重要です。</span><span class="sxs-lookup"><span data-stu-id="615a1-111">To drive a successful Teams upgrade in your organization, it's important that you validate your current Skype for Business environment and your network readiness.</span></span> <span data-ttu-id="615a1-112">現在の環境を準備することで、Teams でのユーザーエクスペリエンスの品質を向上させるだけでなく、高品質なユーザーエクスペリエンスを実現することができます。</span><span class="sxs-lookup"><span data-stu-id="615a1-112">Preparing your current environment will help ensure a high-quality user experience now, in addition to improving the quality of the user experience in Teams.</span></span> <span data-ttu-id="615a1-113">個々の手順を計画する時間を取ることで、展開を迅速化し、重要な実施項目をスキップしていないことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="615a1-113">Taking time to plan individual steps can help accelerate your deployment and ensure that you haven't skipped any important action items.</span></span>

<span data-ttu-id="615a1-114">ユーザーの準備をする準備をして、次の作業を並行して完了します。</span><span class="sxs-lookup"><span data-stu-id="615a1-114">Complete these activities in parallel with your user readiness preparation:</span></span>

- <span data-ttu-id="615a1-115">アップグレードを成功させるために必要なものがあるかどうかを確認するために[IT スタッフを準備](upgrade-prepare-IT-pros.md)します。</span><span class="sxs-lookup"><span data-stu-id="615a1-115">[Prepare your IT staff](upgrade-prepare-IT-pros.md) to help ensure they have what they need for a successful upgrade journey.</span></span>
- <span data-ttu-id="615a1-116">環境がすべての[前提条件](upgrade-plan-journey-prerequisites.md)を満たしていることを確認し、Office 365 サービスと Teams の間の依存関係を理解します。</span><span class="sxs-lookup"><span data-stu-id="615a1-116">Verify that your environment meets all [prerequisites](upgrade-plan-journey-prerequisites.md), and understand dependencies among Office 365 services and Teams.</span></span>
- <span data-ttu-id="615a1-117">サンプルのアンケートを使用して[環境を評価](upgrade-plan-journey-evaluate-environment.md)し、組織がチームへのアップグレードを成功させるための準備を確認します。</span><span class="sxs-lookup"><span data-stu-id="615a1-117">[Evaluate your environment](upgrade-plan-journey-evaluate-environment.md) by performing environmental discovery by using a sample questionnaire to confirm your organization's readiness to undertake a successful upgrade journey to Teams.</span></span>
- <span data-ttu-id="615a1-118">計画、準備、および必要な修復手順に従って、組織のワークロードをサポートするようにネットワークを[準備](prepare-network.md)します。</span><span class="sxs-lookup"><span data-stu-id="615a1-118">[Prepare your network](prepare-network.md) through planning, preparation, and taking any necessary remediation steps for your network to support Teams workloads.</span></span>
- <span data-ttu-id="615a1-119">オンボードチェックリストを使用してサービスをロールアウトするための[準備](upgrade-prepare-environment-prepare-service.md)をして、チームの構成で Skype for Business から teams へのユーザーの移行をサポートする準備ができていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="615a1-119">[Prepare your service](upgrade-prepare-environment-prepare-service.md) for rollout by using onboarding checklists to ensure that your Teams configuration is ready to support migrating your users from Skype for Business to Teams.</span></span>
