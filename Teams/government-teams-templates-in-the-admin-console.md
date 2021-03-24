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
ms.openlocfilehash: db22de142b9e7f2bead93e607dd01c9dd362ddba
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092215"
---
# <a name="use-teams-government-templates-in-the-admin-center"></a><span data-ttu-id="ec7c9-104">管理センターで Teams の政府用テンプレートを使用する</span><span class="sxs-lookup"><span data-stu-id="ec7c9-104">Use Teams government templates in the admin center</span></span>

<span data-ttu-id="ec7c9-105">Teams テンプレートでは、設定、チャネル、事前にインストールされたアプリの定義済みテンプレートを使用することで、チームをすばやく簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="ec7c9-105">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="ec7c9-106">Teams テンプレートには、政府のニーズを中心に設計されたチーム構造の定義があらかじめ構築されています。</span><span class="sxs-lookup"><span data-stu-id="ec7c9-106">Teams templates have pre-built definitions of team structures designed around governmental needs.</span></span> <span data-ttu-id="ec7c9-107">Teams テンプレートを拡張して、組織固有のニーズに合わせてチームを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="ec7c9-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="ec7c9-108">この記事では、Teams の各テンプレートについて説明し、その使い方をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ec7c9-108">In this article, we introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="ec7c9-109">この記事は、政府機関全体で複数のチームを計画、展開、管理する責任がある場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ec7c9-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your governmental organization.</span></span> <span data-ttu-id="ec7c9-110">組織内に Teams サービスがすでに展開されています。</span><span class="sxs-lookup"><span data-stu-id="ec7c9-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="ec7c9-111">展開がまだの場合は、「[Microsoft Teams の展開方法](./deploy-overview.md)」をお読みになって展開を開始してください。</span><span class="sxs-lookup"><span data-stu-id="ec7c9-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](./deploy-overview.md).</span></span>

<span data-ttu-id="ec7c9-112">一般的なチーム テンプレートの詳細については、「[Teams テンプレートの使用を開始する](get-started-with-teams-templates-in-the-admin-console.md)」をご参照ください。</span><span class="sxs-lookup"><span data-stu-id="ec7c9-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="coordinate-incident-response"></a><span data-ttu-id="ec7c9-113">インシデントの対応を調整する</span><span class="sxs-lookup"><span data-stu-id="ec7c9-113">Coordinate incident response</span></span>

<span data-ttu-id="ec7c9-114">クライシス管理チームまたはインシデント対応チームのコミュニケーションと重要なリソースを一元管理します。</span><span class="sxs-lookup"><span data-stu-id="ec7c9-114">Centralize communication and critical resources for your crisis management or incident response team.</span></span> <span data-ttu-id="ec7c9-115">このチーム内には、さまざまな種類のファイルを含め、すべてのドキュメントの中心的な場所を作成できます。</span><span class="sxs-lookup"><span data-stu-id="ec7c9-115">Within this team, you can include many different types of files to help create a central place for all your documents.</span></span> <span data-ttu-id="ec7c9-116">オンライン会議を使用して、情報の流れと状況の認識を向上します。</span><span class="sxs-lookup"><span data-stu-id="ec7c9-116">Use online meetings to improve information flow and situational awareness.</span></span>

| <span data-ttu-id="ec7c9-117">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="ec7c9-117">Base template type</span></span> |<span data-ttu-id="ec7c9-118">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="ec7c9-118">baseTemplateId</span></span> | <span data-ttu-id="ec7c9-119">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="ec7c9-119">Properties that come with this base template</span></span> |
|-------------------|-------|---------------------------------------------------------------------------|
|<span data-ttu-id="ec7c9-120">インシデントの対応を調整する</span><span class="sxs-lookup"><span data-stu-id="ec7c9-120">Coordinate incident response</span></span>|`com.microsoft.teams.template.CoordinateIncidentResponse`|<span data-ttu-id="ec7c9-121">チャネル:</span><span class="sxs-lookup"><span data-stu-id="ec7c9-121">Channels:</span></span> <ul><li><span data-ttu-id="ec7c9-122">全般</span><span class="sxs-lookup"><span data-stu-id="ec7c9-122">General</span></span><li><span data-ttu-id="ec7c9-123">お知らせ</span><span class="sxs-lookup"><span data-stu-id="ec7c9-123">Announcements</span></span></li><li><span data-ttu-id="ec7c9-124">物流</span><span class="sxs-lookup"><span data-stu-id="ec7c9-124">Logistics</span></span></li><li><span data-ttu-id="ec7c9-125">計画</span><span class="sxs-lookup"><span data-stu-id="ec7c9-125">Planning</span></span></li><li><span data-ttu-id="ec7c9-126">回復</span><span class="sxs-lookup"><span data-stu-id="ec7c9-126">Recovery</span></span></li><li><span data-ttu-id="ec7c9-127">緊急</span><span class="sxs-lookup"><span data-stu-id="ec7c9-127">Urgent</span></span></li></ul> <span data-ttu-id="ec7c9-128">アプリ:</span><span class="sxs-lookup"><span data-stu-id="ec7c9-128">Apps:</span></span> <ul><li><span data-ttu-id="ec7c9-129">Wiki</span><span class="sxs-lookup"><span data-stu-id="ec7c9-129">Wiki</span></span></li><li><span data-ttu-id="ec7c9-130">Excel</span><span class="sxs-lookup"><span data-stu-id="ec7c9-130">Excel</span></span></li><li><span data-ttu-id="ec7c9-131">OneNote</span><span class="sxs-lookup"><span data-stu-id="ec7c9-131">OneNote</span></span></li><li><span data-ttu-id="ec7c9-132">SharePoint</span><span class="sxs-lookup"><span data-stu-id="ec7c9-132">SharePoint</span></span></li><li><span data-ttu-id="ec7c9-133">プランナー</span><span class="sxs-lookup"><span data-stu-id="ec7c9-133">Planner</span></span></li></ul>|
||||