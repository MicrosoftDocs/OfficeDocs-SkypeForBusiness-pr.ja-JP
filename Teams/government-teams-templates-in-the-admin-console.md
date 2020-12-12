---
title: 管理センターで Teams の政府用テンプレートを使用する
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
description: 使い方について学習します。 管理センターを使用して定義済みの設定、チャネル、およびプレインストールされたアプリを提供することで、政府のニーズに合って設計されたチーム構造を作成する Teams テンプレート。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: db0d8fa4a2744f0f3c3591918230e3f569727ae7
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662202"
---
# <a name="use-teams-government-templates-in-the-admin-center"></a><span data-ttu-id="8b36f-104">管理センターで Teams の政府用テンプレートを使用する</span><span class="sxs-lookup"><span data-stu-id="8b36f-104">Use Teams government templates in the admin center</span></span>

<span data-ttu-id="8b36f-105">Teams テンプレートを使用すると、設定、チャネル、およびプレインストールされているアプリの定義済みのテンプレートを提供することで、チームをすばやく簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="8b36f-105">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="8b36f-106">Teams テンプレートには、政府のニーズを中心に設計されたチーム構造の定義があらかじめ構築されています。</span><span class="sxs-lookup"><span data-stu-id="8b36f-106">Teams templates have pre-built definitions of team structures designed around governmental needs.</span></span> <span data-ttu-id="8b36f-107">また、Teams テンプレートを拡張して、組織の特定のニーズに合わせてカスタマイズされたチームを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="8b36f-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="8b36f-108">この記事では、Teams の各テンプレートについて説明し、その使い方をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8b36f-108">In this article, we introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="8b36f-109">この記事は、政府機関全体で複数のチームを計画、展開、管理する責任がある場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8b36f-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your governmental organization.</span></span> <span data-ttu-id="8b36f-110">Teams サービスは既に組織に展開されています。</span><span class="sxs-lookup"><span data-stu-id="8b36f-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="8b36f-111">Teams をまだ展開していない場合は、まず、Microsoft Teams を展開する方法 [を参照してください](How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="8b36f-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="8b36f-112">チーム テンプレート全般の詳細については、「Teams テンプレートの使用を開始する [」を参照してください](get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="8b36f-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="coordinate-incident-response"></a><span data-ttu-id="8b36f-113">インシデントの対応を調整する</span><span class="sxs-lookup"><span data-stu-id="8b36f-113">Coordinate incident response</span></span>

<span data-ttu-id="8b36f-114">クライシス管理チームまたはインシデント対応チームのコミュニケーションと重要なリソースを一元管理します。</span><span class="sxs-lookup"><span data-stu-id="8b36f-114">Centralize communication and critical resources for your crisis management or incident response team.</span></span> <span data-ttu-id="8b36f-115">このチーム内で、さまざまな種類のファイルを含め、すべてのドキュメントの中心的な場所を作成できます。</span><span class="sxs-lookup"><span data-stu-id="8b36f-115">Within this team, you can include many different types of files to help create a central place for all your documents.</span></span> <span data-ttu-id="8b36f-116">オンライン会議を使用して、情報の流れと状況の認識を向上します。</span><span class="sxs-lookup"><span data-stu-id="8b36f-116">Use online meetings to improve information flow and situational awareness.</span></span>

| <span data-ttu-id="8b36f-117">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="8b36f-117">Base template type</span></span> |<span data-ttu-id="8b36f-118">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="8b36f-118">baseTemplateId</span></span> | <span data-ttu-id="8b36f-119">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="8b36f-119">Properties that come with this base template</span></span> |
|-------------------|-------|---------------------------------------------------------------------------|
|<span data-ttu-id="8b36f-120">インシデントの対応を調整する</span><span class="sxs-lookup"><span data-stu-id="8b36f-120">Coordinate incident response</span></span>|`com.microsoft.teams.template.CoordinateIncidentResponse`|<span data-ttu-id="8b36f-121">チャネル:</span><span class="sxs-lookup"><span data-stu-id="8b36f-121">Channels:</span></span> <ul><li><span data-ttu-id="8b36f-122">一般</span><span class="sxs-lookup"><span data-stu-id="8b36f-122">General</span></span><li><span data-ttu-id="8b36f-123">お知らせ</span><span class="sxs-lookup"><span data-stu-id="8b36f-123">Announcements</span></span></li><li><span data-ttu-id="8b36f-124">物流</span><span class="sxs-lookup"><span data-stu-id="8b36f-124">Logistics</span></span></li><li><span data-ttu-id="8b36f-125">計画</span><span class="sxs-lookup"><span data-stu-id="8b36f-125">Planning</span></span></li><li><span data-ttu-id="8b36f-126">回復</span><span class="sxs-lookup"><span data-stu-id="8b36f-126">Recovery</span></span></li><li><span data-ttu-id="8b36f-127">緊急</span><span class="sxs-lookup"><span data-stu-id="8b36f-127">Urgent</span></span></li></ul> <span data-ttu-id="8b36f-128">アプリ:</span><span class="sxs-lookup"><span data-stu-id="8b36f-128">Apps:</span></span> <ul><li><span data-ttu-id="8b36f-129">Wiki</span><span class="sxs-lookup"><span data-stu-id="8b36f-129">Wiki</span></span></li><li><span data-ttu-id="8b36f-130">Excel</span><span class="sxs-lookup"><span data-stu-id="8b36f-130">Excel</span></span></li><li><span data-ttu-id="8b36f-131">OneNote</span><span class="sxs-lookup"><span data-stu-id="8b36f-131">OneNote</span></span></li><li><span data-ttu-id="8b36f-132">SharePoint</span><span class="sxs-lookup"><span data-stu-id="8b36f-132">SharePoint</span></span></li><li><span data-ttu-id="8b36f-133">プランナー</span><span class="sxs-lookup"><span data-stu-id="8b36f-133">Planner</span></span></li></ul>|
||||