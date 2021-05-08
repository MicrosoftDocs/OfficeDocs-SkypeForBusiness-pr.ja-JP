---
title: アプリケーションにアップグレードする前に環境を評価Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: アプリケーションにアップグレードするための現在の環境を適切に評価するための要件Teams。
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
ms.openlocfilehash: aeb236edddea69c1c112b695c9323de19da46092
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282204"
---
# <a name="evaluate-your-environment-before-upgrading-to-teams"></a><span data-ttu-id="5fd4d-103">アプリケーションにアップグレードする前に環境を評価Teams</span><span class="sxs-lookup"><span data-stu-id="5fd4d-103">Evaluate your environment before upgrading to Teams</span></span>

<span data-ttu-id="5fd4d-104">![技術準備段階が協調表示されたアップグレード行程図](media/upgrade-banner-tech-readiness.png "技術準備段階が強調表示された、アップグレード行程の各段階")</span><span class="sxs-lookup"><span data-stu-id="5fd4d-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="5fd4d-105">この記事は、ユーザーの準備段階と並行して実行されるアクティビティである、アップグレードが行われる技術準備段階の一部です。</span><span class="sxs-lookup"><span data-stu-id="5fd4d-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="5fd4d-106">先に進む前に、前のステージからこれらのアクティビティを完了してください。</span><span class="sxs-lookup"><span data-stu-id="5fd4d-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="5fd4d-107">プロジェクトの関係者をリスト化した</span><span class="sxs-lookup"><span data-stu-id="5fd4d-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="5fd4d-108">プロジェクトの対象範囲を定義した</span><span class="sxs-lookup"><span data-stu-id="5fd4d-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="5fd4d-109">Skype for Business と Teams の共存と相互運用を理解した</span><span class="sxs-lookup"><span data-stu-id="5fd4d-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="5fd4d-110">アップグレードの手順を選択した</span><span class="sxs-lookup"><span data-stu-id="5fd4d-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="5fd4d-111">この記事では、現在の環境を適切に評価するための要件の概要を説明し、Teams。</span><span class="sxs-lookup"><span data-stu-id="5fd4d-111">This article gives an overview of the requirements for properly evaluating your current environment for operating Teams.</span></span> <span data-ttu-id="5fd4d-112">環境を評価することで、全体的なデプロイに影響を与えるリスクと要件を特定します。</span><span class="sxs-lookup"><span data-stu-id="5fd4d-112">By evaluating your environment, you identify risks and requirements that will influence your overall deployment.</span></span> <span data-ttu-id="5fd4d-113">これらの項目を事前に特定することで、成功を引き出す計画を調整できます。</span><span class="sxs-lookup"><span data-stu-id="5fd4d-113">By identifying these items beforehand, you can adjust your planning to drive success.</span></span>

## <a name="introduction-to-the-discovery-questionnaire"></a><span data-ttu-id="5fd4d-114">検出アンケートの概要</span><span class="sxs-lookup"><span data-stu-id="5fd4d-114">Introduction to the Discovery Questionnaire</span></span>

<span data-ttu-id="5fd4d-115">目標となる主要な結果 (OKRs) を達成するために、以前に主要なサービスの決定を行いました。</span><span class="sxs-lookup"><span data-stu-id="5fd4d-115">To achieve your objective key results (OKRs), you previously made key service decisions.</span></span> <span data-ttu-id="5fd4d-116">次の手順では、環境検出を実行して、IT インフラストラクチャ、ネットワーク、運用に関連するすべての側面を評価し、組織がソリューションを実装する準備ができていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5fd4d-116">The next step is to perform environmental discovery to evaluate all aspects relating to your IT infrastructure, networking, and operations to confirm that your organization is ready to implement the solution.</span></span> <span data-ttu-id="5fd4d-117">検出は、データの検出を計画するときに実行する最初の重要な手順の 1 Teams。</span><span class="sxs-lookup"><span data-stu-id="5fd4d-117">Discovery is one of the very first, key steps that you take when planning for your journey to Teams.</span></span> <span data-ttu-id="5fd4d-118">環境検出には、ネットワークがネットワークへのアップグレードをサポートできるよう、ネットワークの準備評価を含めるTeams。</span><span class="sxs-lookup"><span data-stu-id="5fd4d-118">Environmental discovery must include a network readiness assessment to ensure your network can support upgrading to Teams.</span></span> <span data-ttu-id="5fd4d-119">環境の詳細な検出を実行して、現在の状態をよりよく理解し、問題や、さらに重要な、Teams ロールアウトの実行をブロックする可能性を明らかにします。</span><span class="sxs-lookup"><span data-stu-id="5fd4d-119">You perform a detailed discovery of your environment to better understand its current state and to reveal any difficulties or—even more important—possible blockers to the execution of your Teams rollout.</span></span>

<span data-ttu-id="5fd4d-120">環境評価と導入準備評価の一環として技術的なリスクを特定し、特定されたリスクごとに軽減計画を策定します。</span><span class="sxs-lookup"><span data-stu-id="5fd4d-120">You identify technical risks as part of an environmental assessment and adoption readiness evaluation, and develop a mitigation plan for each identified risk.</span></span> <span data-ttu-id="5fd4d-121">この情報は、リスク レジスタに組み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fd4d-121">You should incorporate this information in the risk register.</span></span>

<span data-ttu-id="5fd4d-122">既存のコラボレーション インフラストラクチャと Microsoft 365 または Office 365 組織、ネットワーク、エンドポイント、運用、導入と準備に関する事項はすべて、環境検出アンケートの一部として含まれています。</span><span class="sxs-lookup"><span data-stu-id="5fd4d-122">All matters related to your existing collaboration infrastructure and Microsoft 365 or Office 365 organization, networking, endpoints, operations, and adoption and readiness are included as part of the environmental discovery questionnaire.</span></span> <span data-ttu-id="5fd4d-123">プロジェクト チームと一緒に、計画作業を容易にするために、必要な情報を可能な限り詳細に提供します。</span><span class="sxs-lookup"><span data-stu-id="5fd4d-123">Work with your project team to provide the requested information with as much detail as possible to facilitate your planning activities.</span></span>

<span data-ttu-id="5fd4d-124">[アンケートは](upgrade-plan-journey-discovery-questionnaire.md)次のセクションに分かれ、組織が複数の主要な領域に展開Teams準備を確認します。</span><span class="sxs-lookup"><span data-stu-id="5fd4d-124">[The questionnaire](upgrade-plan-journey-discovery-questionnaire.md) is divided into the following sections to confirm your organization's readiness for your Teams deployment in several major areas:</span></span>

- <span data-ttu-id="5fd4d-125">Microsoft 365またはOffice 365の詳細</span><span class="sxs-lookup"><span data-stu-id="5fd4d-125">Microsoft 365 or Office 365 organization details</span></span>
- <span data-ttu-id="5fd4d-126">既存のコラボレーション プラットフォームの概要</span><span class="sxs-lookup"><span data-stu-id="5fd4d-126">Existing collaboration platform summary</span></span>
- <span data-ttu-id="5fd4d-127">コラボレーション プラットフォームのデプロイの詳細</span><span class="sxs-lookup"><span data-stu-id="5fd4d-127">Collaboration platform deployment details</span></span>
- <span data-ttu-id="5fd4d-128">ネットワークとサービスMicrosoft 365またはOffice 365アクセス</span><span class="sxs-lookup"><span data-stu-id="5fd4d-128">Networking and access to Microsoft 365 or Office 365 services</span></span>
- <span data-ttu-id="5fd4d-129">エンドポイント</span><span class="sxs-lookup"><span data-stu-id="5fd4d-129">Endpoints</span></span>
- <span data-ttu-id="5fd4d-130">操作</span><span class="sxs-lookup"><span data-stu-id="5fd4d-130">Operations</span></span>
- <span data-ttu-id="5fd4d-131">導入と準備</span><span class="sxs-lookup"><span data-stu-id="5fd4d-131">Adoption and readiness</span></span>

> [!TIP]
> <span data-ttu-id="5fd4d-132">最初に、アンケートを別のドキュメントにMicrosoft Wordできます。</span><span class="sxs-lookup"><span data-stu-id="5fd4d-132">You can start by copying the questionnaire into a Microsoft Word document.</span></span> <span data-ttu-id="5fd4d-133">すべての質問に回答し、移動中にすべての詳細をキャプチャしてみてください。</span><span class="sxs-lookup"><span data-stu-id="5fd4d-133">Try to answer all questions and capture all details as you move through.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/><span data-ttu-id="5fd4d-134">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="5fd4d-134">Decision point</span></span></td><td><ul><li><span data-ttu-id="5fd4d-135">Who評価を完了する責任は何ですか?</span><span class="sxs-lookup"><span data-stu-id="5fd4d-135">Who will be responsible for completing an environment assessment?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/><span data-ttu-id="5fd4d-136">次の手順</span><span class="sxs-lookup"><span data-stu-id="5fd4d-136">Next step</span></span></td><td><ul><li><span data-ttu-id="5fd4d-137">環境評価の結果を文書化します。</span><span class="sxs-lookup"><span data-stu-id="5fd4d-137">Document the results of the environment assessment.</span></span></li></ul></td></tr>
</table>


## <a name="project-team"></a><span data-ttu-id="5fd4d-138">Project チーム</span><span class="sxs-lookup"><span data-stu-id="5fd4d-138">Project team</span></span>

<span data-ttu-id="5fd4d-139">プロジェクト チームに適切な人と関わり合ったことを確認します。</span><span class="sxs-lookup"><span data-stu-id="5fd4d-139">Ensure that you've engaged the right people for your project team.</span></span> <span data-ttu-id="5fd4d-140">「プロジェクト関係者を参加する [」で完了した手順を確認します](upgrade-enlist-stakeholders.md)。</span><span class="sxs-lookup"><span data-stu-id="5fd4d-140">Verify the steps you completed in [Enlist your project stakeholders](upgrade-enlist-stakeholders.md).</span></span>

<span data-ttu-id="5fd4d-141">環境を評価した後、次の手順「サービスを準備 [する」に進みます](upgrade-prepare-environment-prepare-service.md)。</span><span class="sxs-lookup"><span data-stu-id="5fd4d-141">After you evaluate your environment, proceed to the next step: [Prepare your service](upgrade-prepare-environment-prepare-service.md).</span></span>