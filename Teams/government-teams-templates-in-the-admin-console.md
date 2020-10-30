---
title: 管理センターで Teams government テンプレートを使用する
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
description: 使い方については、こちらを参照してください。 管理センターを使って、事前に定義された設定、チャネル、プリインストール済みのアプリを提供することで、行政機関向けに設計されたチーム構造を作成する Teams テンプレート。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 513b83fdab26d73b42bed692b5ea887629fc1851
ms.sourcegitcommit: bc471f18e40e37456edc9696e11b175581847617
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "48800630"
---
# <a name="use-teams-government-templates-in-the-admin-center"></a><span data-ttu-id="55cca-104">管理センターで Teams government テンプレートを使用する</span><span class="sxs-lookup"><span data-stu-id="55cca-104">Use Teams government templates in the admin center</span></span>

<span data-ttu-id="55cca-105">Teams テンプレートを使用すると、設定、チャネル、プリインストールされているアプリに定義済みのテンプレートを提供して、チームをすばやく簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="55cca-105">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="55cca-106">Teams テンプレートには、行政機関のニーズに合わせて設計されたチーム構造の事前定義が含まれています。</span><span class="sxs-lookup"><span data-stu-id="55cca-106">Teams templates have pre-built definitions of team structures designed around governmental needs.</span></span> <span data-ttu-id="55cca-107">また、チームテンプレートを拡張して、特定の組織のニーズに合わせてカスタマイズされたチームを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="55cca-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="55cca-108">この記事では、各チームテンプレートを紹介し、その使い方をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="55cca-108">In this article, we introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="55cca-109">この記事は、組織内の複数のチームの計画、展開、管理を担当しているユーザーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="55cca-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your governmental organization.</span></span> <span data-ttu-id="55cca-110">組織に Teams サービスを既に展開している。</span><span class="sxs-lookup"><span data-stu-id="55cca-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="55cca-111">まだチームをロールアウトしていない場合は、「 [Microsoft teams をロールアウトする方法](How-to-roll-out-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55cca-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="55cca-112">チームテンプレート全般の詳細については、「 [チームテンプレートの概要](get-started-with-teams-templates-in-the-admin-console.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55cca-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="coordinate-incident-response"></a><span data-ttu-id="55cca-113">インシデント応答の調整</span><span class="sxs-lookup"><span data-stu-id="55cca-113">Coordinate incident response</span></span>

<span data-ttu-id="55cca-114">緊急管理またはインシデント対応チームのコミュニケーションと重要なリソースを一元管理します。</span><span class="sxs-lookup"><span data-stu-id="55cca-114">Centralize communication and critical resources for your crisis management or incident response team.</span></span> <span data-ttu-id="55cca-115">このチームでは、さまざまな種類のファイルを用意して、すべてのドキュメントの一元的な場所を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="55cca-115">Within this team, you can include many different types of files to help create a central place for all your documents.</span></span> <span data-ttu-id="55cca-116">オンライン会議を使って、情報フローと状況に関する認識を向上させます。</span><span class="sxs-lookup"><span data-stu-id="55cca-116">Use online meetings to improve information flow and situational awareness.</span></span>

| <span data-ttu-id="55cca-117">ベーステンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="55cca-117">Base template type</span></span> |<span data-ttu-id="55cca-118">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="55cca-118">baseTemplateId</span></span> | <span data-ttu-id="55cca-119">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="55cca-119">Properties that come with this base template</span></span> |
|-------------------|-------|---------------------------------------------------------------------------|
|<span data-ttu-id="55cca-120">インシデント応答の調整</span><span class="sxs-lookup"><span data-stu-id="55cca-120">Coordinate incident response</span></span>|`com.microsoft.teams.template.CoordinateIncidentResponse` |<span data-ttu-id="55cca-121">チャネル</span><span class="sxs-lookup"><span data-stu-id="55cca-121">Channels:</span></span> <ul><li><span data-ttu-id="55cca-122">一般</span><span class="sxs-lookup"><span data-stu-id="55cca-122">General</span></span><li><span data-ttu-id="55cca-123">お知らせ</span><span class="sxs-lookup"><span data-stu-id="55cca-123">Announcements</span></span></li><li><span data-ttu-id="55cca-124">物流</span><span class="sxs-lookup"><span data-stu-id="55cca-124">Logistics</span></span></li><li><span data-ttu-id="55cca-125">計画</span><span class="sxs-lookup"><span data-stu-id="55cca-125">Planning</span></span></li><li><span data-ttu-id="55cca-126">Recovery</span><span class="sxs-lookup"><span data-stu-id="55cca-126">Recovery</span></span></li><li><span data-ttu-id="55cca-127">度</span><span class="sxs-lookup"><span data-stu-id="55cca-127">Urgent</span></span></li></ul> <span data-ttu-id="55cca-128">アプリ</span><span class="sxs-lookup"><span data-stu-id="55cca-128">Apps:</span></span> <ul><li><span data-ttu-id="55cca-129">ウィキ</span><span class="sxs-lookup"><span data-stu-id="55cca-129">Wiki</span></span></li><li><span data-ttu-id="55cca-130">Excel</span><span class="sxs-lookup"><span data-stu-id="55cca-130">Excel</span></span></li><li><span data-ttu-id="55cca-131">OneNote</span><span class="sxs-lookup"><span data-stu-id="55cca-131">OneNote</span></span></li><li><span data-ttu-id="55cca-132">SharePoint</span><span class="sxs-lookup"><span data-stu-id="55cca-132">SharePoint</span></span></li><li><span data-ttu-id="55cca-133">プランナー</span><span class="sxs-lookup"><span data-stu-id="55cca-133">Planner</span></span></li></ul>|
||||