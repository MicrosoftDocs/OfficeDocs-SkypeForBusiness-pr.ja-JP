---
title: Microsoft Teams で大規模なチームを管理する-ベストプラクティス
ms.reviewer: abgupta
author: lolaj
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
description: 組織のニーズに合わせて Microsoft Teams で大規模なチームを管理するためのベストプラクティスについて説明します。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 90345578ceb6bbf8d8752b561511d8df85023bf1
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582664"
---
<a name="manage-large-teams-in-microsoft-teams---best-practices"></a><span data-ttu-id="2f36a-103">Microsoft Teams で大規模なチームを管理する-ベストプラクティス</span><span class="sxs-lookup"><span data-stu-id="2f36a-103">Manage large teams in Microsoft Teams - Best practices</span></span>
======================================================

<span data-ttu-id="2f36a-104">Microsoft Teams は、多数のメンバーと多数のメンバーを含む大規模なグループ間の通信を容易に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2f36a-104">Microsoft Teams is equally effective at facilitating communications between small groups with dozens of members and large groups with thousands of members.</span></span> <span data-ttu-id="2f36a-105">チームのサイズの更新について[、チームの制限と仕様](limits-specifications-teams.md)を確認します。</span><span class="sxs-lookup"><span data-stu-id="2f36a-105">Review [Limits and specifications for Teams](limits-specifications-teams.md) for updates on team sizes.</span></span> <span data-ttu-id="2f36a-106">チームのサイズを大きくすると、固有の管理および運用上の課題につながります。</span><span class="sxs-lookup"><span data-stu-id="2f36a-106">Increase in team size leads to unique management and operational challenges.</span></span> <span data-ttu-id="2f36a-107">この記事では、数千ものメンバーで構成される大規模なチームを作成して管理するためのベストプラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2f36a-107">This article describes best practices for creating and managing large teams comprised of thousands of members.</span></span>

## <a name="value-of-large-teams"></a><span data-ttu-id="2f36a-108">大規模チームの価値</span><span class="sxs-lookup"><span data-stu-id="2f36a-108">Value of large teams</span></span>

<span data-ttu-id="2f36a-109">大規模なチームは、次のコラボレーションシナリオを実現するのに非常に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2f36a-109">Large teams are very useful in enabling the following collaboration scenarios:</span></span>

- <span data-ttu-id="2f36a-110">**部門全体のコラボレーション**: 組織に財務、運営、R&D など複数の部門がいる場合、特定の部門のすべてのメンバーを含む1つのチームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="2f36a-110">**Department-wide collaboration**: If your organization has multiple departments such as Finance, Operations, R&D etc., then you can create a single team that includes all members in a specific department.</span></span> <span data-ttu-id="2f36a-111">これで、部門に関連するすべての通信をこのチームで共有できるようになりました。これにより、メンバーからすぐに連絡を取ることができます。</span><span class="sxs-lookup"><span data-stu-id="2f36a-111">Now all communications relevant to a department can be shared in this team, which facilitates instant reach and engagement from members.</span></span>

- <span data-ttu-id="2f36a-112">**従業員のリソースグループでの共同作業**: 組織によっては、さまざまな部門またはワークグループに属している相互関係を持つ多数のユーザーが含まれていることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="2f36a-112">**Collaboration in employee resource groups**: Organizations often have large groups of people with mutual interests who belong to a different department or work group.</span></span> <span data-ttu-id="2f36a-113">例として、個人の財務と投資について情熱を共有しているユーザーのグループがあるとします。</span><span class="sxs-lookup"><span data-stu-id="2f36a-113">As an example, there can be a group of people who share a passion for personal finance and investing.</span></span> <span data-ttu-id="2f36a-114">大規模な組織では、多くの場合、接続が困難です。</span><span class="sxs-lookup"><span data-stu-id="2f36a-114">It's often hard to connect in a large organization.</span></span> <span data-ttu-id="2f36a-115">このようなグループのコミュニティを開発するために、テナント管理者は、全員が参加して利用できる、会社全体のパブリックリソースグループとして機能する大規模なチームを作ることができます。</span><span class="sxs-lookup"><span data-stu-id="2f36a-115">To develop communities for such groups, tenant admins can create a large team that serves as a public company-wide resource group that anyone can join and take advantage of.</span></span> <span data-ttu-id="2f36a-116">最終的に、これらのコミュニティは、新規と既存の両方のメンバーが利用できる情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="2f36a-116">Eventually, these communities collect information that both new and existing members can enjoy.</span></span>

- <span data-ttu-id="2f36a-117">**内部と外部のメンバーの共同作業**: 人気のある製品は、多くの場合、新製品のリリースを試してフィードバックを提供するための事前の採用者のコミュニティを開発しています。</span><span class="sxs-lookup"><span data-stu-id="2f36a-117">**Collaboration between internal and external members**: Popular products often develop a community of early adopters who are eager to try new product releases and provide feedback.</span></span> <span data-ttu-id="2f36a-118">早い採用先製品グループとの関係を作成して、製品の形成を支援します。</span><span class="sxs-lookup"><span data-stu-id="2f36a-118">Early adopters develop a relationship with product groups to help shape the product.</span></span> <span data-ttu-id="2f36a-119">このようなシナリオでは、テナント管理者は、社内の製品グループと外部製品エバリュエーターの両方が含まれている大規模なチームをセットアップして、豊富な製品開発プロセスを容易にすることができます。</span><span class="sxs-lookup"><span data-stu-id="2f36a-119">In such scenarios, tenant admins can set up a large team which includes both internal product groups and external product evaluators to facilitate a rich product development process.</span></span> <span data-ttu-id="2f36a-120">また、これらのチームは、一連のユーザーにカスタマサポートを提供することもできます。</span><span class="sxs-lookup"><span data-stu-id="2f36a-120">These teams can also provide customer support to a select set of customers.</span></span>

## <a name="create-teams-from-existing-groups"></a><span data-ttu-id="2f36a-121">既存のグループからチームを作成する</span><span class="sxs-lookup"><span data-stu-id="2f36a-121">Create teams from existing groups</span></span>

<span data-ttu-id="2f36a-122">連絡先グループ、セキュリティグループ、または Office グループを使用して、チームを開始します。</span><span class="sxs-lookup"><span data-stu-id="2f36a-122">Use contact groups, security groups, or Office groups to jump start your team.</span></span> <span data-ttu-id="2f36a-123">グループをインポートして、チームを作成したり、Office グループからチームを作成したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="2f36a-123">You can import a group to make a team or create a team from an Office group.</span></span>

<span data-ttu-id="2f36a-124">**チームを作成するためのグループのインポート**: 最大3500メンバーのグループを teams にインポートすると、グループ内のメンバーの合計数が自動的に計算されます。</span><span class="sxs-lookup"><span data-stu-id="2f36a-124">**Import a group to make a team**: When you import a group with up to 3,500 members into Teams, Teams automatically calculates the total number of members in the group.</span></span> <span data-ttu-id="2f36a-125">これは1回限りのインポートであり、グループ内の将来の変更は Teams で自動的には更新されません。</span><span class="sxs-lookup"><span data-stu-id="2f36a-125">This is a one-time import only and future changes in the group will not automatically be updated in Teams.</span></span>

<span data-ttu-id="2f36a-126">**大規模な microsoft 365 グループからチームを作成**する: 大規模な microsoft 365 グループからチームを作成すると、メンバーは自動的に microsoft 365 グループ**と**チームに含まれます。</span><span class="sxs-lookup"><span data-stu-id="2f36a-126">**Create a team from a large Microsoft 365 group**: When you create a team from a large Microsoft 365 group, members are automatically part of the Microsoft 365 group **and** the team.</span></span> <span data-ttu-id="2f36a-127">今後、チームメンバーが Microsoft 365 グループに参加または脱退すると、チームメンバーは自動的に追加または削除されます。</span><span class="sxs-lookup"><span data-stu-id="2f36a-127">In the future, as team members join or leave the Microsoft 365 group, they're automatically added or removed from the team.</span></span>

## <a name="create-channels-to-focus-discussions"></a><span data-ttu-id="2f36a-128">ディスカッションのためのチャネルを作成する</span><span class="sxs-lookup"><span data-stu-id="2f36a-128">Create channels to focus discussions</span></span>

<span data-ttu-id="2f36a-129">優先チャネルを作成することで、グループのディスカッションを絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="2f36a-129">You can narrow the group discussions by creating focused channels.</span></span> <span data-ttu-id="2f36a-130">「[チームを編成するためのベストプラクティス」を](best-practices-organizing.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f36a-130">See [Best practices for organizing teams](best-practices-organizing.md).</span></span>

## <a name="restrict-channel-creation"></a><span data-ttu-id="2f36a-131">チャネルの作成を制限する</span><span class="sxs-lookup"><span data-stu-id="2f36a-131">Restrict channel creation</span></span>

<span data-ttu-id="2f36a-132">いずれかのチームメンバーがチャネルを作成することを許可されている場合、そのチームはチャネルを拡散することができます。</span><span class="sxs-lookup"><span data-stu-id="2f36a-132">If any team member is allowed to create channels, that team can have channel sprawl.</span></span> <span data-ttu-id="2f36a-133">チーム所有者は、メンバーの [設定] で [メンバーのチャネルの作成、更新、削除、復元] を無効にする必要があり **> メンバーの権限を設定**します。</span><span class="sxs-lookup"><span data-stu-id="2f36a-133">Team owners should turn off channel create, update, delete, and restore for members in **Settings > Member permissions**.</span></span> <span data-ttu-id="2f36a-134">「[チームとチャネルの概要」を](teams-channels-overview.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f36a-134">See [Overview of teams and channels](teams-channels-overview.md).</span></span>

<span data-ttu-id="2f36a-135">![管理コンソールの [設定] タブの [メンバーの権限] セクションを示す画面の画像。](media/no-channel-creation.png "管理コンソールの [設定] タブの [メンバーの権限] セクションの画面画像。[チャネルの作成または削除にメンバーを許可する] オプションがオフになっています。")</span><span class="sxs-lookup"><span data-stu-id="2f36a-135">![Screen image that shows the member permissions section of the admin console Settings tab.](media/no-channel-creation.png "Screen image that member permissions section of the admin console Settings tab. The allow members to create or delete channels options are unchecked.")</span></span>

## <a name="add-favorite-channels"></a><span data-ttu-id="2f36a-136">お気に入りのチャネルを追加する</span><span class="sxs-lookup"><span data-stu-id="2f36a-136">Add favorite channels</span></span>

<span data-ttu-id="2f36a-137">新しいユーザー契約とコンテンツ検出を高速化するために、既定でユーザーが使用できるお気に入りのチャネルを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="2f36a-137">In order to speed up new user engagement and content discovery, you can select favorite channels that are available to the user by default.</span></span> <span data-ttu-id="2f36a-138">管理センターの [**チャネル**] ウィンドウで、[**メンバーの表示**] 列の下にあるチャネルを確認します。</span><span class="sxs-lookup"><span data-stu-id="2f36a-138">In the **Channels** pane of the admin center, check the channels under the **Show for members** column.</span></span>

<span data-ttu-id="2f36a-139">![管理コンソールの [チャネル] ウィンドウが表示された画面の画像。](media/favorite-channels.png "管理コンソールの [チャネル] ウィンドウを示す画面の画像。メンバー用に [表示] がオンになっているチャネルがいくつかあります。")</span><span class="sxs-lookup"><span data-stu-id="2f36a-139">![Screen image that shows the channels pane of the admin console.](media/favorite-channels.png "Screen image that shows channels pane of the admin console. Some channels are checked for Show for members.")</span></span>

 <span data-ttu-id="2f36a-140">詳細については、「初めての[チームとチャネルを作成](get-started-with-teams-create-your-first-teams-and-channels.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f36a-140">See [Create your first teams and channels](get-started-with-teams-create-your-first-teams-and-channels.md) for details.</span></span>

## <a name="regulate-applications-and-bots-in-large-teams"></a><span data-ttu-id="2f36a-141">大規模なチームでのアプリケーションとボットの規制</span><span class="sxs-lookup"><span data-stu-id="2f36a-141">Regulate applications and bots in large teams</span></span>

<span data-ttu-id="2f36a-142">煩雑なアプリケーションやボットを追加できないようにするために、チーム所有者は、チームメンバーのアプリとコネクタの無効化、追加、削除、アップロードを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2f36a-142">To prevent addition of distracting applications or bots, team owners can disable, add, remove, and upload apps and connectors for team members.</span></span> <span data-ttu-id="2f36a-143">管理センターの [**設定 > メンバーの権限**] で、メンバーがアプリまたはコネクタを追加できるようにする3つのオプションをオフにします。</span><span class="sxs-lookup"><span data-stu-id="2f36a-143">In the admin center under **Settings > Member permissions**, uncheck the three options that allow members to add apps or connectors.</span></span>

<span data-ttu-id="2f36a-144">![[設定] ウィンドウの [メンバーの権限] セクションを示す画面の画像。](media/disable-bots-connectors.png "[設定] ウィンドウの [メンバーのアクセス許可] セクションを示す画面の画像。[メンバーにアプリまたはコネクタの追加を許可する] のオプションがオフになっている。")</span><span class="sxs-lookup"><span data-stu-id="2f36a-144">![Screen image that shows the Member permissions section of the Settings pane.](media/disable-bots-connectors.png "Screen image that shows the Member permission section of the Settings pane. The options for allow members to add apps or connectors are unchecked.")</span></span>

<span data-ttu-id="2f36a-145">「[アプリ、ボット、& コネクタ」を](deploy-apps-microsoft-teams-landing-page.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f36a-145">See [Apps, bots, & connectors](deploy-apps-microsoft-teams-landing-page.md).</span></span>

## <a name="regulate-team-and-channel-mentions"></a><span data-ttu-id="2f36a-146">チームおよびチャネルメンションの調整</span><span class="sxs-lookup"><span data-stu-id="2f36a-146">Regulate team and channel mentions</span></span>

<span data-ttu-id="2f36a-147">チームとチャネルのメンションを使用して、チーム全体の注意を特定のチャネル投稿に引き寄せることができます。</span><span class="sxs-lookup"><span data-stu-id="2f36a-147">Team and channel mentions can be used to draw the attention of the whole team to certain channel posts.</span></span> <span data-ttu-id="2f36a-148">投稿でメンションが使用されると、多数のチームメンバーに通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="2f36a-148">Once a mention is used in a post, a notification is sent to thousands of team members.</span></span> <span data-ttu-id="2f36a-149">通知の頻度が高すぎると、チームメンバーが過負荷状態になり、チーム所有者に苦情が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2f36a-149">If the notifications are too frequent, then team members can become overloaded and might complain to team owners.</span></span> <span data-ttu-id="2f36a-150">チームまたはチャネルのメンションを禁止するには、[teams の**設定 > @mentions** ] ウィンドウのボックスをオフにして、メンバーのチームおよびチャネルメンションをオフにします。</span><span class="sxs-lookup"><span data-stu-id="2f36a-150">To prevent team or channel mentions, turn off team and channel mentions for members by unchecking the boxes in the teams **Settings > @mentions** pane.</span></span>

<span data-ttu-id="2f36a-151">![[設定] ウィンドウの [メンション] セクションが表示されている画面の画像。](media/no-at-mentions.png "[設定] ウィンドウの [メンション] セクションが表示されている画面の画像。[メンションを付けるときにメンバーにアクセスする] のオプションがオフになっています。")</span><span class="sxs-lookup"><span data-stu-id="2f36a-151">![Screen image that shows the at Mentions section of the Settings pane.](media/no-at-mentions.png "Screen image that shows the at Mentions section of the Settings pane. The options for show and give members access to at mentions are unchecked.")</span></span>

## <a name="consider-setting-up-moderation-in-your-channels"></a><span data-ttu-id="2f36a-152">チャネル内のモデレーション設定を検討する</span><span class="sxs-lookup"><span data-stu-id="2f36a-152">Consider setting up moderation in your channels</span></span>

<span data-ttu-id="2f36a-153">チーム所有者はチャネルのモデレーションを有効にして、対象チャネルで新しい投稿を開始できるユーザーと、投稿に返信できるユーザーを制御できます。</span><span class="sxs-lookup"><span data-stu-id="2f36a-153">Team owners can turn on moderation for a channel to control who can start new posts and reply to posts in that channel.</span></span> <span data-ttu-id="2f36a-154">モデレーションを設定する場合、1 人以上のチーム メンバーをモデレーターにすることができます。</span><span class="sxs-lookup"><span data-stu-id="2f36a-154">When you set up moderation, you can choose one or more team members to be moderators.</span></span> <span data-ttu-id="2f36a-155">チームの所有者は、既定でモデレーターとなります。</span><span class="sxs-lookup"><span data-stu-id="2f36a-155">Team owners are moderators by default.</span></span> <span data-ttu-id="2f36a-156">詳細については、「[チャネルのモデレーションを設定および管理](manage-channel-moderation-in-teams.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f36a-156">For more information, see [Set up and manage channel moderation](manage-channel-moderation-in-teams.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="2f36a-157">関連トピック</span><span class="sxs-lookup"><span data-stu-id="2f36a-157">Related topics</span></span>

- [<span data-ttu-id="2f36a-158">チームを編成するためのベストプラクティス</span><span class="sxs-lookup"><span data-stu-id="2f36a-158">Best practices for organizing Teams</span></span>](best-practices-organizing.md)
- [<span data-ttu-id="2f36a-159">組織全体のチームを作成する</span><span class="sxs-lookup"><span data-stu-id="2f36a-159">Create an org-wide team</span></span>](create-an-org-wide-team.md)
