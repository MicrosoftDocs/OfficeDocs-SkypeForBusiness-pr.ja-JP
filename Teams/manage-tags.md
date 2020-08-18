---
title: Microsoft Teams でタグを管理する
author: lanachin
ms.author: v-lanac
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
description: Microsoft Teams での組織でのタグの使用方法を管理する方法について説明します。
ms.openlocfilehash: b285cd4348894007d1e487a0788f82c9c8821d43
ms.sourcegitcommit: 27fb021e46d775652a99d862b19d94f3fc020594
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2020
ms.locfileid: "46778079"
---
# <a name="manage-tags-in-microsoft-teams"></a><span data-ttu-id="3502e-103">Microsoft Teams でタグを管理する</span><span class="sxs-lookup"><span data-stu-id="3502e-103">Manage tags in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="3502e-104">この記事で説明されている機能の1つは、 **shift キーでタグ付け**されていますが、まだリリースされていません。</span><span class="sxs-lookup"><span data-stu-id="3502e-104">One of the features discussed in this article, **tagging by shift**, hasn't yet been released.</span></span> <span data-ttu-id="3502e-105">これは発表され、近日公開予定です。</span><span class="sxs-lookup"><span data-stu-id="3502e-105">It's been announced, and it's coming soon.</span></span><span data-ttu-id="3502e-106">管理者は、メッセージ センター ([Microsoft 365 管理センター](https://portal.office.com/adminportal/home)) でこの機能のリリース日を確認できます。</span><span class="sxs-lookup"><span data-stu-id="3502e-106"> If you're an admin, you can find out when this feature will be released in the Message Center (in the [Microsoft 365 admin center](https://portal.office.com/adminportal/home)).</span></span> <span data-ttu-id="3502e-107">Teams 機能の最新情報を入手するには、「[Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3502e-107">To stay on top of upcoming Teams features, check out the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams).</span></span>

## <a name="overview"></a><span data-ttu-id="3502e-108">概要</span><span class="sxs-lookup"><span data-stu-id="3502e-108">Overview</span></span>

<span data-ttu-id="3502e-109">Microsoft Teams のタグを使用すると、チーム内のユーザーのサブセットと簡単に連絡を取ることができます。</span><span class="sxs-lookup"><span data-stu-id="3502e-109">Tags in Microsoft Teams let users quickly and easily connect with a subset of people on a team.</span></span> <span data-ttu-id="3502e-110">ロール、プロジェクト、スキル、場所などの属性に基づいてユーザーを分類するために、カスタムタグを作成して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="3502e-110">You can create and assign custom tags to categorize people based on attributes, such as role, project, skill, or location.</span></span> <span data-ttu-id="3502e-111">または、[ [シフト] アプリ](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts) のスケジュールとシフト情報に基づいて、タグをユーザーに自動的に割り当てることができます (近日公開)。</span><span class="sxs-lookup"><span data-stu-id="3502e-111">Or, tags can be automatically assigned to people based on their schedule and shift information in the [Shifts app](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts) (coming soon).</span></span> <span data-ttu-id="3502e-112">1つまたは複数のチームメンバーにタグを追加した後は、チャネル投稿でそのタグを @mentions で使用したり、そのタグが割り当てられているユーザーのみと会話を開始したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="3502e-112">After a tag is added to one or multiple team members, it can be used in @mentions by anyone on the team in a channel post or to start a conversation with only those people who are assigned that tag.</span></span>

<span data-ttu-id="3502e-113">前に説明したように、Teams には2種類のタグがあります。</span><span class="sxs-lookup"><span data-stu-id="3502e-113">As mentioned earlier, there are two kinds of tags in Teams.</span></span>

- <span data-ttu-id="3502e-114">**カスタムタグ**: チーム所有者とチームメンバー (機能が有効になっている場合) は、手動でタグを作成してユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="3502e-114">**Custom tags**: Team owners and team members (if the feature is enabled for them) can manually create and assign tags to people.</span></span> <span data-ttu-id="3502e-115">たとえば、"Designer" や "Radiologist" タグでは、チームメンバーの名前を入力せずに、それらのユーザーのセットにアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="3502e-115">For example, a "Designer" or "Radiologist" tag will reach those sets of people on a team without having to type their names.</span></span>
- <span data-ttu-id="3502e-116">**Shift キーによるタグ付け** (近日公開): この機能を使用すると、Teams の shift [アプリ](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) でのスケジュールとシフトグループ名に一致するタグが自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="3502e-116">**Tagging by shift** (coming soon): With this feature, people are automatically assigned tags that match their schedule and shift group name in the [Shifts app](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) in Teams.</span></span> <span data-ttu-id="3502e-117">たとえば、"EngineerOnCall" タグは、そのタグがチャットまたはチャネルの投稿で使用されるときに、シフトのスケジュールが設定されているすべてのエンジニアに到達します。</span><span class="sxs-lookup"><span data-stu-id="3502e-117">For example, the "EngineerOnCall" tag reaches all engineers who are scheduled in Shifts to work at the time the tag is used in a chat or channel post.</span></span> <span data-ttu-id="3502e-118">シフトによるタグ付けを使用すると、チームは、ユーザーがすばやく情報をやり取りする必要があるときに、シフトしたスタッフの名前がわからない場合があります。</span><span class="sxs-lookup"><span data-stu-id="3502e-118">With tagging by shift, Teams takes the guesswork out of knowing the name of on-shift staff when users need to quickly relay information.</span></span> <span data-ttu-id="3502e-119">シフトでのタグ付けは、JDA、Kronos、AMiON などの主要な労働力管理システムでもサポートされます。これは、チームのシフトとの統合によって実現されます。</span><span class="sxs-lookup"><span data-stu-id="3502e-119">Tagging by shift can also be backed by major workforce management systems like JDA, Kronos, and AMiON by integrating them with Shifts in Teams.</span></span> <span data-ttu-id="3502e-120">この機能の設定方法の詳細については、「 [shift でタグを設定](#set-up-tagging-by-shift-coming-soon)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3502e-120">To learn more about how to set up this feature, see [Set up tagging by shift](#set-up-tagging-by-shift-coming-soon).</span></span>

> [!NOTE]
> <span data-ttu-id="3502e-121">プライベートチャネルでは、タグはまだサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3502e-121">Tags are not yet supported in private channels.</span></span> <span data-ttu-id="3502e-122">US Government Community Cloud (GCC)、GCC High、または国防総省 (DoD) の組織では、タグはまだ利用できません。</span><span class="sxs-lookup"><span data-stu-id="3502e-122">Tags are not yet available in US Government Community Cloud (GCC), GCC High, or Department of Defense (DoD) organizations.</span></span>

## <a name="how-tags-work"></a><span data-ttu-id="3502e-123">タグのしくみ</span><span class="sxs-lookup"><span data-stu-id="3502e-123">How tags work</span></span>

<span data-ttu-id="3502e-124">タグは、特定のチームのメンバーに手動で追加したり、自動的に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="3502e-124">A tag can be manually added or automatically assigned to a person on a specific team.</span></span> <span data-ttu-id="3502e-125">これは、チャットの [ **宛先** ] 行の @mentions、またはチームの任意の標準チャネルの投稿に使用できます。</span><span class="sxs-lookup"><span data-stu-id="3502e-125">It can then be used in @mentions on the **To** line in a chat or in a post on any standard channel of the team.</span></span> <span data-ttu-id="3502e-126">次に、Teams でタグを使用する方法の例をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="3502e-126">Here's some examples of how tags can be used in Teams:</span></span>

- <span data-ttu-id="3502e-127">ストアマネージャーは、すべてのレジに通知するためにお知らせをチャネルに投稿します。</span><span class="sxs-lookup"><span data-stu-id="3502e-127">A store manager posts an announcement to a channel to notify all cashiers.</span></span>
- <span data-ttu-id="3502e-128">病院管理者が、チャネル内のすべての radiologists にメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="3502e-128">A hospital administrator sends a message to all radiologists in a channel.</span></span>
- <span data-ttu-id="3502e-129">マーケティングマネージャーが、すべてのデザイナーとグループチャットを開始します。</span><span class="sxs-lookup"><span data-stu-id="3502e-129">A marketing manager starts a group chat with all designers.</span></span>
- <span data-ttu-id="3502e-130">看護師がすべての cardiologists にメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="3502e-130">A nurse sends a message to all on-call cardiologists.</span></span> <span data-ttu-id="3502e-131">(近日公開)</span><span class="sxs-lookup"><span data-stu-id="3502e-131">(coming soon)</span></span>
- <span data-ttu-id="3502e-132">システムエンジニアは、チャネルにお知らせを投稿して、すべてのシフト型フィールドエンジニアに通知します。</span><span class="sxs-lookup"><span data-stu-id="3502e-132">A system engineer posts an announcement to a channel to notify all on-shift field engineers.</span></span> <span data-ttu-id="3502e-133">(近日公開)</span><span class="sxs-lookup"><span data-stu-id="3502e-133">(coming soon)</span></span>

<span data-ttu-id="3502e-134">チャネルの会話でタグを @mentioned すると、他の @mention と同じように、タグに関連付けられているチームメンバーに通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="3502e-134">When a tag is @mentioned in a channel conversation, team members associated with the tag will get notified, just like any other @mention.</span></span>

## <a name="manage-custom-tags-for-your-organization"></a><span data-ttu-id="3502e-135">組織のカスタムタグを管理する</span><span class="sxs-lookup"><span data-stu-id="3502e-135">Manage custom tags for your organization</span></span>

<span data-ttu-id="3502e-136">管理者は、Microsoft Teams 管理センターで、組織全体でタグを使用する方法を制御できます。</span><span class="sxs-lookup"><span data-stu-id="3502e-136">As an admin, you can control how tags are used across your organization in the Microsoft Teams admin center.</span></span>

![Microsoft Teams 管理センターのタグ設定のスクリーンショット](media/manage-tags-admin-settings.png)

<span data-ttu-id="3502e-138">チームは、最大100のタグを持つことができ、最大で100のチームメンバーを1つのタグに割り当てることができ、最大25個のタグを1人のユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="3502e-138">A team can have up to 100 tags, up to 100 team members can be assigned to a tag, and up to 25 tags can be assigned to a single user.</span></span> 

### <a name="set-who-can-add-custom-tags"></a><span data-ttu-id="3502e-139">カスタムタグを追加できるユーザーを設定する</span><span class="sxs-lookup"><span data-stu-id="3502e-139">Set who can add custom tags</span></span>

<span data-ttu-id="3502e-140">既定では、チーム所有者はカスタムタグを追加できます。</span><span class="sxs-lookup"><span data-stu-id="3502e-140">By default, team owners can add custom tags.</span></span> <span data-ttu-id="3502e-141">この設定を変更して、チーム所有者とチームメンバーがタグを追加できるようにするか、組織のタグをオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="3502e-141">You can change this setting to allow team owners and team members to add tags or you can turn off tags for your organization.</span></span>

1. <span data-ttu-id="3502e-142">Microsoft Teams 管理センターの左のナビゲーションで、[**組織全体の設定**] チームの設定をクリックし  >  **Teams settings**ます。</span><span class="sxs-lookup"><span data-stu-id="3502e-142">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="3502e-143">[ **タグ付け**] で、[ **タグ付けの対象] の**横にある次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="3502e-143">Under **Tagging**, next to **Tagging is enabled for**, select one of the following options:</span></span>

    - <span data-ttu-id="3502e-144">**チームの所有者とメンバー**: チームの所有者とメンバーがタグを追加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="3502e-144">**Team owners and members**: Allow team owners and members to add tags.</span></span>
    - <span data-ttu-id="3502e-145">**チームの所有者**: チーム所有者がタグを追加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="3502e-145">**Team owners**: Allow team owners to add tags.</span></span>
    - <span data-ttu-id="3502e-146">**Disabled**: ノートシールをオフにします。</span><span class="sxs-lookup"><span data-stu-id="3502e-146">**Disabled**: Turn off tags.</span></span>

### <a name="configure-custom-tags-settings"></a><span data-ttu-id="3502e-147">カスタムタグの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="3502e-147">Configure custom tags settings</span></span>

<span data-ttu-id="3502e-148">次のタグ設定を構成して、組織全体でのカスタムタグの使用方法を制御できます。</span><span class="sxs-lookup"><span data-stu-id="3502e-148">You can configure the following tags settings to control how custom tags are used across your organization.</span></span>

1. <span data-ttu-id="3502e-149">Microsoft Teams 管理センターの左のナビゲーションで、[**組織全体の設定**] チームの設定をクリックし  >  **Teams settings**ます。</span><span class="sxs-lookup"><span data-stu-id="3502e-149">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="3502e-150">[ **タグ付け**] で、組織のニーズに応じて次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="3502e-150">Under **Tagging**, set the following, depending on the needs of your organization.</span></span>

    - <span data-ttu-id="3502e-151">**チーム所有者は、タグを適用できるユーザーを上書きでき**ます。この機能がオンになっていると、チームの所有者は、チーム設定でメンバーにタグを追加することを許可または禁止することができます。</span><span class="sxs-lookup"><span data-stu-id="3502e-151">**Team owner can override who can apply tags**: When this is turned on, team owners can allow or disallow members to add tags in team settings.</span></span>
    - <span data-ttu-id="3502e-152">**メンバーはタグ**を追加できます。チームメンバーがタグを追加できるようにするには、このオプションをオンにして、設定した既定のタグ以外のタグをチームメンバーが追加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="3502e-152">**Members can add additional tags**: If you allow team members to add tags, turn this on to let team members add tags other than the suggested default tags that you set.</span></span> <span data-ttu-id="3502e-153">この機能が無効になっている場合、チームメンバーは既定のタグのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3502e-153">If this is turned off, team members can only use the default tags.</span></span>
    - <span data-ttu-id="3502e-154">**提案**された既定のタグ: これを使用して、一連の既定のタグを追加します。</span><span class="sxs-lookup"><span data-stu-id="3502e-154">**Suggested default tags**: Use this to add a set of default tags.</span></span> <span data-ttu-id="3502e-155">最大25個のタグを追加できます。各タグには最大25文字まで含めることができます。</span><span class="sxs-lookup"><span data-stu-id="3502e-155">You can add up to 25 tags, and each tag can contain a maximum of 25 characters.</span></span> <span data-ttu-id="3502e-156">チーム所有者とメンバー (機能が有効になっている場合) は、これらの候補を使用したり、それらを追加したり、新しいタグセットを作成したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="3502e-156">Team owners and members (if the feature is enabled for them) can use these suggestions, add to them, or create a new set of tags.</span></span>

## <a name="manage-custom-tags-settings-for-a-team"></a><span data-ttu-id="3502e-157">チームのカスタムタグ設定を管理する</span><span class="sxs-lookup"><span data-stu-id="3502e-157">Manage custom tags settings for a team</span></span>

<span data-ttu-id="3502e-158">チーム所有者が Microsoft Teams 管理センターの [ **タグを適用できるユーザーを上書きできる** ] 設定をオンにしている場合、チーム所有者は、メンバーがチームレベルでタグを追加できるかどうかを設定できます。</span><span class="sxs-lookup"><span data-stu-id="3502e-158">If you turned on the **Team owner can override who can apply tags** setting in the Microsoft Teams admin center, team owners can set whether members can add tags at the team level.</span></span> <span data-ttu-id="3502e-159">これを行うには、チームの [ **設定** ] タブで [ **タグ**] に移動し、[タグを追加できるユーザー] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3502e-159">To do this, on the **Settings** tab for a team, go to **Tags**, and then choose who can add tags.</span></span>

![チームレベルの [タグ] 設定のスクリーンショット](media/manage-tags-team-settings.png)

## <a name="use-tags"></a><span data-ttu-id="3502e-161">タグを使用する</span><span class="sxs-lookup"><span data-stu-id="3502e-161">Use tags</span></span>

<span data-ttu-id="3502e-162">ここでは、カスタムタグを追加する方法と、shift キーでタグを設定する方法について説明します (Teams でシフトアプリを使用している場合)。</span><span class="sxs-lookup"><span data-stu-id="3502e-162">Here's how to add custom tags and how to set up tagging by shift (if you're using the Shifts app in Teams).</span></span> <span data-ttu-id="3502e-163">詳細については、「 [Teams でタグを使用する」](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3502e-163">To learn more, check out [Using tags in Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).</span></span>

### <a name="create-and-assign-custom-tags"></a><span data-ttu-id="3502e-164">カスタムタグを作成して割り当てる</span><span class="sxs-lookup"><span data-stu-id="3502e-164">Create and assign custom tags</span></span>

<span data-ttu-id="3502e-165">カスタムタグを作成して割り当てるには、アプリの左側にある [ **チーム** ] を選択し、リストからチームを見つけます。</span><span class="sxs-lookup"><span data-stu-id="3502e-165">To create and assign custom tags, select **Teams** on the left side of the app, and then find your team in the list.</span></span> <span data-ttu-id="3502e-166">[ **その他のオプション**] を選択し、[ **タグの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3502e-166">Select **More options**, and then choose **Manage tags**.</span></span> <span data-ttu-id="3502e-167">ここでは、タグを作成して、チームのメンバーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="3502e-167">Here, you can create tags and assign them to people on your team.</span></span>

![<span data-ttu-id="3502e-168">Teams クライアントでタグを適用する方法を示すスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="3502e-168">Screenshot of how to apply tags in the Teams client</span></span> ](media/manage-tags-teams.png)

<span data-ttu-id="3502e-169">タグを削除するには、ノートシールに関連付けられているすべてのチームメンバーを削除します。</span><span class="sxs-lookup"><span data-stu-id="3502e-169">To delete a tag, remove all team members associated with the tag.</span></span>

### <a name="set-up-tagging-by-shift-coming-soon"></a><span data-ttu-id="3502e-170">シフトでタグを設定する (近日公開)</span><span class="sxs-lookup"><span data-stu-id="3502e-170">Set up tagging by shift (coming soon)</span></span>

1. <span data-ttu-id="3502e-171">Teams で、[シフト] [アプリ](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop)に移動します。</span><span class="sxs-lookup"><span data-stu-id="3502e-171">In Teams, go to the [Shifts app](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop).</span></span>
2. <span data-ttu-id="3502e-172">[シフトグループ](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup)を作成し、役割などの属性の後に名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="3502e-172">Create [shift groups](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) and name them after an attribute such as a role.</span></span> <span data-ttu-id="3502e-173">たとえば、EngineerOnCall のようになります。</span><span class="sxs-lookup"><span data-stu-id="3502e-173">For example, EngineerOnCall.</span></span> <span data-ttu-id="3502e-174">シフトグループ名は、タグの名前になります。</span><span class="sxs-lookup"><span data-stu-id="3502e-174">The shift group name will be the name of the tag.</span></span>
3. <span data-ttu-id="3502e-175">チームのメンバーにシフトを割り当てることで[、スケジュールを入力](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea)します。</span><span class="sxs-lookup"><span data-stu-id="3502e-175">[Fill out a schedule](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea) by assigning shifts to members of you teams.</span></span> <span data-ttu-id="3502e-176">完了したら、[シフト] アプリの右上隅で [ **チームと共有**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3502e-176">When you're finished, in the upper-right corner of the Shifts app, select **Share with team**.</span></span>
4. <span data-ttu-id="3502e-177">スケジュールされたシフトがタグ付けサービスに取り込まれるまで15分待ちます。</span><span class="sxs-lookup"><span data-stu-id="3502e-177">Wait 15 minutes for the scheduled shifts to populate the tagging service.</span></span>
5. <span data-ttu-id="3502e-178">Teams でタグを使用する任意の場所でタグを使用します。</span><span class="sxs-lookup"><span data-stu-id="3502e-178">Use the tag anywhere you use tags in Teams.</span></span>

<span data-ttu-id="3502e-179">シフトでタグを付けて、ユーザーがリアルタイムで連絡先にアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="3502e-179">Tagging by shift allows your users to reach the people on-shift in real time.</span></span> <span data-ttu-id="3502e-180">通知は、ノートを使っているユーザーにのみ送信され、チャットまたはチャネルの投稿の開始に使用されます。</span><span class="sxs-lookup"><span data-stu-id="3502e-180">Notifications are sent only to those people who are on shift at the time a tag is used to start a chat or in a channel post.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3502e-181">関連項目</span><span class="sxs-lookup"><span data-stu-id="3502e-181">Related topics</span></span>

[<span data-ttu-id="3502e-182">Teams でタグを使用する</span><span class="sxs-lookup"><span data-stu-id="3502e-182">Using tags in Teams</span></span>](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[<span data-ttu-id="3502e-183">Teams で組織の Shifts アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="3502e-183">Manage the Shifts app for your organization in Teams</span></span>](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[<span data-ttu-id="3502e-184">ヘルプドキュメントのシフト</span><span class="sxs-lookup"><span data-stu-id="3502e-184">Shifts Help documentation</span></span>](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
