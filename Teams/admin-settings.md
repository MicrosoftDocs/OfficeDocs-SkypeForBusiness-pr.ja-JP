---
title: Microsoft Teams でのアプリの管理設定
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: ritikag, rarang
description: Microsoft Teams で組織のアプリの管理に使用できるポリシーと設定について説明します。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
f1keywords:
- ms.teamsadmincenter.apppermspolicies.adminsettings
- ms.teamsadmincenter.apppermspolicies.orgwideapps.thirdpartyapps
- ms.teamsadmincenter.apppolicies.adminsettings
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7d5ecbab6da3936ba0bb20105c40ef0df2c9a1c4
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "37516102"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="477d7-103">Microsoft Teams でのアプリの管理設定</span><span class="sxs-lookup"><span data-stu-id="477d7-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="477d7-104">アプリは、組織が Teams を活用できるよう最先端のツールを提供しています。</span><span class="sxs-lookup"><span data-stu-id="477d7-104">Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="477d7-105">このアプリは、Microsoft が提供する、サードパーティがまたは組織の開発者が開発したタブ、メッセージング拡張機能、コネクタ、ボットの機能を組み合わせたものです。</span><span class="sxs-lookup"><span data-stu-id="477d7-105">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="477d7-106">Microsoft Teams 管理センターの**Teams アプリ**では、組織のアプリを管理するためのポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="477d7-106">In **Teams apps** in the Microsoft Teams admin center, you can set policies to manage apps for your organization.</span></span> <span data-ttu-id="477d7-107">たとえば、チームユーザーが利用できるアプリを制御するポリシーを設定できます。また、ユーザーにとって最も重要なアプリを固定することで、チームをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="477d7-107">For example, you can set policies to control what apps are available to Teams users and you can customize Teams by pinning the apps that are most important for your users.</span></span>

<span data-ttu-id="477d7-108">Sdl では、チームでのアプリのエクスペリエンスを継続的に改善し、機能を追加しています。</span><span class="sxs-lookup"><span data-stu-id="477d7-108">We're continually improving the app experience in Teams and adding features and functionality.</span></span> <span data-ttu-id="477d7-109">時間の経過と共に、アプリの管理機能が追加されています。そのため、アプリのポリシーに関する最新情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="477d7-109">Over time, we'll be building additional app management capabilities, so check back for the most up-to-date information on app policies.</span></span>

## <a name="app-permission-policies"></a><span data-ttu-id="477d7-110">アプリケーションのアクセス許可ポリシー</span><span class="sxs-lookup"><span data-stu-id="477d7-110">App permission policies</span></span>

<span data-ttu-id="477d7-111">アプリのアクセス許可ポリシーで、アプリを組織全体あるいは特定のユーザーにブロックまたは許可できます。</span><span class="sxs-lookup"><span data-stu-id="477d7-111">With app permission policies, you can block or allow apps, either org-wide or for specific users.</span></span>  <span data-ttu-id="477d7-112">アプリをブロックした場合、アプリとのすべての通信が無効になり、アプリがユーザーの Teams に表示されません。</span><span class="sxs-lookup"><span data-stu-id="477d7-112">When you block an app, all interactions with that app are disabled and the app doesn't appear in Teams for users.</span></span>

<span data-ttu-id="477d7-113">たとえば、アプリのアクセス許可ポリシーは次のことに使用できます。</span><span class="sxs-lookup"><span data-stu-id="477d7-113">For example, you can use app permission policies to:</span></span>

- <span data-ttu-id="477d7-114">組織にアクセス許可やデータ損失のリスクをもたらすアプリを無効にする。</span><span class="sxs-lookup"><span data-stu-id="477d7-114">Disable an app that poses a permission or data loss risk to your organization.</span></span>
- <span data-ttu-id="477d7-115">特定のユーザーに新しいサード パーティ製またはカスタムビルド版のアプリを徐々に展開する。</span><span class="sxs-lookup"><span data-stu-id="477d7-115">Gradually roll out new third-party or custom built apps to specific users.</span></span>
- <span data-ttu-id="477d7-116">組織全体で Teams の展開を開始する際に、特にユーザーの作業を簡略化する。</span><span class="sxs-lookup"><span data-stu-id="477d7-116">Simplify the user experience, especially when you start rolling out Teams across your organization.</span></span>

<span data-ttu-id="477d7-117">詳細については、「[Teams のアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)」にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="477d7-117">To learn more, go to [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>

## <a name="app-setup-policies"></a><span data-ttu-id="477d7-118">アプリケーションの設定ポリシー</span><span class="sxs-lookup"><span data-stu-id="477d7-118">App setup policies</span></span>

<span data-ttu-id="477d7-119">アプリケーションの設定ポリシーで、ユーザーのアプリでの操作をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="477d7-119">App setup policies let you customize the app experience for your users.</span></span> <span data-ttu-id="477d7-120">Teams クライアントのアプリ バーに固定するアプリと、アプリが Web、デスクトップ、モバイル クライアントに表示される順序を選択します。</span><span class="sxs-lookup"><span data-stu-id="477d7-120">You choose the apps that you want to pin to the app bar in the Teams clients and the order in which they appear, on web, desktop, and mobile clients.</span></span>

<span data-ttu-id="477d7-121">アプリの設定ポリシーの活用例は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="477d7-121">Here's some examples of how you can use app setup policies:</span></span>
- <span data-ttu-id="477d7-122">主要アプリの認識と導入を促進する。</span><span class="sxs-lookup"><span data-stu-id="477d7-122">Drive awareness and adoption of core apps.</span></span> <span data-ttu-id="477d7-123">たとえば、人事チームのユーザー用のカスタム採用管理と人材管理アプリを固定します。</span><span class="sxs-lookup"><span data-stu-id="477d7-123">For example, pin a custom recruiting and talent management app for users on your HR team.</span></span>
- <span data-ttu-id="477d7-124">チャット、Teams、通話などの主要な Teams 機能を選択して固定します。</span><span class="sxs-lookup"><span data-stu-id="477d7-124">Selectively pin core Teams features, such as Chat, Teams, and Calling.</span></span> <span data-ttu-id="477d7-125">これを行うと、ユーザーが確実に Teams 内の特定のアクティビティに取り組めるようになります。</span><span class="sxs-lookup"><span data-stu-id="477d7-125">Doing so can help ensure users are engaged in specific activities within Teams.</span></span>

<span data-ttu-id="477d7-126">詳細については、「[Teams でアプリの設定ポリシーを管理する](teams-app-setup-policies.md)」を確認してください。</span><span class="sxs-lookup"><span data-stu-id="477d7-126">To learn more, check out [Manage app setup policies in Teams](teams-app-setup-policies.md).</span></span>

## <a name="custom-app-policies-and-settings"></a><span data-ttu-id="477d7-127">カスタム アプリ ポリシーと設定</span><span class="sxs-lookup"><span data-stu-id="477d7-127">Custom app policies and settings</span></span>

<span data-ttu-id="477d7-128">Teams により、組織の開発者がその他のユーザーにカスタム アプリを構築、テスト、展開できるようにします。</span><span class="sxs-lookup"><span data-stu-id="477d7-128">Teams allows developers in your organization to build, test, and deploy custom apps to other users.</span></span> <span data-ttu-id="477d7-129">カスタム パッケージは、.zip ファイルのアプリ パッケージをチームに直接アップロードするか、個人のコンテキストにアップロードして、チームに追加できます。</span><span class="sxs-lookup"><span data-stu-id="477d7-129">Custom apps can be added to Teams by uploading an app package in a .zip file directly to a team or in the personal context.</span></span> <span data-ttu-id="477d7-130">組織でカスタム アプリをアップロードできる人物を管理するアプリの設定ポリシーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="477d7-130">You can use app setup policies to control who in your organization can upload custom apps.</span></span> <span data-ttu-id="477d7-131">ユーザーが特定のカスタム アプリを操作するかどうかを制御する組織全体の設定を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="477d7-131">You can also set org-wide settings to control whether users can interact with specific custom  apps.</span></span>

<span data-ttu-id="477d7-132">詳細については、「[Teams のカスタム アプリのポリシーと設定を管理する](teams-custom-app-policies-and-settings.md)」にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="477d7-132">To learn more, go to [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>