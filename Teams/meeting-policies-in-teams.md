---
title: 会議ポリシーを管理する
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.overview
- ms.teamsadmincenter.meetingpolicies.audioandvideo
- ms.teamsadmincenter.meetingpolicies.contentsharing
- ms.teamsadmincenter.meetingpolicies.general
- ms.teamsadmincenter.meetingpolicies.participantandguests
description: Teams で会議のポリシー設定を管理する方法について説明します。
ms.openlocfilehash: 142152aaa0c47adea7f680b33fa4c9c59441e6eb
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836477"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="3ca8a-103">Teams での会議ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-103">Manage meeting policies in Teams</span></span>

::: zone target="docs"
<span data-ttu-id="3ca8a-104">会議ポリシーは、組織内のユーザーによってスケジュールされた会議への参加者が利用できる機能を制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-104">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="3ca8a-105">ポリシーを作成して変更を行った後、ユーザーをポリシーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-105">After you create a policy and make your changes, you can then assign users to the policy.</span></span> <span data-ttu-id="3ca8a-106">会議ポリシーは、Microsoft Teams 管理センターで管理するか、[PowerShell](teams-powershell-overview.md) を使用して管理します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-106">You manage meeting policies in the Microsoft Teams admin center or by using [PowerShell](teams-powershell-overview.md).</span></span>

<span data-ttu-id="3ca8a-107">次の方法でポリシーを実装できます。これらの方法は、会議の開始前、会議中、または会議後のユーザーの会議エクスペリエンスに影響します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-107">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span>

|<span data-ttu-id="3ca8a-108">実装の種類</span><span class="sxs-lookup"><span data-stu-id="3ca8a-108">Implementation type</span></span>  |<span data-ttu-id="3ca8a-109">説明</span><span class="sxs-lookup"><span data-stu-id="3ca8a-109">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="3ca8a-110">開催者単位</span><span class="sxs-lookup"><span data-stu-id="3ca8a-110">Per-organizer</span></span>    |<span data-ttu-id="3ca8a-111">開催者単位のポリシーを実装すると、すべての参加者は開催者のポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-111">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="3ca8a-112">たとえば、[**ユーザーの参加を自動的に許可する**] は、開催者単位のポリシーであり、ユーザーが会議に直接参加するか、ポリシーが割り当てられたユーザーがスケジュールした会議をロビーで待機するかを制御します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-112">For example, **Automatically admit people** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="3ca8a-113">ユーザーごと</span><span class="sxs-lookup"><span data-stu-id="3ca8a-113">Per-user</span></span>    |<span data-ttu-id="3ca8a-114">ユーザーごとのポリシーを実装すると、ユーザーごとのポリシーのみが適用され、開催者や会議参加者に対する特定の機能が制限されます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-114">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="3ca8a-115">たとえば、[**チャネルで "今すぐ会議" を許可する**] は、ユーザー単位のポリシーです。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-115">For example, **Allow Meet now in channels** is a per-user policy.</span></span>     |
|<span data-ttu-id="3ca8a-116">開催者単位およびユーザーごと</span><span class="sxs-lookup"><span data-stu-id="3ca8a-116">Per-organizer and per-user</span></span>     |<span data-ttu-id="3ca8a-117">開催者単位とユーザー単位のポリシーを組み合わせて実装すると、会議の参加者はユーザーのポリシーと開催者のポリシーに基づいて特定の機能が制限されます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-117">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="3ca8a-118">たとえば、[**クラウド記録を許可する**] は、開催者単位およびユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-118">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="3ca8a-119">この設定をオンにすると、会議の開催者と参加者は記録の開始と停止が可能になります。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-119">Turn on this setting to allow the meeting organizer and participants to start and stop a recording.</span></span>

<span data-ttu-id="3ca8a-120">既定では、グローバル (組織全体の既定値) という名前のポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-120">By default, a policy named Global (Org-wide default) is created.</span></span> <span data-ttu-id="3ca8a-121">組織内のすべてのユーザーに、このグローバル会議ポリシーが既定で割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-121">All users in your organization are assigned the Global meeting policy by default.</span></span> <span data-ttu-id="3ca8a-122">ポリシーを変更するか、1 つ以上のカスタム ポリシーを作成してユーザーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-122">You can either make changes to it or create one or more custom policies and assign users to them.</span></span> <span data-ttu-id="3ca8a-123">カスタム ポリシーを作成して割り当てていない場合、ユーザーにはグローバル ポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-123">Users will get the Global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="3ca8a-124">カスタム ポリシーを作成するときに、特定の機能をユーザーに対して使用可能または使用不可にして、そのポリシーを、適用する 1 人以上のユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-124">When you create a custom policy, you can allow or prevent certain features from being available to your users, and then assign it to one or more users who will have the settings applied to them.</span></span>

## <a name="change-or-create-a-meeting-policy"></a><span data-ttu-id="3ca8a-125">会議ポリシーを変更または作成する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-125">Change or create a meeting policy</span></span>

<span data-ttu-id="3ca8a-126">会議ポリシーを変更または作成するには、Microsoft Teams 管理センターにアクセスし、[**会議**]  >  [**会議ポリシー**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-126">To change or create a meeting policy, go to the Microsoft Teams admin center > **Meetings** > **Meeting policies**.</span></span> <span data-ttu-id="3ca8a-127">一覧からポリシーを選択するか、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-127">Select a policy from the list or select **Add**.</span></span> <span data-ttu-id="3ca8a-128">新しいポリシーを作成する場合は、名前と説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-128">If you're creating a new policy, add a name and description.</span></span> <span data-ttu-id="3ca8a-129">名前に特殊文字を含めたり、64 文字より長くすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-129">The name can't contain special characters or be longer than 64 characters.</span></span> <span data-ttu-id="3ca8a-130">設定を選び、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-130">Choose your settings, and then select **Save**.</span></span>

<span data-ttu-id="3ca8a-131">たとえば、多数のユーザーがいて、会議に必要な帯域幅を制限するとします。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-131">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="3ca8a-132">「制限された帯域幅」という名前の新しいカスタム ポリシーを作成し、次の設定を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-132">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="3ca8a-133">[**オーディオとビデオ**] で、</span><span class="sxs-lookup"><span data-stu-id="3ca8a-133">Under **Audio & video**:</span></span>
- <span data-ttu-id="3ca8a-134">[クラウド記録を許可する] を無効にします。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-134">Turn off Allow cloud recording.</span></span>
- <span data-ttu-id="3ca8a-135">[IP のビデオを許可する] を無効にします。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-135">Turn off Allow IP video.</span></span>

<span data-ttu-id="3ca8a-136">[**コンテンツの共有**] で、</span><span class="sxs-lookup"><span data-stu-id="3ca8a-136">Under **Content sharing**:</span></span>
- <span data-ttu-id="3ca8a-137">画面共有モードを無効にします。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-137">Disable screen sharing mode.</span></span>
- <span data-ttu-id="3ca8a-138">[ホワイトボードを許可] を無効にします。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-138">Turn off Allow whiteboard.</span></span>
- <span data-ttu-id="3ca8a-139">[メモの共有を許可する] を無効にします。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-139">Turn off Allow shared notes.</span></span>

<span data-ttu-id="3ca8a-140">その後、ポリシーをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-140">Then assign the policy to the users.</span></span>

> [!NOTE]
> <span data-ttu-id="3ca8a-141">ユーザーに割り当てることができる会議ポリシーは一度に 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-141">A user can be assigned only one meeting policy at a time.</span></span>

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="3ca8a-142">ユーザーに会議ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="3ca8a-142">Assign a meeting policy to users</span></span>

1. <span data-ttu-id="3ca8a-143">Microsoft Teams 管理センターの左側のナビゲーションで、[**ユーザー**] に移動してユーザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-143">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="3ca8a-144">ユーザー名の左側をクリックしてユーザーを選択し、[**編集を設定する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-144">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="3ca8a-145">[**会議ポリシー**] で割り当てるポリシーを選択し、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-145">Under **Meeting policy**, select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="3ca8a-146">一度に複数のユーザーにポリシーを割り当てる方法については、「[一括でTeams のユーザー設定を編集する](edit-user-settings-in-bulk.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-146">To assign a policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="3ca8a-147">または、次の操作も実行できます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-147">Or, you can also do the following:</span></span>

1. <span data-ttu-id="3ca8a-148">Microsoft Teams 管理センターの左側のナビゲーションで、[**会議**]  >  [**会議ポリシー**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-148">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="3ca8a-149">ポリシー名の左側をクリックしてポリシーを選びます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-149">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="3ca8a-150">[**ユーザーを管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-150">Select **Manage users**.</span></span>
4. <span data-ttu-id="3ca8a-151">[**ユーザーを管理**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-151">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="3ca8a-152">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-152">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="3ca8a-153">ユーザーの追加が完了したら、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-153">After you finish adding users, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="3ca8a-154">ユーザーが割り当てられているポリシーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-154">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="3ca8a-155">影響を受けるすべてのユーザーにまず異なるポリシーを割り当ててから、元のポリシーを削除できます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-155">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

## <a name="meeting-policy-settings"></a><span data-ttu-id="3ca8a-156">会議ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="3ca8a-156">Meeting policy settings</span></span>

<span data-ttu-id="3ca8a-157">[**会議ポリシー**] ページで既存のポリシーを選択するか、新しいポリシーを追加するための [**追加**] を選択すると、次の設定内容を構成できます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-157">When you select an existing policy on the **Meeting policies** page or select **Add** to add a new policy, you can configure settings for the following.</span></span>

- [<span data-ttu-id="3ca8a-158">全般</span><span class="sxs-lookup"><span data-stu-id="3ca8a-158">General</span></span>](#meeting-policy-settings---general)
- [<span data-ttu-id="3ca8a-159">オーディオとビデオ</span><span class="sxs-lookup"><span data-stu-id="3ca8a-159">Audio & video</span></span>](#meeting-policy-settings---audio--video)
- [<span data-ttu-id="3ca8a-160">コンテンツの共有</span><span class="sxs-lookup"><span data-stu-id="3ca8a-160">Content sharing</span></span>](#meeting-policy-settings---content-sharing)
- [<span data-ttu-id="3ca8a-161">参加者とゲスト</span><span class="sxs-lookup"><span data-stu-id="3ca8a-161">Participants & guests</span></span>](#meeting-policy-settings---participants--guests)

::: zone-end 

<span data-ttu-id="3ca8a-162"><a name="bkgeneral"> </a></span><span class="sxs-lookup"><span data-stu-id="3ca8a-162"><a name="bkgeneral"> </a></span></span>

## <a name="meeting-policy-settings---general"></a><span data-ttu-id="3ca8a-163">会議ポリシーの設定 - 全般</span><span class="sxs-lookup"><span data-stu-id="3ca8a-163">Meeting policy settings - General</span></span>

- [<span data-ttu-id="3ca8a-164">チャネルで "今すぐ会議" を許可する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-164">Allow Meet now in channels</span></span>](#allow-meet-now-in-channels)
- [<span data-ttu-id="3ca8a-165">Outlook アドインを許可する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-165">Allow the Outlook add-in</span></span>](#allow-the-outlook-add-in)
- [<span data-ttu-id="3ca8a-166">チャネルの会議スケジュールを許可する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-166">Allow channel meeting scheduling</span></span>](#allow-channel-meeting-scheduling)
- [<span data-ttu-id="3ca8a-167">プライベート会議のスケジュールを許可する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-167">Allow scheduling private meetings</span></span>](#allow-scheduling-private-meetings)

### <a name="allow-meet-now-in-channels"></a><span data-ttu-id="3ca8a-168">チャネルで "今すぐ会議" を許可する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-168">Allow Meet now in channels</span></span>

<span data-ttu-id="3ca8a-169">これはユーザーごとのポリシーであり、会議が始まる前に適用されます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-169">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="3ca8a-170">この設定は、ユーザーが Teams チャネルでアドホック会議を開始できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-170">This setting controls whether a user can start an ad hoc meeting in a Teams channel.</span></span> <span data-ttu-id="3ca8a-171">これをオンにすると、ユーザーが Teams チャネルにメッセージを投稿するときに、ユーザーは作成ボックスの下の [**今すぐ会議**] をクリックして、チャネルでアドホック会議を開始できます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-171">If you turn this on, when a user posts a message in a Teams channel, the user can click **Meet now** under the compose box to start an ad hoc meeting in the channel.</span></span>

![メッセージの下の [今すぐ会議] アイコンが表示されたスクリーンショット](media/meeting-policies-meet-now.png)

### <a name="allow-the-outlook-add-in"></a><span data-ttu-id="3ca8a-173">Outlook アドインを許可する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-173">Allow the Outlook add-in</span></span>

<span data-ttu-id="3ca8a-174">これはユーザーごとのポリシーであり、会議が始まる前に適用されます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-174">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="3ca8a-175">この設定は、Outlook (Windows、Mac、Web、およびモバイル) 内から Teams 会議をスケジュールできるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-175">This setting controls whether Teams meetings can be scheduled from within Outlook (Windows, Mac, web, and mobile).</span></span>

![新しい会議をスケジュールする機能が表示されたスクリーンショット](media/meeting-policies-outlook-add-in.png)

<span data-ttu-id="3ca8a-177">これをオフにすると、ユーザーは Outlook で新しい会議を作成するときに Teams 会議をスケジュールできなくなります。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-177">If you turn this off, users are unable to schedule Teams meetings when they create a new meeting in Outlook.</span></span> <span data-ttu-id="3ca8a-178">たとえば、Windows 上の Outlook では、[**新しい Teams 会議**] オプションはリボンに表示されません。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-178">For example, in Outlook on Windows, the **New Teams Meeting** option won't show up in the ribbon.</span></span>

### <a name="allow-channel-meeting-scheduling"></a><span data-ttu-id="3ca8a-179">チャネルの会議スケジュールを許可する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-179">Allow channel meeting scheduling</span></span>

<span data-ttu-id="3ca8a-180">これはユーザーごとのポリシーであり、会議が始まる前に適用されます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-180">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="3ca8a-181">この設定は、ユーザーが Teams チャネルで会議をスケジュールできるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-181">This setting controls whether users can schedule a meeting in a Teams channel.</span></span>  <span data-ttu-id="3ca8a-182">これをオフにすると、ユーザーは Teams チャネルで会議を開始するときに [**会議の予約**] オプションを使用できなくなり、Teams のユーザーに対して [**チャネルの追加**] オプションが無効になります。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-182">If you turn this off, the **Schedule a meeting** option won't be available to the user when they start a meeting in a Teams channel and the **Add channel** option is disabled for users in Teams.</span></span>

![Teams の [会議の予約] オプションが表示されたスクリーンショット](media/meeting-policies-schedule-a-meeting.png)

![[会議をするチャネルを選択] オプションが表示されたスクリーンショット](media/meeting-policies-select-a-channel-to-meet-in.png)

### <a name="allow-scheduling-private-meetings"></a><span data-ttu-id="3ca8a-185">プライベート会議のスケジュールを許可する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-185">Allow scheduling private meetings</span></span>

<span data-ttu-id="3ca8a-186">これはユーザーごとのポリシーであり、会議が始まる前に適用されます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-186">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="3ca8a-187">この設定は、ユーザーが Teams でプライベート会議をスケジュールできるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-187">This setting controls whether users can schedule private meetings in Teams.</span></span> <span data-ttu-id="3ca8a-188">チームのチャネルに公開されていない会議はプライベートです。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-188">A meeting is private when it's not published to a channel in a team.</span></span>

<span data-ttu-id="3ca8a-189">[**プライベート会議のスケジュールを許可する**] および [**チャネルの会議スケジュールを許可する**] を無効にすると、Teams のユーザーに対して [**必須出席者の追加**] および [**チャネルの追加**] オプションが無効になります。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-189">Note that if you turn off **Allow scheduling private meetings** and **Allow channel meeting scheduling**,  the **Add required attendees** and **Add channel** options are disabled for users in Teams.</span></span>

<span data-ttu-id="3ca8a-190"><a name="bkaudioandvideo"> </a></span><span class="sxs-lookup"><span data-stu-id="3ca8a-190"><a name="bkaudioandvideo"> </a></span></span>

## <a name="meeting-policy-settings---audio--video"></a><span data-ttu-id="3ca8a-191">会議ポリシーの設定 - オーディオとビデオ</span><span class="sxs-lookup"><span data-stu-id="3ca8a-191">Meeting policy settings - Audio & video</span></span>

- [<span data-ttu-id="3ca8a-192">文字起こしを許可する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-192">Allow transcription</span></span>](#allow-transcription)
- [<span data-ttu-id="3ca8a-193">クラウド記録を許可する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-193">Allow cloud recording</span></span>](#allow-cloud-recording)
- [<span data-ttu-id="3ca8a-194">IP のビデオを許可する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-194">Allow IP video</span></span>](#allow-ip-video)
- [<span data-ttu-id="3ca8a-195">メディア ビット レート (KBs)</span><span class="sxs-lookup"><span data-stu-id="3ca8a-195">Media bit rate (KBs)</span></span>](#media-bit-rate-kbs)

### <a name="allow-transcription"></a><span data-ttu-id="3ca8a-196">文字起こしを許可する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-196">Allow transcription</span></span>

<span data-ttu-id="3ca8a-197">これは、開催者単位とユーザーごとのポリシーの組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-197">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="3ca8a-198">この設定は、会議の記録の再生中にキャプションと文字起こし機能を使用できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-198">This setting controls whether captions and transcription features are available during playback of meeting recordings.</span></span> <span data-ttu-id="3ca8a-199">これをオフにすると、会議の記録の再生中に [**検索**] および [**CC**] オプションを使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-199">If you turn this off, the **Search** and **CC** options won't be available during playback of a meeting recording.</span></span> <span data-ttu-id="3ca8a-200">記録を開始したユーザーは、記録に文字起こしも含まれるように、この設定を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-200">The person who started the recording needs this setting turned on so that the recording also includes transcription.</span></span> 

<span data-ttu-id="3ca8a-201">記録された会議の文字起こしは、現在、Teams の言語が英語に設定されているユーザー、および会議で英語が話されている場合のユーザーに対してのみサポートされていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-201">Note that transcription for recorded meetings is currently only supported for users who have the language in Teams set to English and when English is spoken in the meeting.</span></span>

![会議の文字起こしオプションが表示されたスクリーンショット](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a><span data-ttu-id="3ca8a-203">クラウド記録を許可する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-203">Allow cloud recording</span></span>

<span data-ttu-id="3ca8a-204">これは、開催者単位とユーザーごとのポリシーの組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-204">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="3ca8a-205">この設定は、このユーザーの会議を記録できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-205">This setting controls whether this user's meetings can be recorded.</span></span> <span data-ttu-id="3ca8a-206">参加者のポリシー設定が有効になっており、同じ組織の認証済みユーザーである場合、会議の開催者または別の会議参加者が記録を開始できます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-206">The recording can be started by the meeting organizer or by another meeting participant if the policy setting is turned on for the participant and if they're an authenticated user from the same organization.</span></span>

<span data-ttu-id="3ca8a-207">フェデレーション ユーザーや匿名ユーザーなど、組織外のユーザーは記録を開始できません。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-207">People outside your organization, such as federated and anonymous users, can't start the recording.</span></span> <span data-ttu-id="3ca8a-208">ゲスト ユーザーは記録を開始または停止できません。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-208">Guest users can't start or stop the recording.</span></span> 

![記録オプションが表示されたスクリーンショット](media/meeting-policies-recording.png)

<span data-ttu-id="3ca8a-210">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-210">Let's look at the following example.</span></span>

|<span data-ttu-id="3ca8a-211">ユーザー</span><span class="sxs-lookup"><span data-stu-id="3ca8a-211">User</span></span> |<span data-ttu-id="3ca8a-212">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="3ca8a-212">Meeting policy</span></span>  |<span data-ttu-id="3ca8a-213">クラウド記録を許可する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-213">Allow cloud recording</span></span> |
|---------|---------|---------|
|<span data-ttu-id="3ca8a-214">Daniela</span><span class="sxs-lookup"><span data-stu-id="3ca8a-214">Daniela</span></span> | <span data-ttu-id="3ca8a-215">グローバル</span><span class="sxs-lookup"><span data-stu-id="3ca8a-215">Global</span></span>   | <span data-ttu-id="3ca8a-216">False</span><span class="sxs-lookup"><span data-stu-id="3ca8a-216">False</span></span> |
|<span data-ttu-id="3ca8a-217">Amanda</span><span class="sxs-lookup"><span data-stu-id="3ca8a-217">Amanda</span></span> | <span data-ttu-id="3ca8a-218">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="3ca8a-218">Location1MeetingPolicy</span></span> | <span data-ttu-id="3ca8a-219">True</span><span class="sxs-lookup"><span data-stu-id="3ca8a-219">True</span></span>|
|<span data-ttu-id="3ca8a-220">John (外部ユーザー)</span><span class="sxs-lookup"><span data-stu-id="3ca8a-220">John (external user)</span></span> | <span data-ttu-id="3ca8a-221">該当なし</span><span class="sxs-lookup"><span data-stu-id="3ca8a-221">Not applicable</span></span> | <span data-ttu-id="3ca8a-222">該当なし</span><span class="sxs-lookup"><span data-stu-id="3ca8a-222">Not applicable</span></span>|

<span data-ttu-id="3ca8a-223">Daniela が開催する会議は記録されず、ポリシー設定が有効になっている Amanda は Daniela が開催する会議を記録できません。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-223">Meetings organized by Daniela can't be recorded and Amanda, who has the policy setting enabled, can't record meetings organized by Daniela.</span></span> <span data-ttu-id="3ca8a-224">Amanda が開催する会議は記録できますが、ポリシー設定が無効になっている Daniela と外部ユーザーである John は、Amanda が開催する会議を記録できません。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-224">Meetings organized by Amanda can be recorded, however,  Daniela, who has the policy setting disabled and John who is an external user, can't record meetings organized by Amanda.</span></span>

<span data-ttu-id="3ca8a-225">クラウド会議の記録の詳細については、「[Teams のクラウド会議の記録](cloud-recording.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-225">To learn more about cloud meeting recording, see [Teams cloud meeting recording](cloud-recording.md).</span></span>

### <a name="allow-ip-video"></a><span data-ttu-id="3ca8a-226">IP ビデオを許可する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-226">Allow IP video</span></span>

<span data-ttu-id="3ca8a-227">これは、開催者単位とユーザーごとのポリシーの組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-227">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="3ca8a-228">ビデオは、会議の重要な構成要素です。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-228">Video is a key component to meetings.</span></span> <span data-ttu-id="3ca8a-229">一部の組織では、管理者はどのユーザーの会議でビデオを使用するかについてより詳細に制御したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-229">In some organizations, admins might want more control over which users’ meetings have video.</span></span> <span data-ttu-id="3ca8a-230">この設定は、ユーザーがホストする会議、およびユーザーが開始する 1:1 通話やグループ通話でビデオを有効にできるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-230">This setting controls whether video can be turned on in meetings hosted by a user and in 1:1 calls and group calls started by a user.</span></span> <span data-ttu-id="3ca8a-231">このポリシーを有効にしたユーザーが開催する会議では、会議の参加者もポリシーを有効にしている場合に、会議の参加者による会議でのビデオ共有が許可されます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-231">Meetings organized by a user who has this policy enabled, allow video sharing in the meeting by the meeting participants, if the meeting participants also have the policy enabled.</span></span> <span data-ttu-id="3ca8a-232">ポリシーが割り当てられていない会議参加者 (匿名参加者やフェデレーション参加者など) は、会議開催者のポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-232">Meeting participants who don't have any policies assigned (for example, anonymous and federated participants) inherit the policy of the meeting organizer.</span></span>

![オーディオとビデオの設定を含む会議が表示されたスクリーンショット](media/meeting-policies-audio-video-settings.png)

<span data-ttu-id="3ca8a-234">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-234">Let's look at the following example.</span></span>

|<span data-ttu-id="3ca8a-235">ユーザー</span><span class="sxs-lookup"><span data-stu-id="3ca8a-235">User</span></span> |<span data-ttu-id="3ca8a-236">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="3ca8a-236">Meeting policy</span></span>  |<span data-ttu-id="3ca8a-237">IP ビデオを許可する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-237">Allow IP Video</span></span> |
|---------|---------|---------|
|<span data-ttu-id="3ca8a-238">Daniela</span><span class="sxs-lookup"><span data-stu-id="3ca8a-238">Daniela</span></span>   | <span data-ttu-id="3ca8a-239">グローバル</span><span class="sxs-lookup"><span data-stu-id="3ca8a-239">Global</span></span>   | <span data-ttu-id="3ca8a-240">True</span><span class="sxs-lookup"><span data-stu-id="3ca8a-240">True</span></span>        |
|<span data-ttu-id="3ca8a-241">Amanda</span><span class="sxs-lookup"><span data-stu-id="3ca8a-241">Amanda</span></span>    | <span data-ttu-id="3ca8a-242">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="3ca8a-242">Location1MeetingPolicy</span></span>        | <span data-ttu-id="3ca8a-243">False</span><span class="sxs-lookup"><span data-stu-id="3ca8a-243">False</span></span>      |

<span data-ttu-id="3ca8a-244">Daniela が開催する会議では、ビデオを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-244">Meetings hosted by Daniela allow video to be turned on.</span></span> <span data-ttu-id="3ca8a-245">Daniela は会議に参加してビデオを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-245">Daniela can join the meeting and turn on video.</span></span> <span data-ttu-id="3ca8a-246">Amanda のポリシーはビデオを許可しないように設定されているため、Amanda は Daniela の会議でビデオを有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-246">Amanda can't turn on video in Daniela's meeting because Amanda’s policy is set to not allow video.</span></span> <span data-ttu-id="3ca8a-247">Amanda は、会議の他の参加者が共有しているビデオを見ることができます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-247">Amanda can see videos shared by other participants in the meeting.</span></span>

<span data-ttu-id="3ca8a-248">Amanda が主催する会議では、割り当てられたビデオ ポリシーに関係なく、誰もビデオを有効にできません。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-248">In meetings hosted by Amanda, no one can turn on video, regardless of the video policy assigned to them.</span></span> <span data-ttu-id="3ca8a-249">これは、Daniela が Amanda の会議でビデオを有効にできないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-249">This means Daniela can't turn on video in Amanda’s meetings.</span></span>  

<span data-ttu-id="3ca8a-250">Daniela がビデオを有効にして Amanda に電話した場合、Amanda はオーディオのみで電話に出ることができます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-250">If Daniela calls Amanda with video on, Amanda can answer the call with audio only.</span></span>  <span data-ttu-id="3ca8a-251">通話が接続されると、Amanda は Daniela のビデオを見ることができますが、ビデオを有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-251">When the call is connected, Amanda can see Daniela’s video, but can't turn on video.</span></span> <span data-ttu-id="3ca8a-252">Amanda が Daniela に電話すると、Daniela はビデオとオーディオで電話に出ることができます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-252">If Amanda calls Daniela, Daniela can answer the call with video and audio.</span></span> <span data-ttu-id="3ca8a-253">通話が接続されると、Daniela は必要に応じてビデオを有効または無効にできます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-253">When the call is connected, Daniela can turn on or turn off her video, as needed.</span></span>

### <a name="media-bit-rate-kbs"></a><span data-ttu-id="3ca8a-254">メディア ビット レート (KBs)</span><span class="sxs-lookup"><span data-stu-id="3ca8a-254">Media bit rate (KBs)</span></span>

<span data-ttu-id="3ca8a-255">これは、ユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-255">This is a per-user policy.</span></span> <span data-ttu-id="3ca8a-256">この設定により、ユーザーの通話および会議でのオーディオ、ビデオ、およびビデオベースのアプリ共有送信のメディア ビット レートが決まります。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-256">This setting determines the media bit rate for audio, video, and video-based app sharing transmissions in calls and meetings for the user.</span></span> <span data-ttu-id="3ca8a-257">通話または会議のユーザーのアップリンクとダウンリンクの両方のメディア トラバーサルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-257">It's applied to both the uplink and downlink media traversal for users in the call or meeting.</span></span> <span data-ttu-id="3ca8a-258">この設定により、組織の帯域幅の管理をきめ細やかに制御できます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-258">This setting gives you granular control over managing bandwidth in your organization.</span></span> <span data-ttu-id="3ca8a-259">ユーザーが必要とする会議シナリオに応じて、高品質のエクスペリエンスを得るために十分な帯域幅を用意することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-259">Depending on the meetings scenarios required by users, we recommend having enough bandwidth in place for a good quality experience.</span></span> <span data-ttu-id="3ca8a-260">最小値は 30 Kbps で、最大値は会議シナリオによって異なります。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-260">The minimum value is 30 Kbps and the maximum value depends on the meeting scenario.</span></span> <span data-ttu-id="3ca8a-261">Teams での高品質の会議、通話、およびライブ イベントを実現する最小推奨帯域幅の詳細については、「[帯域幅要件](prepare-network.md#bandwidth-requirements)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-261">To learn more about the minimum recommended bandwidth for good quality meetings, calls, and live events in Teams, see [Bandwidth requirements](prepare-network.md#bandwidth-requirements).</span></span>

<span data-ttu-id="3ca8a-262">会議に十分な帯域幅がない場合、参加者にはネットワーク品質の低下を示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-262">If there isn’t enough bandwidth for a meeting, participants see a message that indicates poor network quality.</span></span>

<span data-ttu-id="3ca8a-263">CEO ボード会議や Teams のライブ イベントなど、最高品質のビデオ エクスペリエンスを必要とする会議では、帯域幅を 10 Mbps に設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-263">For meetings that need the highest quality video experience, such as CEO board meetings and Teams live events, we recommend you set the bandwidth to 10 Mbps.</span></span> <span data-ttu-id="3ca8a-264">最大限のエクスペリエンスが設定されている場合でも、特定のネットワーク条件が検出されると、シナリオに応じて、Teams メディア スタックは低帯域幅の条件に適応します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-264">Even when the maximum experience is set, the Teams media stack adapts to low bandwidth conditions when certain network conditions are detected, depending on the scenario.</span></span> 

## <a name="meeting-policy-settings---content-sharing"></a><span data-ttu-id="3ca8a-265">会議ポリシーの設定 - コンテンツの共有</span><span class="sxs-lookup"><span data-stu-id="3ca8a-265">Meeting policy settings - Content sharing</span></span>

- [<span data-ttu-id="3ca8a-266">画面共有モード</span><span class="sxs-lookup"><span data-stu-id="3ca8a-266">Screen sharing mode</span></span>](#screen-sharing-mode)
- [<span data-ttu-id="3ca8a-267">参加者に制御を渡す、または制御を要求する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-267">Allow a participant to give or request control</span></span>](#allow-a-participant-to-give-or-request-control)
- [<span data-ttu-id="3ca8a-268">外部の参加者に制御を渡す、または制御を要求する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-268">Allow an external participant to give or request control</span></span>](#allow-an-external-participant-to-give-or-request-control)
- [<span data-ttu-id="3ca8a-269">PowerPoint の共有を許可する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-269">Allow PowerPoint sharing</span></span>](#allow-powerpoint-sharing)
- [<span data-ttu-id="3ca8a-270">ホワイトボードを許可する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-270">Allow whiteboard</span></span>](#allow-whiteboard)
- [<span data-ttu-id="3ca8a-271">メモの共有を許可する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-271">Allow shared notes</span></span>](#allow-shared-notes)

### <a name="screen-sharing-mode"></a><span data-ttu-id="3ca8a-272">画面共有モード</span><span class="sxs-lookup"><span data-stu-id="3ca8a-272">Screen sharing mode</span></span>

<span data-ttu-id="3ca8a-273">これは、開催者単位とユーザーごとのポリシーの組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-273">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="3ca8a-274">この設定は、ユーザーの会議でデスクトップやウィンドウの共有を許可するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-274">This setting controls whether desktop and/or window sharing is allowed in the user's meeting.</span></span> <span data-ttu-id="3ca8a-275">ポリシーが割り当てられていない会議参加者 (匿名参加者、ゲスト参加者、B2B 参加者、フェデレーション参加者など) は、会議開催者のポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-275">Meeting participants who don't have any policies assigned (for example, anonymous, guest, B2B, and federated participants) inherit the policy of the meeting organizer.</span></span>

|<span data-ttu-id="3ca8a-276">値を設定する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-276">Setting value</span></span> |<span data-ttu-id="3ca8a-277">動作</span><span class="sxs-lookup"><span data-stu-id="3ca8a-277">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="3ca8a-278">**画面全体**</span><span class="sxs-lookup"><span data-stu-id="3ca8a-278">**Entire screen**</span></span>    | <span data-ttu-id="3ca8a-279">会議では完全なデスクトップ共有とアプリケーション共有が許可されます</span><span class="sxs-lookup"><span data-stu-id="3ca8a-279">Full desktop sharing and application sharing is allowed in the meeting</span></span> |
|<span data-ttu-id="3ca8a-280">**単一アプリケーション**</span><span class="sxs-lookup"><span data-stu-id="3ca8a-280">**Single application**</span></span>   | <span data-ttu-id="3ca8a-281">会議ではアプリケーションの共有が許可されます</span><span class="sxs-lookup"><span data-stu-id="3ca8a-281">Application sharing is allowed in the meeting</span></span>        |
|<span data-ttu-id="3ca8a-282">**無効**</span><span class="sxs-lookup"><span data-stu-id="3ca8a-282">**Disabled**</span></span>     |<span data-ttu-id="3ca8a-283">会議では画面共有とアプリケーション共有が無効になります。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-283">Screen sharing and application sharing turned off in the meeting.</span></span>       |

<span data-ttu-id="3ca8a-284">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-284">Let's look at the following example.</span></span>

|<span data-ttu-id="3ca8a-285">ユーザー</span><span class="sxs-lookup"><span data-stu-id="3ca8a-285">User</span></span> |<span data-ttu-id="3ca8a-286">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="3ca8a-286">Meeting policy</span></span> |<span data-ttu-id="3ca8a-287">画面共有モード</span><span class="sxs-lookup"><span data-stu-id="3ca8a-287">Screen sharing mode</span></span> |
|---------|---------|---------|
|<span data-ttu-id="3ca8a-288">Daniela</span><span class="sxs-lookup"><span data-stu-id="3ca8a-288">Daniela</span></span>  | <span data-ttu-id="3ca8a-289">グローバル</span><span class="sxs-lookup"><span data-stu-id="3ca8a-289">Global</span></span>   | <span data-ttu-id="3ca8a-290">画面全体</span><span class="sxs-lookup"><span data-stu-id="3ca8a-290">Entire screen</span></span> |
|<span data-ttu-id="3ca8a-291">Amanda</span><span class="sxs-lookup"><span data-stu-id="3ca8a-291">Amanda</span></span>   | <span data-ttu-id="3ca8a-292">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="3ca8a-292">Location1MeetingPolicy</span></span>  | <span data-ttu-id="3ca8a-293">無効</span><span class="sxs-lookup"><span data-stu-id="3ca8a-293">Disabled</span></span> |

<span data-ttu-id="3ca8a-294">Daniela が開催する会議では、会議の参加者が画面全体または特定のアプリケーションを共有できます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-294">Meetings hosted by Daniela allow meeting participants to share their entire screen or a specific application.</span></span> <span data-ttu-id="3ca8a-295">Amanda が Daniela の会議に参加すると、ポリシー設定が無効になっているため、Amanda は自分の画面または特定のアプリケーションを共有できません。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-295">If Amanda joins Daniela’s meeting, Amanda can't share her screen or a specific application as her policy setting is disabled.</span></span> <span data-ttu-id="3ca8a-296">Amanda がホストする会議では、割り当てられた画面共有モード ポリシーに関係なく、誰も画面または単一のアプリケーションを共有できません。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-296">In meetings hosted by Amanda, no one is allowed to share their screen or a single application, regardless of the screen sharing mode policy assigned to them.</span></span> <span data-ttu-id="3ca8a-297">つまり、Daniela は Amanda の会議で自分の画面や単一のアプリケーションを共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-297">This means that Daniela can't share her screen or a single application in Amanda’s meetings.</span></span>  

<span data-ttu-id="3ca8a-298">現在、ユーザーは Google Chrome を使用している場合、Teams 会議でビデオを再生したり画面を共有したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-298">Currently, users can't play video or share their screen in a Teams meeting if they're using Google Chrome.</span></span>

### <a name="allow-a-participant-to-give-or-request-control"></a><span data-ttu-id="3ca8a-299">参加者に制御を渡す、または制御を要求する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-299">Allow a participant to give or request control</span></span>

<span data-ttu-id="3ca8a-300">これは、ユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-300">This is a per-user policy.</span></span> <span data-ttu-id="3ca8a-301">この設定は、ユーザーが他の会議参加者に共有デスクトップまたはウィンドウの制御を渡すことができるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-301">This setting controls whether the user can give control of the shared desktop or window to other meeting participants.</span></span> <span data-ttu-id="3ca8a-302">制御を渡すには、画面の上部にカーソルを合わせます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-302">To give control, hover over the top of the screen.</span></span> 

<span data-ttu-id="3ca8a-303">ユーザーに対してこの設定が有効になっている場合、共有セッションの上部のバーに [**制御を渡す**] オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-303">If this setting is turned on for the user, the **Give Control** option is displayed in the top bar in a sharing session.</span></span> 

![[制御を渡す] オプションが表示されたスクリーンショット](media/meeting-policies-give-control.png)

<span data-ttu-id="3ca8a-305">ユーザーの設定が無効になっている場合、[**制御を渡す**] オプションは使用できません。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-305">If the settings is turned off for the user, the **Give Control** option isn't available.</span></span>

![[制御を渡す] オプションが利用できないことを示すスクリーンショット](media/meeting-policies-give-control-not-available.png)

<span data-ttu-id="3ca8a-307">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-307">Let's look at the following example.</span></span>

|<span data-ttu-id="3ca8a-308">ユーザー</span><span class="sxs-lookup"><span data-stu-id="3ca8a-308">User</span></span> |<span data-ttu-id="3ca8a-309">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="3ca8a-309">Meeting policy</span></span>  |<span data-ttu-id="3ca8a-310">参加者に制御を渡す、または制御を要求する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-310">Allow participant to give or request control</span></span> |
|---------|---------|---------|
|<span data-ttu-id="3ca8a-311">Daniela</span><span class="sxs-lookup"><span data-stu-id="3ca8a-311">Daniela</span></span>   | <span data-ttu-id="3ca8a-312">グローバル</span><span class="sxs-lookup"><span data-stu-id="3ca8a-312">Global</span></span>   | <span data-ttu-id="3ca8a-313">True</span><span class="sxs-lookup"><span data-stu-id="3ca8a-313">True</span></span>       |
|<span data-ttu-id="3ca8a-314">Babek</span><span class="sxs-lookup"><span data-stu-id="3ca8a-314">Babek</span></span>    | <span data-ttu-id="3ca8a-315">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="3ca8a-315">Location1MeetingPolicy</span></span>        | <span data-ttu-id="3ca8a-316">False</span><span class="sxs-lookup"><span data-stu-id="3ca8a-316">False</span></span>   |

<span data-ttu-id="3ca8a-317">Daniela は、Babek が開催する会議の他の参加者に共有デスクトップまたはウィンドウの制御を渡すことができますが、Babek は他の参加者に制御を渡すことができません。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-317">Daniela can give control of the shared desktop or window to other participants in a meeting organized by Babek whereas Babek can't give control to other participants.</span></span>

<span data-ttu-id="3ca8a-318">制御を渡したり、制御要求を受け入れたりすることができるユーザーを PowerShell を使用して制御するには、AllowParticipantGiveRequestControl コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-318">To use PowerShell to control who can give control or accept requests for control, use the AllowParticipantGiveRequestControl cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="3ca8a-319">共有中に共有コンテンツの制御を渡したり受け取ったりするには、両者が Teams デスクトップ クライアントを使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-319">To give and take control of shared content during sharing, both parties must be using the Teams desktop client.</span></span> <span data-ttu-id="3ca8a-320">いずれかの当事者がブラウザーで Teams を実行している場合、制御はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-320">Control isn't supported when either party is running Teams in a browser.</span></span> <span data-ttu-id="3ca8a-321">これは、修正する予定の技術的制限によるものです。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-321">This is due to a technical limitation that we're planning to fix.</span></span> 

### <a name="allow-an-external-participant-to-give-or-request-control"></a><span data-ttu-id="3ca8a-322">外部の参加者に制御を渡す、または制御を要求する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-322">Allow an external participant to give or request control</span></span>

<span data-ttu-id="3ca8a-323">これは、ユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-323">This is a per-user policy.</span></span> <span data-ttu-id="3ca8a-324">この設定は、会議の外部参加者が共有デスクトップまたはウィンドウの制御を他の会議参加者に渡すことができるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-324">This setting controls whether external participants in a meeting can give control of their shared desktop or window to other participants in the meeting.</span></span> <span data-ttu-id="3ca8a-325">Teams 会議の外部参加者は、次のように分類できます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-325">External participants in Teams meetings can be categorized as follows:</span></span>  

- <span data-ttu-id="3ca8a-326">匿名ユーザー</span><span class="sxs-lookup"><span data-stu-id="3ca8a-326">Anonymous user</span></span>
- <span data-ttu-id="3ca8a-327">ゲスト ユーザー</span><span class="sxs-lookup"><span data-stu-id="3ca8a-327">Guest users</span></span>  
- <span data-ttu-id="3ca8a-328">B2B ユーザー</span><span class="sxs-lookup"><span data-stu-id="3ca8a-328">B2B user</span></span>
- <span data-ttu-id="3ca8a-329">フェデレーション ユーザー</span><span class="sxs-lookup"><span data-stu-id="3ca8a-329">Federated user</span></span>  

<span data-ttu-id="3ca8a-330">フェデレーション ユーザーが共有中に外部ユーザーに制御を渡すことができるかどうかは、組織の「**外部の参加者に制御を渡す、または制御を要求する**」設定によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-330">Whether federated users can give control to external users while sharing is controlled by the **Allow an external participant to give or request control** setting in their organization.</span></span>

<span data-ttu-id="3ca8a-331">PowerShell を使用して、外部の参加者が制御を渡すことができるか、または制御要求を受け入れることができるかを制御するには、AllowExternalParticipantGiveRequestControl コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-331">To use PowerShell to control whether external participants can give control or accept requests for control, use the AllowExternalParticipantGiveRequestControl cmdlet.</span></span>

### <a name="allow-powerpoint-sharing"></a><span data-ttu-id="3ca8a-332">PowerPoint の共有を許可する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-332">Allow PowerPoint sharing</span></span>

<span data-ttu-id="3ca8a-333">これは、ユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-333">This is a per-user policy.</span></span> <span data-ttu-id="3ca8a-334">この設定は、ユーザーが会議で PowerPoint スライド セットを共有できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-334">This setting controls whether the user can share PowerPoint slide decks in a meeting.</span></span> <span data-ttu-id="3ca8a-335">匿名ユーザー、ゲスト ユーザー、フェデレーション ユーザーを含む外部ユーザーは、会議開催者のポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-335">External users, including anonymous, guest, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="3ca8a-336">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-336">Let's look at the following example.</span></span>

|<span data-ttu-id="3ca8a-337">ユーザー</span><span class="sxs-lookup"><span data-stu-id="3ca8a-337">User</span></span> |<span data-ttu-id="3ca8a-338">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="3ca8a-338">Meeting policy</span></span>  |<span data-ttu-id="3ca8a-339">PowerPoint の共有を許可する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-339">Allow PowerPoint sharing</span></span> |
|---------|---------|---------|
|<span data-ttu-id="3ca8a-340">Daniela</span><span class="sxs-lookup"><span data-stu-id="3ca8a-340">Daniela</span></span>   | <span data-ttu-id="3ca8a-341">グローバル</span><span class="sxs-lookup"><span data-stu-id="3ca8a-341">Global</span></span>   | <span data-ttu-id="3ca8a-342">True</span><span class="sxs-lookup"><span data-stu-id="3ca8a-342">True</span></span>       |
|<span data-ttu-id="3ca8a-343">Amanda</span><span class="sxs-lookup"><span data-stu-id="3ca8a-343">Amanda</span></span>   | <span data-ttu-id="3ca8a-344">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="3ca8a-344">Location1MeetingPolicy</span></span>        | <span data-ttu-id="3ca8a-345">False</span><span class="sxs-lookup"><span data-stu-id="3ca8a-345">False</span></span>   |

<span data-ttu-id="3ca8a-346">Amanda は、会議の開催者であっても、PowerPoint スライド セットを会議で共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-346">Amanda can't share PowerPoint slide decks in meetings even if she's the meeting organizer.</span></span> <span data-ttu-id="3ca8a-347">Daniela は、会議が Amanda によって開催されている場合でも、PowerPoint スライド セットを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-347">Daniela can share PowerPoint slide decks even if the meeting is organized by Amanda.</span></span> <span data-ttu-id="3ca8a-348">Amanda は、PowerPoint スライド セットを共有できない場合でも、会議の他のユーザーによって共有されている PowerPoint スライド セットを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-348">Amanda can view the PowerPoint slide decks shared by others in the meeting, even though she can't share PowerPoint slide decks.</span></span>

### <a name="allow-whiteboard"></a><span data-ttu-id="3ca8a-349">ホワイトボードを許可する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-349">Allow whiteboard</span></span>

<span data-ttu-id="3ca8a-350">これは、ユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-350">This is a per-user policy.</span></span> <span data-ttu-id="3ca8a-351">この設定は、ユーザーが会議でホワイトボードを共有できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-351">This setting controls whether a user can share the whiteboard in a meeting.</span></span> <span data-ttu-id="3ca8a-352">匿名ユーザー、B2B ユーザー、およびフェデレーション ユーザーを含む外部ユーザーは、会議開催者のポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-352">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> 

<span data-ttu-id="3ca8a-353">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-353">Let's look at the following example.</span></span>

|<span data-ttu-id="3ca8a-354">ユーザー</span><span class="sxs-lookup"><span data-stu-id="3ca8a-354">User</span></span> |<span data-ttu-id="3ca8a-355">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="3ca8a-355">Meeting policy</span></span>  |<span data-ttu-id="3ca8a-356">ホワイトボードを許可する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-356">Allow whiteboard</span></span>|
|---------|---------|---------|
|<span data-ttu-id="3ca8a-357">Daniela</span><span class="sxs-lookup"><span data-stu-id="3ca8a-357">Daniela</span></span>   | <span data-ttu-id="3ca8a-358">グローバル</span><span class="sxs-lookup"><span data-stu-id="3ca8a-358">Global</span></span>   | <span data-ttu-id="3ca8a-359">True</span><span class="sxs-lookup"><span data-stu-id="3ca8a-359">True</span></span>       |
|<span data-ttu-id="3ca8a-360">Amanda</span><span class="sxs-lookup"><span data-stu-id="3ca8a-360">Amanda</span></span>   | <span data-ttu-id="3ca8a-361">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="3ca8a-361">Location1MeetingPolicy</span></span>        | <span data-ttu-id="3ca8a-362">False</span><span class="sxs-lookup"><span data-stu-id="3ca8a-362">False</span></span>   |

<span data-ttu-id="3ca8a-363">Amanda は、会議の開催者であっても、会議でホワイトボードを共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-363">Amanda can't share the whiteboard in a meeting even if she's the meeting organizer.</span></span> <span data-ttu-id="3ca8a-364">Daniela は、Amanda が会議を開催する場合でも、ホワイトボードを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-364">Daniela can share the whiteboard even if a meeting is organized by Amanda.</span></span>  

### <a name="allow-shared-notes"></a><span data-ttu-id="3ca8a-365">メモの共有を許可する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-365">Allow shared notes</span></span>

<span data-ttu-id="3ca8a-366">これは、ユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-366">This is a per-user policy.</span></span> <span data-ttu-id="3ca8a-367">この設定は、ユーザーが会議でメモを作成および共有できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-367">This setting controls whether a user can create and share notes in a meeting.</span></span> <span data-ttu-id="3ca8a-368">匿名ユーザー、B2B ユーザー、およびフェデレーション ユーザーを含む外部ユーザーは、会議開催者のポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-368">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> <span data-ttu-id="3ca8a-369">現在、[**会議メモ**] タブは、参加者が 20 人未満の会議でのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-369">The **Meeting Notes** tab is currently only supported in meetings that have less than 20 participants.</span></span>

<span data-ttu-id="3ca8a-370">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-370">Let's look at the following example.</span></span>

|<span data-ttu-id="3ca8a-371">ユーザー</span><span class="sxs-lookup"><span data-stu-id="3ca8a-371">User</span></span> |<span data-ttu-id="3ca8a-372">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="3ca8a-372">Meeting policy</span></span>  |<span data-ttu-id="3ca8a-373">メモの共有を許可する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-373">Allow shared notes</span></span> |
|---------|---------|---------|
|<span data-ttu-id="3ca8a-374">Daniela</span><span class="sxs-lookup"><span data-stu-id="3ca8a-374">Daniela</span></span>   | <span data-ttu-id="3ca8a-375">グローバル</span><span class="sxs-lookup"><span data-stu-id="3ca8a-375">Global</span></span>   | <span data-ttu-id="3ca8a-376">True</span><span class="sxs-lookup"><span data-stu-id="3ca8a-376">True</span></span>       |
|<span data-ttu-id="3ca8a-377">Amanda</span><span class="sxs-lookup"><span data-stu-id="3ca8a-377">Amanda</span></span>   | <span data-ttu-id="3ca8a-378">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="3ca8a-378">Location1MeetingPolicy</span></span> | <span data-ttu-id="3ca8a-379">False</span><span class="sxs-lookup"><span data-stu-id="3ca8a-379">False</span></span> |

<span data-ttu-id="3ca8a-380">Daniela は Amanda の会議でメモを取ることができ、Amanda はすべての会議でメモを取ることができません。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-380">Daniela can take notes in Amanda's meetings and Amanda can't take notes in any meetings.</span></span>

## <a name="meeting-policy-settings---participants--guests"></a><span data-ttu-id="3ca8a-381">会議ポリシーの設定 - 参加者とゲスト</span><span class="sxs-lookup"><span data-stu-id="3ca8a-381">Meeting policy settings - Participants & guests</span></span>

<span data-ttu-id="3ca8a-382">これらの設定では、会議への入室が許可されるまでロビーで待機する必要がある会議参加者およびそれらの参加者に許可する会議への参加レベルが制御されます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-382">These settings control which meeting participants wait in the lobby before they are admitted to the meeting and the level of participation they are allowed in a meeting.</span></span>

- [<span data-ttu-id="3ca8a-383">匿名ユーザーが会議を開始できるようにする</span><span class="sxs-lookup"><span data-stu-id="3ca8a-383">Let anonymous people start a meeting</span></span>](#let-anonymous-people-start-a-meeting)
- [<span data-ttu-id="3ca8a-384">ユーザーの参加を自動的に許可する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-384">Automatically admit people</span></span>](#automatically-admit-people)
- [<span data-ttu-id="3ca8a-385">ダイヤルイン ユーザーによるロビーのバイパスを許可する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-385">Allow dial-in users to bypass the lobby</span></span>](#allow-dial-in-users-to-bypass-the-lobby)
- [<span data-ttu-id="3ca8a-386">プライベート会議で "今すぐ会議" を許可する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-386">Allow Meet now in private meetings</span></span>](#allow-meet-now-in-private-meetings)
- [<span data-ttu-id="3ca8a-387">ライブ キャプションを有効にする</span><span class="sxs-lookup"><span data-stu-id="3ca8a-387">Enable live captions </span></span>](#enable-live-captions)
- [<span data-ttu-id="3ca8a-388">会議でチャットを許可する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-388">Allow chat in meetings </span></span>](#allow-chat-in-meetings)

> [!NOTE]
><span data-ttu-id="3ca8a-389">会議に参加するためのオプションは、各 Teams グループの設定および接続方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-389">Options to join a meeting will vary, depending on the settings for each Teams group, and the connection method.</span></span> <span data-ttu-id="3ca8a-390">グループに電話会議があり、それを使用して接続する場合は、「[Office 365 における電話会議](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-390">If your group has audio conferencing, and uses it to connect, see [Audio Conferencing in Office 365](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span></span> <span data-ttu-id="3ca8a-391">Teams グループに電話会議がない場合は、「[Teams での会議に参加する](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-391">If your Teams group does not have audio conferencing, refer to [Join a meeting in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).</span></span>

### <a name="let-anonymous-people-start-a-meeting"></a><span data-ttu-id="3ca8a-392">匿名ユーザーが会議を開始できるようにする</span><span class="sxs-lookup"><span data-stu-id="3ca8a-392">Let anonymous people start a meeting</span></span>

<span data-ttu-id="3ca8a-393">これは開催者単位のポリシーです。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-393">This is a per-organizer policy.</span></span> <span data-ttu-id="3ca8a-394">この設定は、認証された組織のユーザーが参加していない場合でも、B2B ユーザーおよびフェデレーション ユーザーなどの匿名ユーザーがユーザーの会議に参加できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-394">This setting controls whether anonymous people, including B2B, and federated users, can join the user's meeting without an authenticated user from the organization in attendance.</span></span> 

![待機中のユーザーへのメッセージが表示されたスクリーンショット](media/meeting-policies-anonymous-user-lobby.png)

<span data-ttu-id="3ca8a-396">以下は、認証ユーザーが会議に出席しているときの匿名ユーザーの参加動作です。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-396">Here's the join behavior of anonymous people when authenticated users are present in the meeting.</span></span>

|<span data-ttu-id="3ca8a-397">匿名ユーザーが会議を開始できるようにする</span><span class="sxs-lookup"><span data-stu-id="3ca8a-397">Let anonymous people start a meeting</span></span>  |<span data-ttu-id="3ca8a-398">ユーザーの参加を自動的に許可する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-398">Automatically admit people</span></span> |<span data-ttu-id="3ca8a-399">匿名ユーザーの参加動作</span><span class="sxs-lookup"><span data-stu-id="3ca8a-399">Join behavior of anonymous people</span></span> |
|---------|---------|---------|
|<span data-ttu-id="3ca8a-400">True</span><span class="sxs-lookup"><span data-stu-id="3ca8a-400">True</span></span>    | <span data-ttu-id="3ca8a-401">すべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="3ca8a-401">Everyone</span></span>      | <span data-ttu-id="3ca8a-402">直接参加する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-402">Join directly</span></span>         |
|   | <span data-ttu-id="3ca8a-403">組織内のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="3ca8a-403">Everyone in your organization</span></span>       | <span data-ttu-id="3ca8a-404">ロビーで待つ</span><span class="sxs-lookup"><span data-stu-id="3ca8a-404">Wait in lobby</span></span>        |
|   | <span data-ttu-id="3ca8a-405">組織内およびフェデレーション組織のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="3ca8a-405">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="3ca8a-406">ロビーで待つ</span><span class="sxs-lookup"><span data-stu-id="3ca8a-406">Wait in lobby</span></span>         |
|<span data-ttu-id="3ca8a-407">False</span><span class="sxs-lookup"><span data-stu-id="3ca8a-407">False</span></span>    | <span data-ttu-id="3ca8a-408">すべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="3ca8a-408">Everyone</span></span>        | <span data-ttu-id="3ca8a-409">直接参加する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-409">Join directly</span></span>        |
|   | <span data-ttu-id="3ca8a-410">組織内のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="3ca8a-410">Everyone in your organization</span></span>     | <span data-ttu-id="3ca8a-411">ロビーで待つ</span><span class="sxs-lookup"><span data-stu-id="3ca8a-411">Wait in lobby</span></span>        |
|   | <span data-ttu-id="3ca8a-412">組織内およびフェデレーション組織のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="3ca8a-412">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="3ca8a-413">ロビーで待つ</span><span class="sxs-lookup"><span data-stu-id="3ca8a-413">Wait in lobby</span></span>         |

<span data-ttu-id="3ca8a-414">以下は、認証ユーザーが会議に出席していないときの匿名ユーザーの参加動作です。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-414">Here's the join behavior of anonymous people when no authenticated users are present in the meeting.</span></span>

|<span data-ttu-id="3ca8a-415">匿名ユーザーが会議を開始できるようにする</span><span class="sxs-lookup"><span data-stu-id="3ca8a-415">Let anonymous people start a meeting</span></span> |<span data-ttu-id="3ca8a-416">ユーザーの参加を自動的に許可する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-416">Automatically admit people</span></span>  |<span data-ttu-id="3ca8a-417">匿名ユーザーの参加動作</span><span class="sxs-lookup"><span data-stu-id="3ca8a-417">Join behavior of anonymous people</span></span> |
|---------|---------|---------|
|<span data-ttu-id="3ca8a-418">True</span><span class="sxs-lookup"><span data-stu-id="3ca8a-418">True</span></span>    | <span data-ttu-id="3ca8a-419">すべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="3ca8a-419">Everyone</span></span>      | <span data-ttu-id="3ca8a-420">直接参加する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-420">Join directly</span></span>         |
|   | <span data-ttu-id="3ca8a-421">組織内のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="3ca8a-421">Everyone in your organization</span></span>       | <span data-ttu-id="3ca8a-422">ロビーで待つ</span><span class="sxs-lookup"><span data-stu-id="3ca8a-422">Wait in lobby</span></span>        |
|   | <span data-ttu-id="3ca8a-423">組織内およびフェデレーション組織のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="3ca8a-423">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="3ca8a-424">ロビーで待つ</span><span class="sxs-lookup"><span data-stu-id="3ca8a-424">Wait in lobby</span></span>         |
|<span data-ttu-id="3ca8a-425">False</span><span class="sxs-lookup"><span data-stu-id="3ca8a-425">False</span></span>    | <span data-ttu-id="3ca8a-426">すべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="3ca8a-426">Everyone</span></span>        | <span data-ttu-id="3ca8a-427">ロビーで待ちます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-427">Wait in lobby.</span></span> <span data-ttu-id="3ca8a-428">最初の認証ユーザーが会議に参加すると、ユーザーは自動的に許可されます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-428">Users are automatically admitted when the first authenticated user joins the meeting.</span></span>        |
|   | <span data-ttu-id="3ca8a-429">組織内のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="3ca8a-429">Everyone in your organization</span></span>     |<span data-ttu-id="3ca8a-430">ロビーで待つ</span><span class="sxs-lookup"><span data-stu-id="3ca8a-430">Wait in lobby</span></span>         |
|   | <span data-ttu-id="3ca8a-431">組織内およびフェデレーション組織のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="3ca8a-431">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="3ca8a-432">ロビーで待つ</span><span class="sxs-lookup"><span data-stu-id="3ca8a-432">Wait in lobby</span></span>         |

### <a name="automatically-admit-people"></a><span data-ttu-id="3ca8a-433">ユーザーの参加を自動的に許可する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-433">Automatically admit people</span></span>

<span data-ttu-id="3ca8a-434">これは開催者単位のポリシーです。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-434">This is a per-organizer policy.</span></span> <span data-ttu-id="3ca8a-435">この設定は、ユーザーが会議に直接参加するのか、認証ユーザーにより入室が許可されるまでロビーで待機するのかを制御します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-435">This setting controls whether people join a meeting directly or wait in the lobby until they are admitted by an authenticated user.</span></span>

![ロビーにいるユーザーとの会議を示すスクリーンショット](media/meeting-policies-lobby.png)

 <span data-ttu-id="3ca8a-437">会議の開催者は、会議出席依頼の [**会議オプション**] をクリックして、スケジュールする会議ごとにこの設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-437">Meeting organizers can click **Meeting Options** in the meeting invitation to change this setting for each meeting they schedule.</span></span> <span data-ttu-id="3ca8a-438">**近日公開**</span><span class="sxs-lookup"><span data-stu-id="3ca8a-438">**(coming soon)**</span></span>
  
|<span data-ttu-id="3ca8a-439">値を設定する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-439">Setting value</span></span>  |<span data-ttu-id="3ca8a-440">参加動作</span><span class="sxs-lookup"><span data-stu-id="3ca8a-440">Join behavior</span></span> |
|---------|---------|
|<span data-ttu-id="3ca8a-441">**すべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="3ca8a-441">**Everyone**</span></span>   |<span data-ttu-id="3ca8a-442">すべての会議参加者は、ロビーで待たずに会議に直接参加します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-442">All meeting participants join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="3ca8a-443">これには、認証ユーザー、フェデレーション ユーザー、ゲスト、匿名ユーザー、およびスマートフォンでダイヤル インするユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-443">This includes authenticated users, federated users, guests, anonymous users, and people who dial in by phone.</span></span>       |
|<span data-ttu-id="3ca8a-444">**組織内およびフェデレーション組織のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="3ca8a-444">**Everyone in your organization and federated organizations**</span></span>     |<span data-ttu-id="3ca8a-445">ゲスト ユーザーやフェデレーション組織のユーザーなど、組織内の認証ユーザーは、ロビーで待たずに会議に直接参加します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-445">Authenticated users within the organization, including guest users and the users from federated organizations, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="3ca8a-446">匿名ユーザーおよびスマートフォンでダイヤル インするユーザーは、ロビーで待機します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-446">Anonymous users and users who dial in by phone wait in the lobby.</span></span>   |
|<span data-ttu-id="3ca8a-447">**組織内のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="3ca8a-447">**Everyone in your organization**</span></span>    |<span data-ttu-id="3ca8a-448">ゲスト ユーザーを含む組織内の認証ユーザーは、ロビーで待たずに会議に直接参加します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-448">Authenticated users from within the organization, including guest users, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="3ca8a-449">フェデレーション ユーザー、匿名ユーザー、およびスマートフォンでダイヤル インするユーザーは、ロビーで待機します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-449">Federated users, anonymous users, and users who dial in by phone wait in the lobby.</span></span>           |

### <a name="allow-dial-in-users-to-bypass-the-lobby"></a><span data-ttu-id="3ca8a-450">ダイヤルイン ユーザーによるロビーのバイパスを許可する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-450">Allow dial-in users to bypass the lobby</span></span>

<span data-ttu-id="3ca8a-451">これは開催者単位のポリシーです。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-451">This is a per-organizer policy.</span></span> <span data-ttu-id="3ca8a-452">この設定では、スマートフォンでダイヤル インするユーザーが会議に直接参加するのか、[**ユーザーの参加を自動的に許可する**] の設定に関わらずロビーで待機するのかを制御します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-452">This setting controls whether people who dial in by phone join the meeting directly or wait in the lobby regardless of the **Automatically admit people** setting.</span></span>

<span data-ttu-id="3ca8a-453">スマートフォンでダイヤル インするユーザーの参加動作は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-453">Here's the join behavior of people who dial in by phone.</span></span>

|<span data-ttu-id="3ca8a-454">ダイヤルイン ユーザーによるロビーのバイパスを許可する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-454">Allow dial-in users to bypass the lobby</span></span>  |<span data-ttu-id="3ca8a-455">ユーザーの参加を自動的に許可する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-455">Automatically admit people</span></span>  |<span data-ttu-id="3ca8a-456">ダイヤル インするユーザーの参加動作</span><span class="sxs-lookup"><span data-stu-id="3ca8a-456">Join behavior of people who dial in</span></span> |
|---------|---------|---------|
|<span data-ttu-id="3ca8a-457">True</span><span class="sxs-lookup"><span data-stu-id="3ca8a-457">True</span></span>    | <span data-ttu-id="3ca8a-458">すべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="3ca8a-458">Everyone</span></span>      | <span data-ttu-id="3ca8a-459">直接参加する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-459">Join directly</span></span>         |
|   | <span data-ttu-id="3ca8a-460">組織内のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="3ca8a-460">Everyone in your organization</span></span>       | <span data-ttu-id="3ca8a-461">直接参加する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-461">Join directly</span></span>        |
|   | <span data-ttu-id="3ca8a-462">組織内およびフェデレーション組織のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="3ca8a-462">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="3ca8a-463">直接参加する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-463">Join directly</span></span>         |
|<span data-ttu-id="3ca8a-464">False</span><span class="sxs-lookup"><span data-stu-id="3ca8a-464">False</span></span>    | <span data-ttu-id="3ca8a-465">すべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="3ca8a-465">Everyone</span></span>        | <span data-ttu-id="3ca8a-466">直接参加する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-466">Join directly</span></span>        |
|   | <span data-ttu-id="3ca8a-467">組織内のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="3ca8a-467">Everyone in your organization</span></span>     |<span data-ttu-id="3ca8a-468">ロビーで待つ</span><span class="sxs-lookup"><span data-stu-id="3ca8a-468">Wait in lobby</span></span>         |
|   | <span data-ttu-id="3ca8a-469">組織内およびフェデレーション組織のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="3ca8a-469">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="3ca8a-470">ロビーで待つ</span><span class="sxs-lookup"><span data-stu-id="3ca8a-470">Wait in lobby</span></span>         |

### <a name="allow-meet-now-in-private-meetings"></a><span data-ttu-id="3ca8a-471">プライベート会議で "今すぐ会議" を許可する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-471">Allow Meet now in private meetings</span></span>

<span data-ttu-id="3ca8a-472">これはユーザーごとのポリシーであり、会議が始まる前に適用されます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-472">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="3ca8a-473">この設定は、ユーザーがアドホック プライベート会議を開始できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-473">This setting controls whether a user can start an ad hoc private meeting.</span></span> 

### <a name="enable-live-captions"></a><span data-ttu-id="3ca8a-474">ライブ キャプションを有効にする</span><span class="sxs-lookup"><span data-stu-id="3ca8a-474">Enable live captions</span></span>

<span data-ttu-id="3ca8a-475">これはユーザーごとのポリシーであり、会議中に適用されます。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-475">This is a per-user policy and applies during a meeting.</span></span> <span data-ttu-id="3ca8a-476">この設定は、ユーザーが参加する会議でライブ キャプションを有効または無効にするために、[**ライブ キャプションを有効にする**] オプションを使用できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-476">This setting controls whether the **Turn on live captions** option is available for the user to turn on and turn off live captions in meetings that the user attends.</span></span>  

![[ライブ キャプションを有効にする] オプションが表示されたスクリーンショット](media/meeting-policies-live-captions.png)

|<span data-ttu-id="3ca8a-478">値を設定する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-478">Setting value</span></span> |<span data-ttu-id="3ca8a-479">動作</span><span class="sxs-lookup"><span data-stu-id="3ca8a-479">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="3ca8a-480">**無効になっているが、開催者が上書きできる**</span><span class="sxs-lookup"><span data-stu-id="3ca8a-480">**Disabled but the organizer can override**</span></span>     | <span data-ttu-id="3ca8a-481">会議中にユーザーのライブ キャプションが自動的に有効になることはありません。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-481">Live captions aren't automatically turned on for the user during a meeting.</span></span> <span data-ttu-id="3ca8a-482">オーバーフロー (**...**) メニューに [**ライブ キャプションを有効にする**] オプションが表示され、それらを有効にします。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-482">The user sees the **Turn on live captions** option in the overflow (**...**) menu to turn them on.</span></span> <span data-ttu-id="3ca8a-483">これは、既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-483">This is the default setting.</span></span> |
|<span data-ttu-id="3ca8a-484">**無効**</span><span class="sxs-lookup"><span data-stu-id="3ca8a-484">**Disabled**</span></span>     | <span data-ttu-id="3ca8a-485">会議中、ユーザーのライブ キャプションが無効になります。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-485">Live captions are disabled for the user during a meeting.</span></span> <span data-ttu-id="3ca8a-486">ユーザーには、それらを有効にするオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-486">The user doesn't have the option to turn them on.</span></span>          |

<span data-ttu-id="3ca8a-487"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="3ca8a-487"><a name="bkcontentsharing"> </a></span></span>

### <a name="allow-chat-in-meetings"></a><span data-ttu-id="3ca8a-488">会議でチャットを許可する</span><span class="sxs-lookup"><span data-stu-id="3ca8a-488">Allow chat in meetings</span></span>

<span data-ttu-id="3ca8a-489">これは開催者単位のポリシーです。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-489">This is a per-organizer policy.</span></span> <span data-ttu-id="3ca8a-490">この設定は、ユーザーの会議で会議チャットを許可するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-490">This setting controls whether meeting chat is allowed in the user's meeting.</span></span>

<span data-ttu-id="3ca8a-491"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="3ca8a-491"><a name="bkparticipantsandguests"> </a></span></span>

## <a name="related-topics"></a><span data-ttu-id="3ca8a-492">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ca8a-492">Related topics</span></span>

[<span data-ttu-id="3ca8a-493">Teams のメッセージング ポリシー</span><span class="sxs-lookup"><span data-stu-id="3ca8a-493">Messaging policies in Teams</span></span>](messaging-policies-in-teams.md)
