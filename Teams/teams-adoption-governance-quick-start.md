---
title: Microsoft Teams のガバナンスのクイック スタート
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 10/29/2018
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: karuanag
localization_priority: Normal
search.appverid: MET150
description: 導入計画のフェーズ 2 の主な意思決定を行う
ms.custom: Adopt
MS.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ecf91ea9a06b3984b65954617fe5690658015e52
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33896333"
---
# <a name="governance-quick-start-for-microsoft-teams"></a><span data-ttu-id="e38ca-103">Microsoft Teams のガバナンスのクイック スタート</span><span class="sxs-lookup"><span data-stu-id="e38ca-103">Governance quick start for Microsoft Teams</span></span>

<span data-ttu-id="e38ca-104">次のアクティビティは、同時に行われます。また、主要なチームのすべてまたは一部が関係する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e38ca-104">The following activities will happen simultaneously, and they may involve all or part of your key team.</span></span> <span data-ttu-id="e38ca-105">ベスト プラクティスとして、Teams で初期の実験が完了した後に、の大規模なガバナンスとセキュリティの会話を保留します。</span><span class="sxs-lookup"><span data-stu-id="e38ca-105">As a best practice, defer large-scale governance and security conversations for after you have completed your initial experimentation with Teams.</span></span> <span data-ttu-id="e38ca-106">これにより、後日に行う決定が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="e38ca-106">This will simplify the decisions you will need to make at that later date.</span></span> <span data-ttu-id="e38ca-107">このフェーズでは、いくつかの決定を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e38ca-107">For this phase there are some decisions that need to be made.</span></span> <span data-ttu-id="e38ca-108">これらを成功させるには、まず次の質問に答える必要があります。</span><span class="sxs-lookup"><span data-stu-id="e38ca-108">To successfully make them you will first need to answer the following questions:</span></span>

- <span data-ttu-id="e38ca-109">以前の評価から、この限定されたビジネスのオンボードに参加するのに適している関係者は誰ですか?</span><span class="sxs-lookup"><span data-stu-id="e38ca-109">Which stakeholder from your earlier assessment is a good candidate to participate in this limited business onboarding?</span></span>
- <span data-ttu-id="e38ca-110">この個人 (または個人グループ) は、このフェーズに適したユース ケースを提案しましたか?</span><span class="sxs-lookup"><span data-stu-id="e38ca-110">Has this individual (or group of individuals) suggested use cases that would be good candidates for this phase?</span></span>  
- <span data-ttu-id="e38ca-111">彼らは、組織内の従業員から早期導入者になり、有意義で定期的なフィードバックを提供するのに十分な関心を持っていますか?</span><span class="sxs-lookup"><span data-stu-id="e38ca-111">Do they have enough interest from employees in their organization to be early adopters and give you meaningful and regular feedback?</span></span> 

## <a name="decision-point-iconmediateams-adoption-decision-iconpngdecisions"></a>![判断ポイント アイコン。](media/teams-adoption-decision-icon.png)<span data-ttu-id="e38ca-113">決定事項</span><span class="sxs-lookup"><span data-stu-id="e38ca-113">Decisions</span></span>

<span data-ttu-id="e38ca-114">次の決定を行います (この時点で、これらの決定はフェーズ 2 にのみ適用されます)。</span><span class="sxs-lookup"><span data-stu-id="e38ca-114">Make the following decisions (at this point, these decisions apply only to Phase 2):</span></span>

### <a name="decision-1-who-can-create-teams"></a><span data-ttu-id="e38ca-115">決定 1: チームを作成できるユーザー</span><span class="sxs-lookup"><span data-stu-id="e38ca-115">Decision 1: Who can create teams</span></span> 

<span data-ttu-id="e38ca-116">このフェーズの目的のために、チームを作成できるユーザーを、コア プロジェクト チームに加えて、早期導入者の母集団に制限することができます。</span><span class="sxs-lookup"><span data-stu-id="e38ca-116">For the purposes of this phase you can restrict who is able to create teams to the early adopter population in addition to your core project team.</span></span> <span data-ttu-id="e38ca-117">これにより、早期導入者が必要に応じて追加のチームを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="e38ca-117">This will allow your early adopters to create additional teams if needed.</span></span> <span data-ttu-id="e38ca-118">この動作を監視することにより、幅広い展開に関する重要な情報を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="e38ca-118">Monitoring this behavior will give you key information for your broad deployment.</span></span>

### <a name="decision-2-teams-naming-conventions"></a><span data-ttu-id="e38ca-119">決定 2: チームの名前付け規則</span><span class="sxs-lookup"><span data-stu-id="e38ca-119">Decision 2: Teams naming conventions</span></span> 

<span data-ttu-id="e38ca-120">Teams の幅広い展開のために、名前付け規則を実装し、重複する名前がないか確認したいかもしれません。</span><span class="sxs-lookup"><span data-stu-id="e38ca-120">You will likely want to implement some naming conventions for your broad deployment of Teams, and check for duplicate names.</span></span> <span data-ttu-id="e38ca-121">フェーズ 2 では、最初のプロジェクトに対してのみ、手動の名前付け規則を実装することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e38ca-121">In Phase 2 we suggest that you implement a manual naming convention for your initial projects only.</span></span> <span data-ttu-id="e38ca-122">このためのベストプラクティスは、早期導入者のプロジェクトチームとの対話型オンボードを実施し、彼らが自分の名前を選択できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="e38ca-122">The best practice for this is to conduct an interactive onboarding with the early adopter project team and allow them to select their own name.</span></span> <span data-ttu-id="e38ca-123">これにより、従業員が自分の職場をどのように考えるかを分析でき、後でより大規模な名前付け規則を作成する際に重要になります。</span><span class="sxs-lookup"><span data-stu-id="e38ca-123">This will give you insight into how employees think about their work and will be essential in creating a larger scale naming convention at a later time.</span></span> <span data-ttu-id="e38ca-124">(対話型オンボードの要素に関する追加情報は、このガイドの後半に表示されます。)</span><span class="sxs-lookup"><span data-stu-id="e38ca-124">(Additional information on the elements of an interactive onboarding will appear later in this guide.)</span></span>

### <a name="decision-3-guest-access"></a><span data-ttu-id="e38ca-125">決定 3: ゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="e38ca-125">Decision 3: Guest access</span></span>

<span data-ttu-id="e38ca-126">プロジェクトの範囲と種類、および業界の性質によっては、パートナーやベンダーとの保護された共同作業の有効化は、テストしたい重要な機能となる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e38ca-126">Depending on the scope and type of your project and the nature of your industry, enabling secure collaboration with partners or vendors may be an essential capability you want to test.</span></span> <span data-ttu-id="e38ca-127">適切なテナントの制御を使用して、ゲストを Teams の実装に追加できるユーザーを制限できます。</span><span class="sxs-lookup"><span data-stu-id="e38ca-127">You can limit who can add guests to your Teams implementation by using the appropriate tenant controls.</span></span> 

### <a name="decision-4-approved-apps"></a><span data-ttu-id="e38ca-128">判断 4: 承認済みアプリ</span><span class="sxs-lookup"><span data-stu-id="e38ca-128">Decision 4: Approved apps</span></span>

<span data-ttu-id="e38ca-129">Teams の最良の使用例には、他のアプリをエクスペリエンスに統合することが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e38ca-129">The best case use of Teams includes the integration of other apps into the experience.</span></span> <span data-ttu-id="e38ca-130">少なくとも、技術チームは、Teams のエクスペリエンスにおいて最初のパーティとおすすめのアプリを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e38ca-130">At a minimum your technical team should enable the first party and featured apps in your Teams experience.</span></span> <span data-ttu-id="e38ca-131">使用例や組織で使用されている他のアプリによっては、制御された実験の一環として、追加のアプリを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e38ca-131">Depending on your use case and other apps used in your organization, you may opt to include additional apps as a part of your controlled experiment.</span></span> 

### <a name="decision-5-are-meetings-included-in-your-test"></a><span data-ttu-id="e38ca-132">決定 5: 会議はテストに含まれていますか?</span><span class="sxs-lookup"><span data-stu-id="e38ca-132">Decision 5: Are meetings included in your test?</span></span> 

<span data-ttu-id="e38ca-133">Teams 会議のエクスペリエンスは高品質で、ビデオ通話をサポートし、従業員の共同作業の効率を向上します。</span><span class="sxs-lookup"><span data-stu-id="e38ca-133">The Teams meeting experience is high quality, supports video chatting, and brings your employees together to be more effective.</span></span> <span data-ttu-id="e38ca-134">環境に簡単な VoIP 会議を含める準備ができているかどうかを、技術チームに問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="e38ca-134">Consult with your technical team to make sure that your environment is ready to include simple VoIP meetings.</span></span> <span data-ttu-id="e38ca-135">通常、電話会議や音声サービスの有効化は、実験のこのフェーズから除外します。ただし、これは、組織のコア プロジェクト チーム、技術の準備状況、および組織内の他の音声/会議サービスの状態によります。</span><span class="sxs-lookup"><span data-stu-id="e38ca-135">Enabling audio conferencing or voice services would normally be excluded from this phase of your experimentation; however, that depends on your core project team, your technical readiness, and the state of other voice/meeting services in your organization.</span></span> <span data-ttu-id="e38ca-136">Teams の実装からより多くの価値を得るために、ビデオ通話や VoIP 会議を実験に含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e38ca-136">We recommend including video chats and VoIP meetings in your experimentation to gain more value from your Teams implementation.</span></span> 

### <a name="decision-6--data-security"></a><span data-ttu-id="e38ca-137">決定 6: データのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="e38ca-137">Decision 6:  Data security</span></span>

<span data-ttu-id="e38ca-138">幅広い展開の準備として、セキュリティ ラベルを使用して、環境内のチームの種類を分類することができます。</span><span class="sxs-lookup"><span data-stu-id="e38ca-138">In preparation for your broad deployment you may opt to use security labels to classify the types of teams in your environment.</span></span> <span data-ttu-id="e38ca-139">この実験では、「[Teams でのガバナンスを計画する](plan-teams-governance.md)」を参照して、Office 365 組織内の Teams データに基本的なアイテム保持ポリシーが設定されていることを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e38ca-139">For the purposes of this experiment we recommend that you refer to [Plan for Governance in Teams](plan-teams-governance.md) and ensure that a basic retention policy has been set on Teams data in your Office 365 organization.</span></span> <span data-ttu-id="e38ca-140">この作業を完了するには、Office 365 の管理者の権限が必要なため、技術チームとの調整が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e38ca-140">You may need to coordinate this work with your technical team because Office 365 administrator rights are required to complete this work.</span></span>

### <a name="decision-7-length-of-your-experiment"></a><span data-ttu-id="e38ca-141">決定 7: 実験の長さ</span><span class="sxs-lookup"><span data-stu-id="e38ca-141">Decision 7: Length of your experiment</span></span>

<span data-ttu-id="e38ca-142">Teamsの実装に成功すると、適切な勢い、フォーカス、学習を確保しながら正常なペースで進みます。</span><span class="sxs-lookup"><span data-stu-id="e38ca-142">A successful Teams implementation proceeds at a healthy pace to ensure appropriate momentum, focus, and learnings.</span></span> <span data-ttu-id="e38ca-143">早期導入者が十分なビジネスサイクルを実現できるように、プロジェクトのこのフェーズを 60 日間にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e38ca-143">We recommend that this phase of your project be 60 days in length to ensure that your early adopters complete sufficient business cycles.</span></span> <span data-ttu-id="e38ca-144">実験を長時間延長すると、変更プログラムが失敗するリスクが高まります。ただし、この時間は組織によって異なります。</span><span class="sxs-lookup"><span data-stu-id="e38ca-144">Extending experimentation for too lengthy a time increases the risk of a failed change program; however, this time will vary for every organization.</span></span>  

<span data-ttu-id="e38ca-145">![次のステップ アイコン](media/teams-adoption-next-icon.png) 次へ: [使用例を定義する](teams-adoption-define-usage-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="e38ca-145">![Next Steps icon](media/teams-adoption-next-icon.png) Next: [Define usage scenarios](teams-adoption-define-usage-scenarios.md)</span></span>
