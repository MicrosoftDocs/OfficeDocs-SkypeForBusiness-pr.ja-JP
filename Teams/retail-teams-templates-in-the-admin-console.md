---
title: 管理センターで Teams 小売用テンプレートを使用する
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
description: 管理センターを使用して、定義済みの設定、チャネル、プリインストールされたアプリを提供することで、チームテンプレートを使用して、小売業者のニーズに合わせて設計されたチーム構造を作成する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: a24e1f440702f10785e42b83c39a53cb14da8739
ms.sourcegitcommit: bc471f18e40e37456edc9696e11b175581847617
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "48800580"
---
# <a name="use-teams-retail-templates-in-the-admin-center"></a><span data-ttu-id="24104-103">管理センターで Teams 小売用テンプレートを使用する</span><span class="sxs-lookup"><span data-stu-id="24104-103">Use Teams retail templates in the admin center</span></span>

<span data-ttu-id="24104-104">Teams テンプレートを使用すると、設定、チャネル、プリインストールされているアプリに定義済みのテンプレートを提供して、チームをすばやく簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="24104-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="24104-105">Teams のテンプレートには、小売業者のニーズに合わせて設計されたチーム構造の事前定義が含まれています。</span><span class="sxs-lookup"><span data-stu-id="24104-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="24104-106">Teams テンプレートを使用すると、小売業者に適したチームの種類をすばやく作成して、組織全体に展開することができます。</span><span class="sxs-lookup"><span data-stu-id="24104-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="24104-107">また、チームテンプレートを拡張して、特定の組織のニーズに合わせてカスタマイズされたチームを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="24104-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="24104-108">この記事では、各チームテンプレートを紹介し、その使用をお勧めする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="24104-108">In this article, we'll introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="24104-109">この記事は、小売組織全体で複数のチームの計画、展開、管理を担当している場合に使います。</span><span class="sxs-lookup"><span data-stu-id="24104-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="24104-110">組織に Teams サービスを既に展開していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="24104-110">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="24104-111">まだチームをロールアウトしていない場合は、「 [Microsoft teams をロールアウトする方法](How-to-roll-out-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24104-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="24104-112">チームテンプレート全般の詳細については、「 [チームテンプレートの概要](get-started-with-teams-templates-in-the-admin-console.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24104-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="organize-a-store"></a><span data-ttu-id="24104-113">ストアを整理する</span><span class="sxs-lookup"><span data-stu-id="24104-113">Organize a store</span></span>

<span data-ttu-id="24104-114">1つの中央のエクスペリエンスで小売従業員をまとめて、タスクの管理、ドキュメントの共有、顧客の問題の解決を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="24104-114">Bring your retail employees together in one central experience to manage tasks, share documents and resolve customer issues.</span></span> <span data-ttu-id="24104-115">他のアプリケーションを統合して、shift キーを使い始める & プロセスを効率化します。</span><span class="sxs-lookup"><span data-stu-id="24104-115">Integrate additional applications to streamline shift start & end processes.</span></span>

| <span data-ttu-id="24104-116">ベーステンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="24104-116">Base template type</span></span> |<span data-ttu-id="24104-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="24104-117">baseTemplateId</span></span> | <span data-ttu-id="24104-118">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="24104-118">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="24104-119">ストアを整理する</span><span class="sxs-lookup"><span data-stu-id="24104-119">Organize a store</span></span>| `retailStore`|<span data-ttu-id="24104-120">チャネル</span><span class="sxs-lookup"><span data-stu-id="24104-120">Channels:</span></span> <ul><li><span data-ttu-id="24104-121">一般</span><span class="sxs-lookup"><span data-stu-id="24104-121">General</span></span><li><span data-ttu-id="24104-122">シフトハンド</span><span class="sxs-lookup"><span data-stu-id="24104-122">Shift handoff</span></span></li><li><span data-ttu-id="24104-123">意欲</span><span class="sxs-lookup"><span data-stu-id="24104-123">Learning</span></span></li></ul> <span data-ttu-id="24104-124">アプリ</span><span class="sxs-lookup"><span data-stu-id="24104-124">Apps:</span></span> <ul><li><span data-ttu-id="24104-125">ウィキ</span><span class="sxs-lookup"><span data-stu-id="24104-125">Wiki</span></span></li></ul>|
||||

## <a name="manager-collaboration"></a><span data-ttu-id="24104-126">上司との共同作業</span><span class="sxs-lookup"><span data-stu-id="24104-126">Manager Collaboration</span></span>

<span data-ttu-id="24104-127">マネージャーコラボレーションテンプレートは、ストアや地域で共同作業するためのチームを作成するのに適しています。たとえば、組織に地域がある場合は、カリフォルニア地域のマネージャーコラボレーションチームを作成し、その地域のすべてのストアマネージャーとその地域の地域マネージャーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="24104-127">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="24104-128">ベーステンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="24104-128">Base template type</span></span>| <span data-ttu-id="24104-129">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="24104-129">baseTemplateId</span></span> | <span data-ttu-id="24104-130">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="24104-130">Properties that come with this base template</span></span> |
| ------------------|- |----------------------------------------------------- |
|<span data-ttu-id="24104-131">小売課長のコラボレーション</span><span class="sxs-lookup"><span data-stu-id="24104-131">Retail - manager collaboration</span></span>|`retailManagerCollaboration` |<span data-ttu-id="24104-132">チャネル</span><span class="sxs-lookup"><span data-stu-id="24104-132">Channels:</span></span> <ul><li><span data-ttu-id="24104-133">一般</span><span class="sxs-lookup"><span data-stu-id="24104-133">General</span></span><li><span data-ttu-id="24104-134">操作</span><span class="sxs-lookup"><span data-stu-id="24104-134">Operations</span></span></li><li><span data-ttu-id="24104-135">意欲</span><span class="sxs-lookup"><span data-stu-id="24104-135">Learning</span></span></li></ul> <span data-ttu-id="24104-136">アプリ</span><span class="sxs-lookup"><span data-stu-id="24104-136">Apps:</span></span> <ul><li><span data-ttu-id="24104-137">ウィキ</span><span class="sxs-lookup"><span data-stu-id="24104-137">Wiki</span></span></li></ul>|
||||
