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
description: 組織でタグを使用する方法を管理する方法についてMicrosoft Teams。
ms.openlocfilehash: ab57fe5a0528ad5e33b20929bd224cb33273197e
ms.sourcegitcommit: 745b37921a878f1b524a274bfb2fd0732716a5c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2021
ms.locfileid: "52498782"
---
# <a name="manage-tags-in-microsoft-teams"></a><span data-ttu-id="f3a6a-103">Microsoft Teams でタグを管理する</span><span class="sxs-lookup"><span data-stu-id="f3a6a-103">Manage tags in Microsoft Teams</span></span>

## <a name="overview"></a><span data-ttu-id="f3a6a-104">概要</span><span class="sxs-lookup"><span data-stu-id="f3a6a-104">Overview</span></span>

<span data-ttu-id="f3a6a-105">タグをMicrosoft Teams、ユーザーがチームの一部のユーザーとすばやく簡単に接続できます。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-105">Tags in Microsoft Teams let users quickly and easily connect with a subset of people on a team.</span></span> <span data-ttu-id="f3a6a-106">カスタム タグを作成して割り当て、ロール、プロジェクト、スキル、場所などの属性に基づいてユーザーを分類できます。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-106">You can create and assign custom tags to categorize people based on attributes, such as role, project, skill, or location.</span></span> <span data-ttu-id="f3a6a-107">または、Shifts アプリ のスケジュールとシフト情報に基づいて、タグをユーザーに自動的 [に割り当てることができます](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts)。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-107">Or, tags can be automatically assigned to people based on their schedule and shift information in the [Shifts app](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts).</span></span> <span data-ttu-id="f3a6a-108">タグを 1 人または複数のチーム メンバーに追加した後は、チャネル投稿でチームの誰でも @mentions で使用したり、そのタグが割り当てられているユーザーのみと会話を開始したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-108">After a tag is added to one or multiple team members, it can be used in @mentions by anyone on the team in a channel post or to start a conversation with only those people who are assigned that tag.</span></span>

<span data-ttu-id="f3a6a-109">前述のように、2 種類のタグがTeams。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-109">As mentioned earlier, there are two kinds of tags in Teams.</span></span>

- <span data-ttu-id="f3a6a-110">**カスタム タグ**: チーム所有者とチーム メンバー (機能が有効になっている場合) は、手動でタグを作成してユーザーに割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-110">**Custom tags**: Team owners and team members (if the feature is enabled for them) can manually create and assign tags to people.</span></span> <span data-ttu-id="f3a6a-111">たとえば、"Designer" または "Radiradi" タグは、名前を入力することなく、チームのこれらのユーザー セットに到達します。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-111">For example, a "Designer" or "Radiologist" tag will reach those sets of people on a team without having to type their names.</span></span>
- <span data-ttu-id="f3a6a-112">**シフトによるタグ** 付け: この機能を使用すると、ユーザーには、スケジュールとシフト グループ名に一致するタグが、Teams の [Shifts](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop)アプリで自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-112">**Tagging by shift**: With this feature, people are automatically assigned tags that match their schedule and shift group name in the [Shifts app](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) in Teams.</span></span> <span data-ttu-id="f3a6a-113">たとえば、"EngineerOnCall" タグは、チャットまたはチャネルの投稿でタグが使用された時点で、シフトで作業をスケジュールしているすべてのエンジニアに到達します。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-113">For example, the "EngineerOnCall" tag reaches all engineers who are scheduled in Shifts to work at the time the tag is used in a chat or channel post.</span></span> <span data-ttu-id="f3a6a-114">シフトによるタグ付Teams、ユーザーが情報をすばやく中継する必要があるときに、シフト上のスタッフの名前を知ることから推測を取り出します。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-114">With tagging by shift, Teams takes the guesswork out of knowing the name of on-shift staff when users need to quickly relay information.</span></span> <span data-ttu-id="f3a6a-115">シフトによるタグ付けは、JDA、Kronos、AMiON のような主要な従業員管理システムによってもサポートされ、Teams の Shifts と統合されます。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-115">Tagging by shift can also be backed by major workforce management systems like JDA, Kronos, and AMiON by integrating them with Shifts in Teams.</span></span> <span data-ttu-id="f3a6a-116">この機能を設定する方法の詳細については、「Shift でタグ [付けを設定する」を参照してください](#set-up-tagging-by-shift)。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-116">To learn more about how to set up this feature, see [Set up tagging by shift](#set-up-tagging-by-shift).</span></span>

> [!NOTE]
> <span data-ttu-id="f3a6a-117">タグは、プライベート チャネルではまだサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-117">Tags are not yet supported in private channels.</span></span> <span data-ttu-id="f3a6a-118">タグは、GCC国防総省 (DoD) 組織では使用できません。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-118">Tags are not available in GCC High, or Department of Defense (DoD) organizations.</span></span> 

## <a name="how-tags-work"></a><span data-ttu-id="f3a6a-119">タグの動作</span><span class="sxs-lookup"><span data-stu-id="f3a6a-119">How tags work</span></span>

<span data-ttu-id="f3a6a-120">タグは、手動で追加したり、特定のチームのユーザーに自動的に割り当てたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-120">A tag can be manually added or automatically assigned to a person on a specific team.</span></span> <span data-ttu-id="f3a6a-121">チャットの [to] @mentionsまたはチームの標準チャネルの投稿で使用できます。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-121">It can then be used in @mentions on the **To** line in a chat or in a post on any standard channel of the team.</span></span> <span data-ttu-id="f3a6a-122">次に、タグを使用する方法の例を示Teams。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-122">Here's some examples of how tags can be used in Teams:</span></span>

- <span data-ttu-id="f3a6a-123">ストア マネージャーがチャネルにアナウンスを投稿して、すべてのレジ係に通知します。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-123">A store manager posts an announcement to a channel to notify all cashiers.</span></span>
- <span data-ttu-id="f3a6a-124">病院の管理者は、チャネル内のすべてのラジオロジストにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-124">A hospital administrator sends a message to all radiologists in a channel.</span></span>
- <span data-ttu-id="f3a6a-125">マーケティング マネージャーは、すべてのデザイナーとグループ チャットを開始します。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-125">A marketing manager starts a group chat with all designers.</span></span>
- <span data-ttu-id="f3a6a-126">看護師が、すべてのオンコールのカーディジストにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-126">A nurse sends a message to all on-call cardiologists.</span></span> <span data-ttu-id="f3a6a-127">(近日公開)</span><span class="sxs-lookup"><span data-stu-id="f3a6a-127">(coming soon)</span></span>
- <span data-ttu-id="f3a6a-128">システム エンジニアは、すべてのオンシフト フィールド エンジニアに通知するアナウンスをチャネルに投稿します。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-128">A system engineer posts an announcement to a channel to notify all on-shift field engineers.</span></span> <span data-ttu-id="f3a6a-129">(近日公開)</span><span class="sxs-lookup"><span data-stu-id="f3a6a-129">(coming soon)</span></span>

<span data-ttu-id="f3a6a-130">チャネル会話でタグ@mentionedすると、そのタグに関連付けられているチーム メンバーには、他のチーム メンバーと同様に通知が@mention。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-130">When a tag is @mentioned in a channel conversation, team members associated with the tag will get notified, just like any other @mention.</span></span>

## <a name="manage-custom-tags-for-your-organization"></a><span data-ttu-id="f3a6a-131">組織のカスタム タグを管理する</span><span class="sxs-lookup"><span data-stu-id="f3a6a-131">Manage custom tags for your organization</span></span>

<span data-ttu-id="f3a6a-132">管理者は、管理センターで組織全体でタグを使用する方法Microsoft Teamsできます。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-132">As an admin, you can control how tags are used across your organization in the Microsoft Teams admin center.</span></span> <span data-ttu-id="f3a6a-133">現時点では、PowerShell を使用してタグを管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-133">Currently, you can't use PowerShell to manage tags.</span></span>

![管理センターのタグ設定Microsoft Teamsスクリーンショット](media/manage-tags-admin-settings.png)

<span data-ttu-id="f3a6a-135">チームには最大 100 のタグを含め、最大 100 人のチーム メンバーをタグに割り当て、1 人のユーザーに最大 25 のタグを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-135">A team can have up to 100 tags, up to 100 team members can be assigned to a tag, and up to 25 tags can be assigned to a single user.</span></span> 

### <a name="set-who-can-add-custom-tags"></a><span data-ttu-id="f3a6a-136">カスタム タグを追加できるユーザーを設定する</span><span class="sxs-lookup"><span data-stu-id="f3a6a-136">Set who can add custom tags</span></span>

<span data-ttu-id="f3a6a-137">既定では、チーム所有者はカスタム タグを追加できます。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-137">By default, team owners can add custom tags.</span></span> <span data-ttu-id="f3a6a-138">この設定を変更して、チーム所有者とチーム メンバーがタグを作成、編集、削除、管理したり、組織のタグをオフにしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-138">You can change this setting to allow team owners and team members to create, edit, delete, and manage tags or you can turn off tags for your organization.</span></span>

1. <span data-ttu-id="f3a6a-139">管理センターの左側のナビゲーションMicrosoft Teams、[**組織全体の** 設定] をクリックTeams  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-139">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="f3a6a-140">[ **タグの管理**] の横 **にある**[タグの管理] で、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-140">Under **Tagging**, next to **Tags are managed by**, select one of the following options:</span></span>

    - <span data-ttu-id="f3a6a-141">**チームの所有者とメンバー**: チームの所有者とメンバーがタグを管理できます。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-141">**Team owners and members**: Allow team owners and members to manage tags.</span></span>
    - <span data-ttu-id="f3a6a-142">**チーム所有者**: チーム所有者がタグを管理できます。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-142">**Team owners**: Allow team owners to manage tags.</span></span>
    - <span data-ttu-id="f3a6a-143">**無効**: タグをオフにします。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-143">**Disabled**: Turn off tags.</span></span>

### <a name="configure-custom-tags-settings"></a><span data-ttu-id="f3a6a-144">カスタム タグ設定を構成する</span><span class="sxs-lookup"><span data-stu-id="f3a6a-144">Configure custom tags settings</span></span>

<span data-ttu-id="f3a6a-145">次のタグ設定を構成して、組織全体でカスタム タグを使用する方法を制御できます。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-145">You can configure the following tags settings to control how custom tags are used across your organization.</span></span>

1. <span data-ttu-id="f3a6a-146">管理センターの左側のナビゲーションMicrosoft Teams、[**組織全体の** 設定] をクリックTeams  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-146">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="f3a6a-147">[ **タグ付け]** で、組織のニーズに応じて、次の設定を行います。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-147">Under **Tagging**, set the following, depending on the needs of your organization.</span></span>

    - <span data-ttu-id="f3a6a-148">**チーム** 所有者がタグを管理できるユーザーをオーバーライドする: この設定を有効にすると、チーム所有者は、チーム メンバーがチーム内でタグを作成および管理できるかどうかを設定できます。タグの値は、各チームの既定値を設定して管理されます。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-148">**Let team owners override who can manage tags**: When you turn on this setting, team owners can set whether team members can create and manage tags within a team and the value of the **Tags are managed by** setting is the default value for each team.</span></span> <span data-ttu-id="f3a6a-149">この設定をオフにした場合、[ **タグ** は設定によって管理されます] をチームごとに変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-149">If you turn off this setting, the **Tags are managed by** setting can't be changed per team.</span></span>
    - <span data-ttu-id="f3a6a-150">**推奨される既定のタグ**: 既定のタグのセットを追加する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-150">**Suggested default tags**: Use this to add a set of default tags.</span></span> <span data-ttu-id="f3a6a-151">最大 25 のタグを追加できます。各タグには最大 25 文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-151">You can add up to 25 tags, and each tag can contain a maximum of 25 characters.</span></span> <span data-ttu-id="f3a6a-152">チームの所有者とメンバー (機能が有効になっている場合) は、これらの提案を使用したり、追加したり、新しいタグ セットを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-152">Team owners and members (if the feature is enabled for them) can use these suggestions, add to them, or create a new set of tags.</span></span>
    - <span data-ttu-id="f3a6a-153">**カスタム タグを作成する**: ユーザーが設定した推奨される既定のタグ以外のタグを追加するには、この設定をオンにします。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-153">**Let custom tags be created**: Turn on this setting to let people add tags other than the suggested default tags that you set.</span></span> <span data-ttu-id="f3a6a-154">これがオフになっている場合、ユーザーは推奨される既定のタグのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-154">If this is turned off, people can only use the suggested default tags.</span></span> <span data-ttu-id="f3a6a-155">これをオフにした場合は、必ず既定のタグを 1 つ以上追加してください。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-155">If you turn this off, make sure that you add one or more default tags.</span></span>

## <a name="manage-custom-tags-settings-for-a-team"></a><span data-ttu-id="f3a6a-156">チームのカスタム タグ設定を管理する</span><span class="sxs-lookup"><span data-stu-id="f3a6a-156">Manage custom tags settings for a team</span></span>

<span data-ttu-id="f3a6a-157">Microsoft Teams 管理センターで[チーム所有者がタグを管理できるユーザーをオーバーライドする] 設定をオンにした場合、チーム所有者はメンバーがチーム レベルでタグを追加できるかどうかを設定できます。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-157">If you turned on the **Let team owners override who can manage tags** setting in the Microsoft Teams admin center, team owners can set whether members can add tags at the team level.</span></span> <span data-ttu-id="f3a6a-158">これを行うには、チームの **[設定]** タブで 、[タグ]に移動し、タグを追加できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-158">To do this, on the **Settings** tab for a team, go to **Tags**, and then choose who can add tags.</span></span>

![チーム レベルでのタグ設定のスクリーンショット](media/manage-tags-team-settings.png)

## <a name="use-tags"></a><span data-ttu-id="f3a6a-160">タグを使用する</span><span class="sxs-lookup"><span data-stu-id="f3a6a-160">Use tags</span></span>

<span data-ttu-id="f3a6a-161">カスタム タグを追加する方法と、Shift でタグ付けを設定する方法を次に示します (Shifts アプリを使用している場合は、Teams)。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-161">Here's how to add custom tags and how to set up tagging by shift (if you're using the Shifts app in Teams).</span></span> <span data-ttu-id="f3a6a-162">詳細については、「 でタグを[使用する 」をTeams。](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)</span><span class="sxs-lookup"><span data-stu-id="f3a6a-162">To learn more, check out [Using tags in Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).</span></span>

### <a name="create-and-assign-custom-tags"></a><span data-ttu-id="f3a6a-163">カスタム タグを作成して割り当てる</span><span class="sxs-lookup"><span data-stu-id="f3a6a-163">Create and assign custom tags</span></span>

<span data-ttu-id="f3a6a-164">カスタム タグを作成して割り当てるには、アプリ **Teams** の左側にある [カスタム タグ] を選択し、一覧からチームを検索します。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-164">To create and assign custom tags, select **Teams** on the left side of the app, and then find your team in the list.</span></span> <span data-ttu-id="f3a6a-165">**[その他のオプション] を選択し**、[タグの管理]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-165">Select **˙˙˙ More options**, and then choose **Manage tags**.</span></span> <span data-ttu-id="f3a6a-166">ここでは、タグを作成し、チームのユーザーに割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-166">Here, you can create tags and assign them to people on your team.</span></span>

![<span data-ttu-id="f3a6a-167">クライアントでタグを適用する方法Teamsスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="f3a6a-167">Screenshot of how to apply tags in the Teams client</span></span> ](media/manage-tags-teams.png)

<span data-ttu-id="f3a6a-168">タグを削除するには、 **タグの横にある [その** 他のオプション] を選択し、[タグの削除] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-168">To delete a tag, select **˙˙˙ More options** next to the tag, and then select **Delete tag**.</span></span>

### <a name="set-up-tagging-by-shift"></a><span data-ttu-id="f3a6a-169">シフトによるタグ付けを設定する</span><span class="sxs-lookup"><span data-stu-id="f3a6a-169">Set up tagging by shift</span></span>

<span data-ttu-id="f3a6a-170">シフトによるタグ付けにより、ユーザーはリアルタイムでシフト上のユーザーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-170">Tagging by shift allows your users to reach the people on-shift in real-time.</span></span> <span data-ttu-id="f3a6a-171">Teams、スケジュールとシフト グループ名に一致するタグを持つユーザーを Shifts アプリから自動的に割り当て、動的なロールベースのメッセージングを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-171">Teams automatically assigns users with tags matching their schedule and shift group name from the Shifts app, enabling dynamic role-based messaging.</span></span> <span data-ttu-id="f3a6a-172">通知は、タグがチャットの開始またはチャネルの投稿に使用された時点でシフト中のユーザーにのみ送信されます。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-172">Notifications are sent only to those people who are on shift at the time a tag is used to start a chat or in a channel post.</span></span> 

1. <span data-ttu-id="f3a6a-173">このTeams、Shifts アプリ[に移動します](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop)。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-173">In Teams, go to the [Shifts app](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop).</span></span>
2. <span data-ttu-id="f3a6a-174">シフト [グループを作成](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) し、ロールなどの属性の後に名前を付えます。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-174">Create [shift groups](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) and name them after an attribute such as a role.</span></span> <span data-ttu-id="f3a6a-175">たとえば、EngineerOnCall です。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-175">For example, EngineerOnCall.</span></span> <span data-ttu-id="f3a6a-176">シフト グループ名はタグの名前です。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-176">The shift group name will be the name of the tag.</span></span>
3. <span data-ttu-id="f3a6a-177">[チームのメンバーにシフト](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea) を割り当て、スケジュールを入力します。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-177">[Fill out a schedule](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea) by assigning shifts to members of your teams.</span></span> <span data-ttu-id="f3a6a-178">完了したら、Shifts アプリの右上隅にある [チームと共有] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-178">When you're finished, in the upper-right corner of the Shifts app, select **Share with team**.</span></span>
4. <span data-ttu-id="f3a6a-179">スケジュールされたシフトがタグ付けサービスに設定されるのを 15 分待ちます。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-179">Wait 15 minutes for the scheduled shifts to populate the tagging service.</span></span>
5. <span data-ttu-id="f3a6a-180">タグは、タグを使用する場所Teams。</span><span class="sxs-lookup"><span data-stu-id="f3a6a-180">Use the tag anywhere you use tags in Teams.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f3a6a-181">関連トピック</span><span class="sxs-lookup"><span data-stu-id="f3a6a-181">Related topics</span></span>

[<span data-ttu-id="f3a6a-182">Teams でタグを使用する</span><span class="sxs-lookup"><span data-stu-id="f3a6a-182">Using tags in Teams</span></span>](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[<span data-ttu-id="f3a6a-183">Teams で組織の Shifts アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="f3a6a-183">Manage the Shifts app for your organization in Teams</span></span>](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[<span data-ttu-id="f3a6a-184">Shifts のヘルプ ドキュメント</span><span class="sxs-lookup"><span data-stu-id="f3a6a-184">Shifts Help documentation</span></span>](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
