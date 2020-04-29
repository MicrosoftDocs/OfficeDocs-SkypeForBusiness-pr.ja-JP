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
- seo-marvel-apr2020
description: Teams で会議のポリシー設定を管理し、ユーザーによってスケジュールされた会議の参加者に対して利用できる機能を制御するために使用する方法について説明します。
ms.openlocfilehash: 689b22a98c986ca73ae3926785f75dcb6c6a9e74
ms.sourcegitcommit: 0835f4335ebc8ca53b8348e0b1b906828eb4e13e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2020
ms.locfileid: "43918706"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="dcffa-103">Teams での会議ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="dcffa-103">Manage meeting policies in Teams</span></span>

::: zone target="docs"
<span data-ttu-id="dcffa-104">会議ポリシーは、組織内のユーザーによってスケジュールされた会議への参加者が利用できる機能を制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-104">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="dcffa-105">ポリシーを作成して変更を行った後、ユーザーをポリシーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-105">After you create a policy and make your changes, you can then assign users to the policy.</span></span> <span data-ttu-id="dcffa-106">会議ポリシーは、Microsoft Teams 管理センターで管理するか、[PowerShell](teams-powershell-overview.md) を使用して管理します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-106">You manage meeting policies in the Microsoft Teams admin center or by using [PowerShell](teams-powershell-overview.md).</span></span>

<span data-ttu-id="dcffa-107">次の方法でポリシーを実装できます。これらの方法は、会議の開始前、会議中、または会議後のユーザーの会議エクスペリエンスに影響します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-107">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span>

|<span data-ttu-id="dcffa-108">実装の種類</span><span class="sxs-lookup"><span data-stu-id="dcffa-108">Implementation type</span></span>  |<span data-ttu-id="dcffa-109">説明</span><span class="sxs-lookup"><span data-stu-id="dcffa-109">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="dcffa-110">開催者単位</span><span class="sxs-lookup"><span data-stu-id="dcffa-110">Per-organizer</span></span>    |<span data-ttu-id="dcffa-111">開催者単位のポリシーを実装すると、すべての参加者は開催者のポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-111">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="dcffa-112">たとえば、[**ユーザーの参加を自動的に許可する**] は、開催者単位のポリシーであり、ユーザーが会議に直接参加するか、ポリシーが割り当てられたユーザーがスケジュールした会議をロビーで待機するかを制御します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-112">For example, **Automatically admit people** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="dcffa-113">ユーザーごと</span><span class="sxs-lookup"><span data-stu-id="dcffa-113">Per-user</span></span>    |<span data-ttu-id="dcffa-114">ユーザーごとのポリシーを実装すると、ユーザーごとのポリシーのみが適用され、開催者や会議参加者に対する特定の機能が制限されます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-114">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="dcffa-115">たとえば、[**チャネルで "今すぐ会議" を許可する**] は、ユーザー単位のポリシーです。</span><span class="sxs-lookup"><span data-stu-id="dcffa-115">For example, **Allow Meet now in channels** is a per-user policy.</span></span>     |
|<span data-ttu-id="dcffa-116">開催者単位およびユーザーごと</span><span class="sxs-lookup"><span data-stu-id="dcffa-116">Per-organizer and per-user</span></span>     |<span data-ttu-id="dcffa-117">開催者単位とユーザー単位のポリシーを組み合わせて実装すると、会議の参加者はユーザーのポリシーと開催者のポリシーに基づいて特定の機能が制限されます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-117">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="dcffa-118">たとえば、[**クラウド記録を許可する**] は、開催者単位およびユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="dcffa-118">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="dcffa-119">この設定をオンにすると、会議の開催者と参加者は記録の開始と停止が可能になります。</span><span class="sxs-lookup"><span data-stu-id="dcffa-119">Turn on this setting to allow the meeting organizer and participants to start and stop a recording.</span></span>

<span data-ttu-id="dcffa-120">既定では、グローバル (組織全体の既定値) という名前のポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-120">By default, a policy named Global (Org-wide default) is created.</span></span> <span data-ttu-id="dcffa-121">組織内のすべてのユーザーに、このグローバル会議ポリシーが既定で割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-121">All users in your organization are assigned the Global meeting policy by default.</span></span> <span data-ttu-id="dcffa-122">ポリシーを変更するか、1 つ以上のカスタム ポリシーを作成してユーザーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-122">You can either make changes to it or create one or more custom policies and assign users to them.</span></span> <span data-ttu-id="dcffa-123">カスタム ポリシーを作成して割り当てていない場合、ユーザーにはグローバル ポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-123">Users will get the Global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="dcffa-124">カスタム ポリシーを作成するときに、特定の機能をユーザーに対して使用可能または使用不可にして、そのポリシーを、適用する 1 人以上のユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-124">When you create a custom policy, you can allow or prevent certain features from being available to your users, and then assign it to one or more users who will have the settings applied to them.</span></span>
<span data-ttu-id="dcffa-125">-注-[会議の詳細] ボタンは、ユーザーが Audioconference ライセンスを有効にしているか、ユーザーが audioconference を許可している場合に go されます。それ以外の場合は、会議の詳細は go されません。</span><span class="sxs-lookup"><span data-stu-id="dcffa-125">-Note- Meeting details button will be availiable if a user has the audioconference licenses enabled or the user is allow for audioconferencing, if not, the meeting details will not be availiable</span></span>
## <a name="change-or-create-a-meeting-policy"></a><span data-ttu-id="dcffa-126">会議ポリシーを変更または作成する</span><span class="sxs-lookup"><span data-stu-id="dcffa-126">Change or create a meeting policy</span></span>

<span data-ttu-id="dcffa-127">会議ポリシーを変更または作成するには、Microsoft Teams 管理センターにアクセスし、[**会議**]  >  [**会議ポリシー**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-127">To change or create a meeting policy, go to the Microsoft Teams admin center > **Meetings** > **Meeting policies**.</span></span> <span data-ttu-id="dcffa-128">一覧からポリシーを選択するか、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-128">Select a policy from the list or select **Add**.</span></span> <span data-ttu-id="dcffa-129">新しいポリシーを作成する場合は、名前と説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-129">If you're creating a new policy, add a name and description.</span></span> <span data-ttu-id="dcffa-130">名前に特殊文字を含めたり、64 文字より長くすることはできません。</span><span class="sxs-lookup"><span data-stu-id="dcffa-130">The name can't contain special characters or be longer than 64 characters.</span></span> <span data-ttu-id="dcffa-131">設定を選び、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-131">Choose your settings, and then select **Save**.</span></span>

<span data-ttu-id="dcffa-132">たとえば、多数のユーザーがいて、会議に必要な帯域幅を制限するとします。</span><span class="sxs-lookup"><span data-stu-id="dcffa-132">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="dcffa-133">「制限された帯域幅」という名前の新しいカスタム ポリシーを作成し、次の設定を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-133">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="dcffa-134">[**オーディオとビデオ**] で、</span><span class="sxs-lookup"><span data-stu-id="dcffa-134">Under **Audio & video**:</span></span>
- <span data-ttu-id="dcffa-135">[クラウド記録を許可する] を無効にします。</span><span class="sxs-lookup"><span data-stu-id="dcffa-135">Turn off Allow cloud recording.</span></span>
- <span data-ttu-id="dcffa-136">[IP のビデオを許可する] を無効にします。</span><span class="sxs-lookup"><span data-stu-id="dcffa-136">Turn off Allow IP video.</span></span>

<span data-ttu-id="dcffa-137">[**コンテンツの共有**] で、</span><span class="sxs-lookup"><span data-stu-id="dcffa-137">Under **Content sharing**:</span></span>
- <span data-ttu-id="dcffa-138">画面共有モードを無効にします。</span><span class="sxs-lookup"><span data-stu-id="dcffa-138">Disable screen sharing mode.</span></span>
- <span data-ttu-id="dcffa-139">[ホワイトボードを許可] を無効にします。</span><span class="sxs-lookup"><span data-stu-id="dcffa-139">Turn off Allow whiteboard.</span></span>
- <span data-ttu-id="dcffa-140">[メモの共有を許可する] を無効にします。</span><span class="sxs-lookup"><span data-stu-id="dcffa-140">Turn off Allow shared notes.</span></span>

<span data-ttu-id="dcffa-141">その後、ポリシーをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-141">Then assign the policy to the users.</span></span>

> [!NOTE]
> <span data-ttu-id="dcffa-142">ユーザーに割り当てることができる会議ポリシーは一度に 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="dcffa-142">A user can be assigned only one meeting policy at a time.</span></span>

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="dcffa-143">ユーザーに会議ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="dcffa-143">Assign a meeting policy to users</span></span>

1. <span data-ttu-id="dcffa-144">Microsoft Teams 管理センターの左側のナビゲーションで、[**ユーザー**] に移動してユーザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="dcffa-144">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="dcffa-145">ユーザー名の左側をクリックしてユーザーを選択し、[**編集を設定する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dcffa-145">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="dcffa-146">[**会議ポリシー**] で割り当てるポリシーを選択し、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dcffa-146">Under **Meeting policy**, select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="dcffa-147">一度に複数のユーザーにポリシーを割り当てる方法については、「[一括でTeams のユーザー設定を編集する](edit-user-settings-in-bulk.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcffa-147">To assign a policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="dcffa-148">または、次の操作も実行できます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-148">Or, you can also do the following:</span></span>

1. <span data-ttu-id="dcffa-149">Microsoft Teams 管理センターの左側のナビゲーションで、[**会議**]  >  [**会議ポリシー**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-149">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="dcffa-150">ポリシー名の左側をクリックしてポリシーを選びます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-150">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="dcffa-151">[**ユーザーを管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-151">Select **Manage users**.</span></span>
4. <span data-ttu-id="dcffa-152">[**ユーザーを管理**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-152">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="dcffa-153">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-153">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="dcffa-154">ユーザーの追加が完了したら、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-154">After you finish adding users, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="dcffa-155">ユーザーが割り当てられているポリシーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="dcffa-155">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="dcffa-156">影響を受けるすべてのユーザーにまず異なるポリシーを割り当ててから、元のポリシーを削除できます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-156">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

## <a name="meeting-policy-settings"></a><span data-ttu-id="dcffa-157">会議ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="dcffa-157">Meeting policy settings</span></span>

<span data-ttu-id="dcffa-158">[**会議ポリシー**] ページで既存のポリシーを選択するか、新しいポリシーを追加するための [**追加**] を選択すると、次の設定内容を構成できます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-158">When you select an existing policy on the **Meeting policies** page or select **Add** to add a new policy, you can configure settings for the following.</span></span>

- [<span data-ttu-id="dcffa-159">全般</span><span class="sxs-lookup"><span data-stu-id="dcffa-159">General</span></span>](#meeting-policy-settings---general)
- [<span data-ttu-id="dcffa-160">オーディオとビデオ</span><span class="sxs-lookup"><span data-stu-id="dcffa-160">Audio & video</span></span>](#meeting-policy-settings---audio--video)
- [<span data-ttu-id="dcffa-161">コンテンツの共有</span><span class="sxs-lookup"><span data-stu-id="dcffa-161">Content sharing</span></span>](#meeting-policy-settings---content-sharing)
- [<span data-ttu-id="dcffa-162">参加者とゲスト</span><span class="sxs-lookup"><span data-stu-id="dcffa-162">Participants & guests</span></span>](#meeting-policy-settings---participants--guests)

::: zone-end 

<span data-ttu-id="dcffa-163"><a name="bkgeneral"> </a></span><span class="sxs-lookup"><span data-stu-id="dcffa-163"><a name="bkgeneral"> </a></span></span>

## <a name="meeting-policy-settings---general"></a><span data-ttu-id="dcffa-164">会議ポリシーの設定 - 全般</span><span class="sxs-lookup"><span data-stu-id="dcffa-164">Meeting policy settings - General</span></span>

- [<span data-ttu-id="dcffa-165">チャネルで "今すぐ会議" を許可する</span><span class="sxs-lookup"><span data-stu-id="dcffa-165">Allow Meet now in channels</span></span>](#allow-meet-now-in-channels)
- [<span data-ttu-id="dcffa-166">Outlook アドインを許可する</span><span class="sxs-lookup"><span data-stu-id="dcffa-166">Allow the Outlook add-in</span></span>](#allow-the-outlook-add-in)
- [<span data-ttu-id="dcffa-167">チャネルの会議スケジュールを許可する</span><span class="sxs-lookup"><span data-stu-id="dcffa-167">Allow channel meeting scheduling</span></span>](#allow-channel-meeting-scheduling)
- [<span data-ttu-id="dcffa-168">プライベート会議のスケジュールを許可する</span><span class="sxs-lookup"><span data-stu-id="dcffa-168">Allow scheduling private meetings</span></span>](#allow-scheduling-private-meetings)

### <a name="allow-meet-now-in-channels"></a><span data-ttu-id="dcffa-169">チャネルで "今すぐ会議" を許可する</span><span class="sxs-lookup"><span data-stu-id="dcffa-169">Allow Meet now in channels</span></span>

<span data-ttu-id="dcffa-170">これはユーザーごとのポリシーであり、会議が始まる前に適用されます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-170">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="dcffa-171">この設定は、ユーザーが Teams チャネルでアドホック会議を開始できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-171">This setting controls whether a user can start an ad hoc meeting in a Teams channel.</span></span> <span data-ttu-id="dcffa-172">これをオンにすると、ユーザーが Teams チャネルにメッセージを投稿するときに、ユーザーは作成ボックスの下の [**今すぐ会議**] をクリックして、チャネルでアドホック会議を開始できます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-172">If you turn this on, when a user posts a message in a Teams channel, the user can click **Meet now** under the compose box to start an ad hoc meeting in the channel.</span></span>

![メッセージの下の [今すぐ会議] アイコンが表示されたスクリーンショット](media/meeting-policies-meet-now.png)

### <a name="allow-the-outlook-add-in"></a><span data-ttu-id="dcffa-174">Outlook アドインを許可する</span><span class="sxs-lookup"><span data-stu-id="dcffa-174">Allow the Outlook add-in</span></span>

<span data-ttu-id="dcffa-175">これはユーザーごとのポリシーであり、会議が始まる前に適用されます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-175">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="dcffa-176">この設定は、Outlook (Windows、Mac、Web、およびモバイル) 内から Teams 会議をスケジュールできるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-176">This setting controls whether Teams meetings can be scheduled from within Outlook (Windows, Mac, web, and mobile).</span></span>

![新しい会議をスケジュールする機能が表示されたスクリーンショット](media/meeting-policies-outlook-add-in.png)

<span data-ttu-id="dcffa-178">これをオフにすると、ユーザーは Outlook で新しい会議を作成するときに Teams 会議をスケジュールできなくなります。</span><span class="sxs-lookup"><span data-stu-id="dcffa-178">If you turn this off, users are unable to schedule Teams meetings when they create a new meeting in Outlook.</span></span> <span data-ttu-id="dcffa-179">たとえば、Windows 上の Outlook では、[**新しい Teams 会議**] オプションはリボンに表示されません。</span><span class="sxs-lookup"><span data-stu-id="dcffa-179">For example, in Outlook on Windows, the **New Teams Meeting** option won't show up in the ribbon.</span></span>

### <a name="allow-channel-meeting-scheduling"></a><span data-ttu-id="dcffa-180">チャネルの会議スケジュールを許可する</span><span class="sxs-lookup"><span data-stu-id="dcffa-180">Allow channel meeting scheduling</span></span>

<span data-ttu-id="dcffa-181">これはユーザーごとのポリシーであり、会議が始まる前に適用されます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-181">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="dcffa-182">この設定は、ユーザーが Teams チャネルで会議をスケジュールできるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-182">This setting controls whether users can schedule a meeting in a Teams channel.</span></span>  <span data-ttu-id="dcffa-183">これをオフにすると、ユーザーは Teams チャネルで会議を開始するときに [**会議の予約**] オプションを使用できなくなり、Teams のユーザーに対して [**チャネルの追加**] オプションが無効になります。</span><span class="sxs-lookup"><span data-stu-id="dcffa-183">If you turn this off, the **Schedule a meeting** option won't be available to the user when they start a meeting in a Teams channel and the **Add channel** option is disabled for users in Teams.</span></span>

![Teams の [会議の予約] オプションが表示されたスクリーンショット](media/meeting-policies-schedule-a-meeting.png)

![[会議をするチャネルを選択] オプションが表示されたスクリーンショット](media/meeting-policies-select-a-channel-to-meet-in.png)

### <a name="allow-scheduling-private-meetings"></a><span data-ttu-id="dcffa-186">プライベート会議のスケジュールを許可する</span><span class="sxs-lookup"><span data-stu-id="dcffa-186">Allow scheduling private meetings</span></span>

<span data-ttu-id="dcffa-187">これはユーザーごとのポリシーであり、会議が始まる前に適用されます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-187">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="dcffa-188">この設定は、ユーザーが Teams でプライベート会議をスケジュールできるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-188">This setting controls whether users can schedule private meetings in Teams.</span></span> <span data-ttu-id="dcffa-189">チームのチャネルに公開されていない会議はプライベートです。</span><span class="sxs-lookup"><span data-stu-id="dcffa-189">A meeting is private when it's not published to a channel in a team.</span></span>

<span data-ttu-id="dcffa-190">[**プライベート会議のスケジュールを許可する**] および [**チャネルの会議スケジュールを許可する**] を無効にすると、Teams のユーザーに対して [**必須出席者の追加**] および [**チャネルの追加**] オプションが無効になります。</span><span class="sxs-lookup"><span data-stu-id="dcffa-190">Note that if you turn off **Allow scheduling private meetings** and **Allow channel meeting scheduling**,  the **Add required attendees** and **Add channel** options are disabled for users in Teams.</span></span>

<span data-ttu-id="dcffa-191"><a name="bkaudioandvideo"> </a></span><span class="sxs-lookup"><span data-stu-id="dcffa-191"><a name="bkaudioandvideo"> </a></span></span>

## <a name="meeting-policy-settings---audio--video"></a><span data-ttu-id="dcffa-192">会議ポリシーの設定 - オーディオとビデオ</span><span class="sxs-lookup"><span data-stu-id="dcffa-192">Meeting policy settings - Audio & video</span></span>

- [<span data-ttu-id="dcffa-193">文字起こしを許可する</span><span class="sxs-lookup"><span data-stu-id="dcffa-193">Allow transcription</span></span>](#allow-transcription)
- [<span data-ttu-id="dcffa-194">クラウド記録を許可する</span><span class="sxs-lookup"><span data-stu-id="dcffa-194">Allow cloud recording</span></span>](#allow-cloud-recording)
- [<span data-ttu-id="dcffa-195">IP のビデオを許可する</span><span class="sxs-lookup"><span data-stu-id="dcffa-195">Allow IP video</span></span>](#allow-ip-video)
- [<span data-ttu-id="dcffa-196">メディアのビットレート (Kps)</span><span class="sxs-lookup"><span data-stu-id="dcffa-196">Media bit rate (Kps)</span></span>](#media-bit-rate-kps)

### <a name="allow-transcription"></a><span data-ttu-id="dcffa-197">文字起こしを許可する</span><span class="sxs-lookup"><span data-stu-id="dcffa-197">Allow transcription</span></span>

<span data-ttu-id="dcffa-198">これは、開催者単位とユーザーごとのポリシーの組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="dcffa-198">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="dcffa-199">この設定は、会議の記録の再生中にキャプションと文字起こし機能を使用できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-199">This setting controls whether captions and transcription features are available during playback of meeting recordings.</span></span> <span data-ttu-id="dcffa-200">これをオフにすると、会議の記録の再生中に [**検索**] および [**CC**] オプションを使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="dcffa-200">If you turn this off, the **Search** and **CC** options won't be available during playback of a meeting recording.</span></span> <span data-ttu-id="dcffa-201">記録を開始したユーザーは、記録に文字起こしも含まれるように、この設定を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcffa-201">The person who started the recording needs this setting turned on so that the recording also includes transcription.</span></span> 

<span data-ttu-id="dcffa-202">記録された会議の文字起こしは、現在、Teams の言語が英語に設定されているユーザー、および会議で英語が話されている場合のユーザーに対してのみサポートされていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="dcffa-202">Note that transcription for recorded meetings is currently only supported for users who have the language in Teams set to English and when English is spoken in the meeting.</span></span>

![会議の文字起こしオプションが表示されたスクリーンショット](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a><span data-ttu-id="dcffa-204">クラウド記録を許可する</span><span class="sxs-lookup"><span data-stu-id="dcffa-204">Allow cloud recording</span></span>

<span data-ttu-id="dcffa-205">これは、開催者単位とユーザーごとのポリシーの組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="dcffa-205">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="dcffa-206">この設定は、このユーザーの会議を記録できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-206">This setting controls whether this user's meetings can be recorded.</span></span> <span data-ttu-id="dcffa-207">参加者のポリシー設定が有効になっており、同じ組織の認証済みユーザーである場合、会議の開催者または別の会議参加者が記録を開始できます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-207">The recording can be started by the meeting organizer or by another meeting participant if the policy setting is turned on for the participant and if they're an authenticated user from the same organization.</span></span>

<span data-ttu-id="dcffa-208">フェデレーション ユーザーや匿名ユーザーなど、組織外のユーザーは記録を開始できません。</span><span class="sxs-lookup"><span data-stu-id="dcffa-208">People outside your organization, such as federated and anonymous users, can't start the recording.</span></span> <span data-ttu-id="dcffa-209">ゲスト ユーザーは記録を開始または停止できません。</span><span class="sxs-lookup"><span data-stu-id="dcffa-209">Guest users can't start or stop the recording.</span></span> 

![記録オプションが表示されたスクリーンショット](media/meeting-policies-recording.png)

<span data-ttu-id="dcffa-211">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="dcffa-211">Let's look at the following example.</span></span>

|<span data-ttu-id="dcffa-212">ユーザー</span><span class="sxs-lookup"><span data-stu-id="dcffa-212">User</span></span> |<span data-ttu-id="dcffa-213">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="dcffa-213">Meeting policy</span></span>  |<span data-ttu-id="dcffa-214">クラウド記録を許可する</span><span class="sxs-lookup"><span data-stu-id="dcffa-214">Allow cloud recording</span></span> |
|---------|---------|---------|
|<span data-ttu-id="dcffa-215">Daniela</span><span class="sxs-lookup"><span data-stu-id="dcffa-215">Daniela</span></span> | <span data-ttu-id="dcffa-216">グローバル</span><span class="sxs-lookup"><span data-stu-id="dcffa-216">Global</span></span>   | <span data-ttu-id="dcffa-217">False</span><span class="sxs-lookup"><span data-stu-id="dcffa-217">False</span></span> |
|<span data-ttu-id="dcffa-218">Amanda</span><span class="sxs-lookup"><span data-stu-id="dcffa-218">Amanda</span></span> | <span data-ttu-id="dcffa-219">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="dcffa-219">Location1MeetingPolicy</span></span> | <span data-ttu-id="dcffa-220">True</span><span class="sxs-lookup"><span data-stu-id="dcffa-220">True</span></span>|
|<span data-ttu-id="dcffa-221">John (外部ユーザー)</span><span class="sxs-lookup"><span data-stu-id="dcffa-221">John (external user)</span></span> | <span data-ttu-id="dcffa-222">該当なし</span><span class="sxs-lookup"><span data-stu-id="dcffa-222">Not applicable</span></span> | <span data-ttu-id="dcffa-223">該当なし</span><span class="sxs-lookup"><span data-stu-id="dcffa-223">Not applicable</span></span>|

<span data-ttu-id="dcffa-224">Daniela が開催する会議は記録されず、ポリシー設定が有効になっている Amanda は Daniela が開催する会議を記録できません。</span><span class="sxs-lookup"><span data-stu-id="dcffa-224">Meetings organized by Daniela can't be recorded and Amanda, who has the policy setting enabled, can't record meetings organized by Daniela.</span></span> <span data-ttu-id="dcffa-225">Amanda が開催する会議は記録できますが、ポリシー設定が無効になっている Daniela と外部ユーザーである John は、Amanda が開催する会議を記録できません。</span><span class="sxs-lookup"><span data-stu-id="dcffa-225">Meetings organized by Amanda can be recorded, however,  Daniela, who has the policy setting disabled and John who is an external user, can't record meetings organized by Amanda.</span></span>

<span data-ttu-id="dcffa-226">クラウド会議の記録の詳細については、「[Teams のクラウド会議の記録](cloud-recording.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcffa-226">To learn more about cloud meeting recording, see [Teams cloud meeting recording](cloud-recording.md).</span></span>

### <a name="allow-ip-video"></a><span data-ttu-id="dcffa-227">IP ビデオを許可する</span><span class="sxs-lookup"><span data-stu-id="dcffa-227">Allow IP video</span></span>

<span data-ttu-id="dcffa-228">これは、開催者単位とユーザーごとのポリシーの組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="dcffa-228">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="dcffa-229">ビデオは、会議の重要な構成要素です。</span><span class="sxs-lookup"><span data-stu-id="dcffa-229">Video is a key component to meetings.</span></span> <span data-ttu-id="dcffa-230">一部の組織では、管理者がビデオを使用するユーザーの会議をさらに制御する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="dcffa-230">In some organizations, admins might want more control over which users' meetings have video.</span></span> <span data-ttu-id="dcffa-231">この設定は、ユーザーがホストする会議、およびユーザーが開始する 1:1 通話やグループ通話でビデオを有効にできるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-231">This setting controls whether video can be turned on in meetings hosted by a user and in 1:1 calls and group calls started by a user.</span></span> <span data-ttu-id="dcffa-232">このポリシーを有効にしたユーザーが開催する会議では、会議の参加者もポリシーを有効にしている場合に、会議の参加者による会議でのビデオ共有が許可されます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-232">Meetings organized by a user who has this policy enabled, allow video sharing in the meeting by the meeting participants, if the meeting participants also have the policy enabled.</span></span> <span data-ttu-id="dcffa-233">ポリシーが割り当てられていない会議参加者 (匿名参加者やフェデレーション参加者など) は、会議開催者のポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-233">Meeting participants who don't have any policies assigned (for example, anonymous and federated participants) inherit the policy of the meeting organizer.</span></span>

![オーディオとビデオの設定を含む会議が表示されたスクリーンショット](media/meeting-policies-audio-video-settings.png)

<span data-ttu-id="dcffa-235">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="dcffa-235">Let's look at the following example.</span></span>

|<span data-ttu-id="dcffa-236">ユーザー</span><span class="sxs-lookup"><span data-stu-id="dcffa-236">User</span></span> |<span data-ttu-id="dcffa-237">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="dcffa-237">Meeting policy</span></span>  |<span data-ttu-id="dcffa-238">IP ビデオを許可する</span><span class="sxs-lookup"><span data-stu-id="dcffa-238">Allow IP Video</span></span> |
|---------|---------|---------|
|<span data-ttu-id="dcffa-239">Daniela</span><span class="sxs-lookup"><span data-stu-id="dcffa-239">Daniela</span></span>   | <span data-ttu-id="dcffa-240">グローバル</span><span class="sxs-lookup"><span data-stu-id="dcffa-240">Global</span></span>   | <span data-ttu-id="dcffa-241">True</span><span class="sxs-lookup"><span data-stu-id="dcffa-241">True</span></span>        |
|<span data-ttu-id="dcffa-242">Amanda</span><span class="sxs-lookup"><span data-stu-id="dcffa-242">Amanda</span></span>    | <span data-ttu-id="dcffa-243">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="dcffa-243">Location1MeetingPolicy</span></span>        | <span data-ttu-id="dcffa-244">False</span><span class="sxs-lookup"><span data-stu-id="dcffa-244">False</span></span>      |

<span data-ttu-id="dcffa-245">Daniela が開催する会議では、ビデオを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-245">Meetings hosted by Daniela allow video to be turned on.</span></span> <span data-ttu-id="dcffa-246">Daniela は会議に参加してビデオを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-246">Daniela can join the meeting and turn on video.</span></span> <span data-ttu-id="dcffa-247">Amanda のポリシーが [ビデオを許可しない] に設定されているため、Amanda は Daniela の会議でビデオを有効にできません。</span><span class="sxs-lookup"><span data-stu-id="dcffa-247">Amanda can't turn on video in Daniela's meeting because Amanda's policy is set to not allow video.</span></span> <span data-ttu-id="dcffa-248">Amanda は、会議の他の参加者が共有しているビデオを見ることができます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-248">Amanda can see videos shared by other participants in the meeting.</span></span>

<span data-ttu-id="dcffa-249">Amanda が主催する会議では、割り当てられたビデオ ポリシーに関係なく、誰もビデオを有効にできません。</span><span class="sxs-lookup"><span data-stu-id="dcffa-249">In meetings hosted by Amanda, no one can turn on video, regardless of the video policy assigned to them.</span></span> <span data-ttu-id="dcffa-250">これは、Daniela Amanda の会議でビデオを有効にできないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-250">This means Daniela can't turn on video in Amanda's meetings.</span></span>  

<span data-ttu-id="dcffa-251">Daniela がビデオを有効にして Amanda に電話した場合、Amanda はオーディオのみで電話に出ることができます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-251">If Daniela calls Amanda with video on, Amanda can answer the call with audio only.</span></span>  <span data-ttu-id="dcffa-252">通話が接続されている場合、Amanda は Daniela のビデオを見ることはできますが、ビデオを有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="dcffa-252">When the call is connected, Amanda can see Daniela's video, but can't turn on video.</span></span> <span data-ttu-id="dcffa-253">Amanda が Daniela に電話すると、Daniela はビデオとオーディオで電話に出ることができます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-253">If Amanda calls Daniela, Daniela can answer the call with video and audio.</span></span> <span data-ttu-id="dcffa-254">通話が接続されると、Daniela は必要に応じてビデオを有効または無効にできます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-254">When the call is connected, Daniela can turn on or turn off her video, as needed.</span></span>

### <a name="media-bit-rate-kps"></a><span data-ttu-id="dcffa-255">メディアのビットレート (Kps)</span><span class="sxs-lookup"><span data-stu-id="dcffa-255">Media bit rate (Kps)</span></span>

<span data-ttu-id="dcffa-256">これは、ユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="dcffa-256">This is a per-user policy.</span></span> <span data-ttu-id="dcffa-257">この設定により、ユーザーの通話および会議でのオーディオ、ビデオ、およびビデオベースのアプリ共有送信のメディア ビット レートが決まります。</span><span class="sxs-lookup"><span data-stu-id="dcffa-257">This setting determines the media bit rate for audio, video, and video-based app sharing transmissions in calls and meetings for the user.</span></span> <span data-ttu-id="dcffa-258">通話または会議のユーザーのアップリンクとダウンリンクの両方のメディア トラバーサルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-258">It's applied to both the uplink and downlink media traversal for users in the call or meeting.</span></span> <span data-ttu-id="dcffa-259">この設定により、組織の帯域幅の管理をきめ細やかに制御できます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-259">This setting gives you granular control over managing bandwidth in your organization.</span></span> <span data-ttu-id="dcffa-260">ユーザーが必要とする会議シナリオに応じて、高品質のエクスペリエンスを得るために十分な帯域幅を用意することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dcffa-260">Depending on the meetings scenarios required by users, we recommend having enough bandwidth in place for a good quality experience.</span></span> <span data-ttu-id="dcffa-261">最小値は 30 Kps で、最大値は会議シナリオによって異なります。</span><span class="sxs-lookup"><span data-stu-id="dcffa-261">The minimum value is 30 Kps and the maximum value depends on the meeting scenario.</span></span> <span data-ttu-id="dcffa-262">Teams での高品質の会議、通話、およびライブ イベントを実現する最小推奨帯域幅の詳細については、「[帯域幅要件](prepare-network.md#bandwidth-requirements)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcffa-262">To learn more about the minimum recommended bandwidth for good quality meetings, calls, and live events in Teams, see [Bandwidth requirements](prepare-network.md#bandwidth-requirements).</span></span>

<span data-ttu-id="dcffa-263">会議に十分な帯域幅がない場合、参加者には、ネットワークの品質低下を示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-263">If there isn't enough bandwidth for a meeting, participants see a message that indicates poor network quality.</span></span>

<span data-ttu-id="dcffa-264">CEO ボード会議や Teams のライブ イベントなど、最高品質のビデオ エクスペリエンスを必要とする会議では、帯域幅を 10 Mbps に設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dcffa-264">For meetings that need the highest quality video experience, such as CEO board meetings and Teams live events, we recommend you set the bandwidth to 10 Mbps.</span></span> <span data-ttu-id="dcffa-265">最大限のエクスペリエンスが設定されている場合でも、特定のネットワーク条件が検出されると、シナリオに応じて、Teams メディア スタックは低帯域幅の条件に適応します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-265">Even when the maximum experience is set, the Teams media stack adapts to low bandwidth conditions when certain network conditions are detected, depending on the scenario.</span></span> 

## <a name="meeting-policy-settings---content-sharing"></a><span data-ttu-id="dcffa-266">会議ポリシーの設定 - コンテンツの共有</span><span class="sxs-lookup"><span data-stu-id="dcffa-266">Meeting policy settings - Content sharing</span></span>

- [<span data-ttu-id="dcffa-267">画面共有モード</span><span class="sxs-lookup"><span data-stu-id="dcffa-267">Screen sharing mode</span></span>](#screen-sharing-mode)
- [<span data-ttu-id="dcffa-268">参加者に制御を渡す、または制御を要求する</span><span class="sxs-lookup"><span data-stu-id="dcffa-268">Allow a participant to give or request control</span></span>](#allow-a-participant-to-give-or-request-control)
- [<span data-ttu-id="dcffa-269">外部の参加者に制御を渡す、または制御を要求する</span><span class="sxs-lookup"><span data-stu-id="dcffa-269">Allow an external participant to give or request control</span></span>](#allow-an-external-participant-to-give-or-request-control)
- [<span data-ttu-id="dcffa-270">PowerPoint の共有を許可する</span><span class="sxs-lookup"><span data-stu-id="dcffa-270">Allow PowerPoint sharing</span></span>](#allow-powerpoint-sharing)
- [<span data-ttu-id="dcffa-271">ホワイトボードを許可する</span><span class="sxs-lookup"><span data-stu-id="dcffa-271">Allow whiteboard</span></span>](#allow-whiteboard)
- [<span data-ttu-id="dcffa-272">メモの共有を許可する</span><span class="sxs-lookup"><span data-stu-id="dcffa-272">Allow shared notes</span></span>](#allow-shared-notes)

### <a name="screen-sharing-mode"></a><span data-ttu-id="dcffa-273">画面共有モード</span><span class="sxs-lookup"><span data-stu-id="dcffa-273">Screen sharing mode</span></span>

<span data-ttu-id="dcffa-274">これは、開催者単位とユーザーごとのポリシーの組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="dcffa-274">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="dcffa-275">この設定は、ユーザーの会議でデスクトップやウィンドウの共有を許可するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-275">This setting controls whether desktop and/or window sharing is allowed in the user's meeting.</span></span> <span data-ttu-id="dcffa-276">ポリシーが割り当てられていない会議参加者 (匿名参加者、ゲスト参加者、B2B 参加者、フェデレーション参加者など) は、会議開催者のポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-276">Meeting participants who don't have any policies assigned (for example, anonymous, guest, B2B, and federated participants) inherit the policy of the meeting organizer.</span></span>

|<span data-ttu-id="dcffa-277">値を設定する</span><span class="sxs-lookup"><span data-stu-id="dcffa-277">Setting value</span></span> |<span data-ttu-id="dcffa-278">動作</span><span class="sxs-lookup"><span data-stu-id="dcffa-278">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="dcffa-279">**画面全体**</span><span class="sxs-lookup"><span data-stu-id="dcffa-279">**Entire screen**</span></span>    | <span data-ttu-id="dcffa-280">会議では完全なデスクトップ共有とアプリケーション共有が許可されます</span><span class="sxs-lookup"><span data-stu-id="dcffa-280">Full desktop sharing and application sharing is allowed in the meeting</span></span> |
|<span data-ttu-id="dcffa-281">**単一アプリケーション**</span><span class="sxs-lookup"><span data-stu-id="dcffa-281">**Single application**</span></span>   | <span data-ttu-id="dcffa-282">会議ではアプリケーションの共有が許可されます</span><span class="sxs-lookup"><span data-stu-id="dcffa-282">Application sharing is allowed in the meeting</span></span>        |
|<span data-ttu-id="dcffa-283">**無効**</span><span class="sxs-lookup"><span data-stu-id="dcffa-283">**Disabled**</span></span>     |<span data-ttu-id="dcffa-284">会議では画面共有とアプリケーション共有が無効になります。</span><span class="sxs-lookup"><span data-stu-id="dcffa-284">Screen sharing and application sharing turned off in the meeting.</span></span>       |

<span data-ttu-id="dcffa-285">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="dcffa-285">Let's look at the following example.</span></span>

|<span data-ttu-id="dcffa-286">ユーザー</span><span class="sxs-lookup"><span data-stu-id="dcffa-286">User</span></span> |<span data-ttu-id="dcffa-287">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="dcffa-287">Meeting policy</span></span> |<span data-ttu-id="dcffa-288">画面共有モード</span><span class="sxs-lookup"><span data-stu-id="dcffa-288">Screen sharing mode</span></span> |
|---------|---------|---------|
|<span data-ttu-id="dcffa-289">Daniela</span><span class="sxs-lookup"><span data-stu-id="dcffa-289">Daniela</span></span>  | <span data-ttu-id="dcffa-290">グローバル</span><span class="sxs-lookup"><span data-stu-id="dcffa-290">Global</span></span>   | <span data-ttu-id="dcffa-291">画面全体</span><span class="sxs-lookup"><span data-stu-id="dcffa-291">Entire screen</span></span> |
|<span data-ttu-id="dcffa-292">Amanda</span><span class="sxs-lookup"><span data-stu-id="dcffa-292">Amanda</span></span>   | <span data-ttu-id="dcffa-293">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="dcffa-293">Location1MeetingPolicy</span></span>  | <span data-ttu-id="dcffa-294">無効</span><span class="sxs-lookup"><span data-stu-id="dcffa-294">Disabled</span></span> |

<span data-ttu-id="dcffa-295">Daniela が開催する会議では、会議の参加者が画面全体または特定のアプリケーションを共有できます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-295">Meetings hosted by Daniela allow meeting participants to share their entire screen or a specific application.</span></span> <span data-ttu-id="dcffa-296">Amanda が Daniela の会議に参加している場合は、そのポリシー設定が無効になっているために、Amanda が自分の画面や特定のアプリケーションを共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="dcffa-296">If Amanda joins Daniela's meeting, Amanda can't share her screen or a specific application as her policy setting is disabled.</span></span> <span data-ttu-id="dcffa-297">Amanda がホストする会議では、割り当てられた画面共有モード ポリシーに関係なく、誰も画面または単一のアプリケーションを共有できません。</span><span class="sxs-lookup"><span data-stu-id="dcffa-297">In meetings hosted by Amanda, no one is allowed to share their screen or a single application, regardless of the screen sharing mode policy assigned to them.</span></span> <span data-ttu-id="dcffa-298">これは、Daniela が Amanda の会議で、画面や単一のアプリケーションを共有できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-298">This means that Daniela can't share her screen or a single application in Amanda's meetings.</span></span>  

<span data-ttu-id="dcffa-299">現在、ユーザーは Google Chrome を使用している場合、Teams 会議でビデオを再生したり画面を共有したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="dcffa-299">Currently, users can't play video or share their screen in a Teams meeting if they're using Google Chrome.</span></span>

### <a name="allow-a-participant-to-give-or-request-control"></a><span data-ttu-id="dcffa-300">参加者に制御を渡す、または制御を要求する</span><span class="sxs-lookup"><span data-stu-id="dcffa-300">Allow a participant to give or request control</span></span>

<span data-ttu-id="dcffa-301">これは、ユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="dcffa-301">This is a per-user policy.</span></span> <span data-ttu-id="dcffa-302">この設定は、ユーザーが他の会議参加者に共有デスクトップまたはウィンドウの制御を渡すことができるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-302">This setting controls whether the user can give control of the shared desktop or window to other meeting participants.</span></span> <span data-ttu-id="dcffa-303">制御を渡すには、画面の上部にカーソルを合わせます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-303">To give control, hover over the top of the screen.</span></span> 

<span data-ttu-id="dcffa-304">ユーザーに対してこの設定が有効になっている場合、共有セッションの上部のバーに [**制御を渡す**] オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-304">If this setting is turned on for the user, the **Give Control** option is displayed in the top bar in a sharing session.</span></span> 

![[制御を渡す] オプションが表示されたスクリーンショット](media/meeting-policies-give-control.png)

<span data-ttu-id="dcffa-306">ユーザーの設定が無効になっている場合、[**制御を渡す**] オプションは使用できません。</span><span class="sxs-lookup"><span data-stu-id="dcffa-306">If the settings is turned off for the user, the **Give Control** option isn't available.</span></span>

![[制御を渡す] オプションが利用できないことを示すスクリーンショット](media/meeting-policies-give-control-not-available.png)

<span data-ttu-id="dcffa-308">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="dcffa-308">Let's look at the following example.</span></span>

|<span data-ttu-id="dcffa-309">ユーザー</span><span class="sxs-lookup"><span data-stu-id="dcffa-309">User</span></span> |<span data-ttu-id="dcffa-310">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="dcffa-310">Meeting policy</span></span>  |<span data-ttu-id="dcffa-311">参加者に制御を渡す、または制御を要求する</span><span class="sxs-lookup"><span data-stu-id="dcffa-311">Allow participant to give or request control</span></span> |
|---------|---------|---------|
|<span data-ttu-id="dcffa-312">Daniela</span><span class="sxs-lookup"><span data-stu-id="dcffa-312">Daniela</span></span>   | <span data-ttu-id="dcffa-313">グローバル</span><span class="sxs-lookup"><span data-stu-id="dcffa-313">Global</span></span>   | <span data-ttu-id="dcffa-314">True</span><span class="sxs-lookup"><span data-stu-id="dcffa-314">True</span></span>       |
|<span data-ttu-id="dcffa-315">Babek</span><span class="sxs-lookup"><span data-stu-id="dcffa-315">Babek</span></span>    | <span data-ttu-id="dcffa-316">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="dcffa-316">Location1MeetingPolicy</span></span>        | <span data-ttu-id="dcffa-317">False</span><span class="sxs-lookup"><span data-stu-id="dcffa-317">False</span></span>   |

<span data-ttu-id="dcffa-318">Daniela は、Babek が開催する会議の他の参加者に共有デスクトップまたはウィンドウの制御を渡すことができますが、Babek は他の参加者に制御を渡すことができません。</span><span class="sxs-lookup"><span data-stu-id="dcffa-318">Daniela can give control of the shared desktop or window to other participants in a meeting organized by Babek whereas Babek can't give control to other participants.</span></span>

<span data-ttu-id="dcffa-319">制御を渡したり、制御要求を受け入れたりすることができるユーザーを PowerShell を使用して制御するには、AllowParticipantGiveRequestControl コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-319">To use PowerShell to control who can give control or accept requests for control, use the AllowParticipantGiveRequestControl cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="dcffa-320">共有中に共有コンテンツの制御を渡したり受け取ったりするには、両者が Teams デスクトップ クライアントを使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcffa-320">To give and take control of shared content during sharing, both parties must be using the Teams desktop client.</span></span> <span data-ttu-id="dcffa-321">いずれかの当事者がブラウザーで Teams を実行している場合、制御はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="dcffa-321">Control isn't supported when either party is running Teams in a browser.</span></span> <span data-ttu-id="dcffa-322">これは、修正する予定の技術的制限によるものです。</span><span class="sxs-lookup"><span data-stu-id="dcffa-322">This is due to a technical limitation that we're planning to fix.</span></span> 

### <a name="allow-an-external-participant-to-give-or-request-control"></a><span data-ttu-id="dcffa-323">外部の参加者に制御を渡す、または制御を要求する</span><span class="sxs-lookup"><span data-stu-id="dcffa-323">Allow an external participant to give or request control</span></span>

<span data-ttu-id="dcffa-324">これは、ユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="dcffa-324">This is a per-user policy.</span></span> <span data-ttu-id="dcffa-325">この設定は、会議の外部参加者が共有デスクトップまたはウィンドウの制御を他の会議参加者に渡すことができるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-325">This setting controls whether external participants in a meeting can give control of their shared desktop or window to other participants in the meeting.</span></span> <span data-ttu-id="dcffa-326">Teams 会議の外部参加者は、次のように分類できます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-326">External participants in Teams meetings can be categorized as follows:</span></span>  

- <span data-ttu-id="dcffa-327">匿名ユーザー</span><span class="sxs-lookup"><span data-stu-id="dcffa-327">Anonymous user</span></span>
- <span data-ttu-id="dcffa-328">ゲスト ユーザー</span><span class="sxs-lookup"><span data-stu-id="dcffa-328">Guest users</span></span>  
- <span data-ttu-id="dcffa-329">B2B ユーザー</span><span class="sxs-lookup"><span data-stu-id="dcffa-329">B2B user</span></span>
- <span data-ttu-id="dcffa-330">フェデレーション ユーザー</span><span class="sxs-lookup"><span data-stu-id="dcffa-330">Federated user</span></span>  

<span data-ttu-id="dcffa-331">フェデレーション ユーザーが共有中に外部ユーザーに制御を渡すことができるかどうかは、組織の「**外部の参加者に制御を渡す、または制御を要求する**」設定によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-331">Whether federated users can give control to external users while sharing is controlled by the **Allow an external participant to give or request control** setting in their organization.</span></span>

<span data-ttu-id="dcffa-332">PowerShell を使用して、外部の参加者が制御を渡すことができるか、または制御要求を受け入れることができるかを制御するには、AllowExternalParticipantGiveRequestControl コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-332">To use PowerShell to control whether external participants can give control or accept requests for control, use the AllowExternalParticipantGiveRequestControl cmdlet.</span></span>

### <a name="allow-powerpoint-sharing"></a><span data-ttu-id="dcffa-333">PowerPoint の共有を許可する</span><span class="sxs-lookup"><span data-stu-id="dcffa-333">Allow PowerPoint sharing</span></span>

<span data-ttu-id="dcffa-334">これは、ユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="dcffa-334">This is a per-user policy.</span></span> <span data-ttu-id="dcffa-335">この設定は、ユーザーが会議で PowerPoint スライド セットを共有できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-335">This setting controls whether the user can share PowerPoint slide decks in a meeting.</span></span> <span data-ttu-id="dcffa-336">匿名ユーザー、ゲスト ユーザー、フェデレーション ユーザーを含む外部ユーザーは、会議開催者のポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-336">External users, including anonymous, guest, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="dcffa-337">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="dcffa-337">Let's look at the following example.</span></span>

|<span data-ttu-id="dcffa-338">ユーザー</span><span class="sxs-lookup"><span data-stu-id="dcffa-338">User</span></span> |<span data-ttu-id="dcffa-339">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="dcffa-339">Meeting policy</span></span>  |<span data-ttu-id="dcffa-340">PowerPoint の共有を許可する</span><span class="sxs-lookup"><span data-stu-id="dcffa-340">Allow PowerPoint sharing</span></span> |
|---------|---------|---------|
|<span data-ttu-id="dcffa-341">Daniela</span><span class="sxs-lookup"><span data-stu-id="dcffa-341">Daniela</span></span>   | <span data-ttu-id="dcffa-342">グローバル</span><span class="sxs-lookup"><span data-stu-id="dcffa-342">Global</span></span>   | <span data-ttu-id="dcffa-343">True</span><span class="sxs-lookup"><span data-stu-id="dcffa-343">True</span></span>       |
|<span data-ttu-id="dcffa-344">Amanda</span><span class="sxs-lookup"><span data-stu-id="dcffa-344">Amanda</span></span>   | <span data-ttu-id="dcffa-345">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="dcffa-345">Location1MeetingPolicy</span></span>        | <span data-ttu-id="dcffa-346">False</span><span class="sxs-lookup"><span data-stu-id="dcffa-346">False</span></span>   |

<span data-ttu-id="dcffa-347">Amanda は、会議の開催者であっても、PowerPoint スライド セットを会議で共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="dcffa-347">Amanda can't share PowerPoint slide decks in meetings even if she's the meeting organizer.</span></span> <span data-ttu-id="dcffa-348">Daniela は、会議が Amanda によって開催されている場合でも、PowerPoint スライド セットを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-348">Daniela can share PowerPoint slide decks even if the meeting is organized by Amanda.</span></span> <span data-ttu-id="dcffa-349">Amanda は、PowerPoint スライド セットを共有できない場合でも、会議の他のユーザーによって共有されている PowerPoint スライド セットを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-349">Amanda can view the PowerPoint slide decks shared by others in the meeting, even though she can't share PowerPoint slide decks.</span></span>

### <a name="allow-whiteboard"></a><span data-ttu-id="dcffa-350">ホワイトボードを許可する</span><span class="sxs-lookup"><span data-stu-id="dcffa-350">Allow whiteboard</span></span>

<span data-ttu-id="dcffa-351">これは、ユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="dcffa-351">This is a per-user policy.</span></span> <span data-ttu-id="dcffa-352">この設定は、ユーザーが会議でホワイトボードを共有できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-352">This setting controls whether a user can share the whiteboard in a meeting.</span></span> <span data-ttu-id="dcffa-353">匿名ユーザー、B2B ユーザー、およびフェデレーション ユーザーを含む外部ユーザーは、会議開催者のポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-353">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> 

<span data-ttu-id="dcffa-354">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="dcffa-354">Let's look at the following example.</span></span>

|<span data-ttu-id="dcffa-355">ユーザー</span><span class="sxs-lookup"><span data-stu-id="dcffa-355">User</span></span> |<span data-ttu-id="dcffa-356">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="dcffa-356">Meeting policy</span></span>  |<span data-ttu-id="dcffa-357">ホワイトボードを許可する</span><span class="sxs-lookup"><span data-stu-id="dcffa-357">Allow whiteboard</span></span>|
|---------|---------|---------|
|<span data-ttu-id="dcffa-358">Daniela</span><span class="sxs-lookup"><span data-stu-id="dcffa-358">Daniela</span></span>   | <span data-ttu-id="dcffa-359">グローバル</span><span class="sxs-lookup"><span data-stu-id="dcffa-359">Global</span></span>   | <span data-ttu-id="dcffa-360">True</span><span class="sxs-lookup"><span data-stu-id="dcffa-360">True</span></span>       |
|<span data-ttu-id="dcffa-361">Amanda</span><span class="sxs-lookup"><span data-stu-id="dcffa-361">Amanda</span></span>   | <span data-ttu-id="dcffa-362">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="dcffa-362">Location1MeetingPolicy</span></span>        | <span data-ttu-id="dcffa-363">False</span><span class="sxs-lookup"><span data-stu-id="dcffa-363">False</span></span>   |

<span data-ttu-id="dcffa-364">Amanda は、会議の開催者であっても、会議でホワイトボードを共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="dcffa-364">Amanda can't share the whiteboard in a meeting even if she's the meeting organizer.</span></span> <span data-ttu-id="dcffa-365">Daniela は、Amanda が会議を開催する場合でも、ホワイトボードを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-365">Daniela can share the whiteboard even if a meeting is organized by Amanda.</span></span>  

### <a name="allow-shared-notes"></a><span data-ttu-id="dcffa-366">メモの共有を許可する</span><span class="sxs-lookup"><span data-stu-id="dcffa-366">Allow shared notes</span></span>

<span data-ttu-id="dcffa-367">これは、ユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="dcffa-367">This is a per-user policy.</span></span> <span data-ttu-id="dcffa-368">この設定は、ユーザーが会議でメモを作成および共有できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-368">This setting controls whether a user can create and share notes in a meeting.</span></span> <span data-ttu-id="dcffa-369">匿名ユーザー、B2B ユーザー、およびフェデレーション ユーザーを含む外部ユーザーは、会議開催者のポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-369">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> <span data-ttu-id="dcffa-370">現在、[**会議メモ**] タブは、参加者が 20 人未満の会議でのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="dcffa-370">The **Meeting Notes** tab is currently only supported in meetings that have less than 20 participants.</span></span>

<span data-ttu-id="dcffa-371">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="dcffa-371">Let's look at the following example.</span></span>

|<span data-ttu-id="dcffa-372">ユーザー</span><span class="sxs-lookup"><span data-stu-id="dcffa-372">User</span></span> |<span data-ttu-id="dcffa-373">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="dcffa-373">Meeting policy</span></span>  |<span data-ttu-id="dcffa-374">メモの共有を許可する</span><span class="sxs-lookup"><span data-stu-id="dcffa-374">Allow shared notes</span></span> |
|---------|---------|---------|
|<span data-ttu-id="dcffa-375">Daniela</span><span class="sxs-lookup"><span data-stu-id="dcffa-375">Daniela</span></span>   | <span data-ttu-id="dcffa-376">グローバル</span><span class="sxs-lookup"><span data-stu-id="dcffa-376">Global</span></span>   | <span data-ttu-id="dcffa-377">True</span><span class="sxs-lookup"><span data-stu-id="dcffa-377">True</span></span>       |
|<span data-ttu-id="dcffa-378">Amanda</span><span class="sxs-lookup"><span data-stu-id="dcffa-378">Amanda</span></span>   | <span data-ttu-id="dcffa-379">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="dcffa-379">Location1MeetingPolicy</span></span> | <span data-ttu-id="dcffa-380">False</span><span class="sxs-lookup"><span data-stu-id="dcffa-380">False</span></span> |

<span data-ttu-id="dcffa-381">Daniela は Amanda の会議でメモを取ることができ、Amanda はすべての会議でメモを取ることができません。</span><span class="sxs-lookup"><span data-stu-id="dcffa-381">Daniela can take notes in Amanda's meetings and Amanda can't take notes in any meetings.</span></span>

## <a name="meeting-policy-settings---participants--guests"></a><span data-ttu-id="dcffa-382">会議ポリシーの設定 - 参加者とゲスト</span><span class="sxs-lookup"><span data-stu-id="dcffa-382">Meeting policy settings - Participants & guests</span></span>

<span data-ttu-id="dcffa-383">これらの設定では、会議への入室が許可されるまでロビーで待機する必要がある会議参加者およびそれらの参加者に許可する会議への参加レベルが制御されます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-383">These settings control which meeting participants wait in the lobby before they are admitted to the meeting and the level of participation they are allowed in a meeting.</span></span>

- [<span data-ttu-id="dcffa-384">匿名ユーザーが会議を開始できるようにする</span><span class="sxs-lookup"><span data-stu-id="dcffa-384">Let anonymous people start a meeting</span></span>](#let-anonymous-people-start-a-meeting)
- [<span data-ttu-id="dcffa-385">ユーザーの参加を自動的に許可する</span><span class="sxs-lookup"><span data-stu-id="dcffa-385">Automatically admit people</span></span>](#automatically-admit-people)
- [<span data-ttu-id="dcffa-386">ダイヤルイン ユーザーによるロビーのバイパスを許可する</span><span class="sxs-lookup"><span data-stu-id="dcffa-386">Allow dial-in users to bypass the lobby</span></span>](#allow-dial-in-users-to-bypass-the-lobby)
- [<span data-ttu-id="dcffa-387">プライベート会議で "今すぐ会議" を許可する</span><span class="sxs-lookup"><span data-stu-id="dcffa-387">Allow Meet now in private meetings</span></span>](#allow-meet-now-in-private-meetings)
- [<span data-ttu-id="dcffa-388">ライブ キャプションを有効にする</span><span class="sxs-lookup"><span data-stu-id="dcffa-388">Enable live captions </span></span>](#enable-live-captions)
- [<span data-ttu-id="dcffa-389">会議でチャットを許可する</span><span class="sxs-lookup"><span data-stu-id="dcffa-389">Allow chat in meetings </span></span>](#allow-chat-in-meetings)

> [!NOTE]
><span data-ttu-id="dcffa-390">会議に参加するためのオプションは、各 Teams グループの設定および接続方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="dcffa-390">Options to join a meeting will vary, depending on the settings for each Teams group, and the connection method.</span></span> <span data-ttu-id="dcffa-391">グループに電話会議があり、それを使用して接続する場合は、「[Office 365 における電話会議](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcffa-391">If your group has audio conferencing, and uses it to connect, see [Audio Conferencing in Office 365](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span></span> <span data-ttu-id="dcffa-392">Teams グループに電話会議がない場合は、「[Teams での会議に参加する](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcffa-392">If your Teams group does not have audio conferencing, refer to [Join a meeting in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).</span></span>

### <a name="let-anonymous-people-start-a-meeting"></a><span data-ttu-id="dcffa-393">匿名ユーザーが会議を開始できるようにする</span><span class="sxs-lookup"><span data-stu-id="dcffa-393">Let anonymous people start a meeting</span></span>

<span data-ttu-id="dcffa-394">これは開催者単位のポリシーです。</span><span class="sxs-lookup"><span data-stu-id="dcffa-394">This is a per-organizer policy.</span></span> <span data-ttu-id="dcffa-395">この設定は、認証された組織のユーザーが参加していない場合でも、B2B ユーザーおよびフェデレーション ユーザーなどの匿名ユーザーがユーザーの会議に参加できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-395">This setting controls whether anonymous people, including B2B, and federated users, can join the user's meeting without an authenticated user from the organization in attendance.</span></span> 

![待機中のユーザーへのメッセージが表示されたスクリーンショット](media/meeting-policies-anonymous-user-lobby.png)

<span data-ttu-id="dcffa-397">以下は、認証ユーザーが会議に出席しているときの匿名ユーザーの参加動作です。</span><span class="sxs-lookup"><span data-stu-id="dcffa-397">Here's the join behavior of anonymous people when authenticated users are present in the meeting.</span></span>

|<span data-ttu-id="dcffa-398">匿名ユーザーが会議を開始できるようにする</span><span class="sxs-lookup"><span data-stu-id="dcffa-398">Let anonymous people start a meeting</span></span>  |<span data-ttu-id="dcffa-399">ユーザーの参加を自動的に許可する</span><span class="sxs-lookup"><span data-stu-id="dcffa-399">Automatically admit people</span></span> |<span data-ttu-id="dcffa-400">匿名ユーザーの参加動作</span><span class="sxs-lookup"><span data-stu-id="dcffa-400">Join behavior of anonymous people</span></span> |
|---------|---------|---------|
|<span data-ttu-id="dcffa-401">True</span><span class="sxs-lookup"><span data-stu-id="dcffa-401">True</span></span>    | <span data-ttu-id="dcffa-402">すべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="dcffa-402">Everyone</span></span>      | <span data-ttu-id="dcffa-403">直接参加する</span><span class="sxs-lookup"><span data-stu-id="dcffa-403">Join directly</span></span>         |
|   | <span data-ttu-id="dcffa-404">組織内のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="dcffa-404">Everyone in your organization</span></span>       | <span data-ttu-id="dcffa-405">ロビーで待つ</span><span class="sxs-lookup"><span data-stu-id="dcffa-405">Wait in lobby</span></span>        |
|   | <span data-ttu-id="dcffa-406">組織内およびフェデレーション組織のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="dcffa-406">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="dcffa-407">ロビーで待つ</span><span class="sxs-lookup"><span data-stu-id="dcffa-407">Wait in lobby</span></span>         |
|<span data-ttu-id="dcffa-408">False</span><span class="sxs-lookup"><span data-stu-id="dcffa-408">False</span></span>    | <span data-ttu-id="dcffa-409">すべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="dcffa-409">Everyone</span></span>        | <span data-ttu-id="dcffa-410">直接参加する</span><span class="sxs-lookup"><span data-stu-id="dcffa-410">Join directly</span></span>        |
|   | <span data-ttu-id="dcffa-411">組織内のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="dcffa-411">Everyone in your organization</span></span>     | <span data-ttu-id="dcffa-412">ロビーで待つ</span><span class="sxs-lookup"><span data-stu-id="dcffa-412">Wait in lobby</span></span>        |
|   | <span data-ttu-id="dcffa-413">組織内およびフェデレーション組織のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="dcffa-413">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="dcffa-414">ロビーで待つ</span><span class="sxs-lookup"><span data-stu-id="dcffa-414">Wait in lobby</span></span>         |

<span data-ttu-id="dcffa-415">以下は、認証ユーザーが会議に出席していないときの匿名ユーザーの参加動作です。</span><span class="sxs-lookup"><span data-stu-id="dcffa-415">Here's the join behavior of anonymous people when no authenticated users are present in the meeting.</span></span>

|<span data-ttu-id="dcffa-416">匿名ユーザーが会議を開始できるようにする</span><span class="sxs-lookup"><span data-stu-id="dcffa-416">Let anonymous people start a meeting</span></span> |<span data-ttu-id="dcffa-417">ユーザーの参加を自動的に許可する</span><span class="sxs-lookup"><span data-stu-id="dcffa-417">Automatically admit people</span></span>  |<span data-ttu-id="dcffa-418">匿名ユーザーの参加動作</span><span class="sxs-lookup"><span data-stu-id="dcffa-418">Join behavior of anonymous people</span></span> |
|---------|---------|---------|
|<span data-ttu-id="dcffa-419">True</span><span class="sxs-lookup"><span data-stu-id="dcffa-419">True</span></span>    | <span data-ttu-id="dcffa-420">すべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="dcffa-420">Everyone</span></span>      | <span data-ttu-id="dcffa-421">直接参加する</span><span class="sxs-lookup"><span data-stu-id="dcffa-421">Join directly</span></span>         |
|   | <span data-ttu-id="dcffa-422">組織内のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="dcffa-422">Everyone in your organization</span></span>       | <span data-ttu-id="dcffa-423">ロビーで待つ</span><span class="sxs-lookup"><span data-stu-id="dcffa-423">Wait in lobby</span></span>        |
|   | <span data-ttu-id="dcffa-424">組織内およびフェデレーション組織のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="dcffa-424">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="dcffa-425">ロビーで待つ</span><span class="sxs-lookup"><span data-stu-id="dcffa-425">Wait in lobby</span></span>         |
|<span data-ttu-id="dcffa-426">False</span><span class="sxs-lookup"><span data-stu-id="dcffa-426">False</span></span>    | <span data-ttu-id="dcffa-427">すべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="dcffa-427">Everyone</span></span>        | <span data-ttu-id="dcffa-428">ロビーで待ちます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-428">Wait in lobby.</span></span> <span data-ttu-id="dcffa-429">最初の認証ユーザーが会議に参加すると、ユーザーは自動的に許可されます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-429">Users are automatically admitted when the first authenticated user joins the meeting.</span></span>        |
|   | <span data-ttu-id="dcffa-430">組織内のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="dcffa-430">Everyone in your organization</span></span>     |<span data-ttu-id="dcffa-431">ロビーで待つ</span><span class="sxs-lookup"><span data-stu-id="dcffa-431">Wait in lobby</span></span>         |
|   | <span data-ttu-id="dcffa-432">組織内およびフェデレーション組織のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="dcffa-432">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="dcffa-433">ロビーで待つ</span><span class="sxs-lookup"><span data-stu-id="dcffa-433">Wait in lobby</span></span>         |

### <a name="automatically-admit-people"></a><span data-ttu-id="dcffa-434">ユーザーの参加を自動的に許可する</span><span class="sxs-lookup"><span data-stu-id="dcffa-434">Automatically admit people</span></span>

<span data-ttu-id="dcffa-435">これは開催者単位のポリシーです。</span><span class="sxs-lookup"><span data-stu-id="dcffa-435">This is a per-organizer policy.</span></span> <span data-ttu-id="dcffa-436">この設定は、ユーザーが会議に直接参加するのか、認証ユーザーにより入室が許可されるまでロビーで待機するのかを制御します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-436">This setting controls whether people join a meeting directly or wait in the lobby until they are admitted by an authenticated user.</span></span>

![ロビーにいるユーザーとの会議を示すスクリーンショット](media/meeting-policies-lobby.png)

 <span data-ttu-id="dcffa-438">会議の開催者は、会議出席依頼の [**会議オプション**] をクリックして、スケジュールする会議ごとにこの設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-438">Meeting organizers can click **Meeting Options** in the meeting invitation to change this setting for each meeting they schedule.</span></span>
  
|<span data-ttu-id="dcffa-439">値を設定する</span><span class="sxs-lookup"><span data-stu-id="dcffa-439">Setting value</span></span>  |<span data-ttu-id="dcffa-440">参加動作</span><span class="sxs-lookup"><span data-stu-id="dcffa-440">Join behavior</span></span> |
|---------|---------|
|<span data-ttu-id="dcffa-441">**すべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="dcffa-441">**Everyone**</span></span>   |<span data-ttu-id="dcffa-442">すべての会議参加者は、ロビーで待たずに会議に直接参加します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-442">All meeting participants join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="dcffa-443">これには、認証ユーザー、フェデレーション ユーザー、ゲスト、匿名ユーザー、およびスマートフォンでダイヤル インするユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-443">This includes authenticated users, federated users, guests, anonymous users, and people who dial in by phone.</span></span>       |
|<span data-ttu-id="dcffa-444">**組織内およびフェデレーション組織のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="dcffa-444">**Everyone in your organization and federated organizations**</span></span>     |<span data-ttu-id="dcffa-445">ゲスト ユーザーやフェデレーション組織のユーザーなど、組織内の認証ユーザーは、ロビーで待たずに会議に直接参加します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-445">Authenticated users within the organization, including guest users and the users from federated organizations, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="dcffa-446">匿名ユーザーおよびスマートフォンでダイヤル インするユーザーは、ロビーで待機します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-446">Anonymous users and users who dial in by phone wait in the lobby.</span></span>   |
|<span data-ttu-id="dcffa-447">**組織内のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="dcffa-447">**Everyone in your organization**</span></span>    |<span data-ttu-id="dcffa-448">ゲスト ユーザーを含む組織内の認証ユーザーは、ロビーで待たずに会議に直接参加します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-448">Authenticated users from within the organization, including guest users, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="dcffa-449">フェデレーション ユーザー、匿名ユーザー、およびスマートフォンでダイヤル インするユーザーは、ロビーで待機します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-449">Federated users, anonymous users, and users who dial in by phone wait in the lobby.</span></span>           |

### <a name="allow-dial-in-users-to-bypass-the-lobby"></a><span data-ttu-id="dcffa-450">ダイヤルイン ユーザーによるロビーのバイパスを許可する</span><span class="sxs-lookup"><span data-stu-id="dcffa-450">Allow dial-in users to bypass the lobby</span></span>

<span data-ttu-id="dcffa-451">これは開催者単位のポリシーです。</span><span class="sxs-lookup"><span data-stu-id="dcffa-451">This is a per-organizer policy.</span></span> <span data-ttu-id="dcffa-452">この設定では、スマートフォンでダイヤル インするユーザーが会議に直接参加するのか、[**ユーザーの参加を自動的に許可する**] の設定に関わらずロビーで待機するのかを制御します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-452">This setting controls whether people who dial in by phone join the meeting directly or wait in the lobby regardless of the **Automatically admit people** setting.</span></span>

<span data-ttu-id="dcffa-453">スマートフォンでダイヤル インするユーザーの参加動作は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dcffa-453">Here's the join behavior of people who dial in by phone.</span></span>

|<span data-ttu-id="dcffa-454">ダイヤルイン ユーザーによるロビーのバイパスを許可する</span><span class="sxs-lookup"><span data-stu-id="dcffa-454">Allow dial-in users to bypass the lobby</span></span>  |<span data-ttu-id="dcffa-455">ユーザーの参加を自動的に許可する</span><span class="sxs-lookup"><span data-stu-id="dcffa-455">Automatically admit people</span></span>  |<span data-ttu-id="dcffa-456">ダイヤル インするユーザーの参加動作</span><span class="sxs-lookup"><span data-stu-id="dcffa-456">Join behavior of people who dial in</span></span> |
|---------|---------|---------|
|<span data-ttu-id="dcffa-457">True</span><span class="sxs-lookup"><span data-stu-id="dcffa-457">True</span></span>    | <span data-ttu-id="dcffa-458">すべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="dcffa-458">Everyone</span></span>      | <span data-ttu-id="dcffa-459">直接参加する</span><span class="sxs-lookup"><span data-stu-id="dcffa-459">Join directly</span></span>         |
|   | <span data-ttu-id="dcffa-460">組織内のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="dcffa-460">Everyone in your organization</span></span>       | <span data-ttu-id="dcffa-461">直接参加する</span><span class="sxs-lookup"><span data-stu-id="dcffa-461">Join directly</span></span>        |
|   | <span data-ttu-id="dcffa-462">組織内およびフェデレーション組織のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="dcffa-462">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="dcffa-463">直接参加する</span><span class="sxs-lookup"><span data-stu-id="dcffa-463">Join directly</span></span>         |
|<span data-ttu-id="dcffa-464">False</span><span class="sxs-lookup"><span data-stu-id="dcffa-464">False</span></span>    | <span data-ttu-id="dcffa-465">すべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="dcffa-465">Everyone</span></span>        | <span data-ttu-id="dcffa-466">直接参加する</span><span class="sxs-lookup"><span data-stu-id="dcffa-466">Join directly</span></span>        |
|   | <span data-ttu-id="dcffa-467">組織内のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="dcffa-467">Everyone in your organization</span></span>     |<span data-ttu-id="dcffa-468">ロビーで待つ</span><span class="sxs-lookup"><span data-stu-id="dcffa-468">Wait in lobby</span></span>         |
|   | <span data-ttu-id="dcffa-469">組織内およびフェデレーション組織のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="dcffa-469">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="dcffa-470">ロビーで待つ</span><span class="sxs-lookup"><span data-stu-id="dcffa-470">Wait in lobby</span></span>         |

### <a name="allow-meet-now-in-private-meetings"></a><span data-ttu-id="dcffa-471">プライベート会議で "今すぐ会議" を許可する</span><span class="sxs-lookup"><span data-stu-id="dcffa-471">Allow Meet now in private meetings</span></span>

<span data-ttu-id="dcffa-472">これはユーザーごとのポリシーであり、会議が始まる前に適用されます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-472">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="dcffa-473">この設定は、ユーザーがアドホック プライベート会議を開始できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-473">This setting controls whether a user can start an ad hoc private meeting.</span></span> 

### <a name="enable-live-captions"></a><span data-ttu-id="dcffa-474">ライブ キャプションを有効にする</span><span class="sxs-lookup"><span data-stu-id="dcffa-474">Enable live captions</span></span>

<span data-ttu-id="dcffa-475">これはユーザーごとのポリシーであり、会議中に適用されます。</span><span class="sxs-lookup"><span data-stu-id="dcffa-475">This is a per-user policy and applies during a meeting.</span></span> <span data-ttu-id="dcffa-476">この設定は、ユーザーが参加する会議でライブ キャプションを有効または無効にするために、[**ライブ キャプションを有効にする**] オプションを使用できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-476">This setting controls whether the **Turn on live captions** option is available for the user to turn on and turn off live captions in meetings that the user attends.</span></span>  

![[ライブ キャプションを有効にする] オプションが表示されたスクリーンショット](media/meeting-policies-live-captions.png)

|<span data-ttu-id="dcffa-478">値を設定する</span><span class="sxs-lookup"><span data-stu-id="dcffa-478">Setting value</span></span> |<span data-ttu-id="dcffa-479">動作</span><span class="sxs-lookup"><span data-stu-id="dcffa-479">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="dcffa-480">**無効になっているが、開催者が上書きできる**</span><span class="sxs-lookup"><span data-stu-id="dcffa-480">**Disabled but the organizer can override**</span></span>     | <span data-ttu-id="dcffa-481">会議中にユーザーのライブ キャプションが自動的に有効になることはありません。</span><span class="sxs-lookup"><span data-stu-id="dcffa-481">Live captions aren't automatically turned on for the user during a meeting.</span></span> <span data-ttu-id="dcffa-482">オーバーフロー (**...**) メニューに [**ライブ キャプションを有効にする**] オプションが表示され、それらを有効にします。</span><span class="sxs-lookup"><span data-stu-id="dcffa-482">The user sees the **Turn on live captions** option in the overflow (**...**) menu to turn them on.</span></span> <span data-ttu-id="dcffa-483">これは、既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="dcffa-483">This is the default setting.</span></span> |
|<span data-ttu-id="dcffa-484">**無効**</span><span class="sxs-lookup"><span data-stu-id="dcffa-484">**Disabled**</span></span>     | <span data-ttu-id="dcffa-485">会議中、ユーザーのライブ キャプションが無効になります。</span><span class="sxs-lookup"><span data-stu-id="dcffa-485">Live captions are disabled for the user during a meeting.</span></span> <span data-ttu-id="dcffa-486">ユーザーには、それらを有効にするオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="dcffa-486">The user doesn't have the option to turn them on.</span></span>          |

<span data-ttu-id="dcffa-487"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="dcffa-487"><a name="bkcontentsharing"> </a></span></span>

### <a name="allow-chat-in-meetings"></a><span data-ttu-id="dcffa-488">会議でチャットを許可する</span><span class="sxs-lookup"><span data-stu-id="dcffa-488">Allow chat in meetings</span></span>

<span data-ttu-id="dcffa-489">これは開催者単位のポリシーです。</span><span class="sxs-lookup"><span data-stu-id="dcffa-489">This is a per-organizer policy.</span></span> <span data-ttu-id="dcffa-490">この設定は、ユーザーの会議で会議チャットを許可するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="dcffa-490">This setting controls whether meeting chat is allowed in the user's meeting.</span></span>

<span data-ttu-id="dcffa-491"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="dcffa-491"><a name="bkparticipantsandguests"> </a></span></span>

## <a name="related-topics"></a><span data-ttu-id="dcffa-492">関連項目</span><span class="sxs-lookup"><span data-stu-id="dcffa-492">Related topics</span></span>

[<span data-ttu-id="dcffa-493">Teams のメッセージング ポリシー</span><span class="sxs-lookup"><span data-stu-id="dcffa-493">Messaging policies in Teams</span></span>](messaging-policies-in-teams.md)
