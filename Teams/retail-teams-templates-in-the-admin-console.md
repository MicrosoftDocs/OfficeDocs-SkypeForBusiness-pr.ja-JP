---
title: 管理センターで小売業向けの Teams テンプレートを使用する
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
description: 管理センターを使用して定義済みの設定、チャネル、および事前にインストールされたアプリを提供することで、小売業者のニーズに合わせて設計されたチーム構造を作成する Teams テンプレートの使用方法を説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: a63602f07e0c248b4decbc733e41b16fdafc3911
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117615"
---
# <a name="use-teams-retail-templates-in-the-admin-center"></a><span data-ttu-id="09005-103">管理センターで小売業向けの Teams テンプレートを使用する</span><span class="sxs-lookup"><span data-stu-id="09005-103">Use Teams retail templates in the admin center</span></span>

<span data-ttu-id="09005-104">Teams テンプレートでは、設定、チャネル、事前にインストールされたアプリの定義済みテンプレートを使用することで、チームをすばやく簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="09005-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="09005-105">Teams テンプレートには、小売業者のニーズに基づいて設計されたチーム構造の定義が事前に作成されています。</span><span class="sxs-lookup"><span data-stu-id="09005-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="09005-106">Teams テンプレートを使用すると、小売業者にとって適切なチームの種類をすばやく作成し、組織全体に展開できます。</span><span class="sxs-lookup"><span data-stu-id="09005-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="09005-107">Teams テンプレートを拡張して、組織固有のニーズに合わせてチームを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="09005-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="09005-108">この記事では、各 Teams テンプレートと、それらの使用を推奨する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="09005-108">In this article, we'll introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="09005-109">この記事は、小売業の組織全体で複数のチームを計画、展開し、管理する責任があるユーザーに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="09005-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="09005-110">組織内に Teams サービスがすでに展開されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="09005-110">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="09005-111">展開がまだの場合は、「[Microsoft Teams の展開方法](./deploy-overview.md)」をお読みになって展開を開始してください。</span><span class="sxs-lookup"><span data-stu-id="09005-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](./deploy-overview.md).</span></span>

<span data-ttu-id="09005-112">一般的なチーム テンプレートの詳細については、「[Teams テンプレートの使用を開始する](get-started-with-teams-templates-in-the-admin-console.md)」をご参照ください。</span><span class="sxs-lookup"><span data-stu-id="09005-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="organize-a-store"></a><span data-ttu-id="09005-113">店舗を整理する</span><span class="sxs-lookup"><span data-stu-id="09005-113">Organize a store</span></span>

<span data-ttu-id="09005-114">小売業の従業員を 1 つのエクスペリエンスにまとめ、タスクの管理、ドキュメントの共有、およびお客様の問題の解決を行います。</span><span class="sxs-lookup"><span data-stu-id="09005-114">Bring your retail employees together in one central experience to manage tasks, share documents and resolve customer issues.</span></span> <span data-ttu-id="09005-115">追加のアプリケーションを統合して、シフトの開始と終了のプロセスを合理化します。</span><span class="sxs-lookup"><span data-stu-id="09005-115">Integrate additional applications to streamline shift start & end processes.</span></span>

| <span data-ttu-id="09005-116">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="09005-116">Base template type</span></span> |<span data-ttu-id="09005-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="09005-117">baseTemplateId</span></span> | <span data-ttu-id="09005-118">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="09005-118">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="09005-119">店舗を整理する</span><span class="sxs-lookup"><span data-stu-id="09005-119">Organize a store</span></span>|`retailStore`|<span data-ttu-id="09005-120">チャネル:</span><span class="sxs-lookup"><span data-stu-id="09005-120">Channels:</span></span> <ul><li><span data-ttu-id="09005-121">全般</span><span class="sxs-lookup"><span data-stu-id="09005-121">General</span></span><li><span data-ttu-id="09005-122">シフトのハンドオフ</span><span class="sxs-lookup"><span data-stu-id="09005-122">Shift handoff</span></span></li><li><span data-ttu-id="09005-123">学習</span><span class="sxs-lookup"><span data-stu-id="09005-123">Learning</span></span></li></ul> <span data-ttu-id="09005-124">アプリ:</span><span class="sxs-lookup"><span data-stu-id="09005-124">Apps:</span></span> <ul><li><span data-ttu-id="09005-125">Wiki</span><span class="sxs-lookup"><span data-stu-id="09005-125">Wiki</span></span></li></ul>|
||||

## <a name="manager-collaboration"></a><span data-ttu-id="09005-126">マネージャー コラボレーション</span><span class="sxs-lookup"><span data-stu-id="09005-126">Manager Collaboration</span></span>

<span data-ttu-id="09005-127">マネージャー コラボレーションのテンプレートは、マネージャーのグループが店舗や地域間でコラボレーションするためのチームを作成する場合などに最適です。たとえば、組織に地域別のグループがある場合、カリフォルニア地域のマネージャー コラボレーション チームを作成し、その地域のすべての店舗マネージャーと、その地域の地域マネージャーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="09005-127">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="09005-128">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="09005-128">Base template type</span></span>| <span data-ttu-id="09005-129">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="09005-129">baseTemplateId</span></span> | <span data-ttu-id="09005-130">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="09005-130">Properties that come with this base template</span></span> |
| ------------------|- |----------------------------------------------------- |
|<span data-ttu-id="09005-131">小売業 - マネージャー コラボレーション</span><span class="sxs-lookup"><span data-stu-id="09005-131">Retail - manager collaboration</span></span>|`retailManagerCollaboration` |<span data-ttu-id="09005-132">チャネル:</span><span class="sxs-lookup"><span data-stu-id="09005-132">Channels:</span></span> <ul><li><span data-ttu-id="09005-133">全般</span><span class="sxs-lookup"><span data-stu-id="09005-133">General</span></span><li><span data-ttu-id="09005-134">操作</span><span class="sxs-lookup"><span data-stu-id="09005-134">Operations</span></span></li><li><span data-ttu-id="09005-135">学習</span><span class="sxs-lookup"><span data-stu-id="09005-135">Learning</span></span></li></ul> <span data-ttu-id="09005-136">アプリ:</span><span class="sxs-lookup"><span data-stu-id="09005-136">Apps:</span></span> <ul><li><span data-ttu-id="09005-137">Wiki</span><span class="sxs-lookup"><span data-stu-id="09005-137">Wiki</span></span></li></ul>|
||||