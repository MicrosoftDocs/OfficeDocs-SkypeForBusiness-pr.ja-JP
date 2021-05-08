---
title: アプリケーションにアップグレードする環境を準備Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: アップグレードを開始する前に、環境とネットワークの準備Skype for BusinessをTeams。
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
ms.openlocfilehash: e154dc5844c4b8f3994c8c7bc00865c494a4c8c6
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282144"
---
# <a name="prepare-your-environment-for-upgrading-to-teams"></a><span data-ttu-id="5d99d-103">アプリケーションにアップグレードする環境を準備Teams</span><span class="sxs-lookup"><span data-stu-id="5d99d-103">Prepare your environment for upgrading to Teams</span></span>

<span data-ttu-id="5d99d-104">![技術準備段階が協調表示されたアップグレード行程図](media/upgrade-banner-tech-readiness.png "技術準備段階が強調表示された、アップグレード行程の各段階")</span><span class="sxs-lookup"><span data-stu-id="5d99d-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="5d99d-105">この記事は、ユーザーの準備段階と並行して実行されるアクティビティである、アップグレードが行われる技術準備段階の一部です。</span><span class="sxs-lookup"><span data-stu-id="5d99d-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="5d99d-106">先に進む前に、前のステージからこれらのアクティビティを完了してください。</span><span class="sxs-lookup"><span data-stu-id="5d99d-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="5d99d-107">プロジェクトの関係者をリスト化した</span><span class="sxs-lookup"><span data-stu-id="5d99d-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="5d99d-108">プロジェクトの対象範囲を定義した</span><span class="sxs-lookup"><span data-stu-id="5d99d-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="5d99d-109">Skype for Business と Teams の共存と相互運用を理解した</span><span class="sxs-lookup"><span data-stu-id="5d99d-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="5d99d-110">アップグレードの手順を選択した</span><span class="sxs-lookup"><span data-stu-id="5d99d-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="5d99d-111">組織でアップグレードをTeamsするには、現在の環境とネットワークの準備Skype for Business検証することが重要です。</span><span class="sxs-lookup"><span data-stu-id="5d99d-111">To drive a successful Teams upgrade in your organization, it's important that you validate your current Skype for Business environment and your network readiness.</span></span> <span data-ttu-id="5d99d-112">現在の環境を準備することで、ユーザー エクスペリエンスの品質を向上させるだけでなく、高品質のユーザー エクスペリエンスを今すぐTeams。</span><span class="sxs-lookup"><span data-stu-id="5d99d-112">Preparing your current environment will help ensure a high-quality user experience now, in addition to improving the quality of the user experience in Teams.</span></span> <span data-ttu-id="5d99d-113">個々の手順を計画する時間を取って、デプロイを加速し、重要なアクション項目をスキップしていないとします。</span><span class="sxs-lookup"><span data-stu-id="5d99d-113">Taking time to plan individual steps can help accelerate your deployment and ensure that you haven't skipped any important action items.</span></span>

<span data-ttu-id="5d99d-114">ユーザーの準備と並行してこれらのアクティビティを完了します。</span><span class="sxs-lookup"><span data-stu-id="5d99d-114">Complete these activities in parallel with your user readiness preparation:</span></span>

- <span data-ttu-id="5d99d-115">[アップグレードの成功に必要](upgrade-prepare-IT-pros.md) な情報を確実に得るのを支援するために、IT スタッフを準備します。</span><span class="sxs-lookup"><span data-stu-id="5d99d-115">[Prepare your IT staff](upgrade-prepare-IT-pros.md) to help ensure they have what they need for a successful upgrade journey.</span></span>
- <span data-ttu-id="5d99d-116">環境がすべての前提条件 を満[](upgrade-plan-journey-prerequisites.md)たしていることを確認し、サービスとサービス間の依存関係Microsoft 365またはOffice 365理解Teams。</span><span class="sxs-lookup"><span data-stu-id="5d99d-116">Verify that your environment meets all [prerequisites](upgrade-plan-journey-prerequisites.md), and understand dependencies among Microsoft 365 or Office 365 services and Teams.</span></span>
- <span data-ttu-id="5d99d-117">[サンプル アンケートを](upgrade-plan-journey-evaluate-environment.md)使用して環境の検出を実行して環境を評価し、組織がアップグレードを成功にTeams。</span><span class="sxs-lookup"><span data-stu-id="5d99d-117">[Evaluate your environment](upgrade-plan-journey-evaluate-environment.md) by performing environmental discovery by using a sample questionnaire to confirm your organization's readiness to undertake a successful upgrade journey to Teams.</span></span>
- <span data-ttu-id="5d99d-118">[ネットワークを計画、](prepare-network.md)準備、およびネットワークがワークロードに対応するために必要な修復手順を実行して、ネットワークTeamsします。</span><span class="sxs-lookup"><span data-stu-id="5d99d-118">[Prepare your network](prepare-network.md) through planning, preparation, and taking any necessary remediation steps for your network to support Teams workloads.</span></span>
- <span data-ttu-id="5d99d-119">[オンボーディング チェックリストを](upgrade-prepare-environment-prepare-service.md)使用してロールアウト用のサービスを準備し、Teams 構成でユーザーを Skype for Business から Teams への移行をサポートする準備が整います。</span><span class="sxs-lookup"><span data-stu-id="5d99d-119">[Prepare your service](upgrade-prepare-environment-prepare-service.md) for rollout by using onboarding checklists to ensure that your Teams configuration is ready to support migrating your users from Skype for Business to Teams.</span></span>