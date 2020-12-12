---
title: 管理センターで Teams のリテール テンプレートを使用する
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
description: 管理センターを使用して定義済みの設定、チャネル、プレインストールされたアプリを提供することで、Teams テンプレートを使用して販売店のニーズに合ったチーム構造を作成する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b40da8fd1cc8182d0e5ad80c30f5a459f17d26f
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662642"
---
# <a name="use-teams-retail-templates-in-the-admin-center"></a><span data-ttu-id="e3960-103">管理センターで Teams のリテール テンプレートを使用する</span><span class="sxs-lookup"><span data-stu-id="e3960-103">Use Teams retail templates in the admin center</span></span>

<span data-ttu-id="e3960-104">Teams テンプレートを使用すると、設定、チャネル、およびプレインストールされているアプリの定義済みのテンプレートを提供することで、チームをすばやく簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="e3960-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="e3960-105">Teams テンプレートには、販売店のニーズを中心に設計されたチーム構造の定義があらかじめ組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="e3960-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="e3960-106">Teams テンプレートを使用すると、販売店に合った種類のチームをすばやく作成し、組織全体に展開することができます。</span><span class="sxs-lookup"><span data-stu-id="e3960-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="e3960-107">また、Teams テンプレートを拡張して、組織の特定のニーズに合わせてカスタマイズされたチームを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="e3960-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="e3960-108">この記事では、Teams の各テンプレートと、それらを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e3960-108">In this article, we'll introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="e3960-109">この記事は、リテール組織全体で複数のチームを計画、展開、管理する責任がある場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e3960-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="e3960-110">Teams サービスは既に組織に展開済みである場合を想定しています。</span><span class="sxs-lookup"><span data-stu-id="e3960-110">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="e3960-111">Teams をまだ展開していない場合は、まず、Microsoft Teams を展開する方法 [を参照してください](How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="e3960-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="e3960-112">チーム テンプレート全般の詳細については、「Teams テンプレートの使用を開始する [」を参照してください](get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="e3960-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="organize-a-store"></a><span data-ttu-id="e3960-113">ストアを整理する</span><span class="sxs-lookup"><span data-stu-id="e3960-113">Organize a store</span></span>

<span data-ttu-id="e3960-114">小売業の従業員を 1 つの中心的な操作環境にまとめ、タスクの管理、ドキュメントの共有、顧客の問題の解決を行います。</span><span class="sxs-lookup"><span data-stu-id="e3960-114">Bring your retail employees together in one central experience to manage tasks, share documents and resolve customer issues.</span></span> <span data-ttu-id="e3960-115">その他のアプリケーションを統合して、シフトの開始と終了&効率化します。</span><span class="sxs-lookup"><span data-stu-id="e3960-115">Integrate additional applications to streamline shift start & end processes.</span></span>

| <span data-ttu-id="e3960-116">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="e3960-116">Base template type</span></span> |<span data-ttu-id="e3960-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="e3960-117">baseTemplateId</span></span> | <span data-ttu-id="e3960-118">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="e3960-118">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="e3960-119">ストアを整理する</span><span class="sxs-lookup"><span data-stu-id="e3960-119">Organize a store</span></span>|`retailStore`|<span data-ttu-id="e3960-120">チャネル:</span><span class="sxs-lookup"><span data-stu-id="e3960-120">Channels:</span></span> <ul><li><span data-ttu-id="e3960-121">一般</span><span class="sxs-lookup"><span data-stu-id="e3960-121">General</span></span><li><span data-ttu-id="e3960-122">Shift の手渡し</span><span class="sxs-lookup"><span data-stu-id="e3960-122">Shift handoff</span></span></li><li><span data-ttu-id="e3960-123">学習</span><span class="sxs-lookup"><span data-stu-id="e3960-123">Learning</span></span></li></ul> <span data-ttu-id="e3960-124">アプリ:</span><span class="sxs-lookup"><span data-stu-id="e3960-124">Apps:</span></span> <ul><li><span data-ttu-id="e3960-125">Wiki</span><span class="sxs-lookup"><span data-stu-id="e3960-125">Wiki</span></span></li></ul>|
||||

## <a name="manager-collaboration"></a><span data-ttu-id="e3960-126">マネージャーの共同作業</span><span class="sxs-lookup"><span data-stu-id="e3960-126">Manager Collaboration</span></span>

<span data-ttu-id="e3960-127">マネージャーの共同作業テンプレートは、複数のマネージャーが店舗や地域をまたがって共同作業を行うチームを作成する場合などに最適です。たとえば、組織に地域がある場合、カリフォルニア地域のマネージャー コラボレーション チームを作成し、その地域のすべての店舗管理者と、その地域の地域マネージャーを含める場合があります。</span><span class="sxs-lookup"><span data-stu-id="e3960-127">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="e3960-128">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="e3960-128">Base template type</span></span>| <span data-ttu-id="e3960-129">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="e3960-129">baseTemplateId</span></span> | <span data-ttu-id="e3960-130">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="e3960-130">Properties that come with this base template</span></span> |
| ------------------|- |----------------------------------------------------- |
|<span data-ttu-id="e3960-131">リテール - マネージャーの共同作業</span><span class="sxs-lookup"><span data-stu-id="e3960-131">Retail - manager collaboration</span></span>|`retailManagerCollaboration` |<span data-ttu-id="e3960-132">チャネル:</span><span class="sxs-lookup"><span data-stu-id="e3960-132">Channels:</span></span> <ul><li><span data-ttu-id="e3960-133">一般</span><span class="sxs-lookup"><span data-stu-id="e3960-133">General</span></span><li><span data-ttu-id="e3960-134">操作</span><span class="sxs-lookup"><span data-stu-id="e3960-134">Operations</span></span></li><li><span data-ttu-id="e3960-135">学習</span><span class="sxs-lookup"><span data-stu-id="e3960-135">Learning</span></span></li></ul> <span data-ttu-id="e3960-136">アプリ:</span><span class="sxs-lookup"><span data-stu-id="e3960-136">Apps:</span></span> <ul><li><span data-ttu-id="e3960-137">Wiki</span><span class="sxs-lookup"><span data-stu-id="e3960-137">Wiki</span></span></li></ul>|
||||
