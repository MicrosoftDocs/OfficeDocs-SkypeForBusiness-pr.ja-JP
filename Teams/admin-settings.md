---
title: Microsoft Teams でのアプリの管理設定
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/18/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ritikag, lajin
description: Microsoft Teams で組織のアプリの管理に使用できるポリシーと設定について説明します。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.apppolicies.adminsettings
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f013b888b61424c9a3b7dec9950fe45941cd5e6a
ms.sourcegitcommit: 8e62025d630c511ffb0361b9643d46c762188102
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "30568409"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="57c8b-103">Microsoft Teams でのアプリの管理設定</span><span class="sxs-lookup"><span data-stu-id="57c8b-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="57c8b-104">アプリは、組織が Teams を活用できるよう最先端のツールを提供しています。</span><span class="sxs-lookup"><span data-stu-id="57c8b-104">Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="57c8b-105">このアプリは、Microsoft が提供する、サードパーティがまたは組織の開発者が開発したタブ、メッセージング拡張機能、コネクタ、ボットの機能を組み合わせたものです。</span><span class="sxs-lookup"><span data-stu-id="57c8b-105">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="57c8b-106">Microsoft Teams 管理センターで、**Teams アプリ**の組織向けアプリを管理します。</span><span class="sxs-lookup"><span data-stu-id="57c8b-106">You manage apps for your organization in **Teams apps** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="57c8b-107">組織内の Teams ユーザーが利用できるアプリを制御したり、ユーザーにとって最も重要なアプリを固定して Teams をカスタマイズしたり、ユーザーがカスタム アプリをアップロードできるかどうか (サイドローディングとしても知られています) を指定したりできます。</span><span class="sxs-lookup"><span data-stu-id="57c8b-107">You can set policies to control what apps are available to Teams users in your organization, customize Teams by pinning apps that are most important for your users, and specify whether users can upload custom apps (also known as sideloading).</span></span> <span data-ttu-id="57c8b-108">これらのポリシーと設定により、利用可能なアプリ、Teams でのアプリの見え方、組織のニーズに応じて利用できるユーザーを細かく管理できます。</span><span class="sxs-lookup"><span data-stu-id="57c8b-108">These policies and settings give you granular control over what apps are available, how they appear in Teams, and who can use them based on the needs of your organization.</span></span>

## <a name="app-permission-policies"></a><span data-ttu-id="57c8b-109">アプリケーションのアクセス許可ポリシー</span><span class="sxs-lookup"><span data-stu-id="57c8b-109">App permission policies</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="57c8b-110">アプリのアクセス許可ポリシーで、アプリを組織全体あるいは特定のユーザーにブロックまたは許可できます。</span><span class="sxs-lookup"><span data-stu-id="57c8b-110">With app permission policies, you can block or allow apps, either org-wide or for specific users.</span></span>  <span data-ttu-id="57c8b-111">アプリをブロックした場合、アプリとのすべての通信が無効になり、アプリがユーザーの Teams に表示されません。</span><span class="sxs-lookup"><span data-stu-id="57c8b-111">When you block an app, all interactions with that app are disabled and the app doesn't appear in Teams for users.</span></span>

<span data-ttu-id="57c8b-112">たとえば、アプリのアクセス許可ポリシーは次のことに使用できます。</span><span class="sxs-lookup"><span data-stu-id="57c8b-112">For example, you can use app permission policies to:</span></span>

- <span data-ttu-id="57c8b-113">組織にアクセス許可やデータ損失のリスクをもたらすアプリを無効にする。</span><span class="sxs-lookup"><span data-stu-id="57c8b-113">Disable an app that poses a permission or data loss risk to your organization.</span></span>
- <span data-ttu-id="57c8b-114">特定のユーザーに新しいサード パーティ製またはカスタムビルド版のアプリを徐々に展開する。</span><span class="sxs-lookup"><span data-stu-id="57c8b-114">Gradually roll out new third-party or custom built apps to specific users.</span></span>
- <span data-ttu-id="57c8b-115">組織全体で Teams の展開を開始する際に、特にユーザーの作業を簡略化する。</span><span class="sxs-lookup"><span data-stu-id="57c8b-115">Simplify the user experience, especially when you start rolling out Teams across your organization.</span></span>

<span data-ttu-id="57c8b-116">詳細については、「[Teams のアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)」にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="57c8b-116">To learn more, go to [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>

## <a name="app-setup-policies"></a><span data-ttu-id="57c8b-117">アプリケーションの設定ポリシー</span><span class="sxs-lookup"><span data-stu-id="57c8b-117">App setup policies</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="57c8b-118">アプリケーションの設定ポリシーで、ユーザーのアプリでの操作をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="57c8b-118">App setup policies let you customize the app experience for your users.</span></span> <span data-ttu-id="57c8b-119">Teams クライアントのアプリ バーに固定するアプリと、アプリが Web、デスクトップ、モバイル クライアントに表示される順序を選択します。</span><span class="sxs-lookup"><span data-stu-id="57c8b-119">You choose the apps that you want to pin to the app bar in the Teams clients and the order in which they appear, on web, desktop, and mobile clients.</span></span>

<span data-ttu-id="57c8b-120">アプリの設定ポリシーの活用例は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="57c8b-120">Here's some examples of how you can use app setup policies:</span></span>
- <span data-ttu-id="57c8b-121">主要アプリの認識と導入を促進する。</span><span class="sxs-lookup"><span data-stu-id="57c8b-121">Drive awareness and adoption of core apps.</span></span> <span data-ttu-id="57c8b-122">たとえば、人事チームのユーザー用のカスタム採用管理と人材管理アプリを固定します。</span><span class="sxs-lookup"><span data-stu-id="57c8b-122">For example, pin a custom recruiting and talent management app for users on your HR team.</span></span>
- <span data-ttu-id="57c8b-123">チャット、Teams、通話などの主要な Teams 機能を選択して固定します。</span><span class="sxs-lookup"><span data-stu-id="57c8b-123">Selectively pin core Teams features, such as Chat, Teams, and Calling.</span></span> <span data-ttu-id="57c8b-124">これを行うと、ユーザーが確実に Teams 内の特定のアクティビティに取り組めるようになります。</span><span class="sxs-lookup"><span data-stu-id="57c8b-124">Doing so can help ensure users are engaged in specific activities within Teams.</span></span>

<span data-ttu-id="57c8b-125">詳細については、「[Teams でアプリの設定ポリシーを管理する](teams-app-setup-policies.md)」を確認してください。</span><span class="sxs-lookup"><span data-stu-id="57c8b-125">To learn more, check out [Manage app setup policies in Teams](teams-app-setup-policies.md).</span></span>

## <a name="custom-app-policies-and-settings"></a><span data-ttu-id="57c8b-126">カスタム アプリ ポリシーと設定</span><span class="sxs-lookup"><span data-stu-id="57c8b-126">Custom app policies and settings</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="57c8b-127">Teams により、組織の開発者がその他のユーザーにカスタム アプリを構築、テスト、展開できるようにします。</span><span class="sxs-lookup"><span data-stu-id="57c8b-127">Teams allows developers in your organization to build, test, and deploy custom apps to other users.</span></span> <span data-ttu-id="57c8b-128">カスタム パッケージは、.zip ファイルのアプリ パッケージをチームに直接アップロードするか、個人のコンテキストにアップロードして、チームに追加できます。</span><span class="sxs-lookup"><span data-stu-id="57c8b-128">Custom apps can be added to Teams by uploading an app package in a .zip file directly to a team or in the personal context.</span></span> <span data-ttu-id="57c8b-129">組織でカスタム アプリをアップロードできる人物を管理するアプリの設定ポリシーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="57c8b-129">You can use app setup policies to control who in your organization can upload custom apps.</span></span> <span data-ttu-id="57c8b-130">ユーザーが特定のカスタム アプリを操作するかどうかを制御する組織全体の設定を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="57c8b-130">You can also set org-wide settings to control whether users can interact with specific custom  apps.</span></span>

<span data-ttu-id="57c8b-131">詳細については、「[Teams のカスタム アプリのポリシーと設定を管理する](teams-custom-app-policies-and-settings.md)」にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="57c8b-131">To learn more, go to [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>