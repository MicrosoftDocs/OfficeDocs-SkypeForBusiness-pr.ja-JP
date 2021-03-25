---
title: Teams にアップグレードする前に環境を評価する
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Teams にアップグレードするための現在の環境を適切に評価するための要件について説明します。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 119a80f5a25b4a2d8599df3df6a573a1f5554c1a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119106"
---
# <a name="evaluate-your-environment-before-upgrading-to-teams"></a><span data-ttu-id="e7b08-103">Teams にアップグレードする前に環境を評価する</span><span class="sxs-lookup"><span data-stu-id="e7b08-103">Evaluate your environment before upgrading to Teams</span></span>

<span data-ttu-id="e7b08-104">![技術準備段階が協調表示されたアップグレード行程図](media/upgrade-banner-tech-readiness.png "技術準備段階が強調表示された、アップグレード行程の各段階")</span><span class="sxs-lookup"><span data-stu-id="e7b08-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="e7b08-105">この記事は、ユーザーの準備段階と並行して実行されるアクティビティである、アップグレードが行われる技術準備段階の一部です。</span><span class="sxs-lookup"><span data-stu-id="e7b08-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="e7b08-106">次の手順に進む前に、前のステージからこれらのアクティビティを完了したと確認します。</span><span class="sxs-lookup"><span data-stu-id="e7b08-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="e7b08-107">プロジェクトの関係者をリスト化した</span><span class="sxs-lookup"><span data-stu-id="e7b08-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="e7b08-108">プロジェクトの対象範囲を定義した</span><span class="sxs-lookup"><span data-stu-id="e7b08-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="e7b08-109">Skype for Business と Teams の共存と相互運用を理解した</span><span class="sxs-lookup"><span data-stu-id="e7b08-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="e7b08-110">アップグレードの手順を選択した</span><span class="sxs-lookup"><span data-stu-id="e7b08-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="e7b08-111">この記事では、Teams を操作するための現在の環境を適切に評価するための要件の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="e7b08-111">This article gives an overview of the requirements for properly evaluating your current environment for operating Teams.</span></span> <span data-ttu-id="e7b08-112">環境を評価することで、全体的な展開に影響するリスクと要件を特定します。</span><span class="sxs-lookup"><span data-stu-id="e7b08-112">By evaluating your environment, you identify risks and requirements that will influence your overall deployment.</span></span> <span data-ttu-id="e7b08-113">これらの項目を事前に特定することで、計画を調整して成功を後で追い出します。</span><span class="sxs-lookup"><span data-stu-id="e7b08-113">By identifying these items beforehand, you can adjust your planning to drive success.</span></span>

## <a name="introduction-to-the-discovery-questionnaire"></a><span data-ttu-id="e7b08-114">探索アンケートの概要</span><span class="sxs-lookup"><span data-stu-id="e7b08-114">Introduction to the Discovery Questionnaire</span></span>

<span data-ttu-id="e7b08-115">目標キーの結果 (OKRs) を達成するために、以前に主要なサービス決定を行いました。</span><span class="sxs-lookup"><span data-stu-id="e7b08-115">To achieve your objective key results (OKRs), you previously made key service decisions.</span></span> <span data-ttu-id="e7b08-116">次の手順では、環境検出を実行して、IT インフラストラクチャ、ネットワーク、運用に関連するすべての側面を評価し、組織がソリューションを実装する準備ができていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e7b08-116">The next step is to perform environmental discovery to evaluate all aspects relating to your IT infrastructure, networking, and operations to confirm that your organization is ready to implement the solution.</span></span> <span data-ttu-id="e7b08-117">検出は、Teams への旅を計画する際に行う最初の重要な手順の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="e7b08-117">Discovery is one of the very first, key steps that you take when planning for your journey to Teams.</span></span> <span data-ttu-id="e7b08-118">環境検出には、ネットワークが Teams へのアップグレードをサポートするためにネットワークの準備評価を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7b08-118">Environmental discovery must include a network readiness assessment to ensure your network can support upgrading to Teams.</span></span> <span data-ttu-id="e7b08-119">環境の詳細な検出を実行して、現在の状態をよりよく理解し、問題を明らかにしたり、さらに重要なこととして、Teams のロールアウトの実行をブロックする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e7b08-119">You perform a detailed discovery of your environment to better understand its current state and to reveal any difficulties or—even more important—possible blockers to the execution of your Teams rollout.</span></span>

<span data-ttu-id="e7b08-120">環境評価と導入準備評価の一環として技術的なリスクを特定し、特定された各リスクの緩和計画を作成します。</span><span class="sxs-lookup"><span data-stu-id="e7b08-120">You identify technical risks as part of an environmental assessment and adoption readiness evaluation, and develop a mitigation plan for each identified risk.</span></span> <span data-ttu-id="e7b08-121">この情報は、リスク レジスタに組み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7b08-121">You should incorporate this information in the risk register.</span></span>

<span data-ttu-id="e7b08-122">既存のコラボレーション インフラストラクチャと Microsoft 365 または Office 365 組織、ネットワーク、エンドポイント、運用、導入と準備に関連する事項はすべて、環境調査アンケートの一部として含まれています。</span><span class="sxs-lookup"><span data-stu-id="e7b08-122">All matters related to your existing collaboration infrastructure and Microsoft 365 or Office 365 organization, networking, endpoints, operations, and adoption and readiness are included as part of the environmental discovery questionnaire.</span></span> <span data-ttu-id="e7b08-123">プロジェクト チームと一緒に、必要な情報を可能な限り詳細に提供し、計画作業を容易に行います。</span><span class="sxs-lookup"><span data-stu-id="e7b08-123">Work with your project team to provide the requested information with as much detail as possible to facilitate your planning activities.</span></span>

<span data-ttu-id="e7b08-124">[アンケートは](upgrade-plan-journey-discovery-questionnaire.md) 次のセクションに分かれ、いくつかの主要な領域での Teams 展開に対する組織の準備を確認します。</span><span class="sxs-lookup"><span data-stu-id="e7b08-124">[The questionnaire](upgrade-plan-journey-discovery-questionnaire.md) is divided into the following sections to confirm your organization's readiness for your Teams deployment in several major areas:</span></span>

- <span data-ttu-id="e7b08-125">Microsoft 365 または Office 365 組織の詳細</span><span class="sxs-lookup"><span data-stu-id="e7b08-125">Microsoft 365 or Office 365 organization details</span></span>
- <span data-ttu-id="e7b08-126">既存のコラボレーション プラットフォームの概要</span><span class="sxs-lookup"><span data-stu-id="e7b08-126">Existing collaboration platform summary</span></span>
- <span data-ttu-id="e7b08-127">コラボレーション プラットフォームの展開の詳細</span><span class="sxs-lookup"><span data-stu-id="e7b08-127">Collaboration platform deployment details</span></span>
- <span data-ttu-id="e7b08-128">Microsoft 365 または Office 365 サービスへのネットワークとアクセス</span><span class="sxs-lookup"><span data-stu-id="e7b08-128">Networking and access to Microsoft 365 or Office 365 services</span></span>
- <span data-ttu-id="e7b08-129">エンドポイント</span><span class="sxs-lookup"><span data-stu-id="e7b08-129">Endpoints</span></span>
- <span data-ttu-id="e7b08-130">操作</span><span class="sxs-lookup"><span data-stu-id="e7b08-130">Operations</span></span>
- <span data-ttu-id="e7b08-131">導入と準備</span><span class="sxs-lookup"><span data-stu-id="e7b08-131">Adoption and readiness</span></span>

> [!TIP]
> <span data-ttu-id="e7b08-132">最初に、質問票を Microsoft Word 文書にコピーします。</span><span class="sxs-lookup"><span data-stu-id="e7b08-132">You can start by copying the questionnaire into a Microsoft Word document.</span></span> <span data-ttu-id="e7b08-133">すべての質問に回答し、移動に合わせすべての詳細を取り込もうとします。</span><span class="sxs-lookup"><span data-stu-id="e7b08-133">Try to answer all questions and capture all details as you move through.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/><span data-ttu-id="e7b08-134">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="e7b08-134">Decision point</span></span></td><td><ul><li><span data-ttu-id="e7b08-135">環境の評価を完了する責任は誰ですか?</span><span class="sxs-lookup"><span data-stu-id="e7b08-135">Who will be responsible for completing an environment assessment?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/><span data-ttu-id="e7b08-136">次の手順</span><span class="sxs-lookup"><span data-stu-id="e7b08-136">Next step</span></span></td><td><ul><li><span data-ttu-id="e7b08-137">環境評価の結果を文書化します。</span><span class="sxs-lookup"><span data-stu-id="e7b08-137">Document the results of the environment assessment.</span></span></li></ul></td></tr>
</table>


## <a name="project-team"></a><span data-ttu-id="e7b08-138">プロジェクト チーム</span><span class="sxs-lookup"><span data-stu-id="e7b08-138">Project team</span></span>

<span data-ttu-id="e7b08-139">プロジェクト チームに適切なメンバーを関与したとします。</span><span class="sxs-lookup"><span data-stu-id="e7b08-139">Ensure that you've engaged the right people for your project team.</span></span> <span data-ttu-id="e7b08-140">「プロジェクト関係者を参加する」で [完了した手順を確認します](upgrade-enlist-stakeholders.md)。</span><span class="sxs-lookup"><span data-stu-id="e7b08-140">Verify the steps you completed in [Enlist your project stakeholders](upgrade-enlist-stakeholders.md).</span></span>

<span data-ttu-id="e7b08-141">環境を評価した後、次の手順に進みます。サービス [を準備します](upgrade-prepare-environment-prepare-service.md)。</span><span class="sxs-lookup"><span data-stu-id="e7b08-141">After you evaluate your environment, proceed to the next step: [Prepare your service](upgrade-prepare-environment-prepare-service.md).</span></span>