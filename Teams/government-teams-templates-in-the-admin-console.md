---
title: 管理コンソールで Teams government テンプレートを使用する
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
description: 使い方については、こちらを参照してください。 管理コンソールを使用して事前に定義された設定、チャネル、プリインストール済みのアプリを提供することで、行政機関向けに設計されたチーム構造を作成する Teams テンプレート。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 623a80bbe85e0345a9b5812377290db04f4b817b
ms.sourcegitcommit: 45064a0020a1231e17967c74f082106c68213ea0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2020
ms.locfileid: "48308140"
---
# <a name="use-teams-government-templates-in-the-admin-console"></a><span data-ttu-id="dc457-104">管理コンソールで Teams government テンプレートを使用する</span><span class="sxs-lookup"><span data-stu-id="dc457-104">Use Teams government templates in the admin console</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="dc457-105">Teams テンプレートを使用すると、設定、チャネル、プリインストールされているアプリに定義済みのテンプレートを提供して、チームをすばやく簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="dc457-105">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="dc457-106">Teams テンプレートには、行政機関のニーズに合わせて設計されたチーム構造の事前定義が含まれています。</span><span class="sxs-lookup"><span data-stu-id="dc457-106">Teams templates have pre-built definitions of team structures designed around governmental needs.</span></span> <span data-ttu-id="dc457-107">また、チームテンプレートを拡張して、特定の組織のニーズに合わせてカスタマイズされたチームを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="dc457-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="dc457-108">この記事では、各チームテンプレートを紹介し、その使い方をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dc457-108">In this article, we introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="dc457-109">この記事は、組織内の複数のチームの計画、展開、管理を担当しているユーザーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="dc457-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your governmental organization.</span></span> <span data-ttu-id="dc457-110">組織に Teams サービスを既に展開している。</span><span class="sxs-lookup"><span data-stu-id="dc457-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="dc457-111">まだチームをロールアウトしていない場合は、「 [Microsoft teams をロールアウトする方法](How-to-roll-out-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc457-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="dc457-112">チームテンプレート全般の詳細については、「 [チームテンプレートの概要](get-started-with-teams-templates-in-the-admin-console.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc457-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="coordinate-incident-response"></a><span data-ttu-id="dc457-113">インシデント応答の調整</span><span class="sxs-lookup"><span data-stu-id="dc457-113">Coordinate incident response</span></span>

<span data-ttu-id="dc457-114">緊急管理またはインシデント対応チームのコミュニケーションと重要なリソースを一元管理します。</span><span class="sxs-lookup"><span data-stu-id="dc457-114">Centralize communication and critical resources for your crisis management or incident response team.</span></span> <span data-ttu-id="dc457-115">このチームでは、さまざまな種類のファイルを用意して、すべてのドキュメントの一元的な場所を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="dc457-115">Within this team, you can include many different types of files to help create a central place for all your documents.</span></span> <span data-ttu-id="dc457-116">オンライン会議を使って、情報フローと状況に関する認識を向上させます。</span><span class="sxs-lookup"><span data-stu-id="dc457-116">Use online meetings to improve information flow and situational awareness.</span></span>

| <span data-ttu-id="dc457-117">ベーステンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="dc457-117">Base template type</span></span> | | <span data-ttu-id="dc457-118">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="dc457-118">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="dc457-119">インシデント応答の調整</span><span class="sxs-lookup"><span data-stu-id="dc457-119">Coordinate incident response</span></span>|`com.microsoft.teams.template.CoordinateIncidentResponse` |<span data-ttu-id="dc457-120">チャネル</span><span class="sxs-lookup"><span data-stu-id="dc457-120">Channels:</span></span> <ul><li><span data-ttu-id="dc457-121">一般</span><span class="sxs-lookup"><span data-stu-id="dc457-121">General</span></span><li><span data-ttu-id="dc457-122">お知らせ</span><span class="sxs-lookup"><span data-stu-id="dc457-122">Announcements</span></span></li><li><span data-ttu-id="dc457-123">物流</span><span class="sxs-lookup"><span data-stu-id="dc457-123">Logistics</span></span></li><li><span data-ttu-id="dc457-124">計画</span><span class="sxs-lookup"><span data-stu-id="dc457-124">Planning</span></span></li><li><span data-ttu-id="dc457-125">Recovery</span><span class="sxs-lookup"><span data-stu-id="dc457-125">Recovery</span></span></li><li><span data-ttu-id="dc457-126">度</span><span class="sxs-lookup"><span data-stu-id="dc457-126">Urgent</span></span></li></ul> <span data-ttu-id="dc457-127">アプリ</span><span class="sxs-lookup"><span data-stu-id="dc457-127">Apps:</span></span> <ul><li><span data-ttu-id="dc457-128">ウィキ</span><span class="sxs-lookup"><span data-stu-id="dc457-128">Wiki</span></span></li><li><span data-ttu-id="dc457-129">Excel</span><span class="sxs-lookup"><span data-stu-id="dc457-129">Excel</span></span></li><li><span data-ttu-id="dc457-130">OneNote</span><span class="sxs-lookup"><span data-stu-id="dc457-130">OneNote</span></span></li><li><span data-ttu-id="dc457-131">SharePoint</span><span class="sxs-lookup"><span data-stu-id="dc457-131">SharePoint</span></span></li><li><span data-ttu-id="dc457-132">プランナー</span><span class="sxs-lookup"><span data-stu-id="dc457-132">Planner</span></span></li></ul>|
||||