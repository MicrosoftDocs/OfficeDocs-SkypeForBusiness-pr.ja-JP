---
title: Teams にアップグレードする環境を準備する
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Skype for Business から Teams へのアップグレードを開始する前に、環境とネットワークの準備を検証します。
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
ms.openlocfilehash: f75d899f2b14915e265ce8d36c57daeaf0ce72d2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119056"
---
# <a name="prepare-your-environment-for-upgrading-to-teams"></a><span data-ttu-id="c2fab-103">Teams にアップグレードする環境を準備する</span><span class="sxs-lookup"><span data-stu-id="c2fab-103">Prepare your environment for upgrading to Teams</span></span>

<span data-ttu-id="c2fab-104">![技術準備段階が協調表示されたアップグレード行程図](media/upgrade-banner-tech-readiness.png "技術準備段階が強調表示された、アップグレード行程の各段階")</span><span class="sxs-lookup"><span data-stu-id="c2fab-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="c2fab-105">この記事は、ユーザーの準備段階と並行して実行されるアクティビティである、アップグレードが行われる技術準備段階の一部です。</span><span class="sxs-lookup"><span data-stu-id="c2fab-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="c2fab-106">次の手順に進む前に、前のステージからこれらのアクティビティを完了したと確認します。</span><span class="sxs-lookup"><span data-stu-id="c2fab-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="c2fab-107">プロジェクトの関係者をリスト化した</span><span class="sxs-lookup"><span data-stu-id="c2fab-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="c2fab-108">プロジェクトの対象範囲を定義した</span><span class="sxs-lookup"><span data-stu-id="c2fab-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="c2fab-109">Skype for Business と Teams の共存と相互運用を理解した</span><span class="sxs-lookup"><span data-stu-id="c2fab-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="c2fab-110">アップグレードの手順を選択した</span><span class="sxs-lookup"><span data-stu-id="c2fab-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="c2fab-111">組織内で Teams のアップグレードを成功に追い込むには、現在の Skype for Business 環境とネットワークの準備を検証することが重要です。</span><span class="sxs-lookup"><span data-stu-id="c2fab-111">To drive a successful Teams upgrade in your organization, it's important that you validate your current Skype for Business environment and your network readiness.</span></span> <span data-ttu-id="c2fab-112">現在の環境を準備すると、Teams でのユーザー エクスペリエンスの品質の向上に加えて、高品質のユーザー エクスペリエンスを今すぐ実現できます。</span><span class="sxs-lookup"><span data-stu-id="c2fab-112">Preparing your current environment will help ensure a high-quality user experience now, in addition to improving the quality of the user experience in Teams.</span></span> <span data-ttu-id="c2fab-113">個々の手順を計画する時間を取って、展開を加速し、重要なアクション アイテムをスキップされていないことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="c2fab-113">Taking time to plan individual steps can help accelerate your deployment and ensure that you haven't skipped any important action items.</span></span>

<span data-ttu-id="c2fab-114">ユーザーの準備と並行してこれらのアクティビティを完了します。</span><span class="sxs-lookup"><span data-stu-id="c2fab-114">Complete these activities in parallel with your user readiness preparation:</span></span>

- <span data-ttu-id="c2fab-115">[アップグレードを成功に](upgrade-prepare-IT-pros.md) 向けて必要な情報を確実に利用するために IT スタッフを準備します。</span><span class="sxs-lookup"><span data-stu-id="c2fab-115">[Prepare your IT staff](upgrade-prepare-IT-pros.md) to help ensure they have what they need for a successful upgrade journey.</span></span>
- <span data-ttu-id="c2fab-116">使用している環境がすべての前提条件を[](upgrade-plan-journey-prerequisites.md)満たしていることを確認し、Microsoft 365 または Office 365 サービスと Teams 間の依存関係を理解します。</span><span class="sxs-lookup"><span data-stu-id="c2fab-116">Verify that your environment meets all [prerequisites](upgrade-plan-journey-prerequisites.md), and understand dependencies among Microsoft 365 or Office 365 services and Teams.</span></span>
- <span data-ttu-id="c2fab-117">[サンプルアンケートを使用](upgrade-plan-journey-evaluate-environment.md) して環境検出を実行して環境を評価し、Teams へのアップグレードを成功に引き受ける組織の準備を確認します。</span><span class="sxs-lookup"><span data-stu-id="c2fab-117">[Evaluate your environment](upgrade-plan-journey-evaluate-environment.md) by performing environmental discovery by using a sample questionnaire to confirm your organization's readiness to undertake a successful upgrade journey to Teams.</span></span>
- <span data-ttu-id="c2fab-118">[Teams のワークロードを](prepare-network.md) サポートするために、ネットワークの計画、準備、およびネットワークに必要な修復手順を実行して、ネットワークを準備します。</span><span class="sxs-lookup"><span data-stu-id="c2fab-118">[Prepare your network](prepare-network.md) through planning, preparation, and taking any necessary remediation steps for your network to support Teams workloads.</span></span>
- <span data-ttu-id="c2fab-119">[オンボーディング チェックリストを](upgrade-prepare-environment-prepare-service.md) 使用して展開するサービスを準備し、Teams の構成が Skype for Business から Teams へのユーザーの移行をサポートする準備ができていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c2fab-119">[Prepare your service](upgrade-prepare-environment-prepare-service.md) for rollout by using onboarding checklists to ensure that your Teams configuration is ready to support migrating your users from Skype for Business to Teams.</span></span>