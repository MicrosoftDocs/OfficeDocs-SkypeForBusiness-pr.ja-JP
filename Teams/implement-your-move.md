---
title: Microsoft Teams への移行を実装する
author: Benny-54
ms.author: v-bshilpa
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: この記事では、Microsoft Teams を展開して実装する方法について説明します。
f1.keywords: ''
localization_priority: Normal
search.appverid: ''
ms.collection: ''
ms.custom: ''
ms.openlocfilehash: 678cad1b71c9f3e8d1e79a50f5ae46aba4456b5a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120668"
---
# <a name="implement-your-move-to-microsoft-teams"></a><span data-ttu-id="769ad-103">Microsoft Teams への移行を実装する</span><span class="sxs-lookup"><span data-stu-id="769ad-103">Implement your move to Microsoft Teams</span></span>

<span data-ttu-id="769ad-104">この記事では、次のシナリオで Microsoft Teams の展開と実装に関するガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="769ad-104">This article provides your guidance on deployment and implementation of Microsoft Teams for the following scenarios:</span></span>

1. <span data-ttu-id="769ad-105">Microsoft **Teams を既に使用している組織の場合**</span><span class="sxs-lookup"><span data-stu-id="769ad-105">For organizations **already using Microsoft Teams**</span></span>
2. <span data-ttu-id="769ad-106">Microsoft **Teams をまだ使用していない組織の場合**</span><span class="sxs-lookup"><span data-stu-id="769ad-106">For organizations **not yet using Microsoft Teams**</span></span>

## <a name="deploying-and-implementing-microsoft-teams-for-organizations-already-using-microsoft-teams"></a><span data-ttu-id="769ad-107">Microsoft Teams を既に使用している組織向け Microsoft Teams の展開と実装</span><span class="sxs-lookup"><span data-stu-id="769ad-107">Deploying and implementing Microsoft Teams for organizations already using Microsoft Teams</span></span>
 
<span data-ttu-id="769ad-108">先に進む前に、次のアクティビティを完了していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="769ad-108">Before proceeding, confirm that you've completed the following activities:</span></span> 

- <span data-ttu-id="769ad-109">組織のビジョンを描いたチームワーク</span><span class="sxs-lookup"><span data-stu-id="769ad-109">Envisioned teamwork for your organization</span></span>  
- <span data-ttu-id="769ad-110">チャンピオンと重要な関係者が特定されました</span><span class="sxs-lookup"><span data-stu-id="769ad-110">Identified champions and critical stakeholders</span></span> 
- <span data-ttu-id="769ad-111">プロジェクトの対象範囲を定義した</span><span class="sxs-lookup"><span data-stu-id="769ad-111">Defined your project scope</span></span>  
- <span data-ttu-id="769ad-112">パイロットされた Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="769ad-112">Piloted Microsoft Teams</span></span> 
- <span data-ttu-id="769ad-113">組織を準備した</span><span class="sxs-lookup"><span data-stu-id="769ad-113">Prepared your organization</span></span> 

<span data-ttu-id="769ad-114">既に Microsoft Teams を展開済みで **、Kaizala** から Microsoft Teams にライセンスを取得したユーザーを移動する場合は、この記事のガイダンスに従います。</span><span class="sxs-lookup"><span data-stu-id="769ad-114">Follow the guidance in this article, if you **already have Microsoft Teams rolled out** and want to move your licensed users from Kaizala to Microsoft Teams.</span></span> 
   
<span data-ttu-id="769ad-115">移行には、次のフレームワークをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="769ad-115">We recommend the following framework for transition:</span></span>  
   
<span data-ttu-id="769ad-116">**移行を計画する**</span><span class="sxs-lookup"><span data-stu-id="769ad-116">**Plan for your transition**</span></span> 
   
1. <span data-ttu-id="769ad-117">最初に、チャット グループを Microsoft Teams に移動します。</span><span class="sxs-lookup"><span data-stu-id="769ad-117">First, move your chat groups to Microsoft Teams.</span></span>
1. <span data-ttu-id="769ad-118">次に、Teams のアプリを使用して Kaizala アクション カードを置き換える。</span><span class="sxs-lookup"><span data-stu-id="769ad-118">Next, use apps in Teams to replace Kaizala action cards.</span></span>
1. <span data-ttu-id="769ad-119">最前線の従業員が確実に機能するには、Teams Frontline Worker の機能にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="769ad-119">To ensure that frontline workers are equipped, upgrade to Teams Frontline Worker functionality.</span></span> <span data-ttu-id="769ad-120">Teams Frontline Worker のクイック スタート ガイドについては [、Frontline Worker クイック スタート ガイドを参照してください](./flw-quickstart.yml)。</span><span class="sxs-lookup"><span data-stu-id="769ad-120">For a quick start guide on Teams Frontline Worker, see [Frontline Worker Quick Start Guide](./flw-quickstart.yml).</span></span>
1. <span data-ttu-id="769ad-121">Teams でゲストとして招待するサプライヤーとパートナーのオンボーディングを検討してください。</span><span class="sxs-lookup"><span data-stu-id="769ad-121">Consider Onboarding suppliers and partners to invite as guests in Teams.</span></span>  
  
<span data-ttu-id="769ad-122">**変更を管理する**</span><span class="sxs-lookup"><span data-stu-id="769ad-122">**Manage change**</span></span>  
   
1. <span data-ttu-id="769ad-123">移行プロジェクトに関する認識を高めるコミュニケーション キャンペーンを作成します。</span><span class="sxs-lookup"><span data-stu-id="769ad-123">Create a communication campaign to raise awareness on the transition project.</span></span> 
1. <span data-ttu-id="769ad-124">変更を組織に通知し、Microsoft Teams の導入を推進するチャンピオンを特定します。</span><span class="sxs-lookup"><span data-stu-id="769ad-124">Notify your organization of the change and identify champions to drive adoption of Microsoft Teams.</span></span> 
1. <span data-ttu-id="769ad-125">無料のトレーニングを通じて、ユーザーが Microsoft Teams の詳細を知る権限を与える。</span><span class="sxs-lookup"><span data-stu-id="769ad-125">Empower your users to learn more about Microsoft Teams through free training.</span></span> 
   
<span data-ttu-id="769ad-126">詳細については [、Microsoft Teams のビデオ トレーニングを参照してください](https://support.microsoft.com/office/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7?ui=en-us&rs=en-us&ad=us)。</span><span class="sxs-lookup"><span data-stu-id="769ad-126">To learn more, see [Microsoft Teams video training](https://support.microsoft.com/office/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7?ui=en-us&rs=en-us&ad=us).</span></span>   
 
## <a name="deploying-and-implementing-microsoft-teams-for-organizations-not-yet-using-microsoft-teams"></a><span data-ttu-id="769ad-127">Microsoft Teams をまだ使用していない組織向け Microsoft Teams の展開と実装</span><span class="sxs-lookup"><span data-stu-id="769ad-127">Deploying and implementing Microsoft Teams for organizations not yet using Microsoft Teams</span></span>
 
<span data-ttu-id="769ad-128">Kaizala を使用し、Kaizala から Microsoft Teams にユーザーを移動する場合は、このセクションのガイダンスに従います。</span><span class="sxs-lookup"><span data-stu-id="769ad-128">Follow the guidance in this section, if you're using Kaizala and want to move your users from Kaizala to Microsoft Teams.</span></span>
   
<span data-ttu-id="769ad-129">**続く前に、次のアクティビティを完了したと確認します**。</span><span class="sxs-lookup"><span data-stu-id="769ad-129">**Before proceeding, confirm that you've completed the following activities**:</span></span> 
   
- <span data-ttu-id="769ad-130">組織のビジョンを描いたチームワーク</span><span class="sxs-lookup"><span data-stu-id="769ad-130">Envisioned teamwork for your organization</span></span> 
- <span data-ttu-id="769ad-131">チャンピオンと重要な関係者が特定されました</span><span class="sxs-lookup"><span data-stu-id="769ad-131">Identified champions and critical stakeholders</span></span> 
- <span data-ttu-id="769ad-132">プロジェクトの対象範囲を定義した</span><span class="sxs-lookup"><span data-stu-id="769ad-132">Defined your project scope</span></span>  
- <span data-ttu-id="769ad-133">パイロットされた Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="769ad-133">Piloted Microsoft Teams</span></span>
- <span data-ttu-id="769ad-134">組織を準備した</span><span class="sxs-lookup"><span data-stu-id="769ad-134">Prepared your organization</span></span>  
   
<span data-ttu-id="769ad-135">移行には、次のフレームワークをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="769ad-135">We recommend the following framework for transition:</span></span> 
   
- <span data-ttu-id="769ad-136">**組織のチームワークを構想する**</span><span class="sxs-lookup"><span data-stu-id="769ad-136">**Envision teamwork for your organization**</span></span> 
   
   <span data-ttu-id="769ad-137">Kaizala が使用されている現在のシナリオを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="769ad-137">List the current scenarios in which Kaizala is used.</span></span> <span data-ttu-id="769ad-138">次に、Microsoft Teams を使って、上から先のシナリオを想像します。</span><span class="sxs-lookup"><span data-stu-id="769ad-138">Next, envision scenarios above and beyond with Microsoft Teams.</span></span>  

- <span data-ttu-id="769ad-139">**Teams をパイロットする**</span><span class="sxs-lookup"><span data-stu-id="769ad-139">**Pilot Teams**</span></span>

   <span data-ttu-id="769ad-140">優先順位が設定されたシナリオセットを使用して、Teams をパイロット ユーザー グループにロール アウトします。</span><span class="sxs-lookup"><span data-stu-id="769ad-140">Roll out Teams to a Pilot group of users with a prioritized scenario set.</span></span> 

- <span data-ttu-id="769ad-141">**Teams を展開する**</span><span class="sxs-lookup"><span data-stu-id="769ad-141">**Deploy Teams**</span></span> 

   <span data-ttu-id="769ad-142">パイロット グループから学習します。</span><span class="sxs-lookup"><span data-stu-id="769ad-142">Learn from the pilot group.</span></span> <span data-ttu-id="769ad-143">完全な組織に展開する準備をします。</span><span class="sxs-lookup"><span data-stu-id="769ad-143">Prepare to roll out to the complete organization.</span></span>  

- <span data-ttu-id="769ad-144">**Kaizala と Teams を使用する**</span><span class="sxs-lookup"><span data-stu-id="769ad-144">**Use Kaizala and Teams**</span></span>  

   <span data-ttu-id="769ad-145">ビジネスに合った Microsoft Teams を見つけるには、「Microsoft Teams Online のオプションを比較する」を[参照|Microsoft Teams .](https://www.microsoft.com/microsoft-teams/compare-microsoft-teams-options)</span><span class="sxs-lookup"><span data-stu-id="769ad-145">To find the right Microsoft Teams for your business, see [Compare Microsoft Teams Online Options | Microsoft Teams](https://www.microsoft.com/microsoft-teams/compare-microsoft-teams-options).</span></span> 

- <span data-ttu-id="769ad-146">**変更を管理する**</span><span class="sxs-lookup"><span data-stu-id="769ad-146">**Manage change**</span></span> 

   <span data-ttu-id="769ad-147">導入を推進するエンドユーザー トレーニングを通じて組織を変更する準備をします。</span><span class="sxs-lookup"><span data-stu-id="769ad-147">Prepare your organization for change through end-user training to drive adoption.</span></span> <span data-ttu-id="769ad-148">IT 管理者とチャンピオンは、移動中の積極的な変更管理に影響を与える取り組みを推進できます。</span><span class="sxs-lookup"><span data-stu-id="769ad-148">IT Admins and Champions can drive efforts to influence positive change management on the move.</span></span>  

- <span data-ttu-id="769ad-149">**Teams の導入を計画する**</span><span class="sxs-lookup"><span data-stu-id="769ad-149">**Plan for your adoption of Teams**</span></span>

    <span data-ttu-id="769ad-150">カスタム アクション カードなど、カスタム ソリューションを Kaizala から Teams に移行する準備をします。</span><span class="sxs-lookup"><span data-stu-id="769ad-150">Prepare to move custom solutions from Kaizala to Teams, for example, Custom Action cards.</span></span> 
     
- <span data-ttu-id="769ad-151">**組織を Teams に移動する**</span><span class="sxs-lookup"><span data-stu-id="769ad-151">**Move your organization to Teams**</span></span> 

    <span data-ttu-id="769ad-152">CEO から最前線の従業員まで、効率的にコミュニケーションを取るツールを使って組織を強化しましょう。</span><span class="sxs-lookup"><span data-stu-id="769ad-152">Empower your organization with a streamlined tool for communication from CEO to the frontline!</span></span>