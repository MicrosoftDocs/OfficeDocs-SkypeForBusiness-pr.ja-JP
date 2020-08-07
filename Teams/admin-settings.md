---
title: Microsoft Teams でのアプリの管理設定
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: ritikag, rarang
description: Microsoft Teams で組織のアプリの管理に使用できるポリシーと設定について説明します。
localization_priority: Normal
ms.custom:
- ms.teamsadmincenter.apppermspolicies.adminsettings
- ms.teamsadmincenter.apppermspolicies.orgwideapps.thirdpartyapps
- ms.teamsadmincenter.apppolicies.adminsettings
f1.keywords:
- CSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6235352b845898c194e82f3ec292539904a7f61c
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582444"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="49123-103">Microsoft Teams でのアプリの管理設定</span><span class="sxs-lookup"><span data-stu-id="49123-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="49123-104">アプリは、組織が Teams を活用できるよう最先端のツールを提供しています。</span><span class="sxs-lookup"><span data-stu-id="49123-104">Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="49123-105">このアプリは、Microsoft が提供する、サードパーティがまたは組織の開発者が開発したタブ、メッセージング拡張機能、コネクタ、ボットの機能を組み合わせたものです。</span><span class="sxs-lookup"><span data-stu-id="49123-105">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="49123-106">管理センターの**Teams アプリ**で組織のアプリを管理します。</span><span class="sxs-lookup"><span data-stu-id="49123-106">You manage apps for your organization in **Teams apps** in the admin center.</span></span> <span data-ttu-id="49123-107">(「[チーム管理者ロールを使用](https://docs.microsoft.com/microsoftteams/using-admin-roles)してチームを管理し、管理者ロールと権限を取得する」を参照してください。)たとえば、組織レベルでアプリを許可またはブロックしたり、チームユーザーが利用できるアプリを制御するポリシーを設定したり、ユーザーにとって最も重要なアプリを固定することで、チームをカスタマイズしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="49123-107">(See [Use Teams administrator roles to manage Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) to read about getting admin roles and permissions.) For example, you can allow or block apps at the org level, set policies to control what apps are available to Teams users, and customize Teams by pinning the apps that are most important for your users.</span></span>

<span data-ttu-id="49123-108">Microsoft では、Teams でのアプリ エクスペリエンスの継続的な改善と、機能の追加を行うための取り組みを行っています。</span><span class="sxs-lookup"><span data-stu-id="49123-108">We're continually improving the app experience in Teams and adding features and functionality.</span></span> <span data-ttu-id="49123-109">後日、アプリの管理機能が追加されますので、アプリ ポリシーの最新情報をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="49123-109">Over time, we'll be building additional app management capabilities, so check back for the most up-to-date information on app policies.</span></span>

## <a name="manage-apps"></a><span data-ttu-id="49123-110">アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="49123-110">Manage apps</span></span>

<span data-ttu-id="49123-111">**[アプリの管理]** ページを使用して、組織のアプリ カタログにあるすべての Teams アプリを表示および管理できます。</span><span class="sxs-lookup"><span data-stu-id="49123-111">Use the **Manage apps** page to view and manage all Teams apps in your organization's app catalog.</span></span> <span data-ttu-id="49123-112">アプリの組織レベルでの状態とプロパティの確認、組織レベルでのアプリのブロックまたは許可、テナント カタログへの新しいカスタム アプリのアップロード、組織全体のアプリ設定の管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="49123-112">You can see the org-level status and properties of apps, block or allow apps at the org level, upload new custom apps to your tenant catalog, and manage org-wide app settings.</span></span>

<span data-ttu-id="49123-113">**[アプリの管理]** ページでは、テナント カタログ内の使用可能なすべてのアプリを確認することができます。また、組織全体で許可またはブロックするアプリを決定するために必要な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="49123-113">The **Manage apps** page gives you a view into all available apps in your tenant catalog, providing you with the information you need to decide which apps to allow or block across your organization.</span></span> <span data-ttu-id="49123-114">また、[アプリのアクセス許可ポリシー](#app-permission-policies)、[アプリのセットアップ ポリシー](#app-setup-policies)、[カスタム アプリ ポリシーと設定](#custom-app-policies-and-settings)を使って、組織内の特定のユーザーに対してアプリ エクスペリエンスの構成を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="49123-114">You can then use [app permission policies](#app-permission-policies), [app setup policies](#app-setup-policies), and [custom app policies and settings](#custom-app-policies-and-settings) to configure the app experience for specific users in your organization.</span></span>

<span data-ttu-id="49123-115">詳細については、「[Teams でアプリを管理する](manage-apps.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49123-115">To learn more, see [Manage apps in Teams](manage-apps.md).</span></span>

## <a name="app-permission-policies"></a><span data-ttu-id="49123-116">アプリのアクセス許可ポリシー</span><span class="sxs-lookup"><span data-stu-id="49123-116">App permission policies</span></span>

<span data-ttu-id="49123-117">アプリのアクセス許可ポリシーを使用して、組織内の特定のユーザーが使用できるアプリを制御できます。</span><span class="sxs-lookup"><span data-stu-id="49123-117">With app permission policies, you can control what apps are available to specific users in your organization.</span></span> <span data-ttu-id="49123-118">すべてのアプリ、または Microsoft、第三者、お客様の組織によって公開されている特定のアプリを許可またはブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="49123-118">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span>

<span data-ttu-id="49123-119">たとえば、アプリのアクセス許可ポリシーは次のことに使用できます。</span><span class="sxs-lookup"><span data-stu-id="49123-119">For example, you can use app permission policies to:</span></span>

- <span data-ttu-id="49123-120">特定のユーザーに新しいサード パーティ製またはカスタムビルド版のアプリを徐々に展開する。</span><span class="sxs-lookup"><span data-stu-id="49123-120">Gradually roll out new third-party or custom built apps to specific users.</span></span>
- <span data-ttu-id="49123-121">組織全体で Teams の展開を開始する際に、特にユーザーの作業を簡略化する。</span><span class="sxs-lookup"><span data-stu-id="49123-121">Simplify the user experience, especially when you start rolling out Teams across your organization.</span></span>

<span data-ttu-id="49123-122">詳細については、「[Teams のアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)」にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="49123-122">To learn more, go to [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>

## <a name="app-setup-policies"></a><span data-ttu-id="49123-123">アプリケーションの設定ポリシー</span><span class="sxs-lookup"><span data-stu-id="49123-123">App setup policies</span></span>

<span data-ttu-id="49123-124">アプリケーションの設定ポリシーで、ユーザーのアプリでの操作をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="49123-124">App setup policies let you customize the app experience for your users.</span></span> <span data-ttu-id="49123-125">Teams クライアントのアプリ バーに固定するアプリと、アプリが Web、デスクトップ、モバイル クライアントに表示される順序を選択します。</span><span class="sxs-lookup"><span data-stu-id="49123-125">You choose the apps that you want to pin to the app bar in the Teams clients and the order in which they appear, on web, desktop, and mobile clients.</span></span>

<span data-ttu-id="49123-126">アプリの設定ポリシーの活用例は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="49123-126">Here's some examples of how you can use app setup policies:</span></span>

- <span data-ttu-id="49123-127">主要アプリの認識と導入を促進する。</span><span class="sxs-lookup"><span data-stu-id="49123-127">Drive awareness and adoption of core apps.</span></span> <span data-ttu-id="49123-128">たとえば、人事チームのユーザー用のカスタム採用管理と人材管理アプリを固定します。</span><span class="sxs-lookup"><span data-stu-id="49123-128">For example, pin a custom recruiting and talent management app for users on your HR team.</span></span>
- <span data-ttu-id="49123-129">チャット、Teams、通話などの主要な Teams 機能を選択して固定します。</span><span class="sxs-lookup"><span data-stu-id="49123-129">Selectively pin core Teams features, such as Chat, Teams, and Calling.</span></span> <span data-ttu-id="49123-130">これを行うと、ユーザーが確実に Teams 内の特定のアクティビティに取り組めるようになります。</span><span class="sxs-lookup"><span data-stu-id="49123-130">Doing so can help ensure users are engaged in specific activities within Teams.</span></span>

<span data-ttu-id="49123-131">詳細については、「[Teams でアプリの設定ポリシーを管理する](teams-app-setup-policies.md)」を確認してください。</span><span class="sxs-lookup"><span data-stu-id="49123-131">To learn more, check out [Manage app setup policies in Teams](teams-app-setup-policies.md).</span></span>

## <a name="custom-app-policies-and-settings"></a><span data-ttu-id="49123-132">カスタム アプリ ポリシーと設定</span><span class="sxs-lookup"><span data-stu-id="49123-132">Custom app policies and settings</span></span>

<span data-ttu-id="49123-133">Teams により、組織の開発者がその他のユーザーにカスタム アプリを構築、テスト、展開できるようにします。</span><span class="sxs-lookup"><span data-stu-id="49123-133">Teams allows developers in your organization to build, test, and deploy custom apps to other users.</span></span> <span data-ttu-id="49123-134">カスタム パッケージは、.zip ファイルのアプリ パッケージをチームに直接アップロードするか、個人のコンテキストにアップロードして、チームに追加できます。</span><span class="sxs-lookup"><span data-stu-id="49123-134">Custom apps can be added to Teams by uploading an app package in a .zip file directly to a team or in the personal context.</span></span> <span data-ttu-id="49123-135">組織でカスタム アプリをアップロードできる人物を管理するアプリの設定ポリシーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="49123-135">You can use app setup policies to control who in your organization can upload custom apps.</span></span> <span data-ttu-id="49123-136">ユーザーが特定のカスタム アプリを操作するかどうかを制御する組織全体の設定を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="49123-136">You can also set org-wide settings to control whether users can interact with specific custom apps.</span></span>

<span data-ttu-id="49123-137">詳細については、「[Teams のカスタム アプリのポリシーと設定を管理する](teams-custom-app-policies-and-settings.md)」にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="49123-137">To learn more, go to [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>
