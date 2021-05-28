---
title: 管理センターで製造チーム テンプレートの使用を開始する
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
description: 管理センターを使用して定義済みの設定、チャネル、およびプレインストールされたアプリを提供することで、チーム テンプレートを使用して製造ニーズに合ったチーム構造を作成する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: ec27cba4336d86f51a32582440d5d7902ffca2b9
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684484"
---
# <a name="use-manufacturing-team-templates-in-the-admin-center"></a><span data-ttu-id="e3277-103">管理センターで製造チーム テンプレートを使用する</span><span class="sxs-lookup"><span data-stu-id="e3277-103">Use manufacturing team templates in the admin center</span></span>

<span data-ttu-id="e3277-104">チーム テンプレートを使用すると、設定、チャネル、およびプレインストールされたアプリの定義済みのテンプレートを提供することで、チームをすばやく簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="e3277-104">Team templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="e3277-105">チーム テンプレートには、製造ニーズを中心に設計されたチーム構造の定義が事前に構築されています。</span><span class="sxs-lookup"><span data-stu-id="e3277-105">Team templates have pre-built definitions of team structures designed around manufacturing needs.</span></span> <span data-ttu-id="e3277-106">また、チーム テンプレートを拡張して、特定の組織のニーズに合わせて調整されたチームを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="e3277-106">You can also extend the team templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="e3277-107">この記事では、各チーム テンプレートを紹介し、その使い方をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e3277-107">In this article, we introduce each of the team templates and recommend how to use them.</span></span>

<span data-ttu-id="e3277-108">この記事は、製造組織全体で複数のチームを計画、デプロイ、管理する責任がある場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e3277-108">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your manufacturing organization.</span></span> <span data-ttu-id="e3277-109">組織内に Teams サービスがすでに展開されています。</span><span class="sxs-lookup"><span data-stu-id="e3277-109">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="e3277-110">展開がまだの場合は、「[Microsoft Teams の展開方法](./deploy-overview.md)」をお読みになって展開を開始してください。</span><span class="sxs-lookup"><span data-stu-id="e3277-110">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](./deploy-overview.md).</span></span>

<span data-ttu-id="e3277-111">チーム テンプレート全般の詳細については、「チーム テンプレートの概要 [」を参照してください](get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="e3277-111">To learn more about team templates in general, refer to [Get started with team templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="quality-and-safety"></a><span data-ttu-id="e3277-112">品質と安全性</span><span class="sxs-lookup"><span data-stu-id="e3277-112">Quality and safety</span></span>

<span data-ttu-id="e3277-113">製造工場チームとの通信、リソースへのアクセス、および工場の運用を一元化します。</span><span class="sxs-lookup"><span data-stu-id="e3277-113">Centralize communication, access to resources, and plant operations with a Manufacturing Plant team.</span></span> <span data-ttu-id="e3277-114">ポリシーと手順のドキュメント、トレーニング ビデオ、安全性に関する通知、シフト引き渡しプロセスを含める。</span><span class="sxs-lookup"><span data-stu-id="e3277-114">Include policy and procedure documents, training videos, safety notices, shift handover processes.</span></span>

| <span data-ttu-id="e3277-115">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="e3277-115">Base template type</span></span>|<span data-ttu-id="e3277-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="e3277-116">baseTemplateId</span></span>| <span data-ttu-id="e3277-117">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="e3277-117">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="e3277-118">品質と安全性</span><span class="sxs-lookup"><span data-stu-id="e3277-118">Quality and safety</span></span>|`com.microsoft.teams.template.QualitySafety` |<span data-ttu-id="e3277-119">チャネル</span><span class="sxs-lookup"><span data-stu-id="e3277-119">Channels:</span></span> <ul><li><span data-ttu-id="e3277-120">全般</span><span class="sxs-lookup"><span data-stu-id="e3277-120">General</span></span><li><span data-ttu-id="e3277-121">お知らせ</span><span class="sxs-lookup"><span data-stu-id="e3277-121">Announcements</span></span></li><li><span data-ttu-id="e3277-122">1 行目</span><span class="sxs-lookup"><span data-stu-id="e3277-122">Line 1</span></span></li><li><span data-ttu-id="e3277-123">2 行目</span><span class="sxs-lookup"><span data-stu-id="e3277-123">Line 2</span></span></li><li><span data-ttu-id="e3277-124">3 行目</span><span class="sxs-lookup"><span data-stu-id="e3277-124">Line 3</span></span></li><li><span data-ttu-id="e3277-125">安全性</span><span class="sxs-lookup"><span data-stu-id="e3277-125">Safety</span></span></li><li><span data-ttu-id="e3277-126">トレーニング</span><span class="sxs-lookup"><span data-stu-id="e3277-126">Training</span></span></li><li><span data-ttu-id="e3277-127">メンテナンス</span><span class="sxs-lookup"><span data-stu-id="e3277-127">Maintenance</span></span></li><li><span data-ttu-id="e3277-128">楽しい情報</span><span class="sxs-lookup"><span data-stu-id="e3277-128">Fun stuff</span></span></li></ul> <span data-ttu-id="e3277-129">アプリ:</span><span class="sxs-lookup"><span data-stu-id="e3277-129">Apps:</span></span> <ul><li><span data-ttu-id="e3277-130">Wiki</span><span class="sxs-lookup"><span data-stu-id="e3277-130">Wiki</span></span></li><li><span data-ttu-id="e3277-131">プランナー</span><span class="sxs-lookup"><span data-stu-id="e3277-131">Planner</span></span></li></ul>|
||||