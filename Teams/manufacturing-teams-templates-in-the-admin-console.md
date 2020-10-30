---
title: 管理センターで Teams 製造テンプレートの使用を開始する
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
description: 使い方については、こちらを参照してください。 管理センターを使って、事前に定義された設定、チャネル、プリインストール済みのアプリを提供することによって、製造ニーズに合わせて設計されたチーム構造を作成するチームテンプレート。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9013bda2f83a63776dfbf9110a0863dcf68c0ddb
ms.sourcegitcommit: bc471f18e40e37456edc9696e11b175581847617
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "48800600"
---
# <a name="use-teams-manufacturing-templates-in-the-admin-center"></a><span data-ttu-id="671c1-104">管理センターで Teams 製造テンプレートを使用する</span><span class="sxs-lookup"><span data-stu-id="671c1-104">Use Teams manufacturing templates in the admin center</span></span>

<span data-ttu-id="671c1-105">Teams テンプレートを使用すると、設定、チャネル、プリインストールされているアプリに定義済みのテンプレートを提供して、チームをすばやく簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="671c1-105">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="671c1-106">チームテンプレートには、製造ニーズに合わせて設計されたチーム構造の事前定義が用意されています。</span><span class="sxs-lookup"><span data-stu-id="671c1-106">Teams templates have pre-built definitions of team structures designed around manufacturing needs.</span></span> <span data-ttu-id="671c1-107">また、チームテンプレートを拡張して、特定の組織のニーズに合わせてカスタマイズされたチームを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="671c1-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="671c1-108">この記事では、各チームテンプレートを紹介し、その使い方をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="671c1-108">In this article, we introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="671c1-109">この記事は、製造組織全体で複数のチームの計画、展開、管理を担当している場合に使います。</span><span class="sxs-lookup"><span data-stu-id="671c1-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your manufacturing organization.</span></span> <span data-ttu-id="671c1-110">組織に Teams サービスを既に展開している。</span><span class="sxs-lookup"><span data-stu-id="671c1-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="671c1-111">まだチームをロールアウトしていない場合は、「 [Microsoft teams をロールアウトする方法](How-to-roll-out-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="671c1-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="671c1-112">チームテンプレート全般の詳細については、「 [チームテンプレートの概要](get-started-with-teams-templates-in-the-admin-console.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="671c1-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="quality-and-safety"></a><span data-ttu-id="671c1-113">品質と安全性</span><span class="sxs-lookup"><span data-stu-id="671c1-113">Quality and safety</span></span>

<span data-ttu-id="671c1-114">製造プラントチームとのコミュニケーション、リソースへのアクセス、プラント操作の一元管理。</span><span class="sxs-lookup"><span data-stu-id="671c1-114">Centralize communication, access to resources, and plant operations with a Manufacturing Plant team.</span></span> <span data-ttu-id="671c1-115">ポリシーと手続きドキュメント、トレーニングビデオ、安全性の通知、移行プロセスのシフトを含めます。</span><span class="sxs-lookup"><span data-stu-id="671c1-115">Include policy and procedure documents, training videos, safety notices, shift handover processes.</span></span>

| <span data-ttu-id="671c1-116">ベーステンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="671c1-116">Base template type</span></span>|<span data-ttu-id="671c1-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="671c1-117">baseTemplateId</span></span> | <span data-ttu-id="671c1-118">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="671c1-118">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="671c1-119">品質と安全性</span><span class="sxs-lookup"><span data-stu-id="671c1-119">Quality and safety</span></span>|`com.microsoft.teams.template.QualitySafety` |<span data-ttu-id="671c1-120">チャネル</span><span class="sxs-lookup"><span data-stu-id="671c1-120">Channels:</span></span> <ul><li><span data-ttu-id="671c1-121">一般</span><span class="sxs-lookup"><span data-stu-id="671c1-121">General</span></span><li><span data-ttu-id="671c1-122">お知らせ</span><span class="sxs-lookup"><span data-stu-id="671c1-122">Announcements</span></span></li><li><span data-ttu-id="671c1-123">行1</span><span class="sxs-lookup"><span data-stu-id="671c1-123">Line 1</span></span></li><li><span data-ttu-id="671c1-124">2行目</span><span class="sxs-lookup"><span data-stu-id="671c1-124">Line 2</span></span></li><li><span data-ttu-id="671c1-125">行3</span><span class="sxs-lookup"><span data-stu-id="671c1-125">Line 3</span></span></li><li><span data-ttu-id="671c1-126">安全</span><span class="sxs-lookup"><span data-stu-id="671c1-126">Safety</span></span></li><li><span data-ttu-id="671c1-127">トレーニング</span><span class="sxs-lookup"><span data-stu-id="671c1-127">Training</span></span></li><li><span data-ttu-id="671c1-128">メンテナンス</span><span class="sxs-lookup"><span data-stu-id="671c1-128">Maintenance</span></span></li><li><span data-ttu-id="671c1-129">楽しい機能</span><span class="sxs-lookup"><span data-stu-id="671c1-129">Fun stuff</span></span></li></ul> <span data-ttu-id="671c1-130">アプリ</span><span class="sxs-lookup"><span data-stu-id="671c1-130">Apps:</span></span> <ul><li><span data-ttu-id="671c1-131">ウィキ</span><span class="sxs-lookup"><span data-stu-id="671c1-131">Wiki</span></span></li></ul>|
||||
