---
title: Microsoft Teams で大規模なチームを管理する - ベスト プラクティス
ms.reviewer: abgupta
author: lolaj
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
description: 組織のニーズを満たすために Microsoft Teams で大規模なチームを管理するためのベスト プラクティスについて説明します。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 52b1e50cfd29aa6916f7b816f3639953d27d6526
ms.sourcegitcommit: da2a70a9b5e05d0fd7ecc150b451f5805667514c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2021
ms.locfileid: "50756243"
---
<a name="manage-large-teams-in-microsoft-teams---best-practices"></a><span data-ttu-id="a2a2d-103">Microsoft Teams で大規模なチームを管理する - ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="a2a2d-103">Manage large teams in Microsoft Teams - Best practices</span></span>
======================================================

<span data-ttu-id="a2a2d-104">Microsoft Teams は、多数のメンバーを持つ小規模なグループと、数千人のメンバーを持つ大規模なグループとの間のコミュニケーションを促進する上でも同様に効果的です。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-104">Microsoft Teams is equally effective at facilitating communications between small groups with dozens of members and large groups with thousands of members.</span></span> <span data-ttu-id="a2a2d-105">チーム [サイズの更新については、Teams](limits-specifications-teams.md) の制限と仕様を確認してください。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-105">Review [Limits and specifications for Teams](limits-specifications-teams.md) for updates on team sizes.</span></span> <span data-ttu-id="a2a2d-106">チームの規模を増やして、独自の管理と運用上の課題を引き出します。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-106">Increase in team size leads to unique management and operational challenges.</span></span> <span data-ttu-id="a2a2d-107">この記事では、数千人のメンバーで構成される大規模なチームを作成および管理するためのベスト プラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-107">This article describes best practices for creating and managing large teams comprised of thousands of members.</span></span>

## <a name="value-of-large-teams"></a><span data-ttu-id="a2a2d-108">大規模なチームの価値</span><span class="sxs-lookup"><span data-stu-id="a2a2d-108">Value of large teams</span></span>

<span data-ttu-id="a2a2d-109">大規模なチームは、次のコラボレーション シナリオを有効にする場合に非常に便利です。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-109">Large teams are very useful in enabling the following collaboration scenarios:</span></span>

- <span data-ttu-id="a2a2d-110">**部門全体の** 共同作業: 組織に財務、オペレーション、R&D などの複数の部署がある場合、特定の部門のすべてのメンバーを含む 1 つのチームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-110">**Department-wide collaboration**: If your organization has multiple departments such as Finance, Operations, R&D etc., then you can create a single team that includes all members in a specific department.</span></span> <span data-ttu-id="a2a2d-111">部門に関連するすべてのコミュニケーションをこのチームで共有し、メンバーからすぐに連絡を取り合い、関与することができます。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-111">Now all communications relevant to a department can be shared in this team, which facilitates instant reach and engagement from members.</span></span>

- <span data-ttu-id="a2a2d-112">**従業員リソース グループでの共同作業**: 多くの場合、組織には、異なる部門または作業グループに属する相互の関心を持つ大規模なユーザー グループが含されます。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-112">**Collaboration in employee resource groups**: Organizations often have large groups of people with mutual interests who belong to a different department or work group.</span></span> <span data-ttu-id="a2a2d-113">たとえば、個人の資金と投資に対する熱意を共有する人々のグループがいます。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-113">As an example, there can be a group of people who share a passion for personal finance and investing.</span></span> <span data-ttu-id="a2a2d-114">多くの場合、大規模な組織でつながりにくい場合があります。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-114">It's often hard to connect in a large organization.</span></span> <span data-ttu-id="a2a2d-115">このようなグループのコミュニティを作成するために、テナント管理者は大規模なチームを作成し、誰でも参加して利用できる、一般向け会社全体のリソース グループとして機能します。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-115">To develop communities for such groups, tenant admins can create a large team that serves as a public company-wide resource group that anyone can join and take advantage of.</span></span> <span data-ttu-id="a2a2d-116">最終的には、これらのコミュニティは、新規および既存のメンバーの両方が利用できる情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-116">Eventually, these communities collect information that both new and existing members can enjoy.</span></span>

- <span data-ttu-id="a2a2d-117">**内部メンバーと外部メンバー** の共同作業: 人気のある製品は、新製品のリリースを試してフィードバックを提供することを熱望している早期導入者のコミュニティを多く開発します。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-117">**Collaboration between internal and external members**: Popular products often develop a community of early adopters who are eager to try new product releases and provide feedback.</span></span> <span data-ttu-id="a2a2d-118">早期導入者は、製品の形成に役立つ製品グループとの関係を構築します。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-118">Early adopters develop a relationship with product groups to help shape the product.</span></span> <span data-ttu-id="a2a2d-119">このようなシナリオでは、テナント管理者は、豊富な製品開発プロセスを容易にするために、内部製品グループと外部製品評価者の両方を含む大規模なチームを設定できます。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-119">In such scenarios, tenant admins can set up a large team which includes both internal product groups and external product evaluators to facilitate a rich product development process.</span></span> <span data-ttu-id="a2a2d-120">これらのチームは、一部の顧客にカスタマー サポートを提供できます。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-120">These teams can also provide customer support to a select set of customers.</span></span>

## <a name="create-teams-from-existing-groups"></a><span data-ttu-id="a2a2d-121">既存のグループからチームを作成する</span><span class="sxs-lookup"><span data-stu-id="a2a2d-121">Create teams from existing groups</span></span>

<span data-ttu-id="a2a2d-122">連絡先グループ、セキュリティ グループ、またはグループOfficeを使用して、チームを開始します。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-122">Use contact groups, security groups, or Office groups to jump start your team.</span></span> <span data-ttu-id="a2a2d-123">グループをインポートしてチームを作成したり、グループからチームをOfficeできます。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-123">You can import a group to make a team or create a team from an Office group.</span></span>

<span data-ttu-id="a2a2d-124">**グループをインポートして** チームを作成する: 最大 3,500 人のメンバーを含むグループを Teams にインポートすると、Teams はグループ内のメンバーの総数を自動的に計算します。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-124">**Import a group to make a team**: When you import a group with up to 3,500 members into Teams, Teams automatically calculates the total number of members in the group.</span></span> <span data-ttu-id="a2a2d-125">これは 1 回のみインポートされ、グループ内の今後の変更は Teams で自動的に更新されません。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-125">This is a one-time import only and future changes in the group will not automatically be updated in Teams.</span></span>

<span data-ttu-id="a2a2d-126">**大規模な Microsoft 365** グループからチームを作成する: 大規模な Microsoft 365 グループからチームを作成すると、メンバーは自動的にMicrosoft 365 グループとチームの一部になります。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-126">**Create a team from a large Microsoft 365 group**: When you create a team from a large Microsoft 365 group, members are automatically part of the Microsoft 365 group **and** the team.</span></span> <span data-ttu-id="a2a2d-127">今後、チーム メンバーは Microsoft 365 グループに参加または退出すると、自動的にチームに追加または削除されます。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-127">In the future, as team members join or leave the Microsoft 365 group, they're automatically added or removed from the team.</span></span>

## <a name="bulk-importexportremove-members-in-a-team"></a><span data-ttu-id="a2a2d-128">チームのメンバーを一括インポート/エクスポート/削除する</span><span class="sxs-lookup"><span data-stu-id="a2a2d-128">Bulk import/export/remove members in a team</span></span>

<span data-ttu-id="a2a2d-129">Azure Portal を使用すると、ユーザーは Microsoft 365 グループのメンバーを一括でインポート/エクスポート/削除できます。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-129">The Azure portal allows users to bulk import/export/remove members in a Microsoft 365 Group.</span></span> <span data-ttu-id="a2a2d-130">詳細については、「グループ メンバーを一 [括インポートするには」を参照してください](https://docs.microsoft.com/azure/active-directory/enterprise-users/groups-bulk-import-members#to-bulk-import-group-members)。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-130">For more information, see [To bulk import group members](https://docs.microsoft.com/azure/active-directory/enterprise-users/groups-bulk-import-members#to-bulk-import-group-members).</span></span>

<span data-ttu-id="a2a2d-131">すべてのチームが Microsoft 365 グループの支援を受けたので、Azure Portal を使用して、チームに対応するグループでこれらの操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-131">Since every team is backed by a Microsoft 365 Group, you can use the Azure portal to perform these operations in the group corresponding to the team.</span></span> <span data-ttu-id="a2a2d-132">メンバーの操作は、24 時間以内にチームに反映されます。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-132">The member operations will be reflected in the team within 24 hours.</span></span>

## <a name="create-channels-to-focus-discussions"></a><span data-ttu-id="a2a2d-133">ディスカッションのためのチャネルを作成する</span><span class="sxs-lookup"><span data-stu-id="a2a2d-133">Create channels to focus discussions</span></span>

<span data-ttu-id="a2a2d-134">グループ ディスカッションを絞り込むには、注目チャネルを作成します。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-134">You can narrow the group discussions by creating focused channels.</span></span> <span data-ttu-id="a2a2d-135">チーム [を編成するためのベスト プラクティスを参照してください](best-practices-organizing.md)。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-135">See [Best practices for organizing teams](best-practices-organizing.md).</span></span>

## <a name="restrict-channel-creation"></a><span data-ttu-id="a2a2d-136">チャネルの作成を制限する</span><span class="sxs-lookup"><span data-stu-id="a2a2d-136">Restrict channel creation</span></span>

<span data-ttu-id="a2a2d-137">チーム メンバーがチャネルの作成を許可されている場合、そのチームはチャネルの広がりを持つ可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-137">If any team member is allowed to create channels, that team can have channel sprawl.</span></span> <span data-ttu-id="a2a2d-138">チーム所有者は、メンバーのアクセス許可の設定で、チャネルの作成、更新、削除 **、復元>する必要があります**。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-138">Team owners should turn off channel create, update, delete, and restore for members in **Settings > Member permissions**.</span></span> <span data-ttu-id="a2a2d-139">チーム [とチャネルの概要を参照してください](teams-channels-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-139">See [Overview of teams and channels](teams-channels-overview.md).</span></span>

<span data-ttu-id="a2a2d-140">![管理コンソールの [設定] タブのメンバーのアクセス許可セクションを示す画面イメージ。](media/no-channel-creation.png "管理コンソールの [設定] タブのメンバーのアクセス許可セクションの画面イメージ。チャネルの作成または削除をメンバーに許可するオプションはオフです。")</span><span class="sxs-lookup"><span data-stu-id="a2a2d-140">![Screen image that shows the member permissions section of the admin console Settings tab.](media/no-channel-creation.png "Screen image that member permissions section of the admin console Settings tab. The allow members to create or delete channels options are unchecked.")</span></span>

## <a name="add-favorite-channels"></a><span data-ttu-id="a2a2d-141">お気に入りのチャネルを追加する</span><span class="sxs-lookup"><span data-stu-id="a2a2d-141">Add favorite channels</span></span>

<span data-ttu-id="a2a2d-142">新しいユーザーエンゲージメントとコンテンツ検出を速くするために、既定でユーザーが利用できるお気に入りのチャネルを選択できます。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-142">In order to speed up new user engagement and content discovery, you can select favorite channels that are available to the user by default.</span></span> <span data-ttu-id="a2a2d-143">管理センター **の [** チャネル] ウィンドウで、[メンバーの表示] 列の **下にあるチャネルを確認** します。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-143">In the **Channels** pane of the admin center, check the channels under the **Show for members** column.</span></span>

<span data-ttu-id="a2a2d-144">![管理コンソールの [チャネル] ウィンドウを示す画面イメージ。](media/favorite-channels.png "管理コンソールの [チャネル] ウィンドウを示す画面イメージ。一部のチャネルでは、メンバーに対して [表示] がオンになっています。")</span><span class="sxs-lookup"><span data-stu-id="a2a2d-144">![Screen image that shows the channels pane of the admin console.](media/favorite-channels.png "Screen image that shows channels pane of the admin console. Some channels are checked for Show for members.")</span></span>

 <span data-ttu-id="a2a2d-145">詳細 [については、「最初のチームとチャネルを作成する」](get-started-with-teams-create-your-first-teams-and-channels.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-145">See [Create your first teams and channels](get-started-with-teams-create-your-first-teams-and-channels.md) for details.</span></span>

## <a name="regulate-applications-and-bots-in-large-teams"></a><span data-ttu-id="a2a2d-146">大規模なチームのアプリケーションとボットを規制する</span><span class="sxs-lookup"><span data-stu-id="a2a2d-146">Regulate applications and bots in large teams</span></span>

<span data-ttu-id="a2a2d-147">気が散るアプリケーションやボットが追加されるのを防ぐために、チーム所有者は、チーム メンバーのアプリとコネクタを無効、追加、削除、アップロードできます。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-147">To prevent addition of distracting applications or bots, team owners can disable, add, remove, and upload apps and connectors for team members.</span></span> <span data-ttu-id="a2a2d-148">管理センターの [メンバーのアクセス **許可>** 設定] で、メンバーがアプリまたはコネクタを追加できる 3 つのオプションをオフにします。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-148">In the admin center under **Settings > Member permissions**, uncheck the three options that allow members to add apps or connectors.</span></span>

<span data-ttu-id="a2a2d-149">![[設定] ウィンドウの [メンバーのアクセス許可] セクションを示す画面画像。](media/disable-bots-connectors.png "[設定] ウィンドウの [メンバーのアクセス許可] セクションを示す画面画像。メンバーにアプリまたはコネクタの追加を許可するオプションはオフです。")</span><span class="sxs-lookup"><span data-stu-id="a2a2d-149">![Screen image that shows the Member permissions section of the Settings pane.](media/disable-bots-connectors.png "Screen image that shows the Member permission section of the Settings pane. The options for allow members to add apps or connectors are unchecked.")</span></span>

<span data-ttu-id="a2a2d-150">アプリ [、ボット、&をご覧ください](deploy-apps-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-150">See [Apps, bots, & connectors](deploy-apps-microsoft-teams-landing-page.md).</span></span>

## <a name="regulate-team-and-channel-mentions"></a><span data-ttu-id="a2a2d-151">チームとチャネルのメンションを規制する</span><span class="sxs-lookup"><span data-stu-id="a2a2d-151">Regulate team and channel mentions</span></span>

<span data-ttu-id="a2a2d-152">チームとチャネルのメンションを使用して、特定のチャネル投稿にチーム全体の注意を引き付けできます。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-152">Team and channel mentions can be used to draw the attention of the whole team to certain channel posts.</span></span> <span data-ttu-id="a2a2d-153">投稿でメンションを使用すると、何千人ものチーム メンバーに通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-153">Once a mention is used in a post, a notification is sent to thousands of team members.</span></span> <span data-ttu-id="a2a2d-154">通知が頻繁すぎる場合は、チーム メンバーが過負荷になり、チーム所有者に苦情を申し立てる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-154">If the notifications are too frequent, then team members can become overloaded and might complain to team owners.</span></span> <span data-ttu-id="a2a2d-155">チームまたはチャネルのメンションを防ぐには、[チームの設定] ウィンドウのボックスをオフにして、メンバーのチームと **チャネルのメンション> @mentions** します。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-155">To prevent team or channel mentions, turn off team and channel mentions for members by unchecking the boxes in the teams **Settings > @mentions** pane.</span></span>

<span data-ttu-id="a2a2d-156">![[設定] ウィンドウの [メンション] セクションを示す画面画像。](media/no-at-mentions.png "[設定] ウィンドウの [メンション] セクションを示す画面画像。メンションを表示およびメンバーにアクセス権を与えるオプションはオフです。")</span><span class="sxs-lookup"><span data-stu-id="a2a2d-156">![Screen image that shows the at Mentions section of the Settings pane.](media/no-at-mentions.png "Screen image that shows the at Mentions section of the Settings pane. The options for show and give members access to at mentions are unchecked.")</span></span>

## <a name="consider-setting-up-moderation-in-your-channels"></a><span data-ttu-id="a2a2d-157">チャネル内のモデレーション設定を検討する</span><span class="sxs-lookup"><span data-stu-id="a2a2d-157">Consider setting up moderation in your channels</span></span>

<span data-ttu-id="a2a2d-158">チーム所有者はチャネルのモデレーションを有効にして、対象チャネルで新しい投稿を開始できるユーザーと、投稿に返信できるユーザーを制御できます。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-158">Team owners can turn on moderation for a channel to control who can start new posts and reply to posts in that channel.</span></span> <span data-ttu-id="a2a2d-159">モデレーションを設定する場合、1 人以上のチーム メンバーをモデレーターにすることができます。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-159">When you set up moderation, you can choose one or more team members to be moderators.</span></span> <span data-ttu-id="a2a2d-160">チーム所有者は既定でモデレーターです。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-160">Team owners are moderators by default.</span></span> <span data-ttu-id="a2a2d-161">詳細については、「チャネル モデレート [を設定して管理する」を参照してください](manage-channel-moderation-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="a2a2d-161">For more information, see [Set up and manage channel moderation](manage-channel-moderation-in-teams.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="a2a2d-162">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a2a2d-162">Related topics</span></span>

- [<span data-ttu-id="a2a2d-163">Teams を整理するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="a2a2d-163">Best practices for organizing Teams</span></span>](best-practices-organizing.md)
- [<span data-ttu-id="a2a2d-164">組織全体のチームを作成する</span><span class="sxs-lookup"><span data-stu-id="a2a2d-164">Create an org-wide team</span></span>](create-an-org-wide-team.md)
