---
title: 管理コンソールを使用して Teams の財務テンプレートを使ってみる
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: 管理コンソールを使用して、定義済みの設定、チャネル、プリインストールされたアプリを提供することで、チームテンプレートを使用して、財務上のニーズに合わせて設計されたチーム構造を作成する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 270e03d58a89cf35132f254d2dd1af55d894e8d0
ms.sourcegitcommit: 448606977ee67befbdc91060363cf90dd346a528
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2020
ms.locfileid: "48136051"
---
# <a name="use-teams-financial-templates-in-the-admin-console"></a><span data-ttu-id="cf8d9-103">管理コンソールで Teams の財務テンプレートを使用する</span><span class="sxs-lookup"><span data-stu-id="cf8d9-103">Use Teams financial templates in the admin console</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

<span data-ttu-id="cf8d9-104">Teams テンプレートを使用すると、設定、チャネル、プリインストールされているアプリに定義済みのテンプレートを提供して、チームをすばやく簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="cf8d9-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="cf8d9-105">Teams テンプレートには、財務ニーズに合わせて設計されたチーム構造の事前定義が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cf8d9-105">Teams templates have pre-built definitions of team structures designed around financial needs.</span></span> <span data-ttu-id="cf8d9-106">また、チームテンプレートを拡張して、特定の組織のニーズに合わせてカスタマイズされたチームを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="cf8d9-106">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="cf8d9-107">この記事では、各チームテンプレートを紹介し、その使用をお勧めする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cf8d9-107">In this article, we will introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="cf8d9-108">この記事は、お客様が財務組織全体の複数のチームの計画、展開、管理を担当している場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="cf8d9-108">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your financial organization.</span></span> <span data-ttu-id="cf8d9-109">組織に Teams サービスを既に展開していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="cf8d9-109">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="cf8d9-110">まだチームをロールアウトしていない場合は、「 [Microsoft teams をロールアウトする方法](How-to-roll-out-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf8d9-110">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="cf8d9-111">チームテンプレートの詳細については、「 [チームテンプレートの使用を開始](get-started-with-teams-templates-in-the-admin-console.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf8d9-111">To learn more about team templates in general, please refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="global-crisis-or-event"></a><span data-ttu-id="cf8d9-112">グローバルな危機またはイベント</span><span class="sxs-lookup"><span data-stu-id="cf8d9-112">Global crisis or event</span></span>

<span data-ttu-id="cf8d9-113">ビジネスユニット全体での危機管理チームの共同作業を一元化して、ビジネス継続性プランの作成、リモートの作業ヒントの共有、顧客の通信の追跡、全員がお知らせとニュースの記録を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="cf8d9-113">Centralize collaboration for your crisis team across business units and help create business continuity plans, share remote working tips, track customer communications, and keep everyone in the loop with announcements and news.</span></span>

| <span data-ttu-id="cf8d9-114">ベーステンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="cf8d9-114">Base template type</span></span>|<span data-ttu-id="cf8d9-115">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="cf8d9-115">baseTemplateId</span></span> | <span data-ttu-id="cf8d9-116">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="cf8d9-116">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
| <span data-ttu-id="cf8d9-117">グローバルな危機またはイベントでの共同作業</span><span class="sxs-lookup"><span data-stu-id="cf8d9-117">Collaborate on global crisis or event</span></span>|`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent` |<span data-ttu-id="cf8d9-118">チャネル</span><span class="sxs-lookup"><span data-stu-id="cf8d9-118">Channels:</span></span> <ul><li><span data-ttu-id="cf8d9-119">一般</span><span class="sxs-lookup"><span data-stu-id="cf8d9-119">General</span></span><li><span data-ttu-id="cf8d9-120">お知らせ</span><span class="sxs-lookup"><span data-stu-id="cf8d9-120">Announcements</span></span></li><li><span data-ttu-id="cf8d9-121">世界中のニュース</span><span class="sxs-lookup"><span data-stu-id="cf8d9-121">World news</span></span></li><li><span data-ttu-id="cf8d9-122">ビジネス継続性</span><span class="sxs-lookup"><span data-stu-id="cf8d9-122">Business continuity</span></span></li><li><span data-ttu-id="cf8d9-123">リモート作業</span><span class="sxs-lookup"><span data-stu-id="cf8d9-123">Remote working</span></span></li><li><span data-ttu-id="cf8d9-124">内部通信</span><span class="sxs-lookup"><span data-stu-id="cf8d9-124">Internal comms</span></span></li><li><span data-ttu-id="cf8d9-125">外部通信</span><span class="sxs-lookup"><span data-stu-id="cf8d9-125">External comms</span></span></li><li><span data-ttu-id="cf8d9-126">顧客の苦情</span><span class="sxs-lookup"><span data-stu-id="cf8d9-126">Customer complaints</span></span></li><li><span data-ttu-id="cf8d9-127">称賛</span><span class="sxs-lookup"><span data-stu-id="cf8d9-127">Kudos</span></span></li><li><span data-ttu-id="cf8d9-128">エグゼクティブ更新プログラム</span><span class="sxs-lookup"><span data-stu-id="cf8d9-128">Executive update</span></span></li></ul><span data-ttu-id="cf8d9-129">アプリ</span><span class="sxs-lookup"><span data-stu-id="cf8d9-129">Apps:</span></span> <ul><li><span data-ttu-id="cf8d9-130">称賛</span><span class="sxs-lookup"><span data-stu-id="cf8d9-130">Praise</span></span></li><li><span data-ttu-id="cf8d9-131">ウィキ</span><span class="sxs-lookup"><span data-stu-id="cf8d9-131">Wiki</span></span></li><li><span data-ttu-id="cf8d9-132">当</span><span class="sxs-lookup"><span data-stu-id="cf8d9-132">Website</span></span></li></ul>|
||||

## <a name="collaborate-within-a-bank-branch"></a><span data-ttu-id="cf8d9-133">銀行支店内での共同作業</span><span class="sxs-lookup"><span data-stu-id="cf8d9-133">Collaborate within a bank branch</span></span>

<span data-ttu-id="cf8d9-134">Huddles、顧客会議、住宅ローンコラボレーションなどのビジネスプロセスを通じて、銀行支店の共同作業を一元管理し、すべてのユーザーをお知らせや称賛で追跡できます。</span><span class="sxs-lookup"><span data-stu-id="cf8d9-134">Centralize collaboration for your bank branch employees across Huddles, Customer Meetings, Business Processes such as Mortgage Collaboration, and keep everyone in the loop with Announcements and Kudos.</span></span>

| <span data-ttu-id="cf8d9-135">ベーステンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="cf8d9-135">Base template type</span></span> |<span data-ttu-id="cf8d9-136">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="cf8d9-136">baseTemplateId</span></span>| <span data-ttu-id="cf8d9-137">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="cf8d9-137">Properties that come with this base template</span></span> |
| ------------------ |--|----------------------------------------------------- |
|<span data-ttu-id="cf8d9-138">銀行支店内での共同作業</span><span class="sxs-lookup"><span data-stu-id="cf8d9-138">Collaborate within a bank branch</span></span>|`com.microsoft.teams.template.CollaborateWithinABankBranch` |<span data-ttu-id="cf8d9-139">チャネル</span><span class="sxs-lookup"><span data-stu-id="cf8d9-139">Channels:</span></span> <ul><li><span data-ttu-id="cf8d9-140">一般</span><span class="sxs-lookup"><span data-stu-id="cf8d9-140">General</span></span><li><span data-ttu-id="cf8d9-141">お知らせ</span><span class="sxs-lookup"><span data-stu-id="cf8d9-141">Announcements</span></span></li><li><span data-ttu-id="cf8d9-142">Huddles</span><span class="sxs-lookup"><span data-stu-id="cf8d9-142">Huddles</span></span></li><li><span data-ttu-id="cf8d9-143">顧客の会議</span><span class="sxs-lookup"><span data-stu-id="cf8d9-143">Customer meetings</span></span></li><li><span data-ttu-id="cf8d9-144">コーチング</span><span class="sxs-lookup"><span data-stu-id="cf8d9-144">Coaching</span></span></li><li><span data-ttu-id="cf8d9-145">スキルの開発</span><span class="sxs-lookup"><span data-stu-id="cf8d9-145">Skills development</span></span></li><li><span data-ttu-id="cf8d9-146">ローン処理</span><span class="sxs-lookup"><span data-stu-id="cf8d9-146">Loan processing</span></span></li><li><span data-ttu-id="cf8d9-147">顧客の苦情</span><span class="sxs-lookup"><span data-stu-id="cf8d9-147">Customer complaints</span></span></li><li><span data-ttu-id="cf8d9-148">称賛</span><span class="sxs-lookup"><span data-stu-id="cf8d9-148">Kudos</span></span></li><li><span data-ttu-id="cf8d9-149">楽しい機能</span><span class="sxs-lookup"><span data-stu-id="cf8d9-149">Fun stuff</span></span></li><li><span data-ttu-id="cf8d9-150">コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="cf8d9-150">Compliance</span></span></li></ul>|
||||

