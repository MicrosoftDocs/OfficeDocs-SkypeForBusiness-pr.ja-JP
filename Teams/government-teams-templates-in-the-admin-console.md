---
title: 管理センターで政府機関のチーム テンプレートを使用する
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
description: 管理センターを使用して定義済みの設定、チャネル、およびプレインストールされたアプリを提供することで、チーム テンプレートを使用して政府のニーズに合ったチーム構造を作成する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: ff975fc80c0b08136fa18d2b7c31cd100e405911
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684534"
---
# <a name="use-government-team-templates-in-the-admin-center"></a><span data-ttu-id="3a831-103">管理センターで政府機関のチーム テンプレートを使用する</span><span class="sxs-lookup"><span data-stu-id="3a831-103">Use government team templates in the admin center</span></span>

<span data-ttu-id="3a831-104">チーム テンプレートを使用すると、設定、チャネル、およびプレインストールされたアプリの定義済みのテンプレートを提供することで、チームをすばやく簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="3a831-104">Team templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="3a831-105">チーム テンプレートには、政府のニーズを中心に設計されたチーム構造の事前構築された定義があります。</span><span class="sxs-lookup"><span data-stu-id="3a831-105">Team templates have pre-built definitions of team structures designed around governmental needs.</span></span> <span data-ttu-id="3a831-106">また、チーム テンプレートを拡張して、特定の組織のニーズに合わせて調整されたチームを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="3a831-106">You can also extend the team templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="3a831-107">この記事では、各チーム テンプレートを紹介し、その使い方をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3a831-107">In this article, we introduce each of the team templates and recommend how to use them.</span></span>

<span data-ttu-id="3a831-108">この記事は、政府組織全体で複数のチームを計画、デプロイ、管理する責任がある場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3a831-108">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your governmental organization.</span></span> <span data-ttu-id="3a831-109">組織内に Teams サービスがすでに展開されています。</span><span class="sxs-lookup"><span data-stu-id="3a831-109">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="3a831-110">展開がまだの場合は、「[Microsoft Teams の展開方法](./deploy-overview.md)」をお読みになって展開を開始してください。</span><span class="sxs-lookup"><span data-stu-id="3a831-110">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](./deploy-overview.md).</span></span>

<span data-ttu-id="3a831-111">チーム テンプレート全般の詳細については、「チーム テンプレートの概要 [」を参照してください](get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="3a831-111">To learn more about team templates in general, refer to [Get started with team templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="coordinate-incident-response"></a><span data-ttu-id="3a831-112">インシデント対応を調整する</span><span class="sxs-lookup"><span data-stu-id="3a831-112">Coordinate incident response</span></span>

<span data-ttu-id="3a831-113">危機管理チームまたはインシデント対応チームのコミュニケーションと重要なリソースを一元化します。</span><span class="sxs-lookup"><span data-stu-id="3a831-113">Centralize communication and critical resources for your crisis management or incident response team.</span></span> <span data-ttu-id="3a831-114">このチーム内には、さまざまな種類のファイルを含め、すべてのドキュメントの中心的な場所を作成できます。</span><span class="sxs-lookup"><span data-stu-id="3a831-114">Within this team, you can include many different types of files to help create a central place for all your documents.</span></span> <span data-ttu-id="3a831-115">オンライン会議を使用して、情報フローと状況認識を向上します。</span><span class="sxs-lookup"><span data-stu-id="3a831-115">Use online meetings to improve information flow and situational awareness.</span></span>

| <span data-ttu-id="3a831-116">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="3a831-116">Base template type</span></span> |<span data-ttu-id="3a831-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="3a831-117">baseTemplateId</span></span> | <span data-ttu-id="3a831-118">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="3a831-118">Properties that come with this base template</span></span> |
|-------------------|-------|---------------------------------------------------------------------------|
|<span data-ttu-id="3a831-119">インシデント対応を調整する</span><span class="sxs-lookup"><span data-stu-id="3a831-119">Coordinate incident response</span></span>|`com.microsoft.teams.template.CoordinateIncidentResponse`|<span data-ttu-id="3a831-120">チャネル</span><span class="sxs-lookup"><span data-stu-id="3a831-120">Channels:</span></span> <ul><li><span data-ttu-id="3a831-121">全般</span><span class="sxs-lookup"><span data-stu-id="3a831-121">General</span></span><li><span data-ttu-id="3a831-122">お知らせ</span><span class="sxs-lookup"><span data-stu-id="3a831-122">Announcements</span></span></li><li><span data-ttu-id="3a831-123">物流</span><span class="sxs-lookup"><span data-stu-id="3a831-123">Logistics</span></span></li><li><span data-ttu-id="3a831-124">計画</span><span class="sxs-lookup"><span data-stu-id="3a831-124">Planning</span></span></li><li><span data-ttu-id="3a831-125">回復</span><span class="sxs-lookup"><span data-stu-id="3a831-125">Recovery</span></span></li><li><span data-ttu-id="3a831-126">緊急</span><span class="sxs-lookup"><span data-stu-id="3a831-126">Urgent</span></span></li></ul> <span data-ttu-id="3a831-127">アプリ:</span><span class="sxs-lookup"><span data-stu-id="3a831-127">Apps:</span></span> <ul><li><span data-ttu-id="3a831-128">Wiki</span><span class="sxs-lookup"><span data-stu-id="3a831-128">Wiki</span></span></li><li><span data-ttu-id="3a831-129">Excel</span><span class="sxs-lookup"><span data-stu-id="3a831-129">Excel</span></span></li><li><span data-ttu-id="3a831-130">OneNote</span><span class="sxs-lookup"><span data-stu-id="3a831-130">OneNote</span></span></li><li><span data-ttu-id="3a831-131">SharePoint</span><span class="sxs-lookup"><span data-stu-id="3a831-131">SharePoint</span></span></li><li><span data-ttu-id="3a831-132">プランナー</span><span class="sxs-lookup"><span data-stu-id="3a831-132">Planner</span></span></li></ul>|
||||