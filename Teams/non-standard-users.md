---
title: 非標準ユーザーに対する Teams アプリの動作
author: cichur
ms.author: v-cichur
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft Teams のアプリが非標準ユーザーに対してどのように動作するかを学びます。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: fb4b5dfebabfcd0bc86006d93272c3901e7dcfc7
ms.sourcegitcommit: b52b6aba289396c4fc10dd856817137eb1bc1f67
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/07/2021
ms.locfileid: "51617850"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a><span data-ttu-id="b7cf6-103">非標準ユーザーに対する Microsoft Teams アプリの動作</span><span class="sxs-lookup"><span data-stu-id="b7cf6-103">Microsoft Teams apps behavior for non-standard users</span></span>

<span data-ttu-id="b7cf6-104">この記事では、ゲスト、外部 (フェデレーション)、および匿名ユーザーが Teams コンテキストに存在する場合に、Teams 内のアプリがどのように動作するかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b7cf6-104">This article describes how apps in Teams behave when guest, external (federated), and anonymous users are present in a Teams context.</span></span>

- <span data-ttu-id="b7cf6-105">**ゲスト ユーザー** とは、従業員、学生、または組織のメンバーではない人のことです。</span><span class="sxs-lookup"><span data-stu-id="b7cf6-105">A **guest user** is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="b7cf6-106">ゲストは組織内での学校アカウントまたは職場アカウントを持ちません。</span><span class="sxs-lookup"><span data-stu-id="b7cf6-106">They don't have a school or work account with your organization.</span></span>

- <span data-ttu-id="b7cf6-107">**外部 (フェデレーション) ユーザー** は別のドメインに属しており、組織のチームやチーム リソースにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="b7cf6-107">An **external (federated) user** belongs to another domain and has no access to your organization's teams or team resources.</span></span>

  > [!Note]
  > <span data-ttu-id="b7cf6-108">ゲスト ユーザーと外部ユーザーの詳細な比較については、[「他の組織のユーザーとの通信」を参照してください](./communicate-with-users-from-other-organizations.md)。</span><span class="sxs-lookup"><span data-stu-id="b7cf6-108">For a more detailed comparison of guest versus external users, [see communicate with users from other organizations](./communicate-with-users-from-other-organizations.md).</span></span>

- <span data-ttu-id="b7cf6-109">**匿名ユーザー** は、ユーザーがリンクを介して会議に参加している Teams 会議の概念です。</span><span class="sxs-lookup"><span data-stu-id="b7cf6-109">An **anonymous user** is a concept in Teams meetings where the user has joined the meeting via a link.</span></span> <span data-ttu-id="b7cf6-110">ユーザーが Microsoft または組織のアカウントでログインしていません。</span><span class="sxs-lookup"><span data-stu-id="b7cf6-110">The user hasn't logged in with their Microsoft or organization’s account.</span></span>

## <a name="guest-user-access"></a><span data-ttu-id="b7cf6-111">ゲスト ユーザー アクセス</span><span class="sxs-lookup"><span data-stu-id="b7cf6-111">Guest user access</span></span>

### <a name="install-update-and-delete-for-guest-users"></a><span data-ttu-id="b7cf6-112">ゲスト ユーザーのインストール、更新、削除</span><span class="sxs-lookup"><span data-stu-id="b7cf6-112">Install, update, and delete for guest users</span></span>

<span data-ttu-id="b7cf6-113">ゲストは、チャット、チャネル、会議などの共有コンテキストにアプリをインストール、更新、または削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="b7cf6-113">Guests can't install, update, or delete apps into a shared context, such as a chat, channel, or meeting.</span></span> <span data-ttu-id="b7cf6-114">メッセージ拡張機能と直接リンクを使用して、個人の範囲に合わせてアプリをインストール、更新、または削除できます。</span><span class="sxs-lookup"><span data-stu-id="b7cf6-114">They can install, update, or delete apps to their personal scope using message extensions and direct links.</span></span> <span data-ttu-id="b7cf6-115">ゲストは Teams アプリ ストアにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="b7cf6-115">Guests don't have access to the Teams app store.</span></span>

### <a name="usage-behavior-and-policy-for-guest-users"></a><span data-ttu-id="b7cf6-116">ゲスト ユーザーの使用行動とポリシー</span><span class="sxs-lookup"><span data-stu-id="b7cf6-116">Usage behavior and policy for guest users</span></span>

<span data-ttu-id="b7cf6-117">アプリがネイティブ ユーザーによってインストールされた場合、ゲストはアプリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b7cf6-117">Guests can use an app if the app was installed by a native user.</span></span>

<span data-ttu-id="b7cf6-118">ボットはゲスト ユーザーに積極的にメッセージを送信できますが、ゲストはボットと対話できません。</span><span class="sxs-lookup"><span data-stu-id="b7cf6-118">Bots can proactively message guest users, but guests can't interact with the bot.</span></span> <span data-ttu-id="b7cf6-119">ゲストはボットに 1 対 1 のメッセージを送信したり、ボットに @ mention したり、ボットと通信するアダプティブ カードを操作したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b7cf6-119">Guests can't message the bot 1:1, @ mention the bot, or interact with adaptive cards that communicate with the bot.</span></span>

<span data-ttu-id="b7cf6-120">ゲストは、すべてのアプリのホスト テナントに設定されたグローバルおよび組織全体のアクセス許可ポリシーを順守します。</span><span class="sxs-lookup"><span data-stu-id="b7cf6-120">Guests will adhere to global and org-wide permission policies set for the host tenant for any app.</span></span> <span data-ttu-id="b7cf6-121">つまり、ホスト組織全体でアプリがブロックされている場合、ゲストもそのアプリを使用できません。</span><span class="sxs-lookup"><span data-stu-id="b7cf6-121">In other words, if an app is blocked for the whole host organization, then guests can't use the app either.</span></span>

<span data-ttu-id="b7cf6-122">設定ポリシーはゲスト ユーザーには適用されません。</span><span class="sxs-lookup"><span data-stu-id="b7cf6-122">Setup policies don't apply to guest users.</span></span> <span data-ttu-id="b7cf6-123">これは、既定のポリシーから管理者が固定したアプリがゲストユーザーに影響を与えないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="b7cf6-123">This means admin pinned app from the default policy doesn't affect guest users.</span></span>

## <a name="external-federated-user-access"></a><span data-ttu-id="b7cf6-124">外部 (フェデレーション) ユーザー アクセス</span><span class="sxs-lookup"><span data-stu-id="b7cf6-124">External (Federated) user access</span></span>

### <a name="install-update-and-delete-for-external-users"></a><span data-ttu-id="b7cf6-125">外部ユーザーのインストール、更新、および削除</span><span class="sxs-lookup"><span data-stu-id="b7cf6-125">Install, update, and delete for external users</span></span>

<span data-ttu-id="b7cf6-126">外部ユーザーは、個人、チャット、チャネル、会議などのコンテキストにアプリをインストール、更新、または削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="b7cf6-126">External users can't install, update, or delete apps into any context, such as a personal, chat, channel, or meeting.</span></span> <span data-ttu-id="b7cf6-127">外部ユーザーは Teams アプリ ストアにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="b7cf6-127">They don't have access to the Teams app store.</span></span>

### <a name="usage-behavior-and-policy-for-external-users"></a><span data-ttu-id="b7cf6-128">外部ユーザーの使用行動とポリシー</span><span class="sxs-lookup"><span data-stu-id="b7cf6-128">Usage behavior and policy for external users</span></span>

<span data-ttu-id="b7cf6-129">外部ユーザーは Teams アプリを使用できません。また、外部ユーザーがネイティブ ユーザーとのコンテキストに追加されると、ネイティブ ユーザーと外部ユーザーのすべてのユーザーがアプリを使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="b7cf6-129">External users can't use any Teams apps, and when an external user is added to a context with native users, all users – native and external – can no longer use apps.</span></span>

<span data-ttu-id="b7cf6-130">外部ユーザーは Teams アプリを使用できないため、アプリ ポリシーの影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="b7cf6-130">External users aren't impacted by app policies, because they can't use Teams apps.</span></span>

## <a name="anonymous-user-in-meetings-access"></a><span data-ttu-id="b7cf6-131">会議アクセスの匿名ユーザー</span><span class="sxs-lookup"><span data-stu-id="b7cf6-131">Anonymous user in meetings access</span></span>

### <a name="install-update-and-delete-for-anonymous-users"></a><span data-ttu-id="b7cf6-132">匿名ユーザーのインストール、更新、削除</span><span class="sxs-lookup"><span data-stu-id="b7cf6-132">Install, update, and delete for anonymous users</span></span>

<span data-ttu-id="b7cf6-133">匿名ユーザーは、会議でアプリをインストール、更新、または削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="b7cf6-133">Anonymous users can't install, update, or delete apps in meetings.</span></span>

### <a name="usage-behavior-and-policy-for-anonymous-users"></a><span data-ttu-id="b7cf6-134">匿名ユーザーの使用行動とポリシー</span><span class="sxs-lookup"><span data-stu-id="b7cf6-134">Usage behavior and policy for anonymous users</span></span>

<span data-ttu-id="b7cf6-135">匿名ユーザーは、会議でアプリを直接使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="b7cf6-135">Anonymous users can't directly use apps in meetings.</span></span> <span data-ttu-id="b7cf6-136">匿名ユーザーがいる場合、ネイティブ ユーザーは引き続き会議アプリを使用できます。 </span><span class="sxs-lookup"><span data-stu-id="b7cf6-136">Native users can continue to use meetings apps if anonymous users are present.</span></span> <span data-ttu-id="b7cf6-137">アプリがチャットでアダプティブ カードを送信する場合、匿名ユーザーはカードを操作できます。詳細については、「[匿名ユーザーに会議への参加を許可する](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7cf6-137">If an app sends an adaptive card in the chat, anonymous users can interact with the card For more information, see [Allow anonymous users to join meetings](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings).</span></span>

<span data-ttu-id="b7cf6-138">匿名ユーザーは、ユーザー レベルのグローバル既定権限ポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="b7cf6-138">Anonymous users will inherit the user-level global default permission policy.</span></span> <span data-ttu-id="b7cf6-139">ユーザー レベルのアクセス許可ポリシーでアプリが有効になっている場合は、Teams 会議でアプリを操作できます。</span><span class="sxs-lookup"><span data-stu-id="b7cf6-139">They can interact with apps in Teams meetings if the user-level permission policy has enabled the app.</span></span> <span data-ttu-id="b7cf6-140">匿名ユーザーは、会議ですでに利用可能なアプリのみを操作でき、これらのアプリを取得または管理できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b7cf6-140">Anonymous users can only interact with apps that are already available in a meeting and can't acquire and/or manage these apps.</span></span>
