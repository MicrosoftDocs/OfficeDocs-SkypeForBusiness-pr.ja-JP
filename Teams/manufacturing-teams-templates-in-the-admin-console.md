---
title: 管理センターでTeamsテンプレートの使用を開始する
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
description: 使い方について学習します。 Teamsテンプレートを使用して、管理センターを使用して定義済みの設定、チャネル、およびプレインストールされたアプリを提供することで、製造ニーズに合ったチーム構造を作成できます。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9f5439cd8fdd053ab8444a1016eac94064638605
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120558"
---
# <a name="use-teams-manufacturing-templates-in-the-admin-center"></a><span data-ttu-id="54d61-104">管理Teams製造テンプレートを使用する</span><span class="sxs-lookup"><span data-stu-id="54d61-104">Use Teams manufacturing templates in the admin center</span></span>

<span data-ttu-id="54d61-105">Teams テンプレートでは、設定、チャネル、事前にインストールされたアプリの定義済みテンプレートを使用することで、チームをすばやく簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="54d61-105">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="54d61-106">Teamsテンプレートには、製造ニーズを中心に設計されたチーム構造の事前構築された定義があります。</span><span class="sxs-lookup"><span data-stu-id="54d61-106">Teams templates have pre-built definitions of team structures designed around manufacturing needs.</span></span> <span data-ttu-id="54d61-107">Teams テンプレートを拡張して、組織固有のニーズに合わせてチームを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="54d61-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="54d61-108">この記事では、各テンプレートのTeamsし、その使い方をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="54d61-108">In this article, we introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="54d61-109">この記事は、製造組織全体で複数のチームを計画、デプロイ、管理する責任がある場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="54d61-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your manufacturing organization.</span></span> <span data-ttu-id="54d61-110">組織内に Teams サービスがすでに展開されています。</span><span class="sxs-lookup"><span data-stu-id="54d61-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="54d61-111">展開がまだの場合は、「[Microsoft Teams の展開方法](./deploy-overview.md)」をお読みになって展開を開始してください。</span><span class="sxs-lookup"><span data-stu-id="54d61-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](./deploy-overview.md).</span></span>

<span data-ttu-id="54d61-112">一般的なチーム テンプレートの詳細については、「[Teams テンプレートの使用を開始する](get-started-with-teams-templates-in-the-admin-console.md)」をご参照ください。</span><span class="sxs-lookup"><span data-stu-id="54d61-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="quality-and-safety"></a><span data-ttu-id="54d61-113">品質と安全性</span><span class="sxs-lookup"><span data-stu-id="54d61-113">Quality and safety</span></span>

<span data-ttu-id="54d61-114">製造工場チームとの通信、リソースへのアクセス、および工場の運用を一元化します。</span><span class="sxs-lookup"><span data-stu-id="54d61-114">Centralize communication, access to resources, and plant operations with a Manufacturing Plant team.</span></span> <span data-ttu-id="54d61-115">ポリシーと手順のドキュメント、トレーニング ビデオ、安全性に関する通知、シフト引き渡しプロセスを含める。</span><span class="sxs-lookup"><span data-stu-id="54d61-115">Include policy and procedure documents, training videos, safety notices, shift handover processes.</span></span>

| <span data-ttu-id="54d61-116">基本テンプレートの種類</span><span class="sxs-lookup"><span data-stu-id="54d61-116">Base template type</span></span>|<span data-ttu-id="54d61-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="54d61-117">baseTemplateId</span></span>| <span data-ttu-id="54d61-118">この基本テンプレートに含まれるプロパティ</span><span class="sxs-lookup"><span data-stu-id="54d61-118">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="54d61-119">品質と安全性</span><span class="sxs-lookup"><span data-stu-id="54d61-119">Quality and safety</span></span>|`com.microsoft.teams.template.QualitySafety` |<span data-ttu-id="54d61-120">チャネル</span><span class="sxs-lookup"><span data-stu-id="54d61-120">Channels:</span></span> <ul><li><span data-ttu-id="54d61-121">全般</span><span class="sxs-lookup"><span data-stu-id="54d61-121">General</span></span><li><span data-ttu-id="54d61-122">お知らせ</span><span class="sxs-lookup"><span data-stu-id="54d61-122">Announcements</span></span></li><li><span data-ttu-id="54d61-123">1 行目</span><span class="sxs-lookup"><span data-stu-id="54d61-123">Line 1</span></span></li><li><span data-ttu-id="54d61-124">2 行目</span><span class="sxs-lookup"><span data-stu-id="54d61-124">Line 2</span></span></li><li><span data-ttu-id="54d61-125">3 行目</span><span class="sxs-lookup"><span data-stu-id="54d61-125">Line 3</span></span></li><li><span data-ttu-id="54d61-126">安全性</span><span class="sxs-lookup"><span data-stu-id="54d61-126">Safety</span></span></li><li><span data-ttu-id="54d61-127">トレーニング</span><span class="sxs-lookup"><span data-stu-id="54d61-127">Training</span></span></li><li><span data-ttu-id="54d61-128">メンテナンス</span><span class="sxs-lookup"><span data-stu-id="54d61-128">Maintenance</span></span></li><li><span data-ttu-id="54d61-129">楽しい情報</span><span class="sxs-lookup"><span data-stu-id="54d61-129">Fun stuff</span></span></li></ul> <span data-ttu-id="54d61-130">アプリ:</span><span class="sxs-lookup"><span data-stu-id="54d61-130">Apps:</span></span> <ul><li><span data-ttu-id="54d61-131">Wiki</span><span class="sxs-lookup"><span data-stu-id="54d61-131">Wiki</span></span></li><li><span data-ttu-id="54d61-132">プランナー</span><span class="sxs-lookup"><span data-stu-id="54d61-132">Planner</span></span></li></ul>|
||||