---
title: Microsoft Teams で組織全体にわたるチームを作成する
author: LanaChin
ms.author: v-lanac
ms.reviewer: phlouie
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Teams で組織全体のチームを作成して管理する方法について説明します。
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: db7caa3879e016b6e8453ad151785578d2391dd1
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2019
ms.locfileid: "37516652"
---
# <a name="create-an-org-wide-team-in-microsoft-teams"></a><span data-ttu-id="d140f-103">Microsoft Teams で組織全体にわたるチームを作成する</span><span class="sxs-lookup"><span data-stu-id="d140f-103">Create an org-wide team in Microsoft Teams</span></span>

<span data-ttu-id="d140f-104">組織全体のチームは、小規模または中規模の組織内のすべてのユーザーが、共同作業のために1つのチームに参加するための自動的な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="d140f-104">Org-wide teams provide an automatic way for everyone in a small to medium-sized organization to be a part of a single team for collaboration.</span></span>

<span data-ttu-id="d140f-105">組織全体のチームでは、グローバル管理者は、組織内のすべてのユーザーを対象としたパブリックチームを簡単に作成し、ユーザーが参加して組織から脱退するときに Active Directory を使ってメンバーシップを最新の状態に維持することができます。</span><span class="sxs-lookup"><span data-stu-id="d140f-105">With org-wide teams, global admins can easily create a public team that pulls in every user in the organization and keeps the membership up to date with Active Directory as users join and leave the organization.</span></span> <span data-ttu-id="d140f-106">グローバル管理者のみが、組織全体のチームを作成できます。現在、組織全体のチームは、5000ユーザーを超える組織に限定されています。</span><span class="sxs-lookup"><span data-stu-id="d140f-106">Only global admins can create org-wide teams and currently an org-wide team is limited to organizations with no more than 5,000 users.</span></span> <span data-ttu-id="d140f-107">1つのテナントには、組織全体のチームとして5つの制限もあります。</span><span class="sxs-lookup"><span data-stu-id="d140f-107">There's also a limit of five org-wide teams per tenant.</span></span> <span data-ttu-id="d140f-108">これらの要件が満たされている場合、グローバル管理者は、チームの作成時に [**チームを最初から**作成する] を選択すると、**組織全体**をオプションとして表示します。</span><span class="sxs-lookup"><span data-stu-id="d140f-108">If these requirements are met, global admins will see **Org-wide** as an option when they select **Build a team from scratch** when creating a team.</span></span> 

<span data-ttu-id="d140f-109">![組織全体のチームを作成するための組織全体のオプションのスクリーンショット](media/create-org-wide-team.png "組織全体のチームを作成するための組織全体のオプションのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="d140f-109">![Screen shot of the Org-wide option to create an org-wide team](media/create-org-wide-team.png "Screen shot of the Org-wide option to create an org-wide team")</span></span>

<span data-ttu-id="d140f-110">組織全体のチームを作成すると、すべてのグローバル管理者がチーム所有者として追加され、アクティブなすべてのユーザーがチームメンバーとして追加されます。</span><span class="sxs-lookup"><span data-stu-id="d140f-110">When an org-wide team is created, all global admins are added as team owners and all active users are added as team members.</span></span> <span data-ttu-id="d140f-111">ライセンス未付与のユーザーは、チームにも追加されます。</span><span class="sxs-lookup"><span data-stu-id="d140f-111">Unlicensed users are also added to the team.</span></span> <span data-ttu-id="d140f-112">ライセンス未付与のユーザーが初めて Teams にサインインしたとき、そのユーザーには Microsoft Teams の市販クラウド試用ライセンスが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="d140f-112">The first time an unlicensed user signs in to Teams, the user is assigned a Microsoft Teams Commercial Cloud Trial license.</span></span> <span data-ttu-id="d140f-113">試用版のライセンスの詳細については、「 [Teams の市販クラウド試用版を管理](iw-trial-teams.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d140f-113">To learn more about the trial license, check out [Manage the Teams Commercial Cloud Trial offer](iw-trial-teams.md).</span></span> 

<span data-ttu-id="d140f-114">次の種類のアカウントは、組織全体のチームに追加されることはありません。</span><span class="sxs-lookup"><span data-stu-id="d140f-114">These types of accounts won't be added to your org-wide team:</span></span>

- <span data-ttu-id="d140f-115">サインインがブロックされているアカウント</span><span class="sxs-lookup"><span data-stu-id="d140f-115">Accounts that are blocked from sign in</span></span>
- <span data-ttu-id="d140f-116">ゲスト ユーザー</span><span class="sxs-lookup"><span data-stu-id="d140f-116">Guest users</span></span>
- <span data-ttu-id="d140f-117">サービスアカウント</span><span class="sxs-lookup"><span data-stu-id="d140f-117">Service accounts</span></span>
- <span data-ttu-id="d140f-118">会議室または備品のアカウント</span><span class="sxs-lookup"><span data-stu-id="d140f-118">Room or equipment accounts</span></span>
- <span data-ttu-id="d140f-119">共有メールボックスによってバックアップされたアカウント</span><span class="sxs-lookup"><span data-stu-id="d140f-119">Accounts backed by a shared mailbox</span></span>

<span data-ttu-id="d140f-120">組織のディレクトリが更新され、新しいアクティブユーザーが含まれている場合、またはユーザーが会社で仕事をしておらず、そのアカウントが無効になっている場合は、変更が自動的に同期され、ユーザーはチームから追加または削除されます。</span><span class="sxs-lookup"><span data-stu-id="d140f-120">As your organization's directory is updated to include new active users or if users no longer work at your company and their account is disabled, changes are automatically synced and the users are added or removed from the team.</span></span> <span data-ttu-id="d140f-121">チームメンバーは、組織全体のチームを脱退することはできません。</span><span class="sxs-lookup"><span data-stu-id="d140f-121">Team members can't leave an org-wide team.</span></span> <span data-ttu-id="d140f-122">チーム所有者は、必要に応じてユーザーを手動で追加または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="d140f-122">As a team owner, you can manually add or remove users if needed.</span></span>

> [!NOTE]
> - <span data-ttu-id="d140f-123">チームを作成するときに**組織全体**のオプションが表示されず、グローバル管理者である場合は、この機能がまだ展開されている可能性があります。組織全体のチームの制限に達した場合、または組織の5000メンバーの現在のサイズ制限を超えている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d140f-123">If you don't see the **Org-wide** option when creating a team and you're a global admin, the feature might still be rolling out, you have reached the five org-wide teams limit, or your organization might have more than the current size limit of 5,000 members.</span></span> <span data-ttu-id="d140f-124">今後、この制限を引き上げることを検討しています。</span><span class="sxs-lookup"><span data-stu-id="d140f-124">We're looking to increase this limit in the future.</span></span>
> - <span data-ttu-id="d140f-125">会議室リスト、備品、リソースアカウントの一部ではない会議室が、組織全体のチームに追加または同期される場合があります。</span><span class="sxs-lookup"><span data-stu-id="d140f-125">Rooms that aren't a part of a room list, equipment, and resource accounts might be added or synced to the org-wide team.</span></span> <span data-ttu-id="d140f-126">チーム所有者は、これらのアカウントをチームから簡単に削除できます。</span><span class="sxs-lookup"><span data-stu-id="d140f-126">Team owners can easily remove these accounts from the team.</span></span>
> - <span data-ttu-id="d140f-127">メンバーを追加または削除するシステムのすべての操作は、[全般] チャネルに投稿されます。</span><span class="sxs-lookup"><span data-stu-id="d140f-127">All actions by the system to add or remove members are posted in the General channel.</span></span> <span data-ttu-id="d140f-128">チャネルは、Teams クライアントで新しいアクティビティとしてマークされることもあります。</span><span class="sxs-lookup"><span data-stu-id="d140f-128">The channel will also be marked as having new activity in the Teams client.</span></span>

## <a name="best-practices"></a><span data-ttu-id="d140f-129">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="d140f-129">Best practices</span></span>

<span data-ttu-id="d140f-130">組織全体のチームを最大限に活用するには、チーム所有者が次のことを行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d140f-130">To get the most out of your org-wide team, we recommend team owners do the following.</span></span>

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a><span data-ttu-id="d140f-131">[全般] チャネルへの投稿をチーム所有者のみに許可する</span><span class="sxs-lookup"><span data-stu-id="d140f-131">Allow only team owners to post to the General channel</span></span>

<span data-ttu-id="d140f-132">チームの所有者だけが一般的なチャネルに投稿できるようにすることで、チャネルの雑音を減らします。</span><span class="sxs-lookup"><span data-stu-id="d140f-132">Reduce channel noise by having only team owners post to the General channel.</span></span> <span data-ttu-id="d140f-133">チームに移動し、[ **̇̇** > ] をクリックして、[**チームの管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d140f-133">Go to the team and click **˙˙˙ More options** > **Manage Team**.</span></span> <span data-ttu-id="d140f-134">[**設定**] タブで、[**メンバーの権限**] をクリックし > [メッセージを**投稿できるのは所有者のみ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="d140f-134">On the **Settings** tab, click **Member permissions** > select **Only owners can post messages**.</span></span>

### <a name="turn-off-team-and-team-name-mentions"></a><span data-ttu-id="d140f-135">@Team および @ [チーム名] メンションをオフにする</span><span class="sxs-lookup"><span data-stu-id="d140f-135">Turn off @team and @[team name] mentions</span></span>

 <span data-ttu-id="d140f-136">組織全体の過負荷を防ぐため、@mentions を減らします。</span><span class="sxs-lookup"><span data-stu-id="d140f-136">Reduce @mentions to keep them from overloading the entire organization.</span></span> <span data-ttu-id="d140f-137">チームに移動し、[ **̇̇** > ] をクリックして、[**チームの管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d140f-137">Go to the team and click **˙˙˙ More options** > **Manage Team**.</span></span> <span data-ttu-id="d140f-138">[**設定**] タブで、[ <strong>@mentions</strong> ] をクリックし、[**メンバーの表示] オプションを @team するか、@ [チーム名] を**オフに > します。</span><span class="sxs-lookup"><span data-stu-id="d140f-138">On the **Settings** tab, click <strong>@mentions</strong> > turn off **Show members the option to @team or @[team name]**.</span></span> 

### <a name="automatically-favorite-important-channels"></a><span data-ttu-id="d140f-139">重要なチャネルを自動的にお気に入りにする</span><span class="sxs-lookup"><span data-stu-id="d140f-139">Automatically favorite important channels</span></span>

<span data-ttu-id="d140f-140">組織内のすべてのユーザーが特定の会話を行うことができるように、重要なチャネルをお気に入りにします。</span><span class="sxs-lookup"><span data-stu-id="d140f-140">Favorite important channels to ensure everyone in your organization engages in specific conversations.</span></span> <span data-ttu-id="d140f-141">詳細については、「[チーム全体の自動お気に入りチャネル](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d140f-141">To learn more, see [Auto-favorite channels for the whole team](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6).</span></span>

### <a name="set-up-channel-moderation"></a><span data-ttu-id="d140f-142">チャネルのモデレーションを設定する</span><span class="sxs-lookup"><span data-stu-id="d140f-142">Set up channel moderation</span></span>

<span data-ttu-id="d140f-143">チャネルのモデレーションを設定して、特定のチームメンバーにモデレーター機能を提供することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="d140f-143">Consider setting up channel moderation and giving moderator capabilities to certain team members.</span></span> <span data-ttu-id="d140f-144">(モデレートが設定されている場合、チームの所有者にはモデレーター機能が自動的に与えられます。)モデレーターは、チャネル内で新しい投稿を開始できるユーザーを管理し、モデレーターを追加および削除し、チームメンバーが既存のチャネルメッセージに返信できるかどうかを制御し、また、ボットとコネクタがチャネルメッセージを送信できるかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="d140f-144">(When moderation is set up, team owners are given moderator capabilities automatically.) Moderators can control who can start a new post in a channel, add and remove moderators, control whether team members can reply to existing channel messages, and control whether bots and connectors can submit channel messages.</span></span> <span data-ttu-id="d140f-145">詳細については、「 [Microsoft Teams でチャネルのモデレーションを設定および管理](manage-channel-moderation-in-teams.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d140f-145">For more information, see [Set up and manage channel moderation in Microsoft Teams](manage-channel-moderation-in-teams.md).</span></span>

### <a name="remove-accounts-that-might-not-belong"></a><span data-ttu-id="d140f-146">属していない可能性のあるアカウントを削除する</span><span class="sxs-lookup"><span data-stu-id="d140f-146">Remove accounts that might not belong</span></span>

<span data-ttu-id="d140f-147">メンバーは組織全体のチームを脱退することはできませんが、チーム所有者は、所属していないアカウントを削除することでチームリストを管理できます。</span><span class="sxs-lookup"><span data-stu-id="d140f-147">Even though members can’t leave an org-wide team, as a team owner, you can manage the team roster by removing accounts that don’t belong.</span></span> <span data-ttu-id="d140f-148">**Teams を使用して、組織全体のチームからユーザーを削除して**ください。</span><span class="sxs-lookup"><span data-stu-id="d140f-148">**Make sure you use Teams to remove users from your org-wide team**.</span></span> <span data-ttu-id="d140f-149">Microsoft 365 管理センターや Outlook のグループからユーザーを削除する別の方法を使用した場合、ユーザーは組織全体のチームに追加される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d140f-149">If you use another way to remove a user, such as the Microsoft 365 admin center or from a group in Outlook, the user might be added back to the org-wide team.</span></span>

## <a name="faq"></a><span data-ttu-id="d140f-150">FAQ</span><span class="sxs-lookup"><span data-stu-id="d140f-150">FAQ</span></span>

### <a name="is-there-a-way-to-create-an-org-wide-team-other-than-using-the-teams-client"></a><span data-ttu-id="d140f-151">Teams クライアントを使用することなく、組織全体のチームを作成する方法はありますか?</span><span class="sxs-lookup"><span data-stu-id="d140f-151">Is there a way to create an org-wide team other than using the Teams client?</span></span>

<span data-ttu-id="d140f-152">グローバル管理者は、Teams クライアントを使用して、組織全体のチームを作成することのみできます。</span><span class="sxs-lookup"><span data-stu-id="d140f-152">Global admins can only create an org-wide team by using the Teams client.</span></span> <span data-ttu-id="d140f-153">組織で、PowerShell を使用するチームの作成が制限されている場合、回避策として、グローバル管理者を、チームを作成できるユーザーのセキュリティグループに追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d140f-153">If your organization limits creating teams to using PowerShell, the recommended workaround is to add your global admins to the security group of users who can create a team.</span></span> <span data-ttu-id="d140f-154">詳細については、「[Office 365 グループを作成できるユーザーを管理する](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d140f-154">For more information, see [Manage who can create Office 365 Groups](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups).</span></span>

<span data-ttu-id="d140f-155">このオプションがない場合は、PowerShell を使用してパブリックチームを作成し、グローバル管理者をチーム所有者として追加することができます。</span><span class="sxs-lookup"><span data-stu-id="d140f-155">If this isn't an option, you can use PowerShell to create a public team and add a global admin as the team owner.</span></span> <span data-ttu-id="d140f-156">次に、グローバル管理者にチーム名の横にある [**その他のオプション**] をクリックし、[**チームの編集**] をクリックして、プライバシーを組織全体に変更します。**組織内のすべてのユーザーが自動的に追加され**ます。</span><span class="sxs-lookup"><span data-stu-id="d140f-156">Then, have the global admin click **More options** next to the team name, click **Edit team**, and then change the privacy to **Org-wide - Everyone in your organization will be automatically added**.</span></span> <span data-ttu-id="d140f-157">チーム所有者のみが [チームの**編集**] オプションにアクセスできます。また、グローバル管理者のみが**組織全体**のオプションを表示できます。</span><span class="sxs-lookup"><span data-stu-id="d140f-157">Note that only team owners can access the **Edit team** option and only global admins can see the **Org-wide** option.</span></span>

### <a name="is-there-a-way-to-convert-an-existing-team-to-an-org-wide-team"></a><span data-ttu-id="d140f-158">既存のチームを組織全体のチームに変換する方法はありますか?</span><span class="sxs-lookup"><span data-stu-id="d140f-158">Is there a way to convert an existing team to an org-wide team?</span></span>

<span data-ttu-id="d140f-159">グローバル管理者は、チームクライアントで編集することで、既存のチームを組織全体のチームに変換できます。</span><span class="sxs-lookup"><span data-stu-id="d140f-159">Global admins can convert an existing team to an org-wide team by editing it in Teams client.</span></span> <span data-ttu-id="d140f-160">チーム名に移動し、[**その他のオプション** > **] をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="d140f-160">Go to the team name, click **More options** > **Edit team**.</span></span>
