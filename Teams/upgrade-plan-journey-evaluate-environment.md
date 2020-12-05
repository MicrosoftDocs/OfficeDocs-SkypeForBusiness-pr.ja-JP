---
title: Teams にアップグレードする前に環境を評価する
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: チームにアップグレードするために現在の環境を適切に評価するための要件について説明します。
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
ms.openlocfilehash: c783934128e2c1d3f971948c41e3481839ff0aa1
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578240"
---
# <a name="evaluate-your-environment-before-upgrading-to-teams"></a><span data-ttu-id="ffdf9-103">Teams にアップグレードする前に環境を評価する</span><span class="sxs-lookup"><span data-stu-id="ffdf9-103">Evaluate your environment before upgrading to Teams</span></span>

<span data-ttu-id="ffdf9-104">![技術準備段階が協調表示されたアップグレード行程図](media/upgrade-banner-tech-readiness.png "技術準備段階が強調表示された、アップグレード行程の各段階")</span><span class="sxs-lookup"><span data-stu-id="ffdf9-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="ffdf9-105">この記事は、ユーザーの準備段階と並行して実行されるアクティビティである、アップグレードが行われる技術準備段階の一部です。</span><span class="sxs-lookup"><span data-stu-id="ffdf9-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="ffdf9-106">続行する前に、以前のステージでこれらのアクティビティが完了していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ffdf9-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="ffdf9-107">プロジェクトの関係者をリスト化した</span><span class="sxs-lookup"><span data-stu-id="ffdf9-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="ffdf9-108">プロジェクトの対象範囲を定義した</span><span class="sxs-lookup"><span data-stu-id="ffdf9-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="ffdf9-109">Skype for Business と Teams の共存と相互運用を理解した</span><span class="sxs-lookup"><span data-stu-id="ffdf9-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="ffdf9-110">アップグレードの手順を選択した</span><span class="sxs-lookup"><span data-stu-id="ffdf9-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="ffdf9-111">この記事では、オペレーティングチーム向けに現在の環境を適切に評価するための要件の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="ffdf9-111">This article gives an overview of the requirements for properly evaluating your current environment for operating Teams.</span></span> <span data-ttu-id="ffdf9-112">環境を評価することで、全体的な展開に影響を与えるリスクと要件を特定することができます。</span><span class="sxs-lookup"><span data-stu-id="ffdf9-112">By evaluating your environment, you identify risks and requirements that will influence your overall deployment.</span></span> <span data-ttu-id="ffdf9-113">これらの項目を事前に特定することで、計画を調整して成功を収めることができます。</span><span class="sxs-lookup"><span data-stu-id="ffdf9-113">By identifying these items beforehand, you can adjust your planning to drive success.</span></span>

## <a name="introduction-to-the-discovery-questionnaire"></a><span data-ttu-id="ffdf9-114">探索アンケートの概要</span><span class="sxs-lookup"><span data-stu-id="ffdf9-114">Introduction to the Discovery Questionnaire</span></span>

<span data-ttu-id="ffdf9-115">目標のキーの結果 (OKRs) を実現するには、以前に主要サービスの決定を行いました。</span><span class="sxs-lookup"><span data-stu-id="ffdf9-115">To achieve your objective key results (OKRs), you previously made key service decisions.</span></span> <span data-ttu-id="ffdf9-116">次の手順では、環境の検出を実行して、組織がソリューションを実装する準備ができていることを確認するために、IT インフラストラクチャ、ネットワーク、操作に関するすべての側面を評価します。</span><span class="sxs-lookup"><span data-stu-id="ffdf9-116">The next step is to perform environmental discovery to evaluate all aspects relating to your IT infrastructure, networking, and operations to confirm that your organization is ready to implement the solution.</span></span> <span data-ttu-id="ffdf9-117">探索は、チームへの旅を計画するときに実行する主要な手順の1つです。</span><span class="sxs-lookup"><span data-stu-id="ffdf9-117">Discovery is one of the very first, key steps that you take when planning for your journey to Teams.</span></span> <span data-ttu-id="ffdf9-118">ネットワークが Teams へのアップグレードをサポートできるように、環境の検出にはネットワーク準備評価が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ffdf9-118">Environmental discovery must include a network readiness assessment to ensure your network can support upgrading to Teams.</span></span> <span data-ttu-id="ffdf9-119">環境の詳細な検出を行って、現在の状態の理解を深め、問題が発生した場合や、チームのロールアウトの実行に発生する可能性が高いブロックを明らかにすることができます。</span><span class="sxs-lookup"><span data-stu-id="ffdf9-119">You perform a detailed discovery of your environment to better understand its current state and to reveal any difficulties or—even more important—possible blockers to the execution of your Teams rollout.</span></span>

<span data-ttu-id="ffdf9-120">技術的なリスクは、環境の評価と導入の準備評価の一部として特定し、特定された各リスクの軽減計画を作成します。</span><span class="sxs-lookup"><span data-stu-id="ffdf9-120">You identify technical risks as part of an environmental assessment and adoption readiness evaluation, and develop a mitigation plan for each identified risk.</span></span> <span data-ttu-id="ffdf9-121">この情報は、リスク登録に組み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="ffdf9-121">You should incorporate this information in the risk register.</span></span>

<span data-ttu-id="ffdf9-122">既存のコラボレーションインフラストラクチャと、Microsoft 365 または Office 365 の組織、ネットワーキング、エンドポイント、操作、導入と準備に関連するすべての事項は、環境検出アンケートの一部として含まれています。</span><span class="sxs-lookup"><span data-stu-id="ffdf9-122">All matters related to your existing collaboration infrastructure and Microsoft 365 or Office 365 organization, networking, endpoints, operations, and adoption and readiness are included as part of the environmental discovery questionnaire.</span></span> <span data-ttu-id="ffdf9-123">プロジェクトチームと協力して、要求された情報をできるだけ詳しく入力して、計画作業を容易にします。</span><span class="sxs-lookup"><span data-stu-id="ffdf9-123">Work with your project team to provide the requested information with as much detail as possible to facilitate your planning activities.</span></span>

<span data-ttu-id="ffdf9-124">[アンケート](upgrade-plan-journey-discovery-questionnaire.md) は、次のセクションに分かれており、組織のチーム展開に対する準備が、次のいくつかの主要領域で確認されます。</span><span class="sxs-lookup"><span data-stu-id="ffdf9-124">[The questionnaire](upgrade-plan-journey-discovery-questionnaire.md) is divided into the following sections to confirm your organization's readiness for your Teams deployment in several major areas:</span></span>

- <span data-ttu-id="ffdf9-125">Microsoft 365 または Office 365 組織の詳細</span><span class="sxs-lookup"><span data-stu-id="ffdf9-125">Microsoft 365 or Office 365 organization details</span></span>
- <span data-ttu-id="ffdf9-126">既存のコラボレーションプラットフォームの概要</span><span class="sxs-lookup"><span data-stu-id="ffdf9-126">Existing collaboration platform summary</span></span>
- <span data-ttu-id="ffdf9-127">コラボレーションプラットフォームの展開の詳細</span><span class="sxs-lookup"><span data-stu-id="ffdf9-127">Collaboration platform deployment details</span></span>
- <span data-ttu-id="ffdf9-128">Microsoft 365 または Office 365 サービスへのネットワークとアクセス</span><span class="sxs-lookup"><span data-stu-id="ffdf9-128">Networking and access to Microsoft 365 or Office 365 services</span></span>
- <span data-ttu-id="ffdf9-129">エンドポイント</span><span class="sxs-lookup"><span data-stu-id="ffdf9-129">Endpoints</span></span>
- <span data-ttu-id="ffdf9-130">操作</span><span class="sxs-lookup"><span data-stu-id="ffdf9-130">Operations</span></span>
- <span data-ttu-id="ffdf9-131">導入と準備</span><span class="sxs-lookup"><span data-stu-id="ffdf9-131">Adoption and readiness</span></span>

> [!TIP]
> <span data-ttu-id="ffdf9-132">最初に、アンケートを Microsoft Word 文書にコピーすることができます。</span><span class="sxs-lookup"><span data-stu-id="ffdf9-132">You can start by copying the questionnaire into a Microsoft Word document.</span></span> <span data-ttu-id="ffdf9-133">すべての質問に答えて、移動の際にすべての詳細情報を把握してみてください。</span><span class="sxs-lookup"><span data-stu-id="ffdf9-133">Try to answer all questions and capture all details as you move through.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/><span data-ttu-id="ffdf9-134">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="ffdf9-134">Decision point</span></span></td><td><ul><li><span data-ttu-id="ffdf9-135">環境評価の完了責任者は誰ですか?</span><span class="sxs-lookup"><span data-stu-id="ffdf9-135">Who will be responsible for completing an environment assessment?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/><span data-ttu-id="ffdf9-136">次の手順</span><span class="sxs-lookup"><span data-stu-id="ffdf9-136">Next step</span></span></td><td><ul><li><span data-ttu-id="ffdf9-137">環境評価の結果を文書化します。</span><span class="sxs-lookup"><span data-stu-id="ffdf9-137">Document the results of the environment assessment.</span></span></li></ul></td></tr>
</table>


## <a name="project-team"></a><span data-ttu-id="ffdf9-138">プロジェクトチーム</span><span class="sxs-lookup"><span data-stu-id="ffdf9-138">Project team</span></span>

<span data-ttu-id="ffdf9-139">プロジェクトチームに適切なユーザーが参加していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ffdf9-139">Ensure that you've engaged the right people for your project team.</span></span> <span data-ttu-id="ffdf9-140">手順が完了したことを確認して、 [プロジェクトの関係者を登録](upgrade-enlist-stakeholders.md)します。</span><span class="sxs-lookup"><span data-stu-id="ffdf9-140">Verify the steps you completed in [Enlist your project stakeholders](upgrade-enlist-stakeholders.md).</span></span>

<span data-ttu-id="ffdf9-141">環境の評価が完了したら、次の手順「 [サービスを準備](upgrade-prepare-environment-prepare-service.md)する」に進みます。</span><span class="sxs-lookup"><span data-stu-id="ffdf9-141">After you evaluate your environment, proceed to the next step: [Prepare your service](upgrade-prepare-environment-prepare-service.md).</span></span>
