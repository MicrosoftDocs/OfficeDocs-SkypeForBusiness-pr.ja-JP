---
title: 管理センターを使用して Teams の財務テンプレートの使用を開始する
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
description: 使い方について学習します。 管理センターを使用して定義済みの設定、チャネル、およびプレインストールされたアプリを提供することで、財務上のニーズに合って設計されたチーム構造を作成する Teams テンプレート。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 34a462a38581eec8720bd2184749b842aaa6d06f
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662512"
---
# <a name="use-teams-financial-templates-in-the-admin-center"></a><span data-ttu-id="fb30e-104">管理センターで Teams の財務テンプレートを使用する</span><span class="sxs-lookup"><span data-stu-id="fb30e-104">Use Teams financial templates in the admin center</span></span>

<span data-ttu-id="fb30e-105">Teams テンプレートを使用すると、設定、チャネル、およびプレインストールされているアプリの定義済みのテンプレートを提供することで、チームをすばやく簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="fb30e-105">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="fb30e-106">Teams テンプレートには、財務上のニーズを中心に設計されたチーム構造の定義があらかじめ組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="fb30e-106">Teams templates have pre-built definitions of team structures designed around financial needs.</span></span> <span data-ttu-id="fb30e-107">また、Teams テンプレートを拡張して、組織の特定のニーズに合わせてカスタマイズされたチームを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="fb30e-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="fb30e-108">この記事では、Teams の各テンプレートを紹介し、その使い方をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fb30e-108">In this article, we'll introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="fb30e-109">この記事は、財務組織全体で複数のチームを計画、展開、管理する責任がある場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fb30e-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your financial organization.</span></span> <span data-ttu-id="fb30e-110">Teams サービスは既に組織に展開されています。</span><span class="sxs-lookup"><span data-stu-id="fb30e-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="fb30e-111">Teams をまだ展開していない場合は、まず、Microsoft Teams を展開する方法 [を参照してください](How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="fb30e-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="fb30e-112">チーム テンプレート全般の詳細については、「Teams テンプレートの使用を開始する [」を参照してください](get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="fb30e-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="global-crisis-or-event"></a><span data-ttu-id="fb30e-113">グローバルなクライシスまたはイベント</span><span class="sxs-lookup"><span data-stu-id="fb30e-113">Global crisis or event</span></span>

<span data-ttu-id="fb30e-114">ビジネス ユニット間でクライシス チームの共同作業を一元管理し、ビジネス継続性計画の作成、リモート作業のヒントの共有、顧客とのコミュニケーションの追跡、お知らせやニュースで全員が常に連絡を取り合うのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fb30e-114">Centralize collaboration for your crisis team across business units and help create business continuity plans, share remote working tips, track customer communications, and keep everyone in the loop with announcements and news.</span></span>

| <span data-ttu-id="fb30e-115">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="fb30e-115">Base template type</span></span>|<span data-ttu-id="fb30e-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="fb30e-116">baseTemplateId</span></span> | <span data-ttu-id="fb30e-117">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="fb30e-117">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
| <span data-ttu-id="fb30e-118">グローバルクライシスまたはイベントで共同作業する</span><span class="sxs-lookup"><span data-stu-id="fb30e-118">Collaborate on global crisis or event</span></span>|`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent` |<span data-ttu-id="fb30e-119">チャネル:</span><span class="sxs-lookup"><span data-stu-id="fb30e-119">Channels:</span></span> <ul><li><span data-ttu-id="fb30e-120">一般</span><span class="sxs-lookup"><span data-stu-id="fb30e-120">General</span></span><li><span data-ttu-id="fb30e-121">お知らせ</span><span class="sxs-lookup"><span data-stu-id="fb30e-121">Announcements</span></span></li><li><span data-ttu-id="fb30e-122">世界のニュース</span><span class="sxs-lookup"><span data-stu-id="fb30e-122">World news</span></span></li><li><span data-ttu-id="fb30e-123">ビジネス継続性</span><span class="sxs-lookup"><span data-stu-id="fb30e-123">Business continuity</span></span></li><li><span data-ttu-id="fb30e-124">リモート作業</span><span class="sxs-lookup"><span data-stu-id="fb30e-124">Remote working</span></span></li><li><span data-ttu-id="fb30e-125">内部通信</span><span class="sxs-lookup"><span data-stu-id="fb30e-125">Internal comms</span></span></li><li><span data-ttu-id="fb30e-126">外部通信</span><span class="sxs-lookup"><span data-stu-id="fb30e-126">External comms</span></span></li><li><span data-ttu-id="fb30e-127">承認要求</span><span class="sxs-lookup"><span data-stu-id="fb30e-127">Approvals request</span></span></li><li><span data-ttu-id="fb30e-128">顧客からの苦情</span><span class="sxs-lookup"><span data-stu-id="fb30e-128">Customer complaints</span></span></li><li><span data-ttu-id="fb30e-129">クード</span><span class="sxs-lookup"><span data-stu-id="fb30e-129">Kudos</span></span></li><li><span data-ttu-id="fb30e-130">エグゼクティブ更新</span><span class="sxs-lookup"><span data-stu-id="fb30e-130">Executive update</span></span></li></ul><span data-ttu-id="fb30e-131">アプリ:</span><span class="sxs-lookup"><span data-stu-id="fb30e-131">Apps:</span></span> <ul><li><span data-ttu-id="fb30e-132">称賛</span><span class="sxs-lookup"><span data-stu-id="fb30e-132">Praise</span></span></li><li><span data-ttu-id="fb30e-133">Wiki</span><span class="sxs-lookup"><span data-stu-id="fb30e-133">Wiki</span></span></li><li><span data-ttu-id="fb30e-134">Web サイト</span><span class="sxs-lookup"><span data-stu-id="fb30e-134">Website</span></span></li><li><span data-ttu-id="fb30e-135">プランナー</span><span class="sxs-lookup"><span data-stu-id="fb30e-135">Planner</span></span></li></ul>|
||||

## <a name="collaborate-within-a-bank-branch"></a><span data-ttu-id="fb30e-136">銀行の支店内で共同作業を行う</span><span class="sxs-lookup"><span data-stu-id="fb30e-136">Collaborate within a bank branch</span></span>

<span data-ttu-id="fb30e-137">銀行支店の従業員の共同作業を、Huddles、顧客会議、住宅ローンのグループ作業などのビジネス プロセス間で一元管理し、お知らせやクドで全員が常に連絡を取り合います。</span><span class="sxs-lookup"><span data-stu-id="fb30e-137">Centralize collaboration for your bank branch employees across Huddles, Customer Meetings, Business Processes such as Mortgage Collaboration, and keep everyone in the loop with Announcements and Kudos.</span></span>

| <span data-ttu-id="fb30e-138">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="fb30e-138">Base template type</span></span> |<span data-ttu-id="fb30e-139">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="fb30e-139">baseTemplateId</span></span>| <span data-ttu-id="fb30e-140">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="fb30e-140">Properties that come with this base template</span></span> |
| ------------------ |--|----------------------------------------------------- |
|<span data-ttu-id="fb30e-141">銀行の支店内で共同作業を行う</span><span class="sxs-lookup"><span data-stu-id="fb30e-141">Collaborate within a bank branch</span></span>|`com.microsoft.teams.template.CollaborateWithinABankBranch` |<span data-ttu-id="fb30e-142">チャネル:</span><span class="sxs-lookup"><span data-stu-id="fb30e-142">Channels:</span></span> <ul><li><span data-ttu-id="fb30e-143">一般</span><span class="sxs-lookup"><span data-stu-id="fb30e-143">General</span></span><li><span data-ttu-id="fb30e-144">お知らせ</span><span class="sxs-lookup"><span data-stu-id="fb30e-144">Announcements</span></span></li><li><span data-ttu-id="fb30e-145">ハドル</span><span class="sxs-lookup"><span data-stu-id="fb30e-145">Huddles</span></span></li><li><span data-ttu-id="fb30e-146">顧客会議</span><span class="sxs-lookup"><span data-stu-id="fb30e-146">Customer meetings</span></span></li><li><span data-ttu-id="fb30e-147">承認要求</span><span class="sxs-lookup"><span data-stu-id="fb30e-147">Approvals Request</span></span></li><li><span data-ttu-id="fb30e-148">コーチ</span><span class="sxs-lookup"><span data-stu-id="fb30e-148">Coaching</span></span></li><li><span data-ttu-id="fb30e-149">スキル開発</span><span class="sxs-lookup"><span data-stu-id="fb30e-149">Skills development</span></span></li><li><span data-ttu-id="fb30e-150">ローン処理</span><span class="sxs-lookup"><span data-stu-id="fb30e-150">Loan processing</span></span></li><li><span data-ttu-id="fb30e-151">顧客からの苦情</span><span class="sxs-lookup"><span data-stu-id="fb30e-151">Customer complaints</span></span></li><li><span data-ttu-id="fb30e-152">クード</span><span class="sxs-lookup"><span data-stu-id="fb30e-152">Kudos</span></span></li><li><span data-ttu-id="fb30e-153">楽しい情報</span><span class="sxs-lookup"><span data-stu-id="fb30e-153">Fun stuff</span></span></li><li><span data-ttu-id="fb30e-154">コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="fb30e-154">Compliance</span></span></li></ul><span data-ttu-id="fb30e-155">アプリ:</span><span class="sxs-lookup"><span data-stu-id="fb30e-155">Apps:</span></span><ul><li><span data-ttu-id="fb30e-156">称賛</span><span class="sxs-lookup"><span data-stu-id="fb30e-156">Praise</span></span></li></ul>|
||||

