---
title: マイクロソフト チームのチームで Microsoft に、ビジネスの Skype からアップグレードの環境を準備します。
author: turgayo
ms.author: turgayo
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: チームにビジネス用の Skype からのアップグレードを開始する前に、環境とネットワークの対応を検証します。
localization_priority: Priority
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: b9c99a0f6192d611d1b7dad115bdef5a0c489f46
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23858276"
---
<span data-ttu-id="2105b-103">![技術的な準備段階に重点を置いて、旅アップグレードの段階](media/upgrade-banner-tech-readiness.png "技術的な準備段階に重点を置いて、旅アップグレードの段階")</span><span class="sxs-lookup"><span data-stu-id="2105b-103">![Stages of the upgrade journey, with emphasis on the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="2105b-104">この資料は、ユーザーの準備段階と並行して、完了したアクティビティ、アップグレード、旅の技術的な準備段階の一部です。</span><span class="sxs-lookup"><span data-stu-id="2105b-104">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="2105b-105">次に進む前に前の段階からこれらの活動を完了していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2105b-105">Before proceeding, confirm that you’ve completed these activities from previous stages:</span></span>

-   [<span data-ttu-id="2105b-106">プロジェクトの利害関係者が参加しています。</span><span class="sxs-lookup"><span data-stu-id="2105b-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
-   [<span data-ttu-id="2105b-107">プロジェクト スコープの定義</span><span class="sxs-lookup"><span data-stu-id="2105b-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
-   [<span data-ttu-id="2105b-108">ビジネスとチームの共存と Skype の相互運用性を理解します。</span><span class="sxs-lookup"><span data-stu-id="2105b-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
-   [<span data-ttu-id="2105b-109">アップグレード、旅を選択</span><span class="sxs-lookup"><span data-stu-id="2105b-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

# <a name="prepare-your-environment-for-upgrading-to-teams"></a><span data-ttu-id="2105b-110">チームへのアップグレードの環境を準備します。</span><span class="sxs-lookup"><span data-stu-id="2105b-110">Prepare your environment for upgrading to Teams</span></span>

<span data-ttu-id="2105b-111">ドライブ、組織内のチームのアップグレードが正常に実行するには、ビジネス環境や、ネットワーク対応の現在の Skype を検証することが重要です。</span><span class="sxs-lookup"><span data-stu-id="2105b-111">To drive a successful Teams upgrade in your organization, it’s important that you validate your current Skype for Business environment and your network readiness.</span></span> <span data-ttu-id="2105b-112">現在の環境を準備するは、高品質のユーザー エクスペリエンスを今すぐことを確認して、チームで発生するだけでなく、ユーザーの質の向上に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2105b-112">Preparing your current environment will help ensure a high-quality user experience now, in addition to improving the quality of the user experience in Teams.</span></span> <span data-ttu-id="2105b-113">展開を促進し、任意の重要なアクション アイテムをスキップしていないことを確認にかかる時間が個々 のステップを計画することができます。</span><span class="sxs-lookup"><span data-stu-id="2105b-113">Taking time to plan individual steps can help accelerate your deployment and ensure that you haven’t skipped any important action items.</span></span>

<span data-ttu-id="2105b-114">ユーザーの準備の準備と並行して、これらのアクティビティを完了します。</span><span class="sxs-lookup"><span data-stu-id="2105b-114">Complete these activities in parallel with your user readiness preparation:</span></span>

-   <span data-ttu-id="2105b-115">正常なアップグレードの旅に必要なものがあるように、[お客様の IT スタッフの準備](upgrade-prepare-IT-pros.md)をします。</span><span class="sxs-lookup"><span data-stu-id="2105b-115">[Prepare your IT staff](upgrade-prepare-IT-pros.md) to help ensure they have what they need for a successful upgrade journey.</span></span>
-   <span data-ttu-id="2105b-116">環境がすべて[の前提条件](upgrade-plan-journey-prerequisites.md)を満たしていることを確認し、Office 365 のサービスおよびチーム間の依存関係を理解します。</span><span class="sxs-lookup"><span data-stu-id="2105b-116">Verify that your environment meets all [prerequisites](upgrade-plan-journey-prerequisites.md), and understand dependencies among Office 365 services and Teams.</span></span>
-   <span data-ttu-id="2105b-117">チームに正常なアップグレードの旅に着手するときに、組織の準備を確認するのにはサンプルのアンケートを使用して、環境の検出を実行することにより[、環境の評価](upgrade-plan-journey-evaluate-environment.md)を。</span><span class="sxs-lookup"><span data-stu-id="2105b-117">[Evaluate your environment](upgrade-plan-journey-evaluate-environment.md) by performing environmental discovery by using a sample questionnaire to confirm your organization’s readiness to undertake a successful upgrade journey to Teams.</span></span>
-   <span data-ttu-id="2105b-118">計画、準備、およびネットワークの改善のために必要な手順に従うことによって[、ネットワークの準備](upgrade-prepare-environment-prepare-network.md)のチームの作業負荷をサポートするために。</span><span class="sxs-lookup"><span data-stu-id="2105b-118">[Prepare your network](upgrade-prepare-environment-prepare-network.md) through planning, preparation, and taking any necessary remediation steps for your network to support Teams workloads.</span></span>
-   <span data-ttu-id="2105b-119">[準備サービス](upgrade-prepare-environment-prepare-service.md)、チーム構成がチームにビジネス用の Skype のユーザーの移行をサポートするために準備ができていることを確認するのには契約時のチェックリストを使用して展開します。</span><span class="sxs-lookup"><span data-stu-id="2105b-119">[Prepare your service](upgrade-prepare-environment-prepare-service.md) for rollout by using onboarding checklists to ensure that your Teams configuration is ready to support migrating your users from Skype for Business to Teams.</span></span>