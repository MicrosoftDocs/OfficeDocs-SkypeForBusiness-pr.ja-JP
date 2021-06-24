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
ms.openlocfilehash: 23551c102ec8fc0684a979bf85717a02d82e5142
ms.sourcegitcommit: 5c68298474d1782e69bde8c0940be7150cb93f6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2021
ms.locfileid: "53096271"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a><span data-ttu-id="bd5d0-103">非標準ユーザーに対する Microsoft Teams アプリの動作</span><span class="sxs-lookup"><span data-stu-id="bd5d0-103">Microsoft Teams apps behavior for non-standard users</span></span>

<span data-ttu-id="bd5d0-104">この記事では、ゲスト、外部 (フェデレーション)、および匿名ユーザーが Teams コンテキストに存在する場合に、Teams 内のアプリがどのように動作するかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="bd5d0-104">This article describes how apps in Teams behave when guest, external (federated), and anonymous users are present in a Teams context.</span></span>

- <span data-ttu-id="bd5d0-105">**ゲスト ユーザー** とは、従業員、学生、または組織のメンバーではない人のことです。</span><span class="sxs-lookup"><span data-stu-id="bd5d0-105">A **guest user** is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="bd5d0-106">ゲストは組織内での学校アカウントまたは職場アカウントを持ちません。</span><span class="sxs-lookup"><span data-stu-id="bd5d0-106">They don't have a school or work account with your organization.</span></span>

- <span data-ttu-id="bd5d0-107">**外部 (フェデレーション) ユーザー** は別のドメインに属しており、組織のチームやチーム リソースにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="bd5d0-107">An **external (federated) user** belongs to another domain and has no access to your organization's teams or team resources.</span></span>

  > [!Note]
  > <span data-ttu-id="bd5d0-108">ゲスト ユーザーと外部ユーザーの詳細な比較については、[「他の組織のユーザーとの通信」を参照してください](./communicate-with-users-from-other-organizations.md)。</span><span class="sxs-lookup"><span data-stu-id="bd5d0-108">For a more detailed comparison of guest versus external users, [see communicate with users from other organizations](./communicate-with-users-from-other-organizations.md).</span></span>

- <span data-ttu-id="bd5d0-109">**匿名ユーザー** は、ユーザーがリンクを介して会議に参加している Teams 会議の概念です。</span><span class="sxs-lookup"><span data-stu-id="bd5d0-109">An **anonymous user** is a concept in Teams meetings where the user has joined the meeting via a link.</span></span> <span data-ttu-id="bd5d0-110">ユーザーが Microsoft または組織のアカウントでログインしていません。</span><span class="sxs-lookup"><span data-stu-id="bd5d0-110">The user hasn't logged in with their Microsoft or organization’s account.</span></span>

## <a name="guest-users"></a><span data-ttu-id="bd5d0-111">ゲスト ユーザー</span><span class="sxs-lookup"><span data-stu-id="bd5d0-111">Guest users</span></span>

### <a name="install-update-and-delete-for-guest-users"></a><span data-ttu-id="bd5d0-112">ゲスト ユーザーのインストール、更新、削除</span><span class="sxs-lookup"><span data-stu-id="bd5d0-112">Install, update, and delete for guest users</span></span>

<span data-ttu-id="bd5d0-113">ゲストは、チャット、チャネル、会議などの共有コンテキストにアプリをインストール、更新、または削除できませんが、メッセージ拡張機能と直接リンクを使用して個人スコープにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="bd5d0-113">Guests can't install, update, or delete apps into a shared context, such as a chat, channel, or meeting, but they can to their personal scope using message extensions and direct links.</span></span> <span data-ttu-id="bd5d0-114">ゲストは Teams デスクトップ アプリケーションから Teams アプリ ストアにアクセスできますが、直接リンクを使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="bd5d0-114">Guests don't have access to the Teams app store from the Teams desktop application, but they can access it with a direct link.</span></span>

### <a name="usage-behavior-and-policy-for-guest-users"></a><span data-ttu-id="bd5d0-115">ゲスト ユーザーの使用行動とポリシー</span><span class="sxs-lookup"><span data-stu-id="bd5d0-115">Usage behavior and policy for guest users</span></span> 

<span data-ttu-id="bd5d0-116">アプリがネイティブ ユーザーによってインストールされた場合、ゲストはアプリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="bd5d0-116">Guests can use an app if the app was installed by a native user.</span></span>

#### <a name="bots-installed-to-a-channel"></a><span data-ttu-id="bd5d0-117">チャネルにインストールされたボット</span><span class="sxs-lookup"><span data-stu-id="bd5d0-117">Bots installed to a channel</span></span>

<span data-ttu-id="bd5d0-118">ボットはゲスト ユーザーに積極的にメッセージを送信できますが、ゲストはボットと対話できません。</span><span class="sxs-lookup"><span data-stu-id="bd5d0-118">Bots can proactively message guest users, but guests can't interact with the bot.</span></span> <span data-ttu-id="bd5d0-119">ゲストは、ボットに対して 1 対 1 でメッセージを送信したり、ボットにメンションしたり、ボットと通信するアダプティブ カードを操作したりできない。</span><span class="sxs-lookup"><span data-stu-id="bd5d0-119">Guests can't message the bot one-to-one, mention the bot, or interact with adaptive cards that communicate with the bot.</span></span>

#### <a name="personal-bots-installed-with-policies"></a><span data-ttu-id="bd5d0-120">ポリシーと一緒にインストールされた個人用ボット</span><span class="sxs-lookup"><span data-stu-id="bd5d0-120">Personal bots installed with policies</span></span>

- <span data-ttu-id="bd5d0-121">ゲストは、すべてのアプリのホスト テナントに設定されたグローバルおよび組織全体のアクセス許可ポリシーを順守します。</span><span class="sxs-lookup"><span data-stu-id="bd5d0-121">Guests will adhere to global and org-wide permission policies set for the host tenant for any app.</span></span> <span data-ttu-id="bd5d0-122">ホスト組織全体でアプリがブロックされている場合、ゲストもアプリを使用できません。</span><span class="sxs-lookup"><span data-stu-id="bd5d0-122">If an app is blocked for the whole host organization, then guests can't use the app either.</span></span>
- <span data-ttu-id="bd5d0-123">グローバルな既定のアプリ セットアップ ポリシーに含まれるボットも、ゲスト用にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="bd5d0-123">Any bot included in the global default app setup policy will also be installed for guests.</span></span>
- <span data-ttu-id="bd5d0-124">ボットがインストールされた後、ボットはゲストと事前に通信し、ゲストはボットと通信できます。</span><span class="sxs-lookup"><span data-stu-id="bd5d0-124">After a bot is installed, bots can proactively communicate with guests and guests can communicate back with bots.</span></span>
- <span data-ttu-id="bd5d0-125">グローバルな既定のアプリセットアップ ポリシーからゲストを削除できない。</span><span class="sxs-lookup"><span data-stu-id="bd5d0-125">You can't remove a guest from the global default app setup policy.</span></span>
- <span data-ttu-id="bd5d0-126">ゲストがボットにアクセスしないようにするには、さらに多くのアプリ セットアップ ポリシーを作成し、それらを内部ユーザーに割り当て、カスタム ポリシーを使用してボットをインストールします。</span><span class="sxs-lookup"><span data-stu-id="bd5d0-126">To avoid guest from accessing bots, you can create more app setup policies, assign them to internal users, and install bots with the custom policies.</span></span>

## <a name="external-federated-users"></a><span data-ttu-id="bd5d0-127">外部 (フェデレーション) ユーザー</span><span class="sxs-lookup"><span data-stu-id="bd5d0-127">External (Federated) users</span></span>

### <a name="install-update-and-delete-for-external-users"></a><span data-ttu-id="bd5d0-128">外部ユーザーのインストール、更新、および削除</span><span class="sxs-lookup"><span data-stu-id="bd5d0-128">Install, update, and delete for external users</span></span>

<span data-ttu-id="bd5d0-129">外部ユーザーは、個人、チャット、チャネル、会議などのコンテキストにアプリをインストール、更新、または削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="bd5d0-129">External users can't install, update, or delete apps into any context, such as a personal, chat, channel, or meeting.</span></span> <span data-ttu-id="bd5d0-130">ホスティング組織のアプリ ストアTeamsアクセス権を持つユーザーはいます。</span><span class="sxs-lookup"><span data-stu-id="bd5d0-130">They don't have access to the Teams app store of the hosting organization.</span></span>

### <a name="usage-behavior-and-policy-for-external-users"></a><span data-ttu-id="bd5d0-131">外部ユーザーの使用行動とポリシー</span><span class="sxs-lookup"><span data-stu-id="bd5d0-131">Usage behavior and policy for external users</span></span>

- <span data-ttu-id="bd5d0-132">他の組織のユーザーは、ホスティング組織のグローバル (組織全体の既定) ポリシーに従います</span><span class="sxs-lookup"><span data-stu-id="bd5d0-132">People from other organizations adhere to the hosting organization's global (org-wide default) policy</span></span>
- <span data-ttu-id="bd5d0-133">ホスティング組織のユーザーは、他の組織のユーザーと会議チャットにアプリを追加できます。</span><span class="sxs-lookup"><span data-stu-id="bd5d0-133">Users in the hosting organization can add apps in meeting chats with people from other organizations.</span></span> <span data-ttu-id="bd5d0-134">他の組織のユーザーは、会議チャットにアプリを追加することはできませんが、チャットに追加するとボット、タブ、メッセージ拡張機能を操作できます。</span><span class="sxs-lookup"><span data-stu-id="bd5d0-134">People from other organizations cannot add apps in meeting chats but can interact with bots, tabs and message extensions once added to the chat.</span></span>
- <span data-ttu-id="bd5d0-135">ボットは、会議チャットにインストールされた後、そのチャット内の他の組織のユーザーと事前に通信し、それらのユーザーはボットと通信できます。</span><span class="sxs-lookup"><span data-stu-id="bd5d0-135">After a bot is installed in a meeting chat, it can proactively communicate with people from other organizations in that chat and those people can communicate with bot.</span></span>
- <span data-ttu-id="bd5d0-136">ホスティング組織のデータ ポリシーと、そのユーザーの組織によって共有されているサード パーティ製アプリのデータ共有プラクティスが適用されます。</span><span class="sxs-lookup"><span data-stu-id="bd5d0-136">The data policies of the hosting organization, as well as the data sharing practices of any third-party apps shared by that user's organization, are applied.</span></span>

## <a name="anonymous-users"></a><span data-ttu-id="bd5d0-137">匿名ユーザー</span><span class="sxs-lookup"><span data-stu-id="bd5d0-137">Anonymous users</span></span>

### <a name="install-update-and-delete-for-anonymous-users"></a><span data-ttu-id="bd5d0-138">匿名ユーザーのインストール、更新、削除</span><span class="sxs-lookup"><span data-stu-id="bd5d0-138">Install, update, and delete for anonymous users</span></span>

<span data-ttu-id="bd5d0-139">匿名ユーザーは、会議でアプリをインストール、更新、または削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="bd5d0-139">Anonymous users can't install, update, or delete apps in meetings.</span></span>

### <a name="usage-behavior-and-policy-for-anonymous-users"></a><span data-ttu-id="bd5d0-140">匿名ユーザーの使用行動とポリシー</span><span class="sxs-lookup"><span data-stu-id="bd5d0-140">Usage behavior and policy for anonymous users</span></span>

<span data-ttu-id="bd5d0-141">匿名ユーザーは、会議でアプリを直接使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="bd5d0-141">Anonymous users can't directly use apps in meetings.</span></span> <span data-ttu-id="bd5d0-142">匿名ユーザーがいる場合、ネイティブ ユーザーは引き続き会議アプリを使用できます。 </span><span class="sxs-lookup"><span data-stu-id="bd5d0-142">Native users can continue to use meetings apps if anonymous users are present.</span></span> <span data-ttu-id="bd5d0-143">アプリがチャットでアダプティブ カードを送信した場合、匿名ユーザーはカードを操作できます。</span><span class="sxs-lookup"><span data-stu-id="bd5d0-143">If an app sends an adaptive card in the chat, anonymous users can interact with the card.</span></span> <span data-ttu-id="bd5d0-144">詳細については、「匿名ユーザーに [会議への参加を許可する」を参照してください](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings)。</span><span class="sxs-lookup"><span data-stu-id="bd5d0-144">For more information, read [Allow anonymous users to join meetings](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings).</span></span>

<span data-ttu-id="bd5d0-145">匿名ユーザーは、ユーザー レベルのグローバル既定権限ポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="bd5d0-145">Anonymous users will inherit the user-level global default permission policy.</span></span> <span data-ttu-id="bd5d0-146">ユーザー レベルのアクセス許可ポリシーでアプリが有効になっている場合は、Teams 会議でアプリを操作できます。</span><span class="sxs-lookup"><span data-stu-id="bd5d0-146">They can interact with apps in Teams meetings if the user-level permission policy has enabled the app.</span></span> <span data-ttu-id="bd5d0-147">匿名ユーザーは、会議ですでに利用可能なアプリのみを操作でき、これらのアプリを取得または管理できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bd5d0-147">Anonymous users can only interact with apps that are already available in a meeting and can't acquire and/or manage these apps.</span></span>
