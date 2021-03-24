---
title: 標準以外のユーザーに対する Teams アプリの動作
author: cichur
ms.author: v-cichur
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft Teams のアプリが標準以外のユーザーに対してどのように動作するのかについて説明します。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6a8c3c842b47c4575779de4c0ae8301bededb632
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098303"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a><span data-ttu-id="6845d-103">標準以外のユーザーに対する Microsoft Teams アプリの動作</span><span class="sxs-lookup"><span data-stu-id="6845d-103">Microsoft Teams apps behavior for non-standard users</span></span>

<span data-ttu-id="6845d-104">この記事では、ゲスト、外部 (フェデレーション)、匿名ユーザーが Teams のコンテキストで存在する場合の Teams のアプリの動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="6845d-104">This article describes how apps in Teams behave when guest, external (federated), and anonymous users are present in a Teams context.</span></span>

- <span data-ttu-id="6845d-105">ゲスト **ユーザーとは** 、組織の従業員、学生、またはメンバーではないユーザーです。</span><span class="sxs-lookup"><span data-stu-id="6845d-105">A **guest user** is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="6845d-106">ゲストは組織内での学校アカウントまたは職場アカウントを持ちません。</span><span class="sxs-lookup"><span data-stu-id="6845d-106">They don't have a school or work account with your organization.</span></span>

- <span data-ttu-id="6845d-107">外部 **(フェデレーション) ユーザー** は別のドメインに属し、組織のチームまたはチーム リソースにアクセス権はありません。</span><span class="sxs-lookup"><span data-stu-id="6845d-107">An **external (federated) user** belongs to another domain and has no access to your organization's teams or team resources.</span></span>

>[!Note]
> <span data-ttu-id="6845d-108">ゲストと外部ユーザーの詳細な比較については、「他の組織のユーザーとの通信」を [参照してください](./communicate-with-users-from-other-organizations.md)。</span><span class="sxs-lookup"><span data-stu-id="6845d-108">For a more detailed comparison of guest versus external users, [see communicate with users from other organizations](./communicate-with-users-from-other-organizations.md).</span></span>

- <span data-ttu-id="6845d-109">匿名 **ユーザーは、** ユーザーがリンクを介して会議に参加した Teams 会議の概念です。</span><span class="sxs-lookup"><span data-stu-id="6845d-109">An **anonymous user** is a concept in Teams meetings where the user has joined the meeting via a link.</span></span> <span data-ttu-id="6845d-110">ユーザーが Microsoft または組織のアカウントでログインしていない。</span><span class="sxs-lookup"><span data-stu-id="6845d-110">The user hasn't logged in with their Microsoft or organization’s account.</span></span>

## <a name="guest-user-access"></a><span data-ttu-id="6845d-111">ゲスト ユーザー アクセス</span><span class="sxs-lookup"><span data-stu-id="6845d-111">Guest user access</span></span>

### <a name="install-update-and-delete-for-guest-users"></a><span data-ttu-id="6845d-112">ゲスト ユーザーのインストール、更新、削除</span><span class="sxs-lookup"><span data-stu-id="6845d-112">Install, update, and delete for guest users</span></span>

<span data-ttu-id="6845d-113">ゲストは、チャット、チャネル、会議などの共有コンテキストにアプリをインストール、更新、または削除できません。</span><span class="sxs-lookup"><span data-stu-id="6845d-113">Guests can't install, update, or delete apps into a shared context, such as a chat, channel, or meeting.</span></span> <span data-ttu-id="6845d-114">メッセージ拡張機能と直接リンクを使用して、アプリを個人用範囲にインストール、更新、または削除できます。</span><span class="sxs-lookup"><span data-stu-id="6845d-114">They can install, update, or delete apps to their personal scope using message extensions and direct links.</span></span> <span data-ttu-id="6845d-115">ゲストは Teams アプリ ストアにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6845d-115">Guests don't have access to the Teams app store.</span></span>

### <a name="usage-behavior-and-policy-for-guest-users"></a><span data-ttu-id="6845d-116">ゲスト ユーザーの使用状況の動作とポリシー</span><span class="sxs-lookup"><span data-stu-id="6845d-116">Usage behavior and policy for guest users</span></span>

<span data-ttu-id="6845d-117">ネイティブ ユーザーがアプリをインストールした場合、ゲストはアプリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6845d-117">Guests can use an app if the app was installed by a native user.</span></span>

<span data-ttu-id="6845d-118">ボットはゲスト ユーザーに積極的にメッセージを送信できますが、ゲストはボットとやり取りを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="6845d-118">Bots can proactively message guest users, but guests can't interact with the bot.</span></span> <span data-ttu-id="6845d-119">ゲストはボットに 1 対 1 でメッセージを送信したり、ボットに @メンションしたり、ボットと通信するアダプティブ カードを操作したりできない。</span><span class="sxs-lookup"><span data-stu-id="6845d-119">Guests can't message the bot 1:1, @ mention the bot, or interact with adaptive cards that communicate with the bot.</span></span>

<span data-ttu-id="6845d-120">ゲストは、任意のアプリのホスト テナントに設定されたグローバルおよび組織全体のアクセス許可ポリシーに従います。</span><span class="sxs-lookup"><span data-stu-id="6845d-120">Guests will adhere to global and org-wide permission policies set for the host tenant for any app.</span></span> <span data-ttu-id="6845d-121">つまり、ホスト組織全体でアプリがブロックされている場合、ゲストはアプリを使用できません。</span><span class="sxs-lookup"><span data-stu-id="6845d-121">In other words, if an app is blocked for the whole host organization, then guests can't use the app either.</span></span>

<span data-ttu-id="6845d-122">セットアップ ポリシーはゲスト ユーザーには適用されません。</span><span class="sxs-lookup"><span data-stu-id="6845d-122">Setup policies don't apply to guest users.</span></span> <span data-ttu-id="6845d-123">つまり、既定のポリシーからピン留めされた管理者アプリは、ゲスト ユーザーに影響を与えはありません。</span><span class="sxs-lookup"><span data-stu-id="6845d-123">This means admin pinned app from the default policy doesn't affect guest users.</span></span>

## <a name="external-federated-user-access"></a><span data-ttu-id="6845d-124">外部 (フェデレーション) ユーザー アクセス</span><span class="sxs-lookup"><span data-stu-id="6845d-124">External (Federated) user access</span></span>

### <a name="install-update-and-delete-for-external-users"></a><span data-ttu-id="6845d-125">外部ユーザーのインストール、更新、削除</span><span class="sxs-lookup"><span data-stu-id="6845d-125">Install, update, and delete for external users</span></span>

<span data-ttu-id="6845d-126">外部ユーザーは、個人、チャット、チャネル、会議などのコンテキストでアプリをインストール、更新、または削除できません。</span><span class="sxs-lookup"><span data-stu-id="6845d-126">External users can't install, update, or delete apps into any context, such as a personal, chat, channel, or meeting.</span></span> <span data-ttu-id="6845d-127">Teams アプリ ストアにアクセスできない。</span><span class="sxs-lookup"><span data-stu-id="6845d-127">They don't have access to the Teams app store.</span></span>

### <a name="usage-behavior-and-policy-for-external-users"></a><span data-ttu-id="6845d-128">外部ユーザーの使用状況の動作とポリシー</span><span class="sxs-lookup"><span data-stu-id="6845d-128">Usage behavior and policy for external users</span></span>

<span data-ttu-id="6845d-129">外部ユーザーは Teams アプリを使用できません。また、外部ユーザーがネイティブ ユーザーとのコンテキストに追加された場合、すべてのユーザー (ネイティブユーザーと外部ユーザー) はアプリを使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="6845d-129">External users can't use any Teams apps, and when an external user is added to a context with native users, all users – native and external – can no longer use apps.</span></span>

<span data-ttu-id="6845d-130">外部ユーザーは Teams アプリを使用できないので、アプリ ポリシーの影響を受け取らない。</span><span class="sxs-lookup"><span data-stu-id="6845d-130">External users aren't impacted by app policies, because they can't use Teams apps.</span></span>

## <a name="anonymous-user-in-meetings-access"></a><span data-ttu-id="6845d-131">会議アクセスの匿名ユーザー</span><span class="sxs-lookup"><span data-stu-id="6845d-131">Anonymous user in meetings access</span></span>

### <a name="install-update-and-delete-for-anonymous-users"></a><span data-ttu-id="6845d-132">匿名ユーザーのインストール、更新、削除</span><span class="sxs-lookup"><span data-stu-id="6845d-132">Install, update, and delete for anonymous users</span></span>

<span data-ttu-id="6845d-133">匿名ユーザーは、会議でアプリをインストール、更新、または削除できない。</span><span class="sxs-lookup"><span data-stu-id="6845d-133">Anonymous users can't install, update, or delete apps in meetings.</span></span>

### <a name="usage-behavior-and-policy-for-anonymous-users"></a><span data-ttu-id="6845d-134">匿名ユーザーの使用状況の動作とポリシー</span><span class="sxs-lookup"><span data-stu-id="6845d-134">Usage behavior and policy for anonymous users</span></span>

<span data-ttu-id="6845d-135">匿名ユーザーは、会議でアプリを直接使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="6845d-135">Anonymous users can't directly use apps in meetings.</span></span> <span data-ttu-id="6845d-136">匿名ユーザーが存在する場合、ネイティブ ユーザーは会議アプリを引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="6845d-136">Native users can continue to use meetings apps if anonymous users are present.</span></span> <span data-ttu-id="6845d-137">アプリがチャットでアダプティブ カードを送信する場合、匿名ユーザーはカードを操作できます。</span><span class="sxs-lookup"><span data-stu-id="6845d-137">If an app sends an adaptive card in the chat, anonymous users can interact with the card.</span></span>

<span data-ttu-id="6845d-138">匿名ユーザーは、ユーザー レベルのグローバル既定のアクセス許可ポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="6845d-138">Anonymous users will inherit the user-level global default permission policy.</span></span> <span data-ttu-id="6845d-139">このコントロールを使用すると、ユーザー レベルのアクセス許可ポリシーでアプリが有効になっている場合、匿名ユーザーは Teams 会議でアプリを操作できます。</span><span class="sxs-lookup"><span data-stu-id="6845d-139">This control allows anonymous users to interact with apps in Teams meetings if the user-level permission policy has enabled the app.</span></span> <span data-ttu-id="6845d-140">匿名ユーザーは、会議で既に利用可能で、これらのアプリを取得および管理できないアプリのみを操作できます。</span><span class="sxs-lookup"><span data-stu-id="6845d-140">Anonymous users can only interact with apps that are already available in a meeting and can't acquire and/or manage these apps.</span></span>