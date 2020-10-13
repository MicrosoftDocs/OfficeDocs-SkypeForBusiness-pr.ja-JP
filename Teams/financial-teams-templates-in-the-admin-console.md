---
title: 管理センターを使用して Teams の財務テンプレートを使ってみる
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
description: 使い方については、こちらを参照してください。 管理センターを使用して、事前に定義された設定、チャネル、プリインストール済みのアプリを提供することで、財務上のニーズに合わせて設計されたチーム構造を作成する Teams テンプレート。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9f09da72f12b13b7f3dd1ab4846b320f77c9f32a
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424607"
---
# <a name="use-teams-financial-templates-in-the-admin-center"></a><span data-ttu-id="f6cb5-104">管理センターで Teams の財務テンプレートを使用する</span><span class="sxs-lookup"><span data-stu-id="f6cb5-104">Use Teams financial templates in the admin center</span></span>

<span data-ttu-id="f6cb5-105">Teams テンプレートを使用すると、設定、チャネル、プリインストールされているアプリに定義済みのテンプレートを提供して、チームをすばやく簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="f6cb5-105">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="f6cb5-106">Teams テンプレートには、財務ニーズに合わせて設計されたチーム構造の事前定義が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f6cb5-106">Teams templates have pre-built definitions of team structures designed around financial needs.</span></span> <span data-ttu-id="f6cb5-107">また、チームテンプレートを拡張して、特定の組織のニーズに合わせてカスタマイズされたチームを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="f6cb5-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="f6cb5-108">この記事では、各チームテンプレートを紹介し、その使用方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f6cb5-108">In this article, we'll introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="f6cb5-109">この記事は、お客様が財務組織全体の複数のチームの計画、展開、管理を担当している場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="f6cb5-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your financial organization.</span></span> <span data-ttu-id="f6cb5-110">組織に Teams サービスを既に展開している。</span><span class="sxs-lookup"><span data-stu-id="f6cb5-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="f6cb5-111">まだチームをロールアウトしていない場合は、「 [Microsoft teams をロールアウトする方法](How-to-roll-out-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6cb5-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="f6cb5-112">チームテンプレート全般の詳細については、「 [チームテンプレートの概要](get-started-with-teams-templates-in-the-admin-console.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6cb5-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="global-crisis-or-event"></a><span data-ttu-id="f6cb5-113">グローバルな危機またはイベント</span><span class="sxs-lookup"><span data-stu-id="f6cb5-113">Global crisis or event</span></span>

<span data-ttu-id="f6cb5-114">ビジネスユニット全体での危機管理チームの共同作業を一元化して、ビジネス継続性プランの作成、リモートの作業ヒントの共有、顧客の通信の追跡、全員がお知らせとニュースの記録を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f6cb5-114">Centralize collaboration for your crisis team across business units and help create business continuity plans, share remote working tips, track customer communications, and keep everyone in the loop with announcements and news.</span></span>

| <span data-ttu-id="f6cb5-115">ベーステンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="f6cb5-115">Base template type</span></span>|<span data-ttu-id="f6cb5-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="f6cb5-116">baseTemplateId</span></span> | <span data-ttu-id="f6cb5-117">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="f6cb5-117">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
| <span data-ttu-id="f6cb5-118">グローバルな危機またはイベントでの共同作業</span><span class="sxs-lookup"><span data-stu-id="f6cb5-118">Collaborate on global crisis or event</span></span>|`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent` |<span data-ttu-id="f6cb5-119">チャネル</span><span class="sxs-lookup"><span data-stu-id="f6cb5-119">Channels:</span></span> <ul><li><span data-ttu-id="f6cb5-120">一般</span><span class="sxs-lookup"><span data-stu-id="f6cb5-120">General</span></span><li><span data-ttu-id="f6cb5-121">お知らせ</span><span class="sxs-lookup"><span data-stu-id="f6cb5-121">Announcements</span></span></li><li><span data-ttu-id="f6cb5-122">世界中のニュース</span><span class="sxs-lookup"><span data-stu-id="f6cb5-122">World news</span></span></li><li><span data-ttu-id="f6cb5-123">ビジネス継続性</span><span class="sxs-lookup"><span data-stu-id="f6cb5-123">Business continuity</span></span></li><li><span data-ttu-id="f6cb5-124">リモート作業</span><span class="sxs-lookup"><span data-stu-id="f6cb5-124">Remote working</span></span></li><li><span data-ttu-id="f6cb5-125">内部通信</span><span class="sxs-lookup"><span data-stu-id="f6cb5-125">Internal comms</span></span></li><li><span data-ttu-id="f6cb5-126">外部通信</span><span class="sxs-lookup"><span data-stu-id="f6cb5-126">External comms</span></span></li><li><span data-ttu-id="f6cb5-127">顧客の苦情</span><span class="sxs-lookup"><span data-stu-id="f6cb5-127">Customer complaints</span></span></li><li><span data-ttu-id="f6cb5-128">称賛</span><span class="sxs-lookup"><span data-stu-id="f6cb5-128">Kudos</span></span></li><li><span data-ttu-id="f6cb5-129">エグゼクティブ更新プログラム</span><span class="sxs-lookup"><span data-stu-id="f6cb5-129">Executive update</span></span></li></ul><span data-ttu-id="f6cb5-130">アプリ</span><span class="sxs-lookup"><span data-stu-id="f6cb5-130">Apps:</span></span> <ul><li><span data-ttu-id="f6cb5-131">称賛</span><span class="sxs-lookup"><span data-stu-id="f6cb5-131">Praise</span></span></li><li><span data-ttu-id="f6cb5-132">ウィキ</span><span class="sxs-lookup"><span data-stu-id="f6cb5-132">Wiki</span></span></li><li><span data-ttu-id="f6cb5-133">当</span><span class="sxs-lookup"><span data-stu-id="f6cb5-133">Website</span></span></li></ul>|
||||

## <a name="collaborate-within-a-bank-branch"></a><span data-ttu-id="f6cb5-134">銀行支店内での共同作業</span><span class="sxs-lookup"><span data-stu-id="f6cb5-134">Collaborate within a bank branch</span></span>

<span data-ttu-id="f6cb5-135">Huddles、顧客会議、住宅ローンコラボレーションなどのビジネスプロセスを通じて、銀行支店の共同作業を一元管理し、すべてのユーザーをお知らせや称賛で追跡できます。</span><span class="sxs-lookup"><span data-stu-id="f6cb5-135">Centralize collaboration for your bank branch employees across Huddles, Customer Meetings, Business Processes such as Mortgage Collaboration, and keep everyone in the loop with Announcements and Kudos.</span></span>

| <span data-ttu-id="f6cb5-136">ベーステンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="f6cb5-136">Base template type</span></span> |<span data-ttu-id="f6cb5-137">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="f6cb5-137">baseTemplateId</span></span>| <span data-ttu-id="f6cb5-138">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="f6cb5-138">Properties that come with this base template</span></span> |
| ------------------ |--|----------------------------------------------------- |
|<span data-ttu-id="f6cb5-139">銀行支店内での共同作業</span><span class="sxs-lookup"><span data-stu-id="f6cb5-139">Collaborate within a bank branch</span></span>|`com.microsoft.teams.template.CollaborateWithinABankBranch` |<span data-ttu-id="f6cb5-140">チャネル</span><span class="sxs-lookup"><span data-stu-id="f6cb5-140">Channels:</span></span> <ul><li><span data-ttu-id="f6cb5-141">一般</span><span class="sxs-lookup"><span data-stu-id="f6cb5-141">General</span></span><li><span data-ttu-id="f6cb5-142">お知らせ</span><span class="sxs-lookup"><span data-stu-id="f6cb5-142">Announcements</span></span></li><li><span data-ttu-id="f6cb5-143">Huddles</span><span class="sxs-lookup"><span data-stu-id="f6cb5-143">Huddles</span></span></li><li><span data-ttu-id="f6cb5-144">顧客の会議</span><span class="sxs-lookup"><span data-stu-id="f6cb5-144">Customer meetings</span></span></li><li><span data-ttu-id="f6cb5-145">コーチング</span><span class="sxs-lookup"><span data-stu-id="f6cb5-145">Coaching</span></span></li><li><span data-ttu-id="f6cb5-146">スキルの開発</span><span class="sxs-lookup"><span data-stu-id="f6cb5-146">Skills development</span></span></li><li><span data-ttu-id="f6cb5-147">ローン処理</span><span class="sxs-lookup"><span data-stu-id="f6cb5-147">Loan processing</span></span></li><li><span data-ttu-id="f6cb5-148">顧客の苦情</span><span class="sxs-lookup"><span data-stu-id="f6cb5-148">Customer complaints</span></span></li><li><span data-ttu-id="f6cb5-149">称賛</span><span class="sxs-lookup"><span data-stu-id="f6cb5-149">Kudos</span></span></li><li><span data-ttu-id="f6cb5-150">楽しい機能</span><span class="sxs-lookup"><span data-stu-id="f6cb5-150">Fun stuff</span></span></li><li><span data-ttu-id="f6cb5-151">コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="f6cb5-151">Compliance</span></span></li></ul>|
||||

