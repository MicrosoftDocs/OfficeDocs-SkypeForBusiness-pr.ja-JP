---
title: 管理センターを使用して財務チーム テンプレートの使用を開始する
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
description: 管理センターを使用して定義済みの設定、チャネル、およびプレインストールされたアプリを提供することで、Teams テンプレートを使用して、財務ニーズに合ったチーム構造を作成する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 34e1140fe1551c0e0bc52449735755fc6d6428ca
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684444"
---
# <a name="use-financial-team-templates-in-the-admin-center"></a><span data-ttu-id="21ae3-103">管理センターで財務チーム テンプレートを使用する</span><span class="sxs-lookup"><span data-stu-id="21ae3-103">Use financial team templates in the admin center</span></span>

<span data-ttu-id="21ae3-104">チーム テンプレートを使用すると、設定、チャネル、およびプレインストールされたアプリの定義済みのテンプレートを提供することで、チームをすばやく簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="21ae3-104">Team templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="21ae3-105">チーム テンプレートには、財務ニーズを中心に設計されたチーム構造の事前構築された定義があります。</span><span class="sxs-lookup"><span data-stu-id="21ae3-105">Team templates have pre-built definitions of team structures designed around financial needs.</span></span> <span data-ttu-id="21ae3-106">また、チーム テンプレートを拡張して、特定の組織のニーズに合わせて調整されたチームを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="21ae3-106">You can also extend the team templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="21ae3-107">この記事では、各チーム テンプレートを紹介し、その使い方をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="21ae3-107">In this article, we'll introduce each of the team templates and recommend how to use them.</span></span>

<span data-ttu-id="21ae3-108">この記事は、財務組織全体で複数のチームを計画、デプロイ、管理する責任がある場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="21ae3-108">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your financial organization.</span></span> <span data-ttu-id="21ae3-109">組織内に Teams サービスがすでに展開されています。</span><span class="sxs-lookup"><span data-stu-id="21ae3-109">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="21ae3-110">展開がまだの場合は、「[Microsoft Teams の展開方法](./deploy-overview.md)」をお読みになって展開を開始してください。</span><span class="sxs-lookup"><span data-stu-id="21ae3-110">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](./deploy-overview.md).</span></span>

<span data-ttu-id="21ae3-111">チーム テンプレート全般の詳細については、「チーム テンプレートの概要 [」を参照してください](get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="21ae3-111">To learn more about team templates in general, refer to [Get started with team templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="global-crisis-or-event"></a><span data-ttu-id="21ae3-112">グローバルな危機またはイベント</span><span class="sxs-lookup"><span data-stu-id="21ae3-112">Global crisis or event</span></span>

<span data-ttu-id="21ae3-113">ビジネス ユニット間で危機的チームの共同作業を一元化し、ビジネス継続性計画の作成、リモート作業のヒントの共有、顧客とのコミュニケーションの追跡、お知らせやニュースによる全員のループ状態の維持を支援します。</span><span class="sxs-lookup"><span data-stu-id="21ae3-113">Centralize collaboration for your crisis team across business units and help create business continuity plans, share remote working tips, track customer communications, and keep everyone in the loop with announcements and news.</span></span>

| <span data-ttu-id="21ae3-114">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="21ae3-114">Base template type</span></span>|<span data-ttu-id="21ae3-115">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="21ae3-115">baseTemplateId</span></span> | <span data-ttu-id="21ae3-116">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="21ae3-116">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
| <span data-ttu-id="21ae3-117">グローバルな危機やイベントで共同作業を行う</span><span class="sxs-lookup"><span data-stu-id="21ae3-117">Collaborate on global crisis or event</span></span>|`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent` |<span data-ttu-id="21ae3-118">チャネル</span><span class="sxs-lookup"><span data-stu-id="21ae3-118">Channels:</span></span> <ul><li><span data-ttu-id="21ae3-119">全般</span><span class="sxs-lookup"><span data-stu-id="21ae3-119">General</span></span><li><span data-ttu-id="21ae3-120">お知らせ</span><span class="sxs-lookup"><span data-stu-id="21ae3-120">Announcements</span></span></li><li><span data-ttu-id="21ae3-121">世界のニュース</span><span class="sxs-lookup"><span data-stu-id="21ae3-121">World news</span></span></li><li><span data-ttu-id="21ae3-122">ビジネス継続性</span><span class="sxs-lookup"><span data-stu-id="21ae3-122">Business continuity</span></span></li><li><span data-ttu-id="21ae3-123">リモート作業</span><span class="sxs-lookup"><span data-stu-id="21ae3-123">Remote working</span></span></li><li><span data-ttu-id="21ae3-124">内部 comms</span><span class="sxs-lookup"><span data-stu-id="21ae3-124">Internal comms</span></span></li><li><span data-ttu-id="21ae3-125">外部通信</span><span class="sxs-lookup"><span data-stu-id="21ae3-125">External comms</span></span></li><li><span data-ttu-id="21ae3-126">承認要求</span><span class="sxs-lookup"><span data-stu-id="21ae3-126">Approvals request</span></span></li><li><span data-ttu-id="21ae3-127">顧客からの苦情</span><span class="sxs-lookup"><span data-stu-id="21ae3-127">Customer complaints</span></span></li><li><span data-ttu-id="21ae3-128">Kudos</span><span class="sxs-lookup"><span data-stu-id="21ae3-128">Kudos</span></span></li><li><span data-ttu-id="21ae3-129">エグゼクティブの更新</span><span class="sxs-lookup"><span data-stu-id="21ae3-129">Executive update</span></span></li></ul><span data-ttu-id="21ae3-130">アプリ:</span><span class="sxs-lookup"><span data-stu-id="21ae3-130">Apps:</span></span> <ul><li><span data-ttu-id="21ae3-131">称賛</span><span class="sxs-lookup"><span data-stu-id="21ae3-131">Praise</span></span></li><li><span data-ttu-id="21ae3-132">Wiki</span><span class="sxs-lookup"><span data-stu-id="21ae3-132">Wiki</span></span></li><li><span data-ttu-id="21ae3-133">Web サイト</span><span class="sxs-lookup"><span data-stu-id="21ae3-133">Website</span></span></li><li><span data-ttu-id="21ae3-134">プランナー</span><span class="sxs-lookup"><span data-stu-id="21ae3-134">Planner</span></span></li></ul>|
||||

## <a name="collaborate-within-a-bank-branch"></a><span data-ttu-id="21ae3-135">銀行支店内で共同作業を行う</span><span class="sxs-lookup"><span data-stu-id="21ae3-135">Collaborate within a bank branch</span></span>

<span data-ttu-id="21ae3-136">Huddles、Customer Meetings、Business Processes (住宅ローンのコラボレーションなど) 全体で銀行支店の従業員の共同作業を一元化し、お知らせや Kudos で全員をループ状態に保つ。</span><span class="sxs-lookup"><span data-stu-id="21ae3-136">Centralize collaboration for your bank branch employees across Huddles, Customer Meetings, Business Processes such as Mortgage Collaboration, and keep everyone in the loop with Announcements and Kudos.</span></span>

| <span data-ttu-id="21ae3-137">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="21ae3-137">Base template type</span></span> |<span data-ttu-id="21ae3-138">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="21ae3-138">baseTemplateId</span></span>| <span data-ttu-id="21ae3-139">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="21ae3-139">Properties that come with this base template</span></span> |
| ------------------ |--|----------------------------------------------------- |
|<span data-ttu-id="21ae3-140">銀行支店内で共同作業を行う</span><span class="sxs-lookup"><span data-stu-id="21ae3-140">Collaborate within a bank branch</span></span>|`com.microsoft.teams.template.CollaborateWithinABankBranch` |<span data-ttu-id="21ae3-141">チャネル</span><span class="sxs-lookup"><span data-stu-id="21ae3-141">Channels:</span></span> <ul><li><span data-ttu-id="21ae3-142">全般</span><span class="sxs-lookup"><span data-stu-id="21ae3-142">General</span></span><li><span data-ttu-id="21ae3-143">お知らせ</span><span class="sxs-lookup"><span data-stu-id="21ae3-143">Announcements</span></span></li><li><span data-ttu-id="21ae3-144">ハドル</span><span class="sxs-lookup"><span data-stu-id="21ae3-144">Huddles</span></span></li><li><span data-ttu-id="21ae3-145">顧客会議</span><span class="sxs-lookup"><span data-stu-id="21ae3-145">Customer meetings</span></span></li><li><span data-ttu-id="21ae3-146">承認要求</span><span class="sxs-lookup"><span data-stu-id="21ae3-146">Approvals Request</span></span></li><li><span data-ttu-id="21ae3-147">コーチング</span><span class="sxs-lookup"><span data-stu-id="21ae3-147">Coaching</span></span></li><li><span data-ttu-id="21ae3-148">スキル開発</span><span class="sxs-lookup"><span data-stu-id="21ae3-148">Skills development</span></span></li><li><span data-ttu-id="21ae3-149">ローン処理</span><span class="sxs-lookup"><span data-stu-id="21ae3-149">Loan processing</span></span></li><li><span data-ttu-id="21ae3-150">顧客からの苦情</span><span class="sxs-lookup"><span data-stu-id="21ae3-150">Customer complaints</span></span></li><li><span data-ttu-id="21ae3-151">Kudos</span><span class="sxs-lookup"><span data-stu-id="21ae3-151">Kudos</span></span></li><li><span data-ttu-id="21ae3-152">楽しい情報</span><span class="sxs-lookup"><span data-stu-id="21ae3-152">Fun stuff</span></span></li><li><span data-ttu-id="21ae3-153">コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="21ae3-153">Compliance</span></span></li></ul><span data-ttu-id="21ae3-154">アプリ:</span><span class="sxs-lookup"><span data-stu-id="21ae3-154">Apps:</span></span><ul><li><span data-ttu-id="21ae3-155">称賛</span><span class="sxs-lookup"><span data-stu-id="21ae3-155">Praise</span></span></li></ul>|
||||