---
title: Microsoft Teams の導入の推進を開始する
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 11/01/2018
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: karuanag
localization_priority: Normal
search.appverid: MET150
description: この記事では、Microsoft Teams の導入フェーズのスタートアップ、実験、有効化について説明します。
f1.keywords:
- CSH
ms.custom:
- Adopt
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7fc3d2deea06e7502884741470aec7e58660eeb0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834147"
---
# <a name="get-started-driving-adoption-of-microsoft-teams"></a><span data-ttu-id="e6382-103">Microsoft Teams の導入の推進を開始する</span><span class="sxs-lookup"><span data-stu-id="e6382-103">Get started driving adoption of Microsoft Teams</span></span>

<span data-ttu-id="e6382-104">Microsoft Teams の導入を推進することで、優れたユーザー エクスペリエンスと企業内でのビジネス価値の向上を実現できます。</span><span class="sxs-lookup"><span data-stu-id="e6382-104">By driving adoption of Microsoft Teams, you can deliver an excellent user experience and increased business value inside your company.</span></span> <span data-ttu-id="e6382-105">目標は、Teams を使用して旅を開始できるよう、ユーザーを迅速に立ち上げ、実行する方法です。</span><span class="sxs-lookup"><span data-stu-id="e6382-105">Our goal is to get you up and running quickly so that you can begin your journey with Teams.</span></span> <span data-ttu-id="e6382-106">このガイドでは、Teams のユーザーの導入に重点を当て、ドキュメントの他のセクションで説明する環境の技術的準備に依存します。</span><span class="sxs-lookup"><span data-stu-id="e6382-106">This guide focuses on user adoption of Teams and has dependencies on your environment's technical readiness, which is addressed in other sections of our documentation.</span></span>

## <a name="adoption-prerequisites"></a><span data-ttu-id="e6382-107">導入の前提条件</span><span class="sxs-lookup"><span data-stu-id="e6382-107">Adoption prerequisites</span></span>

<span data-ttu-id="e6382-108">始める前に、次の確認を行います。</span><span class="sxs-lookup"><span data-stu-id="e6382-108">Before getting started, make sure that:</span></span>

- <span data-ttu-id="e6382-109">[Teams がインストールされ](get-clients.md)[、ライセンスが環境](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e6382-109">[Teams is installed](get-clients.md) and [licenses are assigned](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description) in your environment.</span></span> <span data-ttu-id="e6382-110">最低でも、コア チームと、この初期プロジェクト フェーズに参加する早期導入者にライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6382-110">At a minimum licenses should be assigned to your core team and to the early adopters who will participate in this initial project phase.</span></span>

- <span data-ttu-id="e6382-111">デスクトップ アプリケーションとモバイル アプリケーションをダウンロードしました。</span><span class="sxs-lookup"><span data-stu-id="e6382-111">You've downloaded the desktop and mobile applications.</span></span> 

## <a name="adoption-framework"></a><span data-ttu-id="e6382-112">導入フレームワーク</span><span class="sxs-lookup"><span data-stu-id="e6382-112">Adoption framework</span></span>

<span data-ttu-id="e6382-113">Microsoft 365 と Office 365 には、サービスの主要なワークロードに適用される導入フレームワークがあります。</span><span class="sxs-lookup"><span data-stu-id="e6382-113">Microsoft 365 and Office 365 have an adoption framework that applies to major workloads in the service.</span></span> <span data-ttu-id="e6382-114">このフレームワークは、クラウド サービスをサポートするために組織が実行する必要がある主要な手順に対応します。</span><span class="sxs-lookup"><span data-stu-id="e6382-114">This framework addresses the core steps that any organization should take to support cloud services.</span></span> <span data-ttu-id="e6382-115">導入フレームワーク全体の詳細については、Microsoft Enterprise のドキュメントと [リソースを参照してください](https://aka.ms/O365AdoptionHub)。</span><span class="sxs-lookup"><span data-stu-id="e6382-115">To learn more about the overall adoption framework, see [Microsoft Enterprise documentation and resources](https://aka.ms/O365AdoptionHub).</span></span> 

<span data-ttu-id="e6382-116">この Teams の導入計画では、フェーズの手順を整理し、導入フェーズで説明されている特定の Teams [ガイダンスを次](#adoption-phases)に示します。</span><span class="sxs-lookup"><span data-stu-id="e6382-116">In this Teams adoption plan, we've organized the steps in phases and provided specific Teams guidance as outlined in [Adoption phases](#adoption-phases), next.</span></span>

## <a name="adoption-phases"></a><span data-ttu-id="e6382-117">導入フェーズ</span><span class="sxs-lookup"><span data-stu-id="e6382-117">Adoption phases</span></span> 

<span data-ttu-id="e6382-118">導入プロジェクトの規模や複雑さは環境によって異なりますが、最初の手順はボード全体で同じです。</span><span class="sxs-lookup"><span data-stu-id="e6382-118">Every adoption project varies in size and complexity based on your environment, but the initial steps are identical across the board.</span></span> <span data-ttu-id="e6382-119">このプロセスを 3 つの異なるフェーズ (スタートアップ、実験、有効化) に分割すると、すべてのユーザーの導入が合理化されると考っています。</span><span class="sxs-lookup"><span data-stu-id="e6382-119">We believe that breaking the process down into three distinct phases—startup, experiment, and enable—will streamline adoption for everyone.</span></span>  

- <span data-ttu-id="e6382-120">**開始** - この最初のフェーズでは、チームをまとめて、初期のチームを設定し、Teams を使用して Teams の導入の計画を開始します。</span><span class="sxs-lookup"><span data-stu-id="e6382-120">**Start** - In this first phase, you'll gather your team together, set up your initial teams, and use Teams to begin planning Teams adoption.</span></span> <span data-ttu-id="e6382-121">この方法は、製品に関する技術的な知識を高め、後続のフェーズを正常に完了するために必要なスキルを構築するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e6382-121">This approach will increase your technical familiarity with the product and help you to build the skills necessary to successfully complete subsequent phases.</span></span> 

- <span data-ttu-id="e6382-122">**実験** - 制御された成長のこのフェーズでは、内部チャンピオンと早期採用者をオンボードします。</span><span class="sxs-lookup"><span data-stu-id="e6382-122">**Experiment** - In this phase of controlled growth, you'll bring your internal champions and early adopters onboard.</span></span> <span data-ttu-id="e6382-123">ビジネス ユーザーと話し合って、Teams が提供するコラボレーション機能とコミュニケーション機能の恩恵を受けるシナリオをすぐに特定します。</span><span class="sxs-lookup"><span data-stu-id="e6382-123">You'll speak with your business users to identify scenarios that would immediately benefit from the collaboration and communications capabilities that Teams provides.</span></span> <span data-ttu-id="e6382-124">広範な導入フェーズを通知するフィードバックを収集し、展開を成功させるガバナンスとライフサイクル管理に関するサービス決定を行います。</span><span class="sxs-lookup"><span data-stu-id="e6382-124">You'll gather feedback that will inform your broad-scale adoption phase, and you'll make service decisions about governance and lifecycle management that will ensure a successful deployment.</span></span>

- <span data-ttu-id="e6382-125">**規模** - これは、すべての従業員に Teams の機能を有効にする広範な展開フェーズです。</span><span class="sxs-lookup"><span data-stu-id="e6382-125">**Scale** - This is the broad-scale deployment phase in which you'll turn on Teams capabilities for all your employees.</span></span> <span data-ttu-id="e6382-126">このフェーズでは、組織の規模によって、これがすべての従業員に対して Teams を同時に有効にする "大きなプロジェクトに進む" か、地域、ビジネス ユニット、または従業員の人口をセグメント化するその他の方法でこの方法に取り組むかどうかが決定されます。</span><span class="sxs-lookup"><span data-stu-id="e6382-126">In this phase, the size of your organization will determine whether this is a "go big" project that will turn on Teams for all employees simultaneously or if you'll approach this by region, business unit, or other method of segmenting your employee population.</span></span> <span data-ttu-id="e6382-127">このフェーズでは、継続的配信モデルに移動します。</span><span class="sxs-lookup"><span data-stu-id="e6382-127">In this phase you'll move to a continuous delivery model.</span></span> <span data-ttu-id="e6382-128">従業員、リーダー、およびビジネス ユニットは、Teams の使用を拡大する必要があります。Microsoft 365 または Office 365 の Teams とその他の機能を最適に使用する方法を理解するには、トレーニングと関与が必要です。</span><span class="sxs-lookup"><span data-stu-id="e6382-128">Employees, leaders, and business units will want to expand their use of Teams and will require training and your engagement to understand how to best use Teams and other features of Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="e6382-129">これらの導入フェーズは、Teams の技術的準備と環境の準備状況によって異なります。</span><span class="sxs-lookup"><span data-stu-id="e6382-129">Each of these adoption phases depends on your technical and environmental readiness for Teams.</span></span> <span data-ttu-id="e6382-130">では、始めましょう。</span><span class="sxs-lookup"><span data-stu-id="e6382-130">Let's get started!</span></span>


<span data-ttu-id="e6382-131">![次の手順を表すアイコン ](media/teams-adoption-next-icon.png) 次:        [Microsoft Teams の導入フェーズ 1: 開始](teams-adoption-phase1.md)|</span><span class="sxs-lookup"><span data-stu-id="e6382-131">![An icon representing the next step](media/teams-adoption-next-icon.png) Next:        [Microsoft Teams adoption phase 1: Start](teams-adoption-phase1.md)|</span></span>
