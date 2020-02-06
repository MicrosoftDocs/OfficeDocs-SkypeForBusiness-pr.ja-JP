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
description: Teams で組織全体にわたるチームを作成および管理する方法について説明します。
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f291e0c2902754f346dfadb855e4e6bc6fbd573c
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41795156"
---
# <a name="create-an-org-wide-team-in-microsoft-teams"></a><span data-ttu-id="3ae79-103">Microsoft Teams で組織全体にわたるチームを作成する</span><span class="sxs-lookup"><span data-stu-id="3ae79-103">Create an org-wide team in Microsoft Teams</span></span>

<span data-ttu-id="3ae79-104">組織全体のチームは、小規模から中規模の組織内の全員がコラボレーションのための単一チームの一部に自動的になれる方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="3ae79-104">Org-wide teams provide an automatic way for everyone in a small to medium-sized organization to be a part of a single team for collaboration.</span></span>

<span data-ttu-id="3ae79-105">組織全体のチームでは、グローバル管理者は、組織内のすべてのユーザーを取り込むパブリック チームを簡単に作成し、組織でユーザーの出入りがあっても Active Directory のメンバーシップを最新の状態に保つことができます。</span><span class="sxs-lookup"><span data-stu-id="3ae79-105">With org-wide teams, global admins can easily create a public team that pulls in every user in the organization and keeps the membership up to date with Active Directory as users join and leave the organization.</span></span> <span data-ttu-id="3ae79-106">組織全体のチームを作成できるのはグローバル管理者のみです。現在、組織全体のチームは、ユーザー数が 5,000 を超えない組織に限定されています。</span><span class="sxs-lookup"><span data-stu-id="3ae79-106">Only global admins can create org-wide teams and currently an org-wide team is limited to organizations with no more than 5,000 users.</span></span> <span data-ttu-id="3ae79-107">組織全体のチーム数も、1 つのテナントに対し 5 つまでに制限されています。</span><span class="sxs-lookup"><span data-stu-id="3ae79-107">There's also a limit of five org-wide teams per tenant.</span></span> <span data-ttu-id="3ae79-108">これらの要件が満たされている場合、グローバル管理者がチームを作成する際、[**初めからチームを作成する**] を選択すると、[**組織全体**] オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ae79-108">If these requirements are met, global admins will see **Org-wide** as an option when they select **Build a team from scratch** when creating a team.</span></span> 

<span data-ttu-id="3ae79-109">![組織全体のチームを作成するための組織全体のオプションのスクリーンショット](media/create-org-wide-team.png "組織全体のチームを作成するための [組織全体] オプションのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="3ae79-109">![Screenshot of the Org-wide option to create an org-wide team](media/create-org-wide-team.png "Screen shot of the Org-wide option to create an org-wide team")</span></span>

<span data-ttu-id="3ae79-110">組織全体のチームが作成されると、すべてのグローバル管理者がチームの所有者として追加され、すべてのアクティブなユーザーがチーム メンバーとして追加されます。</span><span class="sxs-lookup"><span data-stu-id="3ae79-110">When an org-wide team is created, all global admins are added as team owners and all active users are added as team members.</span></span> <span data-ttu-id="3ae79-111">ライセンス未付与のユーザーもチームに追加されます。</span><span class="sxs-lookup"><span data-stu-id="3ae79-111">Unlicensed users are also added to the team.</span></span> <span data-ttu-id="3ae79-112">ライセンスのないユーザーが初めて Teams にサインインすると、Microsoft Teams の商用クラウド試用版のライセンスがそのユーザーに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="3ae79-112">The first time an unlicensed user signs in to Teams, the user is assigned a Microsoft Teams Commercial Cloud Trial license.</span></span> <span data-ttu-id="3ae79-113">試用版ライセンスの詳細については、「[Teams の商用クラウドの試用提供を管理する](iw-trial-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ae79-113">To learn more about the trial license, check out [Manage the Teams Commercial Cloud Trial offer](iw-trial-teams.md).</span></span> 

<span data-ttu-id="3ae79-114">これらの種類のアカウントは、組織全体のチームには追加されません。</span><span class="sxs-lookup"><span data-stu-id="3ae79-114">These types of accounts won't be added to your org-wide team:</span></span>

- <span data-ttu-id="3ae79-115">サインインがブロックされるアカウントの種類</span><span class="sxs-lookup"><span data-stu-id="3ae79-115">Accounts that are blocked from sign in</span></span>
- <span data-ttu-id="3ae79-116">ゲスト ユーザー</span><span class="sxs-lookup"><span data-stu-id="3ae79-116">Guest users</span></span>
- <span data-ttu-id="3ae79-117">サービス アカウント</span><span class="sxs-lookup"><span data-stu-id="3ae79-117">Service accounts</span></span>
- <span data-ttu-id="3ae79-118">会議室または備品用のアカウント</span><span class="sxs-lookup"><span data-stu-id="3ae79-118">Room or equipment accounts</span></span>
- <span data-ttu-id="3ae79-119">共有メール ボックスでサポートされているアカウント</span><span class="sxs-lookup"><span data-stu-id="3ae79-119">Accounts backed by a shared mailbox</span></span>

<span data-ttu-id="3ae79-120">組織のディレクトリが更新されて新しいアクティブなユーザーが追加されたり、ユーザーが会社を退職したためにアカウントが無効になったりした場合、変更は自動的に同期され、ユーザーはチームに追加または削除されます。</span><span class="sxs-lookup"><span data-stu-id="3ae79-120">As your organization's directory is updated to include new active users or if users no longer work at your company and their account is disabled, changes are automatically synced and the users are added or removed from the team.</span></span> <span data-ttu-id="3ae79-121">チーム メンバーは、組織全体のチームから抜けることはできません。</span><span class="sxs-lookup"><span data-stu-id="3ae79-121">Team members can't leave an org-wide team.</span></span> <span data-ttu-id="3ae79-122">チームの所有者は、必要に応じてユーザーを手動で追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="3ae79-122">As a team owner, you can manually add or remove users if needed.</span></span>

> [!NOTE]
> - <span data-ttu-id="3ae79-123">グローバル管理者がチーム作成時に [**組織全体**] オプションが表示されない場合、機能がまだ展開中であるか、組織全体チーム数の上限である 5 チームに達したか、メンバー数 5,000 の現在の制限を超えている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3ae79-123">If you don't see the **Org-wide** option when creating a team and you're a global admin, the feature might still be rolling out, you have reached the five org-wide teams limit, or your organization might have more than the current size limit of 5,000 members.</span></span> <span data-ttu-id="3ae79-124">将来的には、これらの制限を緩和しようと考えています。</span><span class="sxs-lookup"><span data-stu-id="3ae79-124">We're looking to increase this limit in the future.</span></span>
> - <span data-ttu-id="3ae79-125">会議室の一覧、備品、リソース アカウントに含まれていない会議室が組織全体のチームに追加または同期される可能性がありますが、</span><span class="sxs-lookup"><span data-stu-id="3ae79-125">Rooms that aren't a part of a room list, equipment, and resource accounts might be added or synced to the org-wide team.</span></span> <span data-ttu-id="3ae79-126">チームの所有者は、これらのアカウントをチームから簡単に削除できます。</span><span class="sxs-lookup"><span data-stu-id="3ae79-126">Team owners can easily remove these accounts from the team.</span></span>
> - <span data-ttu-id="3ae79-127">メンバーを追加または削除するシステムによるすべての操作は、[全般] チャネルに投稿されます。</span><span class="sxs-lookup"><span data-stu-id="3ae79-127">All actions by the system to add or remove members are posted in the General channel.</span></span> <span data-ttu-id="3ae79-128">また、Teams クライアント チャネルで新しいアクティビティがあったとして、チャネルにマークされます。</span><span class="sxs-lookup"><span data-stu-id="3ae79-128">The channel will also be marked as having new activity in the Teams client.</span></span>

## <a name="best-practices"></a><span data-ttu-id="3ae79-129">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="3ae79-129">Best practices</span></span>

<span data-ttu-id="3ae79-130">組織全体のチームを最大限に利用するために、チーム所有者に次の方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3ae79-130">To get the most out of your org-wide team, we recommend team owners do the following.</span></span>

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a><span data-ttu-id="3ae79-131">チームの所有者のみが一般チャネルに投稿できるようにする</span><span class="sxs-lookup"><span data-stu-id="3ae79-131">Allow only team owners to post to the General channel</span></span>

<span data-ttu-id="3ae79-132">チームの所有者だけが一般チャネルに投稿することで、チャネルのノイズを低減します。</span><span class="sxs-lookup"><span data-stu-id="3ae79-132">Reduce channel noise by having only team owners post to the General channel.</span></span> <span data-ttu-id="3ae79-133">チームにアクセスし、**[˙˙˙その他のオプション]** > **[チームの管理]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="3ae79-133">Go to the team and click **˙˙˙ More options** > **Manage Team**.</span></span> <span data-ttu-id="3ae79-134">**[設定]** タブで、**[メンバーのアクセス許可]** をクリックし、**[所有者のみがメッセージを投稿する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3ae79-134">On the **Settings** tab, click **Member permissions** > select **Only owners can post messages**.</span></span>

### <a name="turn-off-team-and-team-name-mentions"></a><span data-ttu-id="3ae79-135">@team と @[チーム名] のメンションを無効にする</span><span class="sxs-lookup"><span data-stu-id="3ae79-135">Turn off @team and @[team name] mentions</span></span>

 <span data-ttu-id="3ae79-136">@メンションを減らして、組織全体がオーバー ロードしないようにします。</span><span class="sxs-lookup"><span data-stu-id="3ae79-136">Reduce @mentions to keep them from overloading the entire organization.</span></span> <span data-ttu-id="3ae79-137">チームにアクセスし、**[˙˙˙その他のオプション]** > **[チームの管理]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="3ae79-137">Go to the team and click **˙˙˙ More options** > **Manage Team**.</span></span> <span data-ttu-id="3ae79-138">**[設定]** タブで、<strong>[@メンション]</strong> > **[メンバーに @team または @ [チーム名] のオプションを表示する]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3ae79-138">On the **Settings** tab, click <strong>@mentions</strong> > turn off **Show members the option to @team or @[team name]**.</span></span> 

### <a name="automatically-show-important-channels"></a><span data-ttu-id="3ae79-139">重要なチャネルを自動的に表示する</span><span class="sxs-lookup"><span data-stu-id="3ae79-139">Automatically show important channels</span></span>

<span data-ttu-id="3ae79-140">重要なチャネルを表示して、組織内のすべてのユーザーが特定の会話に参加していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3ae79-140">Show important channels to ensure everyone in your organization engages in specific conversations.</span></span> <span data-ttu-id="3ae79-141">詳細については、「[チーム全体に対してチャネルをお気に入りに自動追加する](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ae79-141">To learn more, see [Auto-favorite channels for the whole team](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6).</span></span> 

### <a name="set-up-channel-moderation"></a><span data-ttu-id="3ae79-142">チャネル モデレーションを設定する</span><span class="sxs-lookup"><span data-stu-id="3ae79-142">Set up channel moderation</span></span>

<span data-ttu-id="3ae79-143">チャネル モデレーションをセットアップし、特定のチームメンバーにモデレーター機能を付与することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="3ae79-143">Consider setting up channel moderation and giving moderator capabilities to certain team members.</span></span> <span data-ttu-id="3ae79-144">(モデレーションが設定されると、チームの所有者にモデレーター機能が自動的に付与されます) モデレーターは、チャネルで新しい投稿を開始できるユーザーを制御したり、モデレーターの追加および削除を行ったり、チーム メンバーが既存のチャネル メッセージに返信できるかどうかを制御したり、ボットとコネクタがチャネル メッセージを送信できるかどうかを制御したりできます。</span><span class="sxs-lookup"><span data-stu-id="3ae79-144">(When moderation is set up, team owners are given moderator capabilities automatically.) Moderators can control who can start a new post in a channel, add and remove moderators, control whether team members can reply to existing channel messages, and control whether bots and connectors can submit channel messages.</span></span> <span data-ttu-id="3ae79-145">詳細については、「[Microsoft Teams でチャネル モデレーションをセットアップして管理する](manage-channel-moderation-in-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ae79-145">For more information, see [Set up and manage channel moderation in Microsoft Teams](manage-channel-moderation-in-teams.md).</span></span>

### <a name="remove-accounts-that-might-not-belong"></a><span data-ttu-id="3ae79-146">所属していない可能性のあるアカウントの削除</span><span class="sxs-lookup"><span data-stu-id="3ae79-146">Remove accounts that might not belong</span></span>

<span data-ttu-id="3ae79-147">メンバーは組織全体のチームから抜けることはできませんが、チームの所有者は、所属していないアカウントを削除することにより、チームの参加者名簿を管理できます。</span><span class="sxs-lookup"><span data-stu-id="3ae79-147">Even though members can’t leave an org-wide team, as a team owner, you can manage the team roster by removing accounts that don’t belong.</span></span> <span data-ttu-id="3ae79-148">**組織全体のチームからユーザーを削除するには、必ず Teams を使用してください**。</span><span class="sxs-lookup"><span data-stu-id="3ae79-148">**Make sure you use Teams to remove users from your org-wide team**.</span></span> <span data-ttu-id="3ae79-149">Microsoft 365 管理センターや Outlook のグループなど、別の方法でユーザーを削除した場合、そのユーザーは組織全体のチームに再び追加される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3ae79-149">If you use another way to remove a user, such as the Microsoft 365 admin center or from a group in Outlook, the user might be added back to the org-wide team.</span></span>

## <a name="faq"></a><span data-ttu-id="3ae79-150">FAQ</span><span class="sxs-lookup"><span data-stu-id="3ae79-150">FAQ</span></span>

### <a name="is-there-a-way-to-create-an-org-wide-team-other-than-using-the-teams-client"></a><span data-ttu-id="3ae79-151">Teams クライアントを使用する以外に、組織全体のチームを作成する方法はありますか?</span><span class="sxs-lookup"><span data-stu-id="3ae79-151">Is there a way to create an org-wide team other than using the Teams client?</span></span>

<span data-ttu-id="3ae79-152">グローバル管理者が組織全体のチームを作成できるのは、Teams クライアントを使用する方法のみです。</span><span class="sxs-lookup"><span data-stu-id="3ae79-152">Global admins can only create an org-wide team by using the Teams client.</span></span> <span data-ttu-id="3ae79-153">組織がチームの作成を PowerShell を使用する場合に制限している場合、推奨される回避策は、チームを作成できるユーザーのセキュリティ グループにグローバル管理者を追加することです。</span><span class="sxs-lookup"><span data-stu-id="3ae79-153">If your organization limits creating teams to using PowerShell, the recommended workaround is to add your global admins to the security group of users who can create a team.</span></span> <span data-ttu-id="3ae79-154">詳細については、「[Office 365 グループを作成できるユーザーを管理する](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3ae79-154">For more information, see [Manage who can create Office 365 Groups](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups).</span></span>

<span data-ttu-id="3ae79-155">これが不可能な場合は、PowerShell を使用してパブリック チームを作成し、チームの所有者としてグローバル管理者を追加できます。</span><span class="sxs-lookup"><span data-stu-id="3ae79-155">If this isn't an option, you can use PowerShell to create a public team and add a global admin as the team owner.</span></span> <span data-ttu-id="3ae79-156">次に、グローバル管理者は、チーム名の横にある [**その他のオプション**] をクリックし、[**チームの編集**] をクリックし、プライバシーを [**組織全体: 組織内のすべてのユーザーが自動的に追加されます**] に変更します。</span><span class="sxs-lookup"><span data-stu-id="3ae79-156">Then, have the global admin click **More options** next to the team name, click **Edit team**, and then change the privacy to **Org-wide - Everyone in your organization will be automatically added**.</span></span> <span data-ttu-id="3ae79-157">[**チームの編集**] オプションにアクセスできるのはチームの所有者のみであること、[**組織全体**] オプションを表示できるのはグローバル管理者のみであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3ae79-157">Note that only team owners can access the **Edit team** option and only global admins can see the **Org-wide** option.</span></span>

### <a name="is-there-a-way-to-convert-an-existing-team-to-an-org-wide-team"></a><span data-ttu-id="3ae79-158">既存のチームを組織全体のチームに変換する方法はありますか?</span><span class="sxs-lookup"><span data-stu-id="3ae79-158">Is there a way to convert an existing team to an org-wide team?</span></span>

<span data-ttu-id="3ae79-159">グローバル管理者は、Teams クライアントで編集することにより、既存のチームを組織全体のチームに変換できます。</span><span class="sxs-lookup"><span data-stu-id="3ae79-159">Global admins can convert an existing team to an org-wide team by editing it in Teams client.</span></span> <span data-ttu-id="3ae79-160">チーム名にアクセスし、[**その他のオプション**] > [**チームの編集**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="3ae79-160">Go to the team name, click **More options** > **Edit team**.</span></span>

## <a name="see-also"></a><span data-ttu-id="3ae79-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ae79-161">See also</span></span>

<span data-ttu-id="3ae79-162">[Microsoft Teams で会社全体のチームを作成する](https://support.office.com/article/037bb27a-bcc9-48fe-8d72-44d9482420a3)方法に関するビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3ae79-162">Watch a video about about [creating a company-wide team in Microsoft Teams](https://support.office.com/article/037bb27a-bcc9-48fe-8d72-44d9482420a3).</span></span>
