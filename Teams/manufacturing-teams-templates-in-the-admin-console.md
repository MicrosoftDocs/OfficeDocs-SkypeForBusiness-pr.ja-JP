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
description: 使い方について学習します。 管理センターを使用して定義済みの設定、チャネル、およびプレインストールされたアプリを提供することで、製造ニーズに合って設計されたチーム構造を作成する Teams テンプレート。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 51a28e997e5c7c0b36fb49cd0bb46768b7808a29
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662222"
---
# <a name="use-teams-manufacturing-templates-in-the-admin-center"></a><span data-ttu-id="b209d-104">管理センターで Teams 製造テンプレートを使用する</span><span class="sxs-lookup"><span data-stu-id="b209d-104">Use Teams manufacturing templates in the admin center</span></span>

<span data-ttu-id="b209d-105">Teams テンプレートを使用すると、設定、チャネル、およびプレインストールされているアプリの定義済みのテンプレートを提供することで、チームをすばやく簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="b209d-105">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="b209d-106">Teams テンプレートには、製造のニーズを中心に設計されたチーム構造の定義があらかじめ組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="b209d-106">Teams templates have pre-built definitions of team structures designed around manufacturing needs.</span></span> <span data-ttu-id="b209d-107">また、Teams テンプレートを拡張して、組織の特定のニーズに合わせてカスタマイズされたチームを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="b209d-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="b209d-108">この記事では、Teams の各テンプレートについて説明し、その使い方をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b209d-108">In this article, we introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="b209d-109">この記事は、製造組織全体で複数のチームを計画、展開、管理する責任がある場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b209d-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your manufacturing organization.</span></span> <span data-ttu-id="b209d-110">既に Teams サービスを組織に展開しています。</span><span class="sxs-lookup"><span data-stu-id="b209d-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="b209d-111">Teams をまだ展開していない場合は、まず、Microsoft Teams を展開する方法 [を参照してください](How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="b209d-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="b209d-112">チーム テンプレート全般の詳細については、「Teams テンプレートの使用を開始する [」を参照してください](get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="b209d-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="quality-and-safety"></a><span data-ttu-id="b209d-113">品質と安全性</span><span class="sxs-lookup"><span data-stu-id="b209d-113">Quality and safety</span></span>

<span data-ttu-id="b209d-114">製造工場チームとのコミュニケーション、リソースへのアクセス、および工場運営を一元管理します。</span><span class="sxs-lookup"><span data-stu-id="b209d-114">Centralize communication, access to resources, and plant operations with a Manufacturing Plant team.</span></span> <span data-ttu-id="b209d-115">ポリシーと手順のドキュメント、トレーニング ビデオ、安全性に関する通知、シフトの引き渡しプロセスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b209d-115">Include policy and procedure documents, training videos, safety notices, shift handover processes.</span></span>

| <span data-ttu-id="b209d-116">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="b209d-116">Base template type</span></span>|<span data-ttu-id="b209d-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="b209d-117">baseTemplateId</span></span>| <span data-ttu-id="b209d-118">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="b209d-118">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="b209d-119">品質と安全性</span><span class="sxs-lookup"><span data-stu-id="b209d-119">Quality and safety</span></span>|`com.microsoft.teams.template.QualitySafety` |<span data-ttu-id="b209d-120">チャネル:</span><span class="sxs-lookup"><span data-stu-id="b209d-120">Channels:</span></span> <ul><li><span data-ttu-id="b209d-121">一般</span><span class="sxs-lookup"><span data-stu-id="b209d-121">General</span></span><li><span data-ttu-id="b209d-122">お知らせ</span><span class="sxs-lookup"><span data-stu-id="b209d-122">Announcements</span></span></li><li><span data-ttu-id="b209d-123">行 1</span><span class="sxs-lookup"><span data-stu-id="b209d-123">Line 1</span></span></li><li><span data-ttu-id="b209d-124">行 2</span><span class="sxs-lookup"><span data-stu-id="b209d-124">Line 2</span></span></li><li><span data-ttu-id="b209d-125">行 3</span><span class="sxs-lookup"><span data-stu-id="b209d-125">Line 3</span></span></li><li><span data-ttu-id="b209d-126">安全性</span><span class="sxs-lookup"><span data-stu-id="b209d-126">Safety</span></span></li><li><span data-ttu-id="b209d-127">トレーニング</span><span class="sxs-lookup"><span data-stu-id="b209d-127">Training</span></span></li><li><span data-ttu-id="b209d-128">メンテナンス</span><span class="sxs-lookup"><span data-stu-id="b209d-128">Maintenance</span></span></li><li><span data-ttu-id="b209d-129">楽しい情報</span><span class="sxs-lookup"><span data-stu-id="b209d-129">Fun stuff</span></span></li></ul> <span data-ttu-id="b209d-130">アプリ:</span><span class="sxs-lookup"><span data-stu-id="b209d-130">Apps:</span></span> <ul><li><span data-ttu-id="b209d-131">Wiki</span><span class="sxs-lookup"><span data-stu-id="b209d-131">Wiki</span></span></li><li><span data-ttu-id="b209d-132">プランナー</span><span class="sxs-lookup"><span data-stu-id="b209d-132">Planner</span></span></li></ul>|
||||
