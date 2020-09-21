---
title: 管理コンソールで Teams 製造テンプレートの使用を開始する
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
description: 管理コンソールを使用して、定義済みの設定、チャネル、事前にインストールされたアプリを提供することで、チームテンプレートを使用して製造ニーズに合わせて設計されたチーム構造を作成する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 896435daaf7b1036a54649e8670b0a19d88b2474
ms.sourcegitcommit: 448606977ee67befbdc91060363cf90dd346a528
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2020
ms.locfileid: "48136063"
---
# <a name="use-teams-manufacturing-templates-in-the-admin-console"></a><span data-ttu-id="4837c-103">管理コンソールで Teams 製造テンプレートを使用する</span><span class="sxs-lookup"><span data-stu-id="4837c-103">Use Teams manufacturing templates in the admin console</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

<span data-ttu-id="4837c-104">Teams テンプレートを使用すると、設定、チャネル、プリインストールされているアプリに定義済みのテンプレートを提供して、チームをすばやく簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="4837c-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="4837c-105">チームテンプレートには、製造ニーズに合わせて設計されたチーム構造の事前定義が用意されています。</span><span class="sxs-lookup"><span data-stu-id="4837c-105">Teams templates have pre-built definitions of team structures designed around manufacturing needs.</span></span> <span data-ttu-id="4837c-106">また、チームテンプレートを拡張して、特定の組織のニーズに合わせてカスタマイズされたチームを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="4837c-106">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="4837c-107">この記事では、各チームテンプレートを紹介し、その使用をお勧めする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4837c-107">In this article, we will introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="4837c-108">この記事は、製造組織全体で複数のチームの計画、展開、管理を担当している場合に使います。</span><span class="sxs-lookup"><span data-stu-id="4837c-108">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your manufacturing organization.</span></span> <span data-ttu-id="4837c-109">組織に Teams サービスを既に展開していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="4837c-109">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="4837c-110">まだチームをロールアウトしていない場合は、「 [Microsoft teams をロールアウトする方法](How-to-roll-out-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4837c-110">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="4837c-111">チームテンプレートの詳細については、「 [チームテンプレートの使用を開始](get-started-with-teams-templates-in-the-admin-console.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4837c-111">To learn more about team templates in general, please refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="quality-and-safety"></a><span data-ttu-id="4837c-112">品質と安全性</span><span class="sxs-lookup"><span data-stu-id="4837c-112">Quality and safety</span></span>

<span data-ttu-id="4837c-113">製造プラントチームとのコミュニケーション、リソースへのアクセス、プラント操作の一元管理。</span><span class="sxs-lookup"><span data-stu-id="4837c-113">Centralize communication, access to resources, and plant operations with a Manufacturing Plant team.</span></span> <span data-ttu-id="4837c-114">ポリシーと手続きドキュメント、トレーニングビデオ、安全性の通知、移行プロセスのシフトを含めます。</span><span class="sxs-lookup"><span data-stu-id="4837c-114">Include policy and procedure documents, training videos, safety notices, shift handover processes.</span></span>

| <span data-ttu-id="4837c-115">ベーステンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="4837c-115">Base template type</span></span>|<span data-ttu-id="4837c-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="4837c-116">baseTemplateId</span></span> | <span data-ttu-id="4837c-117">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="4837c-117">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="4837c-118">品質と安全性</span><span class="sxs-lookup"><span data-stu-id="4837c-118">Quality and safety</span></span>|`com.microsoft.teams.template.QualitySafety` |<span data-ttu-id="4837c-119">チャネル</span><span class="sxs-lookup"><span data-stu-id="4837c-119">Channels:</span></span> <ul><li><span data-ttu-id="4837c-120">一般</span><span class="sxs-lookup"><span data-stu-id="4837c-120">General</span></span><li><span data-ttu-id="4837c-121">お知らせ</span><span class="sxs-lookup"><span data-stu-id="4837c-121">Announcements</span></span></li><li><span data-ttu-id="4837c-122">行1</span><span class="sxs-lookup"><span data-stu-id="4837c-122">Line 1</span></span></li><li><span data-ttu-id="4837c-123">2行目</span><span class="sxs-lookup"><span data-stu-id="4837c-123">Line 2</span></span></li><li><span data-ttu-id="4837c-124">行3</span><span class="sxs-lookup"><span data-stu-id="4837c-124">Line 3</span></span></li><li><span data-ttu-id="4837c-125">安全</span><span class="sxs-lookup"><span data-stu-id="4837c-125">Safety</span></span></li><li><span data-ttu-id="4837c-126">トレーニング</span><span class="sxs-lookup"><span data-stu-id="4837c-126">Training</span></span></li><li><span data-ttu-id="4837c-127">メンテナンス</span><span class="sxs-lookup"><span data-stu-id="4837c-127">Maintenance</span></span></li><li><span data-ttu-id="4837c-128">楽しい機能</span><span class="sxs-lookup"><span data-stu-id="4837c-128">Fun stuff</span></span></li></ul> <span data-ttu-id="4837c-129">アプリ</span><span class="sxs-lookup"><span data-stu-id="4837c-129">Apps:</span></span> <ul><li><span data-ttu-id="4837c-130">ウィキ</span><span class="sxs-lookup"><span data-stu-id="4837c-130">Wiki</span></span></li></ul>|
||||