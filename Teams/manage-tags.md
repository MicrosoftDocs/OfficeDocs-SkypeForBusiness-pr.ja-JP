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
description: Microsoft Teams で組織でタグがどのように使用されるのかについて説明します。
ms.openlocfilehash: 9d9ba4584572ad1e1707c250ee92c49e9aaec7fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831237"
---
# <a name="manage-tags-in-microsoft-teams"></a><span data-ttu-id="bcf88-103">Microsoft Teams でタグを管理する</span><span class="sxs-lookup"><span data-stu-id="bcf88-103">Manage tags in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="bcf88-104">この記事で説明されている機能の 1つ、シフトによるタグ付けはまだリリースされていません。</span><span class="sxs-lookup"><span data-stu-id="bcf88-104">One of the features discussed in this article, **tagging by shift**, hasn't yet been released.</span></span> <span data-ttu-id="bcf88-105">これは発表され、近日公開される予定です。</span><span class="sxs-lookup"><span data-stu-id="bcf88-105">It's been announced, and it's coming soon.</span></span> <span data-ttu-id="bcf88-106">管理者は、メッセージ センター ([Microsoft 365 管理センター](https://portal.office.com/adminportal/home)) でこの機能のリリース日を確認できます。</span><span class="sxs-lookup"><span data-stu-id="bcf88-106">If you're an admin, you can find out when this feature will be released in the Message Center (in the [Microsoft 365 admin center](https://portal.office.com/adminportal/home)).</span></span> <span data-ttu-id="bcf88-107">Teams 機能の最新情報を入手するには、「[Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcf88-107">To stay on top of upcoming Teams features, check out the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams).</span></span>

## <a name="overview"></a><span data-ttu-id="bcf88-108">概要</span><span class="sxs-lookup"><span data-stu-id="bcf88-108">Overview</span></span>

<span data-ttu-id="bcf88-109">Microsoft Teams のタグを使用すると、ユーザーはチームの一部のユーザーとすばやく簡単に接続できます。</span><span class="sxs-lookup"><span data-stu-id="bcf88-109">Tags in Microsoft Teams let users quickly and easily connect with a subset of people on a team.</span></span> <span data-ttu-id="bcf88-110">カスタム タグを作成して割り当て、役割、プロジェクト、スキル、場所などの属性に基づいてユーザーを分類できます。</span><span class="sxs-lookup"><span data-stu-id="bcf88-110">You can create and assign custom tags to categorize people based on attributes, such as role, project, skill, or location.</span></span> <span data-ttu-id="bcf88-111">または [、Shifts](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts) アプリのスケジュールとシフト情報に基づいて、タグをユーザーに自動的に割り当てることができます (近日公開予定)。</span><span class="sxs-lookup"><span data-stu-id="bcf88-111">Or, tags can be automatically assigned to people based on their schedule and shift information in the [Shifts app](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts) (coming soon).</span></span> <span data-ttu-id="bcf88-112">1 人または複数のチーム メンバーにタグを追加した後は、チャネルの投稿でチームの誰でも @mentions でタグを使用したり、そのタグが割り当てられているユーザーのみと会話を開始したりするために使用できます。</span><span class="sxs-lookup"><span data-stu-id="bcf88-112">After a tag is added to one or multiple team members, it can be used in @mentions by anyone on the team in a channel post or to start a conversation with only those people who are assigned that tag.</span></span>

<span data-ttu-id="bcf88-113">前述のように、Teams には 2 種類のタグがあります。</span><span class="sxs-lookup"><span data-stu-id="bcf88-113">As mentioned earlier, there are two kinds of tags in Teams.</span></span>

- <span data-ttu-id="bcf88-114">**カスタム タグ**: チーム所有者とチーム メンバー (機能が有効な場合) は、手動でタグを作成してユーザーに割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="bcf88-114">**Custom tags**: Team owners and team members (if the feature is enabled for them) can manually create and assign tags to people.</span></span> <span data-ttu-id="bcf88-115">たとえば、"Designer" タグまたは "Radiradiradi" タグは、名前を入力することなく、チーム内のユーザー のセットに到達します。</span><span class="sxs-lookup"><span data-stu-id="bcf88-115">For example, a "Designer" or "Radiologist" tag will reach those sets of people on a team without having to type their names.</span></span>
- <span data-ttu-id="bcf88-116">**シフトによるタグ付** け (近日公開): この機能を使用すると、Teams の [Shifts](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) アプリでスケジュールとシフト グループ名に一致するタグが自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="bcf88-116">**Tagging by shift** (coming soon): With this feature, people are automatically assigned tags that match their schedule and shift group name in the [Shifts app](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) in Teams.</span></span> <span data-ttu-id="bcf88-117">たとえば、"EngineerOnCall" タグは、チャットまたはチャネル投稿でタグが使用された時点で作業するためにシフトでスケジュールされているすべてのエンジニアに到達します。</span><span class="sxs-lookup"><span data-stu-id="bcf88-117">For example, the "EngineerOnCall" tag reaches all engineers who are scheduled in Shifts to work at the time the tag is used in a chat or channel post.</span></span> <span data-ttu-id="bcf88-118">シフトによるタグ付けにより、Teams は、ユーザーが情報をすばやく中継する必要があるときに、シフト上のスタッフの名前を知ることから推測を取り出します。</span><span class="sxs-lookup"><span data-stu-id="bcf88-118">With tagging by shift, Teams takes the guesswork out of knowing the name of on-shift staff when users need to quickly relay information.</span></span> <span data-ttu-id="bcf88-119">シフト別のタグ付けは、Teams の Shifts と統合することで、JDA、Kronos、AMiON のような主要な人員管理システムによってもサポートされます。</span><span class="sxs-lookup"><span data-stu-id="bcf88-119">Tagging by shift can also be backed by major workforce management systems like JDA, Kronos, and AMiON by integrating them with Shifts in Teams.</span></span> <span data-ttu-id="bcf88-120">この機能の設定方法の詳細については、「シフトでタグ付けを設定する [」を参照してください](#set-up-tagging-by-shift-coming-soon)。</span><span class="sxs-lookup"><span data-stu-id="bcf88-120">To learn more about how to set up this feature, see [Set up tagging by shift](#set-up-tagging-by-shift-coming-soon).</span></span>

> [!NOTE]
> <span data-ttu-id="bcf88-121">プライベート チャネルでは、タグはまだサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="bcf88-121">Tags are not yet supported in private channels.</span></span> <span data-ttu-id="bcf88-122">タグは、米国政府機関コミュニティ クラウド (GCC)、GCC High、または国防総省 (DoD) 組織ではまだ利用できません。</span><span class="sxs-lookup"><span data-stu-id="bcf88-122">Tags are not yet available in US Government Community Cloud (GCC), GCC High, or Department of Defense (DoD) organizations.</span></span> 

## <a name="how-tags-work"></a><span data-ttu-id="bcf88-123">タグの動作</span><span class="sxs-lookup"><span data-stu-id="bcf88-123">How tags work</span></span>

<span data-ttu-id="bcf88-124">タグは、手動で追加したり、特定のチームのユーザーに自動的に割り当てたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="bcf88-124">A tag can be manually added or automatically assigned to a person on a specific team.</span></span> <span data-ttu-id="bcf88-125">チャットの [to] 行@mentions、またはチームの標準チャネルの投稿で、この機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="bcf88-125">It can then be used in @mentions on the **To** line in a chat or in a post on any standard channel of the team.</span></span> <span data-ttu-id="bcf88-126">Teams でタグを使用する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bcf88-126">Here's some examples of how tags can be used in Teams:</span></span>

- <span data-ttu-id="bcf88-127">店舗管理者は、すべての店舗に通知するアナウンスをチャネルに投稿します。</span><span class="sxs-lookup"><span data-stu-id="bcf88-127">A store manager posts an announcement to a channel to notify all cashiers.</span></span>
- <span data-ttu-id="bcf88-128">病院の管理者がチャネル内のすべてのラジオロジストにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="bcf88-128">A hospital administrator sends a message to all radiologists in a channel.</span></span>
- <span data-ttu-id="bcf88-129">マーケティング マネージャーは、すべてのデザイナーとグループ チャットを開始します。</span><span class="sxs-lookup"><span data-stu-id="bcf88-129">A marketing manager starts a group chat with all designers.</span></span>
- <span data-ttu-id="bcf88-130">看護師が、すべてのオンコール カーディロジストにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="bcf88-130">A nurse sends a message to all on-call cardiologists.</span></span> <span data-ttu-id="bcf88-131">(近日公開)</span><span class="sxs-lookup"><span data-stu-id="bcf88-131">(coming soon)</span></span>
- <span data-ttu-id="bcf88-132">システム エンジニアは、シフト上のすべてのフィールド エンジニアに通知するアナウンスをチャネルに投稿します。</span><span class="sxs-lookup"><span data-stu-id="bcf88-132">A system engineer posts an announcement to a channel to notify all on-shift field engineers.</span></span> <span data-ttu-id="bcf88-133">(近日公開)</span><span class="sxs-lookup"><span data-stu-id="bcf88-133">(coming soon)</span></span>

<span data-ttu-id="bcf88-134">チャネルの会話@mentionedタグが追加された場合、他の会話と同様に、タグに関連付けられているチーム メンバーに通知が@mention。</span><span class="sxs-lookup"><span data-stu-id="bcf88-134">When a tag is @mentioned in a channel conversation, team members associated with the tag will get notified, just like any other @mention.</span></span>

## <a name="manage-custom-tags-for-your-organization"></a><span data-ttu-id="bcf88-135">組織のカスタム タグを管理する</span><span class="sxs-lookup"><span data-stu-id="bcf88-135">Manage custom tags for your organization</span></span>

<span data-ttu-id="bcf88-136">管理者は、Microsoft Teams 管理センターで組織全体でタグを使用する方法を制御できます。</span><span class="sxs-lookup"><span data-stu-id="bcf88-136">As an admin, you can control how tags are used across your organization in the Microsoft Teams admin center.</span></span> <span data-ttu-id="bcf88-137">現時点では、PowerShell を使用してタグを管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="bcf88-137">Currently, you can't use PowerShell to manage tags.</span></span>

![Microsoft Teams 管理センターのタグ付け設定のスクリーンショット](media/manage-tags-admin-settings.png)

<span data-ttu-id="bcf88-139">チームには最大 100 のタグを割り当て、最大 100 人のチーム メンバーをタグに割り当て、1 人のユーザーに最大 25 のタグを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="bcf88-139">A team can have up to 100 tags, up to 100 team members can be assigned to a tag, and up to 25 tags can be assigned to a single user.</span></span> 

### <a name="set-who-can-add-custom-tags"></a><span data-ttu-id="bcf88-140">カスタム タグを追加できるユーザーを設定する</span><span class="sxs-lookup"><span data-stu-id="bcf88-140">Set who can add custom tags</span></span>

<span data-ttu-id="bcf88-141">既定では、チーム所有者はカスタム タグを追加できます。</span><span class="sxs-lookup"><span data-stu-id="bcf88-141">By default, team owners can add custom tags.</span></span> <span data-ttu-id="bcf88-142">この設定を変更して、チーム所有者とチーム メンバーがタグの作成、編集、削除、管理を行えるか、組織のタグをオフにできます。</span><span class="sxs-lookup"><span data-stu-id="bcf88-142">You can change this setting to allow team owners and team members to create, edit, delete, and manage tags or you can turn off tags for your organization.</span></span>

1. <span data-ttu-id="bcf88-143">Microsoft Teams 管理センターの左側のナビゲーションで、[組織全体の設定チームの **設定]**  >  **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="bcf88-143">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="bcf88-144">[ **タグ付け] の**[ **タグの管理** 方法] の横で、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="bcf88-144">Under **Tagging**, next to **Tags are managed by**, select one of the following options:</span></span>

    - <span data-ttu-id="bcf88-145">**チームの所有者とメンバー**: チームの所有者とメンバーがタグを管理できます。</span><span class="sxs-lookup"><span data-stu-id="bcf88-145">**Team owners and members**: Allow team owners and members to manage tags.</span></span>
    - <span data-ttu-id="bcf88-146">**チーム所有者**: チーム所有者にタグの管理を許可します。</span><span class="sxs-lookup"><span data-stu-id="bcf88-146">**Team owners**: Allow team owners to manage tags.</span></span>
    - <span data-ttu-id="bcf88-147">**無効**: タグをオフにします。</span><span class="sxs-lookup"><span data-stu-id="bcf88-147">**Disabled**: Turn off tags.</span></span>

### <a name="configure-custom-tags-settings"></a><span data-ttu-id="bcf88-148">カスタム タグの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="bcf88-148">Configure custom tags settings</span></span>

<span data-ttu-id="bcf88-149">組織全体でカスタム タグを使用する方法を制御するために、次のタグ設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="bcf88-149">You can configure the following tags settings to control how custom tags are used across your organization.</span></span>

1. <span data-ttu-id="bcf88-150">Microsoft Teams 管理センターの左側のナビゲーションで、[組織全体の設定チームの **設定]**  >  **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="bcf88-150">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="bcf88-151">[ **タグ付け]** で、組織のニーズに応じて、次を設定します。</span><span class="sxs-lookup"><span data-stu-id="bcf88-151">Under **Tagging**, set the following, depending on the needs of your organization.</span></span>

    - <span data-ttu-id="bcf88-152">チーム所有者がタグを管理できるユーザーを上書き **する:** この設定をオンにすると、チーム所有者はチーム メンバーがチーム内でタグを作成および管理できるかどうかを設定できます。タグの値は、各チームの既定値に設定することで管理されます。</span><span class="sxs-lookup"><span data-stu-id="bcf88-152">**Let team owners override who can manage tags**: When you turn on this setting, team owners can set whether team members can create and manage tags within a team and the value of the **Tags are managed by** setting is the default value for each team.</span></span> <span data-ttu-id="bcf88-153">この設定をオフにすると、タグ **は** 設定によって管理され、チームごとに変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="bcf88-153">If you turn off this setting, the **Tags are managed by** setting can't be changed per team.</span></span>
    - <span data-ttu-id="bcf88-154">**推奨される既定のタグ**: 既定のタグのセットを追加する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="bcf88-154">**Suggested default tags**: Use this to add a set of default tags.</span></span> <span data-ttu-id="bcf88-155">最大 25 のタグを追加できます。各タグには最大 25 文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="bcf88-155">You can add up to 25 tags, and each tag can contain a maximum of 25 characters.</span></span> <span data-ttu-id="bcf88-156">チーム所有者とメンバー (機能が有効になっている場合) は、これらの候補を使用したり、それらの候補に追加したり、新しいタグ セットを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="bcf88-156">Team owners and members (if the feature is enabled for them) can use these suggestions, add to them, or create a new set of tags.</span></span>
    - <span data-ttu-id="bcf88-157">**カスタム タグを作成する**: ユーザーが設定した推奨される既定のタグ以外のタグを追加するには、この設定をオンにします。</span><span class="sxs-lookup"><span data-stu-id="bcf88-157">**Let custom tags be created**: Turn on this setting to let people add tags other than the suggested default tags that you set.</span></span> <span data-ttu-id="bcf88-158">この設定をオフにすると、ユーザーは推奨される既定のタグのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="bcf88-158">If this is turned off, people can only use the suggested default tags.</span></span> <span data-ttu-id="bcf88-159">これをオフにする場合は、1 つ以上の既定のタグを追加してください。</span><span class="sxs-lookup"><span data-stu-id="bcf88-159">If you turn this off, make sure that you add one or more default tags.</span></span>

## <a name="manage-custom-tags-settings-for-a-team"></a><span data-ttu-id="bcf88-160">チームのカスタム タグ設定を管理する</span><span class="sxs-lookup"><span data-stu-id="bcf88-160">Manage custom tags settings for a team</span></span>

<span data-ttu-id="bcf88-161">Microsoft Teams 管理センターで [チーム所有者がタグを管理できるユーザーを上書きする] 設定をオンにした場合、チーム所有者はメンバーがチーム レベルでタグを追加できるかどうかを設定できます。</span><span class="sxs-lookup"><span data-stu-id="bcf88-161">If you turned on the **Let team owners override who can manage tags** setting in the Microsoft Teams admin center, team owners can set whether members can add tags at the team level.</span></span> <span data-ttu-id="bcf88-162">これを行うには、チームの[設定] タブで[タグ] に移動し、タグを追加できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="bcf88-162">To do this, on the **Settings** tab for a team, go to **Tags**, and then choose who can add tags.</span></span>

![チーム レベルでのタグ設定のスクリーンショット](media/manage-tags-team-settings.png)

## <a name="use-tags"></a><span data-ttu-id="bcf88-164">タグを使用する</span><span class="sxs-lookup"><span data-stu-id="bcf88-164">Use tags</span></span>

<span data-ttu-id="bcf88-165">カスタム タグを追加する方法と、シフトでタグを設定する方法を示します (Teams で Shifts アプリを使用している場合)。</span><span class="sxs-lookup"><span data-stu-id="bcf88-165">Here's how to add custom tags and how to set up tagging by shift (if you're using the Shifts app in Teams).</span></span> <span data-ttu-id="bcf88-166">詳細については、「Teams でタグを [使用する」を参照してください](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)。</span><span class="sxs-lookup"><span data-stu-id="bcf88-166">To learn more, check out [Using tags in Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).</span></span>

### <a name="create-and-assign-custom-tags"></a><span data-ttu-id="bcf88-167">カスタム タグを作成して割り当てる</span><span class="sxs-lookup"><span data-stu-id="bcf88-167">Create and assign custom tags</span></span>

<span data-ttu-id="bcf88-168">カスタム タグを作成して割り当てるには、アプリの左側にある **[Teams]** を選択し、一覧から自分のチームを見つける必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcf88-168">To create and assign custom tags, select **Teams** on the left side of the app, and then find your team in the list.</span></span> <span data-ttu-id="bcf88-169">**[ 1] を選択し、[** その他のオプション] を選択し、[タグ **の管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="bcf88-169">Select **˙˙˙ More options**, and then choose **Manage tags**.</span></span> <span data-ttu-id="bcf88-170">ここでは、タグを作成し、チームのユーザーに割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="bcf88-170">Here, you can create tags and assign them to people on your team.</span></span>

![<span data-ttu-id="bcf88-171">Teams クライアントでタグを適用する方法のスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="bcf88-171">Screenshot of how to apply tags in the Teams client</span></span> ](media/manage-tags-teams.png)

<span data-ttu-id="bcf88-172">タグを削除するには、タグの横にある [その他のオプション] **を選択** し、[タグの削除] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="bcf88-172">To delete a tag, select **˙˙˙ More options** next to the tag, and then select **Delete tag**.</span></span>

### <a name="set-up-tagging-by-shift-coming-soon"></a><span data-ttu-id="bcf88-173">シフトによるタグ付けを設定する (近日公開予定)</span><span class="sxs-lookup"><span data-stu-id="bcf88-173">Set up tagging by shift (coming soon)</span></span>

1. <span data-ttu-id="bcf88-174">Teams で [、Shifts アプリに移動します](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop)。</span><span class="sxs-lookup"><span data-stu-id="bcf88-174">In Teams, go to the [Shifts app](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop).</span></span>
2. <span data-ttu-id="bcf88-175">シフト [グループを作成し](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) 、役割などの属性の後に名前を付けします。</span><span class="sxs-lookup"><span data-stu-id="bcf88-175">Create [shift groups](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) and name them after an attribute such as a role.</span></span> <span data-ttu-id="bcf88-176">たとえば、EngineerOnCall などです。</span><span class="sxs-lookup"><span data-stu-id="bcf88-176">For example, EngineerOnCall.</span></span> <span data-ttu-id="bcf88-177">シフト グループ名はタグの名前です。</span><span class="sxs-lookup"><span data-stu-id="bcf88-177">The shift group name will be the name of the tag.</span></span>
3. <span data-ttu-id="bcf88-178">[チームのメンバーにシフト](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea) を割り当て、スケジュールを入力します。</span><span class="sxs-lookup"><span data-stu-id="bcf88-178">[Fill out a schedule](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea) by assigning shifts to members of you teams.</span></span> <span data-ttu-id="bcf88-179">完了したら、Shifts アプリの右上隅にある [チームと共有] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="bcf88-179">When you're finished, in the upper-right corner of the Shifts app, select **Share with team**.</span></span>
4. <span data-ttu-id="bcf88-180">スケジュールされたシフトがタグ付けサービスに追加されるのを 15 分待ちます。</span><span class="sxs-lookup"><span data-stu-id="bcf88-180">Wait 15 minutes for the scheduled shifts to populate the tagging service.</span></span>
5. <span data-ttu-id="bcf88-181">Teams でタグを使用する任意の場所でタグを使用します。</span><span class="sxs-lookup"><span data-stu-id="bcf88-181">Use the tag anywhere you use tags in Teams.</span></span>

<span data-ttu-id="bcf88-182">シフトによるタグ付けにより、ユーザーはリアルタイムでシフト上のユーザーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="bcf88-182">Tagging by shift allows your users to reach the people on-shift in real time.</span></span> <span data-ttu-id="bcf88-183">通知は、タグを使用してチャットを開始した時点またはチャネルの投稿にシフトしているユーザーにのみ送信されます。</span><span class="sxs-lookup"><span data-stu-id="bcf88-183">Notifications are sent only to those people who are on shift at the time a tag is used to start a chat or in a channel post.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bcf88-184">関連項目</span><span class="sxs-lookup"><span data-stu-id="bcf88-184">Related topics</span></span>

[<span data-ttu-id="bcf88-185">Teams でタグを使用する</span><span class="sxs-lookup"><span data-stu-id="bcf88-185">Using tags in Teams</span></span>](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[<span data-ttu-id="bcf88-186">Teams で組織の Shifts アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="bcf88-186">Manage the Shifts app for your organization in Teams</span></span>](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[<span data-ttu-id="bcf88-187">Shifts のヘルプ ドキュメント</span><span class="sxs-lookup"><span data-stu-id="bcf88-187">Shifts Help documentation</span></span>](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
