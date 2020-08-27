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
ms.openlocfilehash: a075a432f57a6634a49e9442da0bdc215b1546d9
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255505"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="d0538-103">Teams での会議ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="d0538-103">Manage meeting policies in Teams</span></span>

::: zone target="docs"
<span data-ttu-id="d0538-104">会議ポリシーは、組織内のユーザーによってスケジュールされた会議への参加者が利用できる機能を制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d0538-104">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="d0538-105">自動的に作成される、またはカスタムポリシーを作成して割り当てるグローバル (組織全体の既定) ポリシーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d0538-105">You can use the global (Org-wide default) policy that's automatically created or create and assign custom policies.</span></span> <span data-ttu-id="d0538-106">会議ポリシーは、Microsoft Teams 管理センターで管理するか、[PowerShell](teams-powershell-overview.md) を使用して管理します。</span><span class="sxs-lookup"><span data-stu-id="d0538-106">You manage meeting policies in the Microsoft Teams admin center or by using [PowerShell](teams-powershell-overview.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d0538-107">ロールを使用して、会議の発表者と出席者の権限を管理する方法については、「 [Teams 会議のロール](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0538-107">For information about using roles to manage the permissions of meeting presenters and attendees, see [Roles in a Teams meeting](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).</span></span>

<span data-ttu-id="d0538-108">次の方法でポリシーを実装できます。これらの方法は、会議の開始前、会議中、または会議後のユーザーの会議エクスペリエンスに影響します。</span><span class="sxs-lookup"><span data-stu-id="d0538-108">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span>

|<span data-ttu-id="d0538-109">実装の種類</span><span class="sxs-lookup"><span data-stu-id="d0538-109">Implementation type</span></span>  |<span data-ttu-id="d0538-110">説明</span><span class="sxs-lookup"><span data-stu-id="d0538-110">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="d0538-111">開催者単位</span><span class="sxs-lookup"><span data-stu-id="d0538-111">Per-organizer</span></span>    |<span data-ttu-id="d0538-112">開催者単位のポリシーを実装すると、すべての参加者は開催者のポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="d0538-112">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="d0538-113">たとえば、[**ユーザーの参加を自動的に許可する**] は、開催者単位のポリシーであり、ユーザーが会議に直接参加するか、ポリシーが割り当てられたユーザーがスケジュールした会議をロビーで待機するかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d0538-113">For example, **Automatically admit people** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="d0538-114">ユーザーごと</span><span class="sxs-lookup"><span data-stu-id="d0538-114">Per-user</span></span>    |<span data-ttu-id="d0538-115">ユーザーごとのポリシーを実装すると、ユーザーごとのポリシーのみが適用され、開催者や会議参加者に対する特定の機能が制限されます。</span><span class="sxs-lookup"><span data-stu-id="d0538-115">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="d0538-116">たとえば、[**チャネルで "今すぐ会議" を許可する**] は、ユーザー単位のポリシーです。</span><span class="sxs-lookup"><span data-stu-id="d0538-116">For example, **Allow Meet now in channels** is a per-user policy.</span></span>     |
|<span data-ttu-id="d0538-117">開催者単位およびユーザーごと</span><span class="sxs-lookup"><span data-stu-id="d0538-117">Per-organizer and per-user</span></span>     |<span data-ttu-id="d0538-118">開催者単位とユーザー単位のポリシーを組み合わせて実装すると、会議の参加者はユーザーのポリシーと開催者のポリシーに基づいて特定の機能が制限されます。</span><span class="sxs-lookup"><span data-stu-id="d0538-118">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="d0538-119">たとえば、[**クラウド記録を許可する**] は、開催者単位およびユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="d0538-119">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="d0538-120">この設定をオンにすると、会議の開催者と参加者は記録の開始と停止が可能になります。</span><span class="sxs-lookup"><span data-stu-id="d0538-120">Turn on this setting to allow the meeting organizer and participants to start and stop a recording.</span></span>

<span data-ttu-id="d0538-121">グローバルポリシーの設定を編集するか、または1つまたは複数のカスタムポリシーを作成して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="d0538-121">You can edit the settings in the global policy or create and assign one or more custom policies.</span></span> <span data-ttu-id="d0538-122">カスタムポリシーを作成して割り当てる場合を除き、ユーザーはグローバルポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="d0538-122">Users will get the global policy unless you create and assign a custom policy.</span></span>

> [!NOTE]
> <span data-ttu-id="d0538-123">[会議の詳細] ボタンは、ユーザーが電話会議ライセンスを有効にしているか、ユーザーが電話会議を許可している場合に使用できます。それ以外の場合は、会議の詳細は使用できません。</span><span class="sxs-lookup"><span data-stu-id="d0538-123">Meeting details button will be available if a user has the audio conference licenses enabled or the user is allow for audio conferencing, if not, the meeting details will not be available.</span></span>

## <a name="create-a-custom-meeting-policy"></a><span data-ttu-id="d0538-124">ユーザー設定の会議ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="d0538-124">Create a custom meeting policy</span></span>

1. <span data-ttu-id="d0538-125">Microsoft Teams 管理センターの左側のナビゲーションで、[**会議**]  >  [**会議ポリシー**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="d0538-125">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="d0538-126">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0538-126">Click **Add**.</span></span>
3. <span data-ttu-id="d0538-127">ポリシーの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="d0538-127">Enter a name and description for the policy.</span></span> <span data-ttu-id="d0538-128">名前に特殊文字を含めたり、64 文字より長くしたりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d0538-128">The name can't contain special characters or be longer than 64 characters.</span></span>
4. <span data-ttu-id="d0538-129">目的の設定を選びます。</span><span class="sxs-lookup"><span data-stu-id="d0538-129">Choose the settings that you want.</span></span>
5. <span data-ttu-id="d0538-130">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0538-130">Click **Save**.</span></span>

<span data-ttu-id="d0538-131">たとえば、多数のユーザーがいて、会議に必要な帯域幅を制限するとします。</span><span class="sxs-lookup"><span data-stu-id="d0538-131">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="d0538-132">「制限された帯域幅」という名前の新しいカスタム ポリシーを作成し、次の設定を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="d0538-132">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="d0538-133">[**オーディオとビデオ**] で、</span><span class="sxs-lookup"><span data-stu-id="d0538-133">Under **Audio & video**:</span></span>

- <span data-ttu-id="d0538-134">[クラウド記録を許可する] を無効にします。</span><span class="sxs-lookup"><span data-stu-id="d0538-134">Turn off Allow cloud recording.</span></span>
- <span data-ttu-id="d0538-135">[IP のビデオを許可する] を無効にします。</span><span class="sxs-lookup"><span data-stu-id="d0538-135">Turn off Allow IP video.</span></span>

<span data-ttu-id="d0538-136">[**コンテンツの共有**] で、</span><span class="sxs-lookup"><span data-stu-id="d0538-136">Under **Content sharing**:</span></span>

- <span data-ttu-id="d0538-137">画面共有モードを無効にします。</span><span class="sxs-lookup"><span data-stu-id="d0538-137">Disable screen sharing mode.</span></span>
- <span data-ttu-id="d0538-138">[ホワイトボードを許可] を無効にします。</span><span class="sxs-lookup"><span data-stu-id="d0538-138">Turn off Allow whiteboard.</span></span>
- <span data-ttu-id="d0538-139">[メモの共有を許可する] を無効にします。</span><span class="sxs-lookup"><span data-stu-id="d0538-139">Turn off Allow shared notes.</span></span>

<span data-ttu-id="d0538-140">その後、ポリシーをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d0538-140">Then assign the policy to the users.</span></span>

## <a name="edit-a-meeting-policy"></a><span data-ttu-id="d0538-141">会議ポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="d0538-141">Edit a meeting policy</span></span>

<span data-ttu-id="d0538-142">グローバルポリシーは、作成した任意のカスタムポリシーで編集できます。</span><span class="sxs-lookup"><span data-stu-id="d0538-142">You can edit the global policy an any custom policies that you create.</span></span>

1. <span data-ttu-id="d0538-143">Microsoft Teams 管理センターの左側のナビゲーションで、[**会議**]  >  [**会議ポリシー**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="d0538-143">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="d0538-144">ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0538-144">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="d0538-145">ここで、必要な変更を行います。</span><span class="sxs-lookup"><span data-stu-id="d0538-145">From here, make the changes that you want.</span></span>
4. <span data-ttu-id="d0538-146">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0538-146">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="d0538-147">ユーザーに割り当てることができる会議ポリシーは一度に 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="d0538-147">A user can be assigned only one meeting policy at a time.</span></span>

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="d0538-148">ユーザーに会議ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="d0538-148">Assign a meeting policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

> [!NOTE]
> <span data-ttu-id="d0538-149">ユーザーが割り当てられているポリシーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="d0538-149">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="d0538-150">影響を受けるすべてのユーザーにまず異なるポリシーを割り当ててから、元のポリシーを削除できます。</span><span class="sxs-lookup"><span data-stu-id="d0538-150">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

## <a name="meeting-policy-settings"></a><span data-ttu-id="d0538-151">会議ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="d0538-151">Meeting policy settings</span></span>

<span data-ttu-id="d0538-152">[**会議ポリシー**] ページで既存のポリシーを選択するか、新しいポリシーを追加するための [**追加**] を選択すると、次の設定内容を構成できます。</span><span class="sxs-lookup"><span data-stu-id="d0538-152">When you select an existing policy on the **Meeting policies** page or select **Add** to add a new policy, you can configure settings for the following.</span></span>

- [<span data-ttu-id="d0538-153">全般</span><span class="sxs-lookup"><span data-stu-id="d0538-153">General</span></span>](#meeting-policy-settings---general)
- [<span data-ttu-id="d0538-154">オーディオとビデオ</span><span class="sxs-lookup"><span data-stu-id="d0538-154">Audio & video</span></span>](#meeting-policy-settings---audio--video)
- [<span data-ttu-id="d0538-155">コンテンツの共有</span><span class="sxs-lookup"><span data-stu-id="d0538-155">Content sharing</span></span>](#meeting-policy-settings---content-sharing)
- [<span data-ttu-id="d0538-156">参加者とゲスト</span><span class="sxs-lookup"><span data-stu-id="d0538-156">Participants & guests</span></span>](#meeting-policy-settings---participants--guests)

::: zone-end

<span data-ttu-id="d0538-157"><a name="bkgeneral"> </a></span><span class="sxs-lookup"><span data-stu-id="d0538-157"><a name="bkgeneral"> </a></span></span>

## <a name="meeting-policy-settings---general"></a><span data-ttu-id="d0538-158">会議ポリシーの設定 - 全般</span><span class="sxs-lookup"><span data-stu-id="d0538-158">Meeting policy settings - General</span></span>

- [<span data-ttu-id="d0538-159">チャネルで "今すぐ会議" を許可する</span><span class="sxs-lookup"><span data-stu-id="d0538-159">Allow Meet now in channels</span></span>](#allow-meet-now-in-channels)
- [<span data-ttu-id="d0538-160">Outlook アドインを許可する</span><span class="sxs-lookup"><span data-stu-id="d0538-160">Allow the Outlook add-in</span></span>](#allow-the-outlook-add-in)
- [<span data-ttu-id="d0538-161">チャネルの会議スケジュールを許可する</span><span class="sxs-lookup"><span data-stu-id="d0538-161">Allow channel meeting scheduling</span></span>](#allow-channel-meeting-scheduling)
- [<span data-ttu-id="d0538-162">プライベート会議のスケジュールを許可する</span><span class="sxs-lookup"><span data-stu-id="d0538-162">Allow scheduling private meetings</span></span>](#allow-scheduling-private-meetings)
- [<span data-ttu-id="d0538-163">プライベート会議で "今すぐ会議" を許可する</span><span class="sxs-lookup"><span data-stu-id="d0538-163">Allow Meet now in private meetings</span></span>](#allow-meet-now-in-private-meetings)

### <a name="allow-meet-now-in-channels"></a><span data-ttu-id="d0538-164">チャネルで "今すぐ会議" を許可する</span><span class="sxs-lookup"><span data-stu-id="d0538-164">Allow Meet now in channels</span></span>

<span data-ttu-id="d0538-165">これはユーザーごとのポリシーであり、会議が始まる前に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d0538-165">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="d0538-166">この設定は、ユーザーが Teams チャネルでアドホック会議を開始できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d0538-166">This setting controls whether a user can start an ad hoc meeting in a Teams channel.</span></span> <span data-ttu-id="d0538-167">これをオンにすると、ユーザーが Teams チャネルにメッセージを投稿するときに、ユーザーは作成ボックスの下の [**今すぐ会議**] をクリックして、チャネルでアドホック会議を開始できます。</span><span class="sxs-lookup"><span data-stu-id="d0538-167">If you turn this on, when a user posts a message in a Teams channel, the user can click **Meet now** under the compose box to start an ad hoc meeting in the channel.</span></span> <span data-ttu-id="d0538-168">既定値は True です。</span><span class="sxs-lookup"><span data-stu-id="d0538-168">The default value is True.</span></span>

![メッセージの下の [今すぐ会議] アイコンが表示されたスクリーンショット](media/meeting-policies-meet-now.png)

### <a name="allow-the-outlook-add-in"></a><span data-ttu-id="d0538-170">Outlook アドインを許可する</span><span class="sxs-lookup"><span data-stu-id="d0538-170">Allow the Outlook add-in</span></span>

<span data-ttu-id="d0538-171">これはユーザーごとのポリシーであり、会議が始まる前に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d0538-171">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="d0538-172">この設定は、Outlook (Windows、Mac、Web、およびモバイル) 内から Teams 会議をスケジュールできるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d0538-172">This setting controls whether Teams meetings can be scheduled from within Outlook (Windows, Mac, web, and mobile).</span></span>

![新しい会議をスケジュールする機能が表示されたスクリーンショット](media/meeting-policies-outlook-add-in.png)

<span data-ttu-id="d0538-174">これをオフにすると、ユーザーは Outlook で新しい会議を作成するときに Teams 会議をスケジュールできなくなります。</span><span class="sxs-lookup"><span data-stu-id="d0538-174">If you turn this off, users are unable to schedule Teams meetings when they create a new meeting in Outlook.</span></span> <span data-ttu-id="d0538-175">たとえば、Windows 上の Outlook では、[**新しい Teams 会議**] オプションはリボンに表示されません。</span><span class="sxs-lookup"><span data-stu-id="d0538-175">For example, in Outlook on Windows, the **New Teams Meeting** option won't show up in the ribbon.</span></span>

### <a name="allow-channel-meeting-scheduling"></a><span data-ttu-id="d0538-176">チャネルの会議スケジュールを許可する</span><span class="sxs-lookup"><span data-stu-id="d0538-176">Allow channel meeting scheduling</span></span>

<span data-ttu-id="d0538-177">既存の Allowchannel会議スケジュールポリシーを使用して、チームチャネルの予定表で作成できるイベントの種類を制御します。</span><span class="sxs-lookup"><span data-stu-id="d0538-177">Use the existing AllowChannelMeetingScheduling policy to control the types of events that can be created on the team channel calendars.</span></span> <span data-ttu-id="d0538-178">これはユーザーごとのポリシーであり、会議が始まる前に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d0538-178">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="d0538-179">この設定は、ユーザーが Teams チャネルで会議をスケジュールできるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d0538-179">This setting controls whether users can schedule a meeting in a Teams channel.</span></span> <span data-ttu-id="d0538-180">既定値は True です。</span><span class="sxs-lookup"><span data-stu-id="d0538-180">The default value is True.</span></span>

<span data-ttu-id="d0538-181">このポリシーが無効になっている場合、ユーザーは新しいチャネル会議を作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="d0538-181">If this policy is OFF, users will not be able to create new channel meetings.</span></span> <span data-ttu-id="d0538-182">ただし、既存のチャネル会議は、イベントの開催者によって編集できます。</span><span class="sxs-lookup"><span data-stu-id="d0538-182">However, existing channel meetings can be edited by the organizer of the event.</span></span>

<span data-ttu-id="d0538-183">会議のスケジュールが無効になります。</span><span class="sxs-lookup"><span data-stu-id="d0538-183">Schedule a meeting will be disabled.</span></span>

![Teams の [会議の予約] オプションが表示されたスクリーンショット](media/schedule-meeting-option.png)

<span data-ttu-id="d0538-185">チャネルの選択が無効になっています。</span><span class="sxs-lookup"><span data-stu-id="d0538-185">Channel selection is disabled.</span></span>

![会議をスケジュールするチャネルを選択するための [予定表] オプションを示すスクリーンショット。](media/meeting-policies-select-a-channel-to-meet-in.png)

<span data-ttu-id="d0538-187">[チャネルの投稿] ページでは、次の機能が無効になります。</span><span class="sxs-lookup"><span data-stu-id="d0538-187">In the channel posts page, the following will be disabled:</span></span>

- <span data-ttu-id="d0538-188">[チャネル返信の作成] ボックスの [**会議の予約**] ボタン。</span><span class="sxs-lookup"><span data-stu-id="d0538-188">**Schedule a meeting** button on the channel reply compose box.</span></span>
<span data-ttu-id="d0538-189">![会議をスケジュールするチャネルを選択するための [予定表] オプションを示すスクリーンショット。](media/schedule-meeting-disabled-in-chat2.png)</span><span class="sxs-lookup"><span data-stu-id="d0538-189">![Screenshot showing the calendar option for selecting a channel that you want to schedule a meeting in.](media/schedule-meeting-disabled-in-chat2.png)</span></span>
- <span data-ttu-id="d0538-190">チャネルヘッダーの [**会議の予約**] ボタン。</span><span class="sxs-lookup"><span data-stu-id="d0538-190">**Schedule a meeting** button on the channel header.</span></span>
<span data-ttu-id="d0538-191">![会議をスケジュールするチャネルを選択するための [予定表] オプションを示すスクリーンショット。](media/schedule-now-in-header.png)</span><span class="sxs-lookup"><span data-stu-id="d0538-191">![Screenshot showing the calendar option for selecting a channel that you want to schedule a meeting in.](media/schedule-now-in-header.png)</span></span>

<span data-ttu-id="d0538-192">チャネルの予定表で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d0538-192">In the channel calendar:</span></span>

- <span data-ttu-id="d0538-193">チャネル予定表ヘッダーの [**新しいイベントの追加**] ボタンは無効になります。</span><span class="sxs-lookup"><span data-stu-id="d0538-193">**Add new event** button on channel calendar header will be disabled.</span></span>
<span data-ttu-id="d0538-194">![会議をスケジュールするチャネルを選択するための [予定表] オプションを示すスクリーンショット。](media/add-new-event-disabled.png)</span><span class="sxs-lookup"><span data-stu-id="d0538-194">![Screenshot showing the calendar option for selecting a channel that you want to schedule a meeting in.](media/add-new-event-disabled.png)</span></span>
- <span data-ttu-id="d0538-195">チャネルの会議を作成するために、ユーザーはチャネルの予定表の時間ブロックをドラッグして選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="d0538-195">Users will not be able to drag and select a time block on the channel calendar to create a channel meeting.</span></span>
- <span data-ttu-id="d0538-196">ユーザーはキーボードショートカットを使用して、チャネル予定表で会議を作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="d0538-196">Users cannot use Keyboard shortcuts to create a meeting on the channel calendar.</span></span>

<span data-ttu-id="d0538-197">管理センターでは、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d0538-197">In the Admin Center:</span></span>

<span data-ttu-id="d0538-198">[管理者] パネルの [ **Microsoft アプリ** ] セクションに、アクセス許可ポリシーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d0538-198">The channel calendar app will show up under the **Microsoft apps** section in the admin panel for permission policies.</span></span>

![Teams の管理コンソールでの Microsoft アプリのポリシーを示すスクリーンショット。](media/manage-microsoft-apps-policy.png)

### <a name="allow-scheduling-private-meetings"></a><span data-ttu-id="d0538-200">プライベート会議のスケジュールを許可する</span><span class="sxs-lookup"><span data-stu-id="d0538-200">Allow scheduling private meetings</span></span>

<span data-ttu-id="d0538-201">これはユーザーごとのポリシーであり、会議が始まる前に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d0538-201">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="d0538-202">この設定は、ユーザーが Teams でプライベート会議をスケジュールできるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d0538-202">This setting controls whether users can schedule private meetings in Teams.</span></span> <span data-ttu-id="d0538-203">チームのチャネルに公開されていない会議はプライベートです。</span><span class="sxs-lookup"><span data-stu-id="d0538-203">A meeting is private when it's not published to a channel in a team.</span></span>

<span data-ttu-id="d0538-204">[**プライベート会議のスケジュールを許可する**] および [**チャネルの会議スケジュールを許可する**] を無効にすると、Teams のユーザーに対して [**必須出席者の追加**] および [**チャネルの追加**] オプションが無効になります。</span><span class="sxs-lookup"><span data-stu-id="d0538-204">Note that if you turn off **Allow scheduling private meetings** and **Allow channel meeting scheduling**,  the **Add required attendees** and **Add channel** options are disabled for users in Teams.</span></span> <span data-ttu-id="d0538-205">既定値は True です。</span><span class="sxs-lookup"><span data-stu-id="d0538-205">The default value is True.</span></span>

### <a name="allow-meet-now-in-private-meetings"></a><span data-ttu-id="d0538-206">プライベート会議で "今すぐ会議" を許可する</span><span class="sxs-lookup"><span data-stu-id="d0538-206">Allow Meet now in private meetings</span></span>

<span data-ttu-id="d0538-207">これはユーザーごとのポリシーであり、会議が始まる前に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d0538-207">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="d0538-208">この設定は、ユーザーがアドホック プライベート会議を開始できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d0538-208">This setting controls whether a user can start an ad hoc private meeting.</span></span>  <span data-ttu-id="d0538-209">既定値は True です。</span><span class="sxs-lookup"><span data-stu-id="d0538-209">The default value is True.</span></span>

<span data-ttu-id="d0538-210"><a name="bkaudioandvideo"> </a></span><span class="sxs-lookup"><span data-stu-id="d0538-210"><a name="bkaudioandvideo"> </a></span></span>

## <a name="meeting-policy-settings---audio--video"></a><span data-ttu-id="d0538-211">会議ポリシーの設定 - オーディオとビデオ</span><span class="sxs-lookup"><span data-stu-id="d0538-211">Meeting policy settings - Audio & video</span></span>

- [<span data-ttu-id="d0538-212">文字起こしを許可する</span><span class="sxs-lookup"><span data-stu-id="d0538-212">Allow transcription</span></span>](#allow-transcription)
- [<span data-ttu-id="d0538-213">クラウド記録を許可する</span><span class="sxs-lookup"><span data-stu-id="d0538-213">Allow cloud recording</span></span>](#allow-cloud-recording)
- [<span data-ttu-id="d0538-214">IP のビデオを許可する</span><span class="sxs-lookup"><span data-stu-id="d0538-214">Allow IP video</span></span>](#allow-ip-video)
- [<span data-ttu-id="d0538-215">メディアのビットレート (Kbs)</span><span class="sxs-lookup"><span data-stu-id="d0538-215">Media bit rate (Kbs)</span></span>](#media-bit-rate-kbs)

### <a name="allow-transcription"></a><span data-ttu-id="d0538-216">文字起こしを許可する</span><span class="sxs-lookup"><span data-stu-id="d0538-216">Allow transcription</span></span>

<span data-ttu-id="d0538-217">これは、開催者単位とユーザーごとのポリシーの組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="d0538-217">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="d0538-218">この設定は、会議の記録の再生中にキャプションと文字起こし機能を使用できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d0538-218">This setting controls whether captions and transcription features are available during playback of meeting recordings.</span></span> <span data-ttu-id="d0538-219">これをオフにすると、会議の記録の再生中に [**検索**] および [**CC**] オプションを使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="d0538-219">If you turn this off, the **Search** and **CC** options won't be available during playback of a meeting recording.</span></span> <span data-ttu-id="d0538-220">記録を開始したユーザーは、記録に文字起こしも含まれるように、この設定を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0538-220">The person who started the recording needs this setting turned on so that the recording also includes transcription.</span></span>

<span data-ttu-id="d0538-221">記録された会議の文字起こしは、現在、Teams の言語が英語に設定されているユーザー、および会議で英語が話されている場合のユーザーに対してのみサポートされていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d0538-221">Note that transcription for recorded meetings is currently only supported for users who have the language in Teams set to English and when English is spoken in the meeting.</span></span>

![会議の文字起こしオプションが表示されたスクリーンショット](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a><span data-ttu-id="d0538-223">クラウド記録を許可する</span><span class="sxs-lookup"><span data-stu-id="d0538-223">Allow cloud recording</span></span>

<span data-ttu-id="d0538-224">これは、開催者単位とユーザーごとのポリシーの組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="d0538-224">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="d0538-225">この設定は、このユーザーの会議を記録できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d0538-225">This setting controls whether this user's meetings can be recorded.</span></span> <span data-ttu-id="d0538-226">参加者のポリシー設定が有効になっており、同じ組織の認証済みユーザーである場合、会議の開催者または別の会議参加者が記録を開始できます。</span><span class="sxs-lookup"><span data-stu-id="d0538-226">The recording can be started by the meeting organizer or by another meeting participant if the policy setting is turned on for the participant and if they're an authenticated user from the same organization.</span></span>

<span data-ttu-id="d0538-227">フェデレーション ユーザーや匿名ユーザーなど、組織外のユーザーは記録を開始できません。</span><span class="sxs-lookup"><span data-stu-id="d0538-227">People outside your organization, such as federated and anonymous users, can't start the recording.</span></span> <span data-ttu-id="d0538-228">ゲスト ユーザーは記録を開始または停止できません。</span><span class="sxs-lookup"><span data-stu-id="d0538-228">Guest users can't start or stop the recording.</span></span>

![記録オプションが表示されたスクリーンショット](media/meeting-policies-recording.png)

<span data-ttu-id="d0538-230">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="d0538-230">Let's look at the following example.</span></span>

|<span data-ttu-id="d0538-231">ユーザー</span><span class="sxs-lookup"><span data-stu-id="d0538-231">User</span></span> |<span data-ttu-id="d0538-232">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="d0538-232">Meeting policy</span></span>  |<span data-ttu-id="d0538-233">クラウド記録を許可する</span><span class="sxs-lookup"><span data-stu-id="d0538-233">Allow cloud recording</span></span> |
|---------|---------|---------|
|<span data-ttu-id="d0538-234">Daniela</span><span class="sxs-lookup"><span data-stu-id="d0538-234">Daniela</span></span> | <span data-ttu-id="d0538-235">グローバル</span><span class="sxs-lookup"><span data-stu-id="d0538-235">Global</span></span>   | <span data-ttu-id="d0538-236">False</span><span class="sxs-lookup"><span data-stu-id="d0538-236">False</span></span> |
|<span data-ttu-id="d0538-237">Amanda</span><span class="sxs-lookup"><span data-stu-id="d0538-237">Amanda</span></span> | <span data-ttu-id="d0538-238">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="d0538-238">Location1MeetingPolicy</span></span> | <span data-ttu-id="d0538-239">True</span><span class="sxs-lookup"><span data-stu-id="d0538-239">True</span></span>|
|<span data-ttu-id="d0538-240">John (外部ユーザー)</span><span class="sxs-lookup"><span data-stu-id="d0538-240">John (external user)</span></span> | <span data-ttu-id="d0538-241">該当なし</span><span class="sxs-lookup"><span data-stu-id="d0538-241">Not applicable</span></span> | <span data-ttu-id="d0538-242">該当なし</span><span class="sxs-lookup"><span data-stu-id="d0538-242">Not applicable</span></span>|

<span data-ttu-id="d0538-243">Daniela が開催する会議は記録されず、ポリシー設定が有効になっている Amanda は Daniela が開催する会議を記録できません。</span><span class="sxs-lookup"><span data-stu-id="d0538-243">Meetings organized by Daniela can't be recorded and Amanda, who has the policy setting enabled, can't record meetings organized by Daniela.</span></span> <span data-ttu-id="d0538-244">Amanda が開催する会議は記録できますが、ポリシー設定が無効になっている Daniela と外部ユーザーである John は、Amanda が開催する会議を記録できません。</span><span class="sxs-lookup"><span data-stu-id="d0538-244">Meetings organized by Amanda can be recorded, however,  Daniela, who has the policy setting disabled and John who is an external user, can't record meetings organized by Amanda.</span></span>

<span data-ttu-id="d0538-245">クラウド会議の記録の詳細については、「[Teams のクラウド会議の記録](cloud-recording.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0538-245">To learn more about cloud meeting recording, see [Teams cloud meeting recording](cloud-recording.md).</span></span>

### <a name="allow-ip-video"></a><span data-ttu-id="d0538-246">IP ビデオを許可する</span><span class="sxs-lookup"><span data-stu-id="d0538-246">Allow IP video</span></span>

<span data-ttu-id="d0538-247">これは、開催者単位とユーザーごとのポリシーの組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="d0538-247">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="d0538-248">ビデオは、会議の重要な構成要素です。</span><span class="sxs-lookup"><span data-stu-id="d0538-248">Video is a key component to meetings.</span></span> <span data-ttu-id="d0538-249">一部の組織では、管理者がビデオを使用するユーザーの会議をさらに制御する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="d0538-249">In some organizations, admins might want more control over which users' meetings have video.</span></span> <span data-ttu-id="d0538-250">この設定は、ユーザーがホストする会議、およびユーザーが開始する 1:1 通話やグループ通話でビデオを有効にできるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d0538-250">This setting controls whether video can be turned on in meetings hosted by a user and in 1:1 calls and group calls started by a user.</span></span> <span data-ttu-id="d0538-251">このポリシーを有効にしたユーザーが開催する会議では、会議の参加者もポリシーを有効にしている場合に、会議の参加者による会議でのビデオ共有が許可されます。</span><span class="sxs-lookup"><span data-stu-id="d0538-251">Meetings organized by a user who has this policy enabled, allow video sharing in the meeting by the meeting participants, if the meeting participants also have the policy enabled.</span></span> <span data-ttu-id="d0538-252">ポリシーが割り当てられていない会議参加者 (匿名参加者やフェデレーション参加者など) は、会議開催者のポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="d0538-252">Meeting participants who don't have any policies assigned (for example, anonymous and federated participants) inherit the policy of the meeting organizer.</span></span>

![オーディオとビデオの設定を含む会議が表示されたスクリーンショット](media/meeting-policies-audio-video-settings.png)

<span data-ttu-id="d0538-254">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="d0538-254">Let's look at the following example.</span></span>

|<span data-ttu-id="d0538-255">ユーザー</span><span class="sxs-lookup"><span data-stu-id="d0538-255">User</span></span> |<span data-ttu-id="d0538-256">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="d0538-256">Meeting policy</span></span>  |<span data-ttu-id="d0538-257">IP ビデオを許可する</span><span class="sxs-lookup"><span data-stu-id="d0538-257">Allow IP Video</span></span> |
|---------|---------|---------|
|<span data-ttu-id="d0538-258">Daniela</span><span class="sxs-lookup"><span data-stu-id="d0538-258">Daniela</span></span>   | <span data-ttu-id="d0538-259">グローバル</span><span class="sxs-lookup"><span data-stu-id="d0538-259">Global</span></span>   | <span data-ttu-id="d0538-260">True</span><span class="sxs-lookup"><span data-stu-id="d0538-260">True</span></span>        |
|<span data-ttu-id="d0538-261">Amanda</span><span class="sxs-lookup"><span data-stu-id="d0538-261">Amanda</span></span>    | <span data-ttu-id="d0538-262">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="d0538-262">Location1MeetingPolicy</span></span>        | <span data-ttu-id="d0538-263">False</span><span class="sxs-lookup"><span data-stu-id="d0538-263">False</span></span>      |

<span data-ttu-id="d0538-264">Daniela が開催する会議では、ビデオを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d0538-264">Meetings hosted by Daniela allow video to be turned on.</span></span> <span data-ttu-id="d0538-265">Daniela は会議に参加してビデオを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d0538-265">Daniela can join the meeting and turn on video.</span></span> <span data-ttu-id="d0538-266">Amanda のポリシーが [ビデオを許可しない] に設定されているため、Amanda は Daniela の会議でビデオを有効にできません。</span><span class="sxs-lookup"><span data-stu-id="d0538-266">Amanda can't turn on video in Daniela's meeting because Amanda's policy is set to not allow video.</span></span> <span data-ttu-id="d0538-267">Amanda は、会議の他の参加者が共有しているビデオを見ることができます。</span><span class="sxs-lookup"><span data-stu-id="d0538-267">Amanda can see videos shared by other participants in the meeting.</span></span>

<span data-ttu-id="d0538-268">Amanda が主催する会議では、割り当てられたビデオ ポリシーに関係なく、誰もビデオを有効にできません。</span><span class="sxs-lookup"><span data-stu-id="d0538-268">In meetings hosted by Amanda, no one can turn on video, regardless of the video policy assigned to them.</span></span> <span data-ttu-id="d0538-269">これは、Daniela Amanda の会議でビデオを有効にできないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="d0538-269">This means Daniela can't turn on video in Amanda's meetings.</span></span>  

<span data-ttu-id="d0538-270">Daniela がビデオを有効にして Amanda に電話した場合、Amanda はオーディオのみで電話に出ることができます。</span><span class="sxs-lookup"><span data-stu-id="d0538-270">If Daniela calls Amanda with video on, Amanda can answer the call with audio only.</span></span>  <span data-ttu-id="d0538-271">通話が接続されている場合、Amanda は Daniela のビデオを見ることはできますが、ビデオを有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d0538-271">When the call is connected, Amanda can see Daniela's video, but can't turn on video.</span></span> <span data-ttu-id="d0538-272">Amanda が Daniela に電話すると、Daniela はビデオとオーディオで電話に出ることができます。</span><span class="sxs-lookup"><span data-stu-id="d0538-272">If Amanda calls Daniela, Daniela can answer the call with video and audio.</span></span> <span data-ttu-id="d0538-273">通話が接続されると、Daniela は必要に応じてビデオを有効または無効にできます。</span><span class="sxs-lookup"><span data-stu-id="d0538-273">When the call is connected, Daniela can turn on or turn off her video, as needed.</span></span>

### <a name="media-bit-rate-kbs"></a><span data-ttu-id="d0538-274">メディアのビットレート (Kbs)</span><span class="sxs-lookup"><span data-stu-id="d0538-274">Media bit rate (Kbs)</span></span>

<span data-ttu-id="d0538-275">これは、ユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="d0538-275">This is a per-user policy.</span></span> <span data-ttu-id="d0538-276">この設定により、ユーザーの通話および会議でのオーディオ、ビデオ、およびビデオベースのアプリ共有送信のメディア ビット レートが決まります。</span><span class="sxs-lookup"><span data-stu-id="d0538-276">This setting determines the media bit rate for audio, video, and video-based app sharing transmissions in calls and meetings for the user.</span></span> <span data-ttu-id="d0538-277">通話または会議のユーザーのアップリンクとダウンリンクの両方のメディア トラバーサルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="d0538-277">It's applied to both the uplink and downlink media traversal for users in the call or meeting.</span></span> <span data-ttu-id="d0538-278">この設定により、組織の帯域幅の管理をきめ細やかに制御できます。</span><span class="sxs-lookup"><span data-stu-id="d0538-278">This setting gives you granular control over managing bandwidth in your organization.</span></span> <span data-ttu-id="d0538-279">ユーザーが必要とする会議シナリオに応じて、高品質のエクスペリエンスを得るために十分な帯域幅を用意することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d0538-279">Depending on the meetings scenarios required by users, we recommend having enough bandwidth in place for a good quality experience.</span></span> <span data-ttu-id="d0538-280">最小値は 30 Kbps で、最大値は会議シナリオによって異なります。</span><span class="sxs-lookup"><span data-stu-id="d0538-280">The minimum value is 30 Kbps and the maximum value depends on the meeting scenario.</span></span> <span data-ttu-id="d0538-281">Teams での高品質の会議、通話、およびライブ イベントを実現する最小推奨帯域幅の詳細については、「[帯域幅要件](prepare-network.md#bandwidth-requirements)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0538-281">To learn more about the minimum recommended bandwidth for good quality meetings, calls, and live events in Teams, see [Bandwidth requirements](prepare-network.md#bandwidth-requirements).</span></span>

<span data-ttu-id="d0538-282">会議に十分な帯域幅がない場合、参加者には、ネットワークの品質低下を示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d0538-282">If there isn't enough bandwidth for a meeting, participants see a message that indicates poor network quality.</span></span>

<span data-ttu-id="d0538-283">CEO ボード会議や Teams のライブ イベントなど、最高品質のビデオ エクスペリエンスを必要とする会議では、帯域幅を 10 Mbps に設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d0538-283">For meetings that need the highest quality video experience, such as CEO board meetings and Teams live events, we recommend you set the bandwidth to 10 Mbps.</span></span> <span data-ttu-id="d0538-284">最大限のエクスペリエンスが設定されている場合でも、特定のネットワーク条件が検出されると、シナリオに応じて、Teams メディア スタックは低帯域幅の条件に適応します。</span><span class="sxs-lookup"><span data-stu-id="d0538-284">Even when the maximum experience is set, the Teams media stack adapts to low bandwidth conditions when certain network conditions are detected, depending on the scenario.</span></span>

## <a name="meeting-policy-settings---content-sharing"></a><span data-ttu-id="d0538-285">会議ポリシーの設定 - コンテンツの共有</span><span class="sxs-lookup"><span data-stu-id="d0538-285">Meeting policy settings - Content sharing</span></span>

- [<span data-ttu-id="d0538-286">画面共有モード</span><span class="sxs-lookup"><span data-stu-id="d0538-286">Screen sharing mode</span></span>](#screen-sharing-mode)
- [<span data-ttu-id="d0538-287">参加者に制御を渡す、または制御を要求する</span><span class="sxs-lookup"><span data-stu-id="d0538-287">Allow a participant to give or request control</span></span>](#allow-a-participant-to-give-or-request-control)
- [<span data-ttu-id="d0538-288">外部の参加者に制御を渡す、または制御を要求する</span><span class="sxs-lookup"><span data-stu-id="d0538-288">Allow an external participant to give or request control</span></span>](#allow-an-external-participant-to-give-or-request-control)
- [<span data-ttu-id="d0538-289">PowerPoint の共有を許可する</span><span class="sxs-lookup"><span data-stu-id="d0538-289">Allow PowerPoint sharing</span></span>](#allow-powerpoint-sharing)
- [<span data-ttu-id="d0538-290">ホワイトボードを許可する</span><span class="sxs-lookup"><span data-stu-id="d0538-290">Allow whiteboard</span></span>](#allow-whiteboard)
- [<span data-ttu-id="d0538-291">メモの共有を許可する</span><span class="sxs-lookup"><span data-stu-id="d0538-291">Allow shared notes</span></span>](#allow-shared-notes)

### <a name="screen-sharing-mode"></a><span data-ttu-id="d0538-292">画面共有モード</span><span class="sxs-lookup"><span data-stu-id="d0538-292">Screen sharing mode</span></span>

<span data-ttu-id="d0538-293">これは、開催者単位とユーザーごとのポリシーの組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="d0538-293">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="d0538-294">この設定は、ユーザーの会議でデスクトップやウィンドウの共有を許可するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d0538-294">This setting controls whether desktop and/or window sharing is allowed in the user's meeting.</span></span> <span data-ttu-id="d0538-295">ポリシーが割り当てられていない会議参加者 (匿名参加者、ゲスト参加者、B2B 参加者、フェデレーション参加者など) は、会議開催者のポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="d0538-295">Meeting participants who don't have any policies assigned (for example, anonymous, guest, B2B, and federated participants) inherit the policy of the meeting organizer.</span></span>

|<span data-ttu-id="d0538-296">値を設定する</span><span class="sxs-lookup"><span data-stu-id="d0538-296">Setting value</span></span> |<span data-ttu-id="d0538-297">動作</span><span class="sxs-lookup"><span data-stu-id="d0538-297">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="d0538-298">**画面全体**</span><span class="sxs-lookup"><span data-stu-id="d0538-298">**Entire screen**</span></span>    | <span data-ttu-id="d0538-299">会議では完全なデスクトップ共有とアプリケーション共有が許可されます</span><span class="sxs-lookup"><span data-stu-id="d0538-299">Full desktop sharing and application sharing is allowed in the meeting</span></span> |
|<span data-ttu-id="d0538-300">**単一アプリケーション**</span><span class="sxs-lookup"><span data-stu-id="d0538-300">**Single application**</span></span>   | <span data-ttu-id="d0538-301">会議ではアプリケーションの共有が許可されます</span><span class="sxs-lookup"><span data-stu-id="d0538-301">Application sharing is allowed in the meeting</span></span>        |
|<span data-ttu-id="d0538-302">**無効**</span><span class="sxs-lookup"><span data-stu-id="d0538-302">**Disabled**</span></span>     |<span data-ttu-id="d0538-303">会議では画面共有とアプリケーション共有が無効になります。</span><span class="sxs-lookup"><span data-stu-id="d0538-303">Screen sharing and application sharing turned off in the meeting.</span></span>       |

<span data-ttu-id="d0538-304">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="d0538-304">Let's look at the following example.</span></span>

|<span data-ttu-id="d0538-305">ユーザー</span><span class="sxs-lookup"><span data-stu-id="d0538-305">User</span></span> |<span data-ttu-id="d0538-306">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="d0538-306">Meeting policy</span></span> |<span data-ttu-id="d0538-307">画面共有モード</span><span class="sxs-lookup"><span data-stu-id="d0538-307">Screen sharing mode</span></span> |
|---------|---------|---------|
|<span data-ttu-id="d0538-308">Daniela</span><span class="sxs-lookup"><span data-stu-id="d0538-308">Daniela</span></span>  | <span data-ttu-id="d0538-309">グローバル</span><span class="sxs-lookup"><span data-stu-id="d0538-309">Global</span></span>   | <span data-ttu-id="d0538-310">画面全体</span><span class="sxs-lookup"><span data-stu-id="d0538-310">Entire screen</span></span> |
|<span data-ttu-id="d0538-311">Amanda</span><span class="sxs-lookup"><span data-stu-id="d0538-311">Amanda</span></span>   | <span data-ttu-id="d0538-312">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="d0538-312">Location1MeetingPolicy</span></span>  | <span data-ttu-id="d0538-313">無効</span><span class="sxs-lookup"><span data-stu-id="d0538-313">Disabled</span></span> |

<span data-ttu-id="d0538-314">Daniela が開催する会議では、会議の参加者が画面全体または特定のアプリケーションを共有できます。</span><span class="sxs-lookup"><span data-stu-id="d0538-314">Meetings hosted by Daniela allow meeting participants to share their entire screen or a specific application.</span></span> <span data-ttu-id="d0538-315">Amanda が Daniela の会議に参加している場合は、そのポリシー設定が無効になっているために、Amanda が自分の画面や特定のアプリケーションを共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="d0538-315">If Amanda joins Daniela's meeting, Amanda can't share her screen or a specific application as her policy setting is disabled.</span></span> <span data-ttu-id="d0538-316">Amanda がホストする会議では、割り当てられた画面共有モード ポリシーに関係なく、誰も画面または単一のアプリケーションを共有できません。</span><span class="sxs-lookup"><span data-stu-id="d0538-316">In meetings hosted by Amanda, no one is allowed to share their screen or a single application, regardless of the screen sharing mode policy assigned to them.</span></span> <span data-ttu-id="d0538-317">これは、Daniela が Amanda の会議で、画面や単一のアプリケーションを共有できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="d0538-317">This means that Daniela can't share her screen or a single application in Amanda's meetings.</span></span>  

<span data-ttu-id="d0538-318">現在、ユーザーは Google Chrome を使用している場合、Teams 会議でビデオを再生したり画面を共有したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d0538-318">Currently, users can't play video or share their screen in a Teams meeting if they're using Google Chrome.</span></span>

### <a name="allow-a-participant-to-give-or-request-control"></a><span data-ttu-id="d0538-319">参加者に制御を渡す、または制御を要求する</span><span class="sxs-lookup"><span data-stu-id="d0538-319">Allow a participant to give or request control</span></span>

<span data-ttu-id="d0538-320">これは、ユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="d0538-320">This is a per-user policy.</span></span> <span data-ttu-id="d0538-321">この設定は、ユーザーが他の会議参加者に共有デスクトップまたはウィンドウの制御を渡すことができるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d0538-321">This setting controls whether the user can give control of the shared desktop or window to other meeting participants.</span></span> <span data-ttu-id="d0538-322">制御を渡すには、画面の上部にカーソルを合わせます。</span><span class="sxs-lookup"><span data-stu-id="d0538-322">To give control, hover over the top of the screen.</span></span>

<span data-ttu-id="d0538-323">ユーザーに対してこの設定が有効になっている場合、共有セッションの上部のバーに [**制御を渡す**] オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d0538-323">If this setting is turned on for the user, the **Give Control** option is displayed in the top bar in a sharing session.</span></span>

![[制御を渡す] オプションが表示されたスクリーンショット](media/meeting-policies-give-control.png)

<span data-ttu-id="d0538-325">ユーザーの設定が無効になっている場合、[**制御を渡す**] オプションは使用できません。</span><span class="sxs-lookup"><span data-stu-id="d0538-325">If the settings is turned off for the user, the **Give Control** option isn't available.</span></span>

![[制御を渡す] オプションが利用できないことを示すスクリーンショット](media/meeting-policies-give-control-not-available.png)

<span data-ttu-id="d0538-327">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="d0538-327">Let's look at the following example.</span></span>

|<span data-ttu-id="d0538-328">ユーザー</span><span class="sxs-lookup"><span data-stu-id="d0538-328">User</span></span> |<span data-ttu-id="d0538-329">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="d0538-329">Meeting policy</span></span>  |<span data-ttu-id="d0538-330">参加者に制御を渡す、または制御を要求する</span><span class="sxs-lookup"><span data-stu-id="d0538-330">Allow participant to give or request control</span></span> |
|---------|---------|---------|
|<span data-ttu-id="d0538-331">Daniela</span><span class="sxs-lookup"><span data-stu-id="d0538-331">Daniela</span></span>   | <span data-ttu-id="d0538-332">グローバル</span><span class="sxs-lookup"><span data-stu-id="d0538-332">Global</span></span>   | <span data-ttu-id="d0538-333">True</span><span class="sxs-lookup"><span data-stu-id="d0538-333">True</span></span>       |
|<span data-ttu-id="d0538-334">Babek</span><span class="sxs-lookup"><span data-stu-id="d0538-334">Babek</span></span>    | <span data-ttu-id="d0538-335">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="d0538-335">Location1MeetingPolicy</span></span>        | <span data-ttu-id="d0538-336">False</span><span class="sxs-lookup"><span data-stu-id="d0538-336">False</span></span>   |

<span data-ttu-id="d0538-337">Daniela は、Babek が開催する会議の他の参加者に共有デスクトップまたはウィンドウの制御を渡すことができますが、Babek は他の参加者に制御を渡すことができません。</span><span class="sxs-lookup"><span data-stu-id="d0538-337">Daniela can give control of the shared desktop or window to other participants in a meeting organized by Babek whereas Babek can't give control to other participants.</span></span>

<span data-ttu-id="d0538-338">制御を渡したり、制御要求を受け入れたりすることができるユーザーを PowerShell を使用して制御するには、AllowParticipantGiveRequestControl コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="d0538-338">To use PowerShell to control who can give control or accept requests for control, use the AllowParticipantGiveRequestControl cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="d0538-339">共有中に共有コンテンツの制御を渡したり受け取ったりするには、両者が Teams デスクトップ クライアントを使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0538-339">To give and take control of shared content during sharing, both parties must be using the Teams desktop client.</span></span> <span data-ttu-id="d0538-340">いずれかの当事者がブラウザーで Teams を実行している場合、制御はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="d0538-340">Control isn't supported when either party is running Teams in a browser.</span></span> <span data-ttu-id="d0538-341">これは、修正する予定の技術的制限によるものです。</span><span class="sxs-lookup"><span data-stu-id="d0538-341">This is due to a technical limitation that we're planning to fix.</span></span>

### <a name="allow-an-external-participant-to-give-or-request-control"></a><span data-ttu-id="d0538-342">外部の参加者に制御を渡す、または制御を要求する</span><span class="sxs-lookup"><span data-stu-id="d0538-342">Allow an external participant to give or request control</span></span>

<span data-ttu-id="d0538-343">これは、ユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="d0538-343">This is a per-user policy.</span></span> <span data-ttu-id="d0538-344">組織がユーザーに対してこのセットを持っているかどうかは、会議の開催者によって設定されているかどうかに関係なく、外部の参加者が実行できる操作を制御しません。</span><span class="sxs-lookup"><span data-stu-id="d0538-344">Whether an organization has this set for a user doesn't control what external participants can do, regardless of what the meeting organizer has set.</span></span> <span data-ttu-id="d0538-345">このパラメーターは、外部の参加者が、組織の会議のポリシーに設定されている内容に応じて、共有元の画面の制御を付与できるか、制御を要求するかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d0538-345">This parameter controls whether external participants can be given control or request control of the sharer's screen, depending on what the sharer has set within their organization's meeting policies.</span></span> <span data-ttu-id="d0538-346">Teams 会議の外部参加者は、次のように分類できます。</span><span class="sxs-lookup"><span data-stu-id="d0538-346">External participants in Teams meetings can be categorized as follows:</span></span>  

- <span data-ttu-id="d0538-347">匿名ユーザー</span><span class="sxs-lookup"><span data-stu-id="d0538-347">Anonymous user</span></span>
- <span data-ttu-id="d0538-348">ゲスト ユーザー</span><span class="sxs-lookup"><span data-stu-id="d0538-348">Guest users</span></span>  
- <span data-ttu-id="d0538-349">B2B ユーザー</span><span class="sxs-lookup"><span data-stu-id="d0538-349">B2B user</span></span>
- <span data-ttu-id="d0538-350">フェデレーション ユーザー</span><span class="sxs-lookup"><span data-stu-id="d0538-350">Federated user</span></span>  

<span data-ttu-id="d0538-351">フェデレーション ユーザーが共有中に外部ユーザーに制御を渡すことができるかどうかは、組織の「**外部の参加者に制御を渡す、または制御を要求する**」設定によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="d0538-351">Whether federated users can give control to external users while sharing is controlled by the **Allow an external participant to give or request control** setting in their organization.</span></span>

<span data-ttu-id="d0538-352">PowerShell を使用して、外部の参加者が制御を渡すことができるか、または制御要求を受け入れることができるかを制御するには、AllowExternalParticipantGiveRequestControl コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="d0538-352">To use PowerShell to control whether external participants can give control or accept requests for control, use the AllowExternalParticipantGiveRequestControl cmdlet.</span></span>

### <a name="allow-powerpoint-sharing"></a><span data-ttu-id="d0538-353">PowerPoint の共有を許可する</span><span class="sxs-lookup"><span data-stu-id="d0538-353">Allow PowerPoint sharing</span></span>

<span data-ttu-id="d0538-354">これは、ユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="d0538-354">This is a per-user policy.</span></span> <span data-ttu-id="d0538-355">この設定は、ユーザーが会議で PowerPoint スライド セットを共有できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d0538-355">This setting controls whether the user can share PowerPoint slide decks in a meeting.</span></span> <span data-ttu-id="d0538-356">匿名ユーザー、ゲスト ユーザー、フェデレーション ユーザーを含む外部ユーザーは、会議開催者のポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="d0538-356">External users, including anonymous, guest, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="d0538-357">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="d0538-357">Let's look at the following example.</span></span>

|<span data-ttu-id="d0538-358">ユーザー</span><span class="sxs-lookup"><span data-stu-id="d0538-358">User</span></span> |<span data-ttu-id="d0538-359">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="d0538-359">Meeting policy</span></span>  |<span data-ttu-id="d0538-360">PowerPoint の共有を許可する</span><span class="sxs-lookup"><span data-stu-id="d0538-360">Allow PowerPoint sharing</span></span> |
|---------|---------|---------|
|<span data-ttu-id="d0538-361">Daniela</span><span class="sxs-lookup"><span data-stu-id="d0538-361">Daniela</span></span>   | <span data-ttu-id="d0538-362">グローバル</span><span class="sxs-lookup"><span data-stu-id="d0538-362">Global</span></span>   | <span data-ttu-id="d0538-363">True</span><span class="sxs-lookup"><span data-stu-id="d0538-363">True</span></span>       |
|<span data-ttu-id="d0538-364">Amanda</span><span class="sxs-lookup"><span data-stu-id="d0538-364">Amanda</span></span>   | <span data-ttu-id="d0538-365">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="d0538-365">Location1MeetingPolicy</span></span>        | <span data-ttu-id="d0538-366">False</span><span class="sxs-lookup"><span data-stu-id="d0538-366">False</span></span>   |

<span data-ttu-id="d0538-367">Amanda は、会議の開催者であっても、PowerPoint スライド セットを会議で共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="d0538-367">Amanda can't share PowerPoint slide decks in meetings even if she's the meeting organizer.</span></span> <span data-ttu-id="d0538-368">Daniela は、会議が Amanda によって開催されている場合でも、PowerPoint スライド セットを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="d0538-368">Daniela can share PowerPoint slide decks even if the meeting is organized by Amanda.</span></span> <span data-ttu-id="d0538-369">Amanda は、PowerPoint スライド セットを共有できない場合でも、会議の他のユーザーによって共有されている PowerPoint スライド セットを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="d0538-369">Amanda can view the PowerPoint slide decks shared by others in the meeting, even though she can't share PowerPoint slide decks.</span></span>

### <a name="allow-whiteboard"></a><span data-ttu-id="d0538-370">ホワイトボードを許可する</span><span class="sxs-lookup"><span data-stu-id="d0538-370">Allow whiteboard</span></span>

<span data-ttu-id="d0538-371">これは、ユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="d0538-371">This is a per-user policy.</span></span> <span data-ttu-id="d0538-372">この設定は、ユーザーが会議でホワイトボードを共有できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d0538-372">This setting controls whether a user can share the whiteboard in a meeting.</span></span> <span data-ttu-id="d0538-373">匿名ユーザー、B2B ユーザー、およびフェデレーション ユーザーを含む外部ユーザーは、会議開催者のポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="d0538-373">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="d0538-374">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="d0538-374">Let's look at the following example.</span></span>

|<span data-ttu-id="d0538-375">ユーザー</span><span class="sxs-lookup"><span data-stu-id="d0538-375">User</span></span> |<span data-ttu-id="d0538-376">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="d0538-376">Meeting policy</span></span>  |<span data-ttu-id="d0538-377">ホワイトボードを許可する</span><span class="sxs-lookup"><span data-stu-id="d0538-377">Allow whiteboard</span></span>|
|---------|---------|---------|
|<span data-ttu-id="d0538-378">Daniela</span><span class="sxs-lookup"><span data-stu-id="d0538-378">Daniela</span></span>   | <span data-ttu-id="d0538-379">グローバル</span><span class="sxs-lookup"><span data-stu-id="d0538-379">Global</span></span>   | <span data-ttu-id="d0538-380">True</span><span class="sxs-lookup"><span data-stu-id="d0538-380">True</span></span>       |
|<span data-ttu-id="d0538-381">Amanda</span><span class="sxs-lookup"><span data-stu-id="d0538-381">Amanda</span></span>   | <span data-ttu-id="d0538-382">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="d0538-382">Location1MeetingPolicy</span></span>        | <span data-ttu-id="d0538-383">False</span><span class="sxs-lookup"><span data-stu-id="d0538-383">False</span></span>   |

<span data-ttu-id="d0538-384">Amanda は、会議の開催者であっても、会議でホワイトボードを共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="d0538-384">Amanda can't share the whiteboard in a meeting even if she's the meeting organizer.</span></span> <span data-ttu-id="d0538-385">Daniela は、Amanda が会議を開催する場合でも、ホワイトボードを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="d0538-385">Daniela can share the whiteboard even if a meeting is organized by Amanda.</span></span>  

### <a name="allow-shared-notes"></a><span data-ttu-id="d0538-386">メモの共有を許可する</span><span class="sxs-lookup"><span data-stu-id="d0538-386">Allow shared notes</span></span>

<span data-ttu-id="d0538-387">これは、ユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="d0538-387">This is a per-user policy.</span></span> <span data-ttu-id="d0538-388">この設定は、ユーザーが会議でメモを作成および共有できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d0538-388">This setting controls whether a user can create and share notes in a meeting.</span></span> <span data-ttu-id="d0538-389">匿名ユーザー、B2B ユーザー、およびフェデレーション ユーザーを含む外部ユーザーは、会議開催者のポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="d0538-389">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> <span data-ttu-id="d0538-390">現在、[**会議メモ**] タブは、参加者が 20 人未満の会議でのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d0538-390">The **Meeting Notes** tab is currently only supported in meetings that have less than 20 participants.</span></span>

<span data-ttu-id="d0538-391">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="d0538-391">Let's look at the following example.</span></span>

|<span data-ttu-id="d0538-392">ユーザー</span><span class="sxs-lookup"><span data-stu-id="d0538-392">User</span></span> |<span data-ttu-id="d0538-393">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="d0538-393">Meeting policy</span></span>  |<span data-ttu-id="d0538-394">メモの共有を許可する</span><span class="sxs-lookup"><span data-stu-id="d0538-394">Allow shared notes</span></span> |
|---------|---------|---------|
|<span data-ttu-id="d0538-395">Daniela</span><span class="sxs-lookup"><span data-stu-id="d0538-395">Daniela</span></span>   | <span data-ttu-id="d0538-396">グローバル</span><span class="sxs-lookup"><span data-stu-id="d0538-396">Global</span></span>   | <span data-ttu-id="d0538-397">True</span><span class="sxs-lookup"><span data-stu-id="d0538-397">True</span></span>       |
|<span data-ttu-id="d0538-398">Amanda</span><span class="sxs-lookup"><span data-stu-id="d0538-398">Amanda</span></span>   | <span data-ttu-id="d0538-399">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="d0538-399">Location1MeetingPolicy</span></span> | <span data-ttu-id="d0538-400">False</span><span class="sxs-lookup"><span data-stu-id="d0538-400">False</span></span> |

<span data-ttu-id="d0538-401">Daniela は Amanda の会議でメモを取ることができ、Amanda はすべての会議でメモを取ることができません。</span><span class="sxs-lookup"><span data-stu-id="d0538-401">Daniela can take notes in Amanda's meetings and Amanda can't take notes in any meetings.</span></span>

## <a name="meeting-policy-settings---participants--guests"></a><span data-ttu-id="d0538-402">会議ポリシーの設定 - 参加者とゲスト</span><span class="sxs-lookup"><span data-stu-id="d0538-402">Meeting policy settings - Participants & guests</span></span>

<span data-ttu-id="d0538-403">これらの設定では、会議への入室が許可されるまでロビーで待機する必要がある会議参加者およびそれらの参加者に許可する会議への参加レベルが制御されます。</span><span class="sxs-lookup"><span data-stu-id="d0538-403">These settings control which meeting participants wait in the lobby before they are admitted to the meeting and the level of participation they are allowed in a meeting.</span></span>

- [<span data-ttu-id="d0538-404">匿名ユーザーが会議を開始できるようにする</span><span class="sxs-lookup"><span data-stu-id="d0538-404">Let anonymous people start a meeting</span></span>](#let-anonymous-people-start-a-meeting)
- [<span data-ttu-id="d0538-405">ユーザーの参加を自動的に許可する</span><span class="sxs-lookup"><span data-stu-id="d0538-405">Automatically admit people</span></span>](#automatically-admit-people)
- [<span data-ttu-id="d0538-406">ダイヤルイン ユーザーによるロビーのバイパスを許可する</span><span class="sxs-lookup"><span data-stu-id="d0538-406">Allow dial-in users to bypass the lobby</span></span>](#allow-dial-in-users-to-bypass-the-lobby)
- [<span data-ttu-id="d0538-407">ライブ キャプションを有効にする</span><span class="sxs-lookup"><span data-stu-id="d0538-407">Enable live captions</span></span>](#enable-live-captions)
- [<span data-ttu-id="d0538-408">会議でチャットを許可する</span><span class="sxs-lookup"><span data-stu-id="d0538-408">Allow chat in meetings</span></span>](#allow-chat-in-meetings)

> [!NOTE]
><span data-ttu-id="d0538-409">会議に参加するためのオプションは、各 Teams グループの設定および接続方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="d0538-409">Options to join a meeting will vary, depending on the settings for each Teams group, and the connection method.</span></span> <span data-ttu-id="d0538-410">グループに電話会議があり、それを使用して接続する場合は、「 [電話会議](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0538-410">If your group has audio conferencing, and uses it to connect, see [Audio Conferencing](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span></span> <span data-ttu-id="d0538-411">Teams グループに電話会議がない場合は、「[Teams での会議に参加する](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0538-411">If your Teams group does not have audio conferencing, refer to [Join a meeting in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).</span></span>

### <a name="let-anonymous-people-start-a-meeting"></a><span data-ttu-id="d0538-412">匿名ユーザーが会議を開始できるようにする</span><span class="sxs-lookup"><span data-stu-id="d0538-412">Let anonymous people start a meeting</span></span>

<span data-ttu-id="d0538-413">これは開催者単位のポリシーであり、会議の leaderless でダイヤルすることができます。</span><span class="sxs-lookup"><span data-stu-id="d0538-413">This is a per-organizer policy that allows for leaderless dial in conferencing meetings.</span></span> <span data-ttu-id="d0538-414">この設定は、ユーザーが会議に参加できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d0538-414">This setting controls whether dial in users can join the meeting without an authenticated user from the organization in attendance.</span></span> <span data-ttu-id="d0538-415">既定値は False であり、ダイヤルインユーザーは、組織から認証されたユーザーが会議に参加するまでロビーで待機することになります。</span><span class="sxs-lookup"><span data-stu-id="d0538-415">The default value is False which means dial in users will wait in the lobby until an authenticated user from the organization joins the meeting.</span></span>

<span data-ttu-id="d0538-416">**注** False で、ダイヤルインユーザーが最初に会議に参加し、ロビーに配置されている場合、組織のユーザーは、ロビーからユーザーを許可するためにチームクライアントとの会議に参加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0538-416">**Note** If False and a dial in user joins the meeting first and is placed in the lobby, an organization user must join the meeting with a Teams client to admit the user from the lobby.</span></span> <span data-ttu-id="d0538-417">ユーザーのダイヤルに使用できるロビーコントロールはありません。</span><span class="sxs-lookup"><span data-stu-id="d0538-417">There are no lobby controls available for dialed in users.</span></span>

### <a name="automatically-admit-people"></a><span data-ttu-id="d0538-418">ユーザーの参加を自動的に許可する</span><span class="sxs-lookup"><span data-stu-id="d0538-418">Automatically admit people</span></span>

<span data-ttu-id="d0538-419">これは開催者単位のポリシーです。</span><span class="sxs-lookup"><span data-stu-id="d0538-419">This is a per-organizer policy.</span></span> <span data-ttu-id="d0538-420">この設定は、ユーザーが会議に直接参加するのか、認証ユーザーにより入室が許可されるまでロビーで待機するのかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d0538-420">This setting controls whether people join a meeting directly or wait in the lobby until they are admitted by an authenticated user.</span></span> <span data-ttu-id="d0538-421">この設定は、ダイヤルインユーザーには適用されません。</span><span class="sxs-lookup"><span data-stu-id="d0538-421">This setting does not apply to dial in users.</span></span>

![ロビーにいるユーザーとの会議を示すスクリーンショット](media/meeting-policies-lobby.png)

 <span data-ttu-id="d0538-423">会議の開催者は、会議出席依頼の [**会議オプション**] をクリックして、スケジュールする会議ごとにこの設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="d0538-423">Meeting organizers can click **Meeting Options** in the meeting invitation to change this setting for each meeting they schedule.</span></span>

 <span data-ttu-id="d0538-424">**注** 会議オプションの設定には、"ロビーをバイパスできるユーザー" のラベルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d0538-424">**Note** In the meeting options the setting is labeled "Who can bypass the lobby"</span></span>
  
|<span data-ttu-id="d0538-425">値を設定する</span><span class="sxs-lookup"><span data-stu-id="d0538-425">Setting value</span></span>  |<span data-ttu-id="d0538-426">参加動作</span><span class="sxs-lookup"><span data-stu-id="d0538-426">Join behavior</span></span> |
|---------|---------|
|<span data-ttu-id="d0538-427">**すべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="d0538-427">**Everyone**</span></span>   |<span data-ttu-id="d0538-428">すべての会議参加者は、ロビーで待たずに会議に直接参加します。</span><span class="sxs-lookup"><span data-stu-id="d0538-428">All meeting participants join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="d0538-429">認証済みのユーザー、信頼された組織の外部ユーザー (フェデレーション)、ゲスト、匿名ユーザーなどが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d0538-429">This includes authenticated users, external users from trusted organizations (federated), guests, and anonymous users.</span></span>     |
|<span data-ttu-id="d0538-430">**組織内およびフェデレーション組織のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="d0538-430">**Everyone in your organization and federated organizations**</span></span>     |<span data-ttu-id="d0538-431">組織内で認証されたユーザー (ゲストユーザーや信頼できる組織のユーザーを含む) は、ロビーで待機することなく直接会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="d0538-431">Authenticated users within the organization, including guest users and the users from trusted organizations, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="d0538-432">匿名ユーザーがロビーで待機しています。</span><span class="sxs-lookup"><span data-stu-id="d0538-432">Anonymous users wait in the lobby.</span></span>   |
|<span data-ttu-id="d0538-433">**組織内のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="d0538-433">**Everyone in your organization**</span></span>    |<span data-ttu-id="d0538-434">ゲスト ユーザーを含む組織内の認証ユーザーは、ロビーで待たずに会議に直接参加します。</span><span class="sxs-lookup"><span data-stu-id="d0538-434">Authenticated users from within the organization, including guest users, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="d0538-435">信頼された組織および匿名ユーザーのユーザーは、ロビーで待機します。</span><span class="sxs-lookup"><span data-stu-id="d0538-435">Users from trusted organizations and anonymous users wait in the lobby.</span></span> <span data-ttu-id="d0538-436">これは、既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="d0538-436">This is the default setting.</span></span>           |

### <a name="allow-dial-in-users-to-bypass-the-lobby"></a><span data-ttu-id="d0538-437">ダイヤルイン ユーザーによるロビーのバイパスを許可する</span><span class="sxs-lookup"><span data-stu-id="d0538-437">Allow dial-in users to bypass the lobby</span></span>

<span data-ttu-id="d0538-438">これは開催者単位のポリシーです。</span><span class="sxs-lookup"><span data-stu-id="d0538-438">This is a per-organizer policy.</span></span> <span data-ttu-id="d0538-439">この設定では、スマートフォンでダイヤル インするユーザーが会議に直接参加するのか、[**ユーザーの参加を自動的に許可する**] の設定に関わらずロビーで待機するのかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d0538-439">This setting controls whether people who dial in by phone join the meeting directly or wait in the lobby regardless of the **Automatically admit people** setting.</span></span> <span data-ttu-id="d0538-440">既定値は False です。</span><span class="sxs-lookup"><span data-stu-id="d0538-440">The default value is False.</span></span> <span data-ttu-id="d0538-441">False の場合、ユーザーは、組織のユーザーがチームクライアントと会議に参加し、そのメンバーを許可するまで、ロビーで待機します。</span><span class="sxs-lookup"><span data-stu-id="d0538-441">When False, dial in users will wait in the lobby until a organization user joins the meeting with a Teams client and admits them.</span></span> <span data-ttu-id="d0538-442">True の場合、組織のユーザーが会議に参加すると、ダイヤルインユーザーは自動的に会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="d0538-442">When True, dial in users will automatically join the meeting when an organization user joins the meeting.</span></span>

<span data-ttu-id="d0538-443">**注** ダイヤルインユーザーが会議に参加する前に、組織のユーザーが会議に参加すると、組織のユーザーがチームクライアントを使って会議に参加し、それを管理するまで、そのユーザーはロビーに配置されます。</span><span class="sxs-lookup"><span data-stu-id="d0538-443">**Note** If a dial in user joins a meeting before an organization user joins the meeting, they will be placed in the lobby until an organization user joins the meeting using a Teams client and admits them.</span></span>

### <a name="enable-live-captions"></a><span data-ttu-id="d0538-444">ライブ キャプションを有効にする</span><span class="sxs-lookup"><span data-stu-id="d0538-444">Enable live captions</span></span>

<span data-ttu-id="d0538-445">これはユーザーごとのポリシーであり、会議中に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d0538-445">This is a per-user policy and applies during a meeting.</span></span> <span data-ttu-id="d0538-446">この設定は、ユーザーが参加する会議でライブ キャプションを有効または無効にするために、[**ライブ キャプションを有効にする**] オプションを使用できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d0538-446">This setting controls whether the **Turn on live captions** option is available for the user to turn on and turn off live captions in meetings that the user attends.</span></span>  

![[ライブ キャプションを有効にする] オプションが表示されたスクリーンショット](media/meeting-policies-live-captions.png)

|<span data-ttu-id="d0538-448">値を設定する</span><span class="sxs-lookup"><span data-stu-id="d0538-448">Setting value</span></span> |<span data-ttu-id="d0538-449">動作</span><span class="sxs-lookup"><span data-stu-id="d0538-449">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="d0538-450">**無効。ただし、ユーザーは上書きできます。**</span><span class="sxs-lookup"><span data-stu-id="d0538-450">**Disabled but the user can override**</span></span>     | <span data-ttu-id="d0538-451">会議中にユーザーのライブ キャプションが自動的に有効になることはありません。</span><span class="sxs-lookup"><span data-stu-id="d0538-451">Live captions aren't automatically turned on for the user during a meeting.</span></span> <span data-ttu-id="d0538-452">オーバーフロー (**...**) メニューに [**ライブ キャプションを有効にする**] オプションが表示され、それらを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d0538-452">The user sees the **Turn on live captions** option in the overflow (**...**) menu to turn them on.</span></span> <span data-ttu-id="d0538-453">これは、既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="d0538-453">This is the default setting.</span></span> |
|<span data-ttu-id="d0538-454">**無効**</span><span class="sxs-lookup"><span data-stu-id="d0538-454">**Disabled**</span></span>     | <span data-ttu-id="d0538-455">会議中、ユーザーのライブ キャプションが無効になります。</span><span class="sxs-lookup"><span data-stu-id="d0538-455">Live captions are disabled for the user during a meeting.</span></span> <span data-ttu-id="d0538-456">ユーザーには、それらを有効にするオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="d0538-456">The user doesn't have the option to turn them on.</span></span>          |

<span data-ttu-id="d0538-457"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="d0538-457"><a name="bkcontentsharing"> </a></span></span>

### <a name="allow-chat-in-meetings"></a><span data-ttu-id="d0538-458">会議でチャットを許可する</span><span class="sxs-lookup"><span data-stu-id="d0538-458">Allow chat in meetings</span></span>

<span data-ttu-id="d0538-459">これは開催者単位のポリシーです。</span><span class="sxs-lookup"><span data-stu-id="d0538-459">This is a per-organizer policy.</span></span> <span data-ttu-id="d0538-460">この設定は、ユーザーの会議で会議チャットを許可するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d0538-460">This setting controls whether meeting chat is allowed in the user's meeting.</span></span>

<span data-ttu-id="d0538-461"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="d0538-461"><a name="bkparticipantsandguests"> </a></span></span>

## <a name="meeting-policy-settings---designated-presenter-role-mode"></a><span data-ttu-id="d0538-462">会議ポリシー設定-指定されたプレゼンターロールモード</span><span class="sxs-lookup"><span data-stu-id="d0538-462">Meeting policy settings - Designated presenter role mode</span></span>

<span data-ttu-id="d0538-463">これは、ユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="d0538-463">This is a per-user policy.</span></span> <span data-ttu-id="d0538-464">この設定では、Teams クライアントの [**会議オプション**] の設定を変更する**こと**ができます。</span><span class="sxs-lookup"><span data-stu-id="d0538-464">This setting lets you change the default value of the **Who can present?** setting in **Meeting options** in the Teams client.</span></span> <span data-ttu-id="d0538-465">このポリシー設定は、[今すぐ会議] を含むすべての会議に影響します。</span><span class="sxs-lookup"><span data-stu-id="d0538-465">This policy setting affects all meetings, including Meet Now meetings.</span></span>

<span data-ttu-id="d0538-466">[ **発表者]** : 会議の開催者が会議で発表者になれるユーザーを選択できるように設定します。</span><span class="sxs-lookup"><span data-stu-id="d0538-466">The **Who can present?** setting lets meeting organizers choose who can be presenters in a meeting.</span></span> <span data-ttu-id="d0538-467">詳細については、「teams 会議のチーム会議と[ロール](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019)[の参加者設定を変更](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0538-467">To learn more, see [Change participant settings for a Teams meeting](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) and [Roles in a Teams meeting](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019).</span></span>

<span data-ttu-id="d0538-468">現時点では、このポリシー設定を構成するには PowerShell を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0538-468">Currently, you can only use PowerShell to configure this policy setting.</span></span> <span data-ttu-id="d0538-469">[CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)コマンドレットを使用して、既存の Teams 会議ポリシーを編集できます。</span><span class="sxs-lookup"><span data-stu-id="d0538-469">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="d0538-470">または、 [CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) コマンドレットを使用して新しいチーム会議ポリシーを作成し、ユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d0538-470">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="d0538-471">Teams で [ **表示できるユーザー]** の既定値を指定するには、 **Designatedpresenterrolemode** パラメーターを次のいずれかに設定します。</span><span class="sxs-lookup"><span data-stu-id="d0538-471">To specify the default value of the **Who can present?** setting in Teams, set the **DesignatedPresenterRoleMode** parameter to one of the following:</span></span>

- <span data-ttu-id="d0538-472">すべてのユーザーの**上書き**: すべての会議参加者を発表者にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d0538-472">**EveryoneUserOverride**:  All meeting participants can be presenters.</span></span> <span data-ttu-id="d0538-473">これは既定の値です。</span><span class="sxs-lookup"><span data-stu-id="d0538-473">This is the default value.</span></span> <span data-ttu-id="d0538-474">このパラメーターは、Teams の [ **すべてのユーザー** ] 設定に対応します。</span><span class="sxs-lookup"><span data-stu-id="d0538-474">This parameter corresponds to the **Everyone** setting in Teams.</span></span>
- <span data-ttu-id="d0538-475">すべてのユーザーの**上書き**: ゲストユーザーを含む、組織内の認証済みユーザーは発表者になることができます。</span><span class="sxs-lookup"><span data-stu-id="d0538-475">**EveryoneInCompanyUserOverride**: Authenticated users in the organization, including guest users, can be presenters.</span></span> <span data-ttu-id="d0538-476">このパラメーターは、Teams の **[組織内のユーザー** ] 設定に対応します。</span><span class="sxs-lookup"><span data-stu-id="d0538-476">This parameter corresponds to the **People in my organization** setting in Teams.</span></span>
- <span data-ttu-id="d0538-477">構成内容の**上書き**: 会議の開催者のみが発表者になり、すべての会議参加者が出席者として指定されます。</span><span class="sxs-lookup"><span data-stu-id="d0538-477">**OrganizerOnlyUserOverride**: Only the meeting organizer can be a presenter and all meeting participants are designated as attendees.</span></span> <span data-ttu-id="d0538-478">このパラメーターは、Teams の [ **自分のみ** ] の設定に対応しています。</span><span class="sxs-lookup"><span data-stu-id="d0538-478">This parameter corresponds to the **Only me** setting in Teams.</span></span>

<span data-ttu-id="d0538-479">既定値を設定した後でも、会議の開催者は Teams でこの設定を変更することができ、スケジュールした会議で発表できるユーザーを選択することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d0538-479">Keep in mind that after you set the default value, meeting organizers can still change this setting in Teams and choose who can present in the meetings that they schedule.</span></span>

## <a name="meeting-policy-settings---meeting-attendance-report"></a><span data-ttu-id="d0538-480">会議のポリシー設定-会議出席依頼のレポート</span><span class="sxs-lookup"><span data-stu-id="d0538-480">Meeting policy settings - Meeting attendance report</span></span>

<span data-ttu-id="d0538-481">これは、ユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="d0538-481">This is a per-user policy.</span></span> <span data-ttu-id="d0538-482">この設定は、会議の開催者が [会議出席の参加者レポート](teams-analytics-and-reports/meeting-attendance-report.md)をダウンロードできるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d0538-482">This setting controls whether meeting organizers can download the [meeting attendance report](teams-analytics-and-reports/meeting-attendance-report.md).</span></span>

<span data-ttu-id="d0538-483">現時点では、このポリシー設定を構成するには PowerShell を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0538-483">Currently, you can only use PowerShell to configure this policy setting.</span></span> <span data-ttu-id="d0538-484">[CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)コマンドレットを使用して、既存の Teams 会議ポリシーを編集できます。</span><span class="sxs-lookup"><span data-stu-id="d0538-484">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="d0538-485">または、 [CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) コマンドレットを使用して新しいチーム会議ポリシーを作成し、ユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d0538-485">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="d0538-486">会議の開催者が会議の出席レポートをダウンロードできるようにするには、 **AllowEngagementReport** パラメーターを [ **有効**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="d0538-486">To enable a meeting organizer to download the meeting attendance report, set the **AllowEngagementReport** parameter  to **Enabled**.</span></span> <span data-ttu-id="d0538-487">有効にした場合、レポートをダウンロードするオプションが [ **参加者** ] ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d0538-487">When enabled, the option to download the report is displayed in the **Participants** pane.</span></span>

<span data-ttu-id="d0538-488">会議の開催者がレポートをダウンロードできないようにするには、パラメーターを [ **無効**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="d0538-488">To prevent a meeting organizer from downloading the report, set the parameter to **Disabled**.</span></span> <span data-ttu-id="d0538-489">既定では、この設定は無効であり、レポートをダウンロードするためのオプションは使用できません。</span><span class="sxs-lookup"><span data-stu-id="d0538-489">By default, this setting is disabled and the option to download the report isn't available.</span></span>

## <a name="meeting-policy-settings---meeting-provider-for-islands-mode"></a><span data-ttu-id="d0538-490">会議ポリシーの設定-諸島モードの会議プロバイダー</span><span class="sxs-lookup"><span data-stu-id="d0538-490">Meeting policy settings - Meeting provider for Islands mode</span></span>

<span data-ttu-id="d0538-491">これは、ユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="d0538-491">This is a per-user policy.</span></span> <span data-ttu-id="d0538-492">この設定は、 *孤島モードのユーザー*が使用する Outlook 会議アドインを制御します。</span><span class="sxs-lookup"><span data-stu-id="d0538-492">This setting controls which Outlook meeting add-in is used for *users who are in Islands mode*.</span></span> <span data-ttu-id="d0538-493">Teams 会議アドインのみを使用するか、Teams 会議アドインと Skype for Business 会議アドインの両方を使用するかを指定して、Outlook で会議をスケジュールできます。</span><span class="sxs-lookup"><span data-stu-id="d0538-493">You can specify whether users can only use the Teams Meeting add-in or both the Teams Meeting and Skype for Business Meeting add-ins to schedule meetings in Outlook.</span></span>

<span data-ttu-id="d0538-494">このポリシーは、アイランドモードで、Teams の会議ポリシーで **AllowOutlookAddIn** パラメーターが **True** に設定されているユーザーにのみ適用できます。</span><span class="sxs-lookup"><span data-stu-id="d0538-494">You can only apply this policy to users who are in Islands mode and have the **AllowOutlookAddIn** parameter set to **True** in their Teams meeting policy.</span></span>

<span data-ttu-id="d0538-495">現在、PowerShell を使ってこのポリシーを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="d0538-495">Currently, you can only use PowerShell to set this policy.</span></span> <span data-ttu-id="d0538-496">[CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)コマンドレットを使用して、既存の Teams 会議ポリシーを編集できます。</span><span class="sxs-lookup"><span data-stu-id="d0538-496">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="d0538-497">または、 [CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) コマンドレットを使用して新しいチーム会議ポリシーを作成し、ユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d0538-497">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="d0538-498">ユーザーが使用できるようにする会議アドインを指定するには、次のように **PreferredMeetingProviderForIslandsMode** パラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="d0538-498">To specify which meeting add-in you want to be available to users, set the **PreferredMeetingProviderForIslandsMode** parameter as follows:</span></span>

- <span data-ttu-id="d0538-499">Outlook で Teams 会議アドインと Skype for Business アドインの両方を有効にするには、パラメーターを **TeamsAndSfB** に設定します。</span><span class="sxs-lookup"><span data-stu-id="d0538-499">Set the parameter to **TeamsAndSfB** to enable both the Teams Meeting add-in and Skype for Business add-in in Outlook.</span></span> <span data-ttu-id="d0538-500">これは既定の値です。</span><span class="sxs-lookup"><span data-stu-id="d0538-500">This is the default value.</span></span>
- <span data-ttu-id="d0538-501">このパラメーターを [ **teams** ] に設定して、Outlook で teams 会議アドインのみを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d0538-501">Set the parameter to **Teams** to enable only the Teams Meeting add-in in Outlook.</span></span> <span data-ttu-id="d0538-502">このポリシー設定では、今後のすべての会議に Teams の会議参加リンクを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="d0538-502">This policy setting ensures that all future meetings have a Teams meeting join link.</span></span> <span data-ttu-id="d0538-503">既存の Skype for Business 会議の参加リンクは Teams に移行されません。</span><span class="sxs-lookup"><span data-stu-id="d0538-503">It doesn't migrate existing Skype for Business meeting join links to Teams.</span></span> <span data-ttu-id="d0538-504">このポリシー設定は、プレゼンス、チャット、PSTN 通話、または Skype for Business のその他の機能には影響しません。つまり、ユーザーはこれらの機能に対して引き続き Skype for Business を使用することになります。</span><span class="sxs-lookup"><span data-stu-id="d0538-504">This policy setting doesn't affect presence, chat, PSTN calling, or any other capabilities in Skype for Business, which means that users will continue to use Skype for Business for these capabilities.</span></span>

  <span data-ttu-id="d0538-505">このパラメーターを **Teams**に設定してから、 **TeamsAndSfB**に戻すと、両方の会議アドインが有効になります。</span><span class="sxs-lookup"><span data-stu-id="d0538-505">If you set the parameter to **Teams**, and then switch back to **TeamsAndSfB**, both meeting add-ins are enabled.</span></span> <span data-ttu-id="d0538-506">ただし、既存の Teams 会議の参加リンクは Skype for Business に移行されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d0538-506">However, note that existing Teams meeting join links won't be migrated to Skype for Business.</span></span> <span data-ttu-id="d0538-507">変更後にスケジュールされた Skype for Business 会議のみが、Skype for Business 会議の参加リンクになります。</span><span class="sxs-lookup"><span data-stu-id="d0538-507">Only Skype for Business meetings scheduled after the change will have a Skype for Business meeting join link.</span></span>

## <a name="meeting-policy-settings---video-filters-mode"></a><span data-ttu-id="d0538-508">会議のポリシー設定-ビデオフィルターモード</span><span class="sxs-lookup"><span data-stu-id="d0538-508">Meeting policy settings - Video filters mode</span></span>

<span data-ttu-id="d0538-509">これは、ユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="d0538-509">This is a per-user policy.</span></span> <span data-ttu-id="d0538-510">この設定は、ユーザーが会議でビデオの背景をカスタマイズできるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d0538-510">This setting controls whether users can customize their video background in a meeting.</span></span>

<span data-ttu-id="d0538-511">現在、PowerShell を使ってこのポリシーを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="d0538-511">Currently, you can only use PowerShell to set this policy.</span></span> <span data-ttu-id="d0538-512">[CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)コマンドレットを使用して、既存の Teams 会議ポリシーを編集できます。</span><span class="sxs-lookup"><span data-stu-id="d0538-512">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="d0538-513">または、 [CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) コマンドレットを使用して新しいチーム会議ポリシーを作成し、ユーザーにポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d0538-513">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet, and then assign the policy to users.</span></span>

<span data-ttu-id="d0538-514">会議中にユーザーがビデオの背景をカスタマイズできるかどうかを指定するには、次のように **Videoフィルタモード** のパラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="d0538-514">To specify whether users can customize their video background in a meeting, set the **VideoFiltersMode** parameter as follows:</span></span>

|<span data-ttu-id="d0538-515">PowerShell での値の設定</span><span class="sxs-lookup"><span data-stu-id="d0538-515">Setting value in PowerShell</span></span> |<span data-ttu-id="d0538-516">動作</span><span class="sxs-lookup"><span data-stu-id="d0538-516">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="d0538-517">**NoFilters**</span><span class="sxs-lookup"><span data-stu-id="d0538-517">**NoFilters**</span></span>     |<span data-ttu-id="d0538-518">ユーザーはビデオの背景をカスタマイズできません。</span><span class="sxs-lookup"><span data-stu-id="d0538-518">User can't customize their video background.</span></span>|
|<span data-ttu-id="d0538-519">**BlurOnly**</span><span class="sxs-lookup"><span data-stu-id="d0538-519">**BlurOnly**</span></span>     |<span data-ttu-id="d0538-520">ユーザーには、ビデオの背景をぼかすオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="d0538-520">User has the option to blur their video background.</span></span> |
|<span data-ttu-id="d0538-521">**BlurandDefaultBackgrounds**</span><span class="sxs-lookup"><span data-stu-id="d0538-521">**BlurandDefaultBackgrounds**</span></span>     |<span data-ttu-id="d0538-522">ユーザーには、ビデオの背景をぼかすか、既定の画像セットから背景として使うかを選択するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="d0538-522">User has the option to blur their video background or choose from the default set of images to use as their background.</span></span> |
|<span data-ttu-id="d0538-523">**AllFilters**</span><span class="sxs-lookup"><span data-stu-id="d0538-523">**AllFilters**</span></span>     |<span data-ttu-id="d0538-524">[使用] では、ビデオの背景をぼかす、既定の画像セットから選ぶ、または背景として使用するカスタム画像をアップロードするオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="d0538-524">Use has the option to blur their video background, choose from the default set of images, or upload custom images to use as their background.</span></span> |

> [!NOTE]
> <span data-ttu-id="d0538-525">ユーザーによってアップロードされた画像は、Teams ではスクリーンされません。</span><span class="sxs-lookup"><span data-stu-id="d0538-525">Images uploaded by users aren't screened by Teams.</span></span> <span data-ttu-id="d0538-526">[ **Allfilters** ] 設定を使用すると、ユーザーが不快感を与える、または不適切な画像をアップロードすることを防止するための内部組織ポリシーが必要になります。また、組織が Teams 会議の背景に使用する権限を持っていない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="d0538-526">When you use the **AllFilters** setting, you should have internal organization policies to prevent users from uploading offensive or inappropriate images, or images your organization don't have rights to use for Teams meeting backgrounds.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d0538-527">関連項目</span><span class="sxs-lookup"><span data-stu-id="d0538-527">Related topics</span></span>

- [<span data-ttu-id="d0538-528">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="d0538-528">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="d0538-529">チームのユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="d0538-529">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="d0538-530">RestrictedAnonymousAccess Teams の会議ポリシーをユーザーから削除する</span><span class="sxs-lookup"><span data-stu-id="d0538-530">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)
