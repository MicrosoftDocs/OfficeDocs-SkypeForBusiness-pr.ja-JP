---
title: Microsoft Teams でタグを管理する
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: acolonna, salu
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams で組織でのタグの使用方法を管理する方法について説明します。
ms.openlocfilehash: ab57fe5a0528ad5e33b20929bd224cb33273197e
ms.sourcegitcommit: 745b37921a878f1b524a274bfb2fd0732716a5c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2021
ms.locfileid: "52498782"
---
# <a name="manage-tags-in-microsoft-teams"></a><span data-ttu-id="e68e7-103">Microsoft Teams でタグを管理する</span><span class="sxs-lookup"><span data-stu-id="e68e7-103">Manage tags in Microsoft Teams</span></span>

## <a name="overview"></a><span data-ttu-id="e68e7-104">概要</span><span class="sxs-lookup"><span data-stu-id="e68e7-104">Overview</span></span>

<span data-ttu-id="e68e7-105">Microsoft Teams のタグを使用すると、チーム内の一部のユーザーとすばやく簡単につながることができます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-105">Tags in Microsoft Teams let users quickly and easily connect with a subset of people on a team.</span></span> <span data-ttu-id="e68e7-106">役割、プロジェクト、スキル、場所などの属性に基づいてユーザーを分類するカスタム タグを作成して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-106">You can create and assign custom tags to categorize people based on attributes, such as role, project, skill, or location.</span></span> <span data-ttu-id="e68e7-107">または、[シフト アプリ](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts)のスケジュールとシフト情報に基づいて、ユーザーにタグを自動的に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-107">Or, tags can be automatically assigned to people based on their schedule and shift information in the [Shifts app](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts).</span></span> <span data-ttu-id="e68e7-108">タグが 1 人または複数のチーム メンバーに追加されると、チャネル投稿でチームの誰もがそれを @メンションで使うことができ、そのタグが割り当てられているユーザーのみと会話を開始することもできます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-108">After a tag is added to one or multiple team members, it can be used in @mentions by anyone on the team in a channel post or to start a conversation with only those people who are assigned that tag.</span></span>

<span data-ttu-id="e68e7-109">前述のとおり、Teams には 2 種類のタグがあります。</span><span class="sxs-lookup"><span data-stu-id="e68e7-109">As mentioned earlier, there are two kinds of tags in Teams.</span></span>

- <span data-ttu-id="e68e7-110">**カスタム タグ**: チームの所有者とチーム メンバー (機能が有効になっている場合) は、手動でタグを作成し、ユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-110">**Custom tags**: Team owners and team members (if the feature is enabled for them) can manually create and assign tags to people.</span></span> <span data-ttu-id="e68e7-111">たとえば、"デザイナー" や "放射線科医" タグは、ユーザーの名前を入力しなくても、チーム内のこれらのユーザーのセットに到達します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-111">For example, a "Designer" or "Radiologist" tag will reach those sets of people on a team without having to type their names.</span></span>
- <span data-ttu-id="e68e7-112">**シフトでのタグ付け**: この機能を使用すると、Teams の[シフトアプリ](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop)内のスケジュールとシフト グループの名前に一致するタグが自動的にユーザーに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-112">**Tagging by shift**: With this feature, people are automatically assigned tags that match their schedule and shift group name in the [Shifts app](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) in Teams.</span></span> <span data-ttu-id="e68e7-113">たとえば、"EngineerOnCall" (待機中のエンジニア) タグは、チャットまたはチャネル投稿でタグが使用されたときに作業をするようにシフトでスケジュールされているすべてのエンジニアに到達します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-113">For example, the "EngineerOnCall" tag reaches all engineers who are scheduled in Shifts to work at the time the tag is used in a chat or channel post.</span></span> <span data-ttu-id="e68e7-114">シフトでのタグ付けを使用すると、ユーザーが情報をすばやく伝える必要がある場合に、シフト中のスタッフの名前を推測することなく知ることができます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-114">With tagging by shift, Teams takes the guesswork out of knowing the name of on-shift staff when users need to quickly relay information.</span></span> <span data-ttu-id="e68e7-115">シフトでのタグ付けは、JDA、Kronos、AMiON などの主要な従業員管理システムでも、Teams のシフトと統合することによりサポートされます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-115">Tagging by shift can also be backed by major workforce management systems like JDA, Kronos, and AMiON by integrating them with Shifts in Teams.</span></span> <span data-ttu-id="e68e7-116">この機能を設定する方法の詳細については、「[シフトでのタグ付けを設定する](#set-up-tagging-by-shift)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e68e7-116">To learn more about how to set up this feature, see [Set up tagging by shift](#set-up-tagging-by-shift).</span></span>

> [!NOTE]
> <span data-ttu-id="e68e7-117">タグは、プライベート チャネルではまだサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e68e7-117">Tags are not yet supported in private channels.</span></span> <span data-ttu-id="e68e7-118">タグは、GCC High または国防総省 (DoD) 組織では使用できません。</span><span class="sxs-lookup"><span data-stu-id="e68e7-118">Tags are not available in GCC High, or Department of Defense (DoD) organizations.</span></span> 

## <a name="how-tags-work"></a><span data-ttu-id="e68e7-119">タグの動作</span><span class="sxs-lookup"><span data-stu-id="e68e7-119">How tags work</span></span>

<span data-ttu-id="e68e7-120">タグは、特定のチームのユーザーに手動で追加することも、自動的に割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-120">A tag can be manually added or automatically assigned to a person on a specific team.</span></span> <span data-ttu-id="e68e7-121">その後、チャットまたはチームの標準チャネルの投稿の **宛先** 行の @メンションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-121">It can then be used in @mentions on the **To** line in a chat or in a post on any standard channel of the team.</span></span> <span data-ttu-id="e68e7-122">Teams でタグを使用する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-122">Here's some examples of how tags can be used in Teams:</span></span>

- <span data-ttu-id="e68e7-123">ストア マネージャーがチャネルにお知らせを投稿して、すべてのレジ係に通知する。</span><span class="sxs-lookup"><span data-stu-id="e68e7-123">A store manager posts an announcement to a channel to notify all cashiers.</span></span>
- <span data-ttu-id="e68e7-124">病院の管理者が、チャネル内のすべての放射線科医にメッセージを送信する。</span><span class="sxs-lookup"><span data-stu-id="e68e7-124">A hospital administrator sends a message to all radiologists in a channel.</span></span>
- <span data-ttu-id="e68e7-125">マーケティング マネージャーが、すべてのデザイナーとグループ チャットを開始する。</span><span class="sxs-lookup"><span data-stu-id="e68e7-125">A marketing manager starts a group chat with all designers.</span></span>
- <span data-ttu-id="e68e7-126">看護師が、すべての待機中の心臓専門医にメッセージを送信する。</span><span class="sxs-lookup"><span data-stu-id="e68e7-126">A nurse sends a message to all on-call cardiologists.</span></span> <span data-ttu-id="e68e7-127">(近日公開)</span><span class="sxs-lookup"><span data-stu-id="e68e7-127">(coming soon)</span></span>
- <span data-ttu-id="e68e7-128">システム エンジニアがチャネルにアナウンスを投稿して、すべてのシフト中のフィールド エンジニアに通知する。</span><span class="sxs-lookup"><span data-stu-id="e68e7-128">A system engineer posts an announcement to a channel to notify all on-shift field engineers.</span></span> <span data-ttu-id="e68e7-129">(近日公開)</span><span class="sxs-lookup"><span data-stu-id="e68e7-129">(coming soon)</span></span>

<span data-ttu-id="e68e7-130">チャネルの会話でタグが @メンションされると、他の @メンションと同様に、タグに関連付けられているチーム メンバーに通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-130">When a tag is @mentioned in a channel conversation, team members associated with the tag will get notified, just like any other @mention.</span></span>

## <a name="manage-custom-tags-for-your-organization"></a><span data-ttu-id="e68e7-131">組織のカスタム タグを管理する</span><span class="sxs-lookup"><span data-stu-id="e68e7-131">Manage custom tags for your organization</span></span>

<span data-ttu-id="e68e7-132">管理者は、Microsoft Teams 管理センターで、タグを組織全体で使用する方法を制御できます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-132">As an admin, you can control how tags are used across your organization in the Microsoft Teams admin center.</span></span> <span data-ttu-id="e68e7-133">現時点では、PowerShell を使用してタグを管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="e68e7-133">Currently, you can't use PowerShell to manage tags.</span></span>

![Microsoft Teams 管理センターのタグ付け設定のスクリーンショット。](media/manage-tags-admin-settings.png)

<span data-ttu-id="e68e7-135">各チームは最大 100 個のタグを持つことができ、1 つのタグに対して最大 100 人のチーム メンバーを、1 人のユーザーに対して最大 25 個のタグを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-135">A team can have up to 100 tags, up to 100 team members can be assigned to a tag, and up to 25 tags can be assigned to a single user.</span></span> 

### <a name="set-who-can-add-custom-tags"></a><span data-ttu-id="e68e7-136">カスタム タグを追加できるユーザーを設定する</span><span class="sxs-lookup"><span data-stu-id="e68e7-136">Set who can add custom tags</span></span>

<span data-ttu-id="e68e7-137">既定では、チームの所有者がカスタム タグを追加できます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-137">By default, team owners can add custom tags.</span></span> <span data-ttu-id="e68e7-138">この設定を変更して、チームの所有者とチーム メンバーがタグを作成、編集、削除、管理できるようにするか、組織のタグをオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-138">You can change this setting to allow team owners and team members to create, edit, delete, and manage tags or you can turn off tags for your organization.</span></span>

1. <span data-ttu-id="e68e7-139">Microsoft Teams 管理センターの左側のナビゲーションで、**[組織全体の設定]** > **[Teams の設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e68e7-139">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="e68e7-140">**[タグ付け]** で、**[タグの管理者]** の横で、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-140">Under **Tagging**, next to **Tags are managed by**, select one of the following options:</span></span>

    - <span data-ttu-id="e68e7-141">**[チームの所有者とメンバー]**: チームの所有者とメンバーにタグの管理を許可します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-141">**Team owners and members**: Allow team owners and members to manage tags.</span></span>
    - <span data-ttu-id="e68e7-142">**[チームの所有者]**: チームの所有者にタグの管理を許可します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-142">**Team owners**: Allow team owners to manage tags.</span></span>
    - <span data-ttu-id="e68e7-143">**[無効]**: タグをオフにします。</span><span class="sxs-lookup"><span data-stu-id="e68e7-143">**Disabled**: Turn off tags.</span></span>

### <a name="configure-custom-tags-settings"></a><span data-ttu-id="e68e7-144">カスタム タグの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="e68e7-144">Configure custom tags settings</span></span>

<span data-ttu-id="e68e7-145">次のタグ設定を構成して、組織全体でのカスタム タグの使用方法を制御できます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-145">You can configure the following tags settings to control how custom tags are used across your organization.</span></span>

1. <span data-ttu-id="e68e7-146">Microsoft Teams 管理センターの左側のナビゲーションで、**[組織全体の設定]** > **[Teams の設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e68e7-146">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="e68e7-147">**[タグ付け]** で、組織のニーズに応じて次の設定を行います。</span><span class="sxs-lookup"><span data-stu-id="e68e7-147">Under **Tagging**, set the following, depending on the needs of your organization.</span></span>

    - <span data-ttu-id="e68e7-148">**[チーム所有者に、タグの管理が可能なユーザーを上書きしてもらいます]**: この設定をオンにすると、チーム の所有者はチーム メンバーがチーム内でタグを作成および管理できるかどうかを設定できます。また、**[タグの管理者]** 設定の値を各チームの既定値に設定することができます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-148">**Let team owners override who can manage tags**: When you turn on this setting, team owners can set whether team members can create and manage tags within a team and the value of the **Tags are managed by** setting is the default value for each team.</span></span> <span data-ttu-id="e68e7-149">この設定をオフにした場合、**[タグの管理者]** 設定をチームごとに変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="e68e7-149">If you turn off this setting, the **Tags are managed by** setting can't be changed per team.</span></span>
    - <span data-ttu-id="e68e7-150">**[おすすめの既定のタグ]**: 既定のタグのセットを追加するには、これを使用します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-150">**Suggested default tags**: Use this to add a set of default tags.</span></span> <span data-ttu-id="e68e7-151">最大 25 個のタグを追加でき、各タグには最大 25 文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-151">You can add up to 25 tags, and each tag can contain a maximum of 25 characters.</span></span> <span data-ttu-id="e68e7-152">チームの所有者とメンバー (機能が有効になっている場合) は、これらの推奨タグを使用したり、追加、または新しいタグのセットを作成したりできます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-152">Team owners and members (if the feature is enabled for them) can use these suggestions, add to them, or create a new set of tags.</span></span>
    - <span data-ttu-id="e68e7-153">**[カスタム タグの作成を許可する]**: この設定をオンにすると、ユーザーが設定したおすすめの既定のタグ以外のタグを追加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e68e7-153">**Let custom tags be created**: Turn on this setting to let people add tags other than the suggested default tags that you set.</span></span> <span data-ttu-id="e68e7-154">これがオフになっている場合、ユーザーはおすすめの既定のタグのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-154">If this is turned off, people can only use the suggested default tags.</span></span> <span data-ttu-id="e68e7-155">これをオフにする場合は、必ず 1 つ以上の既定のタグを追加してください。</span><span class="sxs-lookup"><span data-stu-id="e68e7-155">If you turn this off, make sure that you add one or more default tags.</span></span>

## <a name="manage-custom-tags-settings-for-a-team"></a><span data-ttu-id="e68e7-156">チームのカスタム タグの設定を管理する</span><span class="sxs-lookup"><span data-stu-id="e68e7-156">Manage custom tags settings for a team</span></span>

<span data-ttu-id="e68e7-157">Microsoft Teams 管理センターで **[チーム所有者に、タグの管理が可能なユーザーを上書きしてもらいます]** 設定をオンにした場合、チームの所有者は、メンバーがチーム レベルでタグを追加できるかどうかを設定できます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-157">If you turned on the **Let team owners override who can manage tags** setting in the Microsoft Teams admin center, team owners can set whether members can add tags at the team level.</span></span> <span data-ttu-id="e68e7-158">これを行うには、チームの **[設定]** タブで、**[タグ]** に移動し、タグを追加できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-158">To do this, on the **Settings** tab for a team, go to **Tags**, and then choose who can add tags.</span></span>

![チーム レベルでのタグ設定のスクリーンショット](media/manage-tags-team-settings.png)

## <a name="use-tags"></a><span data-ttu-id="e68e7-160">タグを使用する</span><span class="sxs-lookup"><span data-stu-id="e68e7-160">Use tags</span></span>

<span data-ttu-id="e68e7-161">カスタム タグを追加する方法と、シフトでのタグ付けを設定する方法を次に示します (Teams でシフト アプリを使用している場合)。</span><span class="sxs-lookup"><span data-stu-id="e68e7-161">Here's how to add custom tags and how to set up tagging by shift (if you're using the Shifts app in Teams).</span></span> <span data-ttu-id="e68e7-162">詳細については、「[Teams でのタグの使用](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e68e7-162">To learn more, check out [Using tags in Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).</span></span>

### <a name="create-and-assign-custom-tags"></a><span data-ttu-id="e68e7-163">カスタム タグを作成して割り当てる</span><span class="sxs-lookup"><span data-stu-id="e68e7-163">Create and assign custom tags</span></span>

<span data-ttu-id="e68e7-164">カスタム タグを作成して割り当てるには、アプリの左側にある **[Teams]** を選択し、一覧でチームを見つけます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-164">To create and assign custom tags, select **Teams** on the left side of the app, and then find your team in the list.</span></span> <span data-ttu-id="e68e7-165">**˙˙˙ [その他のオプション]** を選択し、**[タグを管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-165">Select **˙˙˙ More options**, and then choose **Manage tags**.</span></span> <span data-ttu-id="e68e7-166">ここで、タグを作成してチームのユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-166">Here, you can create tags and assign them to people on your team.</span></span>

![<span data-ttu-id="e68e7-167">Teams クライアントでタグを適用する方法のスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="e68e7-167">Screenshot of how to apply tags in the Teams client</span></span> ](media/manage-tags-teams.png)

<span data-ttu-id="e68e7-168">タグを削除するには、タグの横にある **˙˙˙ [その他のオプション]** を選択し、**[タグを削除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-168">To delete a tag, select **˙˙˙ More options** next to the tag, and then select **Delete tag**.</span></span>

### <a name="set-up-tagging-by-shift"></a><span data-ttu-id="e68e7-169">シフトでのタグ付けを設定する</span><span class="sxs-lookup"><span data-stu-id="e68e7-169">Set up tagging by shift</span></span>

<span data-ttu-id="e68e7-170">シフトでのタグ付けを使用すると、シフト中のユーザーにリアルタイムで連絡できます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-170">Tagging by shift allows your users to reach the people on-shift in real-time.</span></span> <span data-ttu-id="e68e7-171">Teams は、シフト アプリからスケジュールとシフト グループの名前に一致するタグをユーザーに自動的に割り当て、動的な役割ベースのメッセージングを可能にします。</span><span class="sxs-lookup"><span data-stu-id="e68e7-171">Teams automatically assigns users with tags matching their schedule and shift group name from the Shifts app, enabling dynamic role-based messaging.</span></span> <span data-ttu-id="e68e7-172">通知は、タグがチャットの開始またはチャネル投稿で使用されたときにシフト中のユーザーにのみ送信されます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-172">Notifications are sent only to those people who are on shift at the time a tag is used to start a chat or in a channel post.</span></span> 

1. <span data-ttu-id="e68e7-173">Teams で、[シフト アプリ](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop)に移動します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-173">In Teams, go to the [Shifts app](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop).</span></span>
2. <span data-ttu-id="e68e7-174">[シフト グループ](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup)を作成し、役割などの属性に続けて名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-174">Create [shift groups](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) and name them after an attribute such as a role.</span></span> <span data-ttu-id="e68e7-175">たとえば、"EngineerOnCall" (待機中のエンジニア) などです。</span><span class="sxs-lookup"><span data-stu-id="e68e7-175">For example, EngineerOnCall.</span></span> <span data-ttu-id="e68e7-176">シフト グループの名前はタグの名前になります。</span><span class="sxs-lookup"><span data-stu-id="e68e7-176">The shift group name will be the name of the tag.</span></span>
3. <span data-ttu-id="e68e7-177">チームのメンバーにシフトを割り当てて、[スケジュールを入力](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea)します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-177">[Fill out a schedule](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea) by assigning shifts to members of your teams.</span></span> <span data-ttu-id="e68e7-178">完了したら、シフト アプリの右上隅にある **[チームと共有]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-178">When you're finished, in the upper-right corner of the Shifts app, select **Share with team**.</span></span>
4. <span data-ttu-id="e68e7-179">スケジュールされたシフトがタグ付けサービスに設定されるまで 15 分待ちます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-179">Wait 15 minutes for the scheduled shifts to populate the tagging service.</span></span>
5. <span data-ttu-id="e68e7-180">Teams でタグを使用する場所であればどこでもこのタグを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-180">Use the tag anywhere you use tags in Teams.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e68e7-181">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e68e7-181">Related topics</span></span>

[<span data-ttu-id="e68e7-182">Teams でのタグの使用</span><span class="sxs-lookup"><span data-stu-id="e68e7-182">Using tags in Teams</span></span>](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[<span data-ttu-id="e68e7-183">Teams で組織のシフト アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="e68e7-183">Manage the Shifts app for your organization in Teams</span></span>](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[<span data-ttu-id="e68e7-184">シフトのヘルプ ドキュメント</span><span class="sxs-lookup"><span data-stu-id="e68e7-184">Shifts Help documentation</span></span>](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
