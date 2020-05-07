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
ms.openlocfilehash: 4a61d2563a63d2dc8d1b55bbf0bbc6c52230d900
ms.sourcegitcommit: c3f44fccdbd9178d30b52bb0db6f6d31a6dd174b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "44139211"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="d8879-103">Teams での会議ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="d8879-103">Manage meeting policies in Teams</span></span>

::: zone target="docs"
<span data-ttu-id="d8879-104">会議ポリシーは、組織内のユーザーによってスケジュールされた会議への参加者が利用できる機能を制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d8879-104">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="d8879-105">ポリシーを作成して変更を行った後、ユーザーをポリシーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="d8879-105">After you create a policy and make your changes, you can then assign users to the policy.</span></span> <span data-ttu-id="d8879-106">会議ポリシーは、Microsoft Teams 管理センターで管理するか、[PowerShell](teams-powershell-overview.md) を使用して管理します。</span><span class="sxs-lookup"><span data-stu-id="d8879-106">You manage meeting policies in the Microsoft Teams admin center or by using [PowerShell](teams-powershell-overview.md).</span></span>

<span data-ttu-id="d8879-107">次の方法でポリシーを実装できます。これらの方法は、会議の開始前、会議中、または会議後のユーザーの会議エクスペリエンスに影響します。</span><span class="sxs-lookup"><span data-stu-id="d8879-107">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span>

|<span data-ttu-id="d8879-108">実装の種類</span><span class="sxs-lookup"><span data-stu-id="d8879-108">Implementation type</span></span>  |<span data-ttu-id="d8879-109">説明</span><span class="sxs-lookup"><span data-stu-id="d8879-109">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="d8879-110">開催者単位</span><span class="sxs-lookup"><span data-stu-id="d8879-110">Per-organizer</span></span>    |<span data-ttu-id="d8879-111">開催者単位のポリシーを実装すると、すべての参加者は開催者のポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="d8879-111">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="d8879-112">たとえば、[**ユーザーの参加を自動的に許可する**] は、開催者単位のポリシーであり、ユーザーが会議に直接参加するか、ポリシーが割り当てられたユーザーがスケジュールした会議をロビーで待機するかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d8879-112">For example, **Automatically admit people** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="d8879-113">ユーザーごと</span><span class="sxs-lookup"><span data-stu-id="d8879-113">Per-user</span></span>    |<span data-ttu-id="d8879-114">ユーザーごとのポリシーを実装すると、ユーザーごとのポリシーのみが適用され、開催者や会議参加者に対する特定の機能が制限されます。</span><span class="sxs-lookup"><span data-stu-id="d8879-114">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="d8879-115">たとえば、[**チャネルで "今すぐ会議" を許可する**] は、ユーザー単位のポリシーです。</span><span class="sxs-lookup"><span data-stu-id="d8879-115">For example, **Allow Meet now in channels** is a per-user policy.</span></span>     |
|<span data-ttu-id="d8879-116">開催者単位およびユーザーごと</span><span class="sxs-lookup"><span data-stu-id="d8879-116">Per-organizer and per-user</span></span>     |<span data-ttu-id="d8879-117">開催者単位とユーザー単位のポリシーを組み合わせて実装すると、会議の参加者はユーザーのポリシーと開催者のポリシーに基づいて特定の機能が制限されます。</span><span class="sxs-lookup"><span data-stu-id="d8879-117">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="d8879-118">たとえば、[**クラウド記録を許可する**] は、開催者単位およびユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="d8879-118">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="d8879-119">この設定をオンにすると、会議の開催者と参加者は記録の開始と停止が可能になります。</span><span class="sxs-lookup"><span data-stu-id="d8879-119">Turn on this setting to allow the meeting organizer and participants to start and stop a recording.</span></span>

<span data-ttu-id="d8879-120">既定では、グローバル (組織全体の既定値) という名前のポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d8879-120">By default, a policy named Global (Org-wide default) is created.</span></span> <span data-ttu-id="d8879-121">組織内のすべてのユーザーに、このグローバル会議ポリシーが既定で割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="d8879-121">All users in your organization are assigned the Global meeting policy by default.</span></span> <span data-ttu-id="d8879-122">ポリシーを変更するか、1 つ以上のカスタム ポリシーを作成してユーザーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="d8879-122">You can either make changes to it or create one or more custom policies and assign users to them.</span></span> <span data-ttu-id="d8879-123">カスタム ポリシーを作成して割り当てていない場合、ユーザーにはグローバル ポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="d8879-123">Users will get the Global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="d8879-124">カスタム ポリシーを作成するときに、特定の機能をユーザーに対して使用可能または使用不可にして、そのポリシーを、適用する 1 人以上のユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="d8879-124">When you create a custom policy, you can allow or prevent certain features from being available to your users, and then assign it to one or more users who will have the settings applied to them.</span></span>

> [!NOTE]
> <span data-ttu-id="d8879-125">[会議の詳細] ボタンは、ユーザーが電話会議ライセンスを有効にしているか、ユーザーが電話会議を許可している場合に使用できます。それ以外の場合は、会議の詳細は使用できません。</span><span class="sxs-lookup"><span data-stu-id="d8879-125">Meeting details button will be available if a user has the audio conference licenses enabled or the user is allow for audio conferencing, if not, the meeting details will not be available</span></span>

## <a name="change-or-create-a-meeting-policy"></a><span data-ttu-id="d8879-126">会議ポリシーを変更または作成する</span><span class="sxs-lookup"><span data-stu-id="d8879-126">Change or create a meeting policy</span></span>

<span data-ttu-id="d8879-127">会議ポリシーを変更または作成するには、Microsoft Teams 管理センターにアクセスし、[**会議**]  >  [**会議ポリシー**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="d8879-127">To change or create a meeting policy, go to the Microsoft Teams admin center > **Meetings** > **Meeting policies**.</span></span> <span data-ttu-id="d8879-128">一覧からポリシーを選択するか、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d8879-128">Select a policy from the list or select **Add**.</span></span> <span data-ttu-id="d8879-129">新しいポリシーを作成する場合は、名前と説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="d8879-129">If you're creating a new policy, add a name and description.</span></span> <span data-ttu-id="d8879-130">名前に特殊文字を含めたり、64 文字より長くすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d8879-130">The name can't contain special characters or be longer than 64 characters.</span></span> <span data-ttu-id="d8879-131">設定を選び、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d8879-131">Choose your settings, and then select **Save**.</span></span>

<span data-ttu-id="d8879-132">たとえば、多数のユーザーがいて、会議に必要な帯域幅を制限するとします。</span><span class="sxs-lookup"><span data-stu-id="d8879-132">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="d8879-133">「制限された帯域幅」という名前の新しいカスタム ポリシーを作成し、次の設定を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="d8879-133">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="d8879-134">[**オーディオとビデオ**] で、</span><span class="sxs-lookup"><span data-stu-id="d8879-134">Under **Audio & video**:</span></span>
- <span data-ttu-id="d8879-135">[クラウド記録を許可する] を無効にします。</span><span class="sxs-lookup"><span data-stu-id="d8879-135">Turn off Allow cloud recording.</span></span>
- <span data-ttu-id="d8879-136">[IP のビデオを許可する] を無効にします。</span><span class="sxs-lookup"><span data-stu-id="d8879-136">Turn off Allow IP video.</span></span>

<span data-ttu-id="d8879-137">[**コンテンツの共有**] で、</span><span class="sxs-lookup"><span data-stu-id="d8879-137">Under **Content sharing**:</span></span>
- <span data-ttu-id="d8879-138">画面共有モードを無効にします。</span><span class="sxs-lookup"><span data-stu-id="d8879-138">Disable screen sharing mode.</span></span>
- <span data-ttu-id="d8879-139">[ホワイトボードを許可] を無効にします。</span><span class="sxs-lookup"><span data-stu-id="d8879-139">Turn off Allow whiteboard.</span></span>
- <span data-ttu-id="d8879-140">[メモの共有を許可する] を無効にします。</span><span class="sxs-lookup"><span data-stu-id="d8879-140">Turn off Allow shared notes.</span></span>

<span data-ttu-id="d8879-141">その後、ポリシーをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d8879-141">Then assign the policy to the users.</span></span>

> [!NOTE]
> <span data-ttu-id="d8879-142">ユーザーに割り当てることができる会議ポリシーは一度に 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="d8879-142">A user can be assigned only one meeting policy at a time.</span></span>

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="d8879-143">ユーザーに会議ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="d8879-143">Assign a meeting policy to users</span></span>

1. <span data-ttu-id="d8879-144">Microsoft Teams 管理センターの左側のナビゲーションで、[**ユーザー**] に移動してユーザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8879-144">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="d8879-145">ユーザー名の左側をクリックしてユーザーを選択し、[**編集を設定する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8879-145">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="d8879-146">[**会議ポリシー**] で割り当てるポリシーを選択し、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8879-146">Under **Meeting policy**, select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="d8879-147">一度に複数のユーザーにポリシーを割り当てる方法については、「[一括でTeams のユーザー設定を編集する](edit-user-settings-in-bulk.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8879-147">To assign a policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="d8879-148">または、次の操作も実行できます。</span><span class="sxs-lookup"><span data-stu-id="d8879-148">Or, you can also do the following:</span></span>

1. <span data-ttu-id="d8879-149">Microsoft Teams 管理センターの左側のナビゲーションで、[**会議**]  >  [**会議ポリシー**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="d8879-149">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="d8879-150">ポリシー名の左側をクリックしてポリシーを選びます。</span><span class="sxs-lookup"><span data-stu-id="d8879-150">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="d8879-151">[**ユーザーを管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d8879-151">Select **Manage users**.</span></span>
4. <span data-ttu-id="d8879-152">[**ユーザーを管理**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="d8879-152">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="d8879-153">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d8879-153">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="d8879-154">ユーザーの追加が完了したら、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d8879-154">After you finish adding users, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="d8879-155">ユーザーが割り当てられているポリシーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="d8879-155">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="d8879-156">影響を受けるすべてのユーザーにまず異なるポリシーを割り当ててから、元のポリシーを削除できます。</span><span class="sxs-lookup"><span data-stu-id="d8879-156">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

## <a name="meeting-policy-settings"></a><span data-ttu-id="d8879-157">会議ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="d8879-157">Meeting policy settings</span></span>

<span data-ttu-id="d8879-158">[**会議ポリシー**] ページで既存のポリシーを選択するか、新しいポリシーを追加するための [**追加**] を選択すると、次の設定内容を構成できます。</span><span class="sxs-lookup"><span data-stu-id="d8879-158">When you select an existing policy on the **Meeting policies** page or select **Add** to add a new policy, you can configure settings for the following.</span></span>

- [<span data-ttu-id="d8879-159">全般</span><span class="sxs-lookup"><span data-stu-id="d8879-159">General</span></span>](#meeting-policy-settings---general)
- [<span data-ttu-id="d8879-160">オーディオとビデオ</span><span class="sxs-lookup"><span data-stu-id="d8879-160">Audio & video</span></span>](#meeting-policy-settings---audio--video)
- [<span data-ttu-id="d8879-161">コンテンツの共有</span><span class="sxs-lookup"><span data-stu-id="d8879-161">Content sharing</span></span>](#meeting-policy-settings---content-sharing)
- [<span data-ttu-id="d8879-162">参加者とゲスト</span><span class="sxs-lookup"><span data-stu-id="d8879-162">Participants & guests</span></span>](#meeting-policy-settings---participants--guests)

::: zone-end 

<span data-ttu-id="d8879-163"><a name="bkgeneral"> </a></span><span class="sxs-lookup"><span data-stu-id="d8879-163"><a name="bkgeneral"> </a></span></span>

## <a name="meeting-policy-settings---general"></a><span data-ttu-id="d8879-164">会議ポリシーの設定 - 全般</span><span class="sxs-lookup"><span data-stu-id="d8879-164">Meeting policy settings - General</span></span>

- [<span data-ttu-id="d8879-165">チャネルで "今すぐ会議" を許可する</span><span class="sxs-lookup"><span data-stu-id="d8879-165">Allow Meet now in channels</span></span>](#allow-meet-now-in-channels)
- [<span data-ttu-id="d8879-166">Outlook アドインを許可する</span><span class="sxs-lookup"><span data-stu-id="d8879-166">Allow the Outlook add-in</span></span>](#allow-the-outlook-add-in)
- [<span data-ttu-id="d8879-167">チャネルの会議スケジュールを許可する</span><span class="sxs-lookup"><span data-stu-id="d8879-167">Allow channel meeting scheduling</span></span>](#allow-channel-meeting-scheduling)
- [<span data-ttu-id="d8879-168">プライベート会議のスケジュールを許可する</span><span class="sxs-lookup"><span data-stu-id="d8879-168">Allow scheduling private meetings</span></span>](#allow-scheduling-private-meetings)
- [<span data-ttu-id="d8879-169">プライベート会議で "今すぐ会議" を許可する</span><span class="sxs-lookup"><span data-stu-id="d8879-169">Allow Meet now in private meetings</span></span>](#allow-meet-now-in-private-meetings)

### <a name="allow-meet-now-in-channels"></a><span data-ttu-id="d8879-170">チャネルで "今すぐ会議" を許可する</span><span class="sxs-lookup"><span data-stu-id="d8879-170">Allow Meet now in channels</span></span>

<span data-ttu-id="d8879-171">これはユーザーごとのポリシーであり、会議が始まる前に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d8879-171">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="d8879-172">この設定は、ユーザーが Teams チャネルでアドホック会議を開始できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d8879-172">This setting controls whether a user can start an ad hoc meeting in a Teams channel.</span></span> <span data-ttu-id="d8879-173">これをオンにすると、ユーザーが Teams チャネルにメッセージを投稿するときに、ユーザーは作成ボックスの下の [**今すぐ会議**] をクリックして、チャネルでアドホック会議を開始できます。</span><span class="sxs-lookup"><span data-stu-id="d8879-173">If you turn this on, when a user posts a message in a Teams channel, the user can click **Meet now** under the compose box to start an ad hoc meeting in the channel.</span></span> <span data-ttu-id="d8879-174">既定値は True です。</span><span class="sxs-lookup"><span data-stu-id="d8879-174">The default value is True.</span></span>

![メッセージの下の [今すぐ会議] アイコンが表示されたスクリーンショット](media/meeting-policies-meet-now.png)

### <a name="allow-the-outlook-add-in"></a><span data-ttu-id="d8879-176">Outlook アドインを許可する</span><span class="sxs-lookup"><span data-stu-id="d8879-176">Allow the Outlook add-in</span></span>

<span data-ttu-id="d8879-177">これはユーザーごとのポリシーであり、会議が始まる前に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d8879-177">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="d8879-178">この設定は、Outlook (Windows、Mac、Web、およびモバイル) 内から Teams 会議をスケジュールできるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d8879-178">This setting controls whether Teams meetings can be scheduled from within Outlook (Windows, Mac, web, and mobile).</span></span>

![新しい会議をスケジュールする機能が表示されたスクリーンショット](media/meeting-policies-outlook-add-in.png)

<span data-ttu-id="d8879-180">これをオフにすると、ユーザーは Outlook で新しい会議を作成するときに Teams 会議をスケジュールできなくなります。</span><span class="sxs-lookup"><span data-stu-id="d8879-180">If you turn this off, users are unable to schedule Teams meetings when they create a new meeting in Outlook.</span></span> <span data-ttu-id="d8879-181">たとえば、Windows 上の Outlook では、[**新しい Teams 会議**] オプションはリボンに表示されません。</span><span class="sxs-lookup"><span data-stu-id="d8879-181">For example, in Outlook on Windows, the **New Teams Meeting** option won't show up in the ribbon.</span></span>

### <a name="allow-channel-meeting-scheduling"></a><span data-ttu-id="d8879-182">チャネルの会議スケジュールを許可する</span><span class="sxs-lookup"><span data-stu-id="d8879-182">Allow channel meeting scheduling</span></span>

<span data-ttu-id="d8879-183">これはユーザーごとのポリシーであり、会議が始まる前に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d8879-183">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="d8879-184">この設定は、ユーザーが Teams チャネルで会議をスケジュールできるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d8879-184">This setting controls whether users can schedule a meeting in a Teams channel.</span></span>  <span data-ttu-id="d8879-185">これをオフにすると、ユーザーは Teams チャネルで会議を開始するときに [**会議の予約**] オプションを使用できなくなり、Teams のユーザーに対して [**チャネルの追加**] オプションが無効になります。</span><span class="sxs-lookup"><span data-stu-id="d8879-185">If you turn this off, the **Schedule a meeting** option won't be available to the user when they start a meeting in a Teams channel and the **Add channel** option is disabled for users in Teams.</span></span> <span data-ttu-id="d8879-186">既定値は True です。</span><span class="sxs-lookup"><span data-stu-id="d8879-186">The default value is True.</span></span>

![Teams の [会議の予約] オプションが表示されたスクリーンショット](media/meeting-policies-schedule-a-meeting.png)

![[会議をするチャネルを選択] オプションが表示されたスクリーンショット](media/meeting-policies-select-a-channel-to-meet-in.png)

### <a name="allow-scheduling-private-meetings"></a><span data-ttu-id="d8879-189">プライベート会議のスケジュールを許可する</span><span class="sxs-lookup"><span data-stu-id="d8879-189">Allow scheduling private meetings</span></span>

<span data-ttu-id="d8879-190">これはユーザーごとのポリシーであり、会議が始まる前に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d8879-190">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="d8879-191">この設定は、ユーザーが Teams でプライベート会議をスケジュールできるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d8879-191">This setting controls whether users can schedule private meetings in Teams.</span></span> <span data-ttu-id="d8879-192">チームのチャネルに公開されていない会議はプライベートです。</span><span class="sxs-lookup"><span data-stu-id="d8879-192">A meeting is private when it's not published to a channel in a team.</span></span>

<span data-ttu-id="d8879-193">[**プライベート会議のスケジュールを許可する**] および [**チャネルの会議スケジュールを許可する**] を無効にすると、Teams のユーザーに対して [**必須出席者の追加**] および [**チャネルの追加**] オプションが無効になります。</span><span class="sxs-lookup"><span data-stu-id="d8879-193">Note that if you turn off **Allow scheduling private meetings** and **Allow channel meeting scheduling**,  the **Add required attendees** and **Add channel** options are disabled for users in Teams.</span></span> <span data-ttu-id="d8879-194">既定値は True です。</span><span class="sxs-lookup"><span data-stu-id="d8879-194">The default value is True.</span></span>

### <a name="allow-meet-now-in-private-meetings"></a><span data-ttu-id="d8879-195">プライベート会議で "今すぐ会議" を許可する</span><span class="sxs-lookup"><span data-stu-id="d8879-195">Allow Meet now in private meetings</span></span>

<span data-ttu-id="d8879-196">これはユーザーごとのポリシーであり、会議が始まる前に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d8879-196">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="d8879-197">この設定は、ユーザーがアドホック プライベート会議を開始できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d8879-197">This setting controls whether a user can start an ad hoc private meeting.</span></span>  <span data-ttu-id="d8879-198">既定値は True です。</span><span class="sxs-lookup"><span data-stu-id="d8879-198">The default value is True.</span></span>

<span data-ttu-id="d8879-199"><a name="bkaudioandvideo"> </a></span><span class="sxs-lookup"><span data-stu-id="d8879-199"><a name="bkaudioandvideo"> </a></span></span>

## <a name="meeting-policy-settings---audio--video"></a><span data-ttu-id="d8879-200">会議ポリシーの設定 - オーディオとビデオ</span><span class="sxs-lookup"><span data-stu-id="d8879-200">Meeting policy settings - Audio & video</span></span>

- [<span data-ttu-id="d8879-201">文字起こしを許可する</span><span class="sxs-lookup"><span data-stu-id="d8879-201">Allow transcription</span></span>](#allow-transcription)
- [<span data-ttu-id="d8879-202">クラウド記録を許可する</span><span class="sxs-lookup"><span data-stu-id="d8879-202">Allow cloud recording</span></span>](#allow-cloud-recording)
- [<span data-ttu-id="d8879-203">IP のビデオを許可する</span><span class="sxs-lookup"><span data-stu-id="d8879-203">Allow IP video</span></span>](#allow-ip-video)
- [<span data-ttu-id="d8879-204">メディアのビットレート (Kbs)</span><span class="sxs-lookup"><span data-stu-id="d8879-204">Media bit rate (Kbs)</span></span>](#media-bit-rate-kbs)

### <a name="allow-transcription"></a><span data-ttu-id="d8879-205">文字起こしを許可する</span><span class="sxs-lookup"><span data-stu-id="d8879-205">Allow transcription</span></span>

<span data-ttu-id="d8879-206">これは、開催者単位とユーザーごとのポリシーの組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="d8879-206">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="d8879-207">この設定は、会議の記録の再生中にキャプションと文字起こし機能を使用できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d8879-207">This setting controls whether captions and transcription features are available during playback of meeting recordings.</span></span> <span data-ttu-id="d8879-208">これをオフにすると、会議の記録の再生中に [**検索**] および [**CC**] オプションを使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="d8879-208">If you turn this off, the **Search** and **CC** options won't be available during playback of a meeting recording.</span></span> <span data-ttu-id="d8879-209">記録を開始したユーザーは、記録に文字起こしも含まれるように、この設定を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8879-209">The person who started the recording needs this setting turned on so that the recording also includes transcription.</span></span> 

<span data-ttu-id="d8879-210">記録された会議の文字起こしは、現在、Teams の言語が英語に設定されているユーザー、および会議で英語が話されている場合のユーザーに対してのみサポートされていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d8879-210">Note that transcription for recorded meetings is currently only supported for users who have the language in Teams set to English and when English is spoken in the meeting.</span></span>

![会議の文字起こしオプションが表示されたスクリーンショット](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a><span data-ttu-id="d8879-212">クラウド記録を許可する</span><span class="sxs-lookup"><span data-stu-id="d8879-212">Allow cloud recording</span></span>

<span data-ttu-id="d8879-213">これは、開催者単位とユーザーごとのポリシーの組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="d8879-213">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="d8879-214">この設定は、このユーザーの会議を記録できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d8879-214">This setting controls whether this user's meetings can be recorded.</span></span> <span data-ttu-id="d8879-215">参加者のポリシー設定が有効になっており、同じ組織の認証済みユーザーである場合、会議の開催者または別の会議参加者が記録を開始できます。</span><span class="sxs-lookup"><span data-stu-id="d8879-215">The recording can be started by the meeting organizer or by another meeting participant if the policy setting is turned on for the participant and if they're an authenticated user from the same organization.</span></span>

<span data-ttu-id="d8879-216">フェデレーション ユーザーや匿名ユーザーなど、組織外のユーザーは記録を開始できません。</span><span class="sxs-lookup"><span data-stu-id="d8879-216">People outside your organization, such as federated and anonymous users, can't start the recording.</span></span> <span data-ttu-id="d8879-217">ゲスト ユーザーは記録を開始または停止できません。</span><span class="sxs-lookup"><span data-stu-id="d8879-217">Guest users can't start or stop the recording.</span></span> 

![記録オプションが表示されたスクリーンショット](media/meeting-policies-recording.png)

<span data-ttu-id="d8879-219">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="d8879-219">Let's look at the following example.</span></span>

|<span data-ttu-id="d8879-220">ユーザー</span><span class="sxs-lookup"><span data-stu-id="d8879-220">User</span></span> |<span data-ttu-id="d8879-221">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="d8879-221">Meeting policy</span></span>  |<span data-ttu-id="d8879-222">クラウド記録を許可する</span><span class="sxs-lookup"><span data-stu-id="d8879-222">Allow cloud recording</span></span> |
|---------|---------|---------|
|<span data-ttu-id="d8879-223">Daniela</span><span class="sxs-lookup"><span data-stu-id="d8879-223">Daniela</span></span> | <span data-ttu-id="d8879-224">グローバル</span><span class="sxs-lookup"><span data-stu-id="d8879-224">Global</span></span>   | <span data-ttu-id="d8879-225">False</span><span class="sxs-lookup"><span data-stu-id="d8879-225">False</span></span> |
|<span data-ttu-id="d8879-226">Amanda</span><span class="sxs-lookup"><span data-stu-id="d8879-226">Amanda</span></span> | <span data-ttu-id="d8879-227">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="d8879-227">Location1MeetingPolicy</span></span> | <span data-ttu-id="d8879-228">True</span><span class="sxs-lookup"><span data-stu-id="d8879-228">True</span></span>|
|<span data-ttu-id="d8879-229">John (外部ユーザー)</span><span class="sxs-lookup"><span data-stu-id="d8879-229">John (external user)</span></span> | <span data-ttu-id="d8879-230">該当なし</span><span class="sxs-lookup"><span data-stu-id="d8879-230">Not applicable</span></span> | <span data-ttu-id="d8879-231">該当なし</span><span class="sxs-lookup"><span data-stu-id="d8879-231">Not applicable</span></span>|

<span data-ttu-id="d8879-232">Daniela が開催する会議は記録されず、ポリシー設定が有効になっている Amanda は Daniela が開催する会議を記録できません。</span><span class="sxs-lookup"><span data-stu-id="d8879-232">Meetings organized by Daniela can't be recorded and Amanda, who has the policy setting enabled, can't record meetings organized by Daniela.</span></span> <span data-ttu-id="d8879-233">Amanda が開催する会議は記録できますが、ポリシー設定が無効になっている Daniela と外部ユーザーである John は、Amanda が開催する会議を記録できません。</span><span class="sxs-lookup"><span data-stu-id="d8879-233">Meetings organized by Amanda can be recorded, however,  Daniela, who has the policy setting disabled and John who is an external user, can't record meetings organized by Amanda.</span></span>

<span data-ttu-id="d8879-234">クラウド会議の記録の詳細については、「[Teams のクラウド会議の記録](cloud-recording.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8879-234">To learn more about cloud meeting recording, see [Teams cloud meeting recording](cloud-recording.md).</span></span>

### <a name="allow-ip-video"></a><span data-ttu-id="d8879-235">IP ビデオを許可する</span><span class="sxs-lookup"><span data-stu-id="d8879-235">Allow IP video</span></span>

<span data-ttu-id="d8879-236">これは、開催者単位とユーザーごとのポリシーの組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="d8879-236">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="d8879-237">ビデオは、会議の重要な構成要素です。</span><span class="sxs-lookup"><span data-stu-id="d8879-237">Video is a key component to meetings.</span></span> <span data-ttu-id="d8879-238">一部の組織では、管理者がビデオを使用するユーザーの会議をさらに制御する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="d8879-238">In some organizations, admins might want more control over which users' meetings have video.</span></span> <span data-ttu-id="d8879-239">この設定は、ユーザーがホストする会議、およびユーザーが開始する 1:1 通話やグループ通話でビデオを有効にできるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d8879-239">This setting controls whether video can be turned on in meetings hosted by a user and in 1:1 calls and group calls started by a user.</span></span> <span data-ttu-id="d8879-240">このポリシーを有効にしたユーザーが開催する会議では、会議の参加者もポリシーを有効にしている場合に、会議の参加者による会議でのビデオ共有が許可されます。</span><span class="sxs-lookup"><span data-stu-id="d8879-240">Meetings organized by a user who has this policy enabled, allow video sharing in the meeting by the meeting participants, if the meeting participants also have the policy enabled.</span></span> <span data-ttu-id="d8879-241">ポリシーが割り当てられていない会議参加者 (匿名参加者やフェデレーション参加者など) は、会議開催者のポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="d8879-241">Meeting participants who don't have any policies assigned (for example, anonymous and federated participants) inherit the policy of the meeting organizer.</span></span>

![オーディオとビデオの設定を含む会議が表示されたスクリーンショット](media/meeting-policies-audio-video-settings.png)

<span data-ttu-id="d8879-243">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="d8879-243">Let's look at the following example.</span></span>

|<span data-ttu-id="d8879-244">ユーザー</span><span class="sxs-lookup"><span data-stu-id="d8879-244">User</span></span> |<span data-ttu-id="d8879-245">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="d8879-245">Meeting policy</span></span>  |<span data-ttu-id="d8879-246">IP ビデオを許可する</span><span class="sxs-lookup"><span data-stu-id="d8879-246">Allow IP Video</span></span> |
|---------|---------|---------|
|<span data-ttu-id="d8879-247">Daniela</span><span class="sxs-lookup"><span data-stu-id="d8879-247">Daniela</span></span>   | <span data-ttu-id="d8879-248">グローバル</span><span class="sxs-lookup"><span data-stu-id="d8879-248">Global</span></span>   | <span data-ttu-id="d8879-249">True</span><span class="sxs-lookup"><span data-stu-id="d8879-249">True</span></span>        |
|<span data-ttu-id="d8879-250">Amanda</span><span class="sxs-lookup"><span data-stu-id="d8879-250">Amanda</span></span>    | <span data-ttu-id="d8879-251">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="d8879-251">Location1MeetingPolicy</span></span>        | <span data-ttu-id="d8879-252">False</span><span class="sxs-lookup"><span data-stu-id="d8879-252">False</span></span>      |

<span data-ttu-id="d8879-253">Daniela が開催する会議では、ビデオを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d8879-253">Meetings hosted by Daniela allow video to be turned on.</span></span> <span data-ttu-id="d8879-254">Daniela は会議に参加してビデオを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d8879-254">Daniela can join the meeting and turn on video.</span></span> <span data-ttu-id="d8879-255">Amanda のポリシーが [ビデオを許可しない] に設定されているため、Amanda は Daniela の会議でビデオを有効にできません。</span><span class="sxs-lookup"><span data-stu-id="d8879-255">Amanda can't turn on video in Daniela's meeting because Amanda's policy is set to not allow video.</span></span> <span data-ttu-id="d8879-256">Amanda は、会議の他の参加者が共有しているビデオを見ることができます。</span><span class="sxs-lookup"><span data-stu-id="d8879-256">Amanda can see videos shared by other participants in the meeting.</span></span>

<span data-ttu-id="d8879-257">Amanda が主催する会議では、割り当てられたビデオ ポリシーに関係なく、誰もビデオを有効にできません。</span><span class="sxs-lookup"><span data-stu-id="d8879-257">In meetings hosted by Amanda, no one can turn on video, regardless of the video policy assigned to them.</span></span> <span data-ttu-id="d8879-258">これは、Daniela Amanda の会議でビデオを有効にできないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="d8879-258">This means Daniela can't turn on video in Amanda's meetings.</span></span>  

<span data-ttu-id="d8879-259">Daniela がビデオを有効にして Amanda に電話した場合、Amanda はオーディオのみで電話に出ることができます。</span><span class="sxs-lookup"><span data-stu-id="d8879-259">If Daniela calls Amanda with video on, Amanda can answer the call with audio only.</span></span>  <span data-ttu-id="d8879-260">通話が接続されている場合、Amanda は Daniela のビデオを見ることはできますが、ビデオを有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d8879-260">When the call is connected, Amanda can see Daniela's video, but can't turn on video.</span></span> <span data-ttu-id="d8879-261">Amanda が Daniela に電話すると、Daniela はビデオとオーディオで電話に出ることができます。</span><span class="sxs-lookup"><span data-stu-id="d8879-261">If Amanda calls Daniela, Daniela can answer the call with video and audio.</span></span> <span data-ttu-id="d8879-262">通話が接続されると、Daniela は必要に応じてビデオを有効または無効にできます。</span><span class="sxs-lookup"><span data-stu-id="d8879-262">When the call is connected, Daniela can turn on or turn off her video, as needed.</span></span>

### <a name="media-bit-rate-kbs"></a><span data-ttu-id="d8879-263">メディアのビットレート (Kbs)</span><span class="sxs-lookup"><span data-stu-id="d8879-263">Media bit rate (Kbs)</span></span>

<span data-ttu-id="d8879-264">これは、ユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="d8879-264">This is a per-user policy.</span></span> <span data-ttu-id="d8879-265">この設定により、ユーザーの通話および会議でのオーディオ、ビデオ、およびビデオベースのアプリ共有送信のメディア ビット レートが決まります。</span><span class="sxs-lookup"><span data-stu-id="d8879-265">This setting determines the media bit rate for audio, video, and video-based app sharing transmissions in calls and meetings for the user.</span></span> <span data-ttu-id="d8879-266">通話または会議のユーザーのアップリンクとダウンリンクの両方のメディア トラバーサルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="d8879-266">It's applied to both the uplink and downlink media traversal for users in the call or meeting.</span></span> <span data-ttu-id="d8879-267">この設定により、組織の帯域幅の管理をきめ細やかに制御できます。</span><span class="sxs-lookup"><span data-stu-id="d8879-267">This setting gives you granular control over managing bandwidth in your organization.</span></span> <span data-ttu-id="d8879-268">ユーザーが必要とする会議シナリオに応じて、高品質のエクスペリエンスを得るために十分な帯域幅を用意することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d8879-268">Depending on the meetings scenarios required by users, we recommend having enough bandwidth in place for a good quality experience.</span></span> <span data-ttu-id="d8879-269">最小値は 30 Kbps で、最大値は会議シナリオによって異なります。</span><span class="sxs-lookup"><span data-stu-id="d8879-269">The minimum value is 30 Kbps and the maximum value depends on the meeting scenario.</span></span> <span data-ttu-id="d8879-270">Teams での高品質の会議、通話、およびライブ イベントを実現する最小推奨帯域幅の詳細については、「[帯域幅要件](prepare-network.md#bandwidth-requirements)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8879-270">To learn more about the minimum recommended bandwidth for good quality meetings, calls, and live events in Teams, see [Bandwidth requirements](prepare-network.md#bandwidth-requirements).</span></span>

<span data-ttu-id="d8879-271">会議に十分な帯域幅がない場合、参加者には、ネットワークの品質低下を示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8879-271">If there isn't enough bandwidth for a meeting, participants see a message that indicates poor network quality.</span></span>

<span data-ttu-id="d8879-272">CEO ボード会議や Teams のライブ イベントなど、最高品質のビデオ エクスペリエンスを必要とする会議では、帯域幅を 10 Mbps に設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d8879-272">For meetings that need the highest quality video experience, such as CEO board meetings and Teams live events, we recommend you set the bandwidth to 10 Mbps.</span></span> <span data-ttu-id="d8879-273">最大限のエクスペリエンスが設定されている場合でも、特定のネットワーク条件が検出されると、シナリオに応じて、Teams メディア スタックは低帯域幅の条件に適応します。</span><span class="sxs-lookup"><span data-stu-id="d8879-273">Even when the maximum experience is set, the Teams media stack adapts to low bandwidth conditions when certain network conditions are detected, depending on the scenario.</span></span> 

## <a name="meeting-policy-settings---content-sharing"></a><span data-ttu-id="d8879-274">会議ポリシーの設定 - コンテンツの共有</span><span class="sxs-lookup"><span data-stu-id="d8879-274">Meeting policy settings - Content sharing</span></span>

- [<span data-ttu-id="d8879-275">画面共有モード</span><span class="sxs-lookup"><span data-stu-id="d8879-275">Screen sharing mode</span></span>](#screen-sharing-mode)
- [<span data-ttu-id="d8879-276">参加者に制御を渡す、または制御を要求する</span><span class="sxs-lookup"><span data-stu-id="d8879-276">Allow a participant to give or request control</span></span>](#allow-a-participant-to-give-or-request-control)
- [<span data-ttu-id="d8879-277">外部の参加者に制御を渡す、または制御を要求する</span><span class="sxs-lookup"><span data-stu-id="d8879-277">Allow an external participant to give or request control</span></span>](#allow-an-external-participant-to-give-or-request-control)
- [<span data-ttu-id="d8879-278">PowerPoint の共有を許可する</span><span class="sxs-lookup"><span data-stu-id="d8879-278">Allow PowerPoint sharing</span></span>](#allow-powerpoint-sharing)
- [<span data-ttu-id="d8879-279">ホワイトボードを許可する</span><span class="sxs-lookup"><span data-stu-id="d8879-279">Allow whiteboard</span></span>](#allow-whiteboard)
- [<span data-ttu-id="d8879-280">メモの共有を許可する</span><span class="sxs-lookup"><span data-stu-id="d8879-280">Allow shared notes</span></span>](#allow-shared-notes)

### <a name="screen-sharing-mode"></a><span data-ttu-id="d8879-281">画面共有モード</span><span class="sxs-lookup"><span data-stu-id="d8879-281">Screen sharing mode</span></span>

<span data-ttu-id="d8879-282">これは、開催者単位とユーザーごとのポリシーの組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="d8879-282">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="d8879-283">この設定は、ユーザーの会議でデスクトップやウィンドウの共有を許可するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d8879-283">This setting controls whether desktop and/or window sharing is allowed in the user's meeting.</span></span> <span data-ttu-id="d8879-284">ポリシーが割り当てられていない会議参加者 (匿名参加者、ゲスト参加者、B2B 参加者、フェデレーション参加者など) は、会議開催者のポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="d8879-284">Meeting participants who don't have any policies assigned (for example, anonymous, guest, B2B, and federated participants) inherit the policy of the meeting organizer.</span></span>

|<span data-ttu-id="d8879-285">値を設定する</span><span class="sxs-lookup"><span data-stu-id="d8879-285">Setting value</span></span> |<span data-ttu-id="d8879-286">動作</span><span class="sxs-lookup"><span data-stu-id="d8879-286">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="d8879-287">**画面全体**</span><span class="sxs-lookup"><span data-stu-id="d8879-287">**Entire screen**</span></span>    | <span data-ttu-id="d8879-288">会議では完全なデスクトップ共有とアプリケーション共有が許可されます</span><span class="sxs-lookup"><span data-stu-id="d8879-288">Full desktop sharing and application sharing is allowed in the meeting</span></span> |
|<span data-ttu-id="d8879-289">**単一アプリケーション**</span><span class="sxs-lookup"><span data-stu-id="d8879-289">**Single application**</span></span>   | <span data-ttu-id="d8879-290">会議ではアプリケーションの共有が許可されます</span><span class="sxs-lookup"><span data-stu-id="d8879-290">Application sharing is allowed in the meeting</span></span>        |
|<span data-ttu-id="d8879-291">**無効**</span><span class="sxs-lookup"><span data-stu-id="d8879-291">**Disabled**</span></span>     |<span data-ttu-id="d8879-292">会議では画面共有とアプリケーション共有が無効になります。</span><span class="sxs-lookup"><span data-stu-id="d8879-292">Screen sharing and application sharing turned off in the meeting.</span></span>       |

<span data-ttu-id="d8879-293">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="d8879-293">Let's look at the following example.</span></span>

|<span data-ttu-id="d8879-294">ユーザー</span><span class="sxs-lookup"><span data-stu-id="d8879-294">User</span></span> |<span data-ttu-id="d8879-295">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="d8879-295">Meeting policy</span></span> |<span data-ttu-id="d8879-296">画面共有モード</span><span class="sxs-lookup"><span data-stu-id="d8879-296">Screen sharing mode</span></span> |
|---------|---------|---------|
|<span data-ttu-id="d8879-297">Daniela</span><span class="sxs-lookup"><span data-stu-id="d8879-297">Daniela</span></span>  | <span data-ttu-id="d8879-298">グローバル</span><span class="sxs-lookup"><span data-stu-id="d8879-298">Global</span></span>   | <span data-ttu-id="d8879-299">画面全体</span><span class="sxs-lookup"><span data-stu-id="d8879-299">Entire screen</span></span> |
|<span data-ttu-id="d8879-300">Amanda</span><span class="sxs-lookup"><span data-stu-id="d8879-300">Amanda</span></span>   | <span data-ttu-id="d8879-301">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="d8879-301">Location1MeetingPolicy</span></span>  | <span data-ttu-id="d8879-302">無効</span><span class="sxs-lookup"><span data-stu-id="d8879-302">Disabled</span></span> |

<span data-ttu-id="d8879-303">Daniela が開催する会議では、会議の参加者が画面全体または特定のアプリケーションを共有できます。</span><span class="sxs-lookup"><span data-stu-id="d8879-303">Meetings hosted by Daniela allow meeting participants to share their entire screen or a specific application.</span></span> <span data-ttu-id="d8879-304">Amanda が Daniela の会議に参加している場合は、そのポリシー設定が無効になっているために、Amanda が自分の画面や特定のアプリケーションを共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="d8879-304">If Amanda joins Daniela's meeting, Amanda can't share her screen or a specific application as her policy setting is disabled.</span></span> <span data-ttu-id="d8879-305">Amanda がホストする会議では、割り当てられた画面共有モード ポリシーに関係なく、誰も画面または単一のアプリケーションを共有できません。</span><span class="sxs-lookup"><span data-stu-id="d8879-305">In meetings hosted by Amanda, no one is allowed to share their screen or a single application, regardless of the screen sharing mode policy assigned to them.</span></span> <span data-ttu-id="d8879-306">これは、Daniela が Amanda の会議で、画面や単一のアプリケーションを共有できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="d8879-306">This means that Daniela can't share her screen or a single application in Amanda's meetings.</span></span>  

<span data-ttu-id="d8879-307">現在、ユーザーは Google Chrome を使用している場合、Teams 会議でビデオを再生したり画面を共有したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d8879-307">Currently, users can't play video or share their screen in a Teams meeting if they're using Google Chrome.</span></span>

### <a name="allow-a-participant-to-give-or-request-control"></a><span data-ttu-id="d8879-308">参加者に制御を渡す、または制御を要求する</span><span class="sxs-lookup"><span data-stu-id="d8879-308">Allow a participant to give or request control</span></span>

<span data-ttu-id="d8879-309">これは、ユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="d8879-309">This is a per-user policy.</span></span> <span data-ttu-id="d8879-310">この設定は、ユーザーが他の会議参加者に共有デスクトップまたはウィンドウの制御を渡すことができるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d8879-310">This setting controls whether the user can give control of the shared desktop or window to other meeting participants.</span></span> <span data-ttu-id="d8879-311">制御を渡すには、画面の上部にカーソルを合わせます。</span><span class="sxs-lookup"><span data-stu-id="d8879-311">To give control, hover over the top of the screen.</span></span> 

<span data-ttu-id="d8879-312">ユーザーに対してこの設定が有効になっている場合、共有セッションの上部のバーに [**制御を渡す**] オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8879-312">If this setting is turned on for the user, the **Give Control** option is displayed in the top bar in a sharing session.</span></span> 

![[制御を渡す] オプションが表示されたスクリーンショット](media/meeting-policies-give-control.png)

<span data-ttu-id="d8879-314">ユーザーの設定が無効になっている場合、[**制御を渡す**] オプションは使用できません。</span><span class="sxs-lookup"><span data-stu-id="d8879-314">If the settings is turned off for the user, the **Give Control** option isn't available.</span></span>

![[制御を渡す] オプションが利用できないことを示すスクリーンショット](media/meeting-policies-give-control-not-available.png)

<span data-ttu-id="d8879-316">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="d8879-316">Let's look at the following example.</span></span>

|<span data-ttu-id="d8879-317">ユーザー</span><span class="sxs-lookup"><span data-stu-id="d8879-317">User</span></span> |<span data-ttu-id="d8879-318">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="d8879-318">Meeting policy</span></span>  |<span data-ttu-id="d8879-319">参加者に制御を渡す、または制御を要求する</span><span class="sxs-lookup"><span data-stu-id="d8879-319">Allow participant to give or request control</span></span> |
|---------|---------|---------|
|<span data-ttu-id="d8879-320">Daniela</span><span class="sxs-lookup"><span data-stu-id="d8879-320">Daniela</span></span>   | <span data-ttu-id="d8879-321">グローバル</span><span class="sxs-lookup"><span data-stu-id="d8879-321">Global</span></span>   | <span data-ttu-id="d8879-322">True</span><span class="sxs-lookup"><span data-stu-id="d8879-322">True</span></span>       |
|<span data-ttu-id="d8879-323">Babek</span><span class="sxs-lookup"><span data-stu-id="d8879-323">Babek</span></span>    | <span data-ttu-id="d8879-324">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="d8879-324">Location1MeetingPolicy</span></span>        | <span data-ttu-id="d8879-325">False</span><span class="sxs-lookup"><span data-stu-id="d8879-325">False</span></span>   |

<span data-ttu-id="d8879-326">Daniela は、Babek が開催する会議の他の参加者に共有デスクトップまたはウィンドウの制御を渡すことができますが、Babek は他の参加者に制御を渡すことができません。</span><span class="sxs-lookup"><span data-stu-id="d8879-326">Daniela can give control of the shared desktop or window to other participants in a meeting organized by Babek whereas Babek can't give control to other participants.</span></span>

<span data-ttu-id="d8879-327">制御を渡したり、制御要求を受け入れたりすることができるユーザーを PowerShell を使用して制御するには、AllowParticipantGiveRequestControl コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="d8879-327">To use PowerShell to control who can give control or accept requests for control, use the AllowParticipantGiveRequestControl cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="d8879-328">共有中に共有コンテンツの制御を渡したり受け取ったりするには、両者が Teams デスクトップ クライアントを使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8879-328">To give and take control of shared content during sharing, both parties must be using the Teams desktop client.</span></span> <span data-ttu-id="d8879-329">いずれかの当事者がブラウザーで Teams を実行している場合、制御はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="d8879-329">Control isn't supported when either party is running Teams in a browser.</span></span> <span data-ttu-id="d8879-330">これは、修正する予定の技術的制限によるものです。</span><span class="sxs-lookup"><span data-stu-id="d8879-330">This is due to a technical limitation that we're planning to fix.</span></span> 

### <a name="allow-an-external-participant-to-give-or-request-control"></a><span data-ttu-id="d8879-331">外部の参加者に制御を渡す、または制御を要求する</span><span class="sxs-lookup"><span data-stu-id="d8879-331">Allow an external participant to give or request control</span></span>

<span data-ttu-id="d8879-332">これは、ユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="d8879-332">This is a per-user policy.</span></span> <span data-ttu-id="d8879-333">この設定は、会議の外部参加者が共有デスクトップまたはウィンドウの制御を他の会議参加者に渡すことができるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d8879-333">This setting controls whether external participants in a meeting can give control of their shared desktop or window to other participants in the meeting.</span></span> <span data-ttu-id="d8879-334">Teams 会議の外部参加者は、次のように分類できます。</span><span class="sxs-lookup"><span data-stu-id="d8879-334">External participants in Teams meetings can be categorized as follows:</span></span>  

- <span data-ttu-id="d8879-335">匿名ユーザー</span><span class="sxs-lookup"><span data-stu-id="d8879-335">Anonymous user</span></span>
- <span data-ttu-id="d8879-336">ゲスト ユーザー</span><span class="sxs-lookup"><span data-stu-id="d8879-336">Guest users</span></span>  
- <span data-ttu-id="d8879-337">B2B ユーザー</span><span class="sxs-lookup"><span data-stu-id="d8879-337">B2B user</span></span>
- <span data-ttu-id="d8879-338">フェデレーション ユーザー</span><span class="sxs-lookup"><span data-stu-id="d8879-338">Federated user</span></span>  

<span data-ttu-id="d8879-339">フェデレーション ユーザーが共有中に外部ユーザーに制御を渡すことができるかどうかは、組織の「**外部の参加者に制御を渡す、または制御を要求する**」設定によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="d8879-339">Whether federated users can give control to external users while sharing is controlled by the **Allow an external participant to give or request control** setting in their organization.</span></span>

<span data-ttu-id="d8879-340">PowerShell を使用して、外部の参加者が制御を渡すことができるか、または制御要求を受け入れることができるかを制御するには、AllowExternalParticipantGiveRequestControl コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="d8879-340">To use PowerShell to control whether external participants can give control or accept requests for control, use the AllowExternalParticipantGiveRequestControl cmdlet.</span></span>

### <a name="allow-powerpoint-sharing"></a><span data-ttu-id="d8879-341">PowerPoint の共有を許可する</span><span class="sxs-lookup"><span data-stu-id="d8879-341">Allow PowerPoint sharing</span></span>

<span data-ttu-id="d8879-342">これは、ユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="d8879-342">This is a per-user policy.</span></span> <span data-ttu-id="d8879-343">この設定は、ユーザーが会議で PowerPoint スライド セットを共有できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d8879-343">This setting controls whether the user can share PowerPoint slide decks in a meeting.</span></span> <span data-ttu-id="d8879-344">匿名ユーザー、ゲスト ユーザー、フェデレーション ユーザーを含む外部ユーザーは、会議開催者のポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="d8879-344">External users, including anonymous, guest, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="d8879-345">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="d8879-345">Let's look at the following example.</span></span>

|<span data-ttu-id="d8879-346">ユーザー</span><span class="sxs-lookup"><span data-stu-id="d8879-346">User</span></span> |<span data-ttu-id="d8879-347">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="d8879-347">Meeting policy</span></span>  |<span data-ttu-id="d8879-348">PowerPoint の共有を許可する</span><span class="sxs-lookup"><span data-stu-id="d8879-348">Allow PowerPoint sharing</span></span> |
|---------|---------|---------|
|<span data-ttu-id="d8879-349">Daniela</span><span class="sxs-lookup"><span data-stu-id="d8879-349">Daniela</span></span>   | <span data-ttu-id="d8879-350">グローバル</span><span class="sxs-lookup"><span data-stu-id="d8879-350">Global</span></span>   | <span data-ttu-id="d8879-351">True</span><span class="sxs-lookup"><span data-stu-id="d8879-351">True</span></span>       |
|<span data-ttu-id="d8879-352">Amanda</span><span class="sxs-lookup"><span data-stu-id="d8879-352">Amanda</span></span>   | <span data-ttu-id="d8879-353">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="d8879-353">Location1MeetingPolicy</span></span>        | <span data-ttu-id="d8879-354">False</span><span class="sxs-lookup"><span data-stu-id="d8879-354">False</span></span>   |

<span data-ttu-id="d8879-355">Amanda は、会議の開催者であっても、PowerPoint スライド セットを会議で共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="d8879-355">Amanda can't share PowerPoint slide decks in meetings even if she's the meeting organizer.</span></span> <span data-ttu-id="d8879-356">Daniela は、会議が Amanda によって開催されている場合でも、PowerPoint スライド セットを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="d8879-356">Daniela can share PowerPoint slide decks even if the meeting is organized by Amanda.</span></span> <span data-ttu-id="d8879-357">Amanda は、PowerPoint スライド セットを共有できない場合でも、会議の他のユーザーによって共有されている PowerPoint スライド セットを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="d8879-357">Amanda can view the PowerPoint slide decks shared by others in the meeting, even though she can't share PowerPoint slide decks.</span></span>

### <a name="allow-whiteboard"></a><span data-ttu-id="d8879-358">ホワイトボードを許可する</span><span class="sxs-lookup"><span data-stu-id="d8879-358">Allow whiteboard</span></span>

<span data-ttu-id="d8879-359">これは、ユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="d8879-359">This is a per-user policy.</span></span> <span data-ttu-id="d8879-360">この設定は、ユーザーが会議でホワイトボードを共有できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d8879-360">This setting controls whether a user can share the whiteboard in a meeting.</span></span> <span data-ttu-id="d8879-361">匿名ユーザー、B2B ユーザー、およびフェデレーション ユーザーを含む外部ユーザーは、会議開催者のポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="d8879-361">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> 

<span data-ttu-id="d8879-362">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="d8879-362">Let's look at the following example.</span></span>

|<span data-ttu-id="d8879-363">ユーザー</span><span class="sxs-lookup"><span data-stu-id="d8879-363">User</span></span> |<span data-ttu-id="d8879-364">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="d8879-364">Meeting policy</span></span>  |<span data-ttu-id="d8879-365">ホワイトボードを許可する</span><span class="sxs-lookup"><span data-stu-id="d8879-365">Allow whiteboard</span></span>|
|---------|---------|---------|
|<span data-ttu-id="d8879-366">Daniela</span><span class="sxs-lookup"><span data-stu-id="d8879-366">Daniela</span></span>   | <span data-ttu-id="d8879-367">グローバル</span><span class="sxs-lookup"><span data-stu-id="d8879-367">Global</span></span>   | <span data-ttu-id="d8879-368">True</span><span class="sxs-lookup"><span data-stu-id="d8879-368">True</span></span>       |
|<span data-ttu-id="d8879-369">Amanda</span><span class="sxs-lookup"><span data-stu-id="d8879-369">Amanda</span></span>   | <span data-ttu-id="d8879-370">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="d8879-370">Location1MeetingPolicy</span></span>        | <span data-ttu-id="d8879-371">False</span><span class="sxs-lookup"><span data-stu-id="d8879-371">False</span></span>   |

<span data-ttu-id="d8879-372">Amanda は、会議の開催者であっても、会議でホワイトボードを共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="d8879-372">Amanda can't share the whiteboard in a meeting even if she's the meeting organizer.</span></span> <span data-ttu-id="d8879-373">Daniela は、Amanda が会議を開催する場合でも、ホワイトボードを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="d8879-373">Daniela can share the whiteboard even if a meeting is organized by Amanda.</span></span>  

### <a name="allow-shared-notes"></a><span data-ttu-id="d8879-374">メモの共有を許可する</span><span class="sxs-lookup"><span data-stu-id="d8879-374">Allow shared notes</span></span>

<span data-ttu-id="d8879-375">これは、ユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="d8879-375">This is a per-user policy.</span></span> <span data-ttu-id="d8879-376">この設定は、ユーザーが会議でメモを作成および共有できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d8879-376">This setting controls whether a user can create and share notes in a meeting.</span></span> <span data-ttu-id="d8879-377">匿名ユーザー、B2B ユーザー、およびフェデレーション ユーザーを含む外部ユーザーは、会議開催者のポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="d8879-377">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> <span data-ttu-id="d8879-378">現在、[**会議メモ**] タブは、参加者が 20 人未満の会議でのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d8879-378">The **Meeting Notes** tab is currently only supported in meetings that have less than 20 participants.</span></span>

<span data-ttu-id="d8879-379">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="d8879-379">Let's look at the following example.</span></span>

|<span data-ttu-id="d8879-380">ユーザー</span><span class="sxs-lookup"><span data-stu-id="d8879-380">User</span></span> |<span data-ttu-id="d8879-381">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="d8879-381">Meeting policy</span></span>  |<span data-ttu-id="d8879-382">メモの共有を許可する</span><span class="sxs-lookup"><span data-stu-id="d8879-382">Allow shared notes</span></span> |
|---------|---------|---------|
|<span data-ttu-id="d8879-383">Daniela</span><span class="sxs-lookup"><span data-stu-id="d8879-383">Daniela</span></span>   | <span data-ttu-id="d8879-384">グローバル</span><span class="sxs-lookup"><span data-stu-id="d8879-384">Global</span></span>   | <span data-ttu-id="d8879-385">True</span><span class="sxs-lookup"><span data-stu-id="d8879-385">True</span></span>       |
|<span data-ttu-id="d8879-386">Amanda</span><span class="sxs-lookup"><span data-stu-id="d8879-386">Amanda</span></span>   | <span data-ttu-id="d8879-387">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="d8879-387">Location1MeetingPolicy</span></span> | <span data-ttu-id="d8879-388">False</span><span class="sxs-lookup"><span data-stu-id="d8879-388">False</span></span> |

<span data-ttu-id="d8879-389">Daniela は Amanda の会議でメモを取ることができ、Amanda はすべての会議でメモを取ることができません。</span><span class="sxs-lookup"><span data-stu-id="d8879-389">Daniela can take notes in Amanda's meetings and Amanda can't take notes in any meetings.</span></span>

## <a name="meeting-policy-settings---participants--guests"></a><span data-ttu-id="d8879-390">会議ポリシーの設定 - 参加者とゲスト</span><span class="sxs-lookup"><span data-stu-id="d8879-390">Meeting policy settings - Participants & guests</span></span>

<span data-ttu-id="d8879-391">これらの設定では、会議への入室が許可されるまでロビーで待機する必要がある会議参加者およびそれらの参加者に許可する会議への参加レベルが制御されます。</span><span class="sxs-lookup"><span data-stu-id="d8879-391">These settings control which meeting participants wait in the lobby before they are admitted to the meeting and the level of participation they are allowed in a meeting.</span></span>

- [<span data-ttu-id="d8879-392">匿名ユーザーが会議を開始できるようにする</span><span class="sxs-lookup"><span data-stu-id="d8879-392">Let anonymous people start a meeting</span></span>](#let-anonymous-people-start-a-meeting)
- [<span data-ttu-id="d8879-393">ユーザーの参加を自動的に許可する</span><span class="sxs-lookup"><span data-stu-id="d8879-393">Automatically admit people</span></span>](#automatically-admit-people)
- [<span data-ttu-id="d8879-394">ダイヤルイン ユーザーによるロビーのバイパスを許可する</span><span class="sxs-lookup"><span data-stu-id="d8879-394">Allow dial-in users to bypass the lobby</span></span>](#allow-dial-in-users-to-bypass-the-lobby)
- [<span data-ttu-id="d8879-395">ライブ キャプションを有効にする</span><span class="sxs-lookup"><span data-stu-id="d8879-395">Enable live captions </span></span>](#enable-live-captions)
- [<span data-ttu-id="d8879-396">会議でチャットを許可する</span><span class="sxs-lookup"><span data-stu-id="d8879-396">Allow chat in meetings </span></span>](#allow-chat-in-meetings)

> [!NOTE]
><span data-ttu-id="d8879-397">会議に参加するためのオプションは、各 Teams グループの設定および接続方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="d8879-397">Options to join a meeting will vary, depending on the settings for each Teams group, and the connection method.</span></span> <span data-ttu-id="d8879-398">グループに電話会議があり、それを使用して接続する場合は、「[Office 365 における電話会議](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8879-398">If your group has audio conferencing, and uses it to connect, see [Audio Conferencing in Office 365](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span></span> <span data-ttu-id="d8879-399">Teams グループに電話会議がない場合は、「[Teams での会議に参加する](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8879-399">If your Teams group does not have audio conferencing, refer to [Join a meeting in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).</span></span>

### <a name="let-anonymous-people-start-a-meeting"></a><span data-ttu-id="d8879-400">匿名ユーザーが会議を開始できるようにする</span><span class="sxs-lookup"><span data-stu-id="d8879-400">Let anonymous people start a meeting</span></span>

<span data-ttu-id="d8879-401">これは開催者単位のポリシーです。</span><span class="sxs-lookup"><span data-stu-id="d8879-401">This is a per-organizer policy.</span></span> <span data-ttu-id="d8879-402">この設定は、認証された組織のユーザーが参加していない場合でも、B2B ユーザーおよびフェデレーション ユーザーなどの匿名ユーザーがユーザーの会議に参加できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d8879-402">This setting controls whether anonymous people, including B2B, and federated users, can join the user's meeting without an authenticated user from the organization in attendance.</span></span> 

![待機中のユーザーへのメッセージが表示されたスクリーンショット](media/meeting-policies-anonymous-user-lobby.png)

<span data-ttu-id="d8879-404">以下は、認証ユーザーが会議に出席しているときの匿名ユーザーの参加動作です。</span><span class="sxs-lookup"><span data-stu-id="d8879-404">Here's the join behavior of anonymous people when authenticated users are present in the meeting.</span></span>

|<span data-ttu-id="d8879-405">匿名ユーザーが会議を開始できるようにする</span><span class="sxs-lookup"><span data-stu-id="d8879-405">Let anonymous people start a meeting</span></span>  |<span data-ttu-id="d8879-406">ユーザーの参加を自動的に許可する</span><span class="sxs-lookup"><span data-stu-id="d8879-406">Automatically admit people</span></span> |<span data-ttu-id="d8879-407">匿名ユーザーの参加動作</span><span class="sxs-lookup"><span data-stu-id="d8879-407">Join behavior of anonymous people</span></span> |
|---------|---------|---------|
|<span data-ttu-id="d8879-408">True</span><span class="sxs-lookup"><span data-stu-id="d8879-408">True</span></span>    | <span data-ttu-id="d8879-409">すべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="d8879-409">Everyone</span></span>      | <span data-ttu-id="d8879-410">直接参加する</span><span class="sxs-lookup"><span data-stu-id="d8879-410">Join directly</span></span>         |
|   | <span data-ttu-id="d8879-411">組織内のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="d8879-411">Everyone in your organization</span></span>       | <span data-ttu-id="d8879-412">ロビーで待つ</span><span class="sxs-lookup"><span data-stu-id="d8879-412">Wait in lobby</span></span>        |
|   | <span data-ttu-id="d8879-413">組織内およびフェデレーション組織のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="d8879-413">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="d8879-414">ロビーで待つ</span><span class="sxs-lookup"><span data-stu-id="d8879-414">Wait in lobby</span></span>         |
|<span data-ttu-id="d8879-415">False</span><span class="sxs-lookup"><span data-stu-id="d8879-415">False</span></span>    | <span data-ttu-id="d8879-416">すべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="d8879-416">Everyone</span></span>        | <span data-ttu-id="d8879-417">直接参加する</span><span class="sxs-lookup"><span data-stu-id="d8879-417">Join directly</span></span>        |
|   | <span data-ttu-id="d8879-418">組織内のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="d8879-418">Everyone in your organization</span></span>     | <span data-ttu-id="d8879-419">ロビーで待つ</span><span class="sxs-lookup"><span data-stu-id="d8879-419">Wait in lobby</span></span>        |
|   | <span data-ttu-id="d8879-420">組織内およびフェデレーション組織のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="d8879-420">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="d8879-421">ロビーで待つ</span><span class="sxs-lookup"><span data-stu-id="d8879-421">Wait in lobby</span></span>         |

<span data-ttu-id="d8879-422">以下は、認証ユーザーが会議に出席していないときの匿名ユーザーの参加動作です。</span><span class="sxs-lookup"><span data-stu-id="d8879-422">Here's the join behavior of anonymous people when no authenticated users are present in the meeting.</span></span>

|<span data-ttu-id="d8879-423">匿名ユーザーが会議を開始できるようにする</span><span class="sxs-lookup"><span data-stu-id="d8879-423">Let anonymous people start a meeting</span></span> |<span data-ttu-id="d8879-424">ユーザーの参加を自動的に許可する</span><span class="sxs-lookup"><span data-stu-id="d8879-424">Automatically admit people</span></span>  |<span data-ttu-id="d8879-425">匿名ユーザーの参加動作</span><span class="sxs-lookup"><span data-stu-id="d8879-425">Join behavior of anonymous people</span></span> |
|---------|---------|---------|
|<span data-ttu-id="d8879-426">True</span><span class="sxs-lookup"><span data-stu-id="d8879-426">True</span></span>    | <span data-ttu-id="d8879-427">すべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="d8879-427">Everyone</span></span>      | <span data-ttu-id="d8879-428">直接参加する</span><span class="sxs-lookup"><span data-stu-id="d8879-428">Join directly</span></span>         |
|   | <span data-ttu-id="d8879-429">組織内のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="d8879-429">Everyone in your organization</span></span>       | <span data-ttu-id="d8879-430">ロビーで待つ</span><span class="sxs-lookup"><span data-stu-id="d8879-430">Wait in lobby</span></span>        |
|   | <span data-ttu-id="d8879-431">組織内およびフェデレーション組織のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="d8879-431">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="d8879-432">ロビーで待つ</span><span class="sxs-lookup"><span data-stu-id="d8879-432">Wait in lobby</span></span>         |
|<span data-ttu-id="d8879-433">False</span><span class="sxs-lookup"><span data-stu-id="d8879-433">False</span></span>    | <span data-ttu-id="d8879-434">すべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="d8879-434">Everyone</span></span>        | <span data-ttu-id="d8879-435">ロビーで待ちます。</span><span class="sxs-lookup"><span data-stu-id="d8879-435">Wait in lobby.</span></span> <span data-ttu-id="d8879-436">最初の認証ユーザーが会議に参加すると、ユーザーは自動的に許可されます。</span><span class="sxs-lookup"><span data-stu-id="d8879-436">Users are automatically admitted when the first authenticated user joins the meeting.</span></span>        |
|   | <span data-ttu-id="d8879-437">組織内のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="d8879-437">Everyone in your organization</span></span>     |<span data-ttu-id="d8879-438">ロビーで待つ</span><span class="sxs-lookup"><span data-stu-id="d8879-438">Wait in lobby</span></span>         |
|   | <span data-ttu-id="d8879-439">組織内およびフェデレーション組織のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="d8879-439">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="d8879-440">ロビーで待つ</span><span class="sxs-lookup"><span data-stu-id="d8879-440">Wait in lobby</span></span>         |

### <a name="automatically-admit-people"></a><span data-ttu-id="d8879-441">ユーザーの参加を自動的に許可する</span><span class="sxs-lookup"><span data-stu-id="d8879-441">Automatically admit people</span></span>

<span data-ttu-id="d8879-442">これは開催者単位のポリシーです。</span><span class="sxs-lookup"><span data-stu-id="d8879-442">This is a per-organizer policy.</span></span> <span data-ttu-id="d8879-443">この設定は、ユーザーが会議に直接参加するのか、認証ユーザーにより入室が許可されるまでロビーで待機するのかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d8879-443">This setting controls whether people join a meeting directly or wait in the lobby until they are admitted by an authenticated user.</span></span>

![ロビーにいるユーザーとの会議を示すスクリーンショット](media/meeting-policies-lobby.png)

 <span data-ttu-id="d8879-445">会議の開催者は、会議出席依頼の [**会議オプション**] をクリックして、スケジュールする会議ごとにこの設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="d8879-445">Meeting organizers can click **Meeting Options** in the meeting invitation to change this setting for each meeting they schedule.</span></span>
  
|<span data-ttu-id="d8879-446">値を設定する</span><span class="sxs-lookup"><span data-stu-id="d8879-446">Setting value</span></span>  |<span data-ttu-id="d8879-447">参加動作</span><span class="sxs-lookup"><span data-stu-id="d8879-447">Join behavior</span></span> |
|---------|---------|
|<span data-ttu-id="d8879-448">**すべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="d8879-448">**Everyone**</span></span>   |<span data-ttu-id="d8879-449">すべての会議参加者は、ロビーで待たずに会議に直接参加します。</span><span class="sxs-lookup"><span data-stu-id="d8879-449">All meeting participants join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="d8879-450">これには、認証ユーザー、フェデレーション ユーザー、ゲスト、匿名ユーザー、およびスマートフォンでダイヤル インするユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d8879-450">This includes authenticated users, federated users, guests, anonymous users, and people who dial in by phone.</span></span>       |
|<span data-ttu-id="d8879-451">**組織内およびフェデレーション組織のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="d8879-451">**Everyone in your organization and federated organizations**</span></span>     |<span data-ttu-id="d8879-452">ゲスト ユーザーやフェデレーション組織のユーザーなど、組織内の認証ユーザーは、ロビーで待たずに会議に直接参加します。</span><span class="sxs-lookup"><span data-stu-id="d8879-452">Authenticated users within the organization, including guest users and the users from federated organizations, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="d8879-453">匿名ユーザーおよびスマートフォンでダイヤル インするユーザーは、ロビーで待機します。</span><span class="sxs-lookup"><span data-stu-id="d8879-453">Anonymous users and users who dial in by phone wait in the lobby.</span></span>   |
|<span data-ttu-id="d8879-454">**組織内のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="d8879-454">**Everyone in your organization**</span></span>    |<span data-ttu-id="d8879-455">ゲスト ユーザーを含む組織内の認証ユーザーは、ロビーで待たずに会議に直接参加します。</span><span class="sxs-lookup"><span data-stu-id="d8879-455">Authenticated users from within the organization, including guest users, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="d8879-456">フェデレーション ユーザー、匿名ユーザー、およびスマートフォンでダイヤル インするユーザーは、ロビーで待機します。</span><span class="sxs-lookup"><span data-stu-id="d8879-456">Federated users, anonymous users, and users who dial in by phone wait in the lobby.</span></span>           |

### <a name="allow-dial-in-users-to-bypass-the-lobby"></a><span data-ttu-id="d8879-457">ダイヤルイン ユーザーによるロビーのバイパスを許可する</span><span class="sxs-lookup"><span data-stu-id="d8879-457">Allow dial-in users to bypass the lobby</span></span>

<span data-ttu-id="d8879-458">これは開催者単位のポリシーです。</span><span class="sxs-lookup"><span data-stu-id="d8879-458">This is a per-organizer policy.</span></span> <span data-ttu-id="d8879-459">この設定では、スマートフォンでダイヤル インするユーザーが会議に直接参加するのか、[**ユーザーの参加を自動的に許可する**] の設定に関わらずロビーで待機するのかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d8879-459">This setting controls whether people who dial in by phone join the meeting directly or wait in the lobby regardless of the **Automatically admit people** setting.</span></span>

<span data-ttu-id="d8879-460">スマートフォンでダイヤル インするユーザーの参加動作は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d8879-460">Here's the join behavior of people who dial in by phone.</span></span>

|<span data-ttu-id="d8879-461">ダイヤルイン ユーザーによるロビーのバイパスを許可する</span><span class="sxs-lookup"><span data-stu-id="d8879-461">Allow dial-in users to bypass the lobby</span></span>  |<span data-ttu-id="d8879-462">ユーザーの参加を自動的に許可する</span><span class="sxs-lookup"><span data-stu-id="d8879-462">Automatically admit people</span></span>  |<span data-ttu-id="d8879-463">ダイヤル インするユーザーの参加動作</span><span class="sxs-lookup"><span data-stu-id="d8879-463">Join behavior of people who dial in</span></span> |
|---------|---------|---------|
|<span data-ttu-id="d8879-464">True</span><span class="sxs-lookup"><span data-stu-id="d8879-464">True</span></span>    | <span data-ttu-id="d8879-465">すべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="d8879-465">Everyone</span></span>      | <span data-ttu-id="d8879-466">直接参加する</span><span class="sxs-lookup"><span data-stu-id="d8879-466">Join directly</span></span>         |
|   | <span data-ttu-id="d8879-467">組織内のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="d8879-467">Everyone in your organization</span></span>       | <span data-ttu-id="d8879-468">直接参加する</span><span class="sxs-lookup"><span data-stu-id="d8879-468">Join directly</span></span>        |
|   | <span data-ttu-id="d8879-469">組織内およびフェデレーション組織のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="d8879-469">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="d8879-470">直接参加する</span><span class="sxs-lookup"><span data-stu-id="d8879-470">Join directly</span></span>         |
|<span data-ttu-id="d8879-471">False</span><span class="sxs-lookup"><span data-stu-id="d8879-471">False</span></span>    | <span data-ttu-id="d8879-472">すべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="d8879-472">Everyone</span></span>        | <span data-ttu-id="d8879-473">直接参加する</span><span class="sxs-lookup"><span data-stu-id="d8879-473">Join directly</span></span>        |
|   | <span data-ttu-id="d8879-474">組織内のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="d8879-474">Everyone in your organization</span></span>     |<span data-ttu-id="d8879-475">ロビーで待つ</span><span class="sxs-lookup"><span data-stu-id="d8879-475">Wait in lobby</span></span>         |
|   | <span data-ttu-id="d8879-476">組織内およびフェデレーション組織のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="d8879-476">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="d8879-477">ロビーで待つ</span><span class="sxs-lookup"><span data-stu-id="d8879-477">Wait in lobby</span></span>         |


### <a name="enable-live-captions"></a><span data-ttu-id="d8879-478">ライブ キャプションを有効にする</span><span class="sxs-lookup"><span data-stu-id="d8879-478">Enable live captions</span></span>

<span data-ttu-id="d8879-479">これはユーザーごとのポリシーであり、会議中に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d8879-479">This is a per-user policy and applies during a meeting.</span></span> <span data-ttu-id="d8879-480">この設定は、ユーザーが参加する会議でライブ キャプションを有効または無効にするために、[**ライブ キャプションを有効にする**] オプションを使用できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d8879-480">This setting controls whether the **Turn on live captions** option is available for the user to turn on and turn off live captions in meetings that the user attends.</span></span>  

![[ライブ キャプションを有効にする] オプションが表示されたスクリーンショット](media/meeting-policies-live-captions.png)

|<span data-ttu-id="d8879-482">値を設定する</span><span class="sxs-lookup"><span data-stu-id="d8879-482">Setting value</span></span> |<span data-ttu-id="d8879-483">動作</span><span class="sxs-lookup"><span data-stu-id="d8879-483">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="d8879-484">**無効になっているが、開催者が上書きできる**</span><span class="sxs-lookup"><span data-stu-id="d8879-484">**Disabled but the organizer can override**</span></span>     | <span data-ttu-id="d8879-485">会議中にユーザーのライブ キャプションが自動的に有効になることはありません。</span><span class="sxs-lookup"><span data-stu-id="d8879-485">Live captions aren't automatically turned on for the user during a meeting.</span></span> <span data-ttu-id="d8879-486">オーバーフロー (**...**) メニューに [**ライブ キャプションを有効にする**] オプションが表示され、それらを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d8879-486">The user sees the **Turn on live captions** option in the overflow (**...**) menu to turn them on.</span></span> <span data-ttu-id="d8879-487">これは、既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="d8879-487">This is the default setting.</span></span> |
|<span data-ttu-id="d8879-488">**無効**</span><span class="sxs-lookup"><span data-stu-id="d8879-488">**Disabled**</span></span>     | <span data-ttu-id="d8879-489">会議中、ユーザーのライブ キャプションが無効になります。</span><span class="sxs-lookup"><span data-stu-id="d8879-489">Live captions are disabled for the user during a meeting.</span></span> <span data-ttu-id="d8879-490">ユーザーには、それらを有効にするオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="d8879-490">The user doesn't have the option to turn them on.</span></span>          |

<span data-ttu-id="d8879-491"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="d8879-491"><a name="bkcontentsharing"> </a></span></span>

### <a name="allow-chat-in-meetings"></a><span data-ttu-id="d8879-492">会議でチャットを許可する</span><span class="sxs-lookup"><span data-stu-id="d8879-492">Allow chat in meetings</span></span>

<span data-ttu-id="d8879-493">これは開催者単位のポリシーです。</span><span class="sxs-lookup"><span data-stu-id="d8879-493">This is a per-organizer policy.</span></span> <span data-ttu-id="d8879-494">この設定は、ユーザーの会議で会議チャットを許可するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d8879-494">This setting controls whether meeting chat is allowed in the user's meeting.</span></span>

<span data-ttu-id="d8879-495"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="d8879-495"><a name="bkparticipantsandguests"> </a></span></span>

## <a name="related-topics"></a><span data-ttu-id="d8879-496">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8879-496">Related topics</span></span>

[<span data-ttu-id="d8879-497">Teams のメッセージング ポリシー</span><span class="sxs-lookup"><span data-stu-id="d8879-497">Messaging policies in Teams</span></span>](messaging-policies-in-teams.md)
